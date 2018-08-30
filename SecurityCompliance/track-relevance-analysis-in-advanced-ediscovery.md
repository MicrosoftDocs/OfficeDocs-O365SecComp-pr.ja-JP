---
title: Office 365 Advanced eDiscovery で関係性分析を追跡する
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: '表示し、関連性の高い学習状況と Office 365 の高度な電子的証拠の開示のケースの問題の結果を解釈する方法について説明します。  '
ms.openlocfilehash: a19f7eaabf5dc15eefaa7209ded8261020d0d557
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532804"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="00072-103">Office 365 Advanced eDiscovery で関係性分析を追跡する</span><span class="sxs-lookup"><span data-stu-id="00072-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="00072-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="00072-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="00072-106">高度な電子的証拠開示は、関連性の履歴] タブ、[タグ] タブで実行される関連性の高いトレーニングの計算の有効性が表示されます. トレーニングの反復的なプロセスの妥当性を次の手順を示します</span><span class="sxs-lookup"><span data-stu-id="00072-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="00072-107">関連性の高い学習状況の追跡</span><span class="sxs-lookup"><span data-stu-id="00072-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="00072-108">**発行物の名前**] ダイアログ ボックスの次の例を次に示すようにケースの問題では、関連性の高いトラックの次の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="00072-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="00072-p102">**評価**: 現時点までに実行されたトレーニングとの関連性がどの程度の誤差の観点から評価の対象を達成したこの進行状況インジケーターが示しています。関連性の高いトレーニング結果の豊富な機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00072-p102">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error. The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="00072-p103">**トレーニング**: この色分けされた進行状況インジケーターとツール ヒントの表示は、関連性の高いトレーニング結果の安定性と、各問題の関連性の高いトレーニング サンプルの数を示す数値のスケールがタグ付けされたことを示します。エキスパートは、反復的な関連性の高いトレーニング プロセスの進行状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="00072-p103">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue. The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="00072-113">**バッチ計算**: この進行状況インジケーターには、バッチ計算の完了に関する情報が用意されています。</span><span class="sxs-lookup"><span data-stu-id="00072-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="00072-114">**次のステップ**: 次の手順を実行するための推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00072-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="00072-p104">例では、問題を正常に完了した評価が表示されて完了したカラーの進行状況インジケーターには、チェック マークによって示されます。進行中でタグ付けですが、大文字と小文字が不安定と考えられる (安定性の状態がツール ヒントにも表示)。次の手順に関する推奨事項は、「トレーニング」です。</span><span class="sxs-lookup"><span data-stu-id="00072-p104">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark. Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip). The next step recommendation is "Training".</span></span> 
    
    ![関連性トラックのトレーニングのステップ 1](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="00072-p105">展開されたビューには、追加情報とオプションが表示されます。現在表示されているエラー マージンは、(既にタグ付き) の評価の既存のファイルを指定して、評価の現在の状態でリコール対象のエラーの余白です。</span><span class="sxs-lookup"><span data-stu-id="00072-p105">The expanded view displays additional information and options. The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="00072-p106">案件ごととし、すべての問題」の [**評価**] チェック ボックスをオフにして、評価の段階を省略できます。ただし、その結果、されませんこの問題の統計情報です。> 評価を実行する前に、、[**評価**] チェック ボックスをオフにするを実行のみできます。各問題のチェック ボックスがオフになっている場合にのみ評価がバイパスされる場合に、複数の問題が存在する場所</span><span class="sxs-lookup"><span data-stu-id="00072-p106">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="00072-125">評価を完了していないファイルの最初のサンプルを設定、評価の他のファイルへのタグ付けは、次の手順があります。</span><span class="sxs-lookup"><span data-stu-id="00072-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="00072-p107">**関連性**の\>**トラック**トレーニングの進行状況インジケーターとツール ヒントは、安定性に到達するために必要なその他のサンプル数の推定値を示します。この見積もりは、必要な追加のトレーニングのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="00072-p107">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability. This estimate provides a guideline for the additional training needed.</span></span>
    
    ![関連性トラックのトレーニング](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="00072-p108">終了タグを付けると、トレーニングを継続する必要がありますができたら、**トレーニング**] をクリックします。ファイルの別のサンプル セットは、追加のトレーニングのセット、読み込まれているファイルから生成されます。タグを付けるしより多くのファイルをトレーニングするのには [タグ] タブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="00072-p108">When you're done tagging and if you need to continue training, click **Training**. Another sample set of files is generated from the loaded file set for additional training. You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="00072-132">安定したトレーニングのレベルに到達</span><span class="sxs-lookup"><span data-stu-id="00072-132">Reaching stable training levels</span></span>

<span data-ttu-id="00072-133">評価ファイルは、安定したレベルのトレーニングを達成した、高度な電子的証拠開示がバッチ計算されます。</span><span class="sxs-lookup"><span data-stu-id="00072-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00072-p109">通常、3 には、トレーニング サンプルが安定して後、次の手順には「バッチ計算」です。可能性があります、例外などから、以前のサンプルまたはシード ファイルが追加されたファイルのタグ付けに変更があったとき。</span><span class="sxs-lookup"><span data-stu-id="00072-p109">Usually, after three stable training samples, the next step is "Batch calculation". There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="00072-136">バッチ計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="00072-136">Performing Batch calculation</span></span>

<span data-ttu-id="00072-137">(トレーニングを安定した状態が表示されると、進行状況バー、チェック ボックスをオンし、ツール ヒントに安定した状態で。)、トレーニングが正常に完了したら、次の手順としてバッチ計算が実行されます。バッチ計算では、ファイルの妥当性を評価し、関連性のスコアを割り当てるには、ファイル全体を母集団に関連性の高いトレーニングで習得した知識を適用します。</span><span class="sxs-lookup"><span data-stu-id="00072-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="00072-p110">複数の問題がある場合は、バッチ計算、案件ごとに行われます。バッチの計算時にすべてのファイルの処理中に進行状況が監視されます。</span><span class="sxs-lookup"><span data-stu-id="00072-p110">When there is more than one issue, Batch calculation is done per issue. During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="00072-p111">ここでは、推奨される次のステップが「なし」、その他の反復的な関連性の高いトレーニングが不要であるこの時点でことを示します。次のフェーズでは、**の関連性\>を決定する**] タブ。</span><span class="sxs-lookup"><span data-stu-id="00072-p111">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point. The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="00072-142">バッチ計算の後に新しいファイルをインポートする場合は、管理者は、新しい荷重をインポートするファイルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="00072-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00072-p112">バッチ計算中に [**キャンセル**] をクリックすると、何が既に実行されたプロセスが保存されます。バッチ計算をもう一度を実行する場合プロセスが最後に実行された時点から続行されます。</span><span class="sxs-lookup"><span data-stu-id="00072-p112">If you click **Cancel** during Batch calculation, the process saves what was already executed. If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="00072-145">タグの整合性を評価します。</span><span class="sxs-lookup"><span data-stu-id="00072-145">Assessing tagging consistency</span></span>

<span data-ttu-id="00072-p113">ファイルへのタグ付けに不整合がある場合は、分析を影響することができます。結果が最適ではないかし、の整合性が不定な状態には、高度な電子的証拠開示プロセスの整合性をタグ付けを使用できます。可能な一貫性がないタグ付きファイルの一覧が返され、確認して再タグ付け、必要に応じてすることができます。</span><span class="sxs-lookup"><span data-stu-id="00072-p113">If there are inconsistencies in file tagging, it can affect the analysis. The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt. A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00072-p114">**関連性**の整合性をタグ付け、次の評価を表示できる 7 つ以上のトレーニング ラウンド後\>**トラック** \> **問題** \> **詳細結果** \> **トレーニングの進行状況**。このレビューは、問題の 1 つの時刻に行われます。</span><span class="sxs-lookup"><span data-stu-id="00072-p114">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**. This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="00072-151">**関連\>トラック**、問題の行を展開します。</span><span class="sxs-lookup"><span data-stu-id="00072-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="00072-152">、**次のステップ**の右側に [**変更**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00072-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="00072-153">トレーニングの 7 つのサンプルの後、**次の手順**のオプションとしての**タグの不一致**を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00072-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="00072-p115">**タグの不整合**を選択します。再必要に応じてタグを付けるための矛盾の一覧を表示する**タグ**」タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="00072-p115">Select **Tag inconsistencies**. The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="00072-p116">変更内容を送信するための**計算**をクリックします。矛盾をタグ付けした後、次の手順は、「トレーニング」です。</span><span class="sxs-lookup"><span data-stu-id="00072-p116">Click **Calculate** to submit the changes. The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="00072-158">表示および関連性の結果を使用します。</span><span class="sxs-lookup"><span data-stu-id="00072-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="00072-p117">**の関連性\>トラック**] タブで、問題の行を展開し、**詳細な結果**、] の [**ビュー**] をクリックします。詳細な結果は表示されるように示すように、以下の説明をします。</span><span class="sxs-lookup"><span data-stu-id="00072-p117">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**. The Detailed results panes are displayed, as shown and described below.</span></span>
  
![関連性トレーニングの詳細な結果](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="00072-162">タグの概要</span><span class="sxs-lookup"><span data-stu-id="00072-162">Tagging summary</span></span>

 <span data-ttu-id="00072-163">次に示す例では、**名札管理の概要**は、アセスメント、トレーニング、およびプロセスへのタグ付けキャッチアップのファイルのそれぞれの合計を表示します。</span><span class="sxs-lookup"><span data-stu-id="00072-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![関連性トラックのタグ付けの概要](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="00072-165">Keywords</span><span class="sxs-lookup"><span data-stu-id="00072-165">Keywords</span></span>

<span data-ttu-id="00072-p118">キーワードとは、一意の文字列、単語、語句、またはファイルが関連するかどうかの重要な指標として、高度な電子的証拠開示によって識別されるファイル内の単語の順序です。キーワードと関連性、としてタグ付きファイルの重量「含める」の列を一覧表示し、[除外] 列は、キーワードおよび Not としてタグ付きファイルの重量を示します関連します。</span><span class="sxs-lookup"><span data-stu-id="00072-p118">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant. The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="00072-p119">高度な電子的証拠開示では、正または負のキーワードに、重みの値が割り当てられます。重量が大きいほど、キーワードが表示されているファイルにバッチ計算時に高い関連性スコアが割り当てられている可能性が高い。</span><span class="sxs-lookup"><span data-stu-id="00072-p119">Advanced eDiscovery assigns negative or positive keyword weight values. The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="00072-170">上級者、または、間接的な正当性チェックとして組み込まれたリストを補完するためにキーワードの高度な電子的証拠開示の一覧を使用することができます、ファイル内の任意の時点でプロセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="00072-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="00072-171">トレーニングの進行状況</span><span class="sxs-lookup"><span data-stu-id="00072-171">Training progress</span></span>

<span data-ttu-id="00072-172">**トレーニングの進行状況**ウィンドウには、次の例のように、トレーニングの進行状況のグラフと品質インジケーターの表示が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00072-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![関連性トラックのトレーニングの進捗状況](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="00072-174">**品質指標のトレーニング**: タグの整合性の評価を次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="00072-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="00072-p120">**良い**: ファイルが一貫してタグ付けします。(緑色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="00072-p120">**Good**: Files are tagged consistently. (Green light displayed)</span></span>
    
- <span data-ttu-id="00072-p121">**[中]**: いくつかのファイルは一貫性がないタグがあります。(黄色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="00072-p121">**Medium**: Some files may be tagged inconsistently. (Yellow light displayed)</span></span>
    
- <span data-ttu-id="00072-p122">**警告**: 多くのファイルは一貫性がないタグ付けがあります。(赤色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="00072-p122">**Warning**: Many files may be tagged inconsistently. (Red light displayed)</span></span>
    
 <span data-ttu-id="00072-p123">**トレーニングの進行状況のグラフ**: F メジャーの値と比較すると関連性の高いトレーニングのサイクル数の後の関連性の高いトレーニングの安定性の程度を示しています。グラフ、信頼区間限定で、左から右に移動のため、F の測定、高度な電子的証拠開示の安定性の決定に関連する私たちと結果の関連性の高いトレーニングは、最適化されています。</span><span class="sxs-lookup"><span data-stu-id="00072-p123">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value. As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00072-p124">関連性は、リコールが有効桁数と 2 倍の重量を受け取る、F メジャーのメトリックは、f2 キーを使用します。持つ場合の高機能 (25% 以上) の関連性は F1 (1:1 の比率)。**関連性の設定**で F メジャーの比率を構成することができます\>**高度な設定**です。</span><span class="sxs-lookup"><span data-stu-id="00072-p124">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision. For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio). The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="00072-186">バッチ計算結果</span><span class="sxs-lookup"><span data-stu-id="00072-186">Batch calculation results</span></span>

<span data-ttu-id="00072-187">**バッチ計算の結果**ペインには、次のようの関連性の評価が受けたされたファイルの数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00072-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="00072-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="00072-188">**Success**</span></span>
    
- <span data-ttu-id="00072-189">**空**: テキスト、たとえば、だけのスペースとタブが含まれていません</span><span class="sxs-lookup"><span data-stu-id="00072-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="00072-190">**失敗**: 必要以上のサイズのためか、読み取ることができませんでした</span><span class="sxs-lookup"><span data-stu-id="00072-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="00072-191">**無視**: 過剰なサイズの関係</span><span class="sxs-lookup"><span data-stu-id="00072-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="00072-192">**Nebulous**: 意味のないテキストまたは問題に関連する機能はありませんが含まれています</span><span class="sxs-lookup"><span data-stu-id="00072-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="00072-193">空、失敗、無視、または Nebulous が表示されます、関連性スコアが-1 の。</span><span class="sxs-lookup"><span data-stu-id="00072-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="00072-194">トレーニングの統計情報</span><span class="sxs-lookup"><span data-stu-id="00072-194">Training statistics</span></span>

<span data-ttu-id="00072-195">**トレーニングの統計情報**] ウィンドウには、統計情報と高度な電子的証拠開示の関連性のトレーニングの結果に基づくグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="00072-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![関連性トラックのトレーニング統計情報](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="00072-197">以下このビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="00072-197">This view shows the following:</span></span>
  
- <span data-ttu-id="00072-p125">**レビュー リコール率**: 線形があるとレビューのスコアを関連性に基づいて結果を比較します。取り消し確認セットのサイズを指定したと推定されます。</span><span class="sxs-lookup"><span data-stu-id="00072-p125">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review. Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="00072-200">**パラメーター**: 累積的な場合は、全体のファイルの作成との関係で設定の確認に関連する統計情報を計算します。</span><span class="sxs-lookup"><span data-stu-id="00072-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="00072-201">**確認**: このカットオフ値に基づいて、ファイルの割合を確認します。</span><span class="sxs-lookup"><span data-stu-id="00072-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="00072-202">**取り消し**: レビューのセットのファイルの関連性の割合です。</span><span class="sxs-lookup"><span data-stu-id="00072-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="00072-p126">**関連性のスコアを使用した配分**: カットオフ スコアの下の左側に、濃いグレーで表示内のファイルです。ツール ヒントは、ファイルの合計数を基準に設定確認ファイル内の関連性スコアと関連ファイルの割合を表示します。</span><span class="sxs-lookup"><span data-stu-id="00072-p126">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="00072-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="00072-205">See also</span></span>

[<span data-ttu-id="00072-206">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="00072-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="00072-207">関連性の評価を理解します。</span><span class="sxs-lookup"><span data-stu-id="00072-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="00072-208">実行して、評価を確認します。</span><span class="sxs-lookup"><span data-stu-id="00072-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="00072-209">関連性の高いトレーニングを実行します。</span><span class="sxs-lookup"><span data-stu-id="00072-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="00072-210">結果に基づいて決定を行う</span><span class="sxs-lookup"><span data-stu-id="00072-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="00072-211">テストの関連性の分析</span><span class="sxs-lookup"><span data-stu-id="00072-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

