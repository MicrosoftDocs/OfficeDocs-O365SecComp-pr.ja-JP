---
title: Office 365 Advanced eDiscovery でインポート ファイルを追加するロードを設定する
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: '定義されたロードの最後、または Office 365 の高度な電子的証拠の開示に関連性の高いトレーニングを実行する前にファイルのバッチをインポートするファイルを追加する手順を確認します。  '
ms.openlocfilehash: 2c986578b969b671351930fd6939a90e3a821dc2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532672"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a><span data-ttu-id="d12a4-103">Office 365 Advanced eDiscovery でインポート ファイルを追加するロードを設定する</span><span class="sxs-lookup"><span data-stu-id="d12a4-103">Set up loads to add imported files in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="d12a4-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d12a4-p102">高度な電子的証拠開示、ロードがサポート案件に追加されたファイルの新しいバッチです。既定では、1 つの荷重が定義されているし、それにインポートされたすべてのファイルが追加されます。関連性の高いトレーニングを実行する前に、荷重をインポートしたファイルを追加しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p102">In Advanced eDiscovery, a load is a new batch of files added to a case. By default, one load is defined and all imported files are added to it. Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="d12a4-109">次のシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d12a4-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="d12a4-p103">新しいファイルが以前のケースのデータベースに読み込まれたファイルのように呼ばれるかのファイルの以前のロード、ファイルのコレクションからのランダムなセット。このインスタンスでは、現在のファイルの読み込みにインポートするファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p103">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection. In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="d12a4-p104">新しいファイルとは異なる (たとえば、別のソースから)、前のものか、類似点と相違前荷重にしている知識がありません。このシナリオでは、新しいファイルの読み込みにインポートするファイルを追加します。高度な電子的証拠開示ローリング ロードのシナリオとして、これを認識するには、キャッチアップのプロセスを起動、キャッチアップが完了し、新しいロードが統合されており、トレーニングを受けたまでに、関連性の高いトレーニングとバッチ計算をロックします。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p104">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads. In this scenario, add the imported files to a new file load. Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="d12a4-115">インポートしたファイルを現在の負荷に追加します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-115">Adding imported files to the current load</span></span>

<span data-ttu-id="d12a4-p105">高度な電子的証拠開示で処理する負荷には、インポートされたすべてのファイルを追加しなければなりません。最後の定義済みのロードには、インポートしたファイルが追加されます。後から追加のファイルをインポートする場合も追加の負荷にします。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p105">All imported files must be added to a load to be processed in Advanced eDiscovery. Imported files are added to the last defined load. If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="d12a4-119">**の関連性\>関連性の高いセットアップ**] タブで、**負荷**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![[関連性の設定をロード] タブ](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="d12a4-p106">**インクルード ファイル**: ファイルに追加のオプションを選択します。既定では、ファイルを現在の負荷に追加するはすべてのファイルの作成に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p106">**Include files**: Select an option for files to include. By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d12a4-p107">関連性に利用可能なすべての culled ファイルをロードします。利用可能なファイルのサブセットだけをロードする場合は、最初に相談するサポート、サブセットを読み込み中に悪影響が関連性の高いトレーニングと。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p107">Load all available culled files into Relevance. If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="d12a4-125">**荷重の管理**では、負荷を選択します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="d12a4-p108">[**ファイルの追加**] をクリックします。ロードするファイルを追加し、確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p108">Click **Add files**. The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="d12a4-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d12a4-128">Click **OK**.</span></span>
    
<span data-ttu-id="d12a4-129">ファイルは、ファイルのトレーニングの高度な電子的証拠開示の関連性で今すぐ処理できます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="d12a4-130">ケース内の荷重名を編集</span><span class="sxs-lookup"><span data-stu-id="d12a4-130">Editing a load name within a case</span></span>

<span data-ttu-id="d12a4-131">荷重名を変更する場合は、大きなケースには名前を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d12a4-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="d12a4-132">**の関連性\>関連性の高いセットアップ**] タブで、**負荷**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="d12a4-p109">**荷重の管理**] ボックスの一覧からは、負荷を選択し、[**編集**] アイコンをクリックします。編集のロード] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p109">From the **Loads management** list, select a load and click the **Edit** icon. The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="d12a4-135">、変更内容を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d12a4-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="d12a4-136">新しい荷重をインポートするファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-136">Adding imported files to a new load</span></span>

<span data-ttu-id="d12a4-137">関連のトレーニングやバッチ計算の実行を開始した後にインポートし、追加のファイルのセットを処理できます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="d12a4-p110">キャッチアップでは、実行中に作成、タグをしてキャッチアップを分析できます。高度な電子的証拠開示では、新しいロードでは、前の荷重での関連性と関連性のないファイルの評価を比較します。結果に基づき、表示されたら、キャッチアップの意思決定に必要な高度な eDiscovery 未収の関連性の高い情報に基づく推奨事項を提供している場合。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p110">During Catch-up, you can create, tag, and analyze the Catch-up set. Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads. Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="d12a4-141">荷重および機能のキャッチアップは次のように異なります。</span><span class="sxs-lookup"><span data-stu-id="d12a4-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="d12a4-142">バッチ計算の後に新しいファイルの読み込みをインポートすると、ファイルが次のカテゴリのいずれかに該当する程度を判断する高度な電子的証拠開示を決定します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="d12a4-143">似ていますが (同機種): 関連性の高いトレーニングの新しい、カスタムのラウンドは必須ではありませんし、以前のロードから計上に関する知識は新しい負荷に適用します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="d12a4-144">Distinct (異機種混在): 新たにカスタムのラウンドの関連性の高いトレーニングが必要であり、計上前の負荷から知識を適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d12a4-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="d12a4-145">これらの用語は、荷重と荷重ではなく、ファイルの類似性のレベルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d12a4-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="d12a4-p111">(前のバッチ計算) に、の関連性の高いトレーニング中に新しいファイルのロードをインポートするとき遅れの取り戻しを使用すると、一連の米国のファイルに関連性の高いトレーニングを継続します。高度な電子的証拠開示は、新しい負荷がかどうかのような以前のロードとは異なるを推定できません。単に新しい負荷についての情報を収集し、関連性は、ファイルのセットのトレーニングを新しいと前に進みます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p111">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set. Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load. It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="d12a4-149">バッチ計算後は、問題だけでなく、関連性の高いトレーニングでの複数の問題があります、キャッチアップのプロセスは、すべての問題については、1 回実行し、結果が計算され、各問題に対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d12a4-p112">キャッチアップ サンプルのサイズが異なる場合があります。新しい負荷を追加する前に完了したサンプルの数と、前の荷重を基準にして新しい負荷のサイズに依存します。キャッチアップのサンプルは、通常、新しい負荷から 200 ~ 2,000 ファイルのセットです。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p112">The size of the Catch-up sample may vary. It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load. The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="d12a4-p113">キャッチアップでは、他のタスクを停止し、個々 のファイルへのタグ付けとレビューを必要とします。したがって、することがオーバーヘッドを減らすため大規模なバッチで新しいファイルを追加する場合。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p113">Catch-up stops any other tasks and requires individual file tagging and review. Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="d12a4-155">ロード キャッチアップとロールを使用して新しいファイルのロードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="d12a4-156">**の関連性\>関連性の高いセットアップ**] タブで、**負荷**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="d12a4-p114">**荷重の管理**の下でをクリックして、**+** ロードを追加するアイコン。確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p114">Under **Loads management**, click the **+** icon to add a load. A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="d12a4-p115">**[はい]** をクリックします。**新規追加の読み込み**ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p115">Click **Yes** to continue. The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d12a4-161">以前のロードにアクションが実行された場合にのみ、新しい負荷を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="d12a4-p116">**新規追加の読み込み**ダイアログ ボックスで、**ロードの名前**と**説明**の情報を入力し、[ **OK**] をクリックします。高度な電子的証拠開示では、新しい負荷を追加します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p116">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**. Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="d12a4-p117">ロードする新しいファイルをインポートするには、**ファイルの追加**をクリックします。この負荷には、すべての新しいファイルが追加されます。ファイルをインポートすると、高度な電子的証拠開示後ローリング ロード シナリオを認識し、キャッチアップとして次の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p117">To import the new load file, click **Add files**. All new files are added to this load. After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="d12a4-167">**キャッチアップ**します] ダイアログ ボックスの下部にあるシナリオを実行する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d12a4-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="d12a4-168">同時実行ファイルへのタグ付けを許可するすべての問題は、通常新しいの負荷では、200 ~ 2,000 ファイルを含む、1 つの遅れの取り戻しセットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="d12a4-169">荷重は、のようなまたは重複するかどうか、高度な電子的証拠開示をマージまたは荷重を自動的に分割するかどうかおよび情報に関する詳細については説明は、次のステップでの処理に関連します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="d12a4-p118">ファイルにタグ付けし、計算を実行します。タグを判断するかどうかの負荷と同様、または個別の関連性を有効にしを使用すると、新しいファイルのセットで作業を続けます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p118">You can then tag files and run a calculate operation. The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="d12a4-172">キャッチアップのセットを確認すると後の表示**関連\>トラック**遅れの取り戻しの結果を得る。</span><span class="sxs-lookup"><span data-stu-id="d12a4-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="d12a4-173">関連のトレーニング中に新しいファイルの負荷を追加した場合 (つまり、問題がまだ完了していないバッチ計算によって)、**継続トレーニング**は、キャッチアップの結果に関係なく、次の手順。</span><span class="sxs-lookup"><span data-stu-id="d12a4-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="d12a4-p119">新しいと以前の荷重は、1 つの荷重として処理され、米国の一連の関連性の高いトレーニングを継続します。これではこの手順を完了し、関連性の高いトレーニングを続けることができます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p119">The new and previous loads are processed as one load and Relevance training continues on the united set. You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="d12a4-176">バッチ計算後新しい負荷を追加した場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="d12a4-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="d12a4-177">バッチ計算の後に追加、新しい荷重のかどうかは新しい負荷がかかっているかのような以前のロードとは異なる次のように高度な電子的証拠開示を決定します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="d12a4-p120">ように荷重が検出された場合: その他の関連性の高いトレーニングの必要はありません。ダッシュ ボードを実行するのには、推奨される次の手順を示しています * * バッチ計算 * * 新しい荷重の関連性スコアを計算するには、もう一度。同様に、新しいファイルの以前の分類子の解析を実行するために荷重が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p120">If loads were found to be similar: No additional Relevance training is necessary. The dashboard shows the recommended next step is to run ** Batch calculation ** again to calculate Relevance scores for the new load. Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="d12a4-p121">される負荷が検出された場合: 複数の関連性のトレーニングが必要な次の手順では、意思決定の遅れの取り戻しです。キャッチアップの意思決定を次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p121">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision. Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="d12a4-p122">**荷重をマージ**を選択すると、高度な電子的証拠開示は、トレーニング セットの以前のバージョンと新規の荷重をマージします。最初の読み込みは、バッチ計算を使用した、複数のトレーニングが必要です。新しいと以前のロードを一緒にトレーニングを継続します。バッチ計算がもう一度実行して、以前のバッチ計算スコアを無視する必要があります。既存の荷重の妥当性の度合いを再計算できます、たとえば、既存のファイル読み込みの確認が開始されていない場合に、この選択範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p122">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set. Although the first load went through Batch calculation, more training is needed. Continue training new and previous loads together. Batch calculation will then run again and the previous Batch calculation scores should be ignored. Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="d12a4-p123">**分割読み込み**を選択した場合は、新しいロードにのみ関連性の高いトレーニングを続行します。この場合、バッチ計算の前のスコアはそのままです。既存の荷重のレビューが既に開始されている場合と、既存の荷重の既存の関連性スコアを再計算できません、たとえば、このオプションを選択します。関連性スコアは、ここから先は個別に管理され、マージすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d12a4-p123">If you select **Split loads**, continue Relevance training only on the new load. In this instance, previous Batch calculation scores will remain as is. Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started. Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="d12a4-192">**トレーニングの続行**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d12a4-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d12a4-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="d12a4-193">See also</span></span>

[<span data-ttu-id="d12a4-194">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d12a4-194">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d12a4-195">問題を定義し、ユーザーの割り当て</span><span class="sxs-lookup"><span data-stu-id="d12a4-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="d12a4-196">定義するキーワードを強調表示され、高度なオプション</span><span class="sxs-lookup"><span data-stu-id="d12a4-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

