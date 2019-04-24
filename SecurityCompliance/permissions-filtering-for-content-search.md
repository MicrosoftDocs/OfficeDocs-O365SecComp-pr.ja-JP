---
title: コンテンツ検索用にアクセス許可フィルターを構成する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/14/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: コンテンツ検索のアクセス許可フィルターを使用して、電子情報開示マネージャーが Office 365 組織のメールボックスとサイトのサブセットのみを検索できるようにします。
ms.openlocfilehash: 1e12a125390deae60cc8762318b3b6bcf0e6533f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261255"
---
# <a name="configure-permissions-filtering-for-content-search"></a>コンテンツ検索用にアクセス許可フィルターを設定する

検索アクセス許可フィルターを使用して、電子情報開示マネージャーが Office 365 組織のメールボックスとサイトのサブセットのみを検索できるようにすることができます。 アクセス許可フィルターを使用して、同じ電子情報開示管理者が特定の検索条件を満たすメールボックスまたはサイトのコンテンツをだけを検索できるようにすることもできます。 たとえば、電子情報開示管理者が、特定の場所または部門内のユーザーのメールボックスのみを検索できるようにします。 これを行うには、サポートされている受信者フィルターを使用して、検索対象となるメールボックスを制限するフィルターを作成します。 どのメールボックスのコンテンツを検索できるかを指定するフィルターを作成することもできます。 これを行うには、検索可能なメッセージ プロパティを使用するフィルターを作成します。 同様に、電子情報開示マネージャーが組織内の特定の SharePoint サイトのみを検索できるようにすることもできます。 これを行うには、検索対象とするサイトを制限するフィルターを作成します。 また、どのようなサイト コンテンツを検索できるかを指定するフィルターを作成することも可能です。 これを行うには、検索可能なサイト プロパティを使用するフィルターを作成します。

また、検索アクセス許可フィルターを使用して、Office 365 組織内で、ユーザーのコンテンツの場所 (メールボックス、SharePoint サイト、OneDrive アカウントなど) を制御する、(*コンプライアンス境界*と呼ばれる) 論理的な境界を作成することもできます。特定の電子情報開示マネージャーが検索できる。 詳細については、「 [Office 365 で電子情報開示の調査のためにコンプライアンスの境界を設定する](set-up-compliance-boundaries.md)」を参照してください。
  
検索アクセス許可フィルターは、セキュリティ & コンプライアンスセンターのコンテンツ検索機能でサポートされています。 次の4つのコマンドレットを使用すると、検索 permisisons フィルターを構成および管理できます。
  
[new-compliancesecurityfilter](#new-compliancesecurityfilter)

[new-compliancesecurityfilter](#get-compliancesecurityfilter)

[new-compliancesecurityfilter](#set-compliancesecurityfilter)

[new-compliancesecurityfilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>開始する前に

- コンプライアンスセキュリティフィルターコマンドレットを実行するには、security & コンプライアンスセンターで、組織の管理役割グループのメンバーである必要があります。 詳細については、「 [Security & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。
    
- コンプライアンスセキュリティフィルターコマンドレットを使用するには、Windows PowerShell を Security & コンプライアンスセンターと Exchange Online 組織の両方に接続する必要があります。 これは、これらのコマンドレットがメールボックスのプロパティにアクセスする必要があるためです。これは、Exchange Online に接続するために必要になります。 次のセクションの手順を参照してください。 
    
- アクセス許可の検索フィルターの詳細については、「[More information](#more-information)」セクションを参照してください。 
    
- 検索アクセス許可フィルターは、非アクティブなメールボックスに適用されます。つまり、メールボックスとメールボックスのコンテンツフィルターを使用して、非アクティブなメールボックスを検索できるユーザーを制限することができます。 アクセス許可のフィルターおよび非アクティブなメールボックスの詳細については、「 [More information](#more-information) 」セクションを参照してください。 
    
-  検索アクセス許可フィルターを使用して、Exchange のパブリックフォルダーを検索できるユーザーを制限することはできません。 
    
- 組織内で作成できる検索アクセス許可フィルターの数に制限はありません。 ただし、100を超える検索アクセス許可フィルターがある場合は、検索のパフォーマンスが影響を受けます。 組織内の検索アクセス許可のフィルターの数を可能な限り小さくするには、可能な限り、Exchange、SharePoint、および OneDrive のルールを1つのフィルターにまとめるフィルターを作成します。
    
## <a name="connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>1つのリモート PowerShell セッションでセキュリティ & コンプライアンスセンターおよび Exchange Online に接続する

1. ファイル拡張子 .ps1 の Windows PowerShell スクリプト ファイルに以下のテキストを保存します。 たとえば、ConnectEXO-CC.ps1 という名前のファイルに保存することができます。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. ローカルコンピューターで、Windows PowerShell を開き、前の手順で作成したスクリプトが置かれているフォルダーに移動して、スクリプトを実行します。例えば：
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
これが正常に機能したことを確認するにはどうすればよいですか。 スクリプトを実行すると、Security & コンプライアンスセンターおよび Exchange Online のコマンドレットがローカルの Windows PowerShell セッションにインポートされます。 何もエラーが表示されなければ、正常に接続されています。 クイックテストでは、Security & コンプライアンスセンターコマンドレット (たとえば、 **UnifiedCompliancePrerequisite** ) と、Exchange Online コマンドレット (たとえば、**メールボックスの取得**) を実行することができます。 
  
エラーが表示された場合は、次の要件を確認します。
  
- よく起きる問題がパスワードの入力ミスです。もう一度 2 つのステップを実行します。特に、ステップ 1 ではユーザー名とパスワードを慎重に入力します。
    
- セキュリティ & コンプライアンスセンターにアクセスするためのアクセス許可がアカウントに付与されていることを確認します。 詳細については、「[ユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。
    
- サービス拒否 (DoS) 攻撃を防止するため、Security & コンプライアンスセンターに対して開かれるリモート PowerShell 接続は3つまでに制限されています。
    
- スクリプトを実行するためには、Windows PowerShell を構成する必要があります。この設定は、コンピューターで一度だけ構成すれば、接続ごとに行う必要はありません。Windows PowerShell で署名されたスクリプトの実行を有効にするには、管理者特権の Windows PowerShell ウィンドウ ( **[管理者として実行]** を選択すると開く Windows PowerShell ウィンドウ) で次のコマンドを実行します。

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- ローカル コンピューターと Office 365 の間に TCP ポート 80 のトラフィックを開く必要があります。 組織で厳格なインターネット アクセス ポリシーが使用されている場合は、開いている可能性がありますが、確認する必要があります。
    

  
## <a name="new-compliancesecurityfilter"></a>new-compliancesecurityfilter
<a name="New"> </a>

新しい検索権限フィルターを作成するには、 **new-compliancesecurityfilter**を使用します。 次の表では、このコマンドレットのパラメーターについて説明します。 コンプライアンス セキュリティ フィルターを作成するには、すべてのパラメーターが必要です。 
  
|**パラメーター**|**説明**|
|:-----|:-----|
| _Action_ <br/> | _Action_パラメーターは、フィルターを適用する検索アクションの種類を指定します。 考えられるコンテンツ検索アクションは次のとおりです。  <br/><br/> **Export** -検索結果をエクスポートするときに、フィルターが適用されます。  <br/> **プレビュー** -検索結果をプレビューするときに、フィルターが適用されます。  <br/> **Purge** -検索結果の削除時にフィルターが適用されます。  <br/> **検索**-検索を実行すると、フィルターが適用されます。  <br/> **all** -すべての検索操作にフィルターが適用されます。  <br/> |
| _FilterName_ <br/> |_FilterName_パラメーターは、アクセス許可フィルターの名前を指定します。 この名前は、**Get-ComplianceSecurityFilter**、**Set-ComplianceSecurityFilter**、および **Remove-ComplianceSecurityFilter** コマンドレットを使用する場合にフィルターを識別するのに使用します。  <br/> |
| _Filters_ <br/> | _Filters_パラメーターは、コンプライアンスセキュリティフィルターの検索条件を指定します。 次の 3 種類のフィルターを作成できます。  <br/><br/> **メールボックスフィルター** -この種類のフィルターでは、( _users_パラメーターで指定された) 割り当てられたユーザーが検索できるメールボックスを指定します。 この種類のフィルターの構文は**Mailbox_** _MailboxPropertyName_です。ここで、 _MailboxPropertyName_では、検索可能なメールボックスの範囲を設定するために使用されるメールボックスのプロパティを指定しています。 たとえば、メールボックスフィルター `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`では、このフィルターを割り当てられたユーザーが、CustomAttribute10 プロパティに "ottawausers" という値を持つメールボックスのみを検索できるようになります。  <br/>  _MailboxPropertyName_プロパティには、サポートされているすべてのフィルター可能な受信者プロパティを使用できます。 サポートされているプロパティの一覧については、「[フィルター可能なプロパティの-受信者フィルターパラメーター](https://go.microsoft.com/fwlink/p/?LinkId=784903)」を参照してください。  <br/><br/> **メールボックスコンテンツフィルター** -この種類のフィルターは、検索可能なコンテンツに適用されます。 割り当てられたユーザーが検索できるメールボックスの内容を指定します。 この種類のフィルターの構文は**MailboxContent_** _searchablepropertyname: value_です。ここで、 _searchablepropertyname_は、コンテンツ検索で指定できるキーワードクエリ言語 (kql) プロパティを指定します。 たとえば、メールボックスのコンテンツフィルター `MailboxContent_recipients:contoso.com`を使用すると、このフィルターを割り当てられたユーザーは、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索できます。  <br/>  検索可能なメッセージプロパティの一覧については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。  <br/><br/> **サイトおよびサイトコンテンツのフィルター処理**: 割り当てられたユーザーが検索できるサイトまたはサイトコンテンツを指定するために使用できる SharePoint および OneDrive for business のサイト関連のフィルターが2つあります。  <br/><br/> - **Site_**_SearchableSiteProperty_ <br/> - **SiteContent_**_SearchableSiteProperty_ <br/><br/>  これら2つのフィルターは相互交換可能です。たとえば`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` 、 `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`は同じ結果を返します。 ただし、フィルターの機能を識別するのに役立つように`Site_` 、を使用してサイト関連のプロパティ (サイト URL など) `SiteContent_`を指定し、コンテンツ関連のプロパティ (ドキュメントの種類など) を指定することができます。 たとえば、フィルター `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`を適用すると、このフィルターを割り当てられたユーザーは、 https://contoso.sharepoint.com/sites/doctorsサイトコレクション内のコンテンツのみを検索できるようになります。 `"SiteContent_FileExtension -eq 'docx'"`このフィルターを使用すると、このフィルターを割り当てられたユーザーが word 文書の検索のみを行うことができます (word 2007 以降)。  <br/><br/>  検索可能なサイトプロパティの一覧については、「SharePoint のクロールされ[たプロパティと管理プロパティの概要](https://go.microsoft.com/fwlink/p/?LinkId=331599)」を参照してください。 * * クエリ可能な * * 列で**Yes**が設定されているプロパティを使用して、サイトまたはサイトコンテンツフィルターを作成できます。  <br/> <br/> **重要:** 1つの検索フィルターに設定できるフィルターの種類は1つだけです。メールボックスフィルターとサイトフィルターを含めることはできません。同様に、メールボックスフィルターとメールボックスのコンテンツフィルターを含めることはできません。 ただし、フィルターには同じ型のより複雑なクエリを含めることができます。 たとえば、  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` です。 <br/><br/> **重要:** ユーザーが特定の Office 365 サービスでコンテンツの場所を検索できないようにするには、検索アクセス許可フィルターを作成する必要があります (たとえば、ユーザーが Exchange メールボックスまたは任意の SharePoint サイトを検索できないようにする)。 言い換えると、ユーザーが組織内のすべての SharePoint サイトを検索できるようにする検索アクセス許可フィルターを作成しても、そのユーザーはメールボックスを検索できません。 たとえば、sharepoint 管理者のみが sharepoint サイトを検索できるようにするには、メールボックスの検索を禁止するフィルターを作成する必要があります。 同様に、Exchange 管理者がメールボックスのみを検索できるようにするには、サイトの検索を禁止するフィルターを作成する必要があります。           |
| _Users_ <br/> |_users_パラメーターには、コンテンツ検索に適用するこのフィルターを取得するユーザーを指定します。 ユーザーをエイリアスまたはプライマリ SMTP アドレスで識別します。 コンマで区切られた複数の値を指定するか、値 **All** を使用してフィルターをすべてのユーザーに割り当てることができます。  <br/> また、 _Users_パラメーターを使用して、セキュリティ & コンプライアンスセンターの役割グループを指定することもできます。 これにより、カスタム役割グループを作成してから、アクセス許可の検索フィルターをその役割グループに割り当てることができます。 たとえば、ある多国籍企業の米国の子会社に在籍する電子情報開示管理者を対象としたカスタム役割グループがあるとします。 この役割グループを指定するには、_ユーザー_パラメーターを使用します (役割グループの Name プロパティを使用)。次に、 _Filter_パラメーターを使用して、米国のメールボックスのみを検索できるようにします。  <br/> このパラメーターで配布グループを指定することはできません。  <br/> |
   

## <a name="examples-of-creating-search-permissions-filters"></a>検索アクセス許可のフィルターを作成する例

以下に、**New-ComplianceSecurityFilter** コマンドレットを使用してアクセス許可の検索フィルターを作成する例を示します。 
  
この例では、ユーザー annb@contoso.com がカナダのメールボックスに対してのみ、すべてのコンテンツ検索アクションを実行できるようにします。 このフィルターには、ISO 3166-1 でカナダを表す 3 桁の数値の国コードが含まれています。

```
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

この例では、ユーザー donh および suzanf は、CustomAttribute1 メールボックス プロパティの値が 'Marketing' であるメールボックスのみを検索できます。

```
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```
   
この例では、"US Discovery Managers" 役割グループのメンバーが、米国内のメールボックスにのみ、すべてのコンテンツ検索アクションを実行できます。このフィルターには、ISO 3166-1 で米国を表す 3 桁の数値の国コードが含まれています。
  
```
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

この例の割り当てでは、電子情報開示管理者の役割グループのメンバーは、Ottawa Users 配布グループのメンバーのメールボックスのみを検索できます。 
  
```
$DG = Get-DistributionGroup "Ottawa Users"
```

```
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```
この例では、すべてのユーザーが Executive Team 配布グループのメンバーのメールボックスからコンテンツを削除することを禁止します。

```
$DG = Get-DistributionGroup "Executive Team"
```

```
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users all -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```
   
この例では、onedrive eDiscovery Managers カスタム役割グループのメンバーは、組織内の onedrive for business の場所にあるコンテンツのみを検索できます。

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> ユーザーが特定のサイトのみを検索できるように`Site_Path`するには、前の例のようにフィルターを使用します。 を`Site_Site`使用しても動作しません。 
  
この例では、2015 年中に送信されるメール メッセージに対してのみ、すべてのコンテンツ検索アクションを実行するようにユーザーを制限します。

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
この例では、前述の例と同じように、最後に変更されたのが 2015 年中であるドキュメントに対してのみ、すべてのコンテンツ検索アクションを実行するようにユーザーを制限します。

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
この例では、"OneDrive Discovery Managers" 役割グループのメンバーが組織内のどのメールボックスでもコンテンツ検索アクションを実行できないようにします。 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```
  
## <a name="get-compliancesecurityfilter"></a>new-compliancesecurityfilter

**new-compliancesecurityfilter**は、検索アクセス許可フィルターの一覧を返すために使用されます。 特定の検索フィルターの情報を取得するには、 _FilterName_パラメーターを使用します。 
  
## <a name="set-compliancesecurityfilter"></a>new-compliancesecurityfilter

**new-compliancesecurityfilter**は、既存の検索アクセス許可フィルターを変更するために使用されます。 唯一必要なパラメーターは_FilterName_です。 
  
|**パラメーター**|**説明**|
|:-----|:-----|
| _Action_| _Action_パラメーターは、フィルターを適用する検索アクションの種類を指定します。 考えられるコンテンツ検索アクションは次のとおりです。 <br/><br/> **Export** -検索結果をエクスポートするときに、フィルターが適用されます。  <br/> **プレビュー** -検索結果をプレビューするときに、フィルターが適用されます。  <br/> **Purge** -検索結果の削除時にフィルターが適用されます。  <br/> **検索**-検索を実行すると、フィルターが適用されます。  <br/> **all** -すべての検索操作にフィルターが適用されます。  <br/> |
| _FilterName_|_FilterName_パラメーターは、アクセス許可フィルターの名前を指定します。 |
| _Filters_| _Filters_パラメーターは、コンプライアンスセキュリティフィルターの検索条件を指定します。 次の 2 種類のフィルターを作成できます。 <br/><br/>**メールボックスフィルター** -この種類のフィルターでは、( _users_パラメーターで指定された) 割り当てられたユーザーが検索できるメールボックスを指定します。 この種類のフィルターの構文は**Mailbox_** _MailboxPropertyName_です。ここで、 _MailboxPropertyName_では、検索可能なメールボックスの範囲を設定するために使用されるメールボックスのプロパティを指定しています。 たとえば、メールボックスフィルター `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`では、このフィルターを割り当てられたユーザーが、CustomAttribute10 プロパティに "ottawausers" という値を持つメールボックスのみを検索できるようになります。  _MailboxPropertyName_プロパティには、サポートされているすべてのフィルター可能な受信者プロパティを使用できます。 サポートされているプロパティの一覧については、「[フィルター可能なプロパティの-受信者フィルターパラメーター](https://go.microsoft.com/fwlink/p/?LinkId=784903)」を参照してください。 <br/><br/>**メールボックスコンテンツフィルター**-この種類のフィルターは、検索可能なコンテンツに適用されます。 割り当てられたユーザーが検索できるメールボックスの内容を指定します。 この種類のフィルターの構文は**MailboxContent_** _searchablepropertyname: value_です。ここで、 _searchablepropertyname_は、コンテンツ検索で指定できるキーワードクエリ言語 (kql) プロパティを指定します。 たとえば、メールボックスのコンテンツフィルター `MailboxContent_recipients:contoso.com`を使用すると、このフィルターを割り当てられたユーザーは、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索できます。  検索可能なメッセージプロパティの一覧については、「[コンテンツ検索のキーワードクエリ](keyword-queries-and-search-conditions.md)」を参照してください。 <br/><br/>**サイトおよびサイトコンテンツのフィルター処理**割り当てられたユーザーが検索できるサイトまたはサイトコンテンツを指定するには、次の2つの SharePoint および OneDrive for business のサイト関連フィルターを使用できます。 <br/><br/>- **Site_***SearchableSiteProperty* <br/>- **sitecontent**_ の**<br/><br/>これら2つのフィルターは相互交換可能です。たとえば`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 、 `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`は同じ結果を返します。 ただし、フィルターの機能を識別するのに役立つように`Site_` 、を使用してサイト関連のプロパティ (サイト URL など) `SiteContent_`を指定し、コンテンツ関連のプロパティ (ドキュメントの種類など) を指定することができます。 たとえば、フィルター `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`を適用すると、このフィルターを割り当てられたユーザーは、 https://contoso.spoppe.com/sites/doctorsサイトコレクション内のコンテンツのみを検索できるようになります。 `"SiteContent_FileExtension -eq 'docx'"`このフィルターを使用すると、このフィルターを割り当てられたユーザーが word 文書の検索のみを行うことができます (word 2007 以降)。  <br/><br/>検索可能なサイトプロパティの一覧については、「SharePoint のクロールされ[たプロパティと管理プロパティの概要](https://go.microsoft.com/fwlink/p/?LinkId=331599)」を参照してください。 [**クエリ**可能] 列で **[はい]** が設定されているプロパティを使用して、サイトまたはサイトコンテンツフィルターを作成できます。 <br/><br/> **重要:** 1つの検索フィルターに設定できるフィルターの種類は1つだけです。メールボックスフィルターとサイトフィルターを含めることはできません。同様に、メールボックスフィルターとメールボックスのコンテンツフィルターを含めることはできません。 ただし、フィルターには同じ型のより複雑なクエリを含めることができます。 たとえば、  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` です。          |
| _Users_|_users_パラメーターには、コンテンツ検索に適用するこのフィルターを取得するユーザーを指定します。 これは、複数値プロパティであるため、このパラメーターを使用してユーザーまたはユーザーのグループを指定すると、既存のユーザーの一覧は上書きされます。 選択したユーザーを追加および削除するための構文については、次の例を参照してください。 <br/><br/>また、 _Users_パラメーターを使用して、セキュリティ & コンプライアンスセンターの役割グループを指定することもできます。 これにより、カスタム役割グループを作成してから、アクセス許可の検索フィルターをその役割グループに割り当てることができます。 たとえば、ある多国籍企業の米国の子会社に在籍する電子情報開示管理者を対象としたカスタム役割グループがあるとします。 この役割グループを指定するには、_ユーザー_パラメーターを使用します (役割グループの Name プロパティを使用)。次に、 _Filter_パラメーターを使用して、米国のメールボックスのみを検索できるようにします。 <br/><br/>このパラメーターで配布グループを指定することはできません。 |

## <a name="examples-of-changing-search-permissions-filters"></a>検索アクセス許可のフィルターの変更例

次の例は、 **new-compliancesecurityfilter**コマンドレットおよび**new-compliancesecurityfilter**コマンドレットを使用して、フィルターが割り当てられているユーザーの既存のリストに対してユーザーを追加または削除する方法を示しています。 フィルターでユーザーを追加または削除するときは、SMTP アドレスを使用してユーザーを指定します。 
  
以下の例では、フィルターにユーザーを追加します。

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```
```
$filterusers.users.add("pilarp@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
   
以下の例では、フィルターからユーザーを削除します。

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```
$filterusers.users.remove("annb@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
  
## <a name="remove-compliancesecurityfilter"></a>new-compliancesecurityfilter

**new-compliancesecurityfilter**は、検索フィルターを削除するために使用されます。 削除するフィルターを指定するには、 _FilterName_パラメーターを使用します。 
  
## <a name="more-information"></a>詳細情報

- **検索アクセス許可のフィルター処理のしくみ** アクセス許可フィルターは、コンテンツ検索が実行されたときに検索クエリに追加されます。 アクセス許可フィルターは基本的に、 **and**ブール演算子によって検索クエリに結合されます。 たとえば、Bob がワーカー配布グループのメンバーのメールボックスに対してすべての検索操作を実行できるようにするアクセス許可フィルターがあるとします。 その後、Bob は検索クエリ`sender:jerry@adatum.com`を使用して組織内のすべてのメールボックスでコンテンツ検索を実行します。 アクセス許可フィルターと検索クエリは論理的に**and**演算子で組み合わされているため、検索によって、jerry@adatum.com によって送信されたすべてのメッセージがワーカー配布グループのメンバーに返されます。 
    
- **複数のアクセス許可の検索フィルターが存在する場合** コンテンツ検索クエリでは、複数のアクセス許可のフィルターは **OR** ブール演算子によって結合されます。 このため、フィルターのいずれかが当てはまる場合に結果が返されます。 コンテンツ検索では、すべてのフィルター (**OR** 演算子で結合) は、**AND** 演算子によって検索クエリと結合されます。 前述の例、つまり Bob が Workers 配布グループのメンバーのメールボックスのみを検索できるようにする検索フィルターについて考えてみましょう。 今回は、Bob が Phil のメールボックス ("Mailbox_Alias-ne 'Phil'") を検索できないようにする別のフィルターを作成します。 さらに、Phil が Workers グループのメンバーであると仮定します。 bob が組織内のすべてのメールボックスでコンテンツ検索 (前の例では) を実行すると、フィルターを適用して、bob が Phil のメールボックスを検索しないようにした場合でも、Phil のメールボックスに対して検索結果が返されます。 これは、1 番目のフィルター (Bob が Workers グループを検索できるようにする) に該当するためです。 Phil が Workers グループのメンバーであるため、Bob はPhil のメールボックスを検索することができます。 
    
- **検索アクセス許可のフィルター処理は、非アクティブなメールボックスに対して機能しますか?** はい。メールボックスとメールボックスのコンテンツフィルターを使用して、組織内の非アクティブなメールボックスを検索できるユーザーを制限することができます。 通常のメールボックスと同様に、非アクティブなメールボックスは、アクセス許可フィルターの作成に使用される受信者プロパティを使用して構成する必要があります。 必要に応じて、**メールボックス-inactivemailboxonly**コマンドを使用して、非アクティブなメールボックスのプロパティを表示することができます。 詳細については、「 [Office 365 の非アクティブなメールボックスの作成と管理](create-and-manage-inactive-mailboxes.md)」を参照してください。
    
- **検索アクセス許可のフィルター処理はパブリックフォルダーに対して機能しますか?** いいえ。 前述のように、検索アクセス許可フィルターを使用して、Exchange のパブリックフォルダーを検索できるユーザーを制限することはできません。 たとえば、パブリックフォルダーの場所にあるアイテムは、アクセス許可フィルターによって検索結果から除外することはできません。 
    
- **特定のサービス内のすべてのコンテンツの場所をユーザーが検索できるようにすることで、別のサービスにあるコンテンツの場所を検索できなくなりますか。** いいえ。 前述したように、検索アクセス許可フィルターを作成して、ユーザーが特定の Office 365 サービス内のコンテンツの場所を検索できないようにする必要があります (たとえば、ユーザーが Exchange メールボックスまたは任意の SharePoint サイトを検索できないようにする)。 言い換えると、ユーザーが組織内のすべての SharePoint サイトを検索できるようにする検索アクセス許可フィルターを作成しても、そのユーザーはメールボックスを検索できません。 たとえば、sharepoint 管理者のみが sharepoint サイトを検索できるようにするには、メールボックスの検索を禁止するフィルターを作成する必要があります。 同様に、Exchange 管理者がメールボックスのみを検索できるようにするには、サイトの検索を禁止するフィルターを作成する必要があります。
