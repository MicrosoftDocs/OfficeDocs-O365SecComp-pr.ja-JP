---
title: コンテンツ検索を複製する
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
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001200"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="9e4c4-105">コンテンツ検索を複製する</span><span class="sxs-lookup"><span data-stu-id="9e4c4-105">Clone a Content Search</span></span>

<span data-ttu-id="9e4c4-106">Office 365 または Microsoft 365 のコンプライアンスセンターでコンテンツ検索を作成して、多くのメールボックスまたは SharePoint および OneDrive for business サイトを検索するには、しばらく時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-106">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile.</span></span> <span data-ttu-id="9e4c4-107">URL を誤って指定すると、検索対象のサイトを指定してもエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-107">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="9e4c4-108">この問題を回避するには、この記事の Windows PowerShell スクリプトを使用して、既存のコンテンツ検索をすばやく複製できます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-108">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="9e4c4-109">検索を複製すると、元の検索と同じプロパティ (コンテンツの場所や検索クエリなど) を含む新しい検索 (別の名前) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-109">When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="9e4c4-110">その後、キーワードクエリまたは日付範囲を変更して、新しい検索を編集して実行できます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-110">Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="9e4c4-111">コンテンツ検索をクローンする理由</span><span class="sxs-lookup"><span data-stu-id="9e4c4-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="9e4c4-112">異なるキーワード検索クエリの結果を同じコンテンツの場所で実行する場合の比較。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="9e4c4-113">を使用して、新しい検索を作成するときに大量のコンテンツの場所を再入力する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="9e4c4-114">検索結果のサイズを小さくすることができます。たとえば、エクスポートする結果が多すぎる場合は、検索結果の複製を作成し、日付範囲に基づく検索条件を追加して、検索結果の数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="9e4c4-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="9e4c4-115">Before you begin</span></span>

- <span data-ttu-id="9e4c4-116">このトピックで説明するスクリプトを実行するには、Security & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-116">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="9e4c4-117">スクリプトには、最小限のエラー処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-117">The script includes minimal error handling.</span></span> <span data-ttu-id="9e4c4-118">このスクリプトの主な目的は、コンテンツ検索をすばやくクローンすることです。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-118">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="9e4c4-119">スクリプトは新しいコンテンツ検索を作成しますが、開始しません。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="9e4c4-120">このスクリプトでは、複製しているコンテンツ検索が電子情報開示ケースに関連付けられているかどうかを考慮します。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-120">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="9e4c4-121">検索がケースに関連付けられている場合は、新しい検索も同じケースに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-121">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="9e4c4-122">既存の検索がケースに関連付けられていない場合は、新しい検索がコンプライアンスセンターの [**コンテンツ検索**] ページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-122">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="9e4c4-123">このトピックで提供されているサンプルスクリプトは、Microsoft 標準サポートプログラムまたはサービスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-123">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="9e4c4-124">このサンプルスクリプトは、あらゆる種類の保証なしに提供されています。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-124">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="9e4c4-125">Microsoft は、商品性の保証および特定目的への適合性の保証を含むいかなる明示もしくは黙示の保証責任を負いません。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-125">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="9e4c4-126">サンプルスクリプトおよびドキュメントの使用によって発生した、またはパフォーマンスの低下によって生じるリスク全体は、そのままになります。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-126">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="9e4c4-127">サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-127">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="9e4c4-128">手順 1: スクリプトを実行して検索を複製する</span><span class="sxs-lookup"><span data-stu-id="9e4c4-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="9e4c4-129">この手順のスクリプトでは、既存のコンテンツ検索を複製して新しいコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-129">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="9e4c4-130">このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-130">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="9e4c4-131">**ユーザーの資格情報**-このスクリプトでは、資格情報を使用して、Windows PowerShell を使用して Office 365 組織のセキュリティ & コンプライアンスセンターに接続します。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-131">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your Office 365 organization with Windows PowerShell.</span></span> <span data-ttu-id="9e4c4-132">前述したように、スクリプトを実行するには、Security & compcompliance センターの電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-132">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="9e4c4-133">**既存の検索の名前**。これは、複製するコンテンツ検索です。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="9e4c4-134">**作成される新しい検索の名前**です。この値を空白のままにすると、複製する検索の名前に基づいて新しい検索の名前が作成されます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="9e4c4-135">検索をクローンするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-135">To clone a search:</span></span>
  
1. <span data-ttu-id="9e4c4-136">ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `CloneSearch.ps1`のようになります。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="9e4c4-137">Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="9e4c4-138">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="9e4c4-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="9e4c4-139">資格情報の入力を求められたら、電子メールアドレスとパスワードを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="9e4c4-140">スクリプトによってプロンプトが表示されたら、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-140">Enter following information when prompted by the script.</span></span> <span data-ttu-id="9e4c4-141">各情報を入力し、enter キー \*\*\*\* を押します。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-141">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="9e4c4-142">既存の検索の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="9e4c4-143">新しい検索の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-143">The name of the new search.</span></span>
    
    <span data-ttu-id="9e4c4-144">スクリプトは新しいコンテンツ検索を作成しますが、開始しません。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-144">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="9e4c4-145">これにより、次の手順で検索を編集して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-145">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="9e4c4-146">新しい検索がケースに関連付けられているかどうかに応じて、 **new-compliancesearch**コマンドレットを実行するか、コンプライアンスセンターの [**コンテンツ検索**] ページまたは [**電子情報開示**] ページに移動することによって、新しい検索のプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-146">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="9e4c4-147">手順 2: コンプライアンスセンターで複製検索を編集して実行する</span><span class="sxs-lookup"><span data-stu-id="9e4c4-147">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="9e4c4-148">スクリプトを実行して既存のコンテンツ検索を複製した後、次の手順として、コンプライアンスセンターに移動して新しい検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-148">After the you've run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="9e4c4-149">前述したように、キーワード検索クエリを変更して検索条件を追加または削除することで、検索を編集できます。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-149">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="9e4c4-150">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e4c4-150">For more information, see:</span></span>
  
- [<span data-ttu-id="9e4c4-151">Office 365 のコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="9e4c4-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="9e4c4-152">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="9e4c4-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="9e4c4-153">電子情報開示ケース</span><span class="sxs-lookup"><span data-stu-id="9e4c4-153">eDiscovery cases</span></span>](ediscovery-cases.md)
