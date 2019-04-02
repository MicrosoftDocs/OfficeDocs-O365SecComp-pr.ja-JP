---
title: 適合性モジュールを使用して証拠でデータを分析する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 3aa37a6778947934759eb652a9367559b9ef838b
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030308"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a><span data-ttu-id="488a8-102">適合性モジュールを使用して証拠でデータを分析する</span><span class="sxs-lookup"><span data-stu-id="488a8-102">Use the Relevance module to analyze data in evidence</span></span>

<span data-ttu-id="488a8-103">データ調査 (プレビュー) で、関連性モジュールには、調査に関連するファイルの関連性トレーニングとレビューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="488a8-103">In Data Investigations (Preview), the Relevance module includes the Relevance training and review of files related to an investigation.</span></span> <span data-ttu-id="488a8-104">関連性ワークフローが表示され、次のように説明されています。</span><span class="sxs-lookup"><span data-stu-id="488a8-104">The Relevance workflow is shown and described as follows:</span></span>
  
![関連性のワークフロー](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="488a8-106">**評価と追跡のサイクル**:</span><span class="sxs-lookup"><span data-stu-id="488a8-106">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="488a8-107">**評価**: ファイルのランダムなサンプルに基づく早期評価を有効にし、この評価を使用して、予測コーディングプロセスのパフォーマンスを判断するための決定を適用します。</span><span class="sxs-lookup"><span data-stu-id="488a8-107">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="488a8-108">**Track**: 評価の中間結果を計算して表示し、プロセスの統計的な有効性を監視します。</span><span class="sxs-lookup"><span data-stu-id="488a8-108">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="488a8-109">**トレーニングと追跡のサイクル**</span><span class="sxs-lookup"><span data-stu-id="488a8-109">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="488a8-110">**タグ**: データ調査 (プレビュー) は、専門家による個々のファイルの反復的なレビューとタグ付けに基づいて、各問題に固有の関連性基準を学習します。</span><span class="sxs-lookup"><span data-stu-id="488a8-110">**Tag**: Data Investigations (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="488a8-111">**追跡**: プロセスの統計的な有効性を監視しながら、関連性トレーニングの一時的な結果を計算して表示します。</span><span class="sxs-lookup"><span data-stu-id="488a8-111">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="488a8-112">**バッチ計算**: 累積および学習した関連性の条件がファイルコレクション全体に適用され、各ファイルに対して関連性スコアが生成されます。</span><span class="sxs-lookup"><span data-stu-id="488a8-112">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="488a8-113">**決定**: バッチ計算の後に、ケース全体に適用される分析の結果が表示され、ドキュメントのレビューの決定に使用されるデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="488a8-113">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="488a8-114">**テスト**: 結果をテストして、データ調査 (プレビュー) 処理の有効性と有効性を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="488a8-114">**Test**: Results can be tested to verify the validity and effectiveness of the Data Investigations (Preview) processing.</span></span>

- <span data-ttu-id="488a8-115">**検索**: 関連性ワークフローが完了すると、作業セット内でクエリを実行するときに、ドキュメントの読み取りの百分位などの出力を使用できます。</span><span class="sxs-lookup"><span data-stu-id="488a8-115">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="488a8-116">関連性のトレーニングとレビューに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="488a8-116">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="488a8-117">関連のトレーニングとレビューのガイドラインの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="488a8-117">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="488a8-118">**エラーと不整合**: トレーニング中にタグ付けエラーが発生した場合は、以前のファイルサンプルに戻って修正してください。</span><span class="sxs-lookup"><span data-stu-id="488a8-118">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="488a8-119">修正するエラーが多すぎる場合や、ケースまたは問題の新しいパースペクティブがある場合は、管理者が関連性の条件を再定義して、関連性トレーニングを再開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="488a8-119">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="488a8-120">**タグ付けとトレーニング**:</span><span class="sxs-lookup"><span data-stu-id="488a8-120">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="488a8-121">ファイルは、コンテンツのみに基づいてタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="488a8-121">Files should be tagged based on content only.</span></span> <span data-ttu-id="488a8-122">保管担当者、日付、ファイルパスなどのメタデータは考慮しません。</span><span class="sxs-lookup"><span data-stu-id="488a8-122">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="488a8-123">ファイルにタグ付けするときに、テキストに日付範囲が表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="488a8-123">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="488a8-124">ファイルへのタグ付け時に埋め込まれた画像を考慮しません。</span><span class="sxs-lookup"><span data-stu-id="488a8-124">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="488a8-125">[無視] 関連性に適用されたテキストは、[関連性] のテキストビューに表示されているファイルの内容から削除されます。</span><span class="sxs-lookup"><span data-stu-id="488a8-125">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="488a8-126">関連性トレーニングが既に開始された後に、Ignore text の値が定義されていた場合、新しい無視されたテキストは、定義された時点から作成されたサンプルファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="488a8-126">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="488a8-127">ファイル分析のパフォーマンスが低下する可能性があるため、[テキストを無視する] 機能は慎重に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="488a8-127">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="488a8-128">[**タグをスキップ**する] オプションは必要な場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="488a8-128">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="488a8-129">データ調査 (プレビュー) は、スキップされたファイルに基づいてトレーニングを行いません。</span><span class="sxs-lookup"><span data-stu-id="488a8-129">Data Investigations (Preview) does not train based on skipped files.</span></span> <span data-ttu-id="488a8-130">評価では、ファイルが関連しているかどうかを判断するのが難しい場合は、 **Skip**を選択するのではなく、可能な限り、関連性のある (R) または関連していない (NR) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="488a8-130">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="488a8-131">データ調査 (プレビュー) でトレーニングを評価すると、これらの種類のファイルがどのように処理されたかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="488a8-131">When Data Investigations (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="488a8-132">抽出されたテキストが非常に小さいファイルでも、可能な場合は "Skip" ではなく、R/NR としてのトレーニングでタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="488a8-132">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="488a8-133">タグ付けは、ファイルが読みやすく、R/NR としてタグ付けできる限り、分類子に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="488a8-133">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="488a8-134">[**タグ**] タブの表示されているサンプルファイルの一覧のファイルシーケンス番号を使用すると、ユーザーは、表示されている元のファイルの順序に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="488a8-134">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="488a8-135">すべてのサンプルに戻って、評価およびトレーニングセットファイルのタグ付けを変更できます。</span><span class="sxs-lookup"><span data-stu-id="488a8-135">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="488a8-136">変更は、次のサンプルを作成するときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="488a8-136">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="488a8-137">PDF 形式でスキャンした excel ファイルは、ファイルにタグ付けするときに、ネイティブの excel ファイルと同じように処理されます。</span><span class="sxs-lookup"><span data-stu-id="488a8-137">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="488a8-138">ファイルの関連性のタグ付けに関して疑わしい場合は、専門家に相談してください。</span><span class="sxs-lookup"><span data-stu-id="488a8-138">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="488a8-139">関連性トレーニング中に誤ったタグ付けを行うと、プロセスの後期に時間が失われることがあり、結果全体の品質に悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="488a8-139">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="488a8-140">キーワードリストで定義されたキーワードは、タグ付け中にユーザーが関連ファイルを識別するのに役立つ色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="488a8-140">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="488a8-141">**バッチ計算**: 専門家による R/NR としてタグ付けされたファイルのスコアは0または100のいずれかとなります。</span><span class="sxs-lookup"><span data-stu-id="488a8-141">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="488a8-142">これは、バッチ計算前に行われるタグ付けに適用されます。</span><span class="sxs-lookup"><span data-stu-id="488a8-142">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="488a8-143">上級者が一括計算した後に問題をアイドルに切り替えて、この問題のタグ付けを続行した場合、新しくタグ付けされたスコアは100/0 にならず、元のスコアになります。</span><span class="sxs-lookup"><span data-stu-id="488a8-143">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="488a8-144">**問題とサンプリングモード**: 問題が発生した場合は、その作業が完了し、問題が取り消されたとき、または他のユーザーが問題に対処しているときに、通常はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="488a8-144">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="488a8-145">関連性トレーニングの手順</span><span class="sxs-lookup"><span data-stu-id="488a8-145">Steps in Relevance training</span></span>

<span data-ttu-id="488a8-146">[**関連性\>の追跡**] タブでは、データ調査で、処理を進める方法に関する推奨事項が提供されます。次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="488a8-146">In the **Relevance \> Track** tab, Data investigations provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="488a8-147">関連トレーニングプロセスで以下の各手順を実行する場合は、次に示す影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="488a8-147">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="488a8-148">タグ付け/続行のタグ付け: サンプル内のファイルと問題について、エキスパートによってファイルのレビューと関連性のタグ付けが実行されます。</span><span class="sxs-lookup"><span data-stu-id="488a8-148">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="488a8-149">暗黙: 既存のサンプルは、タグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="488a8-149">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="488a8-150">評価/続行評価: ケース上の問題の関連性と、現在のケースに対してインポートされたファイルの作成の関連性を事前に検証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="488a8-150">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="488a8-151">暗示: より多くの評価が必要または推奨されています。</span><span class="sxs-lookup"><span data-stu-id="488a8-151">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="488a8-152">トレーニング/続行トレーニング: データ調査がファイルサンプルにタグ付けする専門家から情報を取得するプロセス。また、各案件のコンテキスト内で各問題に関連する関連性基準を特定する機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="488a8-152">Training / Continue training: Process during which Data investigations learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="488a8-153">意味: 問題により多くのトレーニングが必要になります。次のサンプルを作成し、タグを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="488a8-153">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="488a8-154">バッチ計算: データ調査で取得した知識をトレーニング段階で取得し、ファイルの作成全体に適用する関連プロセス。</span><span class="sxs-lookup"><span data-stu-id="488a8-154">Batch calculation: Relevance process in which Data investigations takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="488a8-155">関連するファイルグループ内のすべてのファイルに関連性があることが評価され、関連性スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="488a8-155">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="488a8-156">意味: 問題が安定しており、バッチ計算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="488a8-156">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="488a8-157">キャッチアップ: 関連性は、エキスパートが、ローリングロードシナリオで追加のファイルロードから選択されたファイルのサンプルをレビューし、タグ付けするタイミングを示します。</span><span class="sxs-lookup"><span data-stu-id="488a8-157">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="488a8-158">暗黙: 新しい読み込みが追加され、作業を続行するにはキャッチアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="488a8-158">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="488a8-159">タグの不整合: プロセスは、データ調査アルゴリズムを使用して、分析に悪影響を及ぼす可能性のあるファイルのタグ付けプロセスの不整合を識別します。</span><span class="sxs-lookup"><span data-stu-id="488a8-159">Tag inconsistencies: Process identifies, via an Data investigations algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="488a8-160">意味: 次のサンプルには、前のサンプルでタグ付けされたファイルが含まれており、タグ付けをやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="488a8-160">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="488a8-161">Update クラシファイア: ユーザーがタグ付けまたはシード変更を適用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="488a8-161">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="488a8-162">暗黙: 別の関連性サンプルを手動で実行しなくても、タグ付けとシードによる変更を適用できます。</span><span class="sxs-lookup"><span data-stu-id="488a8-162">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="488a8-163">保留中: 関連トレーニングプロセスが完了します。</span><span class="sxs-lookup"><span data-stu-id="488a8-163">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="488a8-164">意味: この時点では、関連性トレーニングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="488a8-164">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="488a8-165">データ調査では、プロセスについて説明していますが、さまざまな段階での次の推奨手順を使用すると、タブとページ間を移動したり、個別のケース、問題、またはの状況に関係する可能性がある状況に対処することができます。ドキュメントレビュープロセス。</span><span class="sxs-lookup"><span data-stu-id="488a8-165">Although Data investigations guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="488a8-166">データ調査の次のステップ処理の選択を承諾または上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="488a8-166">It is possible to accept or override Data investigations Next step processing choices.</span></span> <span data-ttu-id="488a8-167">次の推奨手順以外の手順を実行する場合は、ダイアログボックスの展開された問題の表示で**次の手順**をクリックし、次の手順の横にある [**変更**] ボタンをクリックして、別の [次の手順] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="488a8-167">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="488a8-168">一部のオプションは、プロセスのその時点で使用することがサポートされていないため、ロックを解除した後も無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="488a8-168">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="488a8-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="488a8-169">More information</span></span>

[<span data-ttu-id="488a8-170">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="488a8-170">Understanding Assessment in Relevance</span></span>](../assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="488a8-171">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="488a8-171">Tagging and assessment</span></span>](../tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="488a8-172">タグ付けと関連性トレーニング</span><span class="sxs-lookup"><span data-stu-id="488a8-172">Tagging and Relevance training</span></span>](../tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="488a8-173">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="488a8-173">Tracking Relevance analysis</span></span>](../track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="488a8-174">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="488a8-174">Deciding based on the results</span></span>](../decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="488a8-175">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="488a8-175">Testing Relevance analysis</span></span>](../test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="488a8-176">証拠でデータを照会する</span><span class="sxs-lookup"><span data-stu-id="488a8-176">Query the data in evidence</span></span>](evidence-query.md)
