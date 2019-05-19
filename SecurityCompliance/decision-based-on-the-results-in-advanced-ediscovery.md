---
title: Office 365 の高度な電子情報開示の結果に基づく決定
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'Office 365 の Advanced eDiscovery の [判断] タブで、ケースファイルのレビューセットの適切なサイズを決定するのに役立つデータを提供する方法について説明します。 '
ms.openlocfilehash: 3f8ce0343b5a09cf3ab4c4bd94a53d8d0cbe0cce
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153519"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="bc13d-103">Office 365 の高度な電子情報開示の結果に基づく決定</span><span class="sxs-lookup"><span data-stu-id="bc13d-103">Decision based on the results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="bc13d-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="bc13d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="bc13d-106">上級電子情報開示の場合、[判断] タブでは、サポートの判断に関する詳細情報を提供して、ケースファイルのレビューセットのサイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="bc13d-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="bc13d-107">[判断] タブの使用</span><span class="sxs-lookup"><span data-stu-id="bc13d-107">Using the Decide tab</span></span>

![関連性の決定](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="bc13d-109">このタブには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc13d-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="bc13d-110">**問題**: ここから、対象の問題をリストから選択できます。</span><span class="sxs-lookup"><span data-stu-id="bc13d-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="bc13d-111">**レビュー-取り消し率**: 関連性スコアによる高度な電子情報開示レビューの比較。</span><span class="sxs-lookup"><span data-stu-id="bc13d-111">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="bc13d-112">グラフのカットオフポイントは、関連性スコアにマッピングされた、確認するファイルのパーセンテージを表します。</span><span class="sxs-lookup"><span data-stu-id="bc13d-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="bc13d-113">これは、関連性テストフェーズで、カリングのエクスポートしきい値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc13d-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="bc13d-114">既定のカットオフポイントは、確認するファイル数に対して、呼び戻しと精度の間のバランスが最適であるポイントです。</span><span class="sxs-lookup"><span data-stu-id="bc13d-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="bc13d-115">実際のカットオフポイントは、目標とコストのトレードオフ (% レビュー) およびリスク (% のリコール) に応じて、ユーザーによって決定される必要があります。スライダーを使用して、カットオフポイントを調整し、グラフおよびパラメータに対する影響を確認したり、取得する関連ファイルの割合を調整したり、決定を検証したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc13d-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="bc13d-116">**パラメーター**: Review、呼び戻し、次の関連性、およびコストの合計パラメーターは、ケース全体のコレクションに対するレビューセットに関連する累積計算された統計情報です。</span><span class="sxs-lookup"><span data-stu-id="bc13d-116">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="bc13d-117">これらのパラメーターの定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bc13d-117">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="bc13d-118">**レビュー**: このカットオフに基づいてレビューするファイルのパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="bc13d-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="bc13d-119">[**呼び戻し**: 校閲セット内の関連ファイルのパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="bc13d-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="bc13d-120">**次に関連**する: 現在レビューセットに含まれていない追加の関連ファイルを確認して識別するためのコスト。</span><span class="sxs-lookup"><span data-stu-id="bc13d-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="bc13d-121">**合計コスト**: この割合のケースファイルを確認するためのコスト。</span><span class="sxs-lookup"><span data-stu-id="bc13d-121">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="bc13d-122">コストパラメーターの設定は、ケースマネージャーで設定できます。</span><span class="sxs-lookup"><span data-stu-id="bc13d-122">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="bc13d-123">**関連性スコア別の配布**: 濃い灰色表示のファイルは、左側にカットオフスコアの下にあります。</span><span class="sxs-lookup"><span data-stu-id="bc13d-123">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="bc13d-124">ツールヒントには、関連スコアと、レビューファイルセット内のファイルの関連パーセンテージが、ファイル総数に対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc13d-124">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="bc13d-125">拡張された詳細ウィンドウには、追加の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc13d-125">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="bc13d-126">コレクションの図のファイルには、空または nebulous ファイルは含まれません。</span><span class="sxs-lookup"><span data-stu-id="bc13d-126">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="bc13d-127">ファミリーファイル図は、関連性がなく、ファミリーの一部としてカウントされているファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="bc13d-127">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bc13d-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc13d-128">See also</span></span>

[<span data-ttu-id="bc13d-129">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bc13d-129">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="bc13d-130">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="bc13d-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bc13d-131">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="bc13d-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bc13d-132">関連性トレーニングの実行</span><span class="sxs-lookup"><span data-stu-id="bc13d-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bc13d-133">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="bc13d-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bc13d-134">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="bc13d-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

