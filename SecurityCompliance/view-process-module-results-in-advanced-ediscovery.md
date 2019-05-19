---
title: Office 365 のプロセスモジュールの結果の表示の詳細電子情報開示
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 'タスクの状態とプロセスの概要を含む、Office 365 のアドバンスト eDiscovery でのプロセスモジュールの実行結果を確認する方法について説明します。  '
ms.openlocfilehash: 4bbdbf68f71e3459ff2ddcd8ba3fb33e52f16825
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157799"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="78255-103">Office 365 のプロセスモジュールの結果の表示の詳細電子情報開示</span><span class="sxs-lookup"><span data-stu-id="78255-103">View Process module results in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="78255-104">**準備** \> **プロセス**が開始されると、進行状況と結果を表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="78255-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="78255-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="78255-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="78255-107">タスクの進捗状況を処理する</span><span class="sxs-lookup"><span data-stu-id="78255-107">Process task status</span></span>

<span data-ttu-id="78255-108">[ \*\*\*\* \> \*\*\*\* 処理\> \*\*\*\* の準備] で、次の例に示すように、ページに現在の状態 (プロセスが実行中の場合) または最後のプロセスの状態タスクの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78255-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![プロセス モジュールのタスクの進捗状況](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="78255-110">表示されるタスクは、選択された [処理] オプションによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="78255-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="78255-111">**インベントリ**: Advanced eDiscovery は、プロセスに対して選択されたすべてのファイルを反復処理し、基本的なデータ収集を実行します。</span><span class="sxs-lookup"><span data-stu-id="78255-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="78255-112">**署名の計算**: MD5 デジタル署名を計算します。</span><span class="sxs-lookup"><span data-stu-id="78255-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="78255-113">**複合語抽出**: 内部または含まれているファイルを複合ファイル (PST、ZIP、MSG など) から抽出します。</span><span class="sxs-lookup"><span data-stu-id="78255-113">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG).</span></span> <span data-ttu-id="78255-114">抽出したファイルは、ケースの case フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="78255-114">Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="78255-115">**データベースの同期**: 内部データベースプロセス。</span><span class="sxs-lookup"><span data-stu-id="78255-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="78255-116">**ファイルコピー**: プロセスファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="78255-116">**File copy**: Copies Process files.</span></span> <span data-ttu-id="78255-117">[ファイルの詳細コピー] オプションが選択されている場合でも、このタスクは常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="78255-117">This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="78255-118">**テキストの抽出**: ネイティブファイルがある場合、Advanced EDiscovery は dtsearch を使用してこれらのファイルからテキストを抽出します。</span><span class="sxs-lookup"><span data-stu-id="78255-118">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch.</span></span> <span data-ttu-id="78255-119">これらのファイルの抽出テキストは、テキストファイルとして case フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="78255-119">The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="78255-120">**メタデータの更新**: 読み込まれたメタデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="78255-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="78255-121">**最終**処理: 読み込まれたケースファイルのデータを終了する内部処理 (たとえば、エラーおよび成功ファイルを識別する)。</span><span class="sxs-lookup"><span data-stu-id="78255-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="78255-122">タスクの進捗状況: タスクの完了後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="78255-122">Task status: Displayed after task completion.</span></span> <span data-ttu-id="78255-123">タスクの実行中は、実行期間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78255-123">While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78255-124">完了したタスクには、処理を完了したファイルやエラーが発生したファイルの合計も含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="78255-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="78255-125">[キャンセル] は、プロセスの実行を停止し、前のデータ作成または保存した処理済みデータにロールバックするためのロールバックオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="78255-125">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data.</span></span> <span data-ttu-id="78255-126">Rollback は、処理されたすべてのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="78255-126">Rollback clears all processed data.</span></span> <span data-ttu-id="78255-127">処理されたデータが失われることがないようにする場合 (たとえば、これらのファイルの再読み込みを計画している場合) は、このウィンドウで [キャンセル] オプションを選択して、ロールバックしないことを選択します。</span><span class="sxs-lookup"><span data-stu-id="78255-127">If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="78255-128">プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="78255-128">Process summary</span></span>

<span data-ttu-id="78255-129">[ \>プロセス\>結果\>の処理の概要] で、読み込まれたファイルの結果の内訳が、正常なファイル処理とエラー結果に従って表示されます。</span><span class="sxs-lookup"><span data-stu-id="78255-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="78255-130">ペインは、次のように、インポートされたファイル統計をグラフィカルに表示します。</span><span class="sxs-lookup"><span data-stu-id="78255-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="78255-131">**プロセスの概要**d: すべてのファイル (ケース内) を蓄積します。</span><span class="sxs-lookup"><span data-stu-id="78255-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="78255-132">**プロセス概要 last**: 最後のセッションまたはアクションから読み込まれたファイル。</span><span class="sxs-lookup"><span data-stu-id="78255-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="78255-133">**姓**: 大文字と小文字のファミリ情報 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="78255-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="78255-134">**Seed**ファイルが追加された場合、ファイルに対して定義された問題ごとにシードファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78255-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="78255-135">**シード**ファイルのマーキングが失敗した場合は、それも記録されます。</span><span class="sxs-lookup"><span data-stu-id="78255-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="78255-136">**プリタグ付き**ファイルが追加された場合は、ファイルに対して定義された問題ごとに、タグ付きファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78255-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="78255-137">**タグ付け**されたファイルのマーキングが失敗した場合は、それも記録されます。</span><span class="sxs-lookup"><span data-stu-id="78255-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![プロセス モジュールの概要](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="78255-139">プロセス概要累計および最終グラフ</span><span class="sxs-lookup"><span data-stu-id="78255-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="78255-140">左側のバーには、ソースと抽出ファイルが含まれています。すべてのファイルが見つかります。</span><span class="sxs-lookup"><span data-stu-id="78255-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="78255-141">次のものが含まれている右のバー。</span><span class="sxs-lookup"><span data-stu-id="78255-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="78255-142">読み込みエラーが発生したファイル</span><span class="sxs-lookup"><span data-stu-id="78255-142">Files with load errors</span></span>
    
- <span data-ttu-id="78255-143">正常に読み込まれたファイル: 次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="78255-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="78255-144">**既存**: 以前に読み込まれ、後で読み込まれたファイル (重複を含む)。</span><span class="sxs-lookup"><span data-stu-id="78255-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="78255-145">**テキスト**: テキストを含む一意のファイル。</span><span class="sxs-lookup"><span data-stu-id="78255-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="78255-146">**テキスト以外**: 空のテキストファイル、空のネイティブテキストファイル、ネイティブの非テキストファイル。</span><span class="sxs-lookup"><span data-stu-id="78255-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="78255-147">**複製**s: ファイルがテキストと重複しています。</span><span class="sxs-lookup"><span data-stu-id="78255-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="78255-148">最後の処理エラー</span><span class="sxs-lookup"><span data-stu-id="78255-148">Last process errors</span></span>

<span data-ttu-id="78255-149">[ \>処理\>結果\>の最終処理] エラーでは、最後に実行されたセッションまたはアクションのエラーの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78255-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![プロセス モジュールのエラー](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="78255-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="78255-151">See also</span></span>

[<span data-ttu-id="78255-152">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="78255-152">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="78255-153">プロセスモジュールの実行とデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="78255-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

