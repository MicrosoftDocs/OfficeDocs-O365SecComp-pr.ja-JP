---
title: Office 365 の高度な電子情報開示でのエクスプレス分析の使用
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Office 365 Advanced eDiscovery の簡易分析モードを実行する方法について説明します。
ms.openlocfilehash: d8457587c9c1a1237ddc076ce803a46382a04ed8
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000960"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="70af5-103">Office 365 の高度な電子情報開示でのエクスプレス分析の使用</span><span class="sxs-lookup"><span data-stu-id="70af5-103">Use Express Analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="70af5-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="70af5-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="70af5-106">**エクスプレス分析**を使用して、ケースを迅速に分析し、結果をエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="70af5-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="70af5-107">エクスプレス分析を使用して、ほぼ重複したスレッドや電子メールのスレッドを計算し、テーマを計算することができます。</span><span class="sxs-lookup"><span data-stu-id="70af5-107">You can use express analysis to calculate near-duplicates and email threads and calculate themes.</span></span> <span data-ttu-id="70af5-108">また、[エクスプレス分析の詳細設定](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)で、テーマ、ドキュメントの類似性、およびエクスポートファイルの特定のパラメーターを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="70af5-108">You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="70af5-109">エクスプレス分析を実行する</span><span class="sxs-lookup"><span data-stu-id="70af5-109">Run Express analysis</span></span>

1. <span data-ttu-id="70af5-110">[**エクスプレス分析**(1)] タブで、[\* \* エクスプレス分析 \* \* (2)] と **[詳細設定**] ボタンを有効にするコンテナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="70af5-110">In the **Express analysis** (1) tab, select a container to enable the \*\* Express analysis \*\* (2), and **Advanced settings** buttons.</span></span> 
    
    ![[エクスプレス分析] ページのスクリーンショット](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="70af5-112">[**パラメーターの分析**]:</span><span class="sxs-lookup"><span data-stu-id="70af5-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="70af5-113">分析を実行する場合は、 **[重複した場合と電子メールスレッドを計算**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="70af5-113">Check **Calculate near-duplicates and email threads** if you want to run the analysis.</span></span> <span data-ttu-id="70af5-114">既定では選択されています。</span><span class="sxs-lookup"><span data-stu-id="70af5-114">It is selected by default.</span></span> 
    
  - <span data-ttu-id="70af5-115">すべてのファイルを処理してテーマを割り当てるには、[**テーマの計算**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="70af5-115">Check **Calculate Themes** to process all files and assign themes to them.</span></span> <span data-ttu-id="70af5-116">既定では選択されています。</span><span class="sxs-lookup"><span data-stu-id="70af5-116">It is selected by default.</span></span> 
    
3. <span data-ttu-id="70af5-117">[**エクスポート先**] の下:</span><span class="sxs-lookup"><span data-stu-id="70af5-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="70af5-118">ローカルコンピューターにダウンロードするには、[**ローカルコンピューターにダウンロード**するをオンにします。</span><span class="sxs-lookup"><span data-stu-id="70af5-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="70af5-119">[**ユーザー定義の Azure blob へのエクスポート**] チェックボックスをオンにすると、コンテナー URL と SAS トークンを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="70af5-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="70af5-120">エクスポートパッケージがユーザーによって定義された Azure blob に保存されると、そのデータは Advanced 電子情報開示によって管理されなくなります。</span><span class="sxs-lookup"><span data-stu-id="70af5-120">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery.</span></span> <span data-ttu-id="70af5-121">Azure blob によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="70af5-121">it is managed by the Azure blob.</span></span> <span data-ttu-id="70af5-122">つまり、ケースを削除しても、エクスポートされたファイルは Azure blob に残ります。</span><span class="sxs-lookup"><span data-stu-id="70af5-122">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="70af5-123">**将来のエクスポートセッション用に sas トークンを保存**する: オンにすると、今後の使用のために、sas トークンが高度な電子情報開示の内部データベースで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="70af5-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="70af5-124">現在、SAS トークンは月後に有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="70af5-124">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="70af5-125">1か月以上後にダウンロードしようとした場合は、前回のセッションを取り消す必要があります。その後、再度エクスポートします。</span><span class="sxs-lookup"><span data-stu-id="70af5-125">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="70af5-126">既定の設定でエクスプレス分析を開始するには、[**エクスプレス分析**] を選択し、[**タスクの状態**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70af5-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="70af5-127">[**タスクの状態**] ページでは、**プロセス**を展開したり、タブを**分析**および**エクスポート**して、エクスプレス実行に関する詳細を表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="70af5-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![高度な電子情報開示エクスプレス分析タスクの状態ページのスクリーンショット](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="70af5-129">[**エクスプレス分析の概要**] ページを選択して、実行に関する詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="70af5-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="70af5-130">[**エクスプレス分析の概要**] ページの下部にある [ **last session のダウンロード**] を選択して、ローカルコンピューターの分析ファイル tp をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="70af5-130">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer.</span></span> <span data-ttu-id="70af5-131">まず、電子情報開示エクスポートツールをダウンロードし、そのエクスポートキーを電子情報開示エクスポートツールに貼り付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="70af5-131">You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="70af5-132">エクスプレス分析の高度な設定</span><span class="sxs-lookup"><span data-stu-id="70af5-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="70af5-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="70af5-133"></span></span>

<span data-ttu-id="70af5-134">オプションで、 **[詳細設定**] を設定して、既定のエクスプレス分析パラメーターを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="70af5-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="70af5-135">[**分析**] セクションで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="70af5-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="70af5-136">[**重複した複製] と [電子メール] スレッド**で、**ドキュメントの類似性**値を入力するか、既定値の 65% をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="70af5-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="70af5-137">[**テーマの最大数**] で、作成するテーマの数の値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="70af5-137">In the **Max number of themes** enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="70af5-138">既定値は 200 です。</span><span class="sxs-lookup"><span data-stu-id="70af5-138">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="70af5-139">テーマの数を増やすと、パフォーマンスに影響が及び、一般化するテーマの能力が向上します。</span><span class="sxs-lookup"><span data-stu-id="70af5-139">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="70af5-140">テーマの数が多いほど、より詳細なものになります。</span><span class="sxs-lookup"><span data-stu-id="70af5-140">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="70af5-141">たとえば、50テーマのセットに "バスケットボール、Spurs、Clippers、Lakers" などのテーマが含まれているとします。300テーマには、"Spurs"、"Clippers"、"Lakers" の各テーマが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="70af5-141">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="70af5-142">テーマ "バスケットボール" を認識していない場合に、ECA でこの機能を使用すると、"バスケットボール" というテーマが役に立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="70af5-142">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="70af5-143">しかし、処理に含まれているテーマの数が多すぎると、"バスケットボール" という単語は表示されず、Spurs と Clippers が、起動時に表示されて、ヘアサイトで使用されるアイテムではなく、確認が適切なバスケットボールテーマであることがわかりません。</span><span class="sxs-lookup"><span data-stu-id="70af5-143">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="70af5-144">提案された**テーマ**で、[**変更**] を選択してテーマの単語を提案し、テーマの処理を制御します。</span><span class="sxs-lookup"><span data-stu-id="70af5-144">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing.</span></span> <span data-ttu-id="70af5-145">高度な電子情報開示では、推奨される単語に焦点を絞り、"テーマの最大数" の設定に基づいて1つ以上の関連するテーマの作成を試みます。</span><span class="sxs-lookup"><span data-stu-id="70af5-145">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="70af5-146">たとえば、提案された単語が "computer" で、"2" が "テーマの最大数" として指定されている場合、上級電子情報開示では、"computer" という単語に関連する2つのテーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="70af5-146">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="70af5-147">この2つのテーマは、「コンピューターソフトウェア」と「コンピュータハードウェア」などです。</span><span class="sxs-lookup"><span data-stu-id="70af5-147">The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![提示されたテーマの追加](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="70af5-149">**モード**ドロップダウンリストから [**テーマ**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="70af5-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="70af5-150">**モデルの作成と適用**: モデルによって、ファイルのセグメントからテーマを計算し、それらの間でファイルを配布します。</span><span class="sxs-lookup"><span data-stu-id="70af5-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="70af5-151">**Create model**: ファイルのセグメントからテーマモデルを計算します。</span><span class="sxs-lookup"><span data-stu-id="70af5-151">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="70af5-152">ファイルを分割する処理は、別の時点で個別に実行されます。</span><span class="sxs-lookup"><span data-stu-id="70af5-152">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="70af5-153">[**モデルの適用**]: このオプションは、モデルが以前に作成され、まだ適用されていない場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="70af5-153">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="70af5-154">これにより、テーマに基づいてファイルが分割されます。</span><span class="sxs-lookup"><span data-stu-id="70af5-154">This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="70af5-155">[**エクスポート**] セクションで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="70af5-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="70af5-156">**[エクスポートバッチの選択]** で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="70af5-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="70af5-157">[バッチの**エクスポート**] ボックスの一覧で、バッチ名を選択するか、[エクスポートする結果をエクスポートする] (既定のバッチ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="70af5-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="70af5-158">既存のケースに追加した新しいファイルの結果をエクスポートするには、現在のバッチを続行します。</span><span class="sxs-lookup"><span data-stu-id="70af5-158">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="70af5-159">バッチにセッションを作成するには、同じバッチ番号を選択し、[**エクスポートセッションの作成**] をクリックします。このオプションを使用すると、前のバッチと同じパラメーターを増分方式でエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="70af5-159">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="70af5-160">新しいバッチにエクスポートするには、 \*\*\*\* ![[追加]](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)アイコンをクリックし、**バッチ名**に新しい名前を入力します (または既定値をそのまま使用します)。または、バッチの**説明**に説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="70af5-160">To export to a new batch, click **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="70af5-161">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70af5-161">Click **OK**.</span></span>
    
  - <span data-ttu-id="70af5-162">バッチ名または説明を編集するには、[**バッチのエクスポート**] \*\*\*\* ![で名前を](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)選択し、[編集] 編集アイコンをクリックしてから、フィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="70af5-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="70af5-163">エクスポートバッチのセッションを実行した後は、それらを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="70af5-163">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="70af5-164">また、最初のセッションを実行すると、一部のパラメーターのみを編集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="70af5-164">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="70af5-165">重複したエクスポートバッチを作成するには、[**重複** ![したエクスポートバッチ](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)の作成] アイコンを選択し、重複したバッチの名前と説明をパネルに入力します。</span><span class="sxs-lookup"><span data-stu-id="70af5-165">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="70af5-166">エクスポートバッチを削除するには、[ **delete** ![delete a export](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)batch] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="70af5-166">To delete an export batch, choose **Delete** ![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="70af5-167">バッチの履歴を表示するには、[ **batch history** ![view history](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="70af5-167">To view the history of a batch, choose **Batch history** ![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="70af5-168">[Define p **opulation** ] で、[**関連性のカットオフスコアの上にあるファイルのみを含める**] を選択し、エクスポートバッチの設定を微調整する場合は [**エクスポートバッチの絞り込み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70af5-168">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> <span data-ttu-id="70af5-169">[関連性のある**カットオフスコアに上記のファイルのみを含める**] を選択すると、**問題**が有効になり、ファイルの関連性スコアが選択した問題のカットオフスコアよりも高い場合、ファイルがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="70af5-169">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported.</span></span> <span data-ttu-id="70af5-170">このファイルは、' **For review**フィルターによって除外されていない限り、エクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="70af5-170">The file will be exported unless it's excluded by the ' **For review** filter.</span></span> <span data-ttu-id="70af5-171">[**エクスポートバッチの絞り込み**] を選択した場合は、[**重複除外**] および [[**レビュー用にフィルターを適用] フィールド**のラジオボタンが有効になります。</span><span class="sxs-lookup"><span data-stu-id="70af5-171">If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled.</span></span> <span data-ttu-id="70af5-172">**重複除外**を選択した場合は、定義されたポリシーに従って、重複ファイルがフィルター処理されます。 [case level (既定)]: 大文字と小文字を区別しない場合は、1つのファイルがすべて duped になります。</span><span class="sxs-lookup"><span data-stu-id="70af5-172">If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="70af5-173">保管担当者 level: 同じ保管担当者の重複ファイルのすべてのセットから、1つのファイル以外はすべて duped になります。</span><span class="sxs-lookup"><span data-stu-id="70af5-173">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.</span></span> <span data-ttu-id="70af5-174">すべての重複ファイルのレコードをエクスポート出力で使用できます。</span><span class="sxs-lookup"><span data-stu-id="70af5-174">A record of all duplicate files is available in export output.</span></span> <span data-ttu-id="70af5-175">[**レビュー用に ' フィルターを適用 '** ] フィールドを選択する場合は、[**メタデータ] の下の [変更**] を選択して、[**レビュー用**] フィールド設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="70af5-175">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="70af5-176">[**入力ファイルを含める**] を選択して、パッケージコンテンツにソースファイルを含めます。</span><span class="sxs-lookup"><span data-stu-id="70af5-176">Select **Include input files**to include source files in the package content.</span></span> <span data-ttu-id="70af5-177">このオプションは、エクスポートプロセスを高速化するためにオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="70af5-177">You can clear this option to speed up the export process.</span></span> <span data-ttu-id="70af5-178">ネイティブファイルは、どのような場合でもエクスポートされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="70af5-178">Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="70af5-179">[**メタデータの定義**] で、[テンプレートの**エクスポート**] ボックスの一覧から次のオプションを選択します (セッションごと)。</span><span class="sxs-lookup"><span data-stu-id="70af5-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="70af5-180">**標準**: データ項目、メタデータ、およびプロパティの基本的なセット。</span><span class="sxs-lookup"><span data-stu-id="70af5-180">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="70af5-181">このオプションは、上級電子情報開示で既にインポートデータが処理されており、エクスポートデータが既にファイルが含まれているシステムにアップロードされている場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="70af5-181">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="70af5-182">既定では、エクスポートテンプレート列が作成され、入力されます。</span><span class="sxs-lookup"><span data-stu-id="70af5-182">By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="70af5-183">**all**: すべての処理データを含む標準メタデータの完全なセットと、分析と関連性のスコア。</span><span class="sxs-lookup"><span data-stu-id="70af5-183">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="70af5-184">このテンプレートは、Advanced eDiscovery が処理を実行し、ファイルデータが外部システムに初めてアップロードされるときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="70af5-184">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="70af5-185">**問題**:**すべての問題**を選択するか、作成した特定の問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="70af5-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="70af5-186">[ **OK]** を選択して詳細設定を保存するか、既定値を使用するように既定値を**復元**するか、[**キャンセル**] をクリックして詳細設定の設定を取り消します。</span><span class="sxs-lookup"><span data-stu-id="70af5-186">Choose **OK**to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="70af5-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="70af5-187">See also</span></span>
<span data-ttu-id="70af5-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="70af5-188"></span></span>

[<span data-ttu-id="70af5-189">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="70af5-189">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)

