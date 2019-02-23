---
title: ワーキング セットに Office 365 以外のデータを読み込む
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 50fcf679b5cd17a079765bfca5435088bef4c06e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217687"
---
# <a name="load-non-office-365-data-into-a-working-set"></a><span data-ttu-id="436c3-102">ワーキング セットに Office 365 以外のデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="436c3-102">Load non-Office 365 data into a working set</span></span>

<span data-ttu-id="436c3-p101">office 365 の高度な電子情報開示で分析する必要があるすべてのドキュメントが office 365 に存在するわけではありません。advanced ediscovery の office 365 以外のコンテンツインポート機能を使用すると、office 365 に存在しないドキュメントを作業セットにアップロードして、advanced ediscovery で分析することができます。この手順では、非 Office 365 ドキュメントを分析のために上級電子情報開示に移行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="436c3-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="436c3-p102">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、Office 365 Enterprise E5 の試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="436c3-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="436c3-108">始める前に</span><span class="sxs-lookup"><span data-stu-id="436c3-108">Before you begin</span></span>
<span data-ttu-id="436c3-109">この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="436c3-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="436c3-110">高度なコンプライアンスアドオンまたは E5 サブスクリプションを備えた Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="436c3-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="436c3-111">Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンまたは E5 ライセンスを含む E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="436c3-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="436c3-112">既存の電子情報開示ケース。</span><span class="sxs-lookup"><span data-stu-id="436c3-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="436c3-p103">収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前が*エイリアス @ domainname*の形式になっているフォルダーにアップロードされます。*エイリアス @ domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。すべての*エイリアス @ domainname*フォルダーをルートフォルダーに収集できます。ルートフォルダーに含めることができるのは、 *@ domainname* folders のエイリアスのみです。ルートフォルダーには圧縮されていないファイルは存在しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="436c3-p103">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* . The *alias@domainname* must be users Office 365 alias and domain. You can collect all the *alias@domainname* folders into a root folder. The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="436c3-117">Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされている、電子情報開示マネージャーまたは電子情報開示管理者の Microsoft Azure Storage Tools のどちらかのアカウント。</span><span class="sxs-lookup"><span data-stu-id="436c3-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="436c3-118">azcopy をインストールします。これは、ここから行うことができます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="436c3-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="436c3-119">Office 以外の365コンテンツを上級電子情報開示にアップロードする</span><span class="sxs-lookup"><span data-stu-id="436c3-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="436c3-p104">電子情報開示マネージャーまたは電子情報開示管理者として、Advanced ediscovery を開き、Office 以外の365データのアップロード先となるケースを開きます。 [**作業設定**] タブをクリックし、Office 以外の365データを読み込む作業セットを選択します。 作業セットをまだ作成していない場合は、ここで作成できます。 最後に、[動作**設定の管理**] をクリックし、[Office ではない365データ] セクションの [**アップロードを表示**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436c3-p104">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.  Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.  If you have not already created a working set, you can do so now.  Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="436c3-124">[**ファイルのアップロード**] ボタンをクリックして、Office 365 以外のデータインポートウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="436c3-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="436c3-p105">ウィザードの最初の手順では、ファイルをアップロードするために、セキュリティで保護された Azure blob を準備するだけです。 準備が整ったら、[**次へ: ファイルのアップロード**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="436c3-p105">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.  Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![Office 以外の365インポート-準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="436c3-p106">[**ファイルのアップロード**] ステップで、**ファイルの場所へのパス**を指定します。この場合、インポートする予定の非 Office 365 データが配置されます。 正しい場所を設定することにより、azcopy コマンドが正しく更新されます。</span><span class="sxs-lookup"><span data-stu-id="436c3-p106">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.  Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="436c3-131">azcopy をまだインストールしていない場合は、ここから実行できます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="436c3-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="436c3-p107">[**クリップボードにコピー** ] リンクをクリックして、定義済みのコマンドをコピーします。windows コマンドプロンプトを起動し、コマンドを貼り付けて、enter キーを押します。 ファイルは、次の手順のために secure Azure blob ストレージにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="436c3-p107">Copy the predefined command by clicking the **Copy to clipboard** link. Start a windows command prompt, paste the command and press enter.  The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Office 以外の365インポート-ファイルのアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Office 以外の365インポート-azcopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="436c3-p108">最後に、Security & コンプライアンスに戻って、[**次へ: ファイルの処理**] ボタンをクリックします。 これにより、アップロードしたファイルの処理、テキストの抽出、およびインデックス作成が開始されます。 処理の進行状況を追跡するには、[**ジョブ**] タブを使用します。 完了すると、新しいファイルがワーキングセットで利用できるようになります。 処理が完了したら、ウィザードを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="436c3-p108">Finally, return back to the Security & Compliance and click the **Next: Process files** button.  This will initiate processing, text extraction and indexing of the uploaded files.  You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.  Once processing is complete, you can dismiss the wizard.</span></span>

![Office 以外の365インポート処理ファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

