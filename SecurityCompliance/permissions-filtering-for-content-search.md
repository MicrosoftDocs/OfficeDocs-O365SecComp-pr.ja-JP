---
title: コンテンツ検索用にアクセス許可フィルターを構成する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/14/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: 電子的証拠開示マネージャーが、Office 365 の組織内のメールボックス、およびサイトのサブセットのみを検索、フィルタ リング、コンテンツの検索のアクセス許可を使用します。
ms.openlocfilehash: 2b6968a097e7abe5943a84b9ceb9b6d126057cc2
ms.sourcegitcommit: c166964fe14eec69139a2d3d9c10d2c40ab33f91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258625"
---
# <a name="configure-permissions-filtering-for-content-search"></a>コンテンツ検索用にアクセス許可フィルターを構成する

検索アクセス権を電子的証拠開示マネージャーが、Office 365 の組織内のメールボックス、およびサイトのサブセットのみを検索するフィルタ リングを使用することができます。その同じ電子的証拠開示マネージャーが特定の検索条件に一致するメールボックスまたはサイトのコンテンツだけを検索するフィルタ リングのアクセス許可を使用することもできます。など、電子的証拠開示マネージャーが特定の場所または部門のユーザーのメールボックスのみを検索するようにする可能性があります。サポートされている受信者のフィルターを使用してメールボックスを検索することができますを制限するフィルターを作成するこれを行います。メールボックス コンテンツを検索対象を指定するフィルターを作成することもできます。これは、は、検索可能なメッセージのプロパティを使用するフィルターを作成することによって行われます。同様に、組織内でのみ特定の SharePoint サイトを検索する、電子的証拠開示マネージャーを使用可能性があります。サイトを検索することができますを制限するフィルターを作成するこれを行います。どのようなサイトのコンテンツを検索対象を指定するフィルターを作成することもできます。これは、は、検索可能なサイトのプロパティを使用するフィルターを作成することによって行われます。

境界を作成する論理 (*コンプライアンスの境界*と呼ばれる)、Office 365 の組織内でユーザー コンテンツの場所 (メールボックス、SharePoint サイトでは、OneDrive アカウントなど) を制御するフィルタ リング検索のアクセス許可を使用することもあります。特定の電子的証拠開示マネージャーが検索できます。詳細については、[電子的証拠開示の調査では、Office 365 のコンプライアンスの境界の設定](set-up-compliance-boundaries.md)を参照してください。
  
Office 365 のセキュリティ、コンテンツの検索機能で検索アクセス権をフィルタ リングがサポートされている&amp;コンプライアンス センターです。これら 4 つのコマンドレットでは、構成および permisisons の検索フィルターを管理できます。
  
[新しい-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[セット ComplianceSecurityFilter](#set-compliancesecurityfilter)

[削除 ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>はじめに

- コンプライアンス セキュリティ フィルターのコマンドレットを実行するには、セキュリティで組織の管理役割グループのメンバーである必要がある&amp;コンプライアンス センターです。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。
    
- 両方のセキュリティを保護する Windows PowerShell を接続する必要が&amp;コンプライアンス センターおよびコンプライアンス セキュリティ フィルターのコマンドレットを使用する Exchange Online 組織にします。これらのコマンドレットは、Exchange Online に接続する必要がある理由は、メールボックスのプロパティへのアクセスを必要とするために必要です。次のセクションで手順を参照してください。 
    
- アクセス許可の検索フィルターの詳細については、「[More information](#more-information)」セクションを参照してください。 
    
- フィルタ リング検索のアクセス許可は、メールボックスとメールボックスの内容を非アクティブなメールボックスを検索することができますユーザーを制限するフィルターを使用することを意味する、非アクティブなメールボックスに適用されます。フィルタ リングのアクセス許可とアクティブでないメールボックスに関する追加情報の[詳細について](#more-information)はを参照してください。 
    
-  フィルタ リング検索のアクセス許可は、Exchange パブリック フォルダーを検索することができますを制限するのには使用できません。 
    
- 組織で作成することができます検索のアクセス許可のフィルターの数に制限はありません。ただし、100 以上の検索のアクセス許可のフィルターがある場合に検索のパフォーマンスが低下します。できるだけ小さく、組織内のアクセス許可の検索フィルターの数を保持するには、Exchange、SharePoint、および OneDrive の可能な限り 1 つのフィルターの規則を結合するフィルターを作成します。
    
## <a name="connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>セキュリティへの接続&amp;コンプライアンス センターおよびリモート PowerShell セッションを 1 つで Exchange のオンライン

1. .Ps1 のファイル名のサフィックスを使用して、Windows PowerShell スクリプト ファイルに次のテキストを保存します。などの ConnectEXO CC.ps1 をという名前のファイルに保存する可能性があります。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. ローカル コンピューターに Windows PowerShell を開く前の手順で作成したスクリプトがある場所のフォルダーに移動し、スクリプトを実行し、例えば：
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
知るかどうかは次のとおりですか。セキュリティのコマンドレット、スクリプトを実行した後に&amp;コンプライアンス センターおよび Exchange Online は、ローカルの Windows PowerShell セッションにインポートします。エラーを受信しない場合、接続に成功しました。簡単なテストは、セキュリティを実行する&amp;コンプライアンス センター コマンドレット:**インストール UnifiedCompliancePrerequisite**などの — と**Get メールボックス**などの Exchange Online のコマンドレット。 
  
エラーが表示された場合は、次の要件を確認します。
  
- よく起きる問題がパスワードの入力ミスです。もう一度 2 つのステップを実行します。特に、ステップ 1 ではユーザー名とパスワードを慎重に入力します。
    
- 自分のアカウントへのセキュリティのアクセス許可があることを確認&amp;コンプライアンス センターです。詳細については、「[のセキュリティにアクセスできるように&amp;コンプライアンス センター](grant-access-to-the-security-and-compliance-center.md)です。
    
- 3 つ開いているリモート PowerShell への接続、セキュリティに制限されているサービス拒否 (DoS) 攻撃を防ぐため、&amp;コンプライアンス センターです。
    
- スクリプトを実行するためには、Windows PowerShell を構成する必要があります。この設定は、コンピューターで一度だけ構成すれば、接続ごとに行う必要はありません。Windows PowerShell で署名されたスクリプトの実行を有効にするには、管理者特権の Windows PowerShell ウィンドウ ( **[管理者として実行]** を選択すると開く Windows PowerShell ウィンドウ) で次のコマンドを実行します。

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- TCP ポート 80 のトラフィックをローカル コンピューターと Office 365 の間で開いている必要があります。開いている可能性がありますが、組織には、制限の厳しいインターネット アクセス ポリシーを考慮する何か。
    

  
## <a name="new-compliancesecurityfilter"></a>新しい-ComplianceSecurityFilter
<a name="New"> </a>

**新規 ComplianceSecurityFilter**を使用して、新しい検索のアクセス許可フィルターを作成します。次の表では、このコマンドレットのパラメーターについて説明します。コンプライアンス セキュリティ フィルターを作成するには、すべてのパラメーターが必要です。 
  
|**パラメーター**|**説明**|
|:-----|:-----|
| _操作_ <br/> | _アクション_パラメーターは、フィルターを適用する検索操作の種類を指定します。コンテンツの検索操作を行うことは次のとおりです。<br/><br/> **エクスポート**- フィルターは、検索結果をエクスポートするときに適用されます。  <br/> **プレビュー**のフィルターは、検索結果をプレビューする際に適用されます。  <br/> **パージ**・ フィルターは、検索結果を削除するときに適用されます。  <br/> **検索**- フィルターは、検索を実行するときに適用されます。  <br/> すべてのアクションを検索する**すべて**のフィルターが適用されます。  <br/> |
| _フィルター名_ <br/> |_フィルター名_のパラメーターは、アクセス許可のフィルターの名前を指定します。この名前は、 **Get ComplianceSecurityFilter**、 **ComplianceSecurityFilter ・ セット、** および**削除 ComplianceSecurityFilter**コマンドレットを使用する場合、フィルターをユーザーに使用します。<br/> |
| _フィルター_ <br/> | _フィルター_パラメーターは、コンプライアンス ・ セキュリティ ・ フィルターの検索条件を指定します。3 つの異なる種類のフィルターを作成できます。<br/><br/> **メールボックスがフィルター処理**のこの種のフィルター (_ユーザー_のパラメーターで指定) 割り当てられているユーザーが検索できるメールボックスを指定します。この種類のフィルターの構文は、 **Mailbox_** _MailboxPropertyName_、 _MailboxPropertyName_が検索できるメールボックスの範囲を使用するメールボックスのプロパティを指定します。メールボックスのフィルターでは、`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`は、ユーザーにのみ値を持つメールボックスを検索するには、このフィルター「OttawaUsers」が割り当てられた、CustomAttribute10 プロパティにします。<br/>  _MailboxPropertyName_プロパティには、任意のサポートされているフィルターの受信者プロパティを使用できます。サポートされているプロパティのリストは、 [- RecipientFilter パラメーターのフィルターのプロパティ](https://go.microsoft.com/fwlink/p/?LinkId=784903)を参照してください。<br/><br/> **メールボックスの内容がフィルター処理**のこの種のフィルターは、検索可能なコンテンツに適用されます。割り当てられているユーザーを検索できます、メールボックスの内容を指定します。この種類のフィルターの構文は、 **MailboxContent_** _SearchablePropertyName:value_、 _SearchablePropertyName_が設定可能なコンテンツの検索にキーワード クエリ言語 (KQL) プロパティを指定する場所です。メールボックスのコンテンツ フィルターなどの`MailboxContent_recipients:contoso.com`ユーザーには、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索するには、このフィルターが割り当てられているようにします。<br/>  検索可能なメッセージのプロパティのリストは、[キーワード クエリとコンテンツの検索の検索条件](keyword-queries-and-search-conditions.md)を参照してください。  <br/><br/> **サイトとサイトのコンテンツ フィルタ リング**・ ビジネス サイトに関連する割り当て済みのユーザーが検索できるどのようなサイトまたはサイトのコンテンツを指定するために使用できるフィルターがある 2 つの SharePoint と OneDrive。  <br/><br/> - **Site_**_SearchableSiteProperty_ <br/> - **SiteContent_**_SearchableSiteProperty_ <br/><br/>  これら 2 つのフィルターは交換可能です。たとえば`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`と`"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`は、同じ結果を返します。フィルターが何を識別するために、使用することができますが、 `Site_` 、サイトの URL など) のサイトに関連するプロパティを指定して`SiteContent_`のコンテンツに関連するプロパティ (ドキュメントの種類を指定するにはフィルターでは、`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`内のコンテンツのみを検索するには、このフィルターが、ユーザーに割り当てられている許可は、https://contoso.sharepoint.com/sites/doctorsサイト コレクションです。フィルター`"SiteContent_FileExtension -eq 'docx'"`ユーザーには、Word 文書 (Word 2007 以降) のみを検索するには、このフィルターが割り当てられているようにします。<br/><br/>  検索可能なサイトのプロパティのリストは、[クロールされ SharePoint 内のプロパティの管理の概要](https://go.microsoft.com/fwlink/p/?LinkId=331599)を参照してください。プロパティは、[**はい]** にマークします * * Queryable * * サイトまたはサイトのコンテンツ フィルターを作成する列を使用することができます。<br/> <br/> **重要な:** 1 つの検索フィルターは、フィルターの 1 つの型を持つことができますのみメールボックス フィルターとサイト フィルターは使用できません。同様に、メールボックスのフィルターと、メールボックスのコンテンツ フィルターは使用できません。ただし、フィルターは、同じ種類のより複雑なクエリを含めることができます。例えば`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` <br/><br/> **重要な:**(ユーザーが Exchange メールボックスまたは任意の SharePoint サイトを検索するを防ぐ) など、特定の Office 365 サービスでのコンテンツの場所を検索するようにユーザーが明示的に指定するには、検索のアクセス許可フィルターを作成する必要があります。つまり、ユーザーが組織内のすべての SharePoint サイトを検索する検索のアクセス許可フィルターを作成するを防ぐそのユーザーのメールボックスを検索します。たとえば、のみを検索する SharePoint サイトを SharePoint の管理者は、メールボックスを検索することを防止するフィルターを作成するには、作成する必要があります。同様に、Exchange の管理者のメールボックスのみを検索するのには、サイトを検索することを防止するフィルターを作成するには、作成する必要があります。           |
| _ユーザー_ <br/> |_ユーザー_パラメーターは、そのコンテンツの検索に適用されるフィルターを取得するユーザーを指定します。エイリアス、またはプライマリ SMTP アドレスでユーザーを識別します。コンマで区切られた複数の値を指定するか、**すべて**の値を使用してフィルターをすべてのユーザーに割り当てることができます。<br/> セキュリティを指定するのには、_ユーザー_のパラメーターを使用することも&amp;コンプライアンス センターの役割のグループです。これにより、カスタムの役割グループを作成して、そのロールを割り当てるには、検索のアクセス許可のフィルターがグループ化します。たとえば、多国籍企業の米国子会社の電子的証拠開示マネージャーのカスタムの役割グループがあるとします。(役割グループの名前のプロパティを使用して)、この役割グループを指定し、検索対象となる米国内のメールボックスのみを許可する_フィルター_パラメーターを使用する、_ユーザー_パラメーターを使用することができます。<br/> このパラメーターで配布グループを指定することはできません。  <br/> |
   

## <a name="examples-of-creating-search-permissions-filters"></a>検索のアクセス許可のフィルターを作成する例

以下に、**New-ComplianceSecurityFilter** コマンドレットを使用してアクセス許可の検索フィルターを作成する例を示します。 
  
次の使用例は、カナダ内のメールボックスに対してのみすべてのコンテンツの検索操作を実行するユーザーの annb@contoso.com を使用できます。このフィルターには、ISO 3166-1 からのカナダの 3 桁の数値の国コードが含まれています。

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
   
次の使用例は、コンテンツのみを検索する OneDrive の電子的証拠開示マネージャーのカスタムの役割グループのメンバーを組織内の事業所の OneDrive にできます。

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> 特定のサイトを検索するユーザーを制限するフィルターを使用して、 `Site_Path`、前の例のように、です。使用して`Site_Site`は機能しません。 
  
この例では、2015 年中に送信されるメール メッセージに対してのみ、すべてのコンテンツ検索アクションを実行するようにユーザーを制限します。

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
この例では、前述の例と同じように、最後に変更されたのが 2015 年中であるドキュメントに対してのみ、すべてのコンテンツ検索アクションを実行するようにユーザーを制限します。

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
この例では、[OneDrive 探索マネージャー] の役割グループのメンバーが組織内のどのメールボックスのコンテンツの検索操作を実行できなくなります。 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```
  
## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get ComplianceSecurityFilter**を使用して、検索のアクセス許可のフィルターの一覧を取得します。_フィルター名_パラメーターを使用して、特定の検索フィルターの情報を取得します。 
  
## <a name="set-compliancesecurityfilter"></a>セット ComplianceSecurityFilter

**セット ComplianceSecurityFilter**を使用して、既存の検索のアクセス許可のフィルターを変更します。唯一必須のパラメーターは、_フィルター名_です。 
  
|**パラメーター**|**説明**|
|:-----|:-----|
| _操作_| _アクション_パラメーターは、フィルターを適用する検索操作の種類を指定します。コンテンツの検索操作を行うことは次のとおりです。<br/><br/> **エクスポート**- フィルターは、検索結果をエクスポートするときに適用されます。  <br/> **プレビュー**のフィルターは、検索結果をプレビューする際に適用されます。  <br/> **パージ**・ フィルターは、検索結果を削除するときに適用されます。  <br/> **検索**- フィルターは、検索を実行するときに適用されます。  <br/> すべてのアクションを検索する**すべて**のフィルターが適用されます。  <br/> |
| _フィルター名_|_フィルター名_のパラメーターは、アクセス許可のフィルターの名前を指定します。 |
| _フィルター_| _フィルター_パラメーターは、コンプライアンス ・ セキュリティ ・ フィルターの検索条件を指定します。フィルターの 2 つの異なる種類を作成することができます。<br/><br/>**メールボックスがフィルター処理**のこの種のフィルター (_ユーザー_のパラメーターで指定) 割り当てられているユーザーが検索できるメールボックスを指定します。この種類のフィルターの構文は、 **Mailbox_** _MailboxPropertyName_、 _MailboxPropertyName_が検索できるメールボックスの範囲を使用するメールボックスのプロパティを指定します。メールボックスのフィルターでは、`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`は、ユーザーにのみ値を持つメールボックスを検索するには、このフィルター「OttawaUsers」が割り当てられた、CustomAttribute10 プロパティにします。 _MailboxPropertyName_プロパティには、任意のサポートされているフィルターの受信者プロパティを使用できます。サポートされているプロパティのリストは、 [- RecipientFilter パラメーターのフィルターのプロパティ](https://go.microsoft.com/fwlink/p/?LinkId=784903)を参照してください。<br/><br/>**メールボックスの内容がフィルター処理**のこの種のフィルターは、検索可能なコンテンツに適用されます。割り当てられているユーザーを検索できます、メールボックスの内容を指定します。この種類のフィルターの構文は、 **MailboxContent_** _SearchablePropertyName:value_、 _SearchablePropertyName_が設定可能なコンテンツの検索にキーワード クエリ言語 (KQL) プロパティを指定する場所です。メールボックスのコンテンツ フィルターなどの`MailboxContent_recipients:contoso.com`ユーザーには、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索するには、このフィルターが割り当てられているようにします。 検索可能なメッセージのプロパティのリストは、[コンテンツ検索用のキーワード クエリ](keyword-queries-and-search-conditions.md)を参照してください。<br/><br/>**サイトとサイトのコンテンツ フィルタ リング**ビジネス サイトに関連する割り当て済みのユーザーが検索できるどのようなサイトまたはサイトのコンテンツを指定するために使用できるフィルターは、2 つの SharePoint と OneDrive があります。 <br/><br/>- **Site_***SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>これら 2 つのフィルターは交換可能です。たとえば`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`と`"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`は、同じ結果を返します。フィルターが何を識別するために、使用することができますが、 `Site_` 、サイトの URL など) のサイトに関連するプロパティを指定して`SiteContent_`のコンテンツに関連するプロパティ (ドキュメントの種類を指定するにはフィルターでは、`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`内のコンテンツのみを検索するには、このフィルターが、ユーザーに割り当てられている許可は、https://contoso.spoppe.com/sites/doctorsサイト コレクションです。フィルター`"SiteContent_FileExtension -eq 'docx'"`ユーザーには、Word 文書 (Word 2007 以降) のみを検索するには、このフィルターが割り当てられているようにします。<br/><br/>検索可能なサイトのプロパティのリストは、[クロールされ SharePoint 内のプロパティの管理の概要](https://go.microsoft.com/fwlink/p/?LinkId=331599)を参照してください。サイトまたはサイトのコンテンツ フィルターを作成すると、**はい**、 **Queryable**列で設定されているプロパティを使用できます。<br/><br/> **重要な:** 1 つの検索フィルターは、フィルターの 1 つの型を持つことができますのみメールボックス フィルターとサイト フィルターは使用できません。同様に、メールボックスのフィルターと、メールボックスのコンテンツ フィルターは使用できません。ただし、フィルターは、同じ種類のより複雑なクエリを含めることができます。例えば`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`          |
| _ユーザー_|_ユーザー_パラメーターは、そのコンテンツの検索に適用されるフィルターを取得するユーザーを指定します。これは複数値プロパティであるため、このパラメーターを使用してユーザーまたはユーザー グループを指定すると、ユーザーの既存のリストが上書きされます。追加して、選択したユーザーを削除するための構文を次の例を参照してください。<br/><br/>セキュリティを指定するのには、_ユーザー_のパラメーターを使用することも&amp;コンプライアンス センターの役割のグループです。これにより、カスタムの役割グループを作成して、そのロールを割り当てるには、検索のアクセス許可のフィルターがグループ化します。たとえば、多国籍企業の米国子会社の電子的証拠開示マネージャーのカスタムの役割グループがあるとします。(役割グループの名前のプロパティを使用して)、この役割グループを指定し、検索対象となる米国内のメールボックスのみを許可する_フィルター_パラメーターを使用する、_ユーザー_パラメーターを使用することができます。<br/><br/>このパラメーターで配布グループを指定することはできません。 |

## <a name="examples-of-changing-search-permissions-filters"></a>検索のアクセス許可のフィルターを変更する例

これらの例では、 **Get ComplianceSecurityFilter**と**セット ComplianceSecurityFilter**コマンドレットを使用して、追加または既存のフィルターに割り当てられているユーザーのリストにユーザーを削除する方法を示します。を追加またはフィルターからユーザーを削除するときは、その SMTP アドレスを使用してユーザーを指定します。 
  
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
  
## <a name="remove-compliancesecurityfilter"></a>削除 ComplianceSecurityFilter

**削除 ComplianceSecurityFilter**を使用して、検索フィルターを削除します。削除するフィルターを指定するのに_フィルター名_のパラメーターを使用します。 
  
## <a name="more-information"></a>詳細情報

- **方法は、作業時間をフィルタ リングのアクセス許可を検索しますか?** アクセス許可フィルターは、コンテンツの検索が実行されると、検索クエリに追加されます。アクセス許可フィルターは、 **AND**ブール演算子によって本質的には検索クエリに結合されています。たとえば、Bob が作業者の配布グループのメンバーのメールボックスに対するすべての検索操作を実行するを許可するアクセス許可フィルターがあるとします。Bob は、検索クエリを使用して組織内のすべてのメールボックスのコンテンツの検索を実行し、 `sender:jerry@adatum.com`。アクセス許可フィルターと検索のクエリは、 **AND**演算子で結合に論理的に、ため検索は作業者の配布グループのメンバーに、jerry@adatum.com によって送信されたメッセージを返します。 
    
- **検索のアクセス許可の複数のフィルターがある場合はどうなるか?** コンテンツの検索クエリで複数のアクセス許可のフィルター**や**ブール演算子で結合されます。その結果は、フィルターのいずれかに該当する場合に返されます。コンテンツの検索では、(**または**演算子で結合) のすべてのフィルターは、検索クエリに**AND**演算子で結合します。みましょう前の例では、検索フィルターが Bob だけの作業者の配布グループのメンバーのメールボックスを検索することができます。Bob が Phil のメールボックス ("Mailbox_Alias - ne 'ね'") を検索することを防止する別のフィルターを作成します。するいるとね、作業者グループのメンバーであること。Bob は、組織内のすべてのメールボックスに (前の例では) からのコンテンツの検索を実行するときに検索結果が戻されます Phil のメールボックスのボブが Phil のメールボックスを検索することを防止するためのフィルターを適用した場合でも。これは、作業者グループを検索するのには、Bob が許可されている最初のフィルターが true であるためにです。Phil は、作業者グループのメンバーであるため、ボブが Phil のメールボックスを検索できます。 
    
- **は、非アクティブなメールボックスの作業時間をフィルタ リングのアクセス許可を検索しますか?** はい、ユーザー組織内で非アクティブなメールボックスを検索することができますを制限するのにメールボックスとメールボックスのコンテンツ フィルターを使用することができます。通常のメールボックスと同じように、非アクティブなメールボックスにアクセス許可フィルターを作成するために使用される受信者のプロパティを使用して構成するのには。必要に応じて、非アクティブなメールボックスのプロパティを表示するのに**Get メールボックス InactiveMailboxOnly**コマンドを使用することができます。詳細についてを参照してください[を作成する Office 365 の非アクティブなメールボックスの管理と](create-and-manage-inactive-mailboxes.md)。
    
- **は、パブリック フォルダーの作業時間をフィルタ リングのアクセス許可を検索しますか?** 違います。として Exchange パブリック フォルダーを検索できるユーザーを制限するフィルタ リングのアクセス許可を使用することはできません前に説明した検索します。などのパブリック フォルダー内のアイテムは、アクセス許可のフィルターによって検索結果から除外できません。 
    
- **は特定のサービスのすべてのコンテンツの場所を検索するユーザーを許可するもしないように、別のサービスでのコンテンツの場所を検索しますか?** 違います。説明したようには、明示的にできないようにする (ユーザーが Exchange メールボックスまたは任意の SharePoint サイトを検索するを防ぐ) など、特定の Office 365 サービスのコンテンツの場所を検索する検索のアクセス許可フィルターを作成する必要が。つまり、ユーザーが組織内のすべての SharePoint サイトを検索する検索のアクセス許可フィルターを作成するを防ぐそのユーザーのメールボックスを検索します。たとえば、のみを検索する SharePoint サイトを SharePoint の管理者は、メールボックスを検索することを防止するフィルターを作成するには、作成する必要があります。同様に、Exchange の管理者のメールボックスのみを検索するのには、サイトを検索することを防止するフィルターを作成するには、作成する必要があります。
