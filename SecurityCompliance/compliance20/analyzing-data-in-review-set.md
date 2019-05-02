---
title: 高度な電子情報開示のレビューセットのデータを分析する
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
ms.openlocfilehash: c765234e1aa0738415f66f90b66ebce0fcab2505
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527213"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="06e70-102">高度な電子情報開示のレビューセットのデータを分析する</span><span class="sxs-lookup"><span data-stu-id="06e70-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="06e70-103">収集されたドキュメントの数が多い場合は、それらをすべて確認するのは非常に困難です。</span><span class="sxs-lookup"><span data-stu-id="06e70-103">When the number of collected documents is large, it can be quite difficult to review them all.</span></span> <span data-ttu-id="06e70-104">Advanced eDiscovery には、ドキュメントを分析して、情報が失われずにレビューされるドキュメントのボリュームを減らし、一貫性のある方法でドキュメントを整理するのに役立つさまざまなツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="06e70-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="06e70-105">これらの機能の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06e70-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="06e70-106">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="06e70-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="06e70-107">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="06e70-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="06e70-108">テーマ</span><span class="sxs-lookup"><span data-stu-id="06e70-108">Themes</span></span>](themes.md)

<span data-ttu-id="06e70-109">レビューセット内のデータを分析するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="06e70-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="06e70-110">ケースの分析設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="06e70-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="06e70-111">詳細については、「 [Configure search and analytics settings](configure-search-analytics-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06e70-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="06e70-112">分析するレビューセットを開きます。</span><span class="sxs-lookup"><span data-stu-id="06e70-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="06e70-113">[**レビューセットの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06e70-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="06e70-114">[**分析**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06e70-114">Click **Analyze**.</span></span>

<span data-ttu-id="06e70-115">ケースの [**ジョブ**] タブで、分析の進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="06e70-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="06e70-116">分析が完了したら、analytics レポートを表示し、分析の出力に対してレビューセット内でクエリを実行し ([レビューセット内のクエリ](review-set-search.md)を参照)、特定のドキュメントの関連ドキュメントを表示できます (「[レビューセット内のデータ](reviewing-data-in-review-set.md)のレビュー」を参照)。</span><span class="sxs-lookup"><span data-stu-id="06e70-116">After analysis is completed, you can view analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="06e70-117">分析レポート</span><span class="sxs-lookup"><span data-stu-id="06e70-117">Analytics report</span></span>

<span data-ttu-id="06e70-118">レビューセットの分析レポートを表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="06e70-118">To view a analytics report for a review set:</span></span>

1. <span data-ttu-id="06e70-119">レビューセットを開きます。</span><span class="sxs-lookup"><span data-stu-id="06e70-119">Open the review set.</span></span>

2. <span data-ttu-id="06e70-120">[**レビューセットの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06e70-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="06e70-121">[**レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06e70-121">Click **Report**.</span></span>

<span data-ttu-id="06e70-122">レポートには、分析の4つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="06e70-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="06e70-123">**内訳**: レビューセットに含まれている電子メールメッセージ、添付ファイル、およびルースドキュメントの数。</span><span class="sxs-lookup"><span data-stu-id="06e70-123">**Breakdown** - How many email messages, attachments, and loose documents were found in the review set.</span></span>

- <span data-ttu-id="06e70-124">**ドキュメント (添付ファイルを除く)** -ピボットされたルースドキュメントの数、ピボットの一意の重複、または別のドキュメントの正確な複製。</span><span class="sxs-lookup"><span data-stu-id="06e70-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="06e70-125">**電子**メール-inclusives の電子メールメッセージの数、包括的なコピー、包括的な minuses、または上記のいずれも含まれません。</span><span class="sxs-lookup"><span data-stu-id="06e70-125">**Emails** - How many email messages were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="06e70-126">**添付ファイル**: レビューセット内の別の電子メール添付ファイルの一意または重複した電子メール添付ファイルの数。</span><span class="sxs-lookup"><span data-stu-id="06e70-126">**Attachments** - How many email attachments were unique or duplicates of a another email attachment in the review set.</span></span>