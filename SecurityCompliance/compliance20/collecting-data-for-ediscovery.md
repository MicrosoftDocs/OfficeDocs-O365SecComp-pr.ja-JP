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
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 2e9e7836a2dc777410b88ffac1aea0c5137b7b89
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218997"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery-preview"></a><span data-ttu-id="fd577-102">高度な電子情報開示でケースのデータを収集する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="fd577-102">Collect data for a case in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="fd577-p101">ケースに関係のある保管担当者とデータソースを識別したら、delve のドキュメントセットを特定してください。上級電子情報開示 (プレビュー) の検索ツールを使用して、Office 365 の custodial および非 wi-fi ダイヤルの場所からこれらを識別することができます。</span><span class="sxs-lookup"><span data-stu-id="fd577-p101">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into. You can use the Search tool in Advanced eDiscovery (Preview) to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="fd577-p102">検索を実行すると、検索クエリに一致したアイテムが最も多い場所など、取得したアイテムの統計情報を表示できるようになります。結果のサブセットをプレビューすることもできます。さらに調べる必要のあるドキュメントセットを特定したら、検索結果を作業セットに追加して、収集して処理することができます。</span><span class="sxs-lookup"><span data-stu-id="fd577-p102">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query. You can also preview a subset of the results. When you've identified the set of documents that want to further examine, you can add the search results to a working set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="fd577-108">検索を作成する</span><span class="sxs-lookup"><span data-stu-id="fd577-108">Create a search</span></span>

<span data-ttu-id="fd577-p103">[検索] タブの\*\*\*\* [**新しい検索**] をクリックすると、検索を作成するための手順が示されたウィザードが起動します。検索を作成する方法の詳細については、「[データを収集するための検索を作成する](create-search-to-collect-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd577-p103">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search. For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="fd577-p104">検索が作成されると、詳細情報を含むフライアウトページが表示されます。検索がまだ完了していないため、[**統計**] ボタンと [**プレビュー** ] ボタンは淡色で表示されます。検索の進行状況を追跡するには、[**検索**] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd577-p104">After a search is created, a flyout page with details is displayed. Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet. You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="fd577-114">検索結果と統計情報を表示する</span><span class="sxs-lookup"><span data-stu-id="fd577-114">View search results and statistics</span></span>
<span data-ttu-id="fd577-p105">コンテンツ検索には、統計 (見積り) とプレビューという2つのコンポーネントがあります。これらの各コンポーネントが完了すると、[**検索**] タブの対応する列に状態が [**送信\*\*\*\*済み**] から [**進行中**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="fd577-p105">There are two components of a content search: Statistics (Estimates) and Preview. As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="fd577-p106">検索の推定が完了したら、検索をクリックしてフライアウトページを表示します。これにより、検索結果に関する大まかな統計情報が表示されます。この時点で、[**統計**] ボタンがアクティブになります。これをクリックすると、次のような検索統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="fd577-p106">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search. At this point, the **Statistics** button will be active. You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="fd577-120">概要</span><span class="sxs-lookup"><span data-stu-id="fd577-120">Summary</span></span>
- <span data-ttu-id="fd577-121">トップの場所</span><span class="sxs-lookup"><span data-stu-id="fd577-121">Top locations</span></span>
- <span data-ttu-id="fd577-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="fd577-122">Queries</span></span>
- <span data-ttu-id="fd577-123">絞り込み条件</span><span class="sxs-lookup"><span data-stu-id="fd577-123">Refiners</span></span>

<span data-ttu-id="fd577-124">検索統計の詳細については、「[検索統計](search-statistics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd577-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="fd577-p107">プレビューが完了すると、[**プレビュー** ] ボタンがアクティブになります。これをクリックして、抽出された結果のサブセットをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="fd577-p107">Once preview is completed, the **Preview** button will be active. Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-working-set"></a><span data-ttu-id="fd577-127">作業セットへの検索結果の追加</span><span class="sxs-lookup"><span data-stu-id="fd577-127">Adding search results to a working set</span></span>

<span data-ttu-id="fd577-p108">検索結果全体を収集して処理する準備ができたら、それを作業セットに追加します。詳細については、「[作業セットにデータを追加する](add-data-to-working-set.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd577-p108">When you are ready to collect and process the entire results of a search, you can do so by adding it to a working set. For details, see [Add data to a working set](add-data-to-working-set.md).</span></span> 