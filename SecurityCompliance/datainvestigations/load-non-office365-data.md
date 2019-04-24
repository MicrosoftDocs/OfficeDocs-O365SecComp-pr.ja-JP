---
title: Office 以外の365データを証拠に読み込む
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f5478d89d71db22e710b5d5fcab397ae8d6aee56
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259565"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="3d3c1-102">Office 以外の365データを証拠に読み込む</span><span class="sxs-lookup"><span data-stu-id="3d3c1-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="3d3c1-103">office 365 の高度な電子情報開示で分析する必要があるすべてのドキュメントが office 365 に存在するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="3d3c1-104">advanced ediscovery の office 365 以外のコンテンツインポート機能を使用すると、office 365 に存在しないドキュメントを作業セットにアップロードして、advanced ediscovery で分析することができます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="3d3c1-105">この手順では、非 Office 365 ドキュメントを分析のために上級電子情報開示に移行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="3d3c1-106">高度な電子情報開示では、組織の高度なコンプライアンスアドオンまたは E5 サブスクリプションに Office 365 E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="3d3c1-107">その計画がなく、高度な電子情報開示を試行する必要がある場合は、Office 365 Enterprise E5 の試用版にサインアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3d3c1-108">始める前に</span><span class="sxs-lookup"><span data-stu-id="3d3c1-108">Before you begin</span></span>
<span data-ttu-id="3d3c1-109">この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="3d3c1-110">高度なコンプライアンスアドオンまたは E5 サブスクリプションを備えた Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="3d3c1-111">Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンまたは E5 ライセンスを含む E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="3d3c1-112">既存の電子情報開示ケース。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="3d3c1-113">収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前が*エイリアス @ domainname*の形式になっているフォルダーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-113">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* .</span></span> <span data-ttu-id="3d3c1-114">*エイリアス @ domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-114">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="3d3c1-115">すべての*エイリアス @ domainname*フォルダーをルートフォルダーに収集できます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-115">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="3d3c1-116">ルートフォルダーに含めることができるのは、 *@ domainname* folders のエイリアスのみです。ルートフォルダーには圧縮されていないファイルは存在しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-116">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="3d3c1-117">Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされている、電子情報開示マネージャーまたは電子情報開示管理者の Microsoft Azure Storage Tools のどちらかのアカウント。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="3d3c1-118">azcopy をインストールします。これは、ここから行うことができます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="3d3c1-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="3d3c1-119">Office 以外の365コンテンツを上級電子情報開示にアップロードする</span><span class="sxs-lookup"><span data-stu-id="3d3c1-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="3d3c1-120">電子情報開示マネージャーまたは電子情報開示管理者として、Advanced ediscovery を開き、Office 以外の365データのアップロード先となるケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-120">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="3d3c1-121">[**作業設定**] タブをクリックし、Office 以外の365データを読み込む作業セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-121">Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="3d3c1-122">作業セットをまだ作成していない場合は、ここで作成できます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-122">If you have not already created a working set, you can do so now.</span></span>  <span data-ttu-id="3d3c1-123">最後に、[動作**設定の管理**] をクリックし、[Office ではない365データ] セクションの [**アップロードを表示**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-123">Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="3d3c1-124">[**ファイルのアップロード**] ボタンをクリックして、Office 365 以外のデータインポートウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="3d3c1-126">ウィザードの最初の手順では、ファイルをアップロードするために、セキュリティで保護された Azure blob を準備するだけです。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-126">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="3d3c1-127">準備が整ったら、[**次へ: ファイルのアップロード**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-127">Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![Office 以外の365インポート-準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="3d3c1-129">[**ファイルのアップロード**] ステップで、**ファイルの場所へのパス**を指定します。この場合、インポートする予定の非 Office 365 データが配置されます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-129">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="3d3c1-130">正しい場所を設定することにより、azcopy コマンドが正しく更新されます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-130">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="3d3c1-131">azcopy をまだインストールしていない場合は、ここから実行できます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="3d3c1-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="3d3c1-132">[**クリップボードにコピー** ] リンクをクリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-132">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="3d3c1-133">windows コマンドプロンプトを起動し、コマンドを貼り付けて、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-133">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="3d3c1-134">ファイルは、次の手順のために secure Azure blob ストレージにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-134">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Office 以外の365インポート-ファイルのアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Office 以外の365インポート-azcopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="3d3c1-137">最後に、Security & コンプライアンスに戻って、[**次へ: ファイルの処理**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-137">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="3d3c1-138">これにより、アップロードしたファイルの処理、テキストの抽出、およびインデックス作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-138">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="3d3c1-139">処理の進行状況を追跡するには、[**ジョブ**] タブを使用します。 完了すると、新しいファイルがワーキングセットで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-139">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.</span></span>  <span data-ttu-id="3d3c1-140">処理が完了したら、ウィザードを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="3d3c1-140">Once processing is complete, you can dismiss the wizard.</span></span>

![Office 以外の365インポート処理ファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

