---
title: 検索結果をレビューセットに追加する
ms.author: markjjo
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
ms.openlocfilehash: fc32836026d1a2c449e73a28eafc2f5a631a1705
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527229"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="dd257-102">検索結果をレビューセットに追加する</span><span class="sxs-lookup"><span data-stu-id="dd257-102">Add search results to a review set</span></span>

<span data-ttu-id="dd257-103">検索結果に問題がなければ、検索結果を確認して分析する準備ができたら、それらをレビューセットに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="dd257-103">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="dd257-104">元のデータをレビューセットにコピーすると、テーマの検出、ほぼ重複した検出、電子メールスレッドの識別などの高度な分析ツールを提供することにより、レビューと分析のプロセスも容易になります。</span><span class="sxs-lookup"><span data-stu-id="dd257-104">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="dd257-105">また、office 365 から収集したデータに加えてデータを確認できるように、Office 以外の365データソースのデータをレビューセットに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd257-105">You can also add data from non-Office 365 data sources to a review set so that you can review that data in addition to the data you collect from Office 365.</span></span>

<span data-ttu-id="dd257-106">検索結果をレビューセットに追加すると (レビューセットは、ケースの [**レビューセット**] タブにあります)、次の2つの処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="dd257-106">When you add the results of a search to a review set (review sets are located on the **Review sets** tab of the case), the following two things occur:</span></span>

- <span data-ttu-id="dd257-107">検索結果内のすべてのアイテムは、live Office 365 サービスの元のデータソースからコピーされ、Microsoft クラウド内のセキュリティ保護された Azure ストレージの場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="dd257-107">All items in the search results are copied from the original data source in the live Office 365 services, and copied to a secure Azure storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="dd257-108">すべてのアイテム (コンテンツとメタデータを含む) が再インデックス化され、ケースデータの確認時にレビューセット内のすべてのデータが完全に検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="dd257-108">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="dd257-109">ケース調査時にレビューセットのデータを検索したときに、データを完全に、かつ高速に検索することにより、データのインデックスを作成し直します。</span><span class="sxs-lookup"><span data-stu-id="dd257-109">Re-indexing the data results in thorough and very fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="dd257-110">レビューセットにデータを追加するには、[**検索**] タブで検索をクリックしてから、フライアウトページの [**結果をレビューに追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="dd257-110">To add data to a review set, click a search on the **Searches** tab and then click **Add results to review set** on the flyout page.</span></span>

![レビューセットへのデータの追加](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="dd257-112">既存のレビューセットに追加したり、新しいレビューセットを作成したりできることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dd257-112">Note that you can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="dd257-113">新しいレビューセットにを追加する場合は、名前を指定して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd257-113">If adding to a new review set, specify the name and then click **Add**.</span></span>

![レビューセットを選択する](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="dd257-115">レビューセットへのデータの追加は、長時間実行されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="dd257-115">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="dd257-116">このプロセスには、Office 365 の元のデータソース (たとえば、メールボックスやサイトから) のアイテムを収集し、それらを Azure ストレージの場所 (このコピープロセスは*取り込み*とも呼ばれます) にコピーして、アイテムのインデックスを再作成することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd257-116">This process includes gathering items from the original data sources in Office 365 (for example, from mailboxes and sites), copying them to the Azure storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="dd257-117">[**ジョブ**] タブまたは [**検索**] タブで進行状況を追跡するには、[[**レビューするデータを確認セットに追加しまし**た] 列の状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="dd257-117">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="dd257-118">レビューセット処理が完了した後で、ケースの [**検査セット**] タブをクリックし、[レビュー] セットをクリックして、検証セットのデータのフィルター処理、確認、タグ付け、エクスポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="dd257-118">After the review set processing is completed, click the **Review sets** tab in the case, and then click the review set to start the process filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="dd257-119">レビューセットにサンプルを追加する</span><span class="sxs-lookup"><span data-stu-id="dd257-119">Add a sample to a review set</span></span>

<span data-ttu-id="dd257-120">すべてをレビューセットに追加する前に、検索結果をより詳細に検証する場合は、すべてを追加するのではなく、検索結果のサンプルをレビューセットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="dd257-120">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="dd257-121">サンプルをレビューセットに追加するには、[**検索**] タブで検索をクリックして、フライアウトページの [**サンプル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd257-121">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="dd257-122">[**サンプリングパラメーター** ] ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="dd257-122">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="dd257-123">[**信頼度レベル%** と**信頼区間%** ]-レビューセットに追加されるアイテムは、設定した統計パラメーターによって決まります。</span><span class="sxs-lookup"><span data-stu-id="dd257-123">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="dd257-124">通常、結果のサンプリング時に信頼度と間隔を使用する場合は、ドロップダウンボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="dd257-124">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="dd257-125">それ以外の場合は、既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd257-125">Otherwise, just use the default settings.</span></span>

- <span data-ttu-id="dd257-126">**ランダムサンプル%** -レビューセットに追加されるアイテムは、検索によって返されるアイテムの総数に対する、指定されたパーセンテージのランダムな選択に基づいています。</span><span class="sxs-lookup"><span data-stu-id="dd257-126">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="dd257-127">前述のオプションのいずれかを選択して構成した後、既存のレビューセットを選択して、サンプルを追加した後、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd257-127">After selecting and configuring one of the previous options, choose an existing review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="dd257-128">この場合も、[**ジョブ**] タブまたは [**検索**] タブで進捗状況を追跡するには、[[**レビューするデータをレビューセットに追加しまし**た] 列の状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="dd257-128">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>