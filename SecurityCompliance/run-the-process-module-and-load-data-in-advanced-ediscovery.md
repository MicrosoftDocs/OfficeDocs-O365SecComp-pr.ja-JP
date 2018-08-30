---
title: プロセス モジュールを実行し Office 365 Advanced eDiscovery にデータを読み込む
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Office 365 のセキュリティを使用する方法を説明&amp;コンプライアンス センターは、電子的証拠開示の Office 365 の詳細にアクセスし、サポート案件のプロセス モジュールを実行します。  '
ms.openlocfilehash: 32052bccc37d20c8707a1efb0592f7c93daf3590
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532160"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="eb679-103">プロセス モジュールを実行し Office 365 Advanced eDiscovery にデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="eb679-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="eb679-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="eb679-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="eb679-106">このセクションでは、高度な電子的証拠開示プロセスのモジュールの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb679-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="eb679-p102">ファイルのデータをファイルの種類、拡張子、場所またはパス、作成日、作成者、管理者と件名などのメタデータに読み込める電子的証拠開示の詳細し、それぞれのケースのために保存します。いくつかのメタデータは、ネイティブのファイルが読み込まれるときになど、高度な電子的証拠開示、によって計算されます。</span><span class="sxs-lookup"><span data-stu-id="eb679-p102">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case. Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="eb679-p103">高度な電子的証拠開示では、メタデータの値、重複の近くのグループ化などの関連性スコア システムを提供します。管理者によっては、ファイルのコメントなど、他のメタデータを追加できます。</span><span class="sxs-lookup"><span data-stu-id="eb679-p103">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores. Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="eb679-111">実行中のプロセス</span><span class="sxs-lookup"><span data-stu-id="eb679-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="eb679-p104">バッチ番号は、ファイルの追跡を許可するのには、ファイル、プロセス中に割り当てられます。バッチ番号は、再処理のオプションのバッチ処理の識別も可能です。バッチ番号およびセッションをフィルター処理するための追加のフィルターを利用できます。</span><span class="sxs-lookup"><span data-stu-id="eb679-p104">Batch numbers are assigned to a file during Process to allow the tracking of files. The batch number also enables identification of Process batches for reprocessing options. Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="eb679-115">プロセスを実行するのには次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb679-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="eb679-116">[Office 365 のセキュリティを開く&amp;コンプライアンス センター](go-to-the-securitycompliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb679-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="eb679-117">移動**検索&amp;調査** \> **電子的証拠開示**し、**高度な電子的証拠開示に移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb679-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="eb679-118">高度な電子的証拠開示、表示されている**場合**のページで、適切な大文字と小文字を選択で**ケースに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb679-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="eb679-119">**準備**」の\>**プロセス** \> **のセットアップ**、使用可能なコンテナーの一覧からコンテナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb679-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![場合に検索結果を追加するプロセスをクリックします。](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="eb679-121">シード ファイルまたは事前に名札付きのファイルとして、コンテナーを追加する場合は、 **[詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb679-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="eb679-p105">シード ファイルを使用して、低の豊富な機能に問題のトレーニングを高速化する (通常 2% 以下)。シード ・ ファイルをお勧めさまざまな互いに関連するファイルと、選択したプロセスに関する問題が (多くのシード ファイルは関連性の高い結果をスキューできます) あたり 20 ~ 50 シードです。シード ファイルは、問題のトレーニングは同じ人で見直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb679-p105">Use seed files to accelerate training for issues with low richness (usually 2%, or less). For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results). Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="eb679-p106">事前にタグ付けされたファイルを使用すると、関連性の高いトレーニングを自動化できます。1,500 以上のファイルにタグを付けるし、関連性に追加されたコレクションの場合と同様の非関連ファイルに関連する比率を維持する必要があります。これらのファイルを手動でタグ付けする必要があります、およびタグ付けの品質を確実にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb679-p106">Use pre-tagged files to automate Relevance training. You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance. These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![バッチ ファイルを処理するための設定ページのスクリーン ショットの高度な](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="eb679-129">**シード**に記載します。</span><span class="sxs-lookup"><span data-stu-id="eb679-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="eb679-p107">コンテナーをシード ファイルとしてマークする**シード ファイルとしてマーク**] を選択します。**問題の**ドロップダウン リストから案件ごとを割り当てるを選択する必要があるも。**タグ**のドロップダウン リストから、**関連性**または**関係のない**のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb679-p107">Choose **Mark as seed files** to mark the container as seed files. You also need choose to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="eb679-133">**シード**ファイルを設定するとは、**タグ付け済み**としてマークできません。</span><span class="sxs-lookup"><span data-stu-id="eb679-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="eb679-134">**事前にタグ付きのファイル**のセクション。</span><span class="sxs-lookup"><span data-stu-id="eb679-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="eb679-p108">コンテナーを事前に名札付きのファイルとしてマークするのには**事前に名札付きのファイルとしてマーク**] を選択します。案件ごと**の問題の**ドロップダウン リストから割り当てる必要があります。**タグ**のドロップダウン リストから、**関連性**または**関係のない**のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb679-p108">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files. You also need to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="eb679-138">**タグを事前**にファイルを設定すると後、は、**シード**としてマークできません。</span><span class="sxs-lookup"><span data-stu-id="eb679-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="eb679-p109">「 **E メールへのタグ付け**します。シードまたは事前にタグ付きとしてマークするのには、処理済みのメールのどの部分を設定します。</span><span class="sxs-lookup"><span data-stu-id="eb679-p109">In the **Email tagging** section. set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="eb679-p110">開始するには、**プロセス**をクリックします。完了すると、処理結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb679-p110">To begin, click **Process**. When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="eb679-143">(省略可能)データ ソースを特定の管理者に割り当てる場合は、追加および**通告**の保管担当者の名前を編集\>**通告**での**管理**と割り当ての通告\>**を割り当てます**。</span><span class="sxs-lookup"><span data-stu-id="eb679-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="eb679-144">ケースに追加する場合処理できますから。</span><span class="sxs-lookup"><span data-stu-id="eb679-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eb679-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb679-145">See also</span></span>

[<span data-ttu-id="eb679-146">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="eb679-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="eb679-147">プロセス モジュールの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="eb679-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

