---
title: 高度な電子情報開示でケースのデータを収集する (プレビュー)
ms.author: esclee
author: markjjo
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
ms.openlocfilehash: fb4b36841394576c44667f9677507c5655179e45
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455419"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery-preview"></a><span data-ttu-id="7d9c2-102">高度な電子情報開示でケースのデータを収集する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7d9c2-102">Collect data for a case in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="7d9c2-103">ケースに関係のある保管担当者とデータソースを識別したら、delve のドキュメントセットを特定してください。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-103">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="7d9c2-104">上級電子情報開示 (プレビュー) の検索ツールを使用して、Office 365 の custodial および非 wi-fi ダイヤルの場所からこれらを識別することができます。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-104">You can use the Search tool in Advanced eDiscovery (Preview) to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="7d9c2-105">検索を実行すると、検索クエリに一致したアイテムが最も多い場所など、取得したアイテムの統計情報を表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-105">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="7d9c2-106">結果のサブセットをプレビューすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="7d9c2-107">さらに調べる必要のあるドキュメントセットを特定したら、検索結果を作業セットに追加して、収集して処理することができます。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-107">When you've identified the set of documents that want to further examine, you can add the search results to a working set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="7d9c2-108">Create a search</span><span class="sxs-lookup"><span data-stu-id="7d9c2-108">Create a search</span></span>

<span data-ttu-id="7d9c2-109">[検索] タブの\*\*\*\* [**新しい検索**] をクリックすると、検索を作成するための手順が示されたウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-109">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="7d9c2-110">検索を作成する方法の詳細については、「[データを収集するための検索を作成する](create-search-to-collect-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="7d9c2-111">検索が作成されると、詳細情報を含むフライアウトページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="7d9c2-112">検索がまだ完了していないため、[**統計**] ボタンと [**プレビュー** ] ボタンは淡色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-112">Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet.</span></span> <span data-ttu-id="7d9c2-113">検索の進行状況を追跡するには、[**検索**] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="7d9c2-114">検索結果と統計情報を表示する</span><span class="sxs-lookup"><span data-stu-id="7d9c2-114">View search results and statistics</span></span>
<span data-ttu-id="7d9c2-115">コンテンツ検索には、統計 (見積り) とプレビューという2つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="7d9c2-116">これらの各コンポーネントが完了すると、[**検索**] タブの対応する列に状態が [**送信\*\*\*\*済み**] から [**進行中**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-116">As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="7d9c2-117">検索の推定が完了したら、検索をクリックしてフライアウトページを表示します。これにより、検索結果に関する大まかな統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-117">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="7d9c2-118">この時点で、[**統計**] ボタンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="7d9c2-119">これをクリックすると、次のような検索統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-119">You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="7d9c2-120">Summary</span><span class="sxs-lookup"><span data-stu-id="7d9c2-120">Summary</span></span>
- <span data-ttu-id="7d9c2-121">トップの場所</span><span class="sxs-lookup"><span data-stu-id="7d9c2-121">Top locations</span></span>
- <span data-ttu-id="7d9c2-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="7d9c2-122">Queries</span></span>

<span data-ttu-id="7d9c2-123">検索統計の詳細については、「[検索統計](search-statistics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="7d9c2-124">プレビューが完了すると、[**プレビュー** ] ボタンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="7d9c2-125">これをクリックして、抽出された結果のサブセットをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-125">Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-working-set"></a><span data-ttu-id="7d9c2-126">作業セットへの検索結果の追加</span><span class="sxs-lookup"><span data-stu-id="7d9c2-126">Adding search results to a working set</span></span>

<span data-ttu-id="7d9c2-127">検索結果全体を収集して処理する準備ができたら、それを作業セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-127">When you are ready to collect and process the entire results of a search, you can do so by adding it to a working set.</span></span> <span data-ttu-id="7d9c2-128">詳細については、「[作業セットにデータを追加する](add-data-to-working-set.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d9c2-128">For details, see [Add data to a working set](add-data-to-working-set.md).</span></span> 