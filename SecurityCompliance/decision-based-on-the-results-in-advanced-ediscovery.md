---
title: Office 365 Advanced eDiscovery の結果に基づく判断
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'レビュー一連の大文字のファイルの正確なサイズを決定する際に役立つデータを電子的証拠開示の Office 365 の詳細設定で [決定] タブが提供するしくみについて説明します。 '
ms.openlocfilehash: 58a181e00ad5843ccbbde4dcb47050eccf199225
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531864"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="dfc95-103">Office 365 Advanced eDiscovery の結果に基づく判断</span><span class="sxs-lookup"><span data-stu-id="dfc95-103">Decision based on the results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="dfc95-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="dfc95-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="dfc95-106">高度な電子的証拠開示を決定するタブは、表示して、レビューのケースのファイルのサイズを決定する意思決定支援の統計情報を使用してに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dfc95-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="dfc95-107">決定] タブを使用</span><span class="sxs-lookup"><span data-stu-id="dfc95-107">Using the Decide tab</span></span>

![関連性の決定](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="dfc95-109">このタブには次のものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfc95-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="dfc95-110">**問題**: ここでは、一覧から目的の問題を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="dfc95-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="dfc95-p102">**レビュー リコール率**: 妥当性の度合いによって電子的証拠開示の比較の高度なレビューです。グラフ内のカットオフ ポイントは、関連性のスコアにマップを確認して、ファイルの割合を表します。カリングは、エクスポートのしきい値と関連性のテスト フェーズで使用されます。ファイルの数を確認するのには、既定カットオフ ポイントでは、リコールと精度のバランスが最適な位置にします。目標とコストのトレードオフ (% レビュー) とリスク (% リコール) によってユーザーが実際のカットオフ ポイントを決定してください。スライダーを使用すると、カットオフ ポイントを調整し、意思決定を検証する前に取得するには、関連するファイルの % を調整するときにグラフやパラメーターへの影響を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfc95-p102">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores. The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score. This is used in the Relevance Test phase and as an Export threshold for culling. The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal. The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="dfc95-p103">**パラメーター**: を確認し、呼び戻すには、次の関連性の合計コスト パラメーターは、コレクション全体のケースを基準に設定の確認に関連する計算された統計情報の累積的な。これらのパラメーターの定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dfc95-p103">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case. Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="dfc95-118">**確認**: このカットオフ値に基づいて、ファイルの割合を確認します。</span><span class="sxs-lookup"><span data-stu-id="dfc95-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="dfc95-119">**取り消し**: レビューのセットに関連するファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="dfc95-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="dfc95-120">**次関連**: を確認し、レビューにも設定されていないその他の関連のファイルを識別するためのコストです。</span><span class="sxs-lookup"><span data-stu-id="dfc95-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="dfc95-p104">**総コスト**: 大文字のファイルの割合を確認するためのコストです。ケース マネージャーでは、コストのパラメーターの設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="dfc95-p104">**Total cost**: Cost for reviewing this percentage of the case files. Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="dfc95-p105">**関連性のスコアを使用した配分**: カットオフ スコアの下の左側に、濃いグレーで表示内のファイルです。ツール ヒントは、ファイルの合計数を基準に設定確認ファイル内の関連性スコアと関連ファイルの割合を表示します。</span><span class="sxs-lookup"><span data-stu-id="dfc95-p105">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="dfc95-p106">展開の詳細ウィンドウには、追加の詳細が表示されます。図表のコレクション内のファイルでは、空であるか、または漠然としたファイルは含まれません。ファミリのファイルの図は、関連性の高さに読み込まれていないファミリの一部として入っているファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="dfc95-p106">The expanded Details pane displays additional details. Files in collection figures do not include empty or nebulous files. Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dfc95-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfc95-128">See also</span></span>

[<span data-ttu-id="dfc95-129">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="dfc95-129">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="dfc95-130">関連性の評価を理解します。</span><span class="sxs-lookup"><span data-stu-id="dfc95-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="dfc95-131">タグ付けおよび評価</span><span class="sxs-lookup"><span data-stu-id="dfc95-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="dfc95-132">関連性の高いトレーニングを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfc95-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="dfc95-133">追跡の関連性の分析</span><span class="sxs-lookup"><span data-stu-id="dfc95-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="dfc95-134">テストの関連性の分析</span><span class="sxs-lookup"><span data-stu-id="dfc95-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

