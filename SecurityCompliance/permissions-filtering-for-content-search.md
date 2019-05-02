---
title: コンテンツ検索用にアクセス許可フィルターを設定する
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
description: コンテンツ検索アクセス許可のフィルター処理を使用して、電子情報開示管理者が Office 365 組織内のメールボックスとサイトのサブセットのみを検索できるようにします。
ms.openlocfilehash: 1e12a125390deae60cc8762318b3b6bcf0e6533f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261255"
---
# <a name="configure-permissions-filtering-for-content-search"></a>コンテンツ検索用にアクセス許可フィルターを設定する

検索アクセス許可のフィルター処理を使用して、電子情報開示管理者が Office 365 組織内のメールボックスとサイトのサブセットのみを検索できるようにします。 また、アクセス許可のフィルター処理を使用して、同じ電子情報開示管理者に特定の検索条件を満たすメールボックスやサイトのコンテンツのみを検索させることができます。 たとえば、電子情報開示管理者に特定の場所または部門のユーザーのメールボックスのみを検索させるようにすることができます。 これは、サポートされている受信者のフィルターを使用して、検索できるメールボックスを制限するフィルターを作成することで行います。 検索可能なメールボックスのコンテンツを指定するフィルターを作成することもできます。 これは、検索可能なメッセージ プロパティを使用するフィルターを作成することで行います。 同様に、電子情報開示管理者が組織内の特定の SharePoint サイトのみを検索するようにもできます。 これは、検索可能なサイトを限定するフィルターを作成することで行います。 検索可能なサイトのコンテンツを指定するフィルターを作成することもできます。 これは、検索可能なサイト プロパティを使用するフィルターを作成することで行います。

検索アクセス許可のフィルター処理を使用して、Office 365 の組織内で (*コンプライアンスの境界*と呼ばれる) 論理的境界を作成することもでき、特定の電子情報開示管理者が検索できるユーザー コンテンツの場所 (メールボックス、SharePoint サイト、OneDrive アカウントなど) を管理できます。 詳細については、「[Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する](set-up-compliance-boundaries.md)」を参照してください。
  
検索アクセス許可フィルターは、セキュリティ/コンプライアンス センターのコンテンツ検索機能によりサポートされています。 次の 4 つのコマンドレットを使用して、検索アクセス許可フィルターの構成と管理ができます。
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>始める前に

- コンプライアンス セキュリティ フィルターのコマンドレットを実行するには、セキュリティ/コンプライアンス センターの組織管理の役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。
    
- コンプライアンス セキュリティ フィルターのコマンドレットを使用するには、Windows PowerShell をセキュリティ/コンプライアンス センターとお客様の Exchange Online 組織の両方に接続する必要があります。 これらのコマンドレットはメールボックスのプロパティへのアクセスを必要とするため、Exchange Online に接続する必要があります。 手順については、次のセクションを参照してください。 
    
- アクセス許可の検索フィルターの詳細については、「[More information](#more-information)」セクションを参照してください。 
    
- 検索アクセス許可のフィルター処理は、非アクティブなメールボックスに適用されます。つまり、メールボックスとメールボックス コンテンツのフィルター処理を使用して、非アクティブなメールボックスを検索できるユーザーを制限することができます。 アクセス許可のフィルター処理と非アクティブなメールボックスの詳細については、「[詳細情報](#more-information)」のセクションを参照してください。 
    
-  検索アクセス許可のフィルター処理は、Exchange のパブリック フォルダーを検索できるユーザーを制限するのに使用することができません。 
    
- 組織で作成できる検索アクセス許可フィルターの数に制限はありません。 ただし、検索アクセス許可フィルターが 100 個以上ある場合、検索のパフォーマンスに影響を与えます。 検索の検索アクセス許可フィルターの数を出来るだけ少なくするために、可能な限り、Exchange、SharePoint、および OneDrive のルールを 1 つのフィルターに統合するフィルターを作成するようにします。
    
## <a name="connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>1 つのリモート PowerShell セッションで、セキュリティ/コンプライアンス センターと Exchange Online に接続する

1. ファイル名のサフィックスに .ps1 を使って、次のテキストを Windows PowerShell スクリプト ファイルに保存します。 たとえば、ConnectEXO-CC.ps1 という名前のファイルに保存することができます。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. ローカル コンピューター上で、Windows PowerShell を開き、前の手順で作成したスクリプトが配置されているフォルダーに移動し、スクリプトを実行します。例:
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
これが機能したかどうかを知る方法 スクリプトの実行後に、セキュリティ/コンプライアンス センターと Exchange Online からのコマンドレットは、ローカルの Windows PowerShell セッションにインポートされます。 何もエラーが表示されなければ、正常に接続されています。 簡単に確かめるには、セキュリティ/コンプライアンス センターのコマンドレット (**Install-UnifiedCompliancePrerequisite** など) および Exchange Online のコマンドレット (**Get-Mailbox** など) を実行して結果を確認します。 
  
エラーが表示された場合は、次の要件を確認します。
  
- よく起きる問題がパスワードの入力ミスです。もう一度 2 つのステップを実行します。特に、ステップ 1 ではユーザー名とパスワードを慎重に入力します。
    
- 使用するアカウントに、セキュリティ/コンプライアンス センターにアクセスする権限があることを確認してください。 詳細については、｢[セキュリティ/コンプライアンス センターへのアクセス権をユーザーに付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。
    
- サービス拒否 (DoS) 攻撃を防止するため、セキュリティ/コンプライアンス センターに対して開かれるリモート PowerShell 接続は 3 つまでに制限されます。
    
- スクリプトを実行するためには、Windows PowerShell を構成する必要があります。この設定は、コンピューターで一度だけ構成すれば、接続ごとに行う必要はありません。Windows PowerShell で署名されたスクリプトの実行を有効にするには、管理者特権の Windows PowerShell ウィンドウ ( **[管理者として実行]** を選択すると開く Windows PowerShell ウィンドウ) で次のコマンドを実行します。

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- ローカル コンピューターと Office 365 の間に TCP ポート 80 のトラフィックを開く必要があります。 このポートは多くの場合開いているはずですが、組織で厳格なインターネット アクセス ポリシーが使用されている場合は、念のために確認する必要があります。
    

  
## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter
<a name="New"> </a>

**New-ComplianceSecurityFilter** は新しいアクセス許可の検索フィルターを作成する場合に使用します。 次の表では、このコマンドレットのパラメーターについて説明します。 コンプライアンス セキュリティ フィルターを作成するには、すべてのパラメーターが必要です。 
  
|**パラメーター**|**説明**|
|:-----|:-----|
| _Action_ <br/> | _Action_ パラメーターは、フィルターに適用する検索操作の種類を指定します。 可能なコンテンツ検索操作は次のとおりです。  <br/><br/> **Export** - 検索結果をエクスポートするときに、フィルターが適用されます。  <br/> **Preview** - 検索結果をプレビューするときに、フィルターが適用されます。  <br/> **Purge** - 検索結果を消去するときに、フィルターが適用されます。  <br/> **Search** - 検索を実行するときに、フィルターが適用されます。  <br/> **All** - すべての検索操作に、フィルターが適用されます。  <br/> |
| _FilterName_ <br/> |_FilterName_ パラメーターは、アクセス許可フィルターの名前を指定します。 この名前は、**Get ComplianceSecurityFilter**、**Set-ComplianceSecurityFilter**、および**Remove-ComplianceSecurityFilter** コマンドレットを使用する際に、フィルターを特定するために使用されます。  <br/> |
| _Filters_ <br/> | _Filters_ パラメーターはコンプライアンス セキュリティ フィルターの検索条件を指定します。 次の 3 種類のフィルターを作成できます。  <br/><br/> **メールボックスのフィルター処理** - この種類のフィルターは、割り当てられているユーザー (_Users_ パラメーターで指定) が検索できるメールボックスを指定します。 この種類のフィルターの構文は、**Mailbox_** _MailboxPropertyName_ です。_MailboxPropertyName_ は、検索できるメールボックスの範囲を指定するために使用されるメールボックス プロパティを指定します。 たとえば、メールボックス フィルター `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` は、このフィルターが割り当てられたユーザーに、CustomAttribute10 プロパティの値が "OttawaUsers" のメールボックスのみを検索することを許可します。  <br/>  _MailboxPropertyName_ プロパティには、サポートされているフィルター可能な受信者プロパティであればどれでも使用できます。 サポートされているプロパティの一覧については、「[-RecipientFilter パラメーターのフィルター可能なプロパティ](https://go.microsoft.com/fwlink/p/?LinkId=784903)」を参照してください。  <br/><br/> **メールボックス コンテンツのフィルター処理** - この種類のフィルターは、検索可能なコンテンツに適用されます。 これは、割り当てられたユーザーが検索できるメールボックス コンテンツを指定します。 この種類のフィルターの構文は、**MailboxContent_** _SearchablePropertyName:value_ です。_SearchablePropertyName_ は、コンテンツ検索で指定できるキーワード クエリ言語 (KQL) のプロパティを指定します。 たとえば、メールボックスのコンテンツ フィルター `MailboxContent_recipients:contoso.com` は、このフィルターが割り当てられたユーザーに、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索することを許可します。  <br/>  検索可能なメッセージ プロパティの一覧は、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。  <br/><br/> **サイトおよびサイト コンテンツのフィルタリング** - 割り当てられているユーザーが検索できるサイトまたはサイト コンテンツを指定するのに使用できる SharePoint および OneDrive for Business 関連のフィルターがあります。  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  これら 2 つのフィルターは交換可能です。たとえば `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` と `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` は同じ結果を返します。 しかし、フィルターの役割を理解するため、`Site_` を使用してサイト関連のプロパティ (サイト URL など) を指定し、`SiteContent_` を使用してコンテンツ関連のプロパティ (ドキュメントの種類など) を指定できます。 たとえば、フィルター `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` は、このフィルターが割り当てられたユーザーが、https://contoso.sharepoint.com/sites/doctors サイト コレクション内のコンテンツのみを検索することを許可します。 フィルター `"SiteContent_FileExtension -eq 'docx'"` は、このフィルターが割り当てられたユーザーに、Word 文書 (Word 2007 以降) のみを検索することを許可します。  <br/><br/>  検索可能なサイト プロパティの一覧については、「[ロールされたプロパティと管理プロパティの概要](https://go.microsoft.com/fwlink/p/?LinkId=331599)」を参照してください。 [クエリ可能] 列で [**はい**] とマークされているプロパティを使用して、サイトまたはサイトのコンテンツ フィルターを作成できます。  <br/> <br/> **重要**: 1 つの検索フィルターには、1 種類のフィルターしか含めることができません。つまり、メールボックス フィルターとサイト フィルターを含めることはできません。同様に、メールボックス フィルターとメールボックス コンテンツ フィルターを含めることもできません。 ただし、フィルターには同じ種類のより複雑なクエリを含めることができます。 例: `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` <br/><br/> **重要**: ユーザーが特定の Office 365 サービス内のコンテンツの場所を検索することを明示的に禁止するには (例: Exchange メールボックスや SharePoint サイトなどを検索できないようにする)、検索アクセス許可のフィルターを作成する必要があります。  つまり、組織内のすべての SharePoint サイトをユーザーが検索できるようにする検索権限フィルターを作成しても、そのユーザーはメールボックスを検索できてしまいます。 たとえば、SharePoint 管理者に SharePoint サイトの検索のみを許可するには、メールボックスを検索できなくするフィルターを作成する必要があります。 同様に、Exchange 管理者にメールボックスの検索のみを許可するには、サイトを検索できなくするフィルターを作成する必要があります。           |
| _Users_ <br/> |_Users_ パラメーターは、コンテンツ検索にこのフィルターを適用するユーザーを指定します。 ユーザーのエイリアスまたはプライマリ SMTP アドレスでユーザーを特定します。 カンマで区切って複数の値を指定することも、値 **All** を使用してすべてのユーザーにフィルターを割り当てることもできます。  <br/> _Users_ パラメーターを使用して、セキュリティ/コンプライアンス センターの役割グループを指定することもできます。 これにより、カスタムの役割グループを作成して、その役割グループに検索アクセス許可フィルターを割り当てることができます。 たとえば、多国籍企業の米国支社の電子情報開示管理者向けのカスタムの役割グループがあるとします。 _Users_ パラメーターを使用してこの役割グループを指定してから (役割グループの Name プロパティを使用)、_Filter_ パラメーターを使用して米国内のメールボックスのみを検索できるようにできます。  <br/> このパラメーターでは、配布グループを指定することはできません。  <br/> |
   

## <a name="examples-of-creating-search-permissions-filters"></a>検索アクセス許可フィルターの作成例

以下に、**New-ComplianceSecurityFilter** コマンドレットを使用して検索アクセス許可フィルターを作成する例を示します。 
  
この例では、annb@contoso.com のユーザーはカナダでのメールボックスにのみ、すべてのコンテンツ検索アクションを実行できます。 このフィルターには、ISO 3166 1 からカナダの 3 桁の数値の国コードが含まれています。

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

この例では、eDiscovery Manager 役割グループのメンバーは、Ottawa Users 配布グループのメンバーのメールボックスのみを検索できます。 
  
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
   
この例では、OneDrive 電子情報開示管理者のカスタム役割グループのメンバーは、組織内の OneDrive for Business の場所にあるコンテンツのみを検索できます。

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> ユーザーが検索できるサイトを特定のサイトに制限する場合、上記の例で示すように、フィルター `Site_Path` を使用します。 `Site_Site` を使用することはできません。 
  
この例では、2015 年中に送信されるメール メッセージに対してのみ、すべてのコンテンツ検索アクションを実行するようにユーザーを制限します。

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
前の例と同様に、この例では、ユーザーがすべてのコンテンツ検索の操作を行うことを、2015 年中のいずれかの時点で最後に変更されたドキュメントに制限しています。

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
この例では、"OneDrive Discovery Managers" 役割グループのメンバーが組織のメールボックスでコンテンツ検索アクションを実施できないようにしています。 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```
  
## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter** はアクセス許可の検索フィルターの一覧を返すために使用します。 _FilterName_ パラメーターを使用して、特定の検索フィルターの情報を返します。 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter** は既存のアクセス許可の検索フィルターを変更する場合に使用します。 唯一の必須パラメーターは _FilterName_ です。 
  
|**パラメーター**|**説明**|
|:-----|:-----|
| _Action_| _Action_ パラメーターは、フィルターに適用する検索操作の種類を指定します。 可能なコンテンツ検索操作は次のとおりです。 <br/><br/> **Export** - 検索結果をエクスポートするときに、フィルターが適用されます。  <br/> **Preview** - 検索結果をプレビューするときに、フィルターが適用されます。  <br/> **Purge** - 検索結果を消去するときに、フィルターが適用されます。  <br/> **Search** - 検索を実行するときに、フィルターが適用されます。  <br/> **All** - すべての検索操作に、フィルターが適用されます。  <br/> |
| _FilterName_|_FilterName_ パラメーターは、アクセス許可フィルターの名前を指定します。 |
| _Filters_| _Filters_ パラメーターはコンプライアンス セキュリティ フィルターの検索条件を指定します。 次の 2 種類のフィルターを作成できます。 <br/><br/>**メールボックスのフィルター処理** - この種類のフィルターは、割り当てられているユーザー (_Users_ パラメーターで指定) が検索できるメールボックスを指定します。 この種類のフィルターの構文は、**Mailbox_** _MailboxPropertyName_ です。_MailboxPropertyName_ は、検索できるメールボックスの範囲を指定するために使用されるメールボックス プロパティを指定します。 たとえば、メールボックス フィルター `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` は、このフィルターが割り当てられたユーザーに、CustomAttribute10 プロパティの値が "OttawaUsers" のメールボックスのみを検索することを許可します。  _MailboxPropertyName_ プロパティには、サポートされているフィルター可能な受信者プロパティであればどれでも使用できます。 サポートされているプロパティの一覧については、「[-RecipientFilter パラメーターのフィルター可能なプロパティ](https://go.microsoft.com/fwlink/p/?LinkId=784903)」を参照してください。 <br/><br/>**メールボックス コンテンツのフィルター処理** - この種類のフィルターは、検索可能なコンテンツに適用されます。 これは、割り当てられたユーザーが検索できるメールボックス コンテンツを指定します。 この種類のフィルターの構文は、**MailboxContent_** _SearchablePropertyName:value_ です。_SearchablePropertyName_ は、コンテンツ検索で指定できるキーワード クエリ言語 (KQL) のプロパティを指定します。 たとえば、メールボックスのコンテンツ フィルター `MailboxContent_recipients:contoso.com` は、このフィルターが割り当てられたユーザーに、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索することを許可します。  検索可能なメッセージ プロパティの一覧は、「[コンテンツ検索のキーワード クエリ](keyword-queries-and-search-conditions.md)」を参照してください。 <br/><br/>**サイトおよびサイト コンテンツのフィルタリング** 割り当てられているユーザーが検索できるサイトまたはサイト コンテンツを指定するのに使用できる SharePoint および OneDrive for Business 関連のフィルターがあります。 <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>これら 2 つのフィルターは交換可能です。たとえば `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` と `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` は同じ結果を返します。 しかし、フィルターの役割を理解するため、`Site_` を使用してサイト関連のプロパティ (サイト URL など) を指定し、`SiteContent_` を使用してコンテンツ関連のプロパティ (ドキュメントの種類など) を指定できます。 たとえば、フィルター `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` は、このフィルターが割り当てられたユーザーが、https://contoso.spoppe.com/sites/doctors サイト コレクション内のコンテンツのみを検索することを許可します。 フィルター `"SiteContent_FileExtension -eq 'docx'"` は、このフィルターが割り当てられたユーザーに、Word 文書 (Word 2007 以降) のみを検索することを許可します。  <br/><br/>検索可能なサイト プロパティの一覧については、「[ロールされたプロパティと管理プロパティの概要](https://go.microsoft.com/fwlink/p/?LinkId=331599)」を参照してください。 [**クエリ可能**] 列で [**はい**] とマークされているプロパティを使用して、サイトまたはサイトのコンテンツ フィルターを作成できます。 <br/><br/> **重要**: 1 つの検索フィルターには、1 種類のフィルターしか含めることができません。つまり、メールボックス フィルターとサイト フィルターを含めることはできません。同様に、メールボックス フィルターとメールボックス コンテンツ フィルターを含めることもできません。 ただし、フィルターには同じ種類のより複雑なクエリを含めることができます。 例: `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`          |
| _Users_|_Users_ パラメーターは、コンテンツ検索にこのフィルターを適用するユーザーを指定します。 これは、複数値プロパティであるため、このパラメーターを使って、ユーザーまたはユーザーのグループを指定すると、既存のユーザーのリストが上書きされます。 選択したユーザーを追加および削除するための構文については、次の例を参照してください。 <br/><br/>_Users_ パラメーターを使用して、セキュリティ/コンプライアンス センターの役割グループを指定することもできます。 これにより、カスタムの役割グループを作成して、その役割グループに検索アクセス許可フィルターを割り当てることができます。 たとえば、多国籍企業の米国支社の電子情報開示管理者向けのカスタムの役割グループがあるとします。 _Users_ パラメーターを使用してこの役割グループを指定してから (役割グループの Name プロパティを使用)、_Filter_ パラメーターを使用して米国内のメールボックスのみを検索できるようにできます。 <br/><br/>このパラメーターでは、配布グループを指定することはできません。 |

## <a name="examples-of-changing-search-permissions-filters"></a>検索アクセス許可フィルターの変更例

以下の例では、**Get-ComplianceSecurityFilter** コマンドレットと **Set-ComplianceSecurityFilter** コマンドレットを使用して、フィルターが割り当てられている既存のユーザーの一覧でユーザーを追加または削除する方法について説明します。 ユーザーをフィルターに追加またはフィルターから削除する場合は、SMTP アドレスを使用してユーザーを指定します。 
  
この例では、フィルターにユーザーを追加します。

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
  
## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

**Remove-ComplianceSecurityFilter** は検索フィルターを削除する場合に使用します。 _FilterName_ パラメーターを使用して、削除するフィルターを指定します。 
  
## <a name="more-information"></a>詳細情報

- **検索アクセス許可のフィルター処理のしくみ。** アクセス許可のフィルターは、コンテンツ検索が実行されると、検索クエリに追加されます。 アクセス許可のフィルターは基本的に、**AND** ブール演算子によって検索クエリに結合されます。 たとえば、Bob に Workers 配布グループのメンバーのメールボックスですべての検索操作の実行を許可するアクセス許可フィルターがあるとします。 Bob は、検索クエリ `sender:jerry@adatum.com` を使用して、組織内のすべてのメールボックスでコンテンツ検索を実行したとします。 アクセス許可フィルターと検索クエリは **AND** 演算子で論理的に結合されているため、検索では jerry@adatum.com から Workers 配布グループの任意のメンバーに送信されたすべてのメッセージが返されます。 
    
- **複数の検索アクセス許可フィルターがある場合。** コンテンツ検索クエリでは、複数のアクセス許可フィルターは **OR** ブール演算子によって結合されます。 したがって、フィルターのいずれかに該当する場合に結果が返されます。 コンテンツ検索では、(**OR** 演算子によって結合された) すべてのフィルターが、**AND** 演算子によって検索クエリと結合されます。 Bob に Workers 配布グループのメンバーのメールボックスのみを検索することを許可する、前述の例を使います。 次に、Bob が Phil のメールボックスを検索することを防止する別のフィルターを作成します ("Mailbox_Alias -ne 'Phil'")。 また、Phil が Workers グループのメンバーであると仮定してみましょう。 Bob が組織内のすべてのメールボックスに対して、前の例のコンテンツ検索を実行すると、Bob が Phil のメールボックスを検索できないようにするフィルターを適用していたにもかかわらず、Phil のメールボックスについての検索結果が返されます。 これは、Bob に Workers グループを検索することを許可する最初のフィルターに該当しているからです。 また、Phil が Workers グループのメンバーであるため、Bob は Phil のメールボックスを検索できます。 
    
- **非アクティブなメールボックスで検索アクセス許可のフィルター処理は動作しますか。** はい、メールボックスとメールボックス コンテンツのフィルター処理を使用して、組織の非アクティブなメールボックスを検索できるユーザーを制限することができます。 通常のメールボックスのように、非アクティブなメールボックスは、アクセス許可のフィルターを作成するのに使用される受信者プロパティで設定する必要があります。 必要に応じて、**Get-Mailbox -InactiveMailboxOnly** コマンドを使用して非アクティブなメールボックスのプロパティを表示することができます。 詳細については、「[Office 365 の非アクティブなメールボックスの作成と管理](create-and-manage-inactive-mailboxes.md)」を参照してください。
    
- **パブリック フォルダーで検索アクセス許可のフィルター処理は動作しますか。** いいえ。 上で説明したように、検索アクセス許可のフィルター処理は、Exchange のパブリック フォルダーを検索できるユーザーを制限する目的には使用できません。 たとえば、パブリック フォルダーの場所にあるアイテムは、アクセス許可のフィルターによって、検索結果から除外することができません。 
    
- **特定のサービスのすべてのコンテンツの場所をユーザーが検索できるようにした場合、ユーザーは他のサービスのコンテンツの場所を検索できないようになりますか。** いいえ。 上で説明したように、ユーザーが特定の Office 365 サービス内のコンテンツの場所を検索することを明示的に禁止するには (例: Exchange メールボックスや SharePoint サイトなどを検索できないようにする)、検索アクセス許可のフィルターを作成する必要があります。  つまり、組織内のすべての SharePoint サイトをユーザーが検索できるようにする検索権限フィルターを作成しても、そのユーザーはメールボックスを検索できてしまいます。 たとえば、SharePoint 管理者に SharePoint サイトの検索のみを許可するには、メールボックスを検索できなくするフィルターを作成する必要があります。 同様に、Exchange 管理者にメールボックスの検索のみを許可するには、サイトを検索できなくするフィルターを作成する必要があります。
