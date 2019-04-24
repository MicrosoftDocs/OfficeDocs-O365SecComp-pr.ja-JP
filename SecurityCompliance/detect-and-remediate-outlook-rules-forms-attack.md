---
title: Office 365 で Outlook のルールとユーザー設定フォームの挿入攻撃を検出して修復する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Office 365 で Outlook のルールとユーザー設定フォームのインジェクション攻撃を認識して修復する方法について説明します。
ms.openlocfilehash: 59d45e50e15e3709c8a041ead59b8cc6e2a38306
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256865"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a>Office 365 で Outlook のルールとカスタム フォーム インジェクション攻撃の検出と修復を行う

**概要**Office 365 で Outlook のルールとユーザー設定フォームのインジェクション攻撃を認識して修復する方法について説明します。

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Outlook のルールとユーザー設定フォームの挿入攻撃とは
攻撃者がテナント内のアカウントを侵害してから、を取得した後は、そのアカウントが検出されて削除された後に再び取得する方法を確立しようとしています。 これは、「持続性メカニズムの確立」と呼ばれます。 これを行うには、2つの方法として、outlook のルールを活用するか、outlook にカスタムフォームを挿入します。
どちらの場合も、ルールまたはフォームは cloud service からデスクトップクライアントに同期されるので、クライアントソフトウェアを完全にフォーマットして再インストールしても、挿入メカニズムは不要になります。 これは、Outlook クライアントソフトウェアがクラウド内のメールボックスに再接続すると、そのルールとフォームがクラウドから再ダウンロードされるためです。 ルールとフォームが配置されると、攻撃者はそれらを使用してリモートまたはカスタムのコードを実行します。通常、マルウェアをローカルコンピューターにインストールします。 その後、マルウェアは資格情報を再盗んで、またはその他の不法な動作を実行します。 ここでの朗報は、クライアントの最新バージョンにパッチを適用したままにしておくと、現在の Outlook クライアントの既定では両方のメカニズムをブロックするため、脅威に対して脆弱ではないということです。 

攻撃は通常、次のパターンに従います。

ルールの悪用
1. 攻撃者は、ユーザーの1人のユーザー名とパスワードを盗みます。
2. その後、攻撃者はそのユーザーの Exchange メールボックスにサインインします。 メールボックスは、exchange online または exchange オンプレミスのいずれかにすることができます。
3. その後、攻撃者はメールボックスに、ルールの条件に一致するメールを受信したときにトリガーされる転送ルールを作成します。 ルールの条件とトリガー電子メールの内容は、互いに対して個別に作成されます。
4. 攻撃者は、メールボックスを通常どおりに使用しているユーザーに、トリガーの電子メールを送信します。
5. 電子メールが受信されると、ルールがトリガーされます。 ルールのアクションは、通常、リモート (WebDAV) サーバー上でアプリケーションを起動します。
6. 通常、アプリケーションは、 [Powershell 帝国](https://www.powershellempire.com/)などのマルウェアをユーザーのコンピューターにローカルにインストールします。
7. マルウェアは、攻撃者がユーザーのユーザー名とパスワードまたはその他の資格情報をローカルコンピューターから再利用して、他の悪意のあるアクティビティを実行することを可能にします。

フォームの悪用
1. 攻撃者は、ユーザーの1人のユーザー名とパスワードを盗みます。
2. その後、攻撃者はそのユーザーの Exchange メールボックスにサインインします。 メールボックスは、exchange online または exchange オンプレミスのいずれかにすることができます。
3. その後、攻撃者はカスタムのメールフォームテンプレートを作成し、それをユーザーのメールボックスに挿入します。  ユーザー設定フォームは、メールボックスがユーザー設定フォームを読み込む必要がある電子メールを受信したときにトリガーされます。 ユーザー設定フォームと電子メールの形式は、互いに対してカスタマイズされます。
4. 攻撃者は、自分のメールボックスを通常どおりに使用しているユーザーに、トリガーの電子メールを送信します。
5. 電子メールを受信すると、フォームがロードされます。 フォームは、リモート (WebDAV) サーバー上でアプリケーションを起動します。
6. 通常、アプリケーションは、 [Powershell 帝国](https://www.powershellempire.com/)などのマルウェアをユーザーのコンピューターにローカルにインストールします。
7. マルウェアは、攻撃者がユーザーのユーザー名とパスワードまたはその他の資格情報をローカルコンピューターから再利用して、他の悪意のあるアクティビティを実行することを可能にします。


## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Office 365 のように、ルールおよびユーザー設定フォームの注入攻撃を考えるか

ユーザーがこれらの永続化メカニズムを認識することはほとんどありませんが、場合によっては非表示になることがあります。  この記事では、以下に示す7つの記号 (妥協の兆候) を確認する方法について説明します。 これらのいずれかが見つかった場合は、修復手順を実行する必要があります。

- ルールが侵害されたことを示すインジケーター
    - ルールの処理として、アプリケーションを開始します。
    - ルールは、EXE、ZIP、または URL を参照します。
    - ローカルコンピューターで、Outlook PID から始まる新しいプロセスが開始されているかどうかを確認します。
- ユーザー設定フォームが侵害されたことを示すインジケーター 
    - カスタムフォームは独自のメッセージクラスとして保存されています。
    - メッセージクラスには、実行可能コードが含まれています。
    - 通常、個人用フォームライブラリまたは受信トレイフォルダーに格納されます。
    - Form には、IPM という名前が付けられます。こと.[カスタム名]。

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>この攻撃の兆候を見つけて確認するための手順
この2つの方法のどちらかを使用して、攻撃を確認できます。
- Outlook クライアントを使用して、各メールボックスのルールとフォームを手動でチェックします。  この方法は完全ですが、多くのユーザーが確認できるようにする場合には、メールボックスユーザーを一度にチェックするだけで十分に時間がかかる場合があります。  また、チェックを実行しているコンピューターが侵害されてしまう可能性があります。
- [Get-AllTenantRulesAndForms](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell スクリプトを使用して、テナント内のすべてのユーザーのメール転送ルールおよびカスタムフォームを自動的にダンプします。 これは、最もオーバーヘッドが少ない最も高速で最も安全な方法です。


### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Outlook クライアントを使用してルールが攻撃されたことを確認する
1. ユーザーとしてユーザーの Outlook クライアントを開きます。  ユーザーは、自分のメールボックスのルールを調べるためにヘルプを必要とする場合があります。
2. 2007、2010、または2013バージョンの Outlook でルールのインターフェイスを開く方法の手順については、「[ルールを使用してメールメッセージを管理](https://support.office.com/article/manage-email-messages-by-using-rules-c24f5dea-9465-4df4-ad17-a50704d66c59#ID0EAABAAA=2010)する」を参照してください。
3. ユーザーが作成しなかったルール、または不審な名前のルールがないかどうかを確認します。
4. ルールの説明で、を起動して、アプリケーションまたはを参照するルールの処理を確認します。EXE、。ZIP ファイルを開くか、URL を起動します。
5. Outlook プロセス ID の使用を開始する新しいプロセスを探します。  「[プロセス ID を検索](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)する」を参照してください。

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Outlook クライアントを使用してフォームの攻撃を確認する手順
1. ユーザーとしてユーザーの Outlook クライアントを開きます。
2. の手順に従い、ユーザーのバージョンの Outlook の [[開発] タブを表示](https://support.office.com/article/show-the-developer-tab-e1192344-5e56-4d45-931b-e5fd9bea2d45)します。
3. Outlook で [現在表示されている開発] タブを開き、[**フォームのデザイン**] をクリックします。
4. [**検索**先] の一覧から [**受信トレイ**] を選択します。 ユーザー設定フォームを検索します。  ユーザー設定フォームがある場合は、ユーザー設定フォームを使用するだけで十分な場合があります。
5. 特に非表示に設定されたカスタムフォームを調査します。
6. 任意のユーザー設定フォームを開き、**フォーム**グループの [**コードの表示**] をクリックして、フォームが読み込まれたときに実行される内容を確認します。

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>PowerShell を使用してルールとフォームの攻撃を確認する手順
ルールまたはユーザー設定フォームの攻撃を確認する最も簡単な方法は、 [Get-AllTenantRulesAndForms](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell スクリプトを実行することです。  このスクリプトは、テナント内のすべてのメールボックスに接続し、すべてのルールとフォームを2つの .csv ファイルにダンプします。

#### <a name="pre-requisites"></a>前提条件
スクリプトは、ルールとフォームを読み取るために、テナント内のすべてのメールボックスに接続するため、スクリプトを実行するためのグローバル管理者権限を持っている必要があります。

1. スクリプトを実行するコンピューターに、ローカル管理者権限を使用してサインインします。
2. Get-AllTenantRulesAndForms スクリプトを GitHub から、実行するフォルダーにダウンロードまたはコピーします。  このスクリプトは、2つの日付のスタンプ付きファイルをこのフォルダー、MailboxFormsExport-yyyy-mm-dd、および MailboxRulesExport-yyyy-mm-dd に作成します。
3. 管理者として PowerShell インスタンスを開き、スクリプトを保存したフォルダーを開きます。
4. 次`.\Get-AllTenantRulesAndForms.ps1`のように、この PowerShell コマンドラインを実行します。 .\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>出力の解釈

MailboxRulesExport-*yyyy-mm-dd*-* csv –アプリケーションまたは実行可能ファイルが含まれるアクション条件のルールを調べます (行ごとに1つ)。
- ActionType (列 A) –値 "ID_ACTION_CUSTOM" が表示される場合、そのルールは悪意のある可能性があります。
- [i座 enti] (列 D)-この値が "TRUE" の場合は、ルールが悪意のある可能性があります。
- actioncommand (列 G) –アプリケーションまたは .exe、.zip 拡張子を持つファイル、または URL を参照するファイルがリストに含まれている場合は、そのルールは悪意のある可能性があります。

MailboxFormsExport-*yyyy-mm-dd*-一般に、ユーザー設定フォームの使用は非常にまれです。  このブック内に見つかった場合は、そのユーザーのメールボックスを開き、フォーム自体を調べます。  組織で意図的に配置しなかった場合は、悪意のある可能性があります。



## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Outlook のルールとフォームの攻撃を停止および修復する方法
このような攻撃のいずれかの証拠を見つけた場合は、単にメールボックスからルールまたはフォームを削除するだけで修復が容易になります。 これを行うには、Outlook クライアントまたはリモート PowerShell を使用してルールを削除します。

### <a name="using-outlook"></a>Outlook を使用する
1. ユーザーが Outlook で使用したすべてのデバイスを特定します。  これらはすべて、潜在的なマルウェアを駆除する必要があります。  すべてのデバイスがクリーニングされるまで、ユーザーはサインオンして電子メールを使用できません。
2. 「各デバイスの[ルールを削除する](https://support.office.com/article/Delete-a-rule-2F0E7139-F696-4422-8498-44846DB9067F)」の手順に従います。
3. 他のマルウェアが存在することが不明な場合は、デバイス上のすべてのソフトウェアを書式設定して再インストールすることができます。  モバイルデバイスでは、製造元の手順に従って、デバイスを出荷時イメージにリセットできます。
4. 最新バージョンの Outlook をインストールします。  Outlook の現在のバージョンでは、この両方の種類の攻撃が既定でブロックされることに注意してください。
5. メールボックスのすべてのオフラインコピーが削除されたら、ユーザーのパスワードをリセット (高品質のパスワードを使用) し、MFA がまだ有効になっていない場合は、 [Office 365 ユーザーのセットアップ多要素認証](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)の手順に従います。 これにより、ユーザーの資格情報が他の手段 (フィッシングやパスワードの再利用など) で公開されることがなくなります。

### <a name="using-powershell"></a>PowerShell の使用
危険なルールを削除または無効にするために使用できるリモート PowerShell コマンドレットは2つあります。 手順を実行するだけです。
 
Exchange サーバー上のメールボックスの手順

1. リモート PowerShell を使用して Exchange サーバーに接続します。 [「リモート PowerShell を使用して Exchange サーバーに接続する](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell?view=exchange-ps)」の手順を実行します。
2. 1つのルール、複数のルール、またはメールボックスからのすべてのルールを完全に削除する場合は、[受信トレイルールコマンドレット](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps)を使用します。これを使用して、メールボックスから1つ、複数、またはすべてのルールを完全に削除します。
3. 詳細な調査のためにルールとその内容を保持する場合は、[コマンドレット](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx)を使用します。 

Exchange Online のメールボックスの手順
1. [「PowerShell を使用して Exchange Online に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)」の手順を実行します。
2.  1つのルール、複数のルール、またはメールボックスからすべてのルールを完全に削除するには、 [[受信トレイルールの削除] コマンドレット](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps)を使用します。
3.  詳細な調査のためにルールとその内容を保持する場合は、[コマンドレット](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx)を使用します。 

## <a name="how-to-minimize-future-attacks"></a>今後の攻撃を最小限に抑える方法

### <a name="first-protect-your-accounts"></a>最初: アカウントを保護する

ルールとフォームのエクスプロイトは、攻撃者がユーザーのアカウントのいずれかを盗んだ後、または侵害した後にのみ使用されます。 そのため、これらの悪用を組織に対して使用できないようにするための最初の手順として、ユーザーアカウントを積極的に保護することが挙げられます。  アカウントが侵害される最も一般的な方法には、フィッシングまたは[パスワード spraying](http://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)攻撃があります。



ユーザーアカウントや特に管理者アカウントを保護する最善の方法は、 [Office 365 ユーザーに多要素認証を設定](https://support.office.com/article/set-up-multi-factor-authentication-for-office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)することです。  次のことも実行する必要があります。
<ol>
    <li>ユーザーアカウントがどのようにアクセスされ、<a href="https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports">使用されるかを</a>監視します。 最初の違反を防ぐことはできませんが、期間を短縮して、違反が早く検出された場合の影響を短縮することができます。 次のものを使用できます。 <a href="https://support.office.com/article/overview-of-office-365-cloud-app-security-81f0ee9a-9645-45ab-ba56-de9cbccab475">Office 365 Cloud App Security ポリシー</a>を使用して、アカウントを監視し、異常なアクティビティについての警告を表示することができます。 
        <ol type="a">
            <li><b>複数のログイン試行失敗</b>このポリシーによって、環境がプロファイルされ、ユーザーが1回のセッションで失敗したログインアクティビティを、学習したベースラインに関して複数回実行したときに、違反が発生したことを示すアラートがトリガーされます。</li>
            <li><b>不可能出張</b>-このポリシーでは、環境をプロファイルし、2つの場所間の予定時間よりも短い期間に異なる場所にある同じユーザーからアクティビティが検出されたときにアラートをトリガーします。 これは、別のユーザーが同じ資格情報を使用していることを示している可能性があります。 このような異常動作を検出するには、新しいユーザーのアクティビティパターンを学習させる7日間の最初の学習期間が必要です。</li>
            <li><b>通常は偽装されるアクティビティ (ユーザー別)</b>-このポリシーでは、環境をプロファイルし、ユーザーが学んだ基準に関して1つのセッションで複数の偽装されたアクティビティを実行したときに、違反が発生したことを示すアラートをトリガーします。</li>
        </ol>
    </li>
    <li><a href="https://securescore.office.com/">Office 365 のセキュリティで保護さ</a>れたスコアのようなツールを活用して、アカウントのセキュリティの構成と動作を管理します。 
    </li>
</ol> 

### <a name="second-keep-your-outlook-clients-current"></a>2番目: Outlook クライアントを最新の状態に保ちます
Outlook 2013 の完全に更新されたバージョンとパッチが適用されたバージョン、および2016は、既定で [アプリケーションを開始する] ルール/フォームアクションを無効にします。  これにより、攻撃者がアカウントに違反したとしても、ルールおよびフォームのアクションはブロックされます。  最新の更新プログラムおよびセキュリティ更新プログラムは、「 [Office の更新プログラムをインストール](https://support.office.com/article/Install-Office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)する」の手順に従ってインストールできます。

Outlook 2013 および2016クライアントのパッチバージョンは次のとおりです。
- Outlook 2013: 15.0.4937.1000 またはそれ以上
- Outlook 2016: 16.0.4534.1001 またはそれ以上

個別のセキュリティ修正プログラムの詳細については、以下を参照してください。

- [Outlook 2013 セキュリティパッチ](https://support.microsoft.com/en-us/help/3191938) 
- [Outlook 2016 セキュリティパッチ](https://support.microsoft.com/en-us/help/3191883)

### <a name="third-monitor-your-outlook-clients"></a>3番目: Outlook クライアントを監視する
なお、パッチと更新プログラムがインストールされている場合でも、攻撃者がローカルコンピューターの構成を変更して "アプリケーションを起動する" 動作を再度有効にすることができます。 [高度なグループポリシー管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/)を使用して、クライアントのローカルコンピューターポリシーを監視し、適用することができます。  
[64 ビットバージョンの Windows を使用してシステムレジストリを表示する方法](https://support.microsoft.com/en-us/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows)についての情報を使用して、"Start Application" がレジストリ内の上書きによって再度有効になっているかどうかを確認できます。  次のサブキーをチェックします。 

- Outlook 2016: HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\
- Outlook 2013: HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\

キー EnableUnsafeClientMailRules を探します。 これが存在し、1に設定されている場合は、Outlook セキュリティパッチが上書きされ、コンピューターはフォーム/ルールの攻撃に対して脆弱になります。 値が0の場合、"アプリケーションを起動します" アクションは無効になります。  更新され、パッチされたバージョンの Outlook がインストールされていて、このレジストリキーが存在しない場合、システムはこれらの攻撃に対して脆弱ではありません。

オンプレミスの Exchange インストールを使用しているお客様は、利用可能なパッチを持たない古いバージョンの Outlook をブロックすることを検討する必要があります。 このプロセスの詳細については、記事「 [Outlook クライアントのブロックを構成](https://technet.microsoft.com/en-us/library/dd335207(v=exchg.150).aspx)する」を参照してください。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>cybersecurity pro などの Office 365 の保護
Office 365 サブスクリプションには、データとユーザーを保護するために使用可能な強力なセキュリティ機能のセットが付属しています。「[Office 365 のセキュリティ ロードマップ: 最初の 30 日間、90 日間、およびそれ以後の優先事項](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)」を使用して、Office 365 テナントをセキュリティで保護するためのマイクロソフト推奨ベスト プラクティスを実践します。
- 最初の 30 日間で完了すべき作業。すぐにユーザーに影響しますが、それほど大きな影響ではありません。
- 最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。
- 90 日以降。最初の 90 日間の作業で保護が強化されます。

## <a name="see-also"></a>関連項目:
- 保護された悪意のある[Outlook](https://silentbreaksecurity.com/malicious-outlook-rules/)ルールベクトルに関するセキュリティ投稿ルールベクトルについては、outlook ルールの詳細を確認してください。 
- [MAPI over HTTP および mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on blog for mailrule Pwnage Outlook のルールによってメールボックスを活用するためのルーラーというツールについて説明します。
- フォームの脅威ベクトルに関する、 [office の Outlook フォームおよびシェル](https://sensepost.com/blog/2017/outlook-forms-and-shells/)。 
- [ルーラーコードベース](https://github.com/sensepost/ruler)
- [セキュリティ侵害のルーラーインジケーター](https://github.com/sensepost/notruler/blob/master/iocs.md)