---
title: 電子情報開示センターを使用したすべてのメールボックスとサイトの検索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 56e2978f-71b6-4141-b769-ad856d31bbec
description: Office 365 の電子情報開示センターの 1 つの電子的証拠開示検索を行うビジネス サイトのすべての Exchange Online のメールボックス、SharePoint Online サイト、および OneDrive を検索できます。組織内すべてのコンテンツ ソースを検索するのには、電子的証拠開示マネージャー割り当てる必要がありますコンテンツ ソースごとに電子情報開示の適切なアクセス許可です。
ms.openlocfilehash: 5612faf6113ceef292f90b49ec70ad7b30905646
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038100"
---
# <a name="search-all-mailboxes-and-sites-using-the-ediscovery-center"></a><span data-ttu-id="87ff7-104">電子情報開示センターを使用したすべてのメールボックスとサイトの検索</span><span class="sxs-lookup"><span data-stu-id="87ff7-104">Search all mailboxes and sites using the eDiscovery Center</span></span>

<span data-ttu-id="87ff7-p102">Office 365 の電子情報開示センターの 1 つの電子的証拠開示検索を行うビジネス サイトのすべての Exchange Online のメールボックス、SharePoint Online サイト、および OneDrive を検索できます。組織内すべてのコンテンツ ソースを検索するのには、電子的証拠開示マネージャー割り当てる必要がありますコンテンツ ソースごとに電子情報開示の適切なアクセス許可です。</span><span class="sxs-lookup"><span data-stu-id="87ff7-p102">In the eDiscovery Center in Office 365, you can search all Exchange Online mailboxes, SharePoint Online sites, and OneDrive for Business sites in a single eDiscovery search. To search all content sources in the organization, an eDiscovery manager must be assigned the appropriate eDiscovery permissions for each content source.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="87ff7-107">開始する前に</span><span class="sxs-lookup"><span data-stu-id="87ff7-107">Before you begin</span></span>

- <span data-ttu-id="87ff7-p103">電子情報開示マネージャーには、コンテンツ ソースを検索する適切なアクセス許可が割り当てられている必要があります。メールボックスとサイトに対する電子情報開示のアクセス許可の割り当ての詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87ff7-p103">An eDiscovery manager must be assigned the appropriate permissions to search a content source. For more information about assigning eDiscovery permissions to mailboxes and sites, see the following:</span></span> 
    
  - [<span data-ttu-id="87ff7-110">Exchange の電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="87ff7-110">Assign eDiscovery permissions in Exchange</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526886)
    
  - [<span data-ttu-id="87ff7-111">SharePoint Online の電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="87ff7-111">Assign eDiscovery permissions in SharePoint Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526885)
    
  - [<span data-ttu-id="87ff7-112">OneDrive for Business サイトに対する電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="87ff7-112">Assign eDiscovery permissions to OneDrive for Business sites</span></span>](assign-permissions-to-onedrive-for-business-sites.md)
    
- <span data-ttu-id="87ff7-p104">1 つの電子的証拠開示検索クエリでは、最大 10,000 のメールボックスおよびビジネスのサイトの SharePoint Online と OneDrive の無制限の数を検索できます。ただし、検索する特定のサイトを指定すると、制限が 100 サイトです。</span><span class="sxs-lookup"><span data-stu-id="87ff7-p104">You can search a maximum of 10,000 mailboxes and an unlimited number of SharePoint Online and OneDrive for Business sites in a single eDiscovery search query. However, if you specify the specific sites to search, the limit is 100 sites.</span></span>
    
- <span data-ttu-id="87ff7-115">すべてのメールボックスとサイトを検索するときに結果を表示するときは、制限の説明の[詳細について](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo)はセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87ff7-115">See the [More information](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo) section for a description of the limits when viewing the results when searching all mailboxes and sites.</span></span> 
    
- <span data-ttu-id="87ff7-116">電子情報開示センターで検索クエリを作成する方法の詳細については、[作成および実行の電子的証拠開示のクエリ](https://go.microsoft.com/fwlink/p/?LinkID=404032)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87ff7-116">For more information about creating search queries in the eDiscovery Center, see [Create and run eDiscovery queries](https://go.microsoft.com/fwlink/p/?LinkID=404032).</span></span>
    
## <a name="search-all-locations"></a><span data-ttu-id="87ff7-117">すべての場所を検索</span><span class="sxs-lookup"><span data-stu-id="87ff7-117">Search all locations</span></span>

1. <span data-ttu-id="87ff7-118">電子情報開示センターで、検索クエリを実行する電子情報開示ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="87ff7-118">In the eDiscovery Center, open the eDiscovery case that you want to run the search query for.</span></span>
    
2. <span data-ttu-id="87ff7-119">[**検索とエクスポート**、既存のクエリをクリックするか、新しい検索クエリを作成する **[新しい項目**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87ff7-119">Under **Search and Export**, click an existing query or click **New item** to create a new search query.</span></span> 
    
3. <span data-ttu-id="87ff7-120">[検索クエリ] ページの **[ソース]** セクションで、**[クエリ範囲の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87ff7-120">On the search query page, in the **Sources** section, click **Modify Query Scope**.</span></span>
    
4. <span data-ttu-id="87ff7-121">**[クエリ範囲の変更]** ページで、**[すべてを検索]** をクリックして、検索するコンテンツの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="87ff7-121">On the **Modify Query Scope** page, click **Search everything**, and select the content locations to search.</span></span>
    
  - <span data-ttu-id="87ff7-122">すべてのメールボックスを検索するように**Exchange**を選択します。</span><span class="sxs-lookup"><span data-stu-id="87ff7-122">Select **Exchange** to search all mailboxes.</span></span> 
    
  - <span data-ttu-id="87ff7-123">ビジネス サイトのすべての SharePoint Online と OneDrive を検索するように**SharePoint**を選択します。</span><span class="sxs-lookup"><span data-stu-id="87ff7-123">Select **SharePoint** to search all SharePoint Online and OneDrive for Business sites.</span></span> 
    
  - <span data-ttu-id="87ff7-124">**交換**および**SharePoint**の両方に、組織内のすべてのコンテンツの場所の検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="87ff7-124">Select both **Exchange** and **SharePoint** to search all content locations in your organization.</span></span> 
    
![すべてのメールボックスとサイトの検索](media/e1f919ab-5596-43bb-a3c9-626cd41067b3.gif)
  
5. <span data-ttu-id="87ff7-126">**[OK]** をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="87ff7-126">Click **OK** to save the changes.</span></span> 
    
6. <span data-ttu-id="87ff7-p105">キーワード クエリ、日付範囲など、[検索クエリ] ページのその他の情報を記入または変更したり、検索対象のコンテンツを特定の種類のコンテンツに絞ったりします。クエリを実行する準備ができたら、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87ff7-p105">Complete or revise other information on the search query page, such as the keyword query, the date range, or narrowing the specific types of content to search for. When you're ready to run the query, click **Search**.</span></span> 
    
## <a name="more-information"></a><span data-ttu-id="87ff7-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="87ff7-129">More information</span></span>
<span data-ttu-id="87ff7-130"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="87ff7-130"></span></span>

- <span data-ttu-id="87ff7-131">上位 500 メールボックス、上位 500 サイトとその他の結果が、**[クエリ]** ページの **[ソース]** の下に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="87ff7-131">The top 500 mailboxes and the top 500 sites with the most results are listed under **Sources** on the **Query** page.</span></span> 
    
- <span data-ttu-id="87ff7-132">すべてのコンテンツ ソースで見つかったアイテムの合計数とそれらの合計サイズが、**[クエリ]** ページの **[ソース]** の下に表示されます。 
</span><span class="sxs-lookup"><span data-stu-id="87ff7-132">The total number of items found in all content sources and their combined total size are displayed under **Sources** on the **Query** page.</span></span> 
    
- <span data-ttu-id="87ff7-133">ExchangeメールボックスまたはSharePointのサイトにある最新の検索結果の 200 個を **[クエリ]** ページでプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="87ff7-133">You can preview the 200 most recent search results located in Exchange mailboxes or SharePoint sites on the **Query** page.</span></span> 
    
    <span data-ttu-id="87ff7-134">次のスクリーン ショットは、すべてのメールボックスとサイトを検索したときの **[クエリ]** ページに表示される検索結果の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="87ff7-134">The following screenshot shows an example of the search results displayed on the **Query** page when you search all mailboxes and sites.</span></span> 
    
    ![すべての場所を検索した結果のスクリーン ショット](media/4bf430f6-41ab-4bf6-afa9-33c3f6fd8b16.gif)
  

