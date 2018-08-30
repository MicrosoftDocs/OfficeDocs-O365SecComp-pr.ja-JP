---
title: Advanced eDiscovery のために Office 365 以外のコンテンツをインポートする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 5/25/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: 方法、Azure に O365 に格納されていないコンテンツをインポートする手順を実行する blob AeD を分析するため
ms.openlocfilehash: ab6c7ac76a159603a34719aa8edb51de3a4fabbb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532813"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a><span data-ttu-id="48371-103">Advanced eDiscovery のために Office 365 以外のコンテンツをインポートする</span><span class="sxs-lookup"><span data-stu-id="48371-103">Import non-Office 365 content for Advanced eDiscovery analysis</span></span>

<span data-ttu-id="48371-p101">電子的証拠開示の Office 365 の詳細を分析する必要がありますすべてのドキュメントは、Office 365 で生活しています。非 Office 365 の内容とケースのリンク、Azure ストレージの blob に (PST ファイル) を除く Office 365 のライブし、高度な電子的証拠開示で解析されていないドキュメントをアップロードすること、高度な電子的証拠開示の機能をインポートします。この手順では、分析のために高度な電子的証拠開示に、Office 365 以外のドキュメントを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="48371-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48371-p102">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="48371-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48371-p103">Office 365 以外のコンテンツのため、Office 365 の高度な電子的証拠開示のデータ ・ ストレージ ・ アドオン サブスクリプションを購入できます。これは、高度な電子的証拠開示を使用して分析するのにはコンテンツだけで利用可能です。[購入または編集、およびビジネス向けの Office 365 用のアドオン](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)で手順を実行し、Office 365 の高度な電子的証拠開示のストレージ ・ アドオンを購入します。</span><span class="sxs-lookup"><span data-stu-id="48371-p103">You can purchase an Office 365 Advanced eDiscovery data storage add-on subscription for your non-Office 365 content. This is exclusively available for content that is to be analyzed with Advanced eDiscovery. Follow the steps in [Buy or edit and add-on for Office 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Office 365 Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="48371-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="48371-112">Before you begin</span></span>

<span data-ttu-id="48371-113">この手順で説明したように非 Office 365 のアップロード機能を使用するがあることが必要です。</span><span class="sxs-lookup"><span data-stu-id="48371-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="48371-114">コンプライアンスの高度なアドオンと E5 のサブスクリプションの Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="48371-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="48371-115">Office 365 以外のコンテンツがアップロードされるすべての通告は、コンプライアンスの高度なアドオンと E5 のライセンス E3 を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="48371-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="48371-116">既存の電子的証拠開示ケース</span><span class="sxs-lookup"><span data-stu-id="48371-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="48371-p104">保管担当者ごとの 1 つのフォルダーは、この形式の*alias@domainname*では、フォルダーの名前のフォルダーにアップロードするすべてのファイルが収集されます。*Alias@domainname*は、Office 365 のユーザーのエイリアスとドメインである必要があります。*Alias@domainname*のすべてのフォルダーは、ルート フォルダーに収集できます。ルート フォルダーは、 *alias@domainname*フォルダーを含めることができますのみ、必要があります圧縮しないファイルのルート フォルダー</span><span class="sxs-lookup"><span data-stu-id="48371-p104">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  . The  *alias@domainname*  must be users Office 365 alias and domain. You can collect all the  *alias@domainname*  folders into a root folder. The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="48371-121">電子的証拠開示マネージャーまたは管理者の電子的証拠開示のいずれかのアカウント</span><span class="sxs-lookup"><span data-stu-id="48371-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="48371-122">-Office 365 以外のコンテンツのフォルダー構造にアクセスできるコンピューターにインストールされている[Microsoft Azure ストレージ ・ ツール](https://aka.ms/downloadazcopy)です。</span><span class="sxs-lookup"><span data-stu-id="48371-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="48371-123">高度な電子的証拠開示に Office 365 以外のコンテンツをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="48371-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="48371-p105">電子的証拠開示マネージャーまたは管理者の電子的証拠開示では、**電子的証拠開示**を Office 365 以外のデータをアップロードする場合を開きます。サポート案件を作成する場合を参照してください[電子的証拠開示の場合は、Office 365 のセキュリティを管理する&amp;コンプライアンス センター](manage-ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="48371-p105">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to. If you need to create a case, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="48371-126">**高度な電子的証拠開示に切り替える**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48371-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="48371-127">[**ソースの種類**には、**非 Office 365 のデータ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="48371-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="48371-p106">**追加のコンテナー**をクリックします。コンテナーの名前し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="48371-p106">Click **Add container**. Name the container and add a description.</span></span>
    
5. <span data-ttu-id="48371-130">コンテナーの一覧から新たに追加されたコンテナーを選択し、コンテナーの詳細ペインに表示し、ウィンドウを URL をコピー</span><span class="sxs-lookup"><span data-stu-id="48371-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="48371-131">管理者としてコマンド プロンプトを開き、インストールされている AzCopy があるフォルダーにディレクトリを変更する.</span><span class="sxs-lookup"><span data-stu-id="48371-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="48371-132">次のようにファイルをアップロードするのには AzCopy コマンド ・ ラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="48371-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="48371-p107">AzCopy/Source:"*ローカル マシン上のルート フォルダーへの完全パス*」/Dest:"*までコンテナーの URL が、ですか?* 」/DestSAS:」からコンテナーの url の残りの部分を *、でしょうか。最後に*/秒</span><span class="sxs-lookup"><span data-stu-id="48371-p107">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*  " /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="48371-135">たとえば、これらの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="48371-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="48371-136">ルート フォルダーの C:\Collected データ</span><span class="sxs-lookup"><span data-stu-id="48371-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="48371-137">コンテナー url -https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&ampは sr = c&amp;si = NonOfficeData15 %7 C 0&amp;sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA %3 D</span><span class="sxs-lookup"><span data-stu-id="48371-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="48371-138">AzCopy コマンドラインの構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="48371-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="48371-139">Azcopy の詳細については構文を参照してください、 [Windows 上で AzCopy を使用してデータを転送](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)します。</span><span class="sxs-lookup"><span data-stu-id="48371-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="48371-140">ユーザーごとに 1 つのルート フォルダーが存在する必要があり、フォルダー名は、 *alias@domainname*の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="48371-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="48371-p108">フォルダーが、アップロードを完了するが高度な電子的証拠開示に戻ります。アップロードしたフォルダー内のコンテンツは、高度な電子的証拠開示で処理する準備ができました。コンテナーを選択し、[プロセス] をクリックします。高度な電子的証拠開示の詳細については処理を参照してください、[プロセスのモジュールを実行し Office 365 の高度な電子的証拠の開示にデータを読み込む](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="48371-p108">Once the folders have finished uploading, switch back to Advanced eDiscovery. The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery. Select the container and click the Process button. For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="48371-p109">コンテナーは、高度な電子的証拠開示で正常に処理されて後、は、Azure で SAS ストレージに新しいコンテンツを追加することができなくなります。その他のコンテンツの収集し分析の高度な電子的証拠開示の場合に追加する、新しい**非 Office 365 のデータ**コンテナーを作成してこの手順を繰り返してください。</span><span class="sxs-lookup"><span data-stu-id="48371-p109">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure. If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="48371-147">コンテナーの*フォルダーの名前付けの問題により正常に処理されない*問題を修正し、まだなら新しいコンテナーと再接続を作成し、この資料の手順を使用してもう一度アップロードします。</span><span class="sxs-lookup"><span data-stu-id="48371-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span> 
  

