---
title: エクスポート ジョブのダウンロード
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 56ed8eac259974b43ca0cd26b2bd0c339a5fc05b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155149"
---
# <a name="download-export-jobs"></a>エクスポート ジョブのダウンロード

エクスポートされたすべてのデータは、Microsoft Azure blob に追加されます。 これにより、データ下流を処理するための複数のオプションが提供されます。 Azure blob にアクセスするには、いくつかの方法があります。 1つの方法は、Azure ストレージエクスプローラーを使用する方法です。 このメソッドは、簡単な接続、参照、ダウンロードをサポートします。 詳細については、<https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer>

1.  エクスポートジョブの完了後にコンテンツをダウンロードするには、[エクスポート] タブに移動して、エクスポートジョブを選択します。

2.  フライアウトの [場所] セクションのテキストをコピーします。

![](../media/eDiscoExportJob.png)

3.  Azure ストレージエクスプローラーを開いて、[接続] ボタンをクリックします。

![](../media/AzureStorageConnect.png)

4.  [共有アクセス署名 URI を使用する] を選択し、[次へ] をクリックします。

![](../media/AzureStorageConnect2.png)

5.  [URI] テキストボックスに位置テキストを貼り付け、[次へ] をクリックします。

![](../media/AzureStorageConnect3.png)

6.  [接続] をクリックします。

![](../media/AzureStorageConnect4.png)

これにより、ストレージアカウントのオブジェクトとしてエクスポートが追加されます。 SAS 接続サービス/Blob コンテナー。 エクスポートを調べて、エクスポートのすべてまたは一部をダウンロードすることができます。

![](../media/AzureStorageConnect5.png)