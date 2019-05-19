---
title: Office 365 の詳細な電子情報開示でのテスト関連の分析
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: 'Office 365 Advanced eDiscovery でバッチ計算の後に [テスト] タブを使用して、全体的な処理の品質をテスト、比較、検証する方法について説明します。  '
ms.openlocfilehash: 984a7b3f8088604aca235a1caf60bb67b5471499
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158309"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="f26df-103">Office 365 の詳細な電子情報開示でのテスト関連の分析</span><span class="sxs-lookup"><span data-stu-id="f26df-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="f26df-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="f26df-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f26df-106">上級電子情報開示の [テスト] タブを使用すると、処理の全体的な品質をテスト、比較、および検証できます。</span><span class="sxs-lookup"><span data-stu-id="f26df-106">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="f26df-107">これらのテストは、バッチ計算の後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-107">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="f26df-108">コレクション内のファイルにタグ付けすることで、エキスパートは各タグ付きファイルが実際にケースに関連しているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f26df-108">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="f26df-109">1つまたは複数の問題があるシナリオでは、通常、テストは問題ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-109">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="f26df-110">結果は各テストの後に表示でき、指定したサンプルテストファイルを使用してテスト結果をやり直すことができます。</span><span class="sxs-lookup"><span data-stu-id="f26df-110">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="f26df-111">Rest のテスト</span><span class="sxs-lookup"><span data-stu-id="f26df-111">Testing the rest</span></span>

<span data-ttu-id="f26df-112">「Rest のテスト」テストは、最終の高度な電子情報開示の結果に基づいて特定の関連性のカットオフスコアの上にあるファイルのみを確認するためのカリングの決定を検証するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-112">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="f26df-113">専門家は、選択されたカットオフスコアの下にあるファイルのサンプルをレビューして、そのセット内の関連ファイルの数を評価します。</span><span class="sxs-lookup"><span data-stu-id="f26df-113">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="f26df-114">このテストでは、評価セットとその他の母集団をテストするための統計と比較が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-114">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="f26df-115">レビューセットの結果は、学習中に関連性によって計算されたものです。</span><span class="sxs-lookup"><span data-stu-id="f26df-115">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="f26df-116">結果には、次のような設定と入力パラメーターに基づいた計算が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f26df-116">The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="f26df-117">サンプル内のファイル数と関連ファイルを識別した統計をテストします。</span><span class="sxs-lookup"><span data-stu-id="f26df-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="f26df-118">校閲セットの母集団パラメーターと残りの部分の表形式の比較。たとえば、ファイルの数、関連ファイルの推定数、高い多様性、および追加の関連ファイルを検索する平均コストなどです。</span><span class="sxs-lookup"><span data-stu-id="f26df-118">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file.</span></span> <span data-ttu-id="f26df-119">コストパラメーターの設定は、管理者が設定できます。</span><span class="sxs-lookup"><span data-stu-id="f26df-119">Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="f26df-120">[**関連性\>テスト**] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="f26df-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="f26df-121">[**テスト**] タブで、[**新しいテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26df-121">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="f26df-122">次の例に示すように、[**テストの作成**] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-122">The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![関連性テストの残りの結果](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="f26df-124">[**テスト名**] と [**説明**] に、名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="f26df-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="f26df-125">[**テストの種類**] ボックスの一覧で、[ **Rest のテスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f26df-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="f26df-126">[**案件/カテゴリ**] ボックスの一覧で、問題の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f26df-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="f26df-127">[ **Load** ] の一覧で、[load] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f26df-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="f26df-128">**読み取り%** では、既定値をそのまま使用するか、カットオフの関連性スコアの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f26df-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="f26df-129">[**設定サイズ**] で、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="f26df-129">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="f26df-130">復元アイコンは既定値を復元することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f26df-130">Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="f26df-131">[**タグ付けの開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26df-131">Click **Start tagging**.</span></span> <span data-ttu-id="f26df-132">テストサンプルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-132">A test sample is generated.</span></span>
    
10. <span data-ttu-id="f26df-133">[ \*\* \>関連性タグ**] タブで各ファイルを確認し、タグを付けます。完了したら、[**計算\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26df-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="f26df-134">[テスト] タブで [結果の**表示**] をクリックすると、テスト結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-134">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="f26df-135">次の図に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f26df-135">An example is shown in the following figure.</span></span> 
    
    ![残りの結果をテストする](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="f26df-137">上記の図では、表の [**サンプルパラメータ**] セクションに、エキスパートによってタグ付けされたファイルの数と、そのサンプルで見つかった関連ファイルの数についての詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f26df-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="f26df-138">表の [**母集団パラメータ**] セクションにはテストの結果が含まれています。これには、選択したカットオフの下にスコアが付けられたファイルのレビューセット、および選択したカットオフの上にスコアが付いたファイルの "Rest" 作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f26df-138">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="f26df-139">母集団ごとに、次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-139">For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="f26df-140">読み取り% で示されたファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f26df-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="f26df-141">ファイルの合計数</span><span class="sxs-lookup"><span data-stu-id="f26df-141">The total number of files</span></span> 
    
- <span data-ttu-id="f26df-142">関連ファイルの推定数</span><span class="sxs-lookup"><span data-stu-id="f26df-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="f26df-143">予想される豊富な</span><span class="sxs-lookup"><span data-stu-id="f26df-143">The estimated richness</span></span> 
    
- <span data-ttu-id="f26df-144">別の関連ファイルを検索するための平均レビューコスト</span><span class="sxs-lookup"><span data-stu-id="f26df-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="f26df-145">スライスのテスト</span><span class="sxs-lookup"><span data-stu-id="f26df-145">Testing the slice</span></span>

<span data-ttu-id="f26df-146">"スライスをテストする" テストは、"Rest をテストする" テストに似たテストを実行しますが、関連性読み取り% で指定されたファイルセットのセグメントに対して行います。</span><span class="sxs-lookup"><span data-stu-id="f26df-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="f26df-147">[**関連性\>テスト**] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="f26df-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="f26df-148">[**テスト**] タブで、[**新しいテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26df-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="f26df-149">[**テストの作成**] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-149">The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="f26df-150">[**テストの名前**と**説明**] で、情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f26df-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="f26df-151">[**テストの種類**] ボックスの一覧で、[**スライスのテスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f26df-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="f26df-152">[**問題**] リストで、問題の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f26df-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="f26df-153">[ **Load** ] の一覧で、[load] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f26df-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="f26df-154">[**の読み取り率**] で、既定の [低] と [高] の範囲の値を使用するか、[カットオフの関連性スコア] の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f26df-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="f26df-155">[**設定サイズ**] で値を選択するか、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="f26df-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="f26df-156">復元アイコンは既定値を復元します。</span><span class="sxs-lookup"><span data-stu-id="f26df-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="f26df-157">[**タグ付けの開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26df-157">Click **Start tagging**.</span></span> <span data-ttu-id="f26df-158">テストサンプルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-158">A test sample is generated.</span></span>
    
10. <span data-ttu-id="f26df-159">[ \*\* \>関連性タグ**] タブで各ファイルを確認し、タグを付けます。完了したら、[**計算\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26df-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="f26df-160">[テスト] タブで [結果の**表示**] をクリックすると、テスト結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f26df-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="f26df-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="f26df-161">See also</span></span>

[<span data-ttu-id="f26df-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f26df-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f26df-163">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="f26df-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f26df-164">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="f26df-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f26df-165">タグ付けと関連性トレーニング</span><span class="sxs-lookup"><span data-stu-id="f26df-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f26df-166">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="f26df-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f26df-167">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="f26df-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

