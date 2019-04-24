---
title: コンテンツ検索をコピーする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: この記事に記載されている Windows PowerShell スクリプトを使用して、Office 365 または Microsoft 365 のコンプライアンスセンターで既存のコンテンツ検索をすばやく複製します。 検索を複製すると、元の検索と同じプロパティを含む新しい検索 (新しい名前) が作成されます。 その後、キーワードクエリまたは日付範囲を変更して新しい検索を編集し、それを実行します。
ms.openlocfilehash: b08ccb6fbaf2dc9d92e0814fe9f92ea77c731147
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243348"
---
# <a name="clone-a-content-search"></a>コンテンツ検索をコピーする

Office 365 または Microsoft 365 のコンプライアンスセンターでコンテンツ検索を作成して、多くのメールボックスまたは SharePoint および OneDrive for business サイトを検索するには、しばらく時間がかかることがあります。 URL を誤って指定すると、検索対象のサイトを指定してもエラーが発生する可能性があります。 この問題を回避するには、この記事の Windows PowerShell スクリプトを使用して、既存のコンテンツ検索をすばやく複製できます。 検索を複製すると、元の検索と同じプロパティ (コンテンツの場所や検索クエリなど) を含む新しい検索 (別の名前) が作成されます。 その後、キーワードクエリまたは日付範囲を変更して、新しい検索を編集して実行できます。
  
コンテンツ検索をクローンする理由
  
- 異なるキーワード検索クエリの結果を同じコンテンツの場所で実行する場合の比較。
    
- を使用して、新しい検索を作成するときに大量のコンテンツの場所を再入力する必要がなくなります。
    
- 検索結果のサイズを小さくすることができます。たとえば、エクスポートする結果が多すぎる場合は、検索結果の複製を作成し、日付範囲に基づく検索条件を追加して、検索結果の数を減らすことができます。
  
## <a name="before-you-begin"></a>始める前に

- このトピックで説明するスクリプトを実行するには、Security & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。
    
- スクリプトには、最小限のエラー処理が含まれています。 このスクリプトの主な目的は、コンテンツ検索をすばやくクローンすることです。
    
- スクリプトは新しいコンテンツ検索を作成しますが、開始しません。
    
- このスクリプトでは、複製しているコンテンツ検索が電子情報開示ケースに関連付けられているかどうかを考慮します。 検索がケースに関連付けられている場合は、新しい検索も同じケースに関連付けられます。 既存の検索がケースに関連付けられていない場合は、新しい検索がコンプライアンスセンターの [**コンテンツ検索**] ページに一覧表示されます。 
    
- このトピックで提供されているサンプルスクリプトは、Microsoft 標準サポートプログラムまたはサービスではサポートされていません。 このサンプルスクリプトは、あらゆる種類の保証なしに提供されています。 Microsoft は、商品性の保証および特定目的への適合性の保証を含むいかなる明示もしくは黙示の保証責任を負いません。 サンプルスクリプトおよびドキュメントの使用によって発生した、またはパフォーマンスの低下によって生じるリスク全体は、そのままになります。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>手順 1: スクリプトを実行して検索を複製する

この手順のスクリプトでは、既存のコンテンツ検索を複製して新しいコンテンツ検索を作成します。 このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。
  
- **ユーザーの資格情報**-このスクリプトでは、資格情報を使用して、Windows PowerShell を使用して Office 365 組織のセキュリティ & コンプライアンスセンターに接続します。 前述したように、スクリプトを実行するには、Security & compcompliance センターの電子情報開示マネージャーの役割グループのメンバーである必要があります。 
    
- **既存の検索の名前**。これは、複製するコンテンツ検索です。 
    
- **作成される新しい検索の名前**です。この値を空白のままにすると、複製する検索の名前に基づいて新しい検索の名前が作成されます。 
    
検索をクローンするには、次のようにします。
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `CloneSearch.ps1`のようになります。
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 security and compliance center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。
    
3. スクリプトを実行します。例えば：
    
    ```
    .\CloneSearch.ps1
    ```

4. 資格情報の入力を求められたら、電子メールアドレスとパスワードを入力し、[ **OK]** をクリックします。
    
5. スクリプトによってプロンプトが表示されたら、次の情報を入力します。 各情報を入力し、enter キー **** を押します。
    
    - 既存の検索の名前を指定します。
    
    - 新しい検索の名前を指定します。
    
    スクリプトは新しいコンテンツ検索を作成しますが、開始しません。 これにより、次の手順で検索を編集して実行することができます。 新しい検索がケースに関連付けられているかどうかに応じて、 **new-compliancesearch**コマンドレットを実行するか、コンプライアンスセンターの [**コンテンツ検索**] ページまたは [**電子情報開示**] ページに移動することによって、新しい検索のプロパティを表示できます。 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>手順 2: コンプライアンスセンターで複製検索を編集して実行する

スクリプトを実行して既存のコンテンツ検索を複製した後、次の手順として、コンプライアンスセンターに移動して新しい検索を実行します。 前述したように、キーワード検索クエリを変更して検索条件を追加または削除することで、検索を編集できます。 詳細については、次のトピックを参照してください。
  
- [Office 365 のコンテンツ検索](content-search.md)
    
- [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
    
- [電子情報開示のケース](ediscovery-cases.md)
