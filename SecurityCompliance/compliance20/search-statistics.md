---
title: 検索の統計
ms.author: markjjo
author: esclee
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a2234d0a0e94e3fbb15f8fac8f6e49cc7b26cfb2
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240969"
---
# <a name="search-statistics"></a><span data-ttu-id="e06b6-102">検索の統計</span><span class="sxs-lookup"><span data-stu-id="e06b6-102">Search statistics</span></span>

<span data-ttu-id="e06b6-103">検索結果を検証する方法の1つは、結果に関する統計を調べて、期待どおりに配置されるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="e06b6-103">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="e06b6-104">検索が完了すると、高度な統計情報が検索の詳細ポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e06b6-104">When a search completes, high-level statistics are shown on the search details flyout:</span></span>
- <span data-ttu-id="e06b6-105">検索によって取得されたアイテムの数とボリューム</span><span class="sxs-lookup"><span data-stu-id="e06b6-105">Number and volume of items retrieved by the search</span></span>
- <span data-ttu-id="e06b6-106">検索場所で見つかった、部分的にインデックスまたはインデックスが設定されていないアイテムの数とボリューム</span><span class="sxs-lookup"><span data-stu-id="e06b6-106">Number and volume of partially indexed/unindexed items that were found in the search locations</span></span>
- <span data-ttu-id="e06b6-107">検索されたメールボックスと場所の数。</span><span class="sxs-lookup"><span data-stu-id="e06b6-107">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="e06b6-108">詳細な統計情報を表示するには、検索の詳細ポップアップから [統計] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e06b6-108">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary"></a><span data-ttu-id="e06b6-109">Summary</span><span class="sxs-lookup"><span data-stu-id="e06b6-109">Summary</span></span>

<span data-ttu-id="e06b6-110">要約ビューでは、検索結果が場所の種類 (例: Exchange) ごとに分類されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="e06b6-110">In Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="e06b6-111">場所の種類ごとに、次の情報が表示できます。</span><span class="sxs-lookup"><span data-stu-id="e06b6-111">For each location type, you can see:</span></span>
- <span data-ttu-id="e06b6-112">検索条件に一致したアイテムがある場所の数</span><span class="sxs-lookup"><span data-stu-id="e06b6-112">Number of locations that had items that matched the search conditions</span></span>
- <span data-ttu-id="e06b6-113">検索条件に一致したこれらの場所からのアイテムの数</span><span class="sxs-lookup"><span data-stu-id="e06b6-113">Number of items from these locations that matched the search conditions</span></span>
- <span data-ttu-id="e06b6-114">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="e06b6-114">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations"></a><span data-ttu-id="e06b6-115">トップの場所</span><span class="sxs-lookup"><span data-stu-id="e06b6-115">Top locations</span></span>

<span data-ttu-id="e06b6-116">[上部の場所] ビューには、最も一致がある個々の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e06b6-116">In Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="e06b6-117">場所ごとに、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e06b6-117">For each location, you will see:</span></span>
- <span data-ttu-id="e06b6-118">場所の名前 (例: SharePoint URL)</span><span class="sxs-lookup"><span data-stu-id="e06b6-118">Location name (e.g. SharePoint URL)</span></span>
- <span data-ttu-id="e06b6-119">場所の種類</span><span class="sxs-lookup"><span data-stu-id="e06b6-119">Location type</span></span>
- <span data-ttu-id="e06b6-120">検索条件に一致したアイテムの数</span><span class="sxs-lookup"><span data-stu-id="e06b6-120">Number of items that matched the search conditions</span></span>
- <span data-ttu-id="e06b6-121">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="e06b6-121">Total volume of items that matched the search conditions.</span></span>

## <a name="queries"></a><span data-ttu-id="e06b6-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="e06b6-122">Queries</span></span>

<span data-ttu-id="e06b6-123">クエリで (c:s) キーワードまたはキーワード行を使用している場合は、場所の種類ごとのクエリビューにクエリのブレークダウンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e06b6-123">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="e06b6-124">場所の種類ごとに、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="e06b6-124">For each location type, you will see:</span></span>

- <span data-ttu-id="e06b6-125">Part: この列には、"Primary" または "Keyword" という単語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e06b6-125">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="e06b6-126">"Primary" は、クエリ全体に対して行が統計情報を表示することを意味し、"Keyword" は1つのクエリコンポーネントを表します。</span><span class="sxs-lookup"><span data-stu-id="e06b6-126">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="e06b6-127">クエリ: 行が参照している実際のクエリコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e06b6-127">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="e06b6-128">Part が "Primary" の場合、これはクエリ全体になります。Part が "Keyword" であった場合は、クエリコンポーネントのいずれかがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e06b6-128">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="e06b6-129">キーワードを指定せずにすべての contentin メールボックスを検索すると、実際のクエリは (size > = 0)、すべてのアイテムが返されるようになります。</span><span class="sxs-lookup"><span data-stu-id="e06b6-129">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="e06b6-130">SharePoint Online と OneDrive for Business サイトを検索すると、次の 2 つのコンポーネントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e06b6-130">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="e06b6-131">NOT IsExternalContent: 1-オンプレミスの SharePoint 組織からコンテンツを除外する</span><span class="sxs-lookup"><span data-stu-id="e06b6-131">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="e06b6-132">NOT isOneNotePage: 1-すべての OneNote ファイルを除外します。これは、検索クエリに一致するドキュメントと重複する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="e06b6-132">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="e06b6-133">検索条件に一致したアイテムがある場所の数。</span><span class="sxs-lookup"><span data-stu-id="e06b6-133">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="e06b6-134">検索条件に一致したこれらの場所からのアイテムの数。</span><span class="sxs-lookup"><span data-stu-id="e06b6-134">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="e06b6-135">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="e06b6-135">Total volume of items that matched the search conditions.</span></span>