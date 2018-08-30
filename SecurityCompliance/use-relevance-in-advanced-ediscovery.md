---
title: Office 365 Advanced eDiscovery で関連性モジュールを使用する
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
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: 'ワークフローとガイドライン、およびトレーニングとファイルの確認のための手順を含む、Office 365 の詳細の開示に関連性の高いモジュールについて説明します。  '
ms.openlocfilehash: 2cf75ef95291c5393367ce01fb0cd660f9b99145
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531910"
---
# <a name="use-the-relevance-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="c16b8-103">Office 365 Advanced eDiscovery で関連性モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="c16b8-103">Use the Relevance module in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="c16b8-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="c16b8-p102">高度な電子的証拠開示には、関連性の高いモジュールには、関連性の高いトレーニングとサポート案件に関連するファイルの確認が含まれています。関連性の高いワークフローが表示され、次のように記載されています。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p102">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case. The Relevance workflow is shown and described as follows:</span></span>
  
![関連性のワークフロー](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="c16b8-109">**サイクル**します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="c16b8-110">**評価**: 高度な電子的証拠開示がにより、ファイルのランダムなサンプルに基づく事前の評価と予測のコーディング プロセスのパフォーマンスを決定する決定を適用するのにはこの評価を使用します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="c16b8-111">**トラック**: 高度な電子的証拠開示を計算し、評価プロセスの統計的な有効性を監視しながらの暫定的な結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="c16b8-112">**サイクル**します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="c16b8-113">**タグ**: 高度な電子的証拠開示がエキスパートの反復的なレビューに基づく各問題を特定し、個々 のファイルのタグ付けの関連性の基準を学習します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="c16b8-114">**トラック**: 高度な電子的証拠開示が計算され、プロセスの統計的な有効性を監視しながら、関連性の高いトレーニングの中間の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="c16b8-115">**バッチ計算**: 高度な電子的証拠開示、累計と学習した関連性の基準は、全体のファイルのコレクションに適用されます、ファイルごとに関連性のスコアを生成します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="c16b8-116">**決定する**: 高度な電子的証拠開示バッチ計算の後、全体のケースに適用される分析の結果を表示し、ドキュメント レビューの決定を行うためのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="c16b8-117">**テスト**: 高度な電子的証拠開示処理の有効性と妥当性を確認するのには高度な電子的証拠開示の結果をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="c16b8-118">関連のトレーニングおよび確認のためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="c16b8-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="c16b8-119">以下は、関連性の高いトレーニングおよび確認のためのガイドラインの概要です。</span><span class="sxs-lookup"><span data-stu-id="c16b8-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="c16b8-p103">**間違いや不統一**: トレーニング中にエラーをタグ付けを行った場合は、それらを修正する前のサンプルのファイルに戻ります。修正するのにはエラーが多すぎる、またはサポート案件または問題の新しい視点がある、管理者が関連性の基準を再定義する必要があり、関連性の高いトレーニングを再開します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p103">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them. If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="c16b8-122">**名札管理とトレーニング**します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="c16b8-p104">ファイルは、コンテンツのみに基づくタグ付けする必要があります。保管担当者、日付、またはファイルのパスなどのメタデータを考慮しません。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p104">Files should be tagged based on content only. Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="c16b8-125">ときに考慮日付、テキストの範囲指示ファイルへのタグ付け。</span><span class="sxs-lookup"><span data-stu-id="c16b8-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="c16b8-126">ファイルをタグ付けするときに埋め込まれた画像を考慮しません。</span><span class="sxs-lookup"><span data-stu-id="c16b8-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="c16b8-p105">タグ付けしているときに**ビューのテキストを書式設定**] アイコンを使用してファイルを表示している場合に、テキストの書式設定を考慮はしません。たとえば、(削除を示す中心から水平の線) は取り消し線付きで表示される単語見なされます分析されたテキストの一部として関連性で。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p105">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text. For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="c16b8-p106">(ケース マネージャーまたは管理者によって設定された) として関連性を適用するテキストを無視して関連性のテキスト ビューに表示されているファイルの内容では削除されます。場合は関連性の高いトレーニング開始されて既に後無視するテキストの値に定義された、無視された新しいテキストが定義されているポイントから作成したサンプル ファイルに適用されます。テキストを無視する機能があるため注意が必要、そのファイルの分析のパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p106">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance. If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined. The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="c16b8-p107">必要な場合のみ**へのタグ付けをスキップする**オプションを使用します。高度な電子的証拠開示はトレーニング ベースにスキップされたファイルです。評価、ファイルが該当するかどうかを確認することは困難である場合お勧めタグに Relevant (R) としてか関連 (NR)**スキップ**を選択するのではなく可能な限りです。高度な電子的証拠開示には、トレーニングが評価されると、これらの種類のファイルが処理された方法も、確認できます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p107">Use the **Skip tagging** option only when necessary. Advanced eDiscovery does not train based on skipped files. In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**. When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="c16b8-136">抽出したテキストの量が非常に小さいにもファイルは、「スキップ」、可能な場合ではなく R と NR としてトレーニングにタグ付き必要があります。</span><span class="sxs-lookup"><span data-stu-id="c16b8-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="c16b8-137">タグを付けることができますに影響を与える分類子である限り、ファイルを読み取ることが R と NR としてタグ付けすることができます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="c16b8-138">[**タグ**] タブで表示されているサンプル ファイルの一覧でファイルのシーケンス番号は、ファイルの元の表示順序を取得するユーザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="c16b8-p108">任意のサンプルに戻るし、評価のタグ付けを変更でき、トレーニングは、ファイルを設定します。変更は、次のサンプルを作成するときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p108">You can go back to any sample and change the tagging of the assessment and training set files. The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="c16b8-141">スキャンした Excel のファイルを PDF 形式で必要がありますを同等に扱うネイティブの Excel ファイルとしてファイルをタグ付けするとします。</span><span class="sxs-lookup"><span data-stu-id="c16b8-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="c16b8-p109">判断に迷う場合、ファイルのタグ付けの関連性について、専門家を参照してください。関連のトレーニング中に不正なタグを付けるプロセスの後半で時間のロスにつながることができ、結果全体の品質に悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p109">When in doubt regarding the Relevance tagging of a file, consult an expert. Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="c16b8-144">定義されているキーワードへのタグ付けしているときに関連ファイルを特定のユーザーのために色のキーワードのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="c16b8-p110">**バッチ計算**: R/NR エキスパートが表示されますスコアが 0 または 100 のいずれかのようにタグ付けされたファイルです。これは、バッチ計算の前に行われたタグに適用されます。上級者は、バッチ計算後のアイドル状態に問題を切り替えられるし、続き、この問題をタグ付けは 100 と 0 ですが、元のスコアではなくも新たにタグ付けされたスコアはできません。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p110">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100. This applies to tagging made before Batch calculation. If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="c16b8-148">**問題およびサンプリング モード**: 問題通常オフになっているそれらの作業が完了したとき (関連性の高いトレーニングを安定させるし、バッチ計算が実行された)、問題がキャンセルされた場合、または問題の別のユーザーを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="c16b8-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="c16b8-149">関連性の高いトレーニングの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-149">Steps in Relevance training</span></span>

<span data-ttu-id="c16b8-p111">**の関連性\>トラック**] タブの [高度な電子的証拠開示に関する推奨事項する方法についての処理は、次の次の手順に進みます。関連性の高いトレーニング プロセスの次の手順をお勧めすると影響については後述します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p111">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps. The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="c16b8-152">タグ付けまたはタグ付けを続行する: ファイルのファイルのレビューとの関連性は、それぞれの専門家によって実行されるタグ付けし、サンプル内で発行します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="c16b8-153">意味: 既存のサンプルは、タグを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c16b8-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="c16b8-154">評価/評価を継続: ケース問題の関連性の事前検証、現在のケースのインポート ファイルの作成との関連性の予備的なビューを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c16b8-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="c16b8-155">意味: 複数の評価は、必須または推奨します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="c16b8-156">トレーニング/トレーニングを続ける: のどの詳細設定の中にファイルへのタグ付けは、エキスパートから学習する電子的証拠開示プロセスをサンプリングし、各ケースのコンテキスト内で各問題に関連する関連性の基準を特定する機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="c16b8-157">影響: 問題が必要なトレーニングです。次のサンプルを作成してタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c16b8-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="c16b8-p112">バッチ計算: 関連性のプロセスの詳細に電子的証拠開示トレーニングの段階で得られる知識は、全体のファイルの作成に適用されます。関連のファイル グループ内のすべてのファイルは関連性の評価し、関連性スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p112">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population. All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="c16b8-160">影響: 問題が安定化、およびバッチの計算を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="c16b8-161">キャッチアップ: 関連性は、専門家が確認し、タグのロールを読み込むシナリオ中に、追加のファイルのロードから選択したファイルのサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="c16b8-162">意味: は、新しい負荷を追加すると、キャッチアップする作業を続行する必要が。</span><span class="sxs-lookup"><span data-stu-id="c16b8-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="c16b8-163">矛盾をタグ付け: プロセスを識別、高度な電子的証拠開示のアルゴリズムを使用して分析に悪影響を与える可能性があるプロセスにタグを付けるファイル内の矛盾します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="c16b8-164">意味: は、次のサンプルにはファイルが含まれてタグが付けられている前のサンプルと、タグ付けをやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c16b8-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="c16b8-165">分類子を更新する: タグ付けまたはシード処理の変更を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c16b8-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="c16b8-166">意味: タグ付けして、シード処理の変更を適用できますせず、手動で別の関連性のサンプルを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c16b8-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="c16b8-167">保留中: の関連性の高い学習のプロセスが完了しました。</span><span class="sxs-lookup"><span data-stu-id="c16b8-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="c16b8-168">意味: 関連性の高いトレーニングは必要ありませんこの時点で。</span><span class="sxs-lookup"><span data-stu-id="c16b8-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="c16b8-169">高度な電子的証拠開示プロセスを案内するのさまざまな段階で次の手順を推奨する、こともできますタブやページ間を移動して、個々 の場合、問題に関連する可能性のある状況を解決するを選択するか、ドキュメントの校閲プロセスです。</span><span class="sxs-lookup"><span data-stu-id="c16b8-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="c16b8-p113">承諾または高度な電子的証拠開示の選択肢を処理する次の手順をオーバーライドすることは。以外の推奨される次の手順のステップを実行] をクリックする場合はダイアログ ボックスで展開されている問題の表示に記載されている**次のステップ**を、次の手順の横にある [**変更**] ボタンをクリックして、別の次の手順オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-p113">It is possible to accept or override Advanced eDiscovery Next step processing choices. If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c16b8-172">ロックを解除した後プロセスの時点で使用するためサポートされていないいくつかのオプションが無効なままです。</span><span class="sxs-lookup"><span data-stu-id="c16b8-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c16b8-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="c16b8-173">See also</span></span>

[<span data-ttu-id="c16b8-174">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c16b8-174">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c16b8-175">関連性の評価を理解します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c16b8-176">タグ付けおよび評価</span><span class="sxs-lookup"><span data-stu-id="c16b8-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c16b8-177">タグ付けと関連性の高いトレーニング</span><span class="sxs-lookup"><span data-stu-id="c16b8-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c16b8-178">追跡の関連性の分析</span><span class="sxs-lookup"><span data-stu-id="c16b8-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c16b8-179">結果に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="c16b8-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c16b8-180">テストの関連性の分析</span><span class="sxs-lookup"><span data-stu-id="c16b8-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

