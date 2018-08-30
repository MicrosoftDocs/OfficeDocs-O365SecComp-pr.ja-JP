---
title: クローンのコンテンツの検索では、Office 365 のセキュリティ&amp;コンプライアンス センター
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: この資料で Windows PowerShell スクリプトを使用して、簡単に既存のコンテンツ検索、セキュリティのクローンを作成する&amp;Compliane センターを検索します。検索を複製する際に、元の検索と同じプロパティが含まれています (新しい名前) を持つ新しい検索が作成されます。できます (変更することによって、キーワード クエリまたは日付の範囲)、新しい検索を編集し、それを実行します。
ms.openlocfilehash: a4f801e3de281e8caf8aeb7d1c2bd48f0facb77c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532021"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a>クローンのコンテンツの検索では、Office 365 のセキュリティ&amp;コンプライアンス センター

Office 365 のセキュリティ コンテンツの検索を作成する&amp;のメールボックス、または SharePoint の多くを検索するコンプライアンス センターとビジネス サイトの OneDrive がしばらくかかることができます。検索するサイトを指定することができますエラーが生じやすく、URL を誤って入力した場合。これらの問題を避けるためには、既存コンテンツの検索を簡単に複製するのにはこの資料で Windows PowerShell スクリプトを使用することができます。検索を複製する際に、元の検索とコンテンツの場所および検索クエリの場合) など同じプロパティが含まれています (別の名前) を持つ新しい検索が作成されます。できます (キーワード クエリや日付の範囲を変更する) で、新たに検索を編集し、それを実行します。
  
コンテンツ検索のクローンを作る理由ですか。
  
- 別のキーワードの結果を比較するには、同一のコンテンツの場所に検索クエリを実行します。
    
- 新しい検索を作成するときに多くのコンテンツの場所を再入力する手間を節約できます。
    
- 検索結果のサイズを小さくにはなどをエクスポートするのには多くの結果を返す検索をした場合は、検索のクローンを作成して、検索結果の数を減らすために日付の範囲に基づいて検索条件を追加します。
  
## <a name="before-you-begin"></a>はじめに

- セキュリティでは、電子的証拠開示マネージャー ロール グループのメンバーである必要がある&amp;コンプライアンス センターは、このトピックで説明したスクリプトを実行します。
    
- スクリプトには、最低限のエラー処理が含まれています。スクリプトの主な目的は、コンテンツの検索を簡単に複製すること。
    
- スクリプトは、新しいコンテンツの検索を作成しますが、それが起動しません。
    
- このスクリプトでは、クローンを作成しているコンテンツの検索では、電子的証拠開示のサポート案件に関連付けられているかどうかが考慮されます。検索がサポート案件に関連付けられている場合は、新しい検索は同じケースに関連付けできます。既存の検索では、サポート案件に関連付けられていない、セキュリティで**コンテンツの検索**ページに新しい検索を一覧表示されます&amp;コンプライアンス センターです。 
    
- このトピックで提供されるサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスでサポートされていません。サンプル スクリプトは、どのような種類の保証もなく、IS として提供されます。さらに、Microsoft はいかなる黙示の保証を含む、いずれかのもので、商品性または特定目的に対する適合性の。サンプル スクリプトおよびドキュメントのパフォーマンスまたは使用から生じるすべてのリスク負担しなければなりません。いかなる場合においてマイクロソフト、著者、または、作成、生産、またはスクリプトの配信に参加するすべてのユーザーを負いませんいかなる損害に対して損害を含め、制限、ビジネス利益、業務の中断、損失の損失の損害ビジネス情報、またはその他の金銭の損失) マイクロソフトが損害の可能性について知らされていた場合でもに、サンプル スクリプトまたはドキュメントを使用すること、または使用から生じる。
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>手順 1: 検索のクローンを作成するスクリプトを実行します。

この手順では、スクリプトは既存のものを複製することによって新しいコンテンツの検索を作成します。このスクリプトを実行するときに次の情報をするように求めします。
  
- **ユーザーの資格情報**でスクリプトは、セキュリティへの接続に資格情報を使用&amp;、Office 365 の組織の Windows PowerShell でのコンプライアンス センター。述べたように、セキュリティ、電子的証拠開示マネージャーの役割グループのメンバーである必要がある&amp;スクリプトを実行するコンプライアンス センターです。 
    
- **既存の検索の名前**- これは、クローンを作成するコンテンツの検索。 
    
- **名前**- この値を空白のままにした場合、スクリプトは、コピー対象を検索の名前に基づく新しい検索の名前で作成されます。 
    
検索を複製します。
  
1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `CloneSearch.ps1`。
    
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

4. 資格情報のダイアログ ボックスが表示されたらの電子メール アドレスとパスワードを入力し、し、[ **OK**] をクリックします。
    
5. 以下のスクリプトによってメッセージが表示されたら、情報を入力します。個々 の情報を入力し、 **Enter**キーを押します。
    
    - 既存の検索の名前。
    
    - 新しい検索の名前。
    
    スクリプトは、新しいコンテンツの検索を作成しますが、それが起動しません。これを編集し、次の手順で検索を実行する機会を与えます。新しい検索のプロパティを表示するには、 **Get ComplianceSearch**コマンドレットを実行することによって、またはセキュリティの**コンテンツの検索**または**電子的証拠開示**のページに移動して&amp;は、検索したのかどうかによって、コンプライアンス センターサポート案件に関連付けられています。 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a>手順 2: 編集し、セキュリティでクローンとして作成された検索を実行する&amp;コンプライアンス センター

セキュリティに移動するのには次の手順は、既存のコンテンツ検索のクローンを作成するスクリプトを実行すると、&amp;を編集し、新しい検索を実行するコンプライアンス センターです。述べたように、キーワード検索のクエリを変更して、追加することによって検索を編集することができます。 または検索条件を削除します。詳細についてを参照してください。
  
- [Office 365 でのコンテンツの検索](content-search.md)
    
- [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
    
- [電子的証拠開示の場合は、Office 365 のセキュリティ&amp;コンプライアンス センター](ediscovery-cases.md)
