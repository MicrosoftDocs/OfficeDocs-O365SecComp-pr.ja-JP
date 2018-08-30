---
title: Office 365 Advanced eDiscovery の評価と関連性について理解する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: '評価ステージと Office 365 の高度な電子的証拠の開示に関連性の高いトレーニング中に問題の豊富な機能を判断する際にその役割の概要を取得します。  '
ms.openlocfilehash: a54a4134609b16568586f3cb6b60ebdeba860bac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532159"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a><span data-ttu-id="18c28-103">Office 365 Advanced eDiscovery の評価と関連性について理解する</span><span class="sxs-lookup"><span data-stu-id="18c28-103">Understand Assessment in Relevance in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="18c28-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="18c28-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="18c28-p102">高度な電子的証拠開示は、定義済みの問題とサポート案件のインポート データのなどの初期評価を使用できます。高度な電子的証拠開示では、専門家が採用されている方法に関連する決定を下すと、そのプロジェクトに適用する、ドキュメントのレビューが有効にします。</span><span class="sxs-lookup"><span data-stu-id="18c28-p102">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case. Advanced eDiscovery enables the expert to make decisions pertaining to an adopted approach and to apply them to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="18c28-108">についての評価</span><span class="sxs-lookup"><span data-stu-id="18c28-108">Understanding assessment</span></span>

<span data-ttu-id="18c28-p103">評価では、上級者は、500 以上のファイルが問題の豊富な機能を決定し、トレーニングの結果を反映した統計情報を生成するために使用される一連のランダムなを確認します。役立つ高度な電子的証拠開示関連性の高い正確な統計情報を提供し、効果的にトレーニング プロセスの安定化のポイントを決定する統計のレベルに到達するための十分な関連するファイルが見つかった場合、評価は成功します。</span><span class="sxs-lookup"><span data-stu-id="18c28-p103">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results. Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="18c28-p104">ほど関連するファイルのセットでは評価より正確な統計情報と安定性のアルゴリズムの有効性。評価ファイル内の関連するファイルの数は、問題の量によって決まります。豊富な機能は、問題に関連する一連の関連するファイルの推定割合です。豊富な機能に問題に到達関連するファイル数が多くなる問題よりも早く下の豊富な機能を持つ。低非常に豊富な機能に問題 (たとえば 2% 以下)、非常に大規模な評価が非常に多くの関連するファイルにアクセスするのには設定が必要になります。</span><span class="sxs-lookup"><span data-stu-id="18c28-p104">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm. The number of relevant files within the assessment files depends on the richness of the issue. Richness is the estimated percent of relevant files in the set relevant to an issue. Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness. Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="18c28-p105">トレーニング中に、バッチ計算の後、トラックとを決定するタブの表示は、統計情報には、別の表示設定の取り消しの見積もりが含まれます。統計学のサンプルに基づく見積もりを設定 (ここでは評価のファイル) の誤差とそのエラーの余白の信頼レベルが含まれます。たとえば、80% の推定のリコールは、95% の信頼レベルでのプラスまたはマイナス 5% のエラーの余白があります。これは、推定のリコールは、実際には 75-85% と、この見積は、95% の信頼度を持つことを意味します。評価のセットが大きいほどの誤差が小さくなり、統計情報がより正確です。</span><span class="sxs-lookup"><span data-stu-id="18c28-p105">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets. In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin. For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%. This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence. The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="18c28-p106">エキスパートが、500 個のファイルのセットで初期評価を確認した後の関連性がリコール対象の値のエラーの現在のマージンを決定します。関連性は評価の設定を最適化するために到達することをお勧めするエラーの既定の余白を設定します。例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="18c28-p106">After the expert reviews an initial assessment set of 500 files, Relevance is able to determine the current margin of error of the recall values. Relevance will also set a default margin of error that it recommends to reach to optimize the assessment set. Following are some examples:</span></span>
  
- <span data-ttu-id="18c28-124">セットは既に評価は、プラスまたはマイナス 10% のエラーの余白を表示、関連性が (その他の評価のレビューは必要ありません) のトレーニングに移動するを推奨します。</span><span class="sxs-lookup"><span data-stu-id="18c28-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend to move on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="18c28-125">評価セットには、プラスまたはマイナス 13% のエラーの余白が返されます、関連性はの到達の余白を小さくするために評価の確認をお勧め可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18c28-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="18c28-126">豊富な機能が非常に低い場合は、関連性の誤差が大きく (なることが統計現実的ではありません) 場合でも、評価を停止するように推奨、ため、有用なエラーの余白に到達するために必要な評価のセットが大きすぎます。</span><span class="sxs-lookup"><span data-stu-id="18c28-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="18c28-p107">各問題独自の豊富な機能、現在の余白の誤差があり、その結果、ファイルの他の評価の数を推定します。(最大 1 つのセットでは 1,000 個) のファイルの最大数に応じて次のアセスメント セットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="18c28-p107">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files. The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="18c28-p108">関連の推奨事項を受け入れるか、必要に応じて、現在のエラーの余白を調整できます。エラーの現在の既定のマージンは、リコール等の以上の 75% に決定されます。</span><span class="sxs-lookup"><span data-stu-id="18c28-p108">You can accept the Relevance recommendations or adjust the current margin of error according to your needs. The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="18c28-p109">評価段階は省略可能で、**の関連性\>トラック**案件ごととし、すべての問題」の [**評価**] チェック ボックスをオフにして、問題の展開されたビュー内のタブです。ただし、その結果、されませんこの問題の統計情報です。> 評価を実行する前に、、[**評価**] チェック ボックスをオフにするを実行のみできます。各問題のチェック ボックスがオフになっている場合にのみ評価がバイパスされる場合に、複数の問題が存在する場所</span><span class="sxs-lookup"><span data-stu-id="18c28-p109">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="18c28-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="18c28-135">See also</span></span>

[<span data-ttu-id="18c28-136">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="18c28-136">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="18c28-137">タグ付けおよび評価</span><span class="sxs-lookup"><span data-stu-id="18c28-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="18c28-138">タグ付けと関連性の高いトレーニング</span><span class="sxs-lookup"><span data-stu-id="18c28-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="18c28-139">追跡の関連性の分析</span><span class="sxs-lookup"><span data-stu-id="18c28-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="18c28-140">結果に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="18c28-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="18c28-141">テストの関連性の分析</span><span class="sxs-lookup"><span data-stu-id="18c28-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

