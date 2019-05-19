---
title: Office 365 の詳細な電子情報開示の関連モジュールを使用する
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
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: 'Office 365 Advanced eDiscovery の関連性モジュールについて説明します。これには、ワークフロー、ガイドライン、トレーニングとファイルレビューの手順が含まれます。  '
ms.openlocfilehash: f5b585008dca58f95b0f3b932b2ee4b82a1ae731
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156079"
---
# <a name="use-the-relevance-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="d96da-103">Office 365 の詳細な電子情報開示の関連モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="d96da-103">Use the Relevance module in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="d96da-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="d96da-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d96da-106">詳細な電子情報開示では、関連性に関するトレーニングと、ケースに関連するファイルのレビューが関連モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="d96da-106">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="d96da-107">関連性ワークフローが表示され、次のように説明されています。</span><span class="sxs-lookup"><span data-stu-id="d96da-107">The Relevance workflow is shown and described as follows:</span></span>
  
![関連性のワークフロー](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="d96da-109">**評価と追跡のサイクル**:</span><span class="sxs-lookup"><span data-stu-id="d96da-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="d96da-110">**評価**: Advanced eDiscovery は、無作為なファイルのサンプルに基づく事前評価を有効にし、この評価を使用して、予測コーディングプロセスのパフォーマンスを判断するために決定を適用します。</span><span class="sxs-lookup"><span data-stu-id="d96da-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="d96da-111">**追跡**: Advanced eDiscovery は、プロセスの統計的な有効性を監視しながら、評価の一時的な結果を計算して表示します。</span><span class="sxs-lookup"><span data-stu-id="d96da-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="d96da-112">**トレーニングと追跡のサイクル**:</span><span class="sxs-lookup"><span data-stu-id="d96da-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="d96da-113">**タグ**: 上級電子情報開示では、専門家による個々のファイルの反復的なレビューとタグ付けに基づいて、各問題に固有の関連性基準を学習します。</span><span class="sxs-lookup"><span data-stu-id="d96da-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="d96da-114">**追跡**: 高度な電子情報開示は、プロセスの統計的な有効性を監視しながら、関連性トレーニングの一時的な結果を計算して表示します。</span><span class="sxs-lookup"><span data-stu-id="d96da-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="d96da-115">**バッチ計算**: 高度な電子情報開示は、累積および学習した関連性の条件を取得し、ファイルコレクション全体に適用して、各ファイルの関連性スコアを生成します。</span><span class="sxs-lookup"><span data-stu-id="d96da-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="d96da-116">**決定**: Advanced eDiscovery は、バッチ計算後にケース全体に適用される分析の結果を表示し、ドキュメントレビューの決定に使用するデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="d96da-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="d96da-117">**テスト**: 高度な電子情報開示の結果は、高度な電子情報開示処理の有効性と効果を確認するためにテストできます。</span><span class="sxs-lookup"><span data-stu-id="d96da-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="d96da-118">関連性のトレーニングとレビューに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="d96da-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="d96da-119">関連のトレーニングとレビューのガイドラインの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d96da-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="d96da-120">**エラーと不整合**: トレーニング中にタグ付けエラーが発生した場合は、以前のファイルサンプルに戻って修正してください。</span><span class="sxs-lookup"><span data-stu-id="d96da-120">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="d96da-121">修正するエラーが多すぎる場合や、ケースまたは問題の新しいパースペクティブがある場合は、管理者が関連性の条件を再定義して、関連性トレーニングを再開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96da-121">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="d96da-122">**タグ付けとトレーニング**:</span><span class="sxs-lookup"><span data-stu-id="d96da-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="d96da-123">ファイルは、コンテンツのみに基づいてタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96da-123">Files should be tagged based on content only.</span></span> <span data-ttu-id="d96da-124">保管担当者、日付、ファイルパスなどのメタデータは考慮しません。</span><span class="sxs-lookup"><span data-stu-id="d96da-124">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="d96da-125">ファイルにタグ付けするときに、テキストに日付範囲が表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="d96da-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="d96da-126">ファイルへのタグ付け時に埋め込まれた画像を考慮しません。</span><span class="sxs-lookup"><span data-stu-id="d96da-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="d96da-127">タグ付けの際に**書式付きのテキストビュー**アイコンを使用してファイルを表示する場合は、テキストの書式設定を考慮しません。</span><span class="sxs-lookup"><span data-stu-id="d96da-127">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text.</span></span> <span data-ttu-id="d96da-128">たとえば、取り消し線を使用して表示された単語 (削除を示す水平線) は、解析されたテキストの一部としても関連性があると見なされます。</span><span class="sxs-lookup"><span data-stu-id="d96da-128">For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="d96da-129">(ケースマネージャーまたは管理者が設定した) 関連性に適用されたテキストは、[関連性] のテキストビューに表示されているファイルコンテンツから削除されます。</span><span class="sxs-lookup"><span data-stu-id="d96da-129">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="d96da-130">関連性トレーニングが既に開始された後に、Ignore text の値が定義されていた場合、新しい無視されたテキストは、定義された時点から作成されたサンプルファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d96da-130">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="d96da-131">ファイル分析のパフォーマンスが低下する可能性があるため、[テキストを無視する] 機能は慎重に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96da-131">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="d96da-132">[**タグをスキップ**する] オプションは必要な場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="d96da-132">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="d96da-133">上級電子情報開示は、スキップされたファイルに基づいてトレーニングを行いません。</span><span class="sxs-lookup"><span data-stu-id="d96da-133">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="d96da-134">評価では、ファイルが関連しているかどうかを判断するのが難しい場合は、 **Skip**を選択するのではなく、可能な限り、関連性のある (R) または関連していない (NR) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d96da-134">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="d96da-135">高度な電子情報開示でトレーニングを評価すると、これらの種類のファイルがどのように処理されたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d96da-135">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="d96da-136">抽出されたテキストが非常に小さいファイルでも、可能な場合は "Skip" ではなく、R/NR としてのトレーニングでタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96da-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="d96da-137">タグ付けは、ファイルが読みやすく、R/NR としてタグ付けできる限り、分類子に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d96da-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="d96da-138">[**タグ**] タブの表示されているサンプルファイルの一覧のファイルシーケンス番号を使用すると、ユーザーは、表示されている元のファイルの順序に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="d96da-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="d96da-139">すべてのサンプルに戻って、評価およびトレーニングセットファイルのタグ付けを変更できます。</span><span class="sxs-lookup"><span data-stu-id="d96da-139">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="d96da-140">変更は、次のサンプルを作成するときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d96da-140">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="d96da-141">PDF 形式でスキャンした Excel ファイルは、ファイルにタグ付けするときに、ネイティブの Excel ファイルと同じように処理されます。</span><span class="sxs-lookup"><span data-stu-id="d96da-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="d96da-142">ファイルの関連性のタグ付けに関して疑わしい場合は、専門家に相談してください。</span><span class="sxs-lookup"><span data-stu-id="d96da-142">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="d96da-143">関連性トレーニング中に誤ったタグ付けを行うと、プロセスの後期に時間が失われることがあり、結果全体の品質に悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d96da-143">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="d96da-144">キーワードリストで定義されたキーワードは、タグ付け中にユーザーが関連ファイルを識別するのに役立つ色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="d96da-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="d96da-145">**バッチ計算**: 専門家による R/NR としてタグ付けされたファイルのスコアは0または100のいずれかとなります。</span><span class="sxs-lookup"><span data-stu-id="d96da-145">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="d96da-146">これは、バッチ計算前に行われるタグ付けに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d96da-146">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="d96da-147">上級者が一括計算した後に問題をアイドルに切り替えて、この問題のタグ付けを続行した場合、新しくタグ付けされたスコアは100/0 にならず、元のスコアになります。</span><span class="sxs-lookup"><span data-stu-id="d96da-147">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="d96da-148">**問題とサンプリングモード**: 問題が発生した場合は、その作業が完了し、問題が取り消されたとき、または他のユーザーが問題に対処しているときに、通常はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="d96da-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="d96da-149">関連性トレーニングの手順</span><span class="sxs-lookup"><span data-stu-id="d96da-149">Steps in Relevance training</span></span>

<span data-ttu-id="d96da-150">[**関連性\>の追跡**] タブで、Advanced eDiscovery は処理を進める方法に関する推奨事項を提供し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d96da-150">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="d96da-151">関連トレーニングプロセスで以下の各手順を実行する場合は、次に示す影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="d96da-151">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="d96da-152">タグ付け/続行のタグ付け: サンプル内のファイルと問題について、エキスパートによってファイルのレビューと関連性のタグ付けが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d96da-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="d96da-153">暗黙: 既存のサンプルは、タグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96da-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="d96da-154">評価/続行評価: ケース上の問題の関連性と、現在のケースに対してインポートされたファイルの作成の関連性を事前に検証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d96da-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="d96da-155">暗示: より多くの評価が必要または推奨されています。</span><span class="sxs-lookup"><span data-stu-id="d96da-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="d96da-156">トレーニング/続行トレーニング: 上級電子情報開示がファイルのサンプルにタグ付けされているエキスパートから学習し、各ケースのコンテキスト内で各問題に関連する関連性基準を特定する機能を取得するプロセス。</span><span class="sxs-lookup"><span data-stu-id="d96da-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="d96da-157">意味: 問題により多くのトレーニングが必要になります。次のサンプルを作成し、タグを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96da-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="d96da-158">バッチ計算: 高度な電子情報開示がトレーニング段階で取得したナレッジを取得し、ファイルの作成全体に適用する関連性プロセス。</span><span class="sxs-lookup"><span data-stu-id="d96da-158">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="d96da-159">関連するファイルグループ内のすべてのファイルに関連性があることが評価され、関連性スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d96da-159">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="d96da-160">意味: 問題が安定しており、バッチ計算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d96da-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="d96da-161">キャッチアップ: 関連性は、エキスパートが、ローリングロードシナリオで追加のファイルロードから選択されたファイルのサンプルをレビューし、タグ付けするタイミングを示します。</span><span class="sxs-lookup"><span data-stu-id="d96da-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="d96da-162">暗黙: 新しい読み込みが追加され、作業を続行するにはキャッチアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="d96da-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="d96da-163">タグの不整合: プロセスは、高度な電子情報開示アルゴリズムを使用して、分析に悪影響を及ぼす可能性のあるファイルのタグ付けプロセスの不整合を識別します。</span><span class="sxs-lookup"><span data-stu-id="d96da-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="d96da-164">意味: 次のサンプルには、前のサンプルでタグ付けされたファイルが含まれており、タグ付けをやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96da-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="d96da-165">Update クラシファイア: ユーザーがタグ付けまたはシード変更を適用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d96da-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="d96da-166">暗黙: 別の関連性サンプルを手動で実行しなくても、タグ付けとシードによる変更を適用できます。</span><span class="sxs-lookup"><span data-stu-id="d96da-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="d96da-167">保留中: 関連トレーニングプロセスが完了します。</span><span class="sxs-lookup"><span data-stu-id="d96da-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="d96da-168">意味: この時点では、関連性トレーニングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d96da-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="d96da-169">詳細な電子情報開示では、さまざまな段階で推奨される次の手順を使用してプロセスを進めることができますが、タブとページ間を移動したり、個別のケース、問題、またはの状況に関係する状況に対処するための選択を行ったりすることもできます。ドキュメントレビュープロセス。</span><span class="sxs-lookup"><span data-stu-id="d96da-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="d96da-170">高度な電子情報開示の次のステップ処理の選択を承諾または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d96da-170">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="d96da-171">次の推奨手順以外の手順を実行する場合は、ダイアログボックスの展開された問題の表示で**次の手順**をクリックし、次の手順の横にある [**変更**] ボタンをクリックして、別の [次の手順] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d96da-171">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d96da-172">一部のオプションは、プロセスのその時点で使用することがサポートされていないため、ロックを解除した後も無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="d96da-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d96da-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="d96da-173">See also</span></span>

[<span data-ttu-id="d96da-174">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d96da-174">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d96da-175">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="d96da-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d96da-176">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="d96da-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d96da-177">タグ付けと関連性トレーニング</span><span class="sxs-lookup"><span data-stu-id="d96da-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d96da-178">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="d96da-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d96da-179">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="d96da-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d96da-180">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="d96da-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

