---
title: ワーキング セットにない-Office 365 のデータを読み込む
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 427b4c8c9dfffe351827a6869ae26a5356d646d8
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608030"
---
# <a name="load-non-office-365-data-into-a-working-set"></a><span data-ttu-id="75477-102">ワーキング セットにない-Office 365 のデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="75477-102">Load non-Office 365 data into a working set</span></span>

<span data-ttu-id="75477-p101">電子的証拠開示の Office 365 の詳細を分析する必要がありますすべてのドキュメントは、Office 365 で生活しています。非 Office 365 のコンテンツを持つだ Office 365 のワーキング セットには、高度な電子的証拠開示を分析するためのドキュメントをアップロードするときに高度な電子的証拠開示の機能をインポートします。この手順では、分析のために高度な電子的証拠開示に、Office 365 以外のドキュメントを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="75477-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="75477-p102">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、Office 365 Enterprise E5 の試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="75477-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="75477-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="75477-108">Before you begin</span></span>
<span data-ttu-id="75477-109">この手順で説明したように非 Office 365 のアップロード機能を使用するがあることが必要です。</span><span class="sxs-lookup"><span data-stu-id="75477-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
* <span data-ttu-id="75477-110">コンプライアンスの高度なアドオンと E5 のサブスクリプションの Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="75477-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
* <span data-ttu-id="75477-111">Office 365 以外のコンテンツがアップロードされるすべての通告は、コンプライアンスの高度なアドオンと E5 のライセンス E3 を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="75477-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
* <span data-ttu-id="75477-112">既存の電子的証拠開示ケース</span><span class="sxs-lookup"><span data-stu-id="75477-112">An existing eDiscovery case</span></span>
* <span data-ttu-id="75477-p103">保管担当者ごとの 1 つのフォルダーは、この形式の*alias@domainname*では、フォルダーの名前のフォルダーにアップロードするすべてのファイルが収集されます。*Alias@domainname*は、Office 365 のユーザーのエイリアスとドメインである必要があります。*Alias@domainname*のすべてのフォルダーは、ルート フォルダーに収集できます。ルート フォルダーは、 *alias@domainname*フォルダーを含めることができますのみ、必要があります圧縮しないファイルのルート フォルダー</span><span class="sxs-lookup"><span data-stu-id="75477-p103">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* . The *alias@domainname* must be users Office 365 alias and domain. You can collect all the *alias@domainname* folders into a root folder. The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder</span></span>
* <span data-ttu-id="75477-117">電子的証拠開示マネージャーか、電子的証拠開示管理者 Microsoft Azure ストレージ ツールを Office 365 以外のコンテンツ フォルダーの構造体へのアクセスを持つコンピューターにインストールされているアカウントです。</span><span class="sxs-lookup"><span data-stu-id="75477-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>
* <span data-ttu-id="75477-118">インストールの AzCopy、ここから実行することができます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="75477-118">Install AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="75477-119">高度な電子的証拠開示に Office 365 以外のコンテンツをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="75477-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>
1. <span data-ttu-id="75477-p104">電子的証拠開示マネージャーまたは管理者の電子的証拠開示では、高度な電子的証拠開示は、[Office 365 以外のデータをアップロードする場合に開きます。 **ワーキング セット**] タブをクリックし、ワーキング セットにない Office 365 のデータをロードするを選択します。 ワーキング セットをまだ作成していない場合これを行うようになりました。 最後に、[**管理の動作を設定**し、非 Office 365 のデータ セクションに**ビューのアップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75477-p104">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.  Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.  If you have not already created a working set, you can do so now.  Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="75477-124">非 Office 365 のデータのインポート ウィザードを起動するのには [**ファイルをアップロード**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="75477-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![ファイルをアップロードします。](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="75477-p105">ウィザードの最初のステップは、単にアップロードするファイルのセキュリティで保護された Azure blob を準備します。 準備が compelted をクリックして、**次: ファイルをアップロード**ボタン。</span><span class="sxs-lookup"><span data-stu-id="75477-p105">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.  Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![非 Office 365 のインポート - の準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="75477-p106">**ファイルのアップロード**の手順で、**ファイルの場所へのパス**を指定してこれをインポートするように計画する非 Office 365 のデータが格納されています。 コマンドが正常に更新 AzCopy を確実に正しい場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="75477-p106">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.  Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="75477-131">AzCopy をまだインストールしていない場合は、ここから行うこのできます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="75477-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="75477-p107">定義済みのコマンドをコピーするには、**クリップボードにコピー** ] リンクをクリックします。Windows コマンド プロンプトを起動し、コマンドを貼り付け、enter キーを押します。 ファイルは、次の手順のセキュリティで保護された Azure blob ストレージにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="75477-p107">Copy the predefined command by clicking the **Copy to clipboard** link. Start a windows command prompt, paste the command and press enter.  The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Office 365 以外のインポート ・ ファイルをアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 のインポート - AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="75477-p108">最後に、セキュリティ & 準拠状態に戻すしをクリックして、**次: ファイルを処理する**ボタン。 テキストの抽出を処理して、アップロードされたファイルのインデックス作成が開始されます。 ここまたは **[ジョブ**] タブでの処理の進行状況を追跡することができます。 完了後、新しいファイルがワーキング セットで使用されます。 処理が完了した後、ウィザードを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="75477-p108">Finally, return back to the Security & Compliance and click the **Next: Process files** button.  This will initiate processing, text extraction and indexing of the uploaded files.  You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.  Once processing is complete, you can dismiss the wizard.</span></span>

![Office 365 以外のインポート ・ ファイルの処理](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

