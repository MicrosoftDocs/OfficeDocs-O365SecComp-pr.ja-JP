---
title: Office 365 Advanced eDiscovery の評価と関連性について理解する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Office 365 Advanced eDiscovery で関連性のトレーニングを実施して、さまざまな問題があるかどうかを判断するための評価ステージとその役割の概要を説明します。
ms.openlocfilehash: 1ddaa7ef37f762d7b63bb6c0c51193ff382b8d6b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30212977"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a><span data-ttu-id="524f3-103">Office 365 Advanced eDiscovery の評価と関連性について理解する</span><span class="sxs-lookup"><span data-stu-id="524f3-103">Understand Assessment in Relevance in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="524f3-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="524f3-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="524f3-p102">上級電子情報開示では、たとえば定義済みの問題とケースに対してインポートされたデータについて、早期に評価することができます。上級電子情報開示を使用すると、エキスパートは、採用されたアプローチに関連する意思決定を行い、ドキュメントレビュープロジェクトに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="524f3-p102">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case. Advanced eDiscovery enables the expert to make decisions pertaining to an adopted approach and to apply them to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="524f3-108">評価について</span><span class="sxs-lookup"><span data-stu-id="524f3-108">Understanding assessment</span></span>

<span data-ttu-id="524f3-p103">評価では、専門家は少なくとも500のファイルのランダムセットをレビューします。これは、問題の豊富さを特定し、トレーニング結果を反映するために統計情報を生成するために使用されます。詳細な電子情報開示の関連性を向上させるために詳細な電子情報開示の関連性を向上させる統計レベルに達すると、評価は成功します。</span><span class="sxs-lookup"><span data-stu-id="524f3-p103">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results. Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="524f3-p104">評価セット内の関連ファイルの数が多いほど、安定性アルゴリズムの統計と効果が正確になります。評価ファイル内の関連ファイルの数は、その問題の豊富さに依存します。多様性は、懸案事項に関連する設定の関連ファイルの予想パーセンテージです。低コストの問題よりも、より高いレベルの関連ファイルをより多く使用すると、低低の問題よりも高速になります。非常に低い (たとえば 2% 以下の) 豊富な問題については、膨大な数の関連ファイルを獲得するために非常に大きな評価を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="524f3-p104">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm. The number of relevant files within the assessment files depends on the richness of the issue. Richness is the estimated percent of relevant files in the set relevant to an issue. Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness. Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="524f3-p105">この統計情報は、トレーニング中に [追跡] タブと [決定] タブに表示されます。また、バッチ計算後には、さまざまなレビューセットに対する呼び戻しの見積もりを含みます。statistics では、サンプルセット (この例では評価ファイル) に基づく見積もりには、エラーの余白と、その誤差範囲の信頼度レベルが含まれています。たとえば、80% の予想リコールは、信頼レベルが 95% で、プラスまたはマイナス 5% の誤差がある可能性があります。これは、推定される呼び戻しは実際には 75%-85% で、この推定は 95% の信頼度があることを意味します。評価セットが大きいほど、エラーの余白が小さくなり、統計値がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="524f3-p105">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets. In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin. For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%. This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence. The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="524f3-p106">専門家が500ファイルの初期評価セットをレビューした後、関連性は呼び戻し値の現在のエラーのマージンを特定することができます。妥当性は、評価セットを最適化するために推奨される既定のエラーのマージンも設定します。次にいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="524f3-p106">After the expert reviews an initial assessment set of 500 files, Relevance is able to determine the current margin of error of the recall values. Relevance will also set a default margin of error that it recommends to reach to optimize the assessment set. Following are some examples:</span></span>
  
- <span data-ttu-id="524f3-124">評価セットで既にプラスまたはマイナス 10% の誤差が得られている場合は、トレーニングに進むことをお勧めします (追加の評価レビューは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="524f3-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend to move on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="524f3-125">評価セットでプラスまたはマイナス 13% の誤差が得られた場合は、別の評価ファイルのセットをレビューして、より小さな余白に到達することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="524f3-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="524f3-126">豊富な機能が非常に低い場合は、エラーの許容範囲を超えている場合でも、評価を停止することをお勧めします (統計値が実用的でない場合)。</span><span class="sxs-lookup"><span data-stu-id="524f3-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="524f3-p107">各問題には、さまざまな豊富なエラーがあり、その結果として予測される追加評価ファイルの推定数が表示されます。次の評価セットは、最大ファイル数 (1 つのセット内の最大 1000) に従って作成されます。</span><span class="sxs-lookup"><span data-stu-id="524f3-p107">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files. The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="524f3-p108">必要に応じて、関連性に関する推奨事項を受け入れるか、または現在の誤差の余白を調整することができます。既定のエラーの現在のマージンは、「呼び戻し」では、75% 以上であることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="524f3-p108">You can accept the Relevance recommendations or adjust the current margin of error according to your needs. The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="524f3-p109">問題が発生した場合は、展開されたビューの [ \*\* \>関連性の追跡**] タブで、問題ごとに [**評価**] チェックボックスをオフにし、次に [すべての問題] を選択して、評価ステージをバイパスできます。そのため、この問題に関する統計情報はありません。> [**評価\*\*] チェックボックスをオフにするには、評価が実行される前にしか実行できません。複数の問題が存在する場合は、各問題のチェックボックスがオフになっている場合にのみ評価が省略されます。</span><span class="sxs-lookup"><span data-stu-id="524f3-p109">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="524f3-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="524f3-135">See also</span></span>

[<span data-ttu-id="524f3-136">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="524f3-136">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="524f3-137">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="524f3-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="524f3-138">タグ付けと関連性トレーニング</span><span class="sxs-lookup"><span data-stu-id="524f3-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="524f3-139">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="524f3-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="524f3-140">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="524f3-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="524f3-141">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="524f3-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

