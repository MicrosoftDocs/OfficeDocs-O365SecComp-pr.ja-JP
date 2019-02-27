---
title: 高度な電子情報開示で作業セット内のデータを分析する (プレビュー)
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
ms.openlocfilehash: e3f3e863423fe4312a944eb6f04a58182e11665c
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295480"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a><span data-ttu-id="ee6a5-102">高度な電子情報開示で作業セット内のデータを分析する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ee6a5-102">Analyze data in a working set in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="ee6a5-p101">収集されたドキュメントの数が多い場合は、それらをすべて確認するのは非常に困難です。Advanced eDiscovery (プレビュー) には、ドキュメントを分析して、情報が失われずにレビューされるドキュメントのボリュームを減らし、一貫性のある方法でドキュメントを整理するのに役立つさまざまなツールが用意されています。これらの機能の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-p101">When the number of collected documents is large, it can be quite difficult to review them all. Advanced eDiscovery (Preview) provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner. To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="ee6a5-106">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="ee6a5-106">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="ee6a5-107">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="ee6a5-107">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="ee6a5-108">テーマ</span><span class="sxs-lookup"><span data-stu-id="ee6a5-108">Themes</span></span>](themes.md)

<span data-ttu-id="ee6a5-109">作業セット内のデータを分析するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-109">To analyze data in a working set:</span></span>

1. <span data-ttu-id="ee6a5-p102">ケースの分析設定を構成します。詳細については、「 [Configure search and analytics settings](configure-search-analytics-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-p102">Configure analytics settings for your case. For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>
2. <span data-ttu-id="ee6a5-112">分析する作業セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-112">Open the working set you wish to analyze.</span></span>
3. <span data-ttu-id="ee6a5-113">[作業セットの管理] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-113">Go to "Manage working set".</span></span>
4. <span data-ttu-id="ee6a5-114">[分析] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-114">Click "Analyze".</span></span>

<span data-ttu-id="ee6a5-115">ケースの [ジョブ] タブで、分析の進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-115">You can check the progress of analysis in the Jobs tab in your case.</span></span>

 <span data-ttu-id="ee6a5-116">分析が完了すると、分析レポートを表示し、分析の出力に対して作業セット内でクエリを実行できます (詳細については[、「作業セット内のクエリ](working-set-search.md)」を参照してください)。詳細については、「関連ドキュメント」を参照してください[。作業セット内のデータを確認](reviewing-data-in-working-set.md)します)。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-116">Once analysis is completed, you can view analytics report, run queries within your working set on outputs of the analysis (for more information see [Query within your working set](working-set-search.md)), and see related documents of a given document (for more information see [Reviewing data in working set](reviewing-data-in-working-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="ee6a5-117">分析レポート</span><span class="sxs-lookup"><span data-stu-id="ee6a5-117">Analytics report</span></span>

<span data-ttu-id="ee6a5-118">作業セットの分析レポートを表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-118">To view a analytics report for your working set:</span></span>

1. <span data-ttu-id="ee6a5-119">ワーキングセットを開きます。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-119">Open your working set.</span></span>
2. <span data-ttu-id="ee6a5-120">[作業セットの管理] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-120">Go to "Manage working set".</span></span>
3. <span data-ttu-id="ee6a5-121">[レポート] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-121">Click "Report".</span></span>

<span data-ttu-id="ee6a5-122">レポートには、分析の4つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="ee6a5-123">**内訳**: 作業セットに含まれているメール、添付ファイル、および圧縮されていないドキュメントの数。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-123">**Breakdown** - How many emails, attachments, and loose documents were found in the working set.</span></span>

- <span data-ttu-id="ee6a5-124">**ドキュメント (添付ファイルを除く)** -ピボットされたルースドキュメントの数、ピボットの一意の重複、または別のドキュメントの正確な複製。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="ee6a5-125">**電子メール**: inclusives、包括的なコピー、包括的に使用、または上記のいずれも含まれないメールの数。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-125">**Emails** - How many emails were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="ee6a5-126">**添付ファイル**: 作業セット内の別の電子メール添付ファイルの一意の、または重複した電子メール添付ファイルの数。</span><span class="sxs-lookup"><span data-stu-id="ee6a5-126">**Attachments** - How many email attachments were unique or duplicates of a different email attachment within the working set.</span></span>