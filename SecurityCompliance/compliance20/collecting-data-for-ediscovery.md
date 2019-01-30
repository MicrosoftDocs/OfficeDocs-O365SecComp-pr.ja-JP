---
title: 高度な電子的証拠開示 (プレビュー) では大文字と小文字のデータを収集します。
ms.author: esclee
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 6964cc00d7ae78078aa0729bd5408abd5ed9542a
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608036"
---
# <a name="collecting-data-for-a-case-in-advanced-ediscovery-preview"></a><span data-ttu-id="03577-102">高度な電子的証拠開示 (プレビュー) では大文字と小文字のデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="03577-102">Collecting data for a case in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="03577-p101">通告し、大文字と小文字の興味のあるデータ ソースを識別した後にドキュメントのセットを識別する時間です。高度な電子的証拠開示 (プレビュー) での検索ツールを使用するには Office 365 の信託および非信託の場所からこれらを識別します。</span><span class="sxs-lookup"><span data-stu-id="03577-p101">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into. You can use the Search tool in Advanced eDiscovery (Preview) to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="03577-p102">検索を実行した後、取得した検索クエリと一致しているほとんどのアイテムのある場所などの統計を表示することになります。結果のサブセットをプレビューすることもできます。さらに調査対象のドキュメントのセットを特定するときを収集および処理のワーキング セットに検索結果を追加できます。</span><span class="sxs-lookup"><span data-stu-id="03577-p102">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query. You can also preview a subset of the results. When you've identified the set of documents that want to further examine, you can add the search results to a working set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="03577-108">検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="03577-108">Create a search</span></span>

<span data-ttu-id="03577-p103">[**検索**] タブで、**新しい検索**をクリックすると、検索の作成を案内するウィザードが開始されます。検索を作成する方法の詳細については、[データを収集するために検索を作成する](create-search-to-collect-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03577-p103">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search. For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="03577-p104">検索を作成すると、フライアウトの詳細ページが表示されます。**統計情報**と**プレビュー**ボタンは、最初に灰色を検索はまだ完了していませんので注意してください。ことができますの追跡 [**検索**] タブで、検索の進行状況。</span><span class="sxs-lookup"><span data-stu-id="03577-p104">After a search is created, a flyout page with details is displayed. Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet. You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="03577-114">検索結果の表示と統計情報</span><span class="sxs-lookup"><span data-stu-id="03577-114">View search results and statistics</span></span>
<span data-ttu-id="03577-p105">コンテンツの検索の 2 つのコンポーネントがある: (推定) の統計情報およびプレビューします。として完全なこれらのコンポーネントごとに、変更から**送信済み**から**進行中の\*\*\*\*完了**に、[**検索**] タブの対応する列に表示されているステータスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03577-p105">There are two components of a content search: Statistics (Estimates) and Preview. As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="03577-p106">検索見積が完了すると、フライアウトのページでは、検索の結果についてのいくつかの高度な統計が表示されますを表示する検索をクリックします。この時点で、[**統計情報**] ボタンはアクティブになります。次のように、検索の統計情報を表示することをクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="03577-p106">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search. At this point, the **Statistics** button will be active. You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="03577-120">概要</span><span class="sxs-lookup"><span data-stu-id="03577-120">Summary</span></span>
- <span data-ttu-id="03577-121">上の場所</span><span class="sxs-lookup"><span data-stu-id="03577-121">Top locations</span></span>
- <span data-ttu-id="03577-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="03577-122">Queries</span></span>
- <span data-ttu-id="03577-123">絞り込み条件</span><span class="sxs-lookup"><span data-stu-id="03577-123">Refiners</span></span>

<span data-ttu-id="03577-124">検索の統計情報の詳細については、[検索の統計情報](search-statistics.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03577-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="03577-p107">プレビューが完了すると、 **[プレビュー** ] ボタンがアクティブにします。サンプリングした結果のサブセットをプレビューするをクリックします。</span><span class="sxs-lookup"><span data-stu-id="03577-p107">Once preview is completed, the **Preview** button will be active. Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-working-set"></a><span data-ttu-id="03577-127">ワーキング セットに追加の検索結果</span><span class="sxs-lookup"><span data-stu-id="03577-127">Adding search results to a working set</span></span>

<span data-ttu-id="03577-p108">収集して、検索結果全体を処理する準備ができたら、これを行うワーキング セットに追加することができます。詳細については、[ワーキング セットにデータを追加](add-data-to-working-set.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03577-p108">When you are ready to collect and process the entire results of a search, you can do so by adding it to a working set. For details, see [Add data to a working set](add-data-to-working-set.md).</span></span> 