---
title: Office 365 アドバンスト eDiscovery 用に検索結果を準備する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: 高度な電子情報開示ツールを使用して詳細な分析を行う&amp;ために、Office 365 セキュリティコンプライアンスセンターでコンテンツ検索の結果を準備する方法について説明します。
ms.openlocfilehash: de96e06dcbb5ae9a3cbf80b66f976e6ffdfd5b0e
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296920"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a><span data-ttu-id="aa02c-103">Office 365 アドバンスト eDiscovery 用に検索結果を準備する</span><span class="sxs-lookup"><span data-stu-id="aa02c-103">Prepare search results for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="aa02c-p101">office 365 セキュリティ&amp; /コンプライアンスセンターの電子情報開示ケースに関連付けられた検索が正常に実行されると、office 365 Advanced eDiscovery を使用してさらに分析するための検索結果を準備することができます。これにより、大規模な分析を行うことができます。構造化されていないデータを設定し、訴訟に関連するデータ量を減らします。高度な電子情報開示機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p101">After a search that's associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center is successfully run, you can prepare the search results for further analysis with Office 365 Advanced eDiscovery, which lets you analyze large, unstructured data sets and reduce the amount of data that's relevant to a legal case. Advanced eDiscovery features include:</span></span>
  
- <span data-ttu-id="aa02c-p102">**光学式文字認識**-高度な電子情報開示の検索結果を準備するときに、光学式文字認識 (ocr) 機能によって画像からテキストが自動的に抽出され、次のような検索結果が表示されます。分析のための高度な電子情報開示。OCR は、ルースファイル、電子メールの添付ファイル、および埋め込み画像に対してサポートされています。これにより、高度な電子情報開示 (ほぼ重複、電子メールスレッド、テーマ、予測可能コーディング) のテキスト分析機能を画像ファイル内のテキストコンテンツに適用することができます。高度な電子情報開示 OCR では、次の画像ファイル形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p102">**Optical character recognition** - When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images, and includes this with the search results that are loaded in to Advanced eDiscovery for analysis. OCR is supported for loose files, email attachments, and embedded images. This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to the text content in image files. Advanced eDiscovery OCR supports the following formats for image files:</span></span>

    - <span data-ttu-id="aa02c-110">GIF</span><span class="sxs-lookup"><span data-stu-id="aa02c-110">GIF</span></span>
    - <span data-ttu-id="aa02c-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="aa02c-111">JPEG</span></span>
    - <span data-ttu-id="aa02c-112">.jpg</span><span class="sxs-lookup"><span data-stu-id="aa02c-112">JPG</span></span>
    - <span data-ttu-id="aa02c-113">PNG</span><span class="sxs-lookup"><span data-stu-id="aa02c-113">PNG</span></span>
    - <span data-ttu-id="aa02c-114">TIFF</span><span class="sxs-lookup"><span data-stu-id="aa02c-114">TIFF</span></span>
    
- <span data-ttu-id="aa02c-p103">**重複の検出**-データのレビューをより効率的に構成できるので、1人のユーザーが類似したドキュメントのグループをレビューできます。これにより、複数の校閲者が同じ文書の異なるバージョンを表示するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p103">**Near-duplicate detection** - Lets you structure your data review more efficiently, so one person reviews a group of similar documents. This helps prevent multiple reviewers from having to view different versions of the same document.</span></span> 
    
- <span data-ttu-id="aa02c-p104">**電子メール**スレッド-電子メールスレッド内の一意のメッセージを特定し、各メッセージの新しい情報のみに集中することができるようにします。電子メールスレッドでは、2番目のメッセージに最初のメッセージが含まれます。同様に、以降のメッセージには、以前のすべてのメッセージが含まれています。電子メールスレッドを削除すると、電子メールスレッド内のすべてのメッセージを完全に確認する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p104">**Email threading** - Helps you identify the unique messages in an email thread so you can focus on only the new information in each message. In an email thread, the second message contains the first message. Likewise, later messages contain all the previous messages. Email threading removes the need to review every message in its entirety in an email thread.</span></span> 
    
- <span data-ttu-id="aa02c-p105">**テーマ**-キーワード検索統計だけでなく、データに関する貴重な洞察を得るのに役立ちます。テーマでは、関連するドキュメントをグループ化して、コンテキスト内でドキュメントを表示できるようにすることで調査を支援します。テーマを使用すると、一連のドキュメントに関連するテーマを表示したり、重なりを特定したり、関連するデータの複数のセクションを識別したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p105">**Themes** - Help you get valuable insight about your data beyond just keyword search statistics. Themes help investigations by grouping related documents so you can look at the documents in context. When using themes, you can view the related themes for a set of documents, determine any overlap, and then identify cross-sections of related data.</span></span> 
    
- <span data-ttu-id="aa02c-p106">**予測コーディング**-小さなドキュメントのセットに対して意思決定 (関連性があるかどうかについての判断) を可能にすることにより、探しているものでシステムをトレーニングできます。高度な電子情報開示では、データセット内のすべてのドキュメントを分析する際に、(ガイダンスに基づいて) そのラーニングを適用します。その学習に基づいて、Advanced eDiscovery は関連性のランク付けを行って、どのドキュメントがケースに最も関連する可能性があるかに基づいてレビューするドキュメントを決定できます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p106">**Predictive coding** - Lets you train the system on what you're looking for, by allowing you to make decisions (about whether something is relevant or not) on a small set of documents. Advanced eDiscovery then applies that learning (based on your guidance) when analyzing all of the documents in the data set. Based on that learning, Advanced eDiscovery provides a relevance ranking so you can decide which documents to review based on what document are the most likely to be relevant to the case.</span></span> 
    
- <span data-ttu-id="aa02c-p107">**レビューアプリケーション用のデータのエクスポート**-分析を完了し、データセットを縮小した後で、高度な電子情報開示と Office 365 のデータをエクスポートできます。エクスポートパッケージには、エクスポートされたコンテンツと分析メタデータのプロパティを含む CSV ファイルが含まれています。このエクスポートパッケージは、電子情報開示レビューアプリケーションにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p107">**Exporting data for review applications**  - You can export data from Advanced eDiscovery and Office 365 after you've completed your analysis and reduced the data set. The export package includes a CSV file that contains the properties from the exported content and analytics metadata. This export package can then be imported to an eDiscovery review application.</span></span> 
    
## <a name="before-you-begin"></a><span data-ttu-id="aa02c-130">はじめに</span><span class="sxs-lookup"><span data-stu-id="aa02c-130">Before you begin</span></span>

- <span data-ttu-id="aa02c-p108">Advanced eDiscovery を使用してユーザーのデータを分析するには、ユーザー (データの保管担当者) に Office 365 E5 ライセンスが割り当てられている必要があります。または、Office 365 E1 または E3 ライセンスを持つユーザーに、Advanced eDiscovery スタンドアロンライセンスを割り当てることができます。ケースに割り当てられ、高度な電子情報開示を使用してデータを分析する管理者とコンプライアンス責任者は、E5 ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p108">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="aa02c-p109">高度な電子情報開示の検索結果を準備するには、Office 365 &amp;セキュリティコンプライアンスセンターの電子情報開示マネージャーまたは電子情報開示管理者である必要があります。電子情報開示マネージャーは、電子情報開示マネージャーの役割グループのメンバーです。電子情報開示管理者は、電子情報開示マネージャーの役割グループのメンバーでもありますが、追加の電子情報開示特権が割り当てられています。電子情報開示管理者のアクセス許可を割り当てる手順については、「 [Office 365 セキュリティ & コンプライアンスセンターでの電子情報開示のケース](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)」のステップ1を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p109">You have to be an eDiscovery Manager or an eDiscovery Administrator in the Office 365 Security &amp; Compliance Center to prepare search results for Advanced eDiscovery. An eDiscovery Manager is a member of the eDiscovery Manager role group. An eDiscovery Administrator is also member of the eDiscovery Manager role group, but has been assigned additional eDiscovery privileges. For instructions about assigning eDiscovery Administrator permissions, see Step 1 in [eDiscovery cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="aa02c-138">手順 1: 高度な電子情報開示の検索結果を準備する</span><span class="sxs-lookup"><span data-stu-id="aa02c-138">Step 1: Prepare search results for Advanced eDiscovery</span></span>

<span data-ttu-id="aa02c-p110">電子情報開示ケースに関連付けられている検索の結果を準備することができます。高度な電子情報開示の検索結果を準備すると、データがアップロードされ、Microsoft クラウド内の一意の Windows Azure ストレージ領域に一時的に格納されます。この時点で、OCR 機能が検索結果の画像からテキストを抽出します。[手順 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)では、このテキストとその他の検索結果データが、Advanced eDiscovery のケースに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p110">You can prepare the results of a search that's associated with an eDiscovery case. When you prepare search results for Advanced eDiscovery, the data is uploaded and temporarily stored in a unique Windows Azure storage area in the Microsoft cloud. It's at this point that the OCR functionality extracts text from images in the search results. In [Step 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), this text and the other search results data is loaded in to the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="aa02c-143">セキュリティ&amp;コンプライアンス センターで、**[検索&amp;調査]** \> **[電子情報開示]** の順にクリックし、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="aa02c-143">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="aa02c-144">高度な電子情報開示で分析のために検索結果を準備するケースの横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa02c-144">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="aa02c-145">ケースの**ホーム**ページで、[**検索**] をクリックし、検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa02c-145">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="aa02c-146">詳細ウィンドウで、[**詳細な電子情報開示を使用して結果を分析**する] の下の [**分析結果の準備**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa02c-146">In the details pane, under **Analyze results with Advanced eDiscovery**, click **Prepare results for analysis**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aa02c-147">検索結果が 7 日よりも前のものである場合、検索結果を更新するように求めるダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-147">If the search results are older than 7 days, you will be prompted to update the search results.</span></span> 
  
5. <span data-ttu-id="aa02c-148">**[分析用に結果を準備]** ページで、次の操作を実行します。 </span><span class="sxs-lookup"><span data-stu-id="aa02c-148">On the **Prepare results for analysis** page, do the following:</span></span> 
    
    - <span data-ttu-id="aa02c-149">インデックス付けされたアイテム、インデックス付きアイテムとインデックスのないアイテム、または詳細な電子情報開示での分析用にインデックスのないアイテムのみを準備することを選択します</span><span class="sxs-lookup"><span data-stu-id="aa02c-149">Choose to prepare indexed items, indexed and unindexed items, or only unindexed items for analysis in Advanced eDiscovery.</span></span>
    
    - <span data-ttu-id="aa02c-p111">検索条件に一致する SharePoint で検出されたすべてのバージョンのドキュメントを含めるかどうかを選択します。このオプションは、検索のコンテンツソースにサイトが含まれている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p111">Choose whether to include all versions of documents found on SharePoint that met the search criteria. This option appears only if the content sources for the search includes sites.</span></span>
    
    - <span data-ttu-id="aa02c-152">準備プロセスが完了し、データを Advanced eDiscovery で処理する準備ができたときに、ユーザーに通知メッセージを送信 (またはコピー) するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="aa02c-152">Specify whether you want a notification message sent (or copied) to a person when the preparation process is completed and the data is ready to be processed in Advanced eDiscovery.</span></span>
    
6. <span data-ttu-id="aa02c-153">**[準備]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa02c-153">Click **Prepare**.</span></span>
    
    <span data-ttu-id="aa02c-154">検索結果は、高度な電子情報開示を使用して分析のために準備されます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-154">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
7. <span data-ttu-id="aa02c-p112">詳細ウィンドウで、[**準備状況の確認**] をクリックして、準備プロセスに関する情報を表示します。準備プロセスが終了したら、Advanced eDiscovery のケースに進み、分析のためにデータを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p112">In the details pane, click **Check preparation status** to display information about the preparation process. When the preparation process is finished, you can go to the case in Advanced eDiscovery to process the data for analysis.</span></span> 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="aa02c-157">手順 2: 高度な電子情報開示のケースに検索結果データを追加する</span><span class="sxs-lookup"><span data-stu-id="aa02c-157">Step 2: Add the search results data to the case in Advanced eDiscovery</span></span>
<span data-ttu-id="aa02c-158"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="aa02c-158"></span></span>

<span data-ttu-id="aa02c-p113">準備が完了したら、次の手順として、advanced ediscovery に進み、高度な電子情報開示のケースに、検索結果データ (Microsoft クラウド内の Azure ストレージ領域にアップロードされています) を読み込みます。前述のとおり、高度な電子情報開示にアクセスするには、セキュリティ&amp;コンプライアンスセンターの電子情報開示管理者であるか、高度な電子情報開示の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p113">When the preparation is finished, the next step is to go to Advanced eDiscovery and load the search results data (which have been uploaded to an Azure storage area in the Microsoft cloud ) to the case in Advanced eDiscovery. As previously explained, to access Advanced eDiscovery you have to be an eDiscovery Administrator in the Security &amp; Compliance Center or an administrator in Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa02c-161">上級電子情報開示のケースに追加できるよう&amp;にセキュリティコンプライアンスセンターからのデータを取得するのにかかる時間は、電子情報開示検索の結果のサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="aa02c-161">The time it takes for the data from the Security &amp; Compliance Center to be available to add to a case in Advanced eDiscovery varies, depending on the size of the results from the eDiscovery search.</span></span> 
  
1. <span data-ttu-id="aa02c-162">セキュリティ&amp;コンプライアンス センターで、**[検索&amp;調査]** \> **[電子情報開示]** の順にクリックし、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="aa02c-162">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="aa02c-163">高度な電子情報開示でにデータを読み込むケースの横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa02c-163">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="aa02c-164">ケースの **[ホーム]** ページで、**[Advanced eDiscovery]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa02c-164">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![[高度な電子情報開示に切り替え] をクリックして、高度な電子情報開示でケースを開きます。](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="aa02c-p114">**[高度な電子情報開示**の進行状況バーへの接続] が表示されます。上級電子情報開示に接続されている場合は、ケースのセットアップページにコンテナーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p114">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![詳細な電子情報開示でケースが表示される](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="aa02c-p115">これらのコンテナーは、手順1でアドバンスト eDiscovery で分析するために準備した検索結果を表します。セキュリティ&amp; /コンプライアンスセンターの場合、コンテナーの名前は検索と同じ名前になることに注意してください。リスト内のコンテナーは、準備したものです。上級電子情報開示のために別のユーザーが検索結果を準備している場合、対応するコンテナーはリストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p115">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1. Note that the name of the container has the same name as the search in the case in the Security &amp; Compliance Center. The containers in the list are the ones that you prepared. If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
4. <span data-ttu-id="aa02c-173">高度な電子情報開示のケースに、コンテナーからの検索結果データを読み込むには、コンテナーを選択し、[**処理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa02c-173">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="aa02c-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="aa02c-174">Next steps</span></span>

<span data-ttu-id="aa02c-p116">電子情報開示検索の結果をケースに追加した後、次の手順では、高度な電子情報開示ツールを使用してデータを分析し、特定の訴訟に対応しているコンテンツを特定します。advanced ediscovery の使用方法については、「 [Office 365 advanced ediscovery](office-365-advanced-ediscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p116">After the results of an eDiscovery search are added to a case, the next step is to use the Advanced eDiscovery tools to analyze the data and identify the content that's responsive to a specific legal case. For information about using Advanced eDiscovery, see [Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="aa02c-177">詳細情報</span><span class="sxs-lookup"><span data-stu-id="aa02c-177">More information</span></span>

<span data-ttu-id="aa02c-p117">検索結果に含まれる rm で暗号化された電子メールメッセージは、上級電子情報開示で分析するために準備するときに復号化されます。この暗号化解除機能は、電子情報開示マネージャーの役割グループのメンバーに対して既定で有効になっています。これは、RMS の解読管理役割がこの役割グループに割り当てられるためです。電子メールメッセージの暗号化解除については、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p117">Any RMS-encrypted email messages that are included in the search results will be decrypted when you prepare them for analysis in Advanced eDiscovery. This decryption capability is enabled by default for members of the eDiscovery Manager role group. This is because the RMS Decrypt management role is assigned to this role group. Keep the following things in mind about decrypting email messages:</span></span>
  
- <span data-ttu-id="aa02c-p118">現時点では、この復号化機能には、SharePoint および OneDrive for business サイトの暗号化されたコンテンツは含まれていません。RMS で暗号化された電子メールメッセージのみが、エクスポート時に復号化されます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p118">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites. Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="aa02c-184">RMS で暗号化された電子メールメッセージに、添付ファイル (ドキュメントや別の電子メールメッセージなど) が含まれている場合は、最上位の電子メールメッセージのみが復号化されます。</span><span class="sxs-lookup"><span data-stu-id="aa02c-184">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="aa02c-p119">上級電子情報開示で分析のための検索結果を準備するときに、他のユーザーが RMS で暗号化されたメッセージの暗号化を解除できないようにする必要がある場合は、(組み込みの電子情報開示マネージャーの役割グループをコピーして) カスタムの役割グループを作成してから、rms を削除する必要があります。カスタム役割グループの管理役割の暗号化を解除します。その後、メッセージの暗号化を解除しないユーザーを、カスタム役割グループのメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="aa02c-p119">If you need to prevent someone from decrypting RMS-encrypted messages when preparing search results for analysis in Advanced eDiscovery, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group. Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>
