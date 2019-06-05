---
title: レビューセットの検索用語レポートを生成する
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 877c0017359ab9193c4cae81cbef4240909053a8
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "34714996"
---
# <a name="generate-search-term-report-for-a-review-set"></a><span data-ttu-id="9f393-102">レビューセットの検索用語レポートを生成する</span><span class="sxs-lookup"><span data-stu-id="9f393-102">Generate search term report for a review set</span></span>

<span data-ttu-id="9f393-103">電子情報開示では、ドキュメントを照会するために最もよく使用される条件の1つとして、キーワード検索用語を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="9f393-103">In eDiscovery, one of the most frequently used conditions for querying documents is by using keyword search terms.</span></span> <span data-ttu-id="9f393-104">特定のキーワード (*用語*とも呼ばれます) が含まれているドキュメントを、ケースにとって重要であるものを特定することにより、レビューアーは自分が直面しているものについての高度な理解を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="9f393-104">By identifying documents that contain the specific keywords (also referred to as *terms*) that are important to a case, reviewers can begin to get a high-level understanding of what they are facing.</span></span> <span data-ttu-id="9f393-105">Microsoft 365 の高度な電子情報開示では、レビューセット内の保存済みのクエリに対して検索用語レポートを生成することで、これを正確に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9f393-105">In Advanced eDiscovery in Microsoft 365, you can do precisely this by generating search term reports on saved queries within a review set.</span></span>

## <a name="step-1-create-a-saved-query-in-the-review-set"></a><span data-ttu-id="9f393-106">手順 1: 保存されたクエリをレビューセットに作成する</span><span class="sxs-lookup"><span data-stu-id="9f393-106">Step 1: Create a saved query in the review set</span></span>

<span data-ttu-id="9f393-107">意味のある検索用語レポートを生成するには、検索用語レポートを生成する対象となる校閲セット内のドキュメントのセットを定義する、保存済みのクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f393-107">To generate a meaningful search term report, create a saved query that defines the set of documents in the review set that you want to generate a search term report for.</span></span> <span data-ttu-id="9f393-108">たとえば、クエリを作成するために、日付の範囲または検索用語の実際のセット (キーワード条件カードを使用) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f393-108">For example, you can use a date range or the actual set of search terms (by using the Keywords condition card) to create the query.</span></span> <span data-ttu-id="9f393-109">レビューセットクエリの詳細については、「[レビューセット内のデータを照会](review-set-search.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f393-109">To learn more about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="step-2-generate-a-search-term-report"></a><span data-ttu-id="9f393-110">手順 2: 検索用語レポートを生成する</span><span class="sxs-lookup"><span data-stu-id="9f393-110">Step 2: Generate a search term report</span></span>

<span data-ttu-id="9f393-111">検索用語レポートを生成するには、手順1で作成した保存済みクエリのコンテキストメニューを使用するか、または検索用語レポート管理コンソールを使用して、2種類の方法があります。</span><span class="sxs-lookup"><span data-stu-id="9f393-111">There are two different ways to generate a search term report: through the context menu of the saved query you created in Step 1, or through the search term report management console.</span></span>

- <span data-ttu-id="9f393-112">ショートカットメニューを使用するには、手順1で作成した保存済みクエリのコンテキストメニューを開き、[**検索用語レポートを生成**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f393-112">To use the context menu, open the context menu of the saved query you created in Step 1, and click **Generate search term report**.</span></span>

- <span data-ttu-id="9f393-113">管理コンソールを使用するには、[レビューセットの管理] に移動し **> 検索用語レポートを表示**し、[**新規**] をクリックして、手順1で作成した保存済みのクエリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9f393-113">To use the management console, go to **Manage review set > View search term reports**, click **New**, and then select the saved query you created in Step 1.</span></span>

<span data-ttu-id="9f393-114">次に、レポートに使用する用語を改行で区切って入力します。手順1で作成した保存済みクエリがキーワード条件カードを使用していた場合、保存されたクエリで使用される最初のキーワード条件カードの用語が、フライアウトページに事前に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9f393-114">Then, enter the terms you would like to report on, separated by newline; if the saved query that you created in Step 1 used keyword condition card, the flyout page will be pre-populated with the terms from the first keyword condition card used in the saved query.</span></span>

<span data-ttu-id="9f393-115">次に、レポートする最大3つのピボットを選択し、[**生成**] をクリックすると、検索用語レポートの生成ジョブが開始されます。</span><span class="sxs-lookup"><span data-stu-id="9f393-115">Then, select up to three pivots to report on, and click on **Generate**, which will start the search term report generation job.</span></span>

### <a name="what-is-a-pivot"></a><span data-ttu-id="9f393-116">ピボットとは</span><span class="sxs-lookup"><span data-stu-id="9f393-116">What is a pivot?</span></span>

<span data-ttu-id="9f393-117">ピボットは、レポートがどのように編成されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="9f393-117">Pivots are how the report will be organized.</span></span> <span data-ttu-id="9f393-118">次の例を検討してください。</span><span class="sxs-lookup"><span data-stu-id="9f393-118">Consider the following example.</span></span>

- <span data-ttu-id="9f393-119">保存されたクエリは、10個のドキュメント (doc1 スルー doc10) を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f393-119">The saved query retrieves 10 documents: doc1 thru doc10.</span></span>

- <span data-ttu-id="9f393-120">doc1、doc2、doc3、doc4、doc5、doc6、および doc7 には、用語 "電子情報開示" が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f393-120">doc1, doc2, doc3, doc4, doc5, doc6, and doc7 contain the term "eDiscovery".</span></span>

- <span data-ttu-id="9f393-121">doc6、doc7、doc8、doc9、および doc10 には、"調査" という用語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f393-121">doc6, doc7, doc8, doc9, and doc10 contain the term "Investigation".</span></span>

- <span data-ttu-id="9f393-122">doc1、doc3、doc5、doc7、doc9 は保管担当者 A からです。</span><span class="sxs-lookup"><span data-stu-id="9f393-122">doc1, doc3, doc5, doc7, doc9 are from custodian A.</span></span>

- <span data-ttu-id="9f393-123">doc2、doc4、doc6、doc8、doc10 は、保管担当者 B からのものです。</span><span class="sxs-lookup"><span data-stu-id="9f393-123">doc2, doc4, doc6, doc8, doc10 are from custodian B.</span></span>

<span data-ttu-id="9f393-124">この例では、"電子情報開示" と "調査" という用語で検索用語レポートを生成し、保管担当者でピボットを実行すると、検索用語レポートは次のように編成されます。</span><span class="sxs-lookup"><span data-stu-id="9f393-124">In this case, if you were to generate a search term report on the terms "eDiscovery" and "Investigation" and pivot on custodians, the search term report would be organized as follows:</span></span>

- <span data-ttu-id="9f393-125">"電子情報開示"-保管担当者 A: 4 ドキュメント</span><span class="sxs-lookup"><span data-stu-id="9f393-125">"eDiscovery" - custodian A: 4 documents</span></span>

- <span data-ttu-id="9f393-126">"電子情報開示"-保管担当者 B: 3 ドキュメント</span><span class="sxs-lookup"><span data-stu-id="9f393-126">"eDiscovery" - custodian B: 3 documents</span></span>

- <span data-ttu-id="9f393-127">「調査」-保管担当者 A: 2 個のドキュメント</span><span class="sxs-lookup"><span data-stu-id="9f393-127">"Investigation" - custodian A: 2 documents</span></span>

- <span data-ttu-id="9f393-128">「調査」-保管担当者 B: 3 ドキュメント</span><span class="sxs-lookup"><span data-stu-id="9f393-128">"Investigation" - custodian B: 3 documents</span></span>

## <a name="step-3-download-report"></a><span data-ttu-id="9f393-129">手順 3: レポートをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="9f393-129">Step 3: Download report</span></span>

<span data-ttu-id="9f393-130">検索用語管理コンソールでは、以前に作成した検索用語レポートジョブの状態を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="9f393-130">In the search term management console, you can track the status of a previously-created search term report job.</span></span> <span data-ttu-id="9f393-131">ジョブが完了したら、検索用語レポートの行をクリックして [ダウンロード] をクリックすることができます。これは、検索用語レポートを CSV 形式でダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9f393-131">Once the job completes, you can click on the row for the search term report and click "Download", which will download the search term report in a CSV format.</span></span> <span data-ttu-id="9f393-132">(検索用語、ピボット) の組ごとに1つの行があり、各行には次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f393-132">There will be one row per (search term, pivots) tuple, and each row will contain the following information:</span></span>

- <span data-ttu-id="9f393-133">取得されたドキュメントの数</span><span class="sxs-lookup"><span data-stu-id="9f393-133">How many documents were retrieved?</span></span>

- <span data-ttu-id="9f393-134">検索用語がドキュメント全体で検出された回数は何回ですか。</span><span class="sxs-lookup"><span data-stu-id="9f393-134">How many times was the search term found across the documents?</span></span>

- <span data-ttu-id="9f393-135">取得したドキュメントの合計量はどの程度ですか。</span><span class="sxs-lookup"><span data-stu-id="9f393-135">What is the total volume of retrieved documents?</span></span>

- <span data-ttu-id="9f393-136">取得されたファミリの数</span><span class="sxs-lookup"><span data-stu-id="9f393-136">How many families were retrieved?</span></span>

- <span data-ttu-id="9f393-137">検索語が含まれていないドキュメントを含む、それらのファミリのドキュメント数の合計はどれくらいですか?</span><span class="sxs-lookup"><span data-stu-id="9f393-137">What is the total document count of those families, including the documents that did not have the search term?</span></span>

- <span data-ttu-id="9f393-138">上記の合計ボリュームはどの程度ですか。</span><span class="sxs-lookup"><span data-stu-id="9f393-138">What is the total volume of the above?</span></span>