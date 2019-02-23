---
title: プロセス モジュールを実行し Office 365 Advanced eDiscovery にデータを読み込む
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
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217607"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="ffa46-103">プロセス モジュールを実行し Office 365 Advanced eDiscovery にデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="ffa46-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="ffa46-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="ffa46-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ffa46-106">このセクションでは、Advanced eDiscovery プロセスモジュールの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffa46-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="ffa46-p102">ファイルデータに加えて、ファイルの種類、拡張子、場所またはパス、作成日時、作成者、保管担当者、および件名などのメタデータは、高度な電子情報開示に読み込んで、各ケースごとに保存することができます。一部のメタデータは、アドバンスト eDiscovery によって計算されます。たとえば、ネイティブファイルが読み込まれるときなどです。</span><span class="sxs-lookup"><span data-stu-id="ffa46-p102">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case. Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="ffa46-p103">Advanced eDiscovery は、重複したグループや関連性のスコアなど、システムメタデータの値を提供します。ファイル注釈などのその他のメタデータは、管理者が追加できます。</span><span class="sxs-lookup"><span data-stu-id="ffa46-p103">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores. Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="ffa46-111">実行中のプロセス</span><span class="sxs-lookup"><span data-stu-id="ffa46-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="ffa46-p104">バッチ番号は、プロセス中にファイルの追跡を許可するためにファイルに割り当てられます。バッチ番号を使用して、再処理オプションのプロセスバッチを識別することもできます。バッチ番号およびセッションによるフィルター処理には、追加のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ffa46-p104">Batch numbers are assigned to a file during Process to allow the tracking of files. The batch number also enables identification of Process batches for reprocessing options. Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="ffa46-115">プロセスを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ffa46-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="ffa46-116">[Office 365 セキュリティ&amp;コンプライアンスセンターを開き](go-to-the-securitycompliance-center.md)ます。</span><span class="sxs-lookup"><span data-stu-id="ffa46-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="ffa46-117">[**検索&amp;調査** \> ]**電子情報開示**に移動し、[ **Advanced ediscovery に移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffa46-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="ffa46-118">[高度な電子情報開示] で、[表示される**ケース**] ページで適切なケースを選択し、[**ケースに移動] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="ffa46-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="ffa46-119">[ \*\*\*\* \> \*\*\*\* プロセス\> **セットアップ**の準備] で、使用可能なコンテナーの一覧からコンテナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ffa46-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![検索結果をケースに追加するには、[処理] をクリックします。](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="ffa46-121">[**詳細設定**] をクリックします。コンテナーを seed ファイルとして、またはタグ付け済みファイルとして追加する場合。</span><span class="sxs-lookup"><span data-stu-id="ffa46-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="ffa46-p105">低低解像度 (通常は 2% 以下) の問題のトレーニングを高速化するには、シードファイルを使用します。シードファイルの場合、さまざまな関連性のあるファイルとプロセスを選択することをお勧めします。1つの問題については、20-50 のシードを使用する必要があります (多くのシードファイルが関連性の結果をスキューする可能性があります)。シードファイルは、問題をトレーニングするのと同じ担当者が見直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffa46-p105">Use seed files to accelerate training for issues with low richness (usually 2%, or less). For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results). Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="ffa46-p106">事前にタグ付けされたファイルを使用して、関連性トレーニングを自動化します。少なくとも1500ファイルにタグを付けて、関連性があるコレクションと同じように関連していないファイルに関連する割合を維持する必要があります。これらのファイルは手動でタグ付けする必要があり、タグの品質に自信を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffa46-p106">Use pre-tagged files to automate Relevance training. You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance. These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![バッチファイルを処理するための [詳細設定] ページのスクリーンショット](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="ffa46-129">[ **Seed** ] セクションで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ffa46-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="ffa46-p107">[ **seed ファイルとしてマーク**] を選択して、コンテナーをシードファイルとしてマークします。[**問題**] ドロップダウンから、問題ごとに割り当てるように選択する必要もあります。[タグ\*\*\*\* ] ドロップダウンから [関連\*\*\*\* する] または [**無関係**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ffa46-p107">Choose **Mark as seed files** to mark the container as seed files. You also need choose to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ffa46-133">ファイルを**Seed**として設定すると、**あらかじめタグ**付けされたマークを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="ffa46-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="ffa46-134">[**プリタグ付け**されたファイル] セクションで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ffa46-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="ffa46-p108">[**プリタグ付きファイルとしてマーク**する] を選択して、タグ付きファイルとしてコンテナーをマークします。[**懸案事項**] ボックスの一覧から、問題ごとに割り当てる必要もあります。[タグ\*\*\*\* ] ドロップダウンから [関連\*\*\*\* する] または [**無関係**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ffa46-p108">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files. You also need to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ffa46-138">**プリタグ付き**でファイルを設定すると、 **Seed**としてマークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ffa46-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="ffa46-p109">[**電子メールのタグ付け**] セクション。処理された電子メールのどの部分を Seed としてマークするか、事前にタグ付けするかを設定します。</span><span class="sxs-lookup"><span data-stu-id="ffa46-p109">In the **Email tagging** section. set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="ffa46-p110">開始するには、[**処理**] をクリックします。完了すると、プロセスの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffa46-p110">To begin, click **Process**. When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="ffa46-143">オプション特定の保管担当者にデータソースを割り当てる必要がある場合は、**保管担当者** \>で保管担当者名を追加および編集し、**保管担当者** \> **assign**で保管担当者を**管理**して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ffa46-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="ffa46-144">ケースにを追加した場合は、もう一度処理することができます。</span><span class="sxs-lookup"><span data-stu-id="ffa46-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ffa46-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffa46-145">See also</span></span>

[<span data-ttu-id="ffa46-146">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ffa46-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ffa46-147">プロセスモジュールの結果を表示する</span><span class="sxs-lookup"><span data-stu-id="ffa46-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

