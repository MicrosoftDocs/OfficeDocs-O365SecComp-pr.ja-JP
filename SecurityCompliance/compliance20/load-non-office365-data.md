---
title: レビュー セットに Office 365 以外のデータを読み込む
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
ms.openlocfilehash: 60775002d5ebec83aacbec350a044b9d6ffeb461
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834963"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="92114-102">レビュー セットに Office 365 以外のデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="92114-102">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="92114-103">Office 365 の高度な電子情報開示で分析する必要があるすべてのドキュメントが Office 365 に存在するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="92114-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="92114-104">Advanced eDiscovery の Office 365 以外のコンテンツインポート機能を使用すると、Office 365 に存在しないドキュメントをレビューセットにアップロードして、高度な電子情報開示で分析することができます。</span><span class="sxs-lookup"><span data-stu-id="92114-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a review set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="92114-105">この手順では、非 Office 365 ドキュメントを分析のために上級電子情報開示に移行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="92114-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="92114-106">高度な電子情報開示では、組織の高度なコンプライアンスアドオンまたは E5 サブスクリプションに Office 365 E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="92114-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="92114-107">その計画がなく、高度な電子情報開示を試行する必要がある場合は、Office 365 Enterprise E5 の試用版にサインアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="92114-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="92114-108">始める前に</span><span class="sxs-lookup"><span data-stu-id="92114-108">Before you begin</span></span>

<span data-ttu-id="92114-109">この記事の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92114-109">Using the upload Non-Office 365 feature as described in this article requires that you have the following:</span></span>

- <span data-ttu-id="92114-110">Office 365 または Microsoft 365 E5 サブスクリプション、または Advanced コンプライアンスアドオンサブスクリプションを使用した E3 サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="92114-110">An Office 365 or Microsoft 365 E5 subscription or an E3 subscription with the Advanced Compliance add-on subscription.</span></span>

- <span data-ttu-id="92114-111">Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンライセンスを備えた E3 ライセンスが必要です。または、E5 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="92114-111">All custodians whose non-Office 365 content will be uploaded must have E3 license with an Advanced Compliance add-on license or have an E5 license.</span></span>

- <span data-ttu-id="92114-112">既存の高度な電子情報開示ケース。</span><span class="sxs-lookup"><span data-stu-id="92114-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="92114-113">関連付けられている Office 以外の365データをアップロードする前に、保管担当者をケースに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92114-113">Custodians must be added to the case before you upload the non-Office 365 data that's associated to them.</span></span>

- <span data-ttu-id="92114-114">アップロードされるすべてのファイルは、特定の保管担当者に関連付けられているフォルダーに格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92114-114">All files that will be uploaded must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="92114-115">これらのフォルダーの名前には、*エイリアス @ domainname*のような名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="92114-115">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="92114-116">*エイリアス @ domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="92114-116">The *alias@domainname* must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="92114-117">すべての*エイリアス @ domainname*フォルダーをルートフォルダーに収集できます。</span><span class="sxs-lookup"><span data-stu-id="92114-117">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="92114-118">ルートフォルダーには、*別名 @ domainname* folders のみを含めることができます。ルートフォルダーでは、圧縮されていないファイルを使用できません。</span><span class="sxs-lookup"><span data-stu-id="92114-118">The root folder can only contain the *alias@domainname* folders; loose files aren't allowed in the root folder.</span></span>

   <span data-ttu-id="92114-119">たとえば、アップロードする Office 365 以外のデータのフォルダー構造は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="92114-119">For example, the folder structure for the non-Office 365 data that you want to upload would be similar to the following:</span></span>

   - <span data-ttu-id="92114-120">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="92114-120">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="92114-121">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="92114-121">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="92114-122">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="92114-122">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="92114-123">この例では、abraham.mcmahon@contoso.com、jewell.gordon@contoso.com、および staci.gonzalez@contoso.com は、保管担当者の SMTP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="92114-123">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Office 以外の365データアップロードフォルダーの構造](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="92114-125">電子情報開示マネージャーまたは電子情報開示管理者のどちらかのアカウント</span><span class="sxs-lookup"><span data-stu-id="92114-125">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>

- <span data-ttu-id="92114-126">Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされた Microsoft Azure Storage Tools。</span><span class="sxs-lookup"><span data-stu-id="92114-126">Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="92114-127">AzCopy をインストールします。これは、ここから行うことができます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="92114-127">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="92114-128">Office 以外の365コンテンツを上級電子情報開示にアップロードする</span><span class="sxs-lookup"><span data-stu-id="92114-128">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="92114-129">電子情報開示マネージャーまたは電子情報開示管理者として、Advanced eDiscovery を開き、Office 以外の365データのアップロード先となるケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="92114-129">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="92114-130">[**閲覧設定**] タブをクリックし、Office ではない365データを読み込むレビューセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="92114-130">Click the **review sets** tab, then select the review set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="92114-131">レビューセットをまだ作成していない場合は、ここで作成できます。</span><span class="sxs-lookup"><span data-stu-id="92114-131">If you have not already created a review set, you can do so now.</span></span>  <span data-ttu-id="92114-132">最後に、[**レビューセットの管理**] をクリックし、[Office 以外の365データタイルでの**アップロードの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92114-132">Finally, click **Manage review set** and then click **View uploads** in the \*\*Non-Office 365 data tile.</span></span>

2. <span data-ttu-id="92114-133">[**ファイルのアップロード**] ボタンをクリックして、Office 365 以外のデータインポートウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="92114-133">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

   ![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="92114-135">ウィザードの最初の手順では、ファイルをアップロードするために、セキュリティで保護された Azure blob を準備するだけです。</span><span class="sxs-lookup"><span data-stu-id="92114-135">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="92114-136">準備が完了したら、[**次へ: ファイルのアップロード**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="92114-136">Once preparation is completed, click the **Next: Upload files** button.</span></span>

   ![Office 以外の365インポート-準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="92114-138">[**ファイルのアップロード**] ステップで、**ファイルの場所へのパス**を指定します。この場合、インポートする予定の非 Office 365 データが配置されます。</span><span class="sxs-lookup"><span data-stu-id="92114-138">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="92114-139">正しい場所を設定することにより、AzCopy コマンドが正しく更新されます。</span><span class="sxs-lookup"><span data-stu-id="92114-139">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

   > [!NOTE]
   > <span data-ttu-id="92114-140">AzCopy をまだインストールしていない場合は、ここから実行できます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="92114-140">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="92114-141">[**クリップボードにコピー** ] リンクをクリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="92114-141">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="92114-142">Windows コマンドプロンプトを起動し、コマンドを貼り付けて、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="92114-142">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="92114-143">ファイルは、次の手順のために secure Azure blob ストレージにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="92114-143">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

   ![Office 以外の365インポート-ファイルのアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   ![Office 以外の365インポート-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="92114-146">指定した AzCopy コマンドが失敗した場合は、 [「Advanced eDiscovery での AzCopy のトラブルシューティング」](troubleshooting-azcopy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92114-146">If the supplied AzCopy command fails, refer to [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)</span></span>

6. <span data-ttu-id="92114-147">最後に、Security & コンプライアンスに戻って、[**次へ: ファイルの処理**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="92114-147">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="92114-148">これにより、アップロードしたファイルの処理、テキストの抽出、およびインデックス作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="92114-148">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="92114-149">処理の進行状況を追跡するには、[**ジョブ**] タブを使用します。 完了すると、新しいファイルがレビューセットで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="92114-149">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the review set.</span></span>  <span data-ttu-id="92114-150">処理が完了したら、ウィザードを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="92114-150">Once processing is complete, you can dismiss the wizard.</span></span>

   ![Office 以外の365インポート処理ファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

