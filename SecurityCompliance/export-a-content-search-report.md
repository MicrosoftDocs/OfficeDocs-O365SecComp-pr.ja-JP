---
title: コンテンツ検索のレポートをエクスポートする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/25/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: コンテンツの検索では、Office 365 のセキュリティの実際の結果をエクスポートするのではなく&amp;コンプライアンス センターでは、検索結果のレポートだけエクスポートできます。レポートには、検索結果とは、エクスポートされる各項目に関する詳細情報を含むドキュメントの概要が含まれています。
ms.openlocfilehash: 45415f25754b4549a919e4ce56853a6ae09a9bdc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531556"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="88cb8-104">コンテンツ検索のレポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="88cb8-104">Export a Content Search report</span></span>

<span data-ttu-id="88cb8-105">Office 365 のセキュリティ コンテンツの検索結果の検索の完全なセットをエクスポートするのではなく&amp;コンプライアンス センターなどから電子的証拠開示のサポート案件に関連付けられているコンテンツの検索はレポートと同じレポートをエクスポートすることができますだけ生成します。検索結果をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-105">Instead of exporting the full set of search results from a Content Search in the Office 365 Security &amp; Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="88cb8-p102">レポートをエクスポートする場合、コンテンツの検索と同じ名前を持つが、 *_ReportsOnly*を追加するフォルダーにダウンロードされます。たとえば、コンテンツの検索は、 *ContosoCase0815*という名前の場合、レポートは*ContosoCase0815_ReportsOnly*をという名前のフォルダーにダウンロードされます。レポートに含まれているドキュメントのリストは、[レポートの内容](#whats-included-in-the-report)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p102">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  . For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  . For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="88cb8-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="88cb8-109">Before you begin</span></span>

- <span data-ttu-id="88cb8-p103">コンテンツの検索レポートをエクスポートするには、Office 365 のセキュリティでのコンプライアンス検索の管理役割を割り当てる必要がある&amp;コンプライアンス センターです。このロールは、組み込みの電子的証拠開示マネージャーおよび組織の管理の役割グループに割り当てられます。組織の管理役割グループに既定で割り当てられますことはありません。詳細についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p103">To export a Content Search report, you have to be assigned the Compliance Search management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager and Organization Management role groups. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="88cb8-p104">レポートをエクスポートするときにローカル コンピューターにダウンロードされる前にデータがマイクロソフト クラウドで独自の Windows Azure ストレージ領域に一時的に格納します。組織が、Azure でエンドポイントに接続できるかどうかを必ず**\*です。 blob.core.windows.net** (ワイルドカードは、エクスポートの一意の識別子を表します)。検索結果のデータは、作成後、2 週間に、Azure のストレージ領域から削除されます。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p104">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="88cb8-117">検索結果をエクスポートする際に使用するコンピューターは、次のシステム要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="88cb8-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="88cb8-118">32 ビットおよび 64 ビット バージョンの Windows 7 およびそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="88cb8-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="88cb8-119">Microsoft.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="88cb8-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="88cb8-120">サポートされているブラウザー:</span><span class="sxs-lookup"><span data-stu-id="88cb8-120">A supported browser:</span></span>
    
    - <span data-ttu-id="88cb8-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="88cb8-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="88cb8-122">または</span><span class="sxs-lookup"><span data-stu-id="88cb8-122">or</span></span>
    
    - <span data-ttu-id="88cb8-123">Microsoft インターネット エクスプ ローラー 10 およびそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="88cb8-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="88cb8-p105">**注:** マイクロソフトではサードパーティ製の拡張機能またはアドオンの ClickOnce アプリケーションを製造します。アドオンまたはサードパーティ製の拡張機能でサポートされていないブラウザーを使用して検索結果のエクスポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 
    
## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="88cb8-126">生成し、コンテンツの検索レポートをダウンロード</span><span class="sxs-lookup"><span data-stu-id="88cb8-126">Generate and download a Content Search report</span></span>

<span data-ttu-id="88cb8-127">生成し、コンテンツの検索レポートをダウンロードする手順は、実際に検索結果をエクスポートするのには非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="88cb8-127">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="88cb8-128">手順 1: エクスポート レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="88cb8-128">Step 1: Generate the report for export</span></span>

<span data-ttu-id="88cb8-p106">最初に、レポートをエクスポートする、コンピューターにダウンロードする準備をします。クラウド、レポート、レポートでは、Microsoft Azure ストレージ領域にドキュメントをアップロードするときです。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p106">The first step is to prepare the report for downloading to your computer exporting. When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="88cb8-131">[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="88cb8-131">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="88cb8-132">職場、学校のアカウントを使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-132">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="88cb8-133">セキュリティ/コンプライアンス センターの左側のウィンドウで、**[検索と調査]** \> **[コンテンツ検索]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-133">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="88cb8-134">**コンテンツの検索**ページで、検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="88cb8-134">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="88cb8-135">詳細ウィンドウで、**コンピューターにレポートをエクスポート**するには、[**レポートの生成**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-135">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="88cb8-p107">検索の結果が 7 日間よりも古い場合は、検索結果を更新するように求められます。このような場合は、エクスポートをキャンセルし、詳細ペインで、選択した検索の**検索結果の更新**] をクリックし、結果を更新した後、レポートのエクスポートを再度起動します。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p107">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="88cb8-138">**レポートをエクスポート**] ページの**検索でこれらの項目を含める**には、次のオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="88cb8-138">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="88cb8-139">インデックス付きのアイテムのみをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="88cb8-139">Export only indexed items</span></span>
    
    - <span data-ttu-id="88cb8-140">インデックス付きのアイテムとインデックスのないアイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="88cb8-140">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="88cb8-141">インデックスのないアイテムのみをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="88cb8-141">Export only unindexed items</span></span>
    
    <span data-ttu-id="88cb8-142">インデックスの項目の詳細については、[一部のコンテンツの検索項目をインデックス](partially-indexed-items-in-content-search.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88cb8-142">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="88cb8-p108">SharePoint ドキュメントのすべてのバージョンの検索の統計情報を含める」を選択します。検索のコンテンツ ソースには、SharePoint または OneDrive ビジネス サイトの場合にのみ、このオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p108">Choose to include search statistics for all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="88cb8-145">**レポートの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-145">Click **Generate report**.</span></span>
    
    <span data-ttu-id="88cb8-p109">検索結果のレポートは、ダウンロードの準備レポート ドキュメントはマイクロソフトのクラウド内の Azure ストレージ領域にアップロードすることを意味します。レポートのダウンロードの準備ができたらは、詳細ペインで、**コンピューターにレポートをエクスポートする**[**レポートのダウンロード**のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p109">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud. When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="88cb8-p110">コンテンツ検索では、電子的証拠開示のサポート案件に関連付けられているレポートをエクスポートすることもできます。これを行うには、**検索&amp;調査** \> **電子的証拠開示**は、サポート案件を選択し、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。[**検索**] ページで、検索を選択し、**エクスポート**] をクリックし、![エクスポートの検索結果のアイコン](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **レポートをエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p110">You can also export a report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="88cb8-151">手順 2: レポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-151">Step 2: Download the report</span></span>

<span data-ttu-id="88cb8-152">次の手順では、Azure のストレージ領域からローカル コンピューターにレポートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-152">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="88cb8-153">**コンピューターにレポートをエクスポートする**] の下に、レポートを生成する検索の詳細ウィンドウで、**レポートのダウンロード**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-153">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="88cb8-154">**レポートのダウンロード**ページが表示され、次が含まれていますまでレポートについての情報がコンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="88cb8-154">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="88cb8-155">ダウンロードされるアイテムの数。</span><span class="sxs-lookup"><span data-stu-id="88cb8-155">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="88cb8-156">ダウンロードされるアイテムの推定合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="88cb8-156">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="88cb8-p111">インデックスまたはインデックスを持たないかどうかがエクスポートされます。インデックス付けされない項目は、形式が認識された、暗号化、または他の理由によりインデックスが作成されなかったアイテムです。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p111">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="88cb8-159">SharePoint ドキュメントのバージョンがダウンロードされるかどうか。</span><span class="sxs-lookup"><span data-stu-id="88cb8-159">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="88cb8-p112">レポートのエクスポート処理の状態です。レポートの準備が完了されていない場合でも、レポートのダウンロードを開始できます。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p112">The status of the report export process. You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="88cb8-p113">**キーをエクスポート**するには、[**クリップボードにコピー**] をクリックします。レポートをダウンロードして、手順 5 でこのキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p113">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="88cb8-164">だれでもことができますインストール、電子的証拠開示のエクスポート ツールを起動し、検索レポートをダウンロードするのにはこのキーを使用して、ためには、パスワードやその他のセキュリティに関連する情報を保護するように、このキーを保護するために対策を講じていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="88cb8-164">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="88cb8-165">**レポートをダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-165">Click **Download report**.</span></span>
    
4. <span data-ttu-id="88cb8-166">**MicrosoftOffice 365 電子的証拠開示のエクスポート ツール**をインストールするメッセージが表示されたら、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-166">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="88cb8-167">**電子情報開示エクスポート ツール**で、手順 2 でコピーしたエクスポート キーを適切なボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="88cb8-167">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="88cb8-168">レポートをダウンロードする場所を指定する**参照**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-168">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="88cb8-169">**[開始]** をクリックして、検索結果をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-169">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="88cb8-p114">**EDiscovery ツールのエクスポート**には、数 (サイズ) の残りのアイテムをダウンロードする推定値を含む、エクスポート プロセスに関するステータス情報が表示されます。エクスポート処理が完了すると、ダウンロードした場所にファイルをアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p114">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="88cb8-p115">電子的証拠開示のサポート案件に関連付けられているコンテンツの検索には、レポートをダウンロードできます。これを行うには、**検索&amp;調査** \> **電子的証拠開示**は、サポート案件を選択し、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。[**エクスポート**] ページで、レポートのエクスポートを選択し、し、詳細ペインで [**レポートのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p115">You can download the report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="88cb8-175">レポートに含まれているもの</span><span class="sxs-lookup"><span data-stu-id="88cb8-175">What's included in the report</span></span>

<span data-ttu-id="88cb8-176">生成し、コンテンツの検索の結果に関するレポートをエクスポートすると、次のドキュメントがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="88cb8-176">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="88cb8-p116">**サマリーのエクスポート**- エクスポートの概要を説明する Excel のドキュメントです。これにより、検索されたコンテンツ ソースの数、各コンテンツの場所、アイテム数の推定、エクスポートは、アイテムの実際の数からの検索結果の数の項目の推定と実際のサイズなどの情報が含まれます。エクスポートするとします。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p116">**Export Summary** - An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="88cb8-p117">インデックス項目の数は推定の検索結果の合計数とダウンロードの検索結果 (検索結果をエクスポートする場合) に記載されている数の合計に含まれているレポートをエクスポートするときにインデックスを持たないアイテムが含まれて場合、サマリー レポートをエクスポートします。つまり、ダウンロードできるように項目の総数は推定結果の合計数とインデックスの項目の合計数です。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p117">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report. In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="88cb8-181">**マニフェスト**がマニフェスト ファイル (XML 形式) で、検索結果に含まれる各アイテムに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="88cb8-181">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="88cb8-p118">**結果**の検索結果をエクスポートするとインデックス付きの各項目に関する情報を含む行を含む、Excel のドキュメントです。電子メールでは、結果のログに、各メッセージに関する情報が含まれているなど。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p118">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="88cb8-184">移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。</span><span class="sxs-lookup"><span data-stu-id="88cb8-184">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="88cb8-185">メッセージが送信または受信された日付。</span><span class="sxs-lookup"><span data-stu-id="88cb8-185">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="88cb8-186">メッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="88cb8-186">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="88cb8-187">メッセージの送信者と受信者。</span><span class="sxs-lookup"><span data-stu-id="88cb8-187">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="88cb8-188">各ドキュメントに関する情報が含まれますビジネス サイトのドキュメント SharePoint と OneDrive から、には結果のログには含みます。</span><span class="sxs-lookup"><span data-stu-id="88cb8-188">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="88cb8-189">ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="88cb8-189">The URL for the document.</span></span>
    
  - <span data-ttu-id="88cb8-190">ドキュメントがあるサイト コレクションの URL。</span><span class="sxs-lookup"><span data-stu-id="88cb8-190">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="88cb8-191">ドキュメントが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="88cb8-191">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="88cb8-192">ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。</span><span class="sxs-lookup"><span data-stu-id="88cb8-192">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="88cb8-193">**結果**レポートに行の数を**インデックス付けされないアイテム**のレポートに表示される項目の合計数を引いたがダウンロードできるよう検索結果の合計数と同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="88cb8-193">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="88cb8-p119">**インデックスの項目**の検索結果に含まれるとインデックスの項目に関する情報を含む、Excel ドキュメント。検索結果のレポートを生成するとき、インデックスの項目を含まない、このレポートは、ダウンロードされますが、空になります。</span><span class="sxs-lookup"><span data-stu-id="88cb8-p119">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results. If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
