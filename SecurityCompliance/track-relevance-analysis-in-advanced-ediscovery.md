---
title: Office 365 の詳細な電子情報開示で関連性分析を追跡する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Office 365 Advanced eDiscovery で関連性トレーニングの状態とケース問題の結果を表示して解釈する方法について説明します。  '
ms.openlocfilehash: 1018b414d0192491feebfbec25d865d4463fa26a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158329"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="43022-103">Office 365 の詳細な電子情報開示で関連性分析を追跡する</span><span class="sxs-lookup"><span data-stu-id="43022-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="43022-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="43022-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="43022-106">上級電子情報開示の場合、[関連性の追跡] タブには、[タグ] タブで実行された関連トレーニングの検証済みの有効性が表示され、関連性のある反復トレーニングプロセスにおける次の手順が示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="43022-107">関連性トレーニングの状態を追跡する</span><span class="sxs-lookup"><span data-stu-id="43022-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="43022-108">次の [**問題名**] ダイアログの例に示されているように、ケースに関する問題については、次の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43022-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="43022-109">**評価**: この進捗状況の指標は、このポイントに対して関連性トレーニングを実施した結果が、エラーの範囲内で評価目標を達成したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="43022-109">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="43022-110">関連性のトレーニング結果の豊富さも表示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-110">The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="43022-111">**トレーニング**: この色分けされた進行状況インジケーターとツールヒント表示は、関連性トレーニング結果の安定性と、各問題に対してタグ付けされた関連性トレーニングサンプルの数を示す数値スケールを示しています。</span><span class="sxs-lookup"><span data-stu-id="43022-111">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="43022-112">専門家は、反復的な関連性トレーニングプロセスの進行状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="43022-112">The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="43022-113">**バッチ計算**: この進捗状況のインジケーターは、バッチ計算の完了に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="43022-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="43022-114">**次の手順**: 実行する次の手順に関する推奨事項を表示します。</span><span class="sxs-lookup"><span data-stu-id="43022-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="43022-115">この例では、問題の評価が正常に完了したことが表示されます。これは、完了した色の進行状況インジケーターとチェックマークで示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-115">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="43022-116">タグ付けは進行中ですが、ケースは依然として不安定であると見なされます (安定性の状態もツールヒントに表示されます)。</span><span class="sxs-lookup"><span data-stu-id="43022-116">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="43022-117">次に推奨される手順は、"トレーニング" です。</span><span class="sxs-lookup"><span data-stu-id="43022-117">The next step recommendation is "Training".</span></span> 
    
    ![関連性トラックのトレーニングのステップ 1](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="43022-119">拡張ビューには、追加情報とオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-119">The expanded view displays additional information and options.</span></span> <span data-ttu-id="43022-120">表示されている現在の誤差の余白は、既存の (既にタグ付けされた) 評価ファイルがある場合に、評価の現在の状態における呼び戻しの誤差範囲です。</span><span class="sxs-lookup"><span data-stu-id="43022-120">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="43022-121">評価ステージは、問題ごとに [**評価**] チェックボックスをオフにしてから、[すべての問題] に対して省略できます。</span><span class="sxs-lookup"><span data-stu-id="43022-121">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="43022-122">そのため、この問題に関する統計情報はありません。</span><span class="sxs-lookup"><span data-stu-id="43022-122">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="43022-123">> [**評価**] チェックボックスをオフにするには、評価が実行される前にしか実行できません。</span><span class="sxs-lookup"><span data-stu-id="43022-123">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="43022-124">複数の問題が存在する場合は、各問題のチェックボックスがオフになっている場合にのみ評価が省略されます。</span><span class="sxs-lookup"><span data-stu-id="43022-124">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="43022-125">最初のサンプルセットのファイルで評価が完了していない場合は、さらにファイルにタグ付けするための次の手順として評価されることがあります。</span><span class="sxs-lookup"><span data-stu-id="43022-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="43022-126">**関連性** \> **トラック**では、トレーニングの進行状況インジケーターとツールヒントは、安定性に必要な追加サンプルの推定数を示します。</span><span class="sxs-lookup"><span data-stu-id="43022-126">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="43022-127">この推定は、必要な追加トレーニングのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="43022-127">This estimate provides a guideline for the additional training needed.</span></span>
    
    ![関連性トラックのトレーニング](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="43022-129">タグ付けが完了し、トレーニングを続行する必要がある場合は、[**トレーニング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43022-129">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="43022-130">ファイルの別のサンプルセットは、追加のトレーニング用に、読み込まれたファイルセットから生成されます。</span><span class="sxs-lookup"><span data-stu-id="43022-130">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="43022-131">その後、[タグ] タブに戻り、追加のファイルのタグ付けとトレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="43022-131">You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="43022-132">安定したトレーニングレベルへの到達</span><span class="sxs-lookup"><span data-stu-id="43022-132">Reaching stable training levels</span></span>

<span data-ttu-id="43022-133">評価ファイルが安定したレベルのトレーニングを取得したら、高度な電子情報開示をバッチ計算の準備が整っています。</span><span class="sxs-lookup"><span data-stu-id="43022-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43022-134">通常、3つの安定したトレーニングサンプルの後、次の手順は "Batch calculation" です。</span><span class="sxs-lookup"><span data-stu-id="43022-134">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="43022-135">前のサンプルからのファイルのタグ付けが変更された場合や、seed ファイルが追加された場合など、例外が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="43022-135">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="43022-136">バッチ計算の実行</span><span class="sxs-lookup"><span data-stu-id="43022-136">Performing Batch calculation</span></span>

<span data-ttu-id="43022-137">一括計算は、トレーニングが正常に完了した後、次のステップとして実行されます (安定したトレーニングの状態が進行状況バーに表示されている場合、ツールヒントにチェックマークが付いている場合)。バッチ計算では、関連性トレーニング中に取得した知識を、ファイルの関連性を評価し、関連性スコアを割り当てるために、ファイルの作成全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="43022-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="43022-138">複数の問題がある場合、バッチ計算は問題ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="43022-138">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="43022-139">バッチの計算中に、すべてのファイルを処理している間、進行状況が監視されます。</span><span class="sxs-lookup"><span data-stu-id="43022-139">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="43022-140">ここで、推奨される次の手順は "なし" で、これは、この時点で反復的な関連トレーニングが不要であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="43022-140">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="43022-141">次のフェーズは、 **[ \>関連性の決定**] タブです。</span><span class="sxs-lookup"><span data-stu-id="43022-141">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="43022-142">バッチ計算後に新しいファイルをインポートする場合、管理者はインポートされたファイルを新しい負荷に追加できます。</span><span class="sxs-lookup"><span data-stu-id="43022-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43022-143">[バッチ計算中に**キャンセル**] をクリックすると、プロセスは既に実行された処理を保存します。</span><span class="sxs-lookup"><span data-stu-id="43022-143">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="43022-144">バッチ計算を再度実行すると、最後に実行された時点から処理が続行されます。</span><span class="sxs-lookup"><span data-stu-id="43022-144">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="43022-145">タグの一貫性の評価</span><span class="sxs-lookup"><span data-stu-id="43022-145">Assessing tagging consistency</span></span>

<span data-ttu-id="43022-146">ファイルのタグ付けに不整合がある場合は、分析に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="43022-146">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="43022-147">高度な電子情報開示のタグ付けの一貫性のプロセスは、結果が最適でない場合、または一貫性が不明な場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="43022-147">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="43022-148">一貫性のないタグ付きファイルの一覧が返され、必要に応じてレビューしてタグを再設定することができます。</span><span class="sxs-lookup"><span data-stu-id="43022-148">A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43022-149">評価の後に7つ以上のトレーニングラウンドを行うと、**関連性** \> **トラック** \> **の問題** \>の**詳細な** \> **トレーニングの進行状況**でタグの一貫性を確認できます。</span><span class="sxs-lookup"><span data-stu-id="43022-149">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="43022-150">このレビューは、一度に1つの問題に対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="43022-150">This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="43022-151">**関連性\>トラック**で、問題の行を展開します。</span><span class="sxs-lookup"><span data-stu-id="43022-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="43022-152">**次の手順**の右側で、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43022-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="43022-153">7つのトレーニングサンプル\*\*\*\* の後に [**タグの不一致**] オプションを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43022-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="43022-154">[**タグの不整合**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="43022-154">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="43022-155">**タグ**タブが開き、必要に応じて再タグ付けするための不整合の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-155">The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="43022-156">[**計算**] をクリックして変更を送信します。</span><span class="sxs-lookup"><span data-stu-id="43022-156">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="43022-157">タグ付けの不整合の後の次の手順は、"トレーニング" です。</span><span class="sxs-lookup"><span data-stu-id="43022-157">The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="43022-158">関連性の結果の表示と使用</span><span class="sxs-lookup"><span data-stu-id="43022-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="43022-159">[**関連\>トラック**] タブで、問題の行を展開し、[**詳細な結果**] の横にある [**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43022-159">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="43022-160">次に示すように、詳細な結果ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-160">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![関連性トレーニングの詳細な結果](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="43022-162">タグ付けの概要</span><span class="sxs-lookup"><span data-stu-id="43022-162">Tagging summary</span></span>

 <span data-ttu-id="43022-163">次に示す例では、**タグ付けの概要**に、評価、トレーニング、およびキャッチアップファイルのタグ付けプロセスごとの合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![関連性トラックのタグ付けの概要](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="43022-165">キーワード</span><span class="sxs-lookup"><span data-stu-id="43022-165">Keywords</span></span>

<span data-ttu-id="43022-166">キーワードは、ファイルが関連しているかどうかを示す重要な指標として、Advanced 電子情報開示によって識別されたファイル内の一意の文字列、単語、語句、または一連の単語です。</span><span class="sxs-lookup"><span data-stu-id="43022-166">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="43022-167">関連としてタグ付けされたファイルの "Include" 列のリストキーワードと重み、[除外] 列は、関連性がないファイルのキーワードと重みを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="43022-167">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="43022-168">上級電子情報開示では、負または正のキーワードの重み値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="43022-168">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="43022-169">重みが高くなるほど、キーワードが表示されるファイルの方が、バッチ計算の間により関連性の高いスコアが割り当てられる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="43022-169">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="43022-170">上級電子情報開示リストは、エキスパートによって作成されたリストを補足するため、またはファイルレビュープロセスの任意の時点で間接的な正当性チェックとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="43022-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="43022-171">トレーニングの進捗状況</span><span class="sxs-lookup"><span data-stu-id="43022-171">Training progress</span></span>

<span data-ttu-id="43022-172">**トレーニングの進行状況**ウィンドウには、次の例に示すように、トレーニングの進行状況のグラフと品質インジケーター表示が含まれています。</span><span class="sxs-lookup"><span data-stu-id="43022-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![関連性トラックのトレーニングの進捗状況](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="43022-174">**トレーニング品質インジケーター**: タグの一貫性の評価を次のように表示します。</span><span class="sxs-lookup"><span data-stu-id="43022-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="43022-175">**良好**: ファイルに一貫したタグが付けられます。</span><span class="sxs-lookup"><span data-stu-id="43022-175">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="43022-176">(緑色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="43022-176">(Green light displayed)</span></span>
    
- <span data-ttu-id="43022-177">**中**: 一部のファイルのタグが一貫していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="43022-177">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="43022-178">(黄色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="43022-178">(Yellow light displayed)</span></span>
    
- <span data-ttu-id="43022-179">**警告**: 多くのファイルのタグ付けに一貫性がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="43022-179">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="43022-180">(赤のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="43022-180">(Red light displayed)</span></span>
    
 <span data-ttu-id="43022-181">**トレーニングの進行状況のグラフ**: 多くの関連性トレーニングサイクルを F メジャーの値と比較した場合の、関連性トレーニングの安定性の程度を示します。</span><span class="sxs-lookup"><span data-stu-id="43022-181">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="43022-182">グラフ上の左から右に移動すると、関連性のトレーニング結果が最適化されている場合に、信頼性を向上させるために、高度な電子情報開示の関連性によって、信頼度の値が、F メジャーと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="43022-182">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43022-183">関連性は F2 を使用します。この指標では、呼び戻しが精度の2倍の重量を受け取る F メジャーの指標です。</span><span class="sxs-lookup"><span data-stu-id="43022-183">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="43022-184">高 (25%) の場合、関連性は F1 (1:1 比) を使用します。</span><span class="sxs-lookup"><span data-stu-id="43022-184">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="43022-185">[**関連性** \>の設定] の**詳細設定**では、F メジャーの比率を構成できます。</span><span class="sxs-lookup"><span data-stu-id="43022-185">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="43022-186">バッチ計算の結果</span><span class="sxs-lookup"><span data-stu-id="43022-186">Batch calculation results</span></span>

<span data-ttu-id="43022-187">[**バッチ計算の結果**] ウィンドウには、次のように、関連性を考慮してスコアされたファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="43022-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="43022-188">**Success**</span></span>
    
- <span data-ttu-id="43022-189">**Empty**: テキストを含まない (スペース/タブのみなど)</span><span class="sxs-lookup"><span data-stu-id="43022-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="43022-190">**失敗**: サイズが大きすぎるか、読み取れませんでした</span><span class="sxs-lookup"><span data-stu-id="43022-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="43022-191">**無視**: サイズが大きすぎるため</span><span class="sxs-lookup"><span data-stu-id="43022-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="43022-192">**Nebulous**: 無意味なテキストが含まれているか、問題に関連する機能がありません</span><span class="sxs-lookup"><span data-stu-id="43022-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="43022-193">Empty、Failed、無視、または Nebulous は、-1 の関連性スコアを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="43022-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="43022-194">トレーニングの統計</span><span class="sxs-lookup"><span data-stu-id="43022-194">Training statistics</span></span>

<span data-ttu-id="43022-195">[**トレーニング統計**] ウィンドウには、高度な電子情報開示の関連性トレーニングからの結果に基づいて、統計とグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![関連性トラックのトレーニング統計情報](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="43022-197">このビューには次のものが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-197">This view shows the following:</span></span>
  
- <span data-ttu-id="43022-198">**レビュー-取り消し比率**: できる線型レビューの関連性スコアに従った結果の比較。</span><span class="sxs-lookup"><span data-stu-id="43022-198">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="43022-199">呼び戻しは、レビューセットのサイズが設定されていると推定されます。</span><span class="sxs-lookup"><span data-stu-id="43022-199">Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="43022-200">**パラメーター**: ケース全体のファイルの作成に関連して、レビューセットに関連する累積計算された統計情報。</span><span class="sxs-lookup"><span data-stu-id="43022-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="43022-201">**レビュー**: このカットオフに基づいてレビューするファイルのパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="43022-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="43022-202">[**呼び戻し**: 校閲セット内の関連ファイルのパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="43022-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="43022-203">**関連性スコア別の配布**: 濃い灰色表示のファイルは、左側にカットオフスコアの下にあります。</span><span class="sxs-lookup"><span data-stu-id="43022-203">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="43022-204">ツールヒントには、関連スコアと、レビューファイルセット内のファイルの関連パーセンテージが、ファイル総数に対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="43022-204">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="43022-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="43022-205">See also</span></span>

[<span data-ttu-id="43022-206">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="43022-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="43022-207">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="43022-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="43022-208">評価の実行とレビュー</span><span class="sxs-lookup"><span data-stu-id="43022-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="43022-209">関連性トレーニングの実行</span><span class="sxs-lookup"><span data-stu-id="43022-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="43022-210">結果に基づいて決定を行う</span><span class="sxs-lookup"><span data-stu-id="43022-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="43022-211">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="43022-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

