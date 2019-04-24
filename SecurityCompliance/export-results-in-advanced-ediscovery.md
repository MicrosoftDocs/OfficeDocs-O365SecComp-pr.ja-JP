---
title: Office の結果をエクスポートする 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: 'Office 365 Advanced eDiscovery の結果をエクスポートするためのオプションを定義する方法について説明します。これには、エクスポートバッチのパラメーターを指定する手順が含まれます。 '
ms.openlocfilehash: a2528c3eab0bc9c06a592b972a3bc602174458d3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255851"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="771a9-103">Office の結果をエクスポートする 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="771a9-103">Export results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="771a9-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="771a9-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="771a9-106">このトピックでは、高度な電子情報開示のエクスポートのセットアップオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="771a9-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="771a9-107">**このトピックの内容**</span><span class="sxs-lookup"><span data-stu-id="771a9-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="771a9-108">エクスポートバッチとセッションの定義</span><span class="sxs-lookup"><span data-stu-id="771a9-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="771a9-109">増分および追加のエクスポート</span><span class="sxs-lookup"><span data-stu-id="771a9-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="771a9-110">バッチエクスポートパラメーターの設定</span><span class="sxs-lookup"><span data-stu-id="771a9-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="771a9-111">レポート出力ファイルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="771a9-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="771a9-112">エクスポートバッチとセッションの定義</span><span class="sxs-lookup"><span data-stu-id="771a9-112">Defining export batches and sessions</span></span>
<span data-ttu-id="771a9-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="771a9-113"></span></span>

<span data-ttu-id="771a9-114">エクスポートバッチでは、一連の定義済みパラメーターを使用して、エクスポート処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="771a9-114">An export batch allows export processing using a set of defined parameters.</span></span> <span data-ttu-id="771a9-115">上級電子情報開示を使用すると、各エクスポートをカスタマイズするためのバッチを定義できます。</span><span class="sxs-lookup"><span data-stu-id="771a9-115">Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="771a9-116">パラメーターは、エクスポートバッチごとに定義されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-116">Parameters are defined per export batch.</span></span> <span data-ttu-id="771a9-117">"Export batch 01" という名前のバッチは、ケースの最初のバッチに対して既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-117">A batch named "Export batch 01" is created by default for the first batch of a case.</span></span> <span data-ttu-id="771a9-118">バッチ名と説明を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="771a9-118">You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="771a9-119">エクスポートセッションは、エクスポートバッチ内での高度な電子情報開示のエクスポートの実行です。</span><span class="sxs-lookup"><span data-stu-id="771a9-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="771a9-120">増分および追加のエクスポート</span><span class="sxs-lookup"><span data-stu-id="771a9-120">Incremental and additional exports</span></span>
<span data-ttu-id="771a9-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="771a9-121"></span></span>

<span data-ttu-id="771a9-122">同じエクスポートテンプレートとパラメーターに基づいて一貫性のある結果を得るために、エクスポートバッチ内で複数のエクスポートセッションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="771a9-122">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters.</span></span> <span data-ttu-id="771a9-123">バッチ内の各セッションに対して、新しく処理されたケースデータの分析をエクスポートし、各 "増分" 処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="771a9-123">For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="771a9-124">別のパラメーターセットを使用してエクスポートするには、まず新しいバッチを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="771a9-124">In order to export using a different set of parameters, you first need to create a new batch.</span></span> <span data-ttu-id="771a9-125">新しいバッチの最初のセッションは、これまでに処理されたファイルに対して、1つまたは複数のインポートでこれらのファイルがインポートされて処理されたかどうかについての結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="771a9-125">The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports.</span></span> <span data-ttu-id="771a9-126">各バッチは、ピボット、類似性、inclusives などを再計算します。セッションでは、バッチに対して定義されているパラメーターを使用します。また、各セッションの実行に対して、ピボット、類似性、inclusives などを再計算しません。</span><span class="sxs-lookup"><span data-stu-id="771a9-126">Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="771a9-127">たとえば、ケースがインポートされ、そのデータが分析されたとします。</span><span class="sxs-lookup"><span data-stu-id="771a9-127">For example, assume a case was imported and its data analyzed.</span></span> <span data-ttu-id="771a9-128">増分データについて、ほぼ重複および電子メールのスレッド結果を取得するには、以前にデータのエクスポートに使用したのと同じバッチで [**エクスポートセッションを作成**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="771a9-128">In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="771a9-129">バッチエクスポートパラメーターの設定</span><span class="sxs-lookup"><span data-stu-id="771a9-129">Set up batch export parameters</span></span>
<span data-ttu-id="771a9-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="771a9-130"></span></span>

<span data-ttu-id="771a9-131">電子情報開示エクスポートツールは、アドバンスト ediscovery からローカルコンピューターに検索結果をエクスポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-131">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer.</span></span> <span data-ttu-id="771a9-132">データ転送のスループットを向上させ、エクスポートプロセスを高速化するために、検索結果のエクスポートに使用するコンピューターで Windows レジストリ設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="771a9-132">To increase the data transfer throughput and speed-up the export process, you can configure a Windows Registry setting on the computer that you use to export the search results.</span></span> <span data-ttu-id="771a9-133">ダウンロード速度を上げる場合は、エクスポートパラメーターを設定する前にレジストリ設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="771a9-133">If you'd like to increase the download speed, configure the registry setting before you set up the export parameters.</span></span> <span data-ttu-id="771a9-134">詳細については、「 [Office の電子情報開示検索結果をエクスポートするときにダウンロード速度を上げる 365](increase-download-speeds-when-exporting-ediscovery-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="771a9-134">For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="771a9-135">[高度な電子情報開示] で、ケースを選択し、[**セットアップ**の**エクスポート** \> ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="771a9-135">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
    - <span data-ttu-id="771a9-136">[バッチの**エクスポート**] ボックスの一覧で、バッチ名を選択するか、[エクスポートする結果をエクスポートする] (既定のバッチ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="771a9-136">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
    - <span data-ttu-id="771a9-137">既存のケースに追加した新しいファイルの結果をエクスポートするには、現在のバッチを続行します。</span><span class="sxs-lookup"><span data-stu-id="771a9-137">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="771a9-138">バッチにセッションを作成するには、同じバッチ番号を選択し、[**エクスポートセッションの作成**] をクリックします。このオプションを使用すると、前のバッチと同じパラメーターを増分方式でエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="771a9-138">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
    - <span data-ttu-id="771a9-139">新しいバッチにエクスポートするには、 \*\*\*\* ![[追加]](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)アイコンをクリックし、**バッチ名**に新しい名前を入力します (または既定値をそのまま使用します)。または、バッチの**説明**に説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="771a9-139">To export to a new batch, click **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="771a9-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="771a9-140">Click **OK**.</span></span>
    
    - <span data-ttu-id="771a9-141">バッチ名または説明を編集するには、[**バッチのエクスポート**] \*\*\*\* ![で名前を](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)選択し、[編集] 編集アイコンをクリックしてから、フィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="771a9-141">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="771a9-142">エクスポートバッチのセッションを実行した後は、それらを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="771a9-142">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="771a9-143">また、最初のセッションを実行すると、一部のパラメーターのみを編集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="771a9-143">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
    - <span data-ttu-id="771a9-144">重複したエクスポートバッチを作成するには、[**重複** ![したエクスポートバッチ](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)の作成] アイコンを選択し、重複したバッチの名前と説明をパネルに入力します。</span><span class="sxs-lookup"><span data-stu-id="771a9-144">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
    - <span data-ttu-id="771a9-145">エクスポートバッチを削除するには、[ **delete** ![delete a export](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)batch] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="771a9-145">To delete an export batch, choose **Delete** ![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
    - <span data-ttu-id="771a9-146">バッチの履歴を表示するには、[ **batch history** ![view history](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="771a9-146">To view the history of a batch, choose **Batch history** ![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="771a9-147">[**母集団**] で、[関連性のある**カットオフスコアの上にファイルのみを含める**] を選択し、エクスポートバッチの設定を微調整する場合は [**エクスポートバッチの絞り込み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="771a9-147">Under **Population**, select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="771a9-148">[**関連性カットオフスコアに上記のファイルのみを含める**] を選択すると、その**問題**は有効になります。</span><span class="sxs-lookup"><span data-stu-id="771a9-148">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled.</span></span> <span data-ttu-id="771a9-149">ファイルの関連性スコアが選択した問題のカットオフスコアよりも大きい場合、ファイルは ' for review ' フィルターで除外されない限り、エクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="771a9-149">If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
    <span data-ttu-id="771a9-150">[**エクスポートバッチの絞り込み**] を選択した場合は、[**重複除外**] および [[レビュー用にフィルターを適用] フィールドのラジオボタンが有効になります。</span><span class="sxs-lookup"><span data-stu-id="771a9-150">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled.</span></span> <span data-ttu-id="771a9-151">重複**除外**を選択すると、重複したファイルは、定義されたポリシーに従ってフィルターで除外されます。大文字と小文字を区別しない場合は、1つのファイルのすべてのセットに対して duped が実行されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-151">If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="771a9-152">保管担当者 level: 同じ保管担当者の重複ファイルのすべてのセットから、1つのファイル以外はすべて duped になります。]エクスポート出力には、すべての重複ファイルのレコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="771a9-152">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files.</span></span> <span data-ttu-id="771a9-153">[**レビュー用に ' フィルターを適用 '** ] フィールドを選択する場合は、[**メタデータ] の下の [変更**] を選択して、[**レビュー用**] フィールド設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="771a9-153">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="771a9-154">[**入力ファイルを含める**] を選択して、パッケージコンテンツにソースファイルを含めます。</span><span class="sxs-lookup"><span data-stu-id="771a9-154">Select **Include input files** to include source files in the package content.</span></span> <span data-ttu-id="771a9-155">この設定をオフにして、エクスポート処理を高速化することができます。</span><span class="sxs-lookup"><span data-stu-id="771a9-155">You can clear this setting to speed up the export process.</span></span> <span data-ttu-id="771a9-156">ネイティブファイルは、どのような場合でもエクスポートされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="771a9-156">Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="771a9-157">[**メタデータ**] で、[**テンプレートのエクスポート**] ボックスの一覧から次のオプションを選択します (セッションごと)。</span><span class="sxs-lookup"><span data-stu-id="771a9-157">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
    - <span data-ttu-id="771a9-158">**標準**: データ項目、メタデータ、およびプロパティの基本的なセット。</span><span class="sxs-lookup"><span data-stu-id="771a9-158">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="771a9-159">このオプションは、上級電子情報開示で既にインポートデータが処理されており、エクスポートデータが既にファイルが含まれているシステムにアップロードされている場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="771a9-159">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="771a9-160">既定では、エクスポートテンプレート列が作成され、入力されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-160">By default, export template columns are created and filled.</span></span>
    
    - <span data-ttu-id="771a9-161">**all**: すべての処理データを含む標準メタデータの完全なセットと、分析と関連性のスコア。</span><span class="sxs-lookup"><span data-stu-id="771a9-161">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="771a9-162">このテンプレートは、Advanced eDiscovery が処理を実行し、ファイルデータが外部システムに初めてアップロードされるときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="771a9-162">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
    - <span data-ttu-id="771a9-163">**問題**:**すべての問題**を選択するか、作成した特定の問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="771a9-163">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="771a9-164">[**宛先**] の下:</span><span class="sxs-lookup"><span data-stu-id="771a9-164">Under **Destination**:</span></span>
    
    - <span data-ttu-id="771a9-165">**ローカルコンピューターへのダウンロード**</span><span class="sxs-lookup"><span data-stu-id="771a9-165">**Download to local machine**</span></span>
    
    - <span data-ttu-id="771a9-166">**ユーザー定義の Azure blob へのエクスポート**: これがチェックされている場合は、コンテナー URL と SAS トークンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="771a9-166">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="771a9-167">エクスポートパッケージがユーザーによって定義された Azure blob に保存されると、そのデータは Advanced 電子情報開示によって管理されなくなります。Azure blob によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-167">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob.</span></span> <span data-ttu-id="771a9-168">つまり、ケースを削除しても、エクスポートされたファイルは Azure blob に残ります。</span><span class="sxs-lookup"><span data-stu-id="771a9-168">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
    - <span data-ttu-id="771a9-169">**将来のエクスポートセッション用に sas トークンを保存**する: オンにすると、今後の使用のために、sas トークンが高度な電子情報開示の内部データベースで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-169">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="771a9-170">現在、SAS トークンは月後に有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="771a9-170">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="771a9-171">1か月以上後にダウンロードしようとした場合は、前回のセッションを取り消す必要があります。その後、再度エクスポートします。</span><span class="sxs-lookup"><span data-stu-id="771a9-171">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="771a9-172">[**変更**] をクリックして [レビュー用] フィールド設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="771a9-172">Click **Modify** to set the 'for review' field settings.</span></span> 
    
    ![エクスポートバッチのレビューフィールドの設定を設定する](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - <span data-ttu-id="771a9-174">[**レビューするフィールドの設定] の**[**シナリオの選択**] プルダウンリストで、レビューのシナリオと範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="771a9-174">Under **For review field settings**, in **Select scenario** pull-down list, select the scenario and scope of the review.</span></span> <span data-ttu-id="771a9-175">設定は、選択内容に基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-175">The settings are displayed based on your selection.</span></span>
    
      - <span data-ttu-id="771a9-176">**すべて確認**(既定値): すべてのメール、添付ファイル、およびドキュメントが既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="771a9-176">**Review all** (default): All emails, attachments, and documents are selected by default.</span></span> 
    
      - <span data-ttu-id="771a9-177">**セット内のすべての固有のコンテンツを確認**します。 Inclusives と一意の包括的コピー、電子メールセットレベルの一意の添付ファイル、すべての正確な複製のセットに関する担当者。</span><span class="sxs-lookup"><span data-stu-id="771a9-177">**Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="771a9-178">**セット内のすべての固有のコンテンツを確認します。包括的なコピーはありません**: Inclusives、電子メールセットレベルの一意の添付ファイル、完全に重複したすべてのセットからの担当者。</span><span class="sxs-lookup"><span data-stu-id="771a9-178">**Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="771a9-179">**すべての固有のコンテンツと関連するファミリーファイルを確認**します。 Inclusives、電子メールセットレベルの一意な添付ファイル、完全に重複したすべてのセットについては、「family ファイルを含める」に展開します。</span><span class="sxs-lookup"><span data-stu-id="771a9-179">**Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.</span></span>
    
      - <span data-ttu-id="771a9-180">**ユーザー設定**(ダイアログでオプションを定義することができます)。既定では、現在の選択を保持し、すべてのダイアログオプションを有効にして選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="771a9-180">**Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection.</span></span> <span data-ttu-id="771a9-181">このオプションを選択すると、電子メール、ドキュメント、添付ファイル、その他の設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="771a9-181">If you select this option, you can then customize the settings for emails, documents, attachments and miscellaneous.</span></span>
    
    - <span data-ttu-id="771a9-182">[**電子メール**] で、エクスポートするメールを選択します。</span><span class="sxs-lookup"><span data-stu-id="771a9-182">Under **Emails**, select the emails you want to export.</span></span>
    
      - <span data-ttu-id="771a9-183">**すべてのメール**: (既定) すべてのメールが選択されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-183">**All emails**: (default) All emails are selected.</span></span>
    
      - <span data-ttu-id="771a9-184">**Inclusives**: 包括的な電子メールは、スレッドの最後の電子メールで、スレッドからの他のすべてのメールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="771a9-184">**Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.</span></span>
    
      - <span data-ttu-id="771a9-185">**Inclusives と一意の包括的コピー**: 同じ件名、本文、添付ファイルを含む、包括的なコピーと Inclusives。一意の包括的コピーは、これらの電子メールの一意のコピーです。</span><span class="sxs-lookup"><span data-stu-id="771a9-185">**Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .</span></span>
    
    - <span data-ttu-id="771a9-186">[**ドキュメント**] で、エクスポートするドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="771a9-186">Under **Documents**, select the documents you want to export.</span></span> 
    
      - <span data-ttu-id="771a9-187">**すべてのドキュメント**: (既定) すべてのドキュメントが選択されています。</span><span class="sxs-lookup"><span data-stu-id="771a9-187">**All documents**: (default) All documents are selected.</span></span>
    
      - <span data-ttu-id="771a9-188">**ピボット**: ほぼ重複したセットの代理人として選択されたファイルです。これは、通常、セットをレビューするときにベースラインとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-188">**Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.</span></span>
    
      - <span data-ttu-id="771a9-189">**完全に重複するすべてのセットの担当者**: 一意の同一ファイル (ピボットを含む)。</span><span class="sxs-lookup"><span data-stu-id="771a9-189">**Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).</span></span>
    
    - <span data-ttu-id="771a9-190">[**添付ファイル**] で、エクスポートする添付ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="771a9-190">Under **Attachments**, select the attachments you want to export.</span></span> 
    
      - <span data-ttu-id="771a9-191">**すべての添付**ファイル: (既定) すべての添付ファイルが選択されています。</span><span class="sxs-lookup"><span data-stu-id="771a9-191">**All attachments**: (default) All attachments are selected.</span></span>
    
      - <span data-ttu-id="771a9-192">**ケースレベルの一意の添付**ファイル: 指定されたケース内の一意の添付ファイルファイル。</span><span class="sxs-lookup"><span data-stu-id="771a9-192">**Unique attachment in case level**: Unique attachment files within the specified case.</span></span>
    
      - <span data-ttu-id="771a9-193">**メールセットレベルの一意の添付**ファイル: 指定された電子メールケース内の一意の添付ファイルファイル。</span><span class="sxs-lookup"><span data-stu-id="771a9-193">**Unique attachment in email set level**: Unique attachment files within the specified email case.</span></span>
    
   - <span data-ttu-id="771a9-194">**Micellaneous**では、**添付ファイルをドキュメントとして**処理するか、**電子メールとして**処理するか、または**ファミリファイルを含める**ように拡張するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="771a9-194">Under**Micellaneous**, you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**.</span></span> <span data-ttu-id="771a9-195">[**ファミリファイルを含める] を**選択すると、確認のフラグが付けられた各ファイルに対して、同じファミリのすべてのファイルにフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-195">When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
7. <span data-ttu-id="771a9-196">[**保存**] を選択して設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="771a9-196">Choose **Save** to save the settings.</span></span> 
    
8. <span data-ttu-id="771a9-197">エクスポートパラメーターを指定した後、[バッチのエクスポート] を開始するには、[**エクスポートセッションの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="771a9-197">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="771a9-198">エクスポート中は、[**タスクの状態**] に状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-198">During export, the status is displayed in **Task status**.</span></span> <span data-ttu-id="771a9-199">結果が [エクスポートの**概要**] に表示されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-199">The results are displayed in **Export summary**.</span></span>
    
9. <span data-ttu-id="771a9-200">[**ファイルのダウンロード**] ウィンドウで、[**クリップボードにコピー** ] をクリックしてエクスポートキーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="771a9-200">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![ファイルをダウンロードする](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. <span data-ttu-id="771a9-202">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="771a9-202">Click **Close**.</span></span> 
    
    <span data-ttu-id="771a9-203">電子情報開示エクスポートツールが開始されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-203">The eDiscovery Export Tool is started.</span></span>
    
    ![電子情報開示のエクスポート ツール](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. <span data-ttu-id="771a9-205">**電子情報開示エクスポートツール**の場合:</span><span class="sxs-lookup"><span data-stu-id="771a9-205">In the **eDiscovery Export Tool**:</span></span>
    
    -  <span data-ttu-id="771a9-206">[**貼り付け元への接続に使用される共有アクセス署名**] で、手順7でクリップボードにコピーしたエクスポートキーを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="771a9-206">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that youcopied to the clipboard in step 7.</span></span>
    
    - <span data-ttu-id="771a9-207">[**参照**] をクリックして、ダウンロードしたエクスポートファイルをローカルコンピューターに保存するためのターゲットの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="771a9-207">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
    - <span data-ttu-id="771a9-208">[**開始**] をクリックします。エクスポートファイルがローカルコンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="771a9-208">Click **Start**.The export files are downloaded to the local machine.</span></span> <span data-ttu-id="771a9-209">手順4で [**ユーザー定義の Azure blob へのエクスポート**] を選択した場合、セッションは選択した blob ストレージ URL の送信先にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="771a9-209">If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span>
    
<span data-ttu-id="771a9-210">エクスポートレポートのフィールドの詳細については、「 [export report fields](export-report-fields-in-advanced-ediscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="771a9-210">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="771a9-211">レポート出力ファイルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="771a9-211">Export report output files</span></span>
<span data-ttu-id="771a9-212"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="771a9-212"></span></span>

<span data-ttu-id="771a9-213">次の表に、エクスポートバッチの実行時に生成される出力ファイルの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="771a9-213">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="771a9-214">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="771a9-214">**File name**</span></span>|<span data-ttu-id="771a9-215">**ファイルの種類**</span><span class="sxs-lookup"><span data-stu-id="771a9-215">**File type**</span></span>|<span data-ttu-id="771a9-216">**説明**</span><span class="sxs-lookup"><span data-stu-id="771a9-216">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="771a9-217">エクスポートの概要</span><span class="sxs-lookup"><span data-stu-id="771a9-217">Export summary</span></span>  <br/> |<span data-ttu-id="771a9-218">.csv</span><span class="sxs-lookup"><span data-stu-id="771a9-218">csv</span></span>  <br/> |<span data-ttu-id="771a9-219">電子情報開示エクスポートツールによって生成されたログファイル。</span><span class="sxs-lookup"><span data-stu-id="771a9-219">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="771a9-220">トレース</span><span class="sxs-lookup"><span data-stu-id="771a9-220">Trace</span></span>  <br/> |<span data-ttu-id="771a9-221">license.txt</span><span class="sxs-lookup"><span data-stu-id="771a9-221">txt</span></span>  <br/> |<span data-ttu-id="771a9-222">電子情報開示エクスポートツールによって生成されたログファイル。</span><span class="sxs-lookup"><span data-stu-id="771a9-222">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="771a9-223">抽出されたテキストファイル</span><span class="sxs-lookup"><span data-stu-id="771a9-223">Extracted text files</span></span>  <br/> |<span data-ttu-id="771a9-224">ファイルフォルダー</span><span class="sxs-lookup"><span data-stu-id="771a9-224">File folder</span></span>  <br/> |<span data-ttu-id="771a9-225">エクスポートされたファイルの抽出済みテキストファイルを含むフォルダー。</span><span class="sxs-lookup"><span data-stu-id="771a9-225">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="771a9-226">入力ファイルまたはネイティブファイル</span><span class="sxs-lookup"><span data-stu-id="771a9-226">Input or native files</span></span>  <br/> |<span data-ttu-id="771a9-227">ファイルフォルダー</span><span class="sxs-lookup"><span data-stu-id="771a9-227">File folder</span></span>  <br/> |<span data-ttu-id="771a9-228">エクスポートされたファイルのネイティブファイルと入力ファイルを含むフォルダ。</span><span class="sxs-lookup"><span data-stu-id="771a9-228">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="771a9-229">リストのエクスポート</span><span class="sxs-lookup"><span data-stu-id="771a9-229">Export list</span></span>  <br/> |<span data-ttu-id="771a9-230">xlsx</span><span class="sxs-lookup"><span data-stu-id="771a9-230">xlsx</span></span>  <br/> |<span data-ttu-id="771a9-231">.xlsx 形式のエクスポートされたファイルのメタデータ。</span><span class="sxs-lookup"><span data-stu-id="771a9-231">Exported files metadata in xlsx format.</span></span> <span data-ttu-id="771a9-232">ファイル内のフィールドは、ユーザーが選択したエクスポート対象のテンプレートに基づいています。</span><span class="sxs-lookup"><span data-stu-id="771a9-232">Fields in files are according to template user selects to export.</span></span> <span data-ttu-id="771a9-233">必要に応じて、複数のファイルが作成されます。各ファイルには、それぞれ 100 150K の行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="771a9-233">If needed, several files are created, each contains 100-150K rows.</span></span> <span data-ttu-id="771a9-234">Excel のセルに含めることができる文字数 (現在の制限値は32767文字) よりも多くの文字が特定の値に含まれている場合、その値は許容される最大の長さにトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="771a9-234">If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed.</span></span> <span data-ttu-id="771a9-235">値がトリミングされている場合は、セルの背景色が赤になり、ユーザーに対して示されます。メールが大規模な配信に送信された場合、メールの参加者は、長さ制限を超える可能性のあるフィールドの例です。</span><span class="sxs-lookup"><span data-stu-id="771a9-235">If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution.</span></span> <span data-ttu-id="771a9-236">出力フィールドの詳細については、「[レポートフィールドをエクスポート](export-report-fields-in-advanced-ediscovery.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="771a9-236">See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.</span></span>  <br/> |
|<span data-ttu-id="771a9-237">ファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="771a9-237">Load file</span></span>  <br/> |<span data-ttu-id="771a9-238">.csv</span><span class="sxs-lookup"><span data-stu-id="771a9-238">csv</span></span>  <br/> |<span data-ttu-id="771a9-239">別のアプリケーションに読み込むための csv 形式のエクスポートされたファイルのメタデータ。</span><span class="sxs-lookup"><span data-stu-id="771a9-239">Exported files metadata in csv format for loading into a different application.</span></span> <span data-ttu-id="771a9-240">ファイル内のフィールドは、ユーザーが選択したエクスポート対象のテンプレートに基づいています。</span><span class="sxs-lookup"><span data-stu-id="771a9-240">Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="771a9-241">成功インジケーター</span><span class="sxs-lookup"><span data-stu-id="771a9-241">Success indicator</span></span>  <br/> |<span data-ttu-id="771a9-242">license.txt</span><span class="sxs-lookup"><span data-stu-id="771a9-242">txt</span></span>  <br/> |<span data-ttu-id="771a9-243">サードパーティの Azure blob へのエクスポート時にのみ作成されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-243">Only created when exporting to a 3rd party Azure blob.</span></span> <span data-ttu-id="771a9-244">エクスポートが完全に成功すると、ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="771a9-244">If export succeed completely, the file will be created.</span></span> <span data-ttu-id="771a9-245">エラーが発生した場合、または成功した場合、ファイルは作成されません。</span><span class="sxs-lookup"><span data-stu-id="771a9-245">In case of failure, or partial success the file will not be created.</span></span> <span data-ttu-id="771a9-246">ルートフォルダーにファイルが作成され、さまざまなエクスポートバッチ/セッションの状態での自動追跡が可能になります。</span><span class="sxs-lookup"><span data-stu-id="771a9-246">File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses.</span></span> <span data-ttu-id="771a9-247">これは空のファイルです。</span><span class="sxs-lookup"><span data-stu-id="771a9-247">This is an empty file.</span></span> <span data-ttu-id="771a9-248">その名前は: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime です。</span><span class="sxs-lookup"><span data-stu-id="771a9-248">Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="771a9-249">関連項目</span><span class="sxs-lookup"><span data-stu-id="771a9-249">See also</span></span>

[<span data-ttu-id="771a9-250">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="771a9-250">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="771a9-251">バッチ履歴の表示と過去の結果のエクスポート</span><span class="sxs-lookup"><span data-stu-id="771a9-251">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="771a9-252">Office 365 Advanced eDiscovery のクイック セットアップ</span><span class="sxs-lookup"><span data-stu-id="771a9-252">Quick setup for Office 365 Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="771a9-253">レポート フィールドのエクスポート</span><span class="sxs-lookup"><span data-stu-id="771a9-253">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
  
[<span data-ttu-id="771a9-254">Office 365 から電子情報開示検索の結果をエクスポートするときにダウンロード速度を上げる</span><span class="sxs-lookup"><span data-stu-id="771a9-254">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>](increase-download-speeds-when-exporting-ediscovery-results.md)

