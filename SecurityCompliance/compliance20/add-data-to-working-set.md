---
title: 検索結果をワーキング セットに追加する
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
ms.openlocfilehash: 7830b483190a69e6055fae369580064c5df42f49
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958288"
---
# <a name="add-search-results-to-a-working-set"></a><span data-ttu-id="90075-102">検索結果をワーキング セットに追加する</span><span class="sxs-lookup"><span data-stu-id="90075-102">Add search results to a working set</span></span>

<span data-ttu-id="90075-103">Exchange、SharePoint、OneDrive for business に対する検索を識別してカリングした後、結果を作業セットに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="90075-103">After you've identified and culled with searches against Exchange, SharePoint and OneDrive for business, you can add the results to a working set.</span></span> <span data-ttu-id="90075-104">ワーキングセットは、稲妻 fast 検索結果のインデックスを作成するドキュメントの静的なセットを表し、電子メールスレッドの識別を分析し、重複の検出とテーマをほぼ重複したものにします。</span><span class="sxs-lookup"><span data-stu-id="90075-104">Working sets represent a static set of documents that we will index for lightning fast search results, analyze for email thread identification, near duplicate detection and themes.</span></span>  <span data-ttu-id="90075-105">office 365 から収集したデータを使用して、office 以外の365データソースのデータを並行して live 側に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="90075-105">You can also add data from Non-Office 365 data sources to live side by side with the data you collect from Office 365.</span></span>

<span data-ttu-id="90075-106">ワークセットにデータを追加するには、まず検索を選択し、検索結果で、[ *+ 結果を作業セットに追加*] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="90075-106">To add data to a working set, start by selecting a search, in the search results fly out, click the *+ Add results to working set* button.</span></span>

![作業セットへのデータの追加](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="90075-108">既存の作業セットまたは*新しい作業セット*に追加することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="90075-108">You can then choose to add to an existing working set or a *New working set*.</span></span>  <span data-ttu-id="90075-109">新しい作業セットに追加する場合は、名前を指定し、最後に [*追加*] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="90075-109">If adding to a new working set, specify the name and finally click the *Add* button.</span></span>

![作業セットを選択する](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="90075-111">作業セットへのデータの追加は長時間実行されるプロセスです。 [ジョブ] タブまたは [*検索*] タブの [*ワーキングセットの状態*] 列で進行状況を追跡できます。 プロセスには、Office 365 からのアイテムの収集と、& インデックス作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="90075-111">Adding data to a working set is a long running process, you can either track the progress in the Jobs tab or in the *Working set status* column in the *Searches* tab.  The process includes gathering items from Office 365 and finally Ingestion & Indexing.</span></span>  <span data-ttu-id="90075-112">作業セット処理が完了したら、[*ワーキングセット*] タブをクリックしてワーキングセットをクリックすることで、ワーキングセットに移動できます。</span><span class="sxs-lookup"><span data-stu-id="90075-112">Once working set processing is completed, you can navigate to the working set by clicking on the *Working Sets* tab and then clicking on the working set.</span></span>  <span data-ttu-id="90075-113">検索、レビュー、タグ付け、および関連するデータのエクスポートに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="90075-113">You can then move on to searching, reviewing, tagging and exporting any relevant data.</span></span>

## <a name="adding-a-sample-to-a-working-set"></a><span data-ttu-id="90075-114">サンプルを作業セットに追加する</span><span class="sxs-lookup"><span data-stu-id="90075-114">Adding a sample to a working set</span></span>

<span data-ttu-id="90075-115">検索によって取得されたすべてのドキュメントを収集する前に検索結果の thorougly をさらに検証する場合は、すべてを追加するのではなく、検索結果のランダムなサンプルを作業セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="90075-115">If you would like to validate your search results more thorougly before collecting all documents that were retrieved by your search, you can add a random sample of the search results to a working set instead of adding everything.</span></span>

<span data-ttu-id="90075-116">サンプルを作業セットに追加するには、まず検索を選択し、検索結果のポップアップで [ *sample* button] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90075-116">To add a sample to a working set, start by selecting a search, in the search results flyout, click *Sample* button.</span></span>

<span data-ttu-id="90075-117">その後、サンプリングのパラメーターを選択できます。</span><span class="sxs-lookup"><span data-stu-id="90075-117">You can then choose the parameter of your sampling.</span></span> <span data-ttu-id="90075-118">次のような 2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="90075-118">There are two options:</span></span>
- <span data-ttu-id="90075-119">信頼度と間隔: 指定された統計パラメーターを満たすようにサンプルサイズが選択されます。</span><span class="sxs-lookup"><span data-stu-id="90075-119">Confidence level and interval: sample size will be chosen to satisfy the given statistical parameters.</span></span>
- <span data-ttu-id="90075-120">パーセンテージ: サンプルサイズは、検索によって返されたアイテムの数と選択したパラメーターに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="90075-120">Percentage: sample size will be determined based on the number of items that was returned by the search, and the chosen parameter.</span></span>

<span data-ttu-id="90075-121">最後に、サンプルを追加するワーキングセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="90075-121">Finally, choose the working set to add the sample to.</span></span> <span data-ttu-id="90075-122">さらに、作業セットに検索全体を追加する場合と同じように、プロセスの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="90075-122">From there, you can check the status of the process just as you would for adding a whole search into a working set.</span></span> 