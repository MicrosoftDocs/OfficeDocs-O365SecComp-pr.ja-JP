---
title: 検索結果をレビュー セットに追加する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fac8ab829107befaa1a3f8b3afe1cec8d3468f1b
ms.sourcegitcommit: bac1b5be5db381e6f8d8f652cff1f8ef4d7f6330
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2019
ms.locfileid: "35233324"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="7cfee-102">検索結果をレビュー セットに追加する</span><span class="sxs-lookup"><span data-stu-id="7cfee-102">Add search results to a review set</span></span>

<span data-ttu-id="7cfee-103">検索結果に問題がなければ、検索結果を確認して分析する準備ができたら、それらをレビューセットに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7cfee-103">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="7cfee-104">元のデータをレビューセットにコピーすると、テーマの検出、ほぼ重複した検出、電子メールスレッドの識別などの高度な分析ツールを提供することにより、レビューと分析のプロセスも容易になります。</span><span class="sxs-lookup"><span data-stu-id="7cfee-104">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="7cfee-105">また、office 365 から収集したデータに加えてデータを確認できるように、Office 以外の365データソースのデータをレビューセットに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="7cfee-105">You can also add data from non-Office 365 data sources to a review set so that you can review that data in addition to the data you collect from Office 365.</span></span>

<span data-ttu-id="7cfee-106">検索結果をレビューセット (ケースの [**レビュー**セット] タブにあります) に追加すると、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="7cfee-106">When you add the results of a search to a review set (review sets are on the **Review sets** tab of the case), the following things occur:</span></span>

- <span data-ttu-id="7cfee-107">検索が再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="7cfee-107">The search is run again.</span></span> <span data-ttu-id="7cfee-108">つまり、レビューセットにコピーされる実際の検索結果は、検索が最後に実行されたときに返された推定結果とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7cfee-108">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="7cfee-109">検索結果内のすべてのアイテムは、live Office 365 サービスの元のデータソースからコピーされ、Microsoft クラウド内のセキュリティ保護された Azure ストレージの場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="7cfee-109">All items in the search results are copied from the original data source in the live Office 365 services, and copied to a secure Azure storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="7cfee-110">すべてのアイテム (コンテンツとメタデータを含む) が再インデックス化され、ケースデータの確認時にレビューセット内のすべてのデータが完全に検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="7cfee-110">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="7cfee-111">ケース調査時にレビューセットのデータを検索したときに、データを完全に、かつ高速に検索することにより、データのインデックスを作成し直します。</span><span class="sxs-lookup"><span data-stu-id="7cfee-111">Re-indexing the data results in thorough and very fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="7cfee-112">レビューセットにデータを追加するには、[**検索**] タブで検索をクリックしてから、ポップアップページの [**レビューセットに結果を追加**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cfee-112">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

![レビューセットへのデータの追加](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="7cfee-114">既存のレビューセットに追加したり、新しいレビューセットを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="7cfee-114">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="7cfee-115">新しいレビューセットにを追加する場合は、名前を指定して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cfee-115">If adding to a new review set, specify the name and then click **Add**.</span></span>

![レビューセットを選択する](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="7cfee-117">レビューセットへのデータの追加は、長時間実行されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="7cfee-117">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="7cfee-118">このプロセスには、Office 365 の元のデータソース (たとえば、メールボックスやサイトから) のアイテムを収集し、それらを Azure ストレージの場所 (このコピープロセスは*取り込み*とも呼ばれます) にコピーして、アイテムのインデックスを再作成することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7cfee-118">This process includes gathering items from the original data sources in Office 365 (for example, from mailboxes and sites), copying them to the Azure storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="7cfee-119">[**ジョブ**] タブまたは [**検索**] タブで進行状況を追跡するには、[[**レビューするデータを確認セットに追加しまし**た] 列の状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="7cfee-119">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="7cfee-120">レビューセット処理が完了した後で、ケースの [**検査セット**] タブをクリックし、[レビュー] セットをクリックして、レビューセットのデータのフィルター、確認、タグ付け、エクスポートのプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="7cfee-120">After the review set processing is completed, click the **Review sets** tab in the case, and click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="7cfee-121">レビューセットにサンプルを追加する</span><span class="sxs-lookup"><span data-stu-id="7cfee-121">Add a sample to a review set</span></span>

<span data-ttu-id="7cfee-122">すべてをレビューセットに追加する前に、検索結果をより詳細に検証する場合は、すべてを追加するのではなく、検索結果のサンプルをレビューセットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="7cfee-122">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="7cfee-123">サンプルをレビューセットに追加するには、[**検索**] タブで検索をクリックして、フライアウトページの [**サンプル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cfee-123">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="7cfee-124">[**サンプリングパラメーター** ] ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7cfee-124">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="7cfee-125">**信頼**度の割合と**信頼区間%** –設定した統計値パラメーターによって、レビューセットに追加されたアイテムが決定されます。</span><span class="sxs-lookup"><span data-stu-id="7cfee-125">**Confidence level %** and **Confidence interval %** – The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="7cfee-126">通常、結果のサンプリング時に信頼度と間隔を使用する場合は、ドロップダウンボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="7cfee-126">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="7cfee-127">それ以外の場合は、既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="7cfee-127">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="7cfee-128">**ランダムサンプル%** –レビューセットに追加されるアイテムは、検索によって返されるアイテムの総数に対する、指定されたパーセンテージのランダムな選択に基づいています。</span><span class="sxs-lookup"><span data-stu-id="7cfee-128">**Random sample %** – The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="7cfee-129">前のオプションの1つを選択して構成した後、そのサンプルを追加するレビューセットを選択し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cfee-129">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="7cfee-130">この場合も、[**ジョブ**] タブまたは [**検索**] タブで進捗状況を追跡するには、[[**レビューするデータをレビューセットに追加しまし**た] 列の状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="7cfee-130">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>