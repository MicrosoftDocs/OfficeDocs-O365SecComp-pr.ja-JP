---
title: Office 365 Advanced eDiscovery でのタグ付けと評価
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 'ファイルへのタグ付け、電子的証拠開示の Office 365 の詳細に評価結果を確認するなど、評価のトレーニングを実行する手順を確認します。 '
ms.openlocfilehash: 0f67dd4780a29536888231f556c18fe887f230ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532018"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a><span data-ttu-id="fe244-103">Office 365 Advanced eDiscovery でのタグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="fe244-103">Tagging and Assessment in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="fe244-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="fe244-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="fe244-106">このセクションでは、高度な電子的証拠開示の妥当性評価モジュールのプロシージャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fe244-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="fe244-107">トレーニングの評価と分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe244-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="fe244-108">**の関連性\>トラック**] タブで、サポート案件の評価を開始するのには**評価**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe244-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="fe244-109">たとえば 500 個のファイルのサンプル評価セットを作成するためにこの手順では、し、[**タグ**] タブが表示されます、名札管理パネル、表示されているファイルのコンテンツおよびその他のタグ付けのオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe244-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![評価ための [関連性タグ] タブ](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="fe244-111">サンプル内の各ファイルを確認、各ケースの問題では、ファイルの関連性の判断、および、Relevance (R) を使用していないファイルにタグ付け**パネルの名札管理**ウィンドウでボタンの関連 (NR) と省略します。</span><span class="sxs-lookup"><span data-stu-id="fe244-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="fe244-p102">評価には、500 個のタグ付きファイルが必要です。ファイルは、「スキップ」、より多くのファイルにタグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe244-p102">Assessment requires 500 tagged files. If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="fe244-114">サンプル内のすべてのファイルにタグ付けした後、**計算**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe244-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="fe244-p103">現在エラーのマージンを評価し、豊富な機能が計算され、次のように、**関連性の履歴**] タブで、問題ごとの展開の詳細を表示します。このダイアログ ボックスの詳細については、[チェック/コメントの評価結果の後のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="fe244-p103">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below. More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![関連性トラック - 評価](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="fe244-p104">既定では、続行すること、デフォルトの次の手順に問題の評価の進行状況のインジケーターが完了したら、評価サンプルの確認、十分な関連するファイルが追加のことを示すことをお勧めします。> それ以外の場合、結果の**追跡**] タブとコントロールのエラー メッセージと次のステップの余白を表示する場合は、**変更****次の手順**の横にある] をクリックして**続行の評価**を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe244-p104">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged. > Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="fe244-p105">**変更**[**評価**] チェック ボックスの右側に表示し、案件ごとの評価のパラメーターを指定する] をクリックします。次の例のように、各問題の**評価レベル**ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe244-p105">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue. An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![評価レベルのケースの問題](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="fe244-123">問題の次のパラメーターが計算され、**レベルの評価**] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe244-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="fe244-p106">**リコールの対象エラーのマージンの予測**: この値に基づいて、追加のファイルを確認するために必要な数の推定値が計算されます。リコールに使用する余白は、95% の信頼レベルと 75% よりも大きい。</span><span class="sxs-lookup"><span data-stu-id="fe244-p106">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated. The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="fe244-126">**評価の追加ファイルが必要です**: 複数ファイルの数が現在エラー マージンの要件が満たされていない場合に必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="fe244-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="fe244-127">現在のエラーの余白を調整し、(問題) ごとに別のエラーの余白の効果を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe244-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="fe244-128">**問題の選択**] ボックスの一覧で、懸案事項を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe244-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="fe244-129">**リコールの対象エラーのマージンの予測**を、新しい値を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe244-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="fe244-130">調整の影響を確認するのには**値の更新**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe244-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="fe244-131">[**評価レベル**] ダイアログ ボックスで次の追加パラメーターと詳細を表示するには、**詳細設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe244-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![[評価レベルのケースの問題] 詳細ビュー](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="fe244-133">**見積もりの豊かさ**: 現在の評価結果には、豊富な機能を推定</span><span class="sxs-lookup"><span data-stu-id="fe244-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="fe244-p107">**仮定してリコールに**: 75% 以上を取り消すには既定では、対象のエラーの余白が適用されます。このパラメーターを変更し、リコールの値の別の範囲のエラーの余白を制御する場合は、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe244-p107">**For assumed recall**: By default, the target error margin applies to recall above 75%. Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="fe244-p108">**信頼レベル**: 既定では、信頼性の推奨されるエラーの余白は、95% です。このパラメーターを変更する場合は、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe244-p108">**Confidence level**: By default, the recommended error margin for confidence is 95%. Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="fe244-138">**期待される豊富なエラーの余白**: 更新された値を指定するには、これは、予想される余白の豊富な機能、エラーの他の評価のすべてのファイルの内容を確認した後。</span><span class="sxs-lookup"><span data-stu-id="fe244-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="fe244-139">**評価の追加ファイルが必要です**: その他の評価の数のファイルを更新された値を指定するには、ターゲットに到達するために確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe244-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="fe244-140">**ファイルの合計の評価が必要です**: 更新された値を指定するには、レビューに必要なファイルを評価の合計します。</span><span class="sxs-lookup"><span data-stu-id="fe244-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="fe244-141">**評価に関連するファイル数の予測**: その他の評価のすべてのファイルの内容を確認した後の全体の評価に関連するファイルの数、更新された値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe244-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="fe244-p109">パラメーターが変更された場合は、**値を再計算**をするをクリックします。完了したら、1 つの問題がある場合、変更 (または**次**を確認または変更するには複数の問題がある場合にし、**終了**) を保存するのには **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe244-p109">Click **Recalculate values**, if parameters are changed. When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="fe244-144">すべての問題が確認されているか、調整した後、複数の問題がある場合に、**評価レベル: 概要**例を次に示すように、ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe244-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![評価レベルの概要](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="fe244-146">評価の学習には、関連性の高いトレーニングの次の段階に進みます。</span><span class="sxs-lookup"><span data-stu-id="fe244-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="fe244-147">評価結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="fe244-147">Reviewing assessment results</span></span>

<span data-ttu-id="fe244-148">評価サンプルをタグ付けすると後、評価の結果が計算され、関連性の履歴] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe244-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="fe244-149">次の結果が表示されますで展開されているトラックの表示。</span><span class="sxs-lookup"><span data-stu-id="fe244-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="fe244-150">現在のエラー マージン リコールの推定値の評価</span><span class="sxs-lookup"><span data-stu-id="fe244-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="fe244-151">推定の豊富な機能</span><span class="sxs-lookup"><span data-stu-id="fe244-151">Estimated richness</span></span>
    
- <span data-ttu-id="fe244-152">その他の評価に必要なファイル (レビュー)</span><span class="sxs-lookup"><span data-stu-id="fe244-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="fe244-p110">評価現在エラーのマージンは、高度な電子的証拠開示によって推奨されるエラーの余白です。"その他の評価に必要なファイル」に表示される数値は、その推奨事項に対応します。</span><span class="sxs-lookup"><span data-stu-id="fe244-p110">The Assessment current error margin is the error margin recommended by Advanced eDiscovery. The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="fe244-p111">評価の進行状況のインジケーターは、現在のエラーの余白を指定する、評価の完了のレベルを示しています。評価が実行されるとき、ユーザーは別の評価サンプルのタグです。</span><span class="sxs-lookup"><span data-stu-id="fe244-p111">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin. When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="fe244-157">評価の進行状況インジケーターには、全体としての評価が表示されている場合は、評価サンプルの確認が完了したし、十分な関連するファイルが追加されるを意味します。</span><span class="sxs-lookup"><span data-stu-id="fe244-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="fe244-158">展開したトラックの表示は、推奨される次の手順、評価の統計情報、および詳細な結果へのアクセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="fe244-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="fe244-p112">豊富な機能は、非常に低いが、有用な統計情報の生成に関連するファイルの最小数に到達するために必要なその他の評価ファイルの数は非常に高いが。高度な電子的証拠開示は、トレーニングに移動し、お勧めします。評価の進行状況のインジケーターが影付きで表示して、統計情報は利用できません。</span><span class="sxs-lookup"><span data-stu-id="fe244-p112">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high. Advanced eDiscovery will then recommend moving on to training. The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="fe244-p113">に基づいて統計的に安定化がない場合、結果の精度と信頼性のレベルの低いレベルとなります。ただし、これらの結果は、関連のファイルの割合を知っている必要がないときは、関連するファイルを検索する使用できます。同様に、この状態ことができますのトレーニングに使用問題低の豊富な機能との関連性スコアが特定の問題に関連するファイルにアクセスを促進する場所です。</span><span class="sxs-lookup"><span data-stu-id="fe244-p113">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level. However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found. Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="fe244-p114">**の関連性\>トラック**] タブの拡張の問題を表示、次の表示オプションがあります: > 推奨される次のステップ、次のように**次のステップ: タグ付け**(問題) ごとに [**変更**] ボタンをクリックすると、省略可能、右、および**次の手順**で別のステップを選択します。評価の進行状況のインジケーターが完了していない場合の評価は評価のより多くのファイルにタグ付けし、統計情報の精度を向上させる、次の推奨されるオプションになります。> エラーの余白を変更して、[**変更**] をクリックして、**評価のレベル] ダイアログ**で、**リコールの対象エラーのマージンの予測**を変更して、**値の更新**をクリックすると、その影響を評価できます。このダイアログ ボックスで、**詳細設定**] をクリックして詳細オプション] を表示できます。> を表示その他の評価レベルの統計情報とその影響**ビュー**] をクリックします。詳細結果表示されるダイアログ ボックスで、統計情報は、500 以上の評価のタグ付きファイルがあるし、問題の 18 以上のファイルと関連タグが付けられた、問題ごとに使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe244-p114">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**. When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy. > You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**. Also, in this dialog, you can view advanced options, by clicking **Advanced**. > You can view additional assessment level statistics and their impact by clicking **View**. In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fe244-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe244-171">See also</span></span>

[<span data-ttu-id="fe244-172">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fe244-172">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="fe244-173">関連性の評価を理解します。</span><span class="sxs-lookup"><span data-stu-id="fe244-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="fe244-174">タグ付けと関連性の高いトレーニング</span><span class="sxs-lookup"><span data-stu-id="fe244-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="fe244-175">追跡の関連性の分析</span><span class="sxs-lookup"><span data-stu-id="fe244-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="fe244-176">結果に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="fe244-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="fe244-177">テストの関連性の分析</span><span class="sxs-lookup"><span data-stu-id="fe244-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

