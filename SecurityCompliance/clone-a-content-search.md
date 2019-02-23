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
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="79239-105">Office 365 セキュリティ&amp;コンプライアンスセンターでコンテンツ検索を複製する</span><span class="sxs-lookup"><span data-stu-id="79239-105">Clone a Content Search in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="79239-p102">Office 365 でコンテンツ検索を作成する&amp;多くのメールボックスまたは SharePoint と OneDrive for business サイトを検索するセキュリティコンプライアンスセンターは、しばらく時間がかかる場合があります。URL を誤って指定すると、検索対象のサイトを指定してもエラーが発生する可能性があります。この問題を回避するには、この記事の Windows PowerShell スクリプトを使用して、既存のコンテンツ検索をすばやく複製できます。検索を複製すると、元の検索と同じプロパティ (コンテンツの場所や検索クエリなど) を含む新しい検索 (別の名前) が作成されます。その後、キーワードクエリまたは日付範囲を変更して、新しい検索を編集して実行できます。</span><span class="sxs-lookup"><span data-stu-id="79239-p102">Creating a Content Search in Office 365 Security &amp; Compliance Center that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile. Specifying the sites to search can also be prone to errors if you mistype a URL. To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search. When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search. Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="79239-111">コンテンツ検索をクローンする理由</span><span class="sxs-lookup"><span data-stu-id="79239-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="79239-112">異なるキーワード検索クエリの結果を同じコンテンツの場所で実行する場合の比較。</span><span class="sxs-lookup"><span data-stu-id="79239-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="79239-113">を使用して、新しい検索を作成するときに大量のコンテンツの場所を再入力する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="79239-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="79239-114">検索結果のサイズを小さくすることができます。たとえば、エクスポートする結果が多すぎる場合は、検索結果の複製を作成し、日付範囲に基づく検索条件を追加して、検索結果の数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="79239-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="79239-115">始める前に</span><span class="sxs-lookup"><span data-stu-id="79239-115">Before you begin</span></span>

- <span data-ttu-id="79239-116">このトピックで説明するスクリプトを実行するには、セキュリティ&amp;コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="79239-116">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="79239-p103">スクリプトには、最小限のエラー処理が含まれています。このスクリプトの主な目的は、コンテンツ検索をすばやくクローンすることです。</span><span class="sxs-lookup"><span data-stu-id="79239-p103">The script includes minimal error handling. The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="79239-119">スクリプトは新しいコンテンツ検索を作成しますが、開始しません。</span><span class="sxs-lookup"><span data-stu-id="79239-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="79239-p104">このスクリプトでは、複製しているコンテンツ検索が電子情報開示ケースに関連付けられているかどうかを考慮します。検索がケースに関連付けられている場合は、新しい検索も同じケースに関連付けられます。既存の検索がケースに関連付けられていない場合、新しい検索はセキュリティ&amp;コンプライアンスセンターの [**コンテンツ検索**] ページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="79239-p104">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case. If the search is associated with a case, the new search will also be associated with the same case. If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the Security &amp; Compliance Center.</span></span> 
    
- <span data-ttu-id="79239-p105">このトピックで提供されているサンプルスクリプトは、Microsoft 標準サポートプログラムまたはサービスではサポートされていません。このサンプルスクリプトは、あらゆる種類の保証なしに提供されています。さらに、Microsoft は、商品性、または特定の目的に対する適合性を明示的に保証することを含め、すべての黙示の保証を放棄します。サンプルスクリプトおよびドキュメントの使用によって発生した、またはパフォーマンスの低下によって生じるリスク全体は、そのままになります。いかなる場合でも、Microsoft、その作成者、またはスクリプトの作成、運用、または配信に関係するユーザーは、いかなる損害 (たとえば、損失を含む損害、ビジネスの中断、損失が発生しても含む) に対して責任を負わないものとします。このような損害が発生する可能性が Microsoft から通知されている場合でも、サンプルのスクリプトまたはドキュメントの使用または使用できないことによって発生する、ビジネス情報、またはその他の pecuniary 損失。</span><span class="sxs-lookup"><span data-stu-id="79239-p105">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="79239-128">手順 1: スクリプトを実行して検索を複製する</span><span class="sxs-lookup"><span data-stu-id="79239-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="79239-p106">この手順のスクリプトでは、既存のコンテンツ検索を複製して新しいコンテンツ検索を作成します。このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79239-p106">The script in this step will create a new Content Search by cloning an existing one. When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="79239-p107">**ユーザーの資格情報**-スクリプトは、資格情報を使用して、 &amp; Windows PowerShell を使用して Office 365 組織のセキュリティコンプライアンスセンターに接続します。前述したように、このスクリプトを実行するには、セキュリティ&amp;コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="79239-p107">**Your user credentials** - The script will use your credentials to connect to the Security &amp; Compliance Center for your Office 365 organization with Windows PowerShell. As previously stated, you have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script.</span></span> 
    
- <span data-ttu-id="79239-133">**既存の検索の名前**。これは、複製するコンテンツ検索です。</span><span class="sxs-lookup"><span data-stu-id="79239-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="79239-134">**作成される新しい検索の名前**です。この値を空白のままにすると、複製する検索の名前に基づいて新しい検索の名前が作成されます。</span><span class="sxs-lookup"><span data-stu-id="79239-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="79239-135">検索をクローンするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="79239-135">To clone a search:</span></span>
  
1. <span data-ttu-id="79239-136">ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `CloneSearch.ps1`のようになります。</span><span class="sxs-lookup"><span data-stu-id="79239-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="79239-137">Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="79239-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="79239-138">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="79239-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="79239-139">資格情報の入力を求められたら、電子メールアドレスとパスワードを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79239-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="79239-p108">スクリプトによってプロンプトが表示されたら、次の情報を入力します。各情報を入力し、enter キー \*\*\*\* を押します。</span><span class="sxs-lookup"><span data-stu-id="79239-p108">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="79239-142">既存の検索の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="79239-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="79239-143">新しい検索の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="79239-143">The name of the new search.</span></span>
    
    <span data-ttu-id="79239-p109">スクリプトは新しいコンテンツ検索を作成しますが、開始しません。これにより、次の手順で検索を編集して実行することができます。新しい検索が新しい検索であるかどうかに応じて、 **new-compliancesearch**コマンドレットを実行するか、セキュリティ&amp; /コンプライアンスセンターの [**コンテンツ検索**] ページまたは [**電子情報開示**] ページに移動することで、新しい検索のプロパティを表示できます。ケースに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="79239-p109">The script creates the new Content Search, but doesn't start it. This gives you a chance to edit and run the search in the next step. You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the Security &amp; Compliance Center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a><span data-ttu-id="79239-147">手順 2: セキュリティ&amp;コンプライアンスセンターで複製検索を編集して実行する</span><span class="sxs-lookup"><span data-stu-id="79239-147">Step 2: Edit and run the cloned search in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="79239-p110">スクリプトを実行して既存のコンテンツ検索を複製した後、次の手順として、セキュリティ&amp;コンプライアンスセンターに移動して新しい検索を実行します。前述したように、キーワード検索クエリを変更して検索条件を追加または削除することで、検索を編集できます。詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79239-p110">After the you've run the script to clone an existing Content Search, the next step is to go to the Security &amp; Compliance Center to edit and run the new search. As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions. For more information, see:</span></span>
  
- [<span data-ttu-id="79239-151">Office 365 でのコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="79239-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="79239-152">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="79239-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="79239-153">Office 365 セキュリティ&amp; /コンプライアンスセンターの電子情報開示ケース</span><span class="sxs-lookup"><span data-stu-id="79239-153">eDiscovery cases in the Office 365 Security &amp; Compliance Center</span></span>](ediscovery-cases.md)
