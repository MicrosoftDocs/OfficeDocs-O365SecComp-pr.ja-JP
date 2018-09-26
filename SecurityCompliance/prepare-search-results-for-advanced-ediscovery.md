---
title: Office 365 アドバンスト eDiscovery 用に検索結果を準備する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/10/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: Office 365 のセキュリティ コンテンツの検索の結果を準備する方法について&amp;コンプライアンス センター高度な電子的証拠開示ツールを使用してさらに詳しく分析します。
ms.openlocfilehash: f5b10ac7fcfa67f67618c936000832b9bdb7d533
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038310"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a><span data-ttu-id="ac830-103">Office 365 アドバンスト eDiscovery 用に検索結果を準備する</span><span class="sxs-lookup"><span data-stu-id="ac830-103">Prepare search results for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="ac830-p101">Office 365 のセキュリティ、電子的証拠開示のケースに関連付けられている検索後に&amp;コンプライアンス センターが正常に実行、大規模な分析することができます、Office 365 の詳細の開示をさらに分析の検索結果を準備することができます非構造化データは、設定し、訴訟事件に関連するデータの量を削減します。高度な電子的証拠開示の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ac830-p101">After a search that's associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center is successfully run, you can prepare the search results for further analysis with Office 365 Advanced eDiscovery, which lets you analyze large, unstructured data sets and reduce the amount of data that's relevant to a legal case. Advanced eDiscovery features include:</span></span>
  
- <span data-ttu-id="ac830-p102">**光学式文字認識**の高度な電子的証拠開示、光学式文字認識 (OCR) 機能の検索結果を自動的に準備ができたら、画像からテキストを抽出し、この内に読み込まれている、検索結果に含まれています分析の高度な電子的証拠開示します。OCR は、圧縮しないファイルではサポートされて、電子メールの添付ファイルと、イメージが埋め込まれています。これにより、イメージ ファイル内のテキスト コンテンツを (重複の近くに、電子メールのスレッド、テーマ、および予測のコーディング) 高度な電子的証拠開示のテキストの分析機能を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="ac830-p102">**Optical character recognition** - When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images, and includes this with the search results that are loaded in to Advanced eDiscovery for analysis. OCR is supported for loose files, email attachments, and embedded images. This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to the text content in image files.</span></span> 
    
- <span data-ttu-id="ac830-p103">1 人のようなドキュメントのグループを確認するため、**近くにある重複データ検出**には構造、データの確認をより効率的にことができます。これにより、複数の校閲者に同じ文書の別のバージョンを表示する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac830-p103">**Near-duplicate detection** - Lets you structure your data review more efficiently, so one person reviews a group of similar documents. This helps prevent multiple reviewers from having to view different versions of the same document.</span></span> 
    
- <span data-ttu-id="ac830-p104">**電子メールのスレッド**では、メッセージごとに、新しい情報のみに集中できるように、電子メール スレッドの一意なメッセージを識別することができます。電子メールのスレッドでは、2 番目のメッセージには、最初のメッセージが含まれています。同様に、それ以降のメッセージには、以前のすべてのメッセージが含まれています。電子メールのスレッド、スレッド内全体のすべてのメッセージを確認する必要があるされます。</span><span class="sxs-lookup"><span data-stu-id="ac830-p104">**Email threading** - Helps you identify the unique messages in an email thread so you can focus on only the new information in each message. In an email thread, the second message contains the first message. Likewise, later messages contain all the previous messages. Email threading removes the need to review every message in its entirety in an email thread.</span></span> 
    
- <span data-ttu-id="ac830-p105">**テーマ**のヘルプ キーワード検索の統計だけを超えるデータに関する貴重な洞察を得ることです。テーマは、コンテキスト内のドキュメントを表示できるように、関連するドキュメントをグループ化して調査を支援します。テーマを使用して、一連のドキュメントに関連するテーマを表示、すべての重複を確認して関連するデータの 2 次元断面を識別し、できます。</span><span class="sxs-lookup"><span data-stu-id="ac830-p105">**Themes** - Help you get valuable insight about your data beyond just keyword search statistics. Themes help investigations by grouping related documents so you can look at the documents in context. When using themes, you can view the related themes for a set of documents, determine any overlap, and then identify cross-sections of related data.</span></span> 
    
- <span data-ttu-id="ac830-p106">何を探している、(かどうかに関する何か関連するか) を決定することによりシステムの教育には、**コーディングの予測**では少数のドキュメントにします。高度な電子的証拠開示 (、ガイダンスに基づく) を学習を適用し、すべてのデータ セット内でドキュメントを解析するとき。その学習に基づき、高度な電子的証拠開示は、どのドキュメントを参照して、最も可能性の高いケースに関連するのには、どのようなドキュメントを基にすることができますので、関連性のランキングを提供します。</span><span class="sxs-lookup"><span data-stu-id="ac830-p106">**Predictive coding** - Lets you train the system on what you're looking for, by allowing you to make decisions (about whether something is relevant or not) on a small set of documents. Advanced eDiscovery then applies that learning (based on your guidance) when analyzing all of the documents in the data set. Based on that learning, Advanced eDiscovery provides a relevance ranking so you can decide which documents to review based on what document are the most likely to be relevant to the case.</span></span> 
    
- <span data-ttu-id="ac830-p107">**エクスポート データを確認してアプリケーション**の分析を完了し、データ セットを制限したら高度な電子的証拠開示と Office 365 からデータをエクスポートできます。エクスポート パッケージには、書き出されたコンテンツとメタデータの分析からプロパティを含む CSV ファイルが含まれています。このエクスポート パッケージは、電子的証拠開示のレビューのアプリケーションにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ac830-p107">**Exporting data for review applications**  - You can export data from Advanced eDiscovery and Office 365 after you've completed your analysis and reduced the data set. The export package includes a CSV file that contains the properties from the exported content and analytics metadata. This export package can then be imported to an eDiscovery review application.</span></span> 
    
## <a name="before-you-begin"></a><span data-ttu-id="ac830-124">はじめに</span><span class="sxs-lookup"><span data-stu-id="ac830-124">Before you begin</span></span>

- <span data-ttu-id="ac830-p108">高度な電子的証拠開示を使用してユーザーのデータを分析するには、ユーザー (データの保管担当者) 割り当てる必要があります、Office 365 の E5 のライセンスです。または、Office 365 の E1 または E3 のライセンスを持つユーザーが高度な電子的証拠開示のスタンドアロン ライセンスを割り当てることができます。管理者およびコンプライアンス担当者の場合に割り当てられ、データを分析する高度な電子的証拠開示を使用している E5 のライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="ac830-p108">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="ac830-p109">電子的証拠開示マネージャーまたは管理者が Office 365 のセキュリティで電子情報開示する必要が&amp;の高度な電子的証拠開示検索結果を準備するのにはコンプライアンス センターです。電子的証拠開示マネージャーは、電子的証拠開示マネージャーの役割グループのメンバーです。電子情報開示管理者も、電子的証拠開示マネージャーの役割グループのメンバーがその他の電子的証拠開示の権限が割り当てられています。電子的証拠開示に管理者のアクセス許可を割り当てる方法の詳細については、[電子的証拠開示の場合](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)でステップ 1 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac830-p109">You have to be an eDiscovery Manager or an eDiscovery Administrator in the Office 365 Security &amp; Compliance Center to prepare search results for Advanced eDiscovery. An eDiscovery Manager is a member of the eDiscovery Manager role group. An eDiscovery Administrator is also member of the eDiscovery Manager role group, but has been assigned additional eDiscovery privileges. For instructions about assigning eDiscovery Administrator permissions, see Step 1 in [eDiscovery cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="ac830-132">手順 1: 準備する高度な電子的証拠開示の検索結果</span><span class="sxs-lookup"><span data-stu-id="ac830-132">Step 1: Prepare search results for Advanced eDiscovery</span></span>

<span data-ttu-id="ac830-p110">電子的証拠開示のサポート案件に関連付けられた検索結果を準備することができます。高度な電子的証拠開示の検索結果を準備するとき、データがアップロードされ、マイクロソフトのクラウドで独自の Windows Azure ストレージ領域に一時的に格納されています。この時点では、OCR 機能が検索結果内の画像からテキストを抽出します。[ステップ 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)、このテキストおよびその他の検索の高度な電子的証拠開示の場合の結果のデータが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="ac830-p110">You can prepare the results of a search that's associated with an eDiscovery case. When you prepare search results for Advanced eDiscovery, the data is uploaded and temporarily stored in a unique Windows Azure storage area in the Microsoft cloud. It's at this point that the OCR functionality extracts text from images in the search results. In [Step 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), this text and the other search results data is loaded in to the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="ac830-137">セキュリティ&amp;コンプライアンス センターで、**[検索&amp;調査]** \> **[電子情報開示]** の順にクリックし、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac830-137">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="ac830-138">分析のために高度な電子的証拠開示検索結果を準備する場合の横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac830-138">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="ac830-139">[**ホーム**] ページの場合、**検索**] をクリックし、検索を選択し、します。</span><span class="sxs-lookup"><span data-stu-id="ac830-139">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="ac830-140">詳細ペインで [**高度な電子的証拠開示の分析結果\*\*\*\*分析のための準備の結果**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac830-140">In the details pane, under **Analyze results with Advanced eDiscovery**, click **Prepare results for analysis**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac830-141">検索結果が 7 日よりも前のものである場合、検索結果を更新するように求めるダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac830-141">If the search results are older than 7 days, you will be prompted to update the search results.</span></span> 
  
5. <span data-ttu-id="ac830-142">**[分析用に結果を準備]** ページで、次の操作を実行します。 </span><span class="sxs-lookup"><span data-stu-id="ac830-142">On the **Prepare results for analysis** page, do the following:</span></span> 
    
    - <span data-ttu-id="ac830-143">分析のために高度な電子的証拠開示、インデックス付きの項目、項目のインデックスを作成し、インデックスを持たない、またはインデックスを持たないアイテムのみを準備する」を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac830-143">Choose to prepare indexed items, indexed and unindexed items, or only unindexed items for analysis in Advanced eDiscovery.</span></span>
    
    - <span data-ttu-id="ac830-p111">検索条件に一致する SharePoint のドキュメントのすべてのバージョンを含めるかどうかを選択します。検索のコンテンツ ソースには、サイトが含まれる場合にのみ、このオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac830-p111">Choose whether to include all versions of documents found on SharePoint that met the search criteria. This option appears only if the content sources for the search includes sites.</span></span>
    
    - <span data-ttu-id="ac830-146">通知メッセージを送信 (またはコピー) 人の準備プロセスが完了したときに、データが高度な電子的証拠開示で処理する準備がするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac830-146">Specify whether you want a notification message sent (or copied) to a person when the preparation process is completed and the data is ready to be processed in Advanced eDiscovery.</span></span>
    
6. <span data-ttu-id="ac830-147">**[準備]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac830-147">Click **Prepare**.</span></span>
    
    <span data-ttu-id="ac830-148">検索結果の分析と高度な電子的証拠開示の準備ができます。</span><span class="sxs-lookup"><span data-stu-id="ac830-148">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
7. <span data-ttu-id="ac830-p112">詳細ペインで、準備プロセスに関する情報を表示する**準備状態の確認**をクリックします。準備処理が完了したら、分析用のデータを処理するには、[高度な電子的証拠開示の場合に移動できます。</span><span class="sxs-lookup"><span data-stu-id="ac830-p112">In the details pane, click **Check preparation status** to display information about the preparation process. When the preparation process is finished, you can go to the case in Advanced eDiscovery to process the data for analysis.</span></span> 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="ac830-151">手順 2: 高度な電子的証拠開示の場合に検索結果のデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="ac830-151">Step 2: Add the search results data to the case in Advanced eDiscovery</span></span>
<span data-ttu-id="ac830-152"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="ac830-152"></span></span>

<span data-ttu-id="ac830-p113">準備が完了したら、次の手順は、高度な電子的証拠開示に移動し、検索結果にデータを読み込む (これは、マイクロソフトのクラウド内の Azure ストレージ領域にアップロードされている) 高度な電子的証拠開示の場合に。前に説明すると、電子的証拠開示、セキュリティ管理者が必要に高度な電子的証拠開示にアクセスするのには&amp;コンプライアンス センターや高度な電子的証拠開示の管理者です。</span><span class="sxs-lookup"><span data-stu-id="ac830-p113">When the preparation is finished, the next step is to go to Advanced eDiscovery and load the search results data (which have been uploaded to an Azure storage area in the Microsoft cloud ) to the case in Advanced eDiscovery. As previously explained, to access Advanced eDiscovery you have to be an eDiscovery Administrator in the Security &amp; Compliance Center or an administrator in Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac830-155">時間データのセキュリティから&amp;に高度な電子的証拠開示の場合に追加可能なコンプライアンス センターは、によって異なります、電子的証拠開示の検索結果のサイズ。</span><span class="sxs-lookup"><span data-stu-id="ac830-155">The time it takes for the data from the Security &amp; Compliance Center to be available to add to a case in Advanced eDiscovery varies, depending on the size of the results from the eDiscovery search.</span></span> 
  
1. <span data-ttu-id="ac830-156">セキュリティ&amp;コンプライアンス センターで、**[検索&amp;調査]** \> **[電子情報開示]** の順にクリックし、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac830-156">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="ac830-157">内でデータを高度な電子的証拠開示をロードする場合の横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac830-157">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="ac830-158">ケースの **[ホーム]** ページで、**[Advanced eDiscovery]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac830-158">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![スイッチをクリックすると高度な電子的証拠開示のケースを開けるには、[高度な電子的証拠開示](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="ac830-p114">**高度な電子的証拠開示への接続**の進行状況バーが表示されます。高度な電子的証拠開示に接続している場合、大文字と小文字のセットアップ] ページでコンテナーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac830-p114">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![高度な電子的証拠開示に大文字と小文字が表示されます。](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="ac830-p115">これらのコンテナーでは、手順 1 には、[高度な電子的証拠開示の分析のために準備した検索結果を表します。コンテナーの名前が、セキュリティの場合、検索と同じ名前を持って注&amp;コンプライアンス センターです。コンテナー、ボックスの一覧では、準備したものです。さまざまなユーザーが検索結果を高度な電子的証拠開示に備える、対応するコンテナーが一覧に含まれません。</span><span class="sxs-lookup"><span data-stu-id="ac830-p115">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1. Note that the name of the container has the same name as the search in the case in the Security &amp; Compliance Center. The containers in the list are the ones that you prepared. If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
4. <span data-ttu-id="ac830-167">内のコンテナーから検索結果のデータを読み込むには高度な電子的証拠開示の場合に、コンテナーを選択して、[**プロセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac830-167">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="ac830-168">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ac830-168">Next steps</span></span>

<span data-ttu-id="ac830-p116">電子情報開示の結果の後検索次の手順は、高度な電子的証拠開示ツールを使用してデータを分析し、特定の法的事例への応答の内容を識別する場合に追加されます。高度な電子的証拠開示を使用する方法の詳細については、[電子的証拠開示の Office 365 の詳細](office-365-advanced-ediscovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac830-p116">After the results of an eDiscovery search are added to a case, the next step is to use the Advanced eDiscovery tools to analyze the data and identify the content that's responsive to a specific legal case. For information about using Advanced eDiscovery, see [Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="ac830-171">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ac830-171">More information</span></span>

<span data-ttu-id="ac830-p117">検索結果に含まれるすべての RMS で暗号化された電子メール メッセージは、分析のために高度な電子的証拠開示を準備すると、復号化されます。この復号化機能は、電子的証拠開示マネージャーの役割グループのメンバーに対して既定で有効です。復号する RMS 管理の役割がこのロール グループに割り当てられているためにです。次のような電子メール メッセージを復号化について注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac830-p117">Any RMS-encrypted email messages that are included in the search results will be decrypted when you prepare them for analysis in Advanced eDiscovery. This decryption capability is enabled by default for members of the eDiscovery Manager role group. This is because the RMS Decrypt management role is assigned to this role group. Keep the following things in mind about decrypting email messages:</span></span>
  
- <span data-ttu-id="ac830-p118">現在、この復号化機能には、ビジネス サイトの SharePoint と OneDrive からの暗号化されたコンテンツが含まれていません。RMS で暗号化された電子メール メッセージだけはそれらをエクスポートすると、復号化します。</span><span class="sxs-lookup"><span data-stu-id="ac830-p118">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites. Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="ac830-178">RMS で暗号化された電子メール メッセージ、添付ファイル (ドキュメント、別の電子メール メッセージなど) も暗号化されている場合は、最上位レベルの電子メール メッセージのみが復号化します。</span><span class="sxs-lookup"><span data-stu-id="ac830-178">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="ac830-p119">分析のために高度な電子的証拠開示検索結果を準備する際は、RMS で暗号化されたメッセージを復号化を禁止する場合は、する必要があります (組み込みの電子証拠開示マネージャーの役割グループをコピーするには)、カスタムの役割グループを作成し、RMS を削除し、カスタムの役割グループから管理役割を復号化します。カスタム役割グループのメンバーとしてメッセージを復号化したくない人を追加します。</span><span class="sxs-lookup"><span data-stu-id="ac830-p119">If you need to prevent someone from decrypting RMS-encrypted messages when preparing search results for analysis in Advanced eDiscovery, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group. Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>
