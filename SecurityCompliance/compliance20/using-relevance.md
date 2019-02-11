---
title: 関連モジュールを使用して、高度な電子的証拠開示 (プレビュー) でデータを分析するには
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 56e83a1f8a951fd6e14172122a5e86447c6f2ccf
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695173"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery-preview"></a><span data-ttu-id="658c6-102">関連モジュールを使用して、高度な電子的証拠開示 (プレビュー) でデータを分析するには</span><span class="sxs-lookup"><span data-stu-id="658c6-102">Use the Relevance module to analyze data in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="658c6-p101">高度な電子的証拠開示 (プレビュー)、関連性の高いモジュールには、関連性の高いトレーニングとサポート案件に関連するファイルの確認が含まれています。関連性の高いワークフローが表示され、次のように記載されています。</span><span class="sxs-lookup"><span data-stu-id="658c6-p101">In Advanced eDiscovery (Preview), the Relevance module includes the Relevance training and review of files related to a case. The Relevance workflow is shown and described as follows:</span></span>
  
![関連性のワークフロー](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="658c6-106">**サイクル**します。</span><span class="sxs-lookup"><span data-stu-id="658c6-106">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="658c6-107">**評価**: ファイルのランダムなサンプルに基づく事前の評価を有効にし、予測のコーディング プロセスのパフォーマンスを決定する決定を適用するのにはこの評価を使用します。</span><span class="sxs-lookup"><span data-stu-id="658c6-107">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="658c6-108">**トラック**: を計算し、評価プロセスの統計的な有効性を監視しながらの中間結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="658c6-108">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="658c6-109">**トレーニングや管理のサイクル**</span><span class="sxs-lookup"><span data-stu-id="658c6-109">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="658c6-110">**タグ**: 高度な電子的証拠開示 (プレビュー) が上級者の反復的なレビューに基づく各問題を特定し、個々 のファイルのタグ付けの関連性の基準を学習します。</span><span class="sxs-lookup"><span data-stu-id="658c6-110">**Tag**: Advanced eDiscovery (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="658c6-111">**トラック**: を計算し、プロセスの統計的な有効性を監視しながら、関連性の高いトレーニングの中間結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="658c6-111">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="658c6-112">**バッチ計算**: 全体のファイルのコレクションに蓄積し、学習した関連性の条件が適用され、関連性スコアは、各ファイルの生成します。</span><span class="sxs-lookup"><span data-stu-id="658c6-112">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="658c6-113">**決定**: バッチの計算の後全体の場合に適用される分析の結果が表示され、ドキュメントのレビューに関する意思決定を行うために使用するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="658c6-113">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="658c6-114">**テスト**: 高度な電子的証拠開示 (プレビュー) 処理の有効性と妥当性を確認する結果をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="658c6-114">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery (Preview) processing.</span></span>

- <span data-ttu-id="658c6-115">**検索**: 関連性の高いワークフローが完了した後する出力を使用してドキュメントの読み取りの百分位数など、問題のワーキング セット内でクエリを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="658c6-115">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="658c6-116">関連のトレーニングおよび確認のためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="658c6-116">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="658c6-117">以下は、関連性の高いトレーニングおよび確認のためのガイドラインの概要です。</span><span class="sxs-lookup"><span data-stu-id="658c6-117">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="658c6-p102">**間違いや不統一**: トレーニング中にエラーをタグ付けを行った場合は、それらを修正する前のサンプルのファイルに戻ります。修正するのにはエラーが多すぎる、またはサポート案件または問題の新しい視点がある、管理者が関連性の基準を再定義する必要があり、関連性の高いトレーニングを再開します。</span><span class="sxs-lookup"><span data-stu-id="658c6-p102">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them. If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="658c6-120">**名札管理とトレーニング**します。</span><span class="sxs-lookup"><span data-stu-id="658c6-120">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="658c6-p103">ファイルは、コンテンツのみに基づくタグ付けする必要があります。保管担当者、日付、またはファイルのパスなどのメタデータを考慮しません。</span><span class="sxs-lookup"><span data-stu-id="658c6-p103">Files should be tagged based on content only. Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="658c6-123">ときに考慮日付、テキストの範囲指示ファイルへのタグ付け。</span><span class="sxs-lookup"><span data-stu-id="658c6-123">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="658c6-124">ファイルをタグ付けするときに埋め込まれた画像を考慮しません。</span><span class="sxs-lookup"><span data-stu-id="658c6-124">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="658c6-p104">無視して関連性で、テキスト ビューに表示されているファイルの内容に関連性を適用するテキストが削除されます。場合は関連性の高いトレーニング開始されて既に後無視するテキストの値に定義された、無視された新しいテキストが定義されているポイントから作成したサンプル ファイルに適用されます。テキストを無視する機能があるため注意が必要、そのファイルの分析のパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="658c6-p104">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance. If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined. The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="658c6-p105">必要な場合のみ**へのタグ付けをスキップする**オプションを使用します。高度な電子的証拠開示 (プレビュー) はトレーニング ベースにスキップされたファイルです。評価、ファイルが該当するかどうかを確認することは困難である場合お勧めタグに Relevant (R) としてか関連 (NR)**スキップ**を選択するのではなく可能な限りです。高度な電子的証拠開示 (プレビュー) には、トレーニングが評価されると、これらの種類のファイルが処理された方法も、確認できます。</span><span class="sxs-lookup"><span data-stu-id="658c6-p105">Use the **Skip tagging** option only when necessary. Advanced eDiscovery (Preview) does not train based on skipped files. In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**. When Advanced eDiscovery (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="658c6-132">抽出したテキストの量が非常に小さいにもファイルは、「スキップ」、可能な場合ではなく R と NR としてトレーニングにタグ付き必要があります。</span><span class="sxs-lookup"><span data-stu-id="658c6-132">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="658c6-133">タグを付けることができますに影響を与える分類子である限り、ファイルを読み取ることが R と NR としてタグ付けすることができます。</span><span class="sxs-lookup"><span data-stu-id="658c6-133">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="658c6-134">[**タグ**] タブで表示されているサンプル ファイルの一覧でファイルのシーケンス番号は、ファイルの元の表示順序を取得するユーザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="658c6-134">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="658c6-p106">任意のサンプルに戻るし、評価のタグ付けを変更でき、トレーニングは、ファイルを設定します。変更は、次のサンプルを作成するときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="658c6-p106">You can go back to any sample and change the tagging of the assessment and training set files. The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="658c6-137">スキャンした Excel のファイルを PDF 形式で必要がありますを同等に扱うネイティブの Excel ファイルとしてファイルをタグ付けするとします。</span><span class="sxs-lookup"><span data-stu-id="658c6-137">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="658c6-p107">判断に迷う場合、ファイルのタグ付けの関連性について、専門家を参照してください。関連のトレーニング中に不正なタグを付けるプロセスの後半で時間のロスにつながることができ、結果全体の品質に悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="658c6-p107">When in doubt regarding the Relevance tagging of a file, consult an expert. Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="658c6-140">定義されているキーワードへのタグ付けしているときに関連ファイルを特定のユーザーのために色のキーワードのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="658c6-140">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="658c6-p108">**バッチ計算**: R/NR エキスパートが表示されますスコアが 0 または 100 のいずれかのようにタグ付けされたファイルです。これは、バッチ計算の前に行われたタグに適用されます。上級者は、バッチ計算後のアイドル状態に問題を切り替えられるし、続き、この問題をタグ付けは 100 と 0 ですが、元のスコアではなくも新たにタグ付けされたスコアはできません。</span><span class="sxs-lookup"><span data-stu-id="658c6-p108">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100. This applies to tagging made before Batch calculation. If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="658c6-144">**問題およびサンプリング モード**: 問題通常オフになっているそれらの作業が完了したとき (関連性の高いトレーニングを安定させるし、バッチ計算が実行された)、問題がキャンセルされた場合、または問題の別のユーザーを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="658c6-144">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="658c6-145">関連性の高いトレーニングの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="658c6-145">Steps in Relevance training</span></span>

<span data-ttu-id="658c6-p109">**の関連性\>トラック**] タブの [高度な電子的証拠開示に関する推奨事項する方法についての処理は、次の次の手順に進みます。関連性の高いトレーニング プロセスの次の手順をお勧めすると影響については後述します。</span><span class="sxs-lookup"><span data-stu-id="658c6-p109">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps. The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="658c6-148">タグ付けまたはタグ付けを続行する: ファイルのファイルのレビューとの関連性は、それぞれの専門家によって実行されるタグ付けし、サンプル内で発行します。</span><span class="sxs-lookup"><span data-stu-id="658c6-148">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="658c6-149">意味: 既存のサンプルは、タグを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="658c6-149">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="658c6-150">評価/評価を継続: ケース問題の関連性の事前検証、現在のケースのインポート ファイルの作成との関連性の予備的なビューを有効にします。</span><span class="sxs-lookup"><span data-stu-id="658c6-150">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="658c6-151">意味: 複数の評価は、必須または推奨します。</span><span class="sxs-lookup"><span data-stu-id="658c6-151">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="658c6-152">トレーニング/トレーニングを続ける: のどの詳細設定の中にファイルへのタグ付けは、エキスパートから学習する電子的証拠開示プロセスをサンプリングし、各ケースのコンテキスト内で各問題に関連する関連性の基準を特定する機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="658c6-152">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="658c6-153">影響: 問題が必要なトレーニングです。次のサンプルを作成してタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="658c6-153">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="658c6-p110">バッチ計算: 関連性のプロセスの詳細に電子的証拠開示トレーニングの段階で得られる知識は、全体のファイルの作成に適用されます。関連のファイル グループ内のすべてのファイルは関連性の評価し、関連性スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="658c6-p110">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population. All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="658c6-156">影響: 問題が安定化、およびバッチの計算を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="658c6-156">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="658c6-157">キャッチアップ: 関連性は、専門家が確認し、タグのロールを読み込むシナリオ中に、追加のファイルのロードから選択したファイルのサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="658c6-157">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="658c6-158">意味: は、新しい負荷を追加すると、キャッチアップする作業を続行する必要が。</span><span class="sxs-lookup"><span data-stu-id="658c6-158">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="658c6-159">矛盾をタグ付け: プロセスを識別、高度な電子的証拠開示のアルゴリズムを使用して分析に悪影響を与える可能性があるプロセスにタグを付けるファイル内の矛盾します。</span><span class="sxs-lookup"><span data-stu-id="658c6-159">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="658c6-160">意味: は、次のサンプルにはファイルが含まれてタグが付けられている前のサンプルと、タグ付けをやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="658c6-160">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="658c6-161">分類子を更新する: タグ付けまたはシード処理の変更を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="658c6-161">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="658c6-162">意味: タグ付けして、シード処理の変更を適用できますせず、手動で別の関連性のサンプルを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="658c6-162">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="658c6-163">保留中: の関連性の高い学習のプロセスが完了しました。</span><span class="sxs-lookup"><span data-stu-id="658c6-163">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="658c6-164">意味: 関連性の高いトレーニングは必要ありませんこの時点で。</span><span class="sxs-lookup"><span data-stu-id="658c6-164">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="658c6-165">高度な電子的証拠開示プロセスを案内するのさまざまな段階で次の手順を推奨する、こともできますタブやページ間を移動して、個々 の場合、問題に関連する可能性のある状況を解決するを選択するか、ドキュメントの校閲プロセスです。</span><span class="sxs-lookup"><span data-stu-id="658c6-165">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="658c6-p111">承諾または高度な電子的証拠開示の選択肢を処理する次の手順をオーバーライドすることは。以外の推奨される次の手順のステップを実行] をクリックする場合はダイアログ ボックスで展開されている問題の表示に記載されている**次のステップ**を、次の手順の横にある [**変更**] ボタンをクリックして、別の次の手順オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="658c6-p111">It is possible to accept or override Advanced eDiscovery Next step processing choices. If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="658c6-168">ロックを解除した後プロセスの時点で使用するためサポートされていないいくつかのオプションが無効なままです。</span><span class="sxs-lookup"><span data-stu-id="658c6-168">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="658c6-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="658c6-169">More information</span></span>

[<span data-ttu-id="658c6-170">関連性の評価を理解します。</span><span class="sxs-lookup"><span data-stu-id="658c6-170">Understanding Assessment in Relevance</span></span>](../assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="658c6-171">タグ付けおよび評価</span><span class="sxs-lookup"><span data-stu-id="658c6-171">Tagging and Assessment</span></span>](../tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="658c6-172">タグ付けと関連性の高いトレーニング</span><span class="sxs-lookup"><span data-stu-id="658c6-172">Tagging and Relevance training</span></span>](../tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="658c6-173">追跡の関連性の分析</span><span class="sxs-lookup"><span data-stu-id="658c6-173">Tracking Relevance analysis</span></span>](../track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="658c6-174">結果に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="658c6-174">Deciding based on the results</span></span>](../decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="658c6-175">テストの関連性の分析</span><span class="sxs-lookup"><span data-stu-id="658c6-175">Testing Relevance analysis</span></span>](../test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="658c6-176">ワーキング セット内でクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="658c6-176">Query within working set</span></span>](working-set-search.md)
