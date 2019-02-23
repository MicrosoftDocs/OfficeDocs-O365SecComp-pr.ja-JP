---
title: コンテンツ検索のレポートをエクスポートする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Office 365 セキュリティ&amp;コンプライアンスセンターでは、コンテンツ検索の実際の結果をエクスポートする代わりに、検索結果レポートをエクスポートするだけで済みます。レポートには、検索結果の概要と、エクスポートされる各アイテムの詳細情報を含むドキュメントが含まれます。
ms.openlocfilehash: 12799474bfb099c521f72cd3902173d42b17d4dd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216237"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="d2fba-104">コンテンツ検索のレポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d2fba-104">Export a Content Search report</span></span>

<span data-ttu-id="d2fba-105">Office 365 セキュリティ&amp;コンプライアンスセンター (および電子情報開示ケースに関連付けられているコンテンツ検索から) のすべての検索結果セットをエクスポートするのではなく、生成された同じレポートをエクスポートするだけで済みます。検索結果をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-105">Instead of exporting the full set of search results from a Content Search in the Office 365 Security &amp; Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="d2fba-p102">レポートをエクスポートすると、コンテンツ検索と同じ名前のフォルダーにダウンロードされますが、そのレポートには [レポート]*のみ*が追加されます。たとえば、コンテンツ検索に*ContosoCase0815*という名前が付けられている場合、レポートは*ContosoCase0815_ReportsOnly*という名前のフォルダーにダウンロードされます。レポートに含まれるドキュメントの一覧については、「[レポートに含まれるもの](#whats-included-in-the-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p102">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  . For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  . For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d2fba-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="d2fba-109">Before you begin</span></span>

- <span data-ttu-id="d2fba-p103">コンテンツ検索レポートをエクスポートするには、Office 365 セキュリティ&amp;コンプライアンスセンターでコンプライアンス検索管理役割が割り当てられている必要があります。この役割は、組み込みの電子情報開示マネージャーと組織の管理役割グループに割り当てられます。既定では、組織の管理役割グループに割り当てられません。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p103">To export a Content Search report, you have to be assigned the Compliance Search management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager and Organization Management role groups. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="d2fba-p104">レポートをエクスポートすると、データがローカルコンピューターにダウンロードされる前に、Microsoft クラウド内の一意の Windows Azure ストレージ領域に一時的に格納されます。組織が Azure のエンドポイントに接続できることを確認し\*\* \*ます。 blob.core.windows.net\*\* (ワイルドカードは、エクスポートの一意識別子を表します)。検索結果データは、作成後2週間後に Azure ストレージ領域から削除されます。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p104">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="d2fba-117">検索結果をエクスポートする際に使用するコンピューターは、次のシステム要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2fba-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="d2fba-118">32 ビットおよび 64 ビット バージョンの Windows 7 およびそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="d2fba-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="d2fba-119">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="d2fba-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="d2fba-120">サポートされているブラウザー:</span><span class="sxs-lookup"><span data-stu-id="d2fba-120">A supported browser:</span></span>
    
    - <span data-ttu-id="d2fba-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d2fba-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="d2fba-122">または</span><span class="sxs-lookup"><span data-stu-id="d2fba-122">or</span></span>
    
    - <span data-ttu-id="d2fba-123">Microsoft Internet Explorer 10 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="d2fba-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="d2fba-p105">**注:** Microsoft は、ClickOnce アプリケーションのサードパーティの拡張機能またはアドオンを製造していません。サポートされていないブラウザーを使用して、サードパーティの内線番号またはアドオンを使用して検索結果をエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="d2fba-p106">コンテンツ検索によって返される結果の推定合計サイズが 20&nbsp;TB を超えている場合、レポートのエクスポートは失敗します。レポートを正常にエクスポートするには、範囲を絞るようにして検索を再実行し、結果の推定サイズが 20&nbsp;TB 未満になるようにします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p106">If the estimated total size of the results returned by a Content Search exceeds 20&nbsp;TB, exporting the report will fail. To successfully export the report, try to narrow the scope and re-run the search so the estimated size of the results is less than 20&nbsp;TB.</span></span>

- <span data-ttu-id="d2fba-p107">コンテンツ検索レポートのエクスポートは、同時に実行しているエクスポートの最大数と、1人のユーザーが実行できるエクスポートの最大数に対してカウントされます。エクスポート制限の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターからコンテンツ検索の結果をエクスポートする](export-search-results.md#export-limits)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p107">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run. For more information about export limits, see [Export Content Search results from the Office 365 Security & Compliance Center](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="d2fba-130">コンテンツ検索レポートを生成してダウンロードする</span><span class="sxs-lookup"><span data-stu-id="d2fba-130">Generate and download a Content Search report</span></span>

<span data-ttu-id="d2fba-131">コンテンツ検索レポートを生成してダウンロードする手順は、実際に検索結果をエクスポートした場合とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="d2fba-131">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="d2fba-132">手順 1: エクスポート用のレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="d2fba-132">Step 1: Generate the report for export</span></span>

<span data-ttu-id="d2fba-p108">最初の手順として、コンピューターをエクスポートするためのレポートをダウンロードする準備をします。レポートを作成すると、レポートドキュメントが Microsoft クラウドの Azure ストレージ領域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p108">The first step is to prepare the report for downloading to your computer exporting. When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="d2fba-135">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="d2fba-135">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="d2fba-136">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-136">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="d2fba-137">セキュリティ/コンプライアンス センターの左側のウィンドウで、**[検索と調査]** \> **[コンテンツ検索]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-137">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="d2fba-138">[**コンテンツ検索**] ページで、検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2fba-138">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="d2fba-139">詳細ウィンドウの [**レポートをコンピューターにエクスポートする**] で、[**レポートの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-139">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d2fba-p109">検索結果が7日よりも古い場合は、検索結果を更新するように求めるメッセージが表示されます。この問題が発生した場合は、エクスポートをキャンセルし、選択した検索の詳細ウィンドウで [**検索結果の更新**] をクリックしてから、結果が更新された後に再度レポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p109">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="d2fba-142">[**レポートのエクスポート**] ページの [**検索からこれらの項目を含める**] で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d2fba-142">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="d2fba-143">インデックス付きのアイテムのみをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d2fba-143">Export only indexed items</span></span>
    
    - <span data-ttu-id="d2fba-144">インデックス付きのアイテムとインデックスのないアイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d2fba-144">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="d2fba-145">インデックスのないアイテムのみをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d2fba-145">Export only unindexed items</span></span>
    
    <span data-ttu-id="d2fba-146">インデックスのないアイテムの詳細については、「[コンテンツ検索でインデックス](partially-indexed-items-in-content-search.md)が作成されたアイテム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2fba-146">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="d2fba-p110">SharePoint ドキュメントのすべてのバージョンの検索統計を含めるかどうかを選択します。このオプションは、検索のコンテンツソースに SharePoint または OneDrive for business サイトが含まれている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p110">Choose to include search statistics for all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="d2fba-149">[**レポートの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-149">Click **Generate report**.</span></span>
    
    <span data-ttu-id="d2fba-p111">検索結果レポートはダウンロード用に準備されています。つまり、レポートドキュメントが Microsoft クラウド内の Azure ストレージ領域にアップロードされます。レポートがダウンロードできる状態になると、[レポートの**ダウンロード**] リンクが [詳細] ウィンドウの [**コンピューターにレポートをエクスポート**します] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p111">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud. When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d2fba-p112">また、電子情報開示ケースに関連付けられているコンテンツ検索のレポートをエクスポートすることもできます。これを行うには、 **[ &amp;検索調査**\>**電子情報開示**] に移動し、ケース](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)を選択して、[編集アイコンの**編集** ![] をクリックします。[検索] ページで、検索を選択し、[ \*\*\*\* ![エクスポート] [検索結果](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \>のエクスポート] アイコンをクリックして**レポートをエクスポート**します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d2fba-p112">You can also export a report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="d2fba-155">手順 2: レポートをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="d2fba-155">Step 2: Download the report</span></span>

<span data-ttu-id="d2fba-156">次の手順では、Azure ストレージ領域からローカルコンピューターにレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-156">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="d2fba-157">レポートを生成した検索の詳細ウィンドウで、[**レポートをコンピューターにエクスポート**する] で、[**レポートのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-157">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="d2fba-158">[**レポートのダウンロード**] ページが表示され、コンピューターにダウンロードされるまでのレポートに関する以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2fba-158">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="d2fba-159">ダウンロードされるアイテムの数。</span><span class="sxs-lookup"><span data-stu-id="d2fba-159">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="d2fba-160">ダウンロードされるアイテムの推定合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="d2fba-160">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="d2fba-p113">インデックス付きまたはインデックスなしをエクスポートするかどうかを指定します。インデックスのないアイテムは、他の理由で、認識された形式、暗号化されている、またはインデックスが作成されていないアイテムです。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p113">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="d2fba-163">SharePoint ドキュメントのバージョンがダウンロードされるかどうか。</span><span class="sxs-lookup"><span data-stu-id="d2fba-163">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="d2fba-p114">レポートエクスポートプロセスの状態。レポートの準備が完了していない場合でも、レポートのダウンロードを開始できます。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p114">The status of the report export process. You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="d2fba-p115">[**キーのエクスポート**] で、[**クリップボードにコピー] を**クリックします。このキーは、手順5で使用してレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p115">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d2fba-168">すべてのユーザーが電子情報開示エクスポートツールをインストールして起動し、このキーを使用して検索レポートをダウンロードすることができるため、パスワードやその他のセキュリティ関連情報を保護するのと同じように、このキーを保護するための対策を必ず実行してください。</span><span class="sxs-lookup"><span data-stu-id="d2fba-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="d2fba-169">[**レポートのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-169">Click **Download report**.</span></span>
    
4. <span data-ttu-id="d2fba-170">**MicrosoftOffice 365 電子情報開示エクスポートツール**をインストールするように求めるメッセージが表示されたら、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-170">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="d2fba-171">**電子情報開示エクスポート ツール**で、手順 2 でコピーしたエクスポート キーを適切なボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d2fba-171">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="d2fba-172">[**参照**] をクリックして、レポートをダウンロードする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="d2fba-172">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="d2fba-173">**[開始]** をクリックして、検索結果をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-173">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="d2fba-p116">**電子情報開示エクスポートツール**は、エクスポート処理に関する状態情報を表示します。これには、ダウンロードする残りのアイテムの数 (およびサイズ) の推定値が含まれます。エクスポートプロセスが完了すると、ダウンロードされた場所にあるファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p116">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d2fba-p117">電子情報開示ケースに関連付けられたコンテンツ検索のレポートをダウンロードできます。これを行うには、 **[ &amp;検索調査**\>**電子情報開示**] に移動し、ケース](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)を選択して、[編集アイコンの**編集** ![] をクリックします。[**エクスポート**] ページで、レポートのエクスポートを選択し、[詳細] ウィンドウの [**レポートのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p117">You can download the report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="d2fba-179">レポートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="d2fba-179">What's included in the report</span></span>

<span data-ttu-id="d2fba-180">コンテンツ検索の結果に関するレポートを生成してエクスポートすると、次のドキュメントがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="d2fba-180">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="d2fba-p118">**エクスポートの概要**-エクスポートの概要を含む Excel ドキュメント。これには、検索されたコンテンツソースの数、各コンテンツの場所からの検索結果の数、アイテムの推定数、エクスポートされるアイテムの実際の数、およびアイテムの予想および実際のサイズなどの情報が含まれます。エクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p118">**Export Summary** - An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d2fba-p119">レポートをエクスポートするときにインデックスのないアイテムを含めると、インデックスが作成されていないアイテムの数が、予想される検索結果の合計数とダウンロードした検索結果の合計数に含まれます (検索結果をエクスポートした場合)。概要レポートをエクスポートします。つまり、ダウンロードされるアイテムの合計数は、予想される結果の合計数と、インデックスが設定されていないアイテムの合計数と同じになります。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p119">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report. In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="d2fba-185">**マニフェスト**-検索結果に含まれる各アイテムに関する情報を含むマニフェストファイル (XML 形式)。</span><span class="sxs-lookup"><span data-stu-id="d2fba-185">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="d2fba-p120">**結果**-検索結果と共にエクスポートされる各インデックス付きアイテムに関する情報を含む行を含む Excel ドキュメント。メールの場合、結果ログには、各メッセージに関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p120">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="d2fba-188">移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。</span><span class="sxs-lookup"><span data-stu-id="d2fba-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="d2fba-189">メッセージが送信または受信された日付。</span><span class="sxs-lookup"><span data-stu-id="d2fba-189">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="d2fba-190">メッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="d2fba-190">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="d2fba-191">メッセージの送信者と受信者。</span><span class="sxs-lookup"><span data-stu-id="d2fba-191">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="d2fba-192">SharePoint および OneDrive for business サイトのドキュメントの場合、結果ログには、各ドキュメントに関する以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2fba-192">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="d2fba-193">ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="d2fba-193">The URL for the document.</span></span>
    
  - <span data-ttu-id="d2fba-194">ドキュメントがあるサイト コレクションの URL。</span><span class="sxs-lookup"><span data-stu-id="d2fba-194">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="d2fba-195">ドキュメントが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="d2fba-195">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="d2fba-196">ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。</span><span class="sxs-lookup"><span data-stu-id="d2fba-196">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d2fba-197">**結果**レポートに表示される行数は、ダウンロードされる検索結果の総数から、インデックスのない**アイテム**レポートにリストされているアイテムの合計数を引いた数と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2fba-197">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="d2fba-p121">**インデックス**のないアイテム-検索結果に含まれるインデックスのないアイテムに関する情報を含む Excel ドキュメント。検索結果レポートを生成するときに、インデックスのないアイテムを含めない場合、このレポートは引き続きダウンロードされますが、空になります。</span><span class="sxs-lookup"><span data-stu-id="d2fba-p121">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results. If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
