---
title: エクスポート ジョブのダウンロード
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
ms.openlocfilehash: 904bc5f8a6d6cef937d55336e8f383957713769a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32251917"
---
# <a name="download-export-jobs"></a><span data-ttu-id="f5d81-102">エクスポート ジョブのダウンロード</span><span class="sxs-lookup"><span data-stu-id="f5d81-102">Download export jobs</span></span>

<span data-ttu-id="f5d81-103">エクスポートされたすべてのデータは、Microsoft Azure blob に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f5d81-103">All exported data is added to a Microsoft Azure blob.</span></span> <span data-ttu-id="f5d81-104">これにより、データ下流を処理するための複数のオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f5d81-104">This provides multiple options to handle the data downstream.</span></span> <span data-ttu-id="f5d81-105">Azure blob にアクセスするには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f5d81-105">There are several ways to access an Azure blob.</span></span> <span data-ttu-id="f5d81-106">1つの方法は、Azure ストレージエクスプローラーを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="f5d81-106">One method is to use Azure Storage Explorer.</span></span> <span data-ttu-id="f5d81-107">このメソッドは、簡単な接続、参照、ダウンロードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f5d81-107">This method supports simple connection, browsing and downloading.</span></span> <span data-ttu-id="f5d81-108">詳細については、<https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span><span class="sxs-lookup"><span data-stu-id="f5d81-108">For more information, visit <https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span></span>

1.  <span data-ttu-id="f5d81-109">エクスポートジョブの完了後にコンテンツをダウンロードするには、[エクスポート] タブに移動して、エクスポートジョブを選択します。</span><span class="sxs-lookup"><span data-stu-id="f5d81-109">To download content after an export job is complete, go to the Exports tab and select an export job.</span></span>

2.  <span data-ttu-id="f5d81-110">フライアウトの [場所] セクションのテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="f5d81-110">Copy the text in the “Locations” section of the flyout.</span></span>

![](../media/eDiscoExportJob.png)

3.  <span data-ttu-id="f5d81-111">Azure ストレージエクスプローラーを開いて、[接続] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5d81-111">Open Azure Storage Explorer and click the “Connect” button</span></span>

![](../media/AzureStorageConnect.png)

4.  <span data-ttu-id="f5d81-112">[共有アクセス署名 URI を使用する] を選択し、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5d81-112">Select “Use a shared access signature URI” and click next</span></span>

![](../media/AzureStorageConnect2.png)

5.  <span data-ttu-id="f5d81-113">[URI] テキストボックスに位置テキストを貼り付け、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5d81-113">Paste the Location text in the URI text box and click next</span></span>

![](../media/AzureStorageConnect3.png)

6.  <span data-ttu-id="f5d81-114">[接続] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5d81-114">Click Connect</span></span>

![](../media/AzureStorageConnect4.png)

<span data-ttu-id="f5d81-115">これにより、ストレージアカウントのオブジェクトとしてエクスポートが追加されます。 SAS 接続サービス/Blob コンテナー。</span><span class="sxs-lookup"><span data-stu-id="f5d81-115">This will add the export as an object in Storage Accounts/SAS-Attached Services/Blob Containers.</span></span> <span data-ttu-id="f5d81-116">エクスポートを調べて、エクスポートのすべてまたは一部をダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="f5d81-116">You will be able to explore the export and download all or portions of the export.</span></span>

![](../media/AzureStorageConnect5.png)