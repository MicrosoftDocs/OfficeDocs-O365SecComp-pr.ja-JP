---
title: Office 365 Advanced eDiscovery で関係性分析をテストする
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: 'テスト、比較、および処理の全体的な品質を検証する電子的証拠開示の Office 365 の詳細設定でバッチ計算後、[テスト] タブを使用する方法について説明します。  '
ms.openlocfilehash: 782859fe3b6bb3d00945c477928131cd1154446d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532168"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="9c327-103">Office 365 Advanced eDiscovery で関係性分析をテストする</span><span class="sxs-lookup"><span data-stu-id="9c327-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="9c327-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="9c327-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="9c327-p102">高度な電子的証拠開示では、[テスト] タブを使用すると、テスト、比較、および処理の全体的な品質を検証できます。バッチ計算後は、これらのテストが実行されます。上級者には、コレクション内のファイルにタグ付けで、各タグ付きファイルが実際には、大文字と小文字に関連するかどうかに関する最終的な判断が。</span><span class="sxs-lookup"><span data-stu-id="9c327-p102">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing. These tests are performed after Batch calculation. By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="9c327-p103">単一および複数の問題のシナリオで、通常案件ごとにテストが実行されます。各テストでは、後に結果を表示でき、テストの結果が指定したサンプル テスト ファイルを作成し直すことです。</span><span class="sxs-lookup"><span data-stu-id="9c327-p103">In single and multiple-issue scenarios, tests are typically performed per issue. Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="9c327-111">残りの部分をテストします。</span><span class="sxs-lookup"><span data-stu-id="9c327-111">Testing the rest</span></span>

<span data-ttu-id="9c327-p104">」、残りのテスト」のテストは、たとえばカリングの決定を検証するために、最後の高度な電子的証拠開示の結果に基づいて特定の関連性の高いカットオフ スコアの上のファイルのみを確認するために使用されます。上級者は、そのセット内の関連するファイルの数を評価するために選択したカットオフ スコアの下にあるファイルのサンプルを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c327-p104">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results. The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="9c327-p105">このテストは、他の人口統計情報と比較、レビューとテストを提供します。レビュー一連の結果はトレーニング中に関連性を計算します。結果など、計算、に基づいて設定され、入力パラメーターは、のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9c327-p105">This test provides statistics and a comparison between the Review set and the Test the Rest population. The results of the review set are those calculated by Relevance during Training. The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="9c327-117">サンプルと特定の関連するファイルのファイルの数のサンプルの統計情報をテストします。</span><span class="sxs-lookup"><span data-stu-id="9c327-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="9c327-p106">レビュー セットおよびその他のファイルの数など、カタログの作成パラメーターの比較を表形式の推定数の関連ファイル、推定の豊富な機能、およびその他の関連するファイルの検索の平均コストです。コスト パラメーターの設定は、管理者によって設定できます。</span><span class="sxs-lookup"><span data-stu-id="9c327-p106">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file. Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="9c327-120">開く、**関連\>テスト**タブします。</span><span class="sxs-lookup"><span data-stu-id="9c327-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="9c327-p107">**テスト**] タブで [**新規のテスト**] をクリックします。次の例のように、**テストの作成**] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c327-p107">In the **Test** tab, click **New test**. The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![関連性テストの残りの結果](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="9c327-124">**テストの名前**と**説明**] で、名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c327-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="9c327-125">**テストの種類**] ボックスの一覧で、**テストの残りの部分**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c327-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="9c327-126">**の問題/カテゴリ**一覧で、発行物の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c327-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="9c327-127">**読み込む**] ボックスの一覧では、負荷を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c327-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="9c327-128">**% の読み取り**、既定値を受け入れるか、カットオフの関連性スコアの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c327-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="9c327-p108">で**サイズを設定**既定値を受け入れるか。復元アイコンがデフォルト値を復元するに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9c327-p108">In **Set size**, or accept the default value. Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="9c327-p109">**タグ付けを開始**] をクリックします。テストのサンプルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9c327-p109">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="9c327-133">タグ内のファイルのそれぞれを確認し、**関連\>タグ**] タブで、[**計算**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c327-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="9c327-p110">テスト] タブで、テスト結果を表示する**結果の表示**をクリックできます。例は次の図に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c327-p110">In the Test tab, you can click **View results** to see the test results. An example is shown in the following figure.</span></span> 
    
    ![残りの結果をテストする](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="9c327-137">上の図では、テーブルの**パラメーターのサンプル**」には、上級者にタグ付けされたサンプル内のファイルの数とそのサンプル内の関連するファイルの数に関する詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c327-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="9c327-p111">テーブルの**カタログ作成のパラメーター** ] セクションには、スコアが選択したカットオフ値の下のファイルのレビュー セットのカタログ作成など、選択したカットオフ値の上のスコアを持つファイルの「の残りの部分」カタログの作成、テストの結果が含まれています。各カタログの作成については、次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c327-p111">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff. For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="9c327-140">読み取り % - 指定されたカットオフを持つファイルが含まれています</span><span class="sxs-lookup"><span data-stu-id="9c327-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="9c327-141">ファイルの合計数</span><span class="sxs-lookup"><span data-stu-id="9c327-141">The total number of files</span></span> 
    
- <span data-ttu-id="9c327-142">関連ファイル数の推定値</span><span class="sxs-lookup"><span data-stu-id="9c327-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="9c327-143">推定の豊富な機能</span><span class="sxs-lookup"><span data-stu-id="9c327-143">The estimated richness</span></span> 
    
- <span data-ttu-id="9c327-144">別の関連するファイルの検索のレビューの平均コスト</span><span class="sxs-lookup"><span data-stu-id="9c327-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="9c327-145">スライスのテスト</span><span class="sxs-lookup"><span data-stu-id="9c327-145">Testing the slice</span></span>

<span data-ttu-id="9c327-146">「テストのスライス」テスト「テストの残りの部分」のようなテストを実行するテスト、ですが、ファイルのセグメントには、関連性の読み取りの % で指定した設定です。</span><span class="sxs-lookup"><span data-stu-id="9c327-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="9c327-147">開く、**関連\>テスト**タブします。</span><span class="sxs-lookup"><span data-stu-id="9c327-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="9c327-p112">**テスト**] タブで [**新規のテスト**] をクリックします。**テストの作成**] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c327-p112">In the **Test** tab, click **New test**. The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="9c327-150">**テストの名前**と**説明**] では、情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c327-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="9c327-151">**テストの種類**] ボックスの一覧では、**テスト スライス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c327-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="9c327-152">**懸案事項**の一覧で、発行物の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c327-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="9c327-153">**読み込む**] ボックスの一覧では、負荷を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c327-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="9c327-154">**% 読み取り**、カットオフの関連性スコアの値を選択、既定値および下限値の範囲の値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9c327-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="9c327-155">**サイズを設定**すると、値を選択するか、既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9c327-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="9c327-156">復元アイコンは、既定値に復元されます。</span><span class="sxs-lookup"><span data-stu-id="9c327-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="9c327-p113">**タグ付けを開始**] をクリックします。テストのサンプルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9c327-p113">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="9c327-159">タグ内のファイルのそれぞれを確認し、**関連\>タグ**] タブで、[**計算**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c327-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="9c327-160">テスト] タブで、テスト結果を表示する**結果の表示**をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="9c327-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="9c327-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c327-161">See also</span></span>

[<span data-ttu-id="9c327-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9c327-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="9c327-163">関連性の評価を理解します。</span><span class="sxs-lookup"><span data-stu-id="9c327-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9c327-164">タグ付けおよび評価</span><span class="sxs-lookup"><span data-stu-id="9c327-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9c327-165">タグ付けと関連性の高いトレーニング</span><span class="sxs-lookup"><span data-stu-id="9c327-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9c327-166">追跡の関連性の分析</span><span class="sxs-lookup"><span data-stu-id="9c327-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9c327-167">結果に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="9c327-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

