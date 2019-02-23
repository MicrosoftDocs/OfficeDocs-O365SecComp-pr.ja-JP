---
title: Office 365 セキュリティ&amp;コンプライアンスセンターでコンテンツ検索を複製する
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
description: この記事に記載されている Windows PowerShell スクリプトを使用して、セキュリティ&amp; Compliane センター検索で既存のコンテンツ検索をすばやく複製します。検索を複製すると、元の検索と同じプロパティを含む新しい検索 (新しい名前) が作成されます。その後、キーワードクエリまたは日付範囲を変更して新しい検索を編集し、それを実行します。
ms.openlocfilehash: 15f1ca5d00f03f510745fef7ae8418192a9eb448
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213547"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a>Office 365 セキュリティ&amp;コンプライアンスセンターでコンテンツ検索を複製する

Office 365 でコンテンツ検索を作成する&amp;多くのメールボックスまたは SharePoint と OneDrive for business サイトを検索するセキュリティコンプライアンスセンターは、しばらく時間がかかる場合があります。URL を誤って指定すると、検索対象のサイトを指定してもエラーが発生する可能性があります。この問題を回避するには、この記事の Windows PowerShell スクリプトを使用して、既存のコンテンツ検索をすばやく複製できます。検索を複製すると、元の検索と同じプロパティ (コンテンツの場所や検索クエリなど) を含む新しい検索 (別の名前) が作成されます。その後、キーワードクエリまたは日付範囲を変更して、新しい検索を編集して実行できます。
  
コンテンツ検索をクローンする理由
  
- 異なるキーワード検索クエリの結果を同じコンテンツの場所で実行する場合の比較。
    
- を使用して、新しい検索を作成するときに大量のコンテンツの場所を再入力する必要がなくなります。
    
- 検索結果のサイズを小さくすることができます。たとえば、エクスポートする結果が多すぎる場合は、検索結果の複製を作成し、日付範囲に基づく検索条件を追加して、検索結果の数を減らすことができます。
  
## <a name="before-you-begin"></a>始める前に

- このトピックで説明するスクリプトを実行するには、セキュリティ&amp;コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。
    
- スクリプトには、最小限のエラー処理が含まれています。このスクリプトの主な目的は、コンテンツ検索をすばやくクローンすることです。
    
- スクリプトは新しいコンテンツ検索を作成しますが、開始しません。
    
- このスクリプトでは、複製しているコンテンツ検索が電子情報開示ケースに関連付けられているかどうかを考慮します。検索がケースに関連付けられている場合は、新しい検索も同じケースに関連付けられます。既存の検索がケースに関連付けられていない場合、新しい検索はセキュリティ&amp;コンプライアンスセンターの [**コンテンツ検索**] ページに一覧表示されます。 
    
- このトピックで提供されているサンプルスクリプトは、Microsoft 標準サポートプログラムまたはサービスではサポートされていません。このサンプルスクリプトは、あらゆる種類の保証なしに提供されています。さらに、Microsoft は、商品性、または特定の目的に対する適合性を明示的に保証することを含め、すべての黙示の保証を放棄します。サンプルスクリプトおよびドキュメントの使用によって発生した、またはパフォーマンスの低下によって生じるリスク全体は、そのままになります。いかなる場合でも、Microsoft、その作成者、またはスクリプトの作成、運用、または配信に関係するユーザーは、いかなる損害 (たとえば、損失を含む損害、ビジネスの中断、損失が発生しても含む) に対して責任を負わないものとします。このような損害が発生する可能性が Microsoft から通知されている場合でも、サンプルのスクリプトまたはドキュメントの使用または使用できないことによって発生する、ビジネス情報、またはその他の pecuniary 損失。
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>手順 1: スクリプトを実行して検索を複製する

この手順のスクリプトでは、既存のコンテンツ検索を複製して新しいコンテンツ検索を作成します。このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。
  
- **ユーザーの資格情報**-スクリプトは、資格情報を使用して、 &amp; Windows PowerShell を使用して Office 365 組織のセキュリティコンプライアンスセンターに接続します。前述したように、このスクリプトを実行するには、セキュリティ&amp;コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。 
    
- **既存の検索の名前**。これは、複製するコンテンツ検索です。 
    
- **作成される新しい検索の名前**です。この値を空白のままにすると、複製する検索の名前に基づいて新しい検索の名前が作成されます。 
    
検索をクローンするには、次のようにします。
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `CloneSearch.ps1`のようになります。
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 Security &amp; Compliance Center
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
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)"
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
    
5. スクリプトによってプロンプトが表示されたら、次の情報を入力します。各情報を入力し、enter キー **** を押します。
    
    - 既存の検索の名前を指定します。
    
    - 新しい検索の名前を指定します。
    
    スクリプトは新しいコンテンツ検索を作成しますが、開始しません。これにより、次の手順で検索を編集して実行することができます。新しい検索が新しい検索であるかどうかに応じて、 **new-compliancesearch**コマンドレットを実行するか、セキュリティ&amp; /コンプライアンスセンターの [**コンテンツ検索**] ページまたは [**電子情報開示**] ページに移動することで、新しい検索のプロパティを表示できます。ケースに関連付けられています。 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a>手順 2: セキュリティ&amp;コンプライアンスセンターで複製検索を編集して実行する

スクリプトを実行して既存のコンテンツ検索を複製した後、次の手順として、セキュリティ&amp;コンプライアンスセンターに移動して新しい検索を実行します。前述したように、キーワード検索クエリを変更して検索条件を追加または削除することで、検索を編集できます。詳細については、以下を参照してください。
  
- [Office 365 でのコンテンツ検索](content-search.md)
    
- [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
    
- [Office 365 セキュリティ&amp; /コンプライアンスセンターの電子情報開示ケース](ediscovery-cases.md)
