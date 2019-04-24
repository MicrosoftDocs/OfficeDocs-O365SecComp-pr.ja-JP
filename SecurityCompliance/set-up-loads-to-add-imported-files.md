---
title: Office 365 の高度な電子情報開示でインポートされたファイルを追加するためのロードを設定する
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: 'Office 365 Advanced eDiscovery で関連性トレーニングを実行する前に、インポートされたファイルを最後に定義したロードまたはバッチファイルに追加する手順を確認します。  '
ms.openlocfilehash: 8c5101628b468719f8aa4f81a4c73cbbb226105f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260742"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a><span data-ttu-id="36bc5-103">Office 365 の高度な電子情報開示でインポートされたファイルを追加するためのロードを設定する</span><span class="sxs-lookup"><span data-stu-id="36bc5-103">Set up loads to add imported files in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="36bc5-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="36bc5-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="36bc5-106">高度な電子情報開示では、ケースに追加されたファイルの新しいバッチがロードされます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-106">In Advanced eDiscovery, a load is a new batch of files added to a case.</span></span> <span data-ttu-id="36bc5-107">既定では、1つの負荷が定義され、インポートされたすべてのファイルが追加されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-107">By default, one load is defined and all imported files are added to it.</span></span> <span data-ttu-id="36bc5-108">関連性トレーニングを実行する前に、インポートしたファイルをロードに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36bc5-108">Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="36bc5-109">次のようなシナリオを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="36bc5-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="36bc5-110">新しいファイルは、ケースデータベースに読み込まれた以前のファイルに似ていることがわかっているか、ファイルの以前の負荷がファイルコレクションからランダムに設定されていました。</span><span class="sxs-lookup"><span data-stu-id="36bc5-110">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection.</span></span> <span data-ttu-id="36bc5-111">このインスタンスでは、インポートしたファイルを現在のファイルの読み込みに追加します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-111">In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="36bc5-112">新しいファイルが以前のファイルと異なる (たとえば、別のソースからの) 場合、または以前の負荷と類似しているか、異なる新しいファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="36bc5-112">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads.</span></span> <span data-ttu-id="36bc5-113">このシナリオでは、インポートしたファイルを新しいファイルの読み込みに追加します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-113">In this scenario, add the imported files to a new file load.</span></span> <span data-ttu-id="36bc5-114">上級電子情報開示は、これをローリングロードシナリオとして認識し、キャッチアッププロセスを起動し、キャッチアップが完了するまで関連トレーニングとバッチ計算をロックし、新しい負荷を統合し、トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="36bc5-114">Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="36bc5-115">インポートされたファイルを現在の負荷に追加する</span><span class="sxs-lookup"><span data-stu-id="36bc5-115">Adding imported files to the current load</span></span>

<span data-ttu-id="36bc5-116">インポートされたすべてのファイルは、高度な電子情報開示で処理するには、負荷に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36bc5-116">All imported files must be added to a load to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="36bc5-117">インポートしたファイルは、最後に定義されたロードに追加されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-117">Imported files are added to the last defined load.</span></span> <span data-ttu-id="36bc5-118">後で追加のファイルをインポートする場合は、それらもロードに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36bc5-118">If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="36bc5-119">[**関連性\>の関連性の設定**] タブで、[**ロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![[関連性の設定をロード] タブ](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="36bc5-121">**インクルードファイル**: 含めるファイルのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-121">**Include files**: Select an option for files to include.</span></span> <span data-ttu-id="36bc5-122">既定では、現在の負荷にファイルを追加すると、"すべてのファイル" の作成に基づきます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-122">By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="36bc5-123">利用可能なすべてのカリングファイルを関連に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-123">Load all available culled files into Relevance.</span></span> <span data-ttu-id="36bc5-124">利用可能なファイルのサブセットのみを読み込む予定の場合は、「サポート」を参照してください。サブセットを読み込むと、関連性トレーニングに悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36bc5-124">If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="36bc5-125">[**ロード管理**] で、ロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="36bc5-126">[**ファイルの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-126">Click **Add files**.</span></span> <span data-ttu-id="36bc5-127">ファイルがロードに追加され、確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-127">The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="36bc5-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-128">Click **OK**.</span></span>
    
<span data-ttu-id="36bc5-129">ファイルをトレーニングするために、上級電子情報開示の関連性でファイルを処理できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="36bc5-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="36bc5-130">ケース内での読み込み名の編集</span><span class="sxs-lookup"><span data-stu-id="36bc5-130">Editing a load name within a case</span></span>

<span data-ttu-id="36bc5-131">読み込み名を変更する場合は、ケースにとって重要な名前を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="36bc5-132">[**関連性\>の関連性の設定**] タブで、[**ロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="36bc5-133">[load **management** ] の一覧から、ロードを選択し、[**編集**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-133">From the **Loads management** list, select a load and click the **Edit** icon.</span></span> <span data-ttu-id="36bc5-134">[読み込みの編集] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-134">The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="36bc5-135">変更を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="36bc5-136">インポートされたファイルを新しいロードに追加する</span><span class="sxs-lookup"><span data-stu-id="36bc5-136">Adding imported files to a new load</span></span>

<span data-ttu-id="36bc5-137">関連性のトレーニングを開始するか、バッチ計算を実行すると、追加のファイルセットをインポートして処理することができます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="36bc5-138">キャッチアップの間に、キャッチアップセットを作成、タグ付け、および分析することができます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-138">During Catch-up, you can create, tag, and analyze the Catch-up set.</span></span> <span data-ttu-id="36bc5-139">上級電子情報開示は、新しい負荷における関連ファイルと関連しないファイルの評価を以前の負荷と比較します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-139">Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads.</span></span> <span data-ttu-id="36bc5-140">結果に基づいて、キャッチアップに関する決定事項を必要に応じて確認するよう求められます。また、上級電子情報開示では、見越計上の関連性情報に基づいた推奨事項を提供します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-140">Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="36bc5-141">ロールロードおよびキャッチアップ機能は、次のように異なります。</span><span class="sxs-lookup"><span data-stu-id="36bc5-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="36bc5-142">バッチ計算後に新しいファイル読み込みをインポートする場合、Advanced eDiscovery は次のいずれかのカテゴリにどの程度ファイルが含まれるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="36bc5-143">類似 (同種): 新しい、カスタムの関連性のトレーニングは必須ではなく、以前の負荷からのナレッジの見越計上を新しい負荷に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="36bc5-144">Distinct (異種): 新しいカスタムラウンドの関連性トレーニングが必要であり、前のロードからのナレッジを適用できません。</span><span class="sxs-lookup"><span data-stu-id="36bc5-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="36bc5-145">これらの用語は、ロード間ではなく、ファイルの類似性のレベルを表します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="36bc5-146">関連性トレーニングの際に (バッチ計算の前に)、新しいファイル読み込みをインポートする場合、キャッチアップを使用すると、英語のファイルセットに対して関連性のトレーニングを続行できます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-146">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set.</span></span> <span data-ttu-id="36bc5-147">上級電子情報開示では、新しい負荷が以前の負荷と類似しているか、または異なるかは予測されません。</span><span class="sxs-lookup"><span data-stu-id="36bc5-147">Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load.</span></span> <span data-ttu-id="36bc5-148">これは単に、新しい負荷に関する情報を収集し、関連のトレーニングが新しいファイルおよび以前のファイルセットに対して継続するようにします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-148">It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="36bc5-149">関連性のトレーニングに問題があり、バッチの計算後に問題が発生した場合、キャッチアッププロセスはすべての問題に対して1回実行され、結果は各問題について計算され、表示されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="36bc5-150">キャッチアップサンプルのサイズは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="36bc5-150">The size of the Catch-up sample may vary.</span></span> <span data-ttu-id="36bc5-151">これは、以前の負荷に対する新しい負荷のサイズと、新しい負荷を追加する前に完了したサンプルの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="36bc5-151">It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load.</span></span> <span data-ttu-id="36bc5-152">キャッチアップサンプルは、通常、新しいロードから 200 ~ 2000 ファイルのセットです。</span><span class="sxs-lookup"><span data-stu-id="36bc5-152">The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="36bc5-153">キャッチアップは他のタスクを停止し、個々のファイルのタグ付けとレビューを必要とします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-153">Catch-up stops any other tasks and requires individual file tagging and review.</span></span> <span data-ttu-id="36bc5-154">そのため、大きなバッチで新しいファイルを追加するときのオーバーヘッドを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-154">Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="36bc5-155">キャッチアップおよびローリングロードを使用して新しいファイル読み込みを追加する</span><span class="sxs-lookup"><span data-stu-id="36bc5-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="36bc5-156">[**関連性\>の関連性の設定**] タブで、[**ロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="36bc5-157">[ロード**管理**] で、 **+** アイコンをクリックしてロードを追加します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-157">Under **Loads management**, click the **+** icon to add a load.</span></span> <span data-ttu-id="36bc5-158">確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-158">A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="36bc5-159">**[はい]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-159">Click **Yes** to continue.</span></span> <span data-ttu-id="36bc5-160">[**新しい読み込みの追加**] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-160">The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="36bc5-161">以前のロードに対してアクションが実行された場合にのみ、新しいロードを追加できます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="36bc5-162">[**新しい負荷の追加**] ダイアログで、[**読み込み名**] と [**説明**] に情報を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-162">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**.</span></span> <span data-ttu-id="36bc5-163">高度な電子情報開示新しい負荷を追加します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-163">Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="36bc5-164">新しいロードファイルをインポートするには、[**ファイルの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-164">To import the new load file, click **Add files**.</span></span> <span data-ttu-id="36bc5-165">すべての新しいファイルがこの負荷に追加されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-165">All new files are added to this load.</span></span> <span data-ttu-id="36bc5-166">詳細な電子情報開示は、ファイルをインポートした後、ローリングロードシナリオを認識し、次の手順としてキャッチアップを示します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-166">After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="36bc5-167">ダイアログボックスの下部にある [**キャッチアップ**] をクリックして、シナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="36bc5-168">ファイルへの同時タグ付けを可能にするすべての問題について、通常、新しいロードから 200 ~ 2000 ファイルを含む単一のキャッチアップセットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="36bc5-169">負荷が類似または特徴的かどうか、高度な電子情報開示を統合するか分割するか、または次の手順での処理に関する情報についての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="36bc5-170">その後、ファイルにタグを付けて、計算操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-170">You can then tag files and run a calculate operation.</span></span> <span data-ttu-id="36bc5-171">タグ付けを使用すると、負荷が類似または特徴的かどうかを判断し、新しいファイルセットで作業を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-171">The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="36bc5-172">キャッチアップセットがレビューされた後、キャッチアップ結果の**関連性\>トラック**を表示します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="36bc5-173">関連性のあるトレーニング中に新しいファイルの読み込みが追加された場合 (つまり、その問題がまだバッチ計算を通過していない場合)、キャッチアップ結果に関係なく、次の手順で**トレーニングを続行**します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="36bc5-174">新しいおよび以前の負荷は、1つの負荷として処理され、関連のトレーニングは米国で続行されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-174">The new and previous loads are processed as one load and Relevance training continues on the united set.</span></span> <span data-ttu-id="36bc5-175">これで、この手順が完了し、関連のトレーニングを続行できます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-175">You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="36bc5-176">バッチ計算後に新しいロードが追加された場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="36bc5-177">バッチ計算後に新しい負荷が追加された場合、Advanced eDiscovery は、次のように、新しい負荷が以前の負荷と類似しているか、または異なるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="36bc5-178">同じような負荷が発生した場合は、追加の関連性トレーニングは不要です。</span><span class="sxs-lookup"><span data-stu-id="36bc5-178">If loads were found to be similar: No additional Relevance training is necessary.</span></span> <span data-ttu-id="36bc5-179">ダッシュボードでは、「\* \* Batch calculation \* \*」を再度実行して、新しい負荷の関連性スコアを計算することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-179">The dashboard shows the recommended next step is to run \*\* Batch calculation \*\* again to calculate Relevance scores for the new load.</span></span> <span data-ttu-id="36bc5-180">類似していることが判明したので、前の分類子分析を新しいファイルに対して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-180">Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="36bc5-181">明確な負荷が見つかった場合は、より関連性のトレーニングが必要であり、次の手順ではキャッチアップが決定されます。</span><span class="sxs-lookup"><span data-stu-id="36bc5-181">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision.</span></span> <span data-ttu-id="36bc5-182">次のようにして、キャッチアップの決定を選択します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-182">Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="36bc5-183">[負荷の**マージ**] を選択した場合、上級電子情報開示では、トレーニングセットの以前の負荷と新しい負荷をマージします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-183">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set.</span></span> <span data-ttu-id="36bc5-184">最初の読み込みはバッチ計算を通じて行われましたが、多くのトレーニングが必要です。</span><span class="sxs-lookup"><span data-stu-id="36bc5-184">Although the first load went through Batch calculation, more training is needed.</span></span> <span data-ttu-id="36bc5-185">新規および以前の負荷を一緒にトレーニングを続行します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-185">Continue training new and previous loads together.</span></span> <span data-ttu-id="36bc5-186">バッチ計算は再実行され、以前のバッチ計算スコアを無視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36bc5-186">Batch calculation will then run again and the previous Batch calculation scores should be ignored.</span></span> <span data-ttu-id="36bc5-187">既存の負荷の関連性スコアを再計算する場合、たとえば、既存のファイルの読み込みが開始されていない場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-187">Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="36bc5-188">**分割荷重**を選択する場合は、新しい負荷でのみ関連のトレーニングを続行します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-188">If you select **Split loads**, continue Relevance training only on the new load.</span></span> <span data-ttu-id="36bc5-189">この例では、以前のバッチ計算のスコアはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="36bc5-189">In this instance, previous Batch calculation scores will remain as is.</span></span> <span data-ttu-id="36bc5-190">既存の負荷の既存の関連性スコアを再計算できない場合、たとえば既存の負荷の確認が既に開始されている場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="36bc5-190">Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started.</span></span> <span data-ttu-id="36bc5-191">関連性スコアはこの点以降の個別に管理され、結合することはできません。</span><span class="sxs-lookup"><span data-stu-id="36bc5-191">Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="36bc5-192">[**トレーニングの続行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36bc5-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="36bc5-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="36bc5-193">See also</span></span>

[<span data-ttu-id="36bc5-194">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="36bc5-194">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="36bc5-195">問題の定義とユーザーの割り当て</span><span class="sxs-lookup"><span data-stu-id="36bc5-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="36bc5-196">強調表示されたキーワードと詳細オプションの定義</span><span class="sxs-lookup"><span data-stu-id="36bc5-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

