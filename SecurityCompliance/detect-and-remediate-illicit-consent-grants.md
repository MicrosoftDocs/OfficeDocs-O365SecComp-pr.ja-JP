---
title: Microsoft Office 365 での不正な同意付与の検出と修復
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Office 365 で不法な同意を付与する攻撃を認識し、修復する方法について説明します。
ms.openlocfilehash: 1d8df4db94129bcdcb6ecf4859f9f89a1974edbe
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223356"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a>Microsoft Office 365 での不正な同意付与の検出と修復

**概要** Office 365 で不法な同意を付与する攻撃を認識し、修復する方法について説明します。

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Office 365 における不正な同意の付与攻撃
違法同意付与攻撃では、攻撃者は、連絡先情報、電子メール、ドキュメントなどのデータへのアクセスを要求する Azure 登録済みアプリケーションを作成します。その後、攻撃者はエンドユーザーに対して、フィッシング攻撃によるデータへのアクセスを許可するように指示するか、または信頼された web サイトに不法なコードを挿入します。不正なアプリケーションに同意した後は、組織のアカウントを使用しなくても、データへのアカウントレベルのアクセス権が付与されます。違反アカウントのパスワードをリセットしたり、アカウントに多要素認証 (MFA) を必要としたりするなど、通常の修復手順は、この種の攻撃に対しては有効ではありません。これらはサードパーティのアプリケーションであり、組織の外部にあるためです。これらの攻撃は、情報を呼び出しているエンティティが人間ではなく、オートメーションであることを前提とする相互作用モデルを利用します。

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Office 365 のように、不法な同意を与える攻撃はどのようになりますか?
この攻撃の兆候 (IOC) を検出するには、Office 365**監査ログ**を検索する必要があります。Azure に登録されているアプリケーションの数が多く、ユーザーが大規模な組織では、組織の同意の付与を週単位で確認することをお勧めします。
### <a name="steps-for-finding-signs-of-this-attack"></a>この攻撃の兆候を見つけるための手順
1. Office 365 テナントの [**セキュリティとコンプライアンスセンター** ] を開きます。
2. [**検索 & 調査**] ノードに移動して、[**監査ログ**の検索] を選択します。
3. 検索を作成し (すべてのアクティビティとすべてのユーザー)、アプリケーションに対する同意のために結果をフィルター処理して、OAuth2PermissionGrant を追加します。
4. 拡張プロパティを調べ、isadmincontent が True に設定されているかどうかを確認します。


この値が true の場合は、グローバル管理者のアクセス権を持つユーザーがデータへの広範なアクセス権を持っている可能性があることを示します。これが予期しない場合は、[攻撃を確認](detect-and-remediate-illicit-consent-grants.md#confirmattack)するための手順を実行します。

<a name="confirmattack"> </a>
## <a name="how-to-confirm-an-attack"></a>攻撃を確認する方法
上記の IOCs のインスタンスが1つ以上ある場合は、攻撃が発生したことを確認するためにさらに調査する必要があります。これら3つの方法のいずれかを使用して、攻撃を確認できます。
- Azure Active Directory ポータルを使用した、アプリケーションとそのアクセス許可の一覧を示します。この方法は徹底していますが、チェックするユーザーが多い場合は、一度に1人のユーザーをチェックするだけで十分な時間がかかる場合があります。
- PowerShell を使用した、アプリケーションとそのアクセス許可の一覧を示します。これは、最も少ないオーバーヘッドを最小限にした最も高速かつ最も綿密な方法です。
- ユーザーが自分のアプリとアクセス許可を個別に確認して、修復のために管理者に結果を報告するようにします。

## <a name="inventory-apps-with-access-in-your-organization"></a>組織内でアクセスできるインベントリアプリ
これは、Azure Active Directory ポータルまたは PowerShell を使用しているユーザーに対して行うことができます。または、ユーザーがアプリケーションアクセスを個別に列挙する必要があります。

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Azure Active Directory ポータルを使用するための手順
[Azure Active Directory ポータル](https://portal.azure.com/)を使用して、個々のユーザーがアクセス許可を付与したアプリケーションを検索できます。 
1. 管理者権限を使用して Azure Portal にサインインします。
2. Azure Active Directory ブレードを選択します。
3. [ **ユーザー**] を選びます。
4. 確認するユーザーを選択します。
5. [**アプリケーション**] を選択します。

これにより、ユーザーに割り当てられているアプリと、applcations に設定されているアクセス許可が表示されます。

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>ユーザーがアプリケーションアクセスを列挙する手順
ユーザーが自分のアプリケーションhttps://myapps.microsoft.comへのアクセスを確認してもらいます。これらのユーザーは、アクセス可能なすべてのアプリを表示したり、それらに関する詳細を表示したり (アクセスの範囲を含む)、疑わしいまたは不法なアプリに対して権限を取り消すことができます。

### <a name="steps-for-doing-this-with-powershell"></a>PowerShell を使用してこれを行うための手順
不法同意付与攻撃を確認する最も簡単な方法は、 [Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)を実行することです。これにより、テナント内のすべてのユーザーの oauth 承諾許可と oauth アプリがすべて、1つの .csv ファイルにダンプされます。 

#### <a name="pre-requisites"></a>前提条件
- Azure AD PowerShell ライブラリがインストールされていること。
- スクリプトが実行されるテナントのグローバル管理者権限。
- スクリプトを実行するコンピューターのローカル管理者。

> [!IMPORTANT]
> 管理アカウントでは、多要素認証を必要とすることを強くお勧めします。 このスクリプトは、MFA 認証をサポートします。

1. スクリプトを実行するコンピューターに、ローカル管理者権限を使用してサインインします。
2. GitHub から scruipt を実行するフォルダーに[Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)スクリプトをダウンロードするか、コピーします。 これは、出力 "permissions" ファイルが書き込まれるフォルダーと同じです。
3. 管理者として PowerShell インスタンスを開き、スクリプトを保存したフォルダーを開きます。
4. [AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0)コマンドレットを使用して、ディレクトリに接続します。
5. 次のように、この PowerShell コマンドラインを実行します。`Get-AzureADPSPermissions.ps1 | Export-csv -path "Permissions.csv" -NoTypeInformation`

スクリプトによって、Permissions という名前のファイルが1つ作成されます。次の手順に従って、不法なアプリケーションアクセス許可の付与を検索します。 
1. [conな種類] 列 (列 G) で、値 "allprinciples" を検索します。allprincipals アクセス許可によって、クライアントアプリケーションは、テナント内のすべてのユーザーのコンテンツにアクセスできます。ネイティブの Office 365 アプリケーションは、正しく動作するためにこのアクセス許可を必要とします。このアクセス許可を持つ Microsoft 以外のすべてのアプリケーションは、慎重にレビューする必要があります。
2.  [アクセス許可] 列 (列 F) に、各委任されたアプリケーションがコンテンツに対して持っているアクセス許可を確認します。"読み取り" と "書き込み" アクセス許可または "* を探します。All "アクセス許可を使用して、適切ではない可能性があるため慎重に確認してください。
3.  同意が付与されている特定のユーザーを確認します。プロファイルが大きい場合や、影響度の高いユーザーに不適切な同意が付与されている場合は、さらに詳しく調査する必要があります。
4.  [clientdisplayname] 列 (列 C) で、疑わしいと思われるアプリを探します。名前のスペルが間違っているアプリ、super bland names、またはハッカーが発音した名前は、慎重に検討する必要があります。

## <a name="determine-the-scope-of-the-attack"></a>攻撃の範囲を決定する
アプリケーションアクセスのインベントリ処理が終了したら、Office 365**監査ログ**を確認して、違反の完全なスコープを特定します。 影響を受けるユーザー、不法アプリケーションが組織にアクセスした時間枠、およびアプリのアクセス許可を検索します。[Office 365 セキュリティ/コンプライアンスセンター](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)で**監査ログ**を検索できます。 

> [!IMPORTANT]
> この情報を取得するには、攻撃の前に、[管理者とユーザーの](https://support.office.com/article/turn-office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)[メールボックスの監査](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)とアクティビティの監査を有効にする必要があります。

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant--attack"></a>方法不法な同意の付与攻撃を停止および修復する方法
不法なアクセス許可を使用してアプリケーションを識別した後、そのアクセスを削除する方法がいくつかあります。
- Azure Active Directory ポータルのアプリケーションのアクセス許可は、次の方法で取り消すことができます。
    - **Azure Active Directory ユーザー**ブレードの影響を受けるユーザーに移動します。
    - [**アプリケーション**] を選択します。
    - 違法アプリケーションを選択します。
    - ドリルダウンで [**削除**] をクリックします。
- PowerShell で OAuth 同意の付与を取り消すには、 [AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0)の手順に従ってください。
- PowerShell を使用してサービスアプリの役割の割り当てを無効にするには、 [AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0)の手順に従ってください。
- 影響を受けるアカウントのサインインを完全に無効にすることもできます。これにより、そのアカウントのデータに対するアプリのアクセスが無効になります。これは、エンドユーザーの生産性を向上させるのには理想的ではありませんが、影響をすばやく抑えるために作業する場合は、実用的な短期的な修復になります。
- テナントのために統合アプリケーションをオフにすることができます。これは、エンドユーザーがテナント全体に同意を付与する機能を無効にする重大な手順です。これにより、ユーザーが悪意のあるアプリケーションへのアクセスを誤って許可するのを防ぐことができます。これは、ユーザーがサードパーティ製のアプリケーションを使用して生産性を向上させることがひどくないため、強くお勧めしません。 これを行うには、[統合アプリをオンまたはオフ](https://support.office.com/article/Turning-Integrated-Apps-on-or-off-7e453a40-66df-44ab-92a1-96786cb7fb34)にする手順に従ってください。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>cybersecurity pro などの Office 365 の保護
Office 365 サブスクリプションには、データとユーザーを保護するために使用可能な強力なセキュリティ機能のセットが付属しています。「[Office 365 のセキュリティ ロードマップ: 最初の 30 日間、90 日間、およびそれ以後の優先事項](https://support.office.com/article/office-365-security-roadmap-top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)」を使用して、Office 365 テナントをセキュリティで保護するためのマイクロソフト推奨ベスト プラクティスを実践します。
- 最初の 30 日間で完了すべき作業。すぐにユーザーに影響しますが、それほど大きな影響ではありません。
- 最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。
- 90 日以降。最初の 90 日間の作業で保護が強化されます。

## <a name="see-also"></a>関連項目:
- [[自分のアプリケーション] リスト内の予期しないアプリケーション](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)は、データにアクセスするための予期しないアプリケーションがあることを認識した後に、管理者がさまざまなアクションを実行できるようにします。
- [Azure Active Directory とアプリケーションを統合] (https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)は、同意とアクセス許可の概要を示しています。 特別な注意事項については、「[同意フレームワーク」セクションの概要](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#overview-of-the-consent-framework)を参照してください。
- [アプリケーションの開発に関する問題](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)さまざまな同意に関する記事へのリンクを提供します。
- 「 [azure Active Directory のアプリケーションおよびサービスプリンシパルオブジェクト (azure AD)」で](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)は、アプリケーションモデルにとって中核となるアプリケーションおよびサービスプリンシパルオブジェクトの概要を示します。
- アプリへの[アクセスを管理](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)すると、管理者がアプリへのユーザーアクセスを管理するために必要な機能の概要が表示されます。
