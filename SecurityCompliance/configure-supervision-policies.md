---
title: 組織用に監督ポリシーを構成する
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 監督機関による監査ポリシーを設定すると、確認のため、従業員の通信をキャプチャします。
ms.openlocfilehash: 898ef9951ea20dec1e0cc6c28ad1ed6f9a0ded6e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29768038"
---
# <a name="configure-supervision-policies-for-your-organization"></a>組織用に監督ポリシーを構成する

監督ポリシーを使用すると、内部または外部の校閲者による、従業員の通信をキャプチャします。監督のポリシーが、組織内の通信の監視にどのように役立つかについての詳細については、 [Office 365 での監視ポリシー](supervision-policies.md)を参照してください。

> [!NOTE]
> 監督ポリシーで監視対象のユーザーは、準拠の高度なアドオンをいずれかの Office 365 エンタープライズ E3 ライセンスを取得する必要がありますか、Office 365 エンタープライズ E5 のサブスクリプションに含まれます。しない既存のエンタープライズ E5 計画して監視を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。
  
設定し、Office 365 の組織の監視を使用してこれらの手順に従います。
  
- **手順 (省略可能) 1** - [監督のグループを設定します](configure-supervision-policies.md#exampledist)

    監督の使用を開始する前に、ユーザーは、通信内容を確認し、それらのレビューを実行する人を決定します。監督の動作を確認するのには、いくつかのユーザーを開始する場合は、ここではグループの設定を省略できます。

- **手順 2 (必須)** - [監督は、組織で使用可能なを作成します。](configure-supervision-policies.md#MakeAvailable)

    自身に追加、監督機関による監査の役割のグループ ポリシーを設定することができますように。このロールが割り当てられているを持つ任意のユーザー ページにアクセスできます、**監督****データの管理**下にあるセキュリティ & コンプライアンス センターで。情報を確認する電子メールが Exchange のオンラインでホストされている場合は、その各校閲者が[Exchange Online にリモート PowerShell のアクセス](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)できる必要があります。

- **手順 3 (省略可能)** - [の構成機密情報のカスタム型またはカスタム キーワード辞書と辞書](configure-supervision-policies.md#sensitiveinfo)

    監督ポリシーの機密情報のカスタム型またはカスタム キーワードの辞書を使用する場合は、監督のウィザードを開始する前に作成する必要があります。

- **手順 4 (必須)** - [監督のポリシーを設定します。](configure-supervision-policies.md#setupsuper)

    セキュリティ & コンプライアンス センターでは、監督のポリシーを作成します。これらのポリシーでは、通信は、組織の見直しの対象とし、レビューを実行する必要がありますを指定を定義します。電子メール、マイクロソフトのチームのコミュニケーションと Facebook、Twitter など) などのサード パーティ プラットフォームの通信の通信が含まれます

- **手順 5: (省略可能)**[新しい監視ポリシーのテスト](configure-supervision-policies.md#TestPolicy)

    コンプライアンス戦略、標準を満たすことができることを保証する重要な部分は、必要に応じて、それが機能しているかどうかを確認するのには、監督のポリシーをテストします。

- **ステップ 6 - (省略可能)**[Outlook アドインを Office 365 の監視のダッシュ ボードや通信のコールを管理するには、OWA を使用しない場合の校閲者の設定](configure-supervision-policies.md#UseOutlook)

    監視アドインを Outlook のレビュー担当者にアクセスできます Outlook クライアントの監視機能の右を評価し、各項目を分類することができます。

<a name="exampledist"> </a>

## <a name="step-1---set-up-groups-for-supervision-optional"></a>ステップ 1 - (省略可能) の監視のグループを設定

 監督ポリシーを作成する場合、通信の確認を持って、それらのレビューを実行する人を決定します。ポリシーでは、個人またはグループのユーザーを識別するのに電子メール アドレスを使用します。セットアップを簡略化するのには、通信が確認されたユーザーのグループとは、それらの通信を確認するユーザーのグループを作成します。グループを使用している場合、いくつかを必要があります-たとえば、人の 2 つの異なるグループ間の通信を監視する場合、または管理するしようとしていないグループを指定する場合は、します。このしくみの詳細については、[配布グループの使用例](configure-supervision-policies.md#GroupExample)を参照してください。
  
Exchange 管理センターで配布グループを設定します間または組織内のグループ内での通信を監督する (**受信者**に\>**グループ**)。配布グループを設定する方法の詳細については、[配布グループの管理](http://go.microsoft.com/fwlink/?LinkId=613635)を参照してください。
  
> [!NOTE]
> 使用できます動的配布グループまたはセキュリティ グループを監督したい場合。組織に合わせてこれらかどうかを判断するには、必要があります、[メールが有効なセキュリティ グループの管理](http://go.microsoft.com/fwlink/?LinkId=627033)、および[動的配布グループの管理](http://go.microsoft.com/fwlink/?LinkId=627058)を参照してください。
  
<a name="GroupExample"> </a>

### <a name="example-distribution-groups"></a>配布グループの例

この例には、contoso 社の財務国際と呼ばれる、金融機関に設定されている配布グループが含まれます。
  
Contoso Financial International では、米国のブローカー間の通信のサンプリングを監視する必要があります。しかし、そのグループ内の法令遵守責任者を監視する必要はありません。この例の場合、次のグループを作成できます。
  
|**セットアップする配布グループ**|**グループのアドレス (エイリアス)**|**説明**|
|:-----|:-----|:-----|
|米国のブローカー全員 | US_Brokers@Contoso.com | このグループには Contoso に勤務し米国を拠点とするブローカー全員の電子メール アドレスが含まれています。 |
| 米国の法令遵守責任者全員 | US_Compliance@Contoso.com  | このグループには、contoso 社のすべての英語ベースのコンプライアンス担当者の電子メール アドレスが含まれます。このグループがすべての米国のブローカーのサブセットであるため、監督のポリシーから控除コンプライアンス責任者にこのエイリアスを使用できます。 |
  
<a name="MakeAvailable"> </a>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a>ステップ 2 - (必須)、組織で利用可能な Make の監督

**監督**として使用するメニュー オプション セキュリティ & コンプライアンス センターは、監督者の確認の管理者の役割を割り当てる必要があります。
  
これを行うには、監督機関による監査の役割グループのメンバーとして追加自分でするか、新しい役割グループを作成することができます。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>監督機関による監査の役割グループにメンバーを追加します。

1. サインイン[https://protection.office.com](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。

2. セキュリティ & コンプライアンス センターでは、**アクセス許可**に移動します。

3. **監督機関による監査**の役割グループを選択し、編集アイコンをクリックします。

4. [**メンバー** ] セクションでは、組織の監督を管理する人を追加します。

### <a name="create-a-new-role-group"></a>新しい役割グループを作成します。

1. サインイン[https://protection.office.com](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。

2. セキュリティ & コンプライアンス センターでは、**アクセス許可**に移動し、し、[追加] をクリックして (**+**)。

3. [**役割**] セクションの [追加] をクリックします (**+**) をスクロールして [**レビュー管理者を監督**します。この役割を役割グループに追加します。

4. [**メンバー** ] セクションでは、組織の監督を管理する人を追加します。

役割グループおよびアクセス許可の詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>(Exchange Online でメールがホストされている) 場合、校閲者の PowerShell のリモート アクセスを有効にします。

1. [有効にするか Exchange のオンライン PowerShell へのアクセスを無効にする](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)の指示に従います。

<a name="sensitiveinfo"> </a>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a>手順 3 - (省略可能) カスタムの機密性の高い情報の種類やキーワードのカスタム辞書を作成

既存のユーザー設定の機密性の高い情報の種類または監視ポリシー ウィザードでは、キーワードのカスタム辞書を選択するためにまず必要な場合にこれらの項目を作成する必要があります。

### <a name="create-custom-sensitive-information-types"></a>カスタムの機密性の高い情報の種類を作成します。

1. Office 365 のセキュリティ & コンプライアンス センターでは、新しい種類の機密情報を作成します。**分類**に移動\>**機密性の高い情報の種類****機密性の高い情報の種類の新規作成ウィザード**の手順に従います。ここで行います。

    - 機密性の高い情報の種類の説明と名前を定義します。
    - 近接、信頼レベル、および主なパターン要素を定義します。
    - 選択内容を確認し、機密性の高い情報の種類を作成

    詳細な情報は、[機密情報のカスタム タイプを作成する](create-a-custom-sensitive-information-type.md)を参照してください。

### <a name="create-custom-keyword-dictionarylexicon"></a>カスタム キーワード辞書と用語集を作成します。

1. テキスト エディター (メモ帳など) を使用すると、監督のポリシーで監視するにはキーワードの用語を含む新しいファイルを作成します。別の行には、各用語かどうかを確認し、 **Unicode と utf-16 (リトルエンディアン)** 形式でファイルを保存します。
2. PowerShell を使用して、Office 365 テナントには、キーワードのファイルをインポートします。PowerShell で Office 365 に接続するには、 [Office 365 のセキュリティ & コンプライアンス センター PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)を参照してください。

    PowerShell で Office 365 に接続した後、キーワードの辞書をインポートするのには次のコマンドを実行します。

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    詳細な情報は、[キーワード辞書を作成する](create-a-keyword-dictionary.md)を参照してください。

3. Office 365 のセキュリティ & コンプライアンス センターでは、新しい種類の機密情報を作成します。**分類**に移動\>**機密性の高い情報の種類****機密性の高い情報の種類の新規作成ウィザード**の手順に従います。ここで行います。

    - 機密性の高い情報の種類の説明と名前を定義します。
    - 一致する要素の要件として、ユーザー辞書を追加します。
    - 選択内容を確認し、機密性の高い情報の種類を作成

    ユーザー辞書と辞書が作成されると、 [Get DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)コマンドレットを使用して構成されているキーワードを表示またはを追加したり[セット DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)コマンドレットを使用して条件を削除します。

    詳細な情報は、[機密情報のカスタム タイプを作成する](create-a-custom-sensitive-information-type.md)を参照してください。

<a name="setupsuper"> </a>

## <a name="step-4---set-up-a-supervision-policy-required"></a>ステップ 4 - (必須) の監視ポリシーを設定します。
  
1. サインイン[https://protection.office.com](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。

2. セキュリティ & コンプライアンス センターでは、**監督**を選択します。
  
3. **作成**] を選択し、ウィザードで、ポリシーの以下のページを設定します。ウィザードを使用すると、次の操作を行います。

    - 名前と説明は、ポリシーを提供します。
    - ユーザーまたはグループを除外するかを選択するなど、監督には、ユーザーまたはグループを選択します。
    - 監督のポリシーの条件を定義します。
    - 機密性の高い情報の種類を含めるかを選択します。これは、既定およびカスタムの機密性の高い情報の種類を選択できます。
    - 確認するのには通信の割合を定義します。
    - ポリシーのレビュー担当者を選択します。レビュー担当者は、個々 のユーザーまたは[メールが有効なセキュリティ グループ](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)にあります。
    - ポリシー選択内容を確認し、ポリシーを作成します。

<a name="TestPolicy"> </a>

## <a name="step-5---test-your-supervision-policy-optional"></a>手順 5: (省略可能)、監督ポリシーをテストします。

監督ポリシーを作成した後に定義した条件は、ポリシーによって正しく強制されているかどうかを確認するテストすることをお勧めです。することも[、データ損失防止 (DLP) のポリシーをテスト](create-test-tune-dlp-policy.md)する場合は、監督のポリシーには、機密性の高い情報の種類が含まれます。監督ポリシーをテストするのには、次の手順に従います。

1. 開いている電子メール クライアント、またはマイクロソフトのチーム、コールを管理のユーザーとしてログインをテストするポリシーで定義されています。
2. 電子メールまたは監督のポリシーで定義した条件に適合するマイクロソフトのチーム チャットを送信します。キーワード、添付ファイルのサイズ、ドメインなどを指定できます。かどうか、ポリシーで構成されている条件付き設定は制限が多すぎてまたは寛大すぎると判断したことを確認します。

    > [!Note]
    > 定義されているポリシーの対象となるメールはほぼリアルタイムで処理され、ポリシーを構成した後すぐにテストすることができます。マイクロソフトのチームでのチャットは、ポリシーに完全に処理するのには最大 24 時間かかります。 

3. 監督のポリシーで指定されているレビュー担当者として、Office 365 のテナントにログインします。**監督**に移動 > *、カスタム ポリシー* > **オープン**ポリシーのレポートを表示します。

<a name="UseOutlook"> </a>

## <a name="step-6---set-up-outlook-add-in-for-reviewers-optional"></a>ステップ 6 - Outlook 用のアドインのレビュー担当者を設定する (省略可能)

通信を確認するのには、監督でダッシュ ボードまたは web 上の Outlook の Office 365 を使用する代わりに Outlook を使用する校閲者は、自分の Outlook クライアントの監視アドインをインストールしなければなりません。

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>監督のメールボックスのアドレスをコピーする手順 1。

Outlook デスクトップ用のアドインをインストールするには、監督のポリシー設定の一部として作成された監督のメールボックスのアドレスを必要があります。
  
> [!NOTE]
> だれかそれ以外の場合、ポリシーを作成する場合は、アドインをインストールするのにはこれらのファイルからこのアドレスを取得する必要があります。

 **監督のメールボックスのアドレスを検索するには**
  
1. サインイン、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。

2. **監督**に移動します。

3. 監督ポリシーを確認する通信を収集する] をクリックします。

4. ポリシーの詳細フライアウトの**メールボックスの監督**の下で、アドレスをコピーします。<br/>![監督ポリシーの詳細のフライアウトが強調表示されている監督のメールボックスのアドレスが表示されているの「メールボックスの監視」セクション](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a>ステップ 2: Outlook デスクトップからのアクセスの監視のメールボックスを構成します。

次に、校閲者は、監督のメールボックスを Outlook に接続するためにはいくつかの Exchange のオンラインの PowerShell コマンドを実行する必要があります。
  
1. オンライン PowerShell を交換するために接続します。[これはどのようにしますか?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. *SupervisoryReview{GUID}@domain.onmicrosoft.com*が、上記の手順 1 でコピーしたアドレスであり、*ユーザー*は、手順 3 で監督のメールボックスに接続する人の校閲者の名前を次のコマンドを実行します。

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. 以下の手順 3 移動する前に 1 時間以上まで待機します。

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>監督のメールボックスに接続する Outlook プロファイルを作成する手順 3。

最後の手順では、校閲者は、監督のメールボックスに接続する Outlook プロファイルを作成する必要があります。

> [!NOTE]
> 新しい Outlook プロファイルを作成するには、Windows コントロール パネルの [メールの設定を使用します。これらの設定を取得するためのパスは、Windows オペレーティング システム (Windows 7、Windows 8 の場合、または Windows の 10) を使用して、Outlook のバージョンがインストールされているによって異なります。
  
1. [コントロール パネル] を開き、ウィンドウの上部にある [**検索**] ボックスで**メール**を入力します。<br/>(されないことを確認してコントロール パネルを取得する方法ですか。参照してください[場所は、コントロール パネルの [?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))
  
2. **メール**アプリケーションを開きます。

3. **メール設定 - Outlook****プロファイルの表示**をクリックします。<br/>![' メール設定 - Outlook] ダイアログ ボックスに、プロファイルの表示] ボタンがハイライトされます](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. [**メール**] の [**追加**を] をクリックします。**新しいプロファイル**(**監督**) などの監督のメールボックスの名前を入力します。<br/>!['監督' の名前を示す、[プロファイル名] ボックスで [新しいプロファイル] ダイアログ ボックス](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. **Outlook に接続**、**別のアカウントへの接続**をクリックします。<br/>![強調表示されている別のアカウントへ接続] リンクを使用して Office 365 に Outlook を接続する ' メッセージ](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. **自動アカウント セットアップ**では、**手動設定] または [その他のサーバー**を選択し、[**次へ**] をクリックします。

7. **アカウント タイプの選択**] では、 **Office 365**を選択します。**電子メール アドレス**] ボックスで、以前にコピーした監督のメールボックスのアドレスを入力します。<br/>![強調表示されている [電子メール アドレス] ボックスを表示する Outlook の [アカウントの追加] ダイアログ ボックスの ' のアカウントの種類の選択] ページです。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. ダイアログ ボックスが表示されたら、Office 365 のユーザーの資格情報を入力します。

9. 成功すると、表示されます、**監督 -\<ポリシー名\>** フォルダーが Outlook のフォルダー一覧ビューで表示します。

## <a name="powershell-reference"></a>PowerShell の参照

必要な場合は、作成し、次の PowerShell コマンドレットを使用して監視ポリシーを管理します。

- [新しい-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [Get SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [セット SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [削除 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [新しい-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [セット SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [Get SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [Get SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [Get SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)