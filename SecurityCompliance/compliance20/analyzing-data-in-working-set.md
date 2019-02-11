---
title: 高度な電子的証拠開示 (プレビュー) での作業セット内のデータを分析します。
ms.author: markjjo
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
ms.openlocfilehash: 68a8b7586700a9bffe78f2b3a4ff419a1f85ba8a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695143"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a><span data-ttu-id="36fa3-102">高度な電子的証拠開示 (プレビュー) での作業セット内のデータを分析します。</span><span class="sxs-lookup"><span data-stu-id="36fa3-102">Analyze data in a working set in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="36fa3-p101">収集したドキュメントの数が大きい場合は、それらすべてを確認するのには非常に困難ができます。高度な電子的証拠開示 (プレビュー) には、さまざまな情報を損なうことがなく情報を確認して、一貫した方法でドキュメントを整理するために、ドキュメントの量を減らすためにドキュメントを分析するツールが用意されています。これらの機能に関する詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36fa3-p101">When the number of collected documents is large, it can be quite difficult to review them all. Advanced eDiscovery (Preview) provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner. To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="36fa3-106">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="36fa3-106">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="36fa3-107">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="36fa3-107">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="36fa3-108">テーマ</span><span class="sxs-lookup"><span data-stu-id="36fa3-108">Themes</span></span>](themes.md)

<span data-ttu-id="36fa3-109">ワーキング セット内のデータを分析するには。</span><span class="sxs-lookup"><span data-stu-id="36fa3-109">To analyze data in a working set:</span></span>

1. <span data-ttu-id="36fa3-p102">ケースの分析の設定を構成します。詳細については、[検索および分析の設定の構成](configure-search-analytics-settings.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36fa3-p102">Configure analytics settings for your case. For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>
2. <span data-ttu-id="36fa3-112">分析するワーキング セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="36fa3-112">Open the working set you wish to analyze.</span></span>
3. <span data-ttu-id="36fa3-113">管理作業の設定] に移動します。</span><span class="sxs-lookup"><span data-stu-id="36fa3-113">Go to "Manage working set".</span></span>
4. <span data-ttu-id="36fa3-114">[分析] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36fa3-114">Click "Analyze".</span></span>

<span data-ttu-id="36fa3-115">場合は、[ジョブ] タブで分析の進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="36fa3-115">You can check the progress of analysis in the Jobs tab in your case.</span></span>

 <span data-ttu-id="36fa3-116">分析が完了すると、分析レポートを表示することができますが作業中のクエリを実行の詳細については[、作業中のクエリを設定](working-set-search.md)) は、「分析の出力に設定し (詳細についてはを参照してください[の特定のドキュメントに関連するドキュメントを参照してください。ワーキング セット内のデータを確認する](reviewing-data-in-working-set.md))。</span><span class="sxs-lookup"><span data-stu-id="36fa3-116">Once analysis is completed, you can view analytics report, run queries within your working set on outputs of the analysis (for more information see [Query within your working set](working-set-search.md)), and see related documents of a given document (for more information see [Reviewing data in working set](reviewing-data-in-working-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="36fa3-117">分析レポート</span><span class="sxs-lookup"><span data-stu-id="36fa3-117">Analytics report</span></span>

<span data-ttu-id="36fa3-118">ワーキング セットの分析レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="36fa3-118">To view a analytics report for your working set:</span></span>

1. <span data-ttu-id="36fa3-119">ワーキング セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="36fa3-119">Open your working set.</span></span>
2. <span data-ttu-id="36fa3-120">管理作業の設定] に移動します。</span><span class="sxs-lookup"><span data-stu-id="36fa3-120">Go to "Manage working set".</span></span>
3. <span data-ttu-id="36fa3-121">[レポート] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36fa3-121">Click "Report".</span></span>

<span data-ttu-id="36fa3-122">レポートには、分析からの 4 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="36fa3-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="36fa3-123">**内訳**の数の e メール、添付ファイル、および柔軟なドキュメントは、ワーキング セットに見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="36fa3-123">**Breakdown** - How many emails, attachments, and loose documents were found in the working set.</span></span>

- <span data-ttu-id="36fa3-124">**ドキュメント (を添付ファイルを除く)** の緩やかなドキュメントの数が、ピボットの重複または別のドキュメントの完全な複製に近い独自のピボットをしました。</span><span class="sxs-lookup"><span data-stu-id="36fa3-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="36fa3-125">**メール**・ inclusives、包括的なコピー、包括的な短所は、上記のいずれかに e メールの数がいた。</span><span class="sxs-lookup"><span data-stu-id="36fa3-125">**Emails** - How many emails were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="36fa3-126">**添付ファイル**を電子メールの添付ファイルをどのように多くの固有またはワーキング セット内の別の電子メールの添付ファイルの重複を許可します。</span><span class="sxs-lookup"><span data-stu-id="36fa3-126">**Attachments** - How many email attachments were unique or duplicates of a different email attachment within the working set.</span></span>