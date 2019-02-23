---
title: Office 365 Advanced eDiscovery でのタグ付けと評価
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: '評価トレーニングを実行する手順を確認します。これには、ファイルのタグ付け、Office 365 Advanced eDiscovery の評価結果の確認が含まれます。 '
ms.openlocfilehash: 02dae23b6489b40243272beea1d79e871ca6a911
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217937"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a><span data-ttu-id="74855-103">Office 365 Advanced eDiscovery でのタグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="74855-103">Tagging and Assessment in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="74855-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="74855-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="74855-106">このセクションでは、Advanced eDiscovery 関連性評価モジュールの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="74855-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="74855-107">評価トレーニングと分析の実行</span><span class="sxs-lookup"><span data-stu-id="74855-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="74855-108">[**関連\>トラック**] タブで、 \*\*\*\* [case 評価を開始する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74855-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="74855-109">この手順では、例として、500ファイルの評価セットのサンプルを作成し、[**タグ**] タブを表示します。これには、タグパネル、表示されるファイルのコンテンツ、およびその他のタグ付けのオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="74855-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![評価ための [関連性タグ] タブ](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="74855-111">サンプル内の各ファイルを確認し、各ケースの問題についてファイルの関連性を調べて、関連性 (R) を使用してファイルをタグ付けし、[タグ**付けパネル**] ウィンドウで関連 (NR) および Skip ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="74855-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="74855-p102">評価には、500のタグ付きファイルが必要です。ファイルが "スキップ" された場合は、タグに追加のファイルを受信します。</span><span class="sxs-lookup"><span data-stu-id="74855-p102">Assessment requires 500 tagged files. If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="74855-114">サンプル内のすべてのファイルにタグを付けた後、[**計算**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74855-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="74855-p103">次に示すように、評価の現在の誤差範囲と多様性が計算され、[**関連性の追跡**] タブに表示され、問題ごとの詳細が展開されます。このダイアログの詳細については、後の「評価結果をレビューする」セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="74855-p103">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below. More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![関連性トラック - 評価](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="74855-p104">既定では、問題の評価進行状況インジケーターが完了したときに、評価サンプルが確認され、十分な関連ファイルがタグ付けされたことを示す、既定の次の手順に進むことをお勧めします。> 場合は、[**トラック**] タブの結果を表示して、エラーの余白と次の手順を制御する場合は、[**次のステップ**に**変更**する] をクリックし、[**評価を続行**する] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74855-p104">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged. > Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="74855-p105">[**評価**] チェックボックスの右にある [**変更**] をクリックして、問題ごとの評価パラメーターを表示および指定します。次の例に示すように、各問題の**評価レベル**のダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74855-p105">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue. An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![評価レベルのケースの問題](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="74855-123">次の問題のパラメーターが計算され、[**評価レベル**] ダイアログボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="74855-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="74855-p106">**呼び戻し推定のターゲット誤差**範囲: この値に基づいて、確認に必要な追加ファイルの推定数が計算されます。呼び戻しで使用される余白は 75% より大きく、信頼度は 95% です。</span><span class="sxs-lookup"><span data-stu-id="74855-p106">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated. The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="74855-126">**必要な追加評価ファイル**: 現在の誤差範囲の要件が満たされていない場合に必要なファイルの数を示します。</span><span class="sxs-lookup"><span data-stu-id="74855-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="74855-127">現在の誤差範囲を調整し、さまざまな誤差の余白の効果を確認する (1 つの問題):</span><span class="sxs-lookup"><span data-stu-id="74855-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="74855-128">**[問題の選択**] リストで、問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="74855-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="74855-129">[**呼び戻しの推定の対象誤差**範囲] に、新しい値を入力します。</span><span class="sxs-lookup"><span data-stu-id="74855-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="74855-130">[**値の更新**] をクリックして、調整の影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="74855-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="74855-131">[**評価レベル**] ダイアログボックスの [**詳細設定**] をクリックして、次の追加パラメーターと詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="74855-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![[評価レベルのケースの問題] 詳細ビュー](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="74855-133">\*\*\*\* 現在の評価結果に応じて予想される豊富な見積もり:</span><span class="sxs-lookup"><span data-stu-id="74855-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="74855-p107">**呼び戻しの推定**値: 既定では、ターゲットの誤差範囲は、75% を超える呼び戻しに適用されます。このパラメーターを変更して、別の範囲の呼び戻し値に対する誤差の余白を制御する場合は、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74855-p107">**For assumed recall**: By default, the target error margin applies to recall above 75%. Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="74855-p108">**信頼**度: 既定では、推奨される精度の誤差の余白は 95% です。このパラメーターを変更する場合は、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74855-p108">**Confidence level**: By default, the recommended error margin for confidence is 95%. Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="74855-138">**必要な豊富な誤差**範囲: 更新された値がある場合は、その他の評価ファイルがすべてレビューされた後に、この誤差の誤差の予想される余白を指定します。</span><span class="sxs-lookup"><span data-stu-id="74855-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="74855-139">**必要な追加評価ファイル**: 更新された値があれば、ターゲットに到達するためにレビューする必要がある追加評価ファイルの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="74855-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="74855-140">**必要な合計評価ファイル**: 更新された値、レビューに必要な評価ファイルの総数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="74855-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="74855-141">**評価に必要な関連ファイルの数**: 更新された値があれば、すべての追加評価ファイルがレビューされた後に、評価全体で予想される関連ファイルの数。</span><span class="sxs-lookup"><span data-stu-id="74855-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="74855-p109">パラメーターが変更された場合は、[**値の再計算**] をクリックします。完了したら、1つの問題が発生した場合は [ **OK** ] をクリックして変更を保存します (または、複数の問題があり、確認または変更して**終了**する場合は、**次**の操作を行います)。</span><span class="sxs-lookup"><span data-stu-id="74855-p109">Click **Recalculate values**, if parameters are changed. When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="74855-144">複数の問題がある場合、次の例に示すように、すべての問題がレビューまたは調整された後に、**評価レベル: 概要**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74855-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![評価レベルの概要](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="74855-146">評価が正常に完了したら、関連トレーニングの次のステージに進みます。</span><span class="sxs-lookup"><span data-stu-id="74855-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="74855-147">評価結果の確認</span><span class="sxs-lookup"><span data-stu-id="74855-147">Reviewing assessment results</span></span>

<span data-ttu-id="74855-148">評価サンプルにタグ付けされた後、評価結果が計算され、[関連トラック] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="74855-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="74855-149">次の結果が、展開されたトラックの表示に表示されます。</span><span class="sxs-lookup"><span data-stu-id="74855-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="74855-150">評価の現在のエラーのマージン (呼び戻し推定)</span><span class="sxs-lookup"><span data-stu-id="74855-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="74855-151">予想豊富</span><span class="sxs-lookup"><span data-stu-id="74855-151">Estimated richness</span></span>
    
- <span data-ttu-id="74855-152">その他の評価ファイルが必要 (レビュー用)</span><span class="sxs-lookup"><span data-stu-id="74855-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="74855-p110">[評価電流誤差] 余白は、Advanced eDiscovery で推奨されるエラーの余白です。「その他の評価ファイルが必要」に表示される番号は、その推奨事項に対応しています。</span><span class="sxs-lookup"><span data-stu-id="74855-p110">The Assessment current error margin is the error margin recommended by Advanced eDiscovery. The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="74855-p111">評価進行状況インジケーターは、現在の誤差範囲に指定された評価の完了レベルを示します。評価が進行している場合、ユーザーは別の評価サンプルにタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="74855-p111">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin. When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="74855-157">評価の進行状況インジケーターで評価が完了と表示された場合、評価サンプルレビューが完了し、十分な関連ファイルがタグ付けされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="74855-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="74855-158">展開されたトラックの表示には、推奨される次のステップ、評価統計、詳細結果へのアクセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74855-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="74855-p112">豊富な機能が非常に少ない場合は、有用な統計情報を生成するために最小限の数の関連ファイルを得るために必要な追加の評価ファイルの数が非常に高くなります。上級電子情報開示については、トレーニングに移行することをお勧めします。評価進行状況インジケーターは影付きになり、統計情報は利用できません。</span><span class="sxs-lookup"><span data-stu-id="74855-p112">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high. Advanced eDiscovery will then recommend moving on to training. The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="74855-p113">統計的に基づく安定化が行われていない場合、精度と信頼度のレベルが低いという結果になります。ただし、検出された関連ファイルの割合を知る必要がない場合は、これらの結果を使用して関連するファイルを見つけることができます。同様に、この状態を使用して、関連性スコアが特定の問題に関連するファイルへのアクセスを促進する、低低性の問題をトレーニングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="74855-p113">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level. However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found. Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="74855-p114">[**関連性\>の追跡**] タブの展開された案件の表示では、次の表示オプションを使用できます。次の手順のように、> は、[**変更**] ボタンをクリックして、**タグ付け**を省略 (問題ごとに) することができます。右に進み、**次の手順**で別の手順を選択します。評価の進行状況インジケーターが完了していない場合は、評価ファイルを追加して、統計の精度を上げるための次の推奨オプションとなります。> 誤差範囲を変更し、その影響を評価するには、[**変更**] をクリックし、[**評価レベル] ダイアログ**で [**取り消しの推定] の対象**となるエラーの余白を変更して、[**値の更新**] をクリックします。また、このダイアログボックスで、[**詳細**設定] をクリックして詳細オプションを表示することもできます。> 追加の評価レベルの統計情報とその影響を表示するには、[**表示**] をクリックします。[詳細結果の表示] ダイアログでは、1つの問題について、少なくとも500のタグ付き評価ファイルがあり、少なくとも18個のファイルが問題に関連してタグ付けされている場合に、統計情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="74855-p114">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**. When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy. > You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**. Also, in this dialog, you can view advanced options, by clicking **Advanced**. > You can view additional assessment level statistics and their impact by clicking **View**. In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="74855-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="74855-171">See also</span></span>

[<span data-ttu-id="74855-172">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="74855-172">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="74855-173">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="74855-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="74855-174">タグ付けと関連性トレーニング</span><span class="sxs-lookup"><span data-stu-id="74855-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="74855-175">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="74855-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="74855-176">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="74855-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="74855-177">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="74855-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

