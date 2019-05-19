---
title: Office 用データを準備する 365 Advanced eDiscovery
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
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 'Microsoft 365 セキュリティ&amp;コンプライアンスセンターを使用して Office 365 Advanced eDiscovery で分析するために office 365 データを準備する方法について説明します。 '
ms.openlocfilehash: be778acb3356071e9575ed708623a0b94e2b3c7a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157459"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a><span data-ttu-id="7abac-103">Office 用データを準備する 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7abac-103">Prepare data for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="7abac-104">このトピックでは、高度な電子情報開示のケースにコンテンツ検索の結果を読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7abac-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7abac-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="7abac-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a><span data-ttu-id="7abac-107">手順 1: 高度な電子情報開示用に Office 365 データを準備する</span><span class="sxs-lookup"><span data-stu-id="7abac-107">Step 1: Prepare Office 365 data for Advanced eDiscovery</span></span>

<span data-ttu-id="7abac-108">上級電子情報開示を使用してデータを分析するには、Microsoft 365 セキュリティ&amp;コンプライアンスセンター (Microsoft 365 セキュリティ&amp;コンプライアンスセンターの**コンテンツ検索**ページにリストされています) で実行するコンテンツ検索の結果を使用するか、電子情報開示ケースに関連付けられている検索 (セキュリティ&amp;コンプライアンスセンターの [**電子情報開示**] ページにリストされています)。</span><span class="sxs-lookup"><span data-stu-id="7abac-108">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="7abac-109">高度な電子情報開示で分析のために検索結果を準備する詳細な手順については、「 [Office 365 Advanced ediscovery の検索結果を準備](prepare-search-results-for-advanced-ediscovery.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7abac-109">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7abac-110">Office 365 の外部にデータがあり、そのデータを office 365 にインポートして、高度な電子情報開示で準備および分析できるようにする場合は、「office 2010 365 への PST ファイルのインポートの概要」と「office の365でのサードパーティデータのアーカイブ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7abac-110">If you have data outside of Office 365 and want to import it to Office 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) and [Archiving third-party data in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="7abac-111">手順 2: 高度な電子情報開示のケースに検索結果データを読み込む</span><span class="sxs-lookup"><span data-stu-id="7abac-111">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="7abac-112">分析のためにセキュリティ&amp;コンプライアンスセンターで検索結果を準備した後、次の手順では、高度な電子情報開示のケースに検索結果を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="7abac-112">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="7abac-113">詳細については、「 [Process module を実行する](run-the-process-module-in-advanced-ediscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7abac-113">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="7abac-114">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="7abac-114">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="7abac-115">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7abac-115">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="7abac-116">セキュリティ&amp;コンプライアンス センターで、**[検索&amp;調査]** \> **[電子情報開示]** の順にクリックし、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7abac-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="7abac-117">高度な電子情報開示でにデータを読み込むケースの横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7abac-117">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="7abac-118">ケースの **[ホーム]** ページで、**[Advanced eDiscovery]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7abac-118">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![[高度な電子情報開示に切り替え] をクリックして、高度な電子情報開示でケースを開きます。](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="7abac-120">**[高度な電子情報開示**の進行状況バーへの接続] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7abac-120">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="7abac-121">上級電子情報開示に接続されている場合は、ケースのセットアップページにコンテナーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7abac-121">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![詳細な電子情報開示でケースが表示される](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="7abac-123">これらのコンテナーは、手順1でアドバンスト eDiscovery で分析するために準備した検索結果を表します。</span><span class="sxs-lookup"><span data-stu-id="7abac-123">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="7abac-124">セキュリティ&amp; /コンプライアンスセンターでは、コンテナーの名前がコンテンツ検索と同じ名前になっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7abac-124">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="7abac-125">リスト内のコンテナーは、準備したものです。</span><span class="sxs-lookup"><span data-stu-id="7abac-125">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="7abac-126">上級電子情報開示のために別のユーザーが検索結果を準備している場合、対応するコンテナーはリストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="7abac-126">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="7abac-127">高度な電子情報開示のケースに、コンテナーからの検索結果データを読み込むには、コンテナーを選択し、[**処理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7abac-127">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="7abac-128">上級電子情報開示のケースに&amp;セキュリティコンプライアンスセンターからの検索結果が追加された後、次の手順では、[advanced ediscovery] のツールを使用して、ケースに関連するデータを分析し、選別します。</span><span class="sxs-lookup"><span data-stu-id="7abac-128">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7abac-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="7abac-129">See also</span></span>

[<span data-ttu-id="7abac-130">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7abac-130">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7abac-131">ユーザーおよびケースをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7abac-131">Set up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7abac-132">ケース データの分析</span><span class="sxs-lookup"><span data-stu-id="7abac-132">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="7abac-133">関連性の設定の管理</span><span class="sxs-lookup"><span data-stu-id="7abac-133">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7abac-134">関連度モジュールの使用</span><span class="sxs-lookup"><span data-stu-id="7abac-134">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7abac-135">ケース データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="7abac-135">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

