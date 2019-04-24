---
title: プロセスモジュールを実行し、Office 365 でデータを読み込む高度な電子情報開示
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'office 365 セキュリティ&amp;コンプライアンスセンターを使用して office 365 Advanced eDiscovery にアクセスし、ケースに対して Process モジュールを実行する方法について説明します。  '
ms.openlocfilehash: 95c73c034ed2ffa1c45f9aacd8463c497a842859
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261409"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="eb8a4-103">プロセスモジュールを実行し、Office 365 でデータを読み込む高度な電子情報開示</span><span class="sxs-lookup"><span data-stu-id="eb8a4-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="eb8a4-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="eb8a4-106">このセクションでは、Advanced eDiscovery プロセスモジュールの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="eb8a4-107">ファイルデータに加えて、ファイルの種類、拡張子、場所またはパス、作成日時、作成者、保管担当者、および件名などのメタデータは、高度な電子情報開示に読み込んで、各ケースごとに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-107">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case.</span></span> <span data-ttu-id="eb8a4-108">一部のメタデータは、アドバンスト eDiscovery によって計算されます。たとえば、ネイティブファイルが読み込まれるときなどです。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-108">Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="eb8a4-109">Advanced eDiscovery は、重複したグループや関連性のスコアなど、システムメタデータの値を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-109">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores.</span></span> <span data-ttu-id="eb8a4-110">ファイル注釈などのその他のメタデータは、管理者が追加できます。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-110">Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="eb8a4-111">実行中のプロセス</span><span class="sxs-lookup"><span data-stu-id="eb8a4-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="eb8a4-112">バッチ番号は、プロセス中にファイルの追跡を許可するためにファイルに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-112">Batch numbers are assigned to a file during Process to allow the tracking of files.</span></span> <span data-ttu-id="eb8a4-113">バッチ番号を使用して、再処理オプションのプロセスバッチを識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-113">The batch number also enables identification of Process batches for reprocessing options.</span></span> <span data-ttu-id="eb8a4-114">バッチ番号およびセッションによるフィルター処理には、追加のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-114">Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="eb8a4-115">プロセスを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="eb8a4-116">[Office 365 セキュリティ&amp;コンプライアンスセンターを開き](go-to-the-securitycompliance-center.md)ます。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="eb8a4-117">[**検索&amp;調査** \> ]**電子情報開示**に移動し、[ **Advanced ediscovery に移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="eb8a4-118">[高度な電子情報開示] で、[表示される**ケース**] ページで適切なケースを選択し、[**ケースに移動] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="eb8a4-119">[ \*\*\*\* \> \*\*\*\* プロセス\> **セットアップ**の準備] で、使用可能なコンテナーの一覧からコンテナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![検索結果をケースに追加するには、[処理] をクリックします。](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="eb8a4-121">[**詳細設定**] をクリックします。コンテナーを seed ファイルとして、またはタグ付け済みファイルとして追加する場合。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="eb8a4-122">低低解像度 (通常は 2% 以下) の問題のトレーニングを高速化するには、シードファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-122">Use seed files to accelerate training for issues with low richness (usually 2%, or less).</span></span> <span data-ttu-id="eb8a4-123">シードファイルの場合、さまざまな関連性のあるファイルとプロセスを選択することをお勧めします。1つの問題については、20-50 のシードを使用する必要があります (多くのシードファイルが関連性の結果をスキューする可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-123">For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results).</span></span> <span data-ttu-id="eb8a4-124">シードファイルは、問題をトレーニングするのと同じ担当者が見直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-124">Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="eb8a4-125">事前にタグ付けされたファイルを使用して、関連性トレーニングを自動化します。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-125">Use pre-tagged files to automate Relevance training.</span></span> <span data-ttu-id="eb8a4-126">少なくとも1500ファイルにタグを付けて、関連性があるコレクションと同じように関連していないファイルに関連する割合を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-126">You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance.</span></span> <span data-ttu-id="eb8a4-127">これらのファイルは手動でタグ付けする必要があり、タグの品質に自信を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-127">These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![バッチファイルを処理するための [詳細設定] ページのスクリーンショット](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="eb8a4-129">[ **Seed** ] セクションで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="eb8a4-130">[ **seed ファイルとしてマーク**] を選択して、コンテナーをシードファイルとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-130">Choose **Mark as seed files** to mark the container as seed files.</span></span> <span data-ttu-id="eb8a4-131">[**問題**] ドロップダウンから、問題ごとに割り当てるように選択する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-131">You also need choose to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="eb8a4-132">[タグ\*\*\*\* ] ドロップダウンから [関連\*\*\*\* する] または [**無関係**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-132">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="eb8a4-133">ファイルを**Seed**として設定すると、**あらかじめタグ**付けされたマークを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="eb8a4-134">[**プリタグ付け**されたファイル] セクションで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="eb8a4-135">[**プリタグ付きファイルとしてマーク**する] を選択して、タグ付きファイルとしてコンテナーをマークします。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-135">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files.</span></span> <span data-ttu-id="eb8a4-136">[**懸案事項**] ボックスの一覧から、問題ごとに割り当てる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-136">You also need to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="eb8a4-137">[タグ\*\*\*\* ] ドロップダウンから [関連\*\*\*\* する] または [**無関係**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-137">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="eb8a4-138">**プリタグ付き**でファイルを設定すると、 **Seed**としてマークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="eb8a4-139">[**電子メールのタグ付け**] セクション。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-139">In the **Email tagging** section.</span></span> <span data-ttu-id="eb8a4-140">処理された電子メールのどの部分を Seed としてマークするか、事前にタグ付けするかを設定します。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-140">set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="eb8a4-141">開始するには、[**処理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-141">To begin, click **Process**.</span></span> <span data-ttu-id="eb8a4-142">完了すると、プロセスの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-142">When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="eb8a4-143">オプション特定の保管担当者にデータソースを割り当てる必要がある場合は、**保管担当者** \>で保管担当者名を追加および編集し、**保管担当者** \> **assign**で保管担当者を**管理**して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="eb8a4-144">ケースにを追加した場合は、もう一度処理することができます。</span><span class="sxs-lookup"><span data-stu-id="eb8a4-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eb8a4-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb8a4-145">See also</span></span>

[<span data-ttu-id="eb8a4-146">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="eb8a4-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="eb8a4-147">プロセスモジュールの結果を表示する</span><span class="sxs-lookup"><span data-stu-id="eb8a4-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

