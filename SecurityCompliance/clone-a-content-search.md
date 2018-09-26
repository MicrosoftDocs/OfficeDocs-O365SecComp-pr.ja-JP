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
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: この資料で Windows PowerShell スクリプトを使用して、簡単に既存のコンテンツ検索、セキュリティのクローンを作成する&amp;Compliane センターを検索します。検索を複製する際に、元の検索と同じプロパティが含まれています (新しい名前) を持つ新しい検索が作成されます。できます (変更することによって、キーワード クエリまたは日付の範囲)、新しい検索を編集し、それを実行します。
ms.openlocfilehash: fd2ea0d8fa812d23e7479b664b13c786a62d5a38
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038050"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="16f34-105">クローンのコンテンツの検索では、Office 365 のセキュリティ&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="16f34-105">Clone a Content Search in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="16f34-p102">Office 365 のセキュリティ コンテンツの検索を作成する&amp;のメールボックス、または SharePoint の多くを検索するコンプライアンス センターとビジネス サイトの OneDrive がしばらくかかることができます。検索するサイトを指定することができますエラーが生じやすく、URL を誤って入力した場合。これらの問題を避けるためには、既存コンテンツの検索を簡単に複製するのにはこの資料で Windows PowerShell スクリプトを使用することができます。検索を複製する際に、元の検索とコンテンツの場所および検索クエリの場合) など同じプロパティが含まれています (別の名前) を持つ新しい検索が作成されます。できます (キーワード クエリや日付の範囲を変更する) で、新たに検索を編集し、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="16f34-p102">Creating a Content Search in Office 365 Security &amp; Compliance Center that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile. Specifying the sites to search can also be prone to errors if you mistype a URL. To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search. When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search. Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="16f34-111">コンテンツ検索のクローンを作る理由ですか。</span><span class="sxs-lookup"><span data-stu-id="16f34-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="16f34-112">別のキーワードの結果を比較するには、同一のコンテンツの場所に検索クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="16f34-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="16f34-113">新しい検索を作成するときに多くのコンテンツの場所を再入力する手間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="16f34-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="16f34-114">検索結果のサイズを小さくにはなどをエクスポートするのには多くの結果を返す検索をした場合は、検索のクローンを作成して、検索結果の数を減らすために日付の範囲に基づいて検索条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="16f34-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="16f34-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="16f34-115">Before you begin</span></span>

- <span data-ttu-id="16f34-116">セキュリティでは、電子的証拠開示マネージャー ロール グループのメンバーである必要がある&amp;コンプライアンス センターは、このトピックで説明したスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="16f34-116">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="16f34-p103">スクリプトには、最低限のエラー処理が含まれています。スクリプトの主な目的は、コンテンツの検索を簡単に複製すること。</span><span class="sxs-lookup"><span data-stu-id="16f34-p103">The script includes minimal error handling. The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="16f34-119">スクリプトは、新しいコンテンツの検索を作成しますが、それが起動しません。</span><span class="sxs-lookup"><span data-stu-id="16f34-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="16f34-p104">このスクリプトでは、クローンを作成しているコンテンツの検索では、電子的証拠開示のサポート案件に関連付けられているかどうかが考慮されます。検索がサポート案件に関連付けられている場合は、新しい検索は同じケースに関連付けできます。既存の検索では、サポート案件に関連付けられていない、セキュリティで**コンテンツの検索**ページに新しい検索を一覧表示されます&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="16f34-p104">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case. If the search is associated with a case, the new search will also be associated with the same case. If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the Security &amp; Compliance Center.</span></span> 
    
- <span data-ttu-id="16f34-p105">このトピックで提供されるサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスでサポートされていません。サンプル スクリプトは、どのような種類の保証もなく、IS として提供されます。さらに、Microsoft はいかなる黙示の保証を含む、いずれかのもので、商品性または特定目的に対する適合性の。サンプル スクリプトおよびドキュメントのパフォーマンスまたは使用から生じるすべてのリスク負担しなければなりません。いかなる場合においてマイクロソフト、著者、または、作成、生産、またはスクリプトの配信に参加するすべてのユーザーを負いませんいかなる損害に対して損害を含め、制限、ビジネス利益、業務の中断、損失の損失の損害ビジネス情報、またはその他の金銭の損失) マイクロソフトが損害の可能性について知らされていた場合でもに、サンプル スクリプトまたはドキュメントを使用すること、または使用から生じる。</span><span class="sxs-lookup"><span data-stu-id="16f34-p105">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="16f34-128">手順 1: 検索のクローンを作成するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="16f34-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="16f34-p106">この手順では、スクリプトは既存のものを複製することによって新しいコンテンツの検索を作成します。このスクリプトを実行するときに次の情報をするように求めします。</span><span class="sxs-lookup"><span data-stu-id="16f34-p106">The script in this step will create a new Content Search by cloning an existing one. When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="16f34-p107">**ユーザーの資格情報**でスクリプトは、セキュリティへの接続に資格情報を使用&amp;、Office 365 の組織の Windows PowerShell でのコンプライアンス センター。述べたように、セキュリティ、電子的証拠開示マネージャーの役割グループのメンバーである必要がある&amp;スクリプトを実行するコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="16f34-p107">**Your user credentials** - The script will use your credentials to connect to the Security &amp; Compliance Center for your Office 365 organization with Windows PowerShell. As previously stated, you have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script.</span></span> 
    
- <span data-ttu-id="16f34-133">**既存の検索の名前**- これは、クローンを作成するコンテンツの検索。</span><span class="sxs-lookup"><span data-stu-id="16f34-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="16f34-134">**名前**- この値を空白のままにした場合、スクリプトは、コピー対象を検索の名前に基づく新しい検索の名前で作成されます。</span><span class="sxs-lookup"><span data-stu-id="16f34-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="16f34-135">検索を複製します。</span><span class="sxs-lookup"><span data-stu-id="16f34-135">To clone a search:</span></span>
  
1. <span data-ttu-id="16f34-136">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `CloneSearch.ps1`。</span><span class="sxs-lookup"><span data-stu-id="16f34-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="16f34-137">Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="16f34-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="16f34-138">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="16f34-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="16f34-139">資格情報のダイアログ ボックスが表示されたらの電子メール アドレスとパスワードを入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16f34-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="16f34-p108">以下のスクリプトによってメッセージが表示されたら、情報を入力します。個々 の情報を入力し、 **Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="16f34-p108">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="16f34-142">既存の検索の名前。</span><span class="sxs-lookup"><span data-stu-id="16f34-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="16f34-143">新しい検索の名前。</span><span class="sxs-lookup"><span data-stu-id="16f34-143">The name of the new search.</span></span>
    
    <span data-ttu-id="16f34-p109">スクリプトは、新しいコンテンツの検索を作成しますが、それが起動しません。これを編集し、次の手順で検索を実行する機会を与えます。新しい検索のプロパティを表示するには、 **Get ComplianceSearch**コマンドレットを実行することによって、またはセキュリティの**コンテンツの検索**または**電子的証拠開示**のページに移動して&amp;は、検索したのかどうかによって、コンプライアンス センターサポート案件に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="16f34-p109">The script creates the new Content Search, but doesn't start it. This gives you a chance to edit and run the search in the next step. You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the Security &amp; Compliance Center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a><span data-ttu-id="16f34-147">手順 2: 編集し、セキュリティでクローンとして作成された検索を実行する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="16f34-147">Step 2: Edit and run the cloned search in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="16f34-p110">セキュリティに移動するのには次の手順は、既存のコンテンツ検索のクローンを作成するスクリプトを実行すると、&amp;を編集し、新しい検索を実行するコンプライアンス センターです。述べたように、キーワード検索のクエリを変更して、追加することによって検索を編集することができます。 または検索条件を削除します。詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16f34-p110">After the you've run the script to clone an existing Content Search, the next step is to go to the Security &amp; Compliance Center to edit and run the new search. As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions. For more information, see:</span></span>
  
- [<span data-ttu-id="16f34-151">Office 365 でのコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="16f34-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="16f34-152">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="16f34-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="16f34-153">電子的証拠開示の場合は、Office 365 のセキュリティ&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="16f34-153">eDiscovery cases in the Office 365 Security &amp; Compliance Center</span></span>](ediscovery-cases.md)
