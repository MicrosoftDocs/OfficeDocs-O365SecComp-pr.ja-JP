---
title: Office 365 Advanced eDiscovery のプロセス モジュールの結果を表示する
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 'プロセス モジュールの結果を Office 365 の高度な電子的証拠開示、タスクの進捗状況やプロセスの概要などの実行を確認する方法について説明します。  '
ms.openlocfilehash: 01093b0230aaf78ab7ccf1235f0874a0b69aa1bd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531564"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="e4a34-103">Office 365 Advanced eDiscovery のプロセス モジュールの結果を表示する</span><span class="sxs-lookup"><span data-stu-id="e4a34-103">View Process module results in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="e4a34-104">**準備**した後\>**プロセス**が開始される、進行状況と結果を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e4a34-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e4a34-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="e4a34-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="e4a34-107">プロセス タスクの進捗状況</span><span class="sxs-lookup"><span data-stu-id="e4a34-107">Process task status</span></span>

<span data-ttu-id="e4a34-108">**準備**」の\>**プロセス** \> **結果**ページを示しています (プロセスが現在実行されている) 場合は、現在の状態またはプロセスの状態タスクの最新のステータス例を次に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="e4a34-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![プロセス モジュールのタスクの進捗状況](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="e4a34-110">表示されているタスクは、選択した処理オプションによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4a34-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="e4a34-111">**在庫**: 高度な電子的証拠開示プロセス用に選択したすべてのファイルを反復処理し、基本的なデータ収集を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4a34-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="e4a34-112">**署名の計算**: MD5 のデジタル署名を計算します。</span><span class="sxs-lookup"><span data-stu-id="e4a34-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="e4a34-p102">**複合抽出**: 複合ファイル (PST、郵便番号のメッセージなど) から抽出の内部または含まれているファイルの再帰的にします。展開されたファイルは、大文字と小文字の大文字のフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e4a34-p102">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG). Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="e4a34-115">**同期データベース**: データベースの内部処理します。</span><span class="sxs-lookup"><span data-stu-id="e4a34-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="e4a34-p103">**ファイルのコピー**: ファイルのコピー処理します。コピー ファイルの詳細オプションを選択した場合でも、このタスクが常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a34-p103">**File copy**: Copies Process files. This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="e4a34-p104">**テキストの抽出**: ネイティブのファイルが存在する場合、高度な電子的証拠開示が DTSearch を使用してこれらのファイルからテキストを抽出します。これらのファイルの抽出されたテキストは、大文字のフォルダー内のテキスト ファイルとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="e4a34-p104">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch. The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="e4a34-120">**メタデータを更新**します。 読み込まれているメタデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="e4a34-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="e4a34-121">**Finalizing**: 内部処理のデータをファイナライズするに大文字のファイルが読み込まれます (たとえば、エラーと成功のファイルを識別します)。</span><span class="sxs-lookup"><span data-stu-id="e4a34-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="e4a34-p105">タスクの状態: タスクの完了後に表示されます。タスクの実行中は、実行の継続時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a34-p105">Task status: Displayed after task completion. While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4a34-124">完了したタスクは、ファイルの処理を完了またはエラーがあるファイルの合計もあります。</span><span class="sxs-lookup"><span data-stu-id="e4a34-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="e4a34-p106">[キャンセル]、ロールバック ・ プロセスの実行を停止し、前のデータの作成をロールバックするオプションが用意されていますか、処理されたデータを保存します。ロールバックでは、すべての処理済のデータをクリアします。場合はデータが失われること (たとえば、これらのファイルを再読み込みする予定)、ロール ・ バックしないように選択するのにはこのウィンドウでの選択]、[キャンセル] オプションを処理したくない場合。</span><span class="sxs-lookup"><span data-stu-id="e4a34-p106">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data. Rollback clears all processed data. If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="e4a34-128">プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="e4a34-128">Process summary</span></span>

<span data-ttu-id="e4a34-129">準備」の\>プロセス\>結果\>要約すると、読み込まれたファイルの結果の内訳が表示されます正常なファイルの処理とエラーの結果を処理します。</span><span class="sxs-lookup"><span data-stu-id="e4a34-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="e4a34-130">ペインでは、インポートされたファイルの統計情報がグラフィカルに表示を次のように表示します。</span><span class="sxs-lookup"><span data-stu-id="e4a34-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="e4a34-131">**プロセスの概要が蓄積される**d: 大文字と小文字のすべてのファイルです。</span><span class="sxs-lookup"><span data-stu-id="e4a34-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="e4a34-132">**プロセスの概要**: 最後のセッションまたは操作からファイルが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="e4a34-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="e4a34-133">**最後の家族**: 家族の情報 (存在する場合) の場合。</span><span class="sxs-lookup"><span data-stu-id="e4a34-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="e4a34-134">**シード**・ ファイルが追加された場合は、ファイルに対して定義された問題ごとシード ファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a34-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="e4a34-135">**シード**ファイルのマークに失敗した場合、また記載されています。</span><span class="sxs-lookup"><span data-stu-id="e4a34-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="e4a34-136">**タグ付け済み**のファイルが追加された場合は、ファイルに対して定義された問題ごと事前にタグ付けされたファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a34-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="e4a34-137">ファイルの**タグ付け済み**のマークが失敗した場合、また記載されています。</span><span class="sxs-lookup"><span data-stu-id="e4a34-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![プロセス モジュールの概要](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="e4a34-139">プロセスの概要が蓄積し、グラフの最後</span><span class="sxs-lookup"><span data-stu-id="e4a34-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="e4a34-140">左側のバーには、ソース + 展開されたファイルが含まれています: すべてのファイルが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="e4a34-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="e4a34-141">右側バーの処理、含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4a34-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="e4a34-142">読み込みエラーがあるファイル</span><span class="sxs-lookup"><span data-stu-id="e4a34-142">Files with load errors</span></span>
    
- <span data-ttu-id="e4a34-143">含めることが正常に読み込まれたファイル:</span><span class="sxs-lookup"><span data-stu-id="e4a34-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="e4a34-144">**既存**: ファイルの前に読み込まれたし、もう一度 (を含む重複) が読み込まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4a34-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="e4a34-145">**テキスト**: テキストに固有のファイルです。</span><span class="sxs-lookup"><span data-stu-id="e4a34-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="e4a34-146">**非テキスト**: テキスト ファイル、ネイティブの空のテキスト ファイル、ネイティブのテキスト以外のファイルを空にします。</span><span class="sxs-lookup"><span data-stu-id="e4a34-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="e4a34-147">**重複して**%s: 重複している文章をファイルします。</span><span class="sxs-lookup"><span data-stu-id="e4a34-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="e4a34-148">最後のプロセスのエラー</span><span class="sxs-lookup"><span data-stu-id="e4a34-148">Last process errors</span></span>

<span data-ttu-id="e4a34-149">準備」の\>プロセス\>結果\>最後の処理エラー、最後のセッションまたはアクションの実行でエラーの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a34-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![プロセス モジュールのエラー](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="e4a34-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4a34-151">See also</span></span>

[<span data-ttu-id="e4a34-152">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e4a34-152">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e4a34-153">プロセス モジュールを実行して、データの読み込み</span><span class="sxs-lookup"><span data-stu-id="e4a34-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

