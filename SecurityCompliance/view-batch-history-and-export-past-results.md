---
title: バッチ履歴を表示し以前の Office 365 Advanced eDiscovery の結果をエクスポートする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d52b41-75ab-4144-9edf-31e11453bd5d
description: '選択したエクスポートバッチセッションの詳細情報を表示する方法と、Office 365 Advanced eDiscovery で最終エクスポートセッションを取り消す方法について説明します。  '
ms.openlocfilehash: a55f299669c2a404ee176153aa766210a3141199
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214947"
---
# <a name="view-batch-history-and-export-past-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="8ae3b-103">バッチ履歴を表示し以前の Office 365 Advanced eDiscovery の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8ae3b-103">View batch history and export past results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="8ae3b-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="8ae3b-106">次のセクションでは、高度な電子情報開示でのデータの一括表示およびエクスポートの追加オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-106">The following section describes additional options for batch viewing and export of data in Advanced eDiscovery.</span></span> 
  
## <a name="viewing-export-batch-history-and-exporting-previous-batches"></a><span data-ttu-id="8ae3b-107">バッチのエクスポート履歴を表示し、以前のバッチをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8ae3b-107">Viewing Export batch history and exporting previous batches</span></span>

<span data-ttu-id="8ae3b-108">[エクスポート履歴] ダイアログは、選択したエクスポートバッチセッションの詳細情報を提供します。また、最後のセッションを取り消すこともできます。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-108">The Export history dialog provides detailed information of selected export batch sessions and also provides the ability to undo the last session.</span></span>
  
1. <span data-ttu-id="8ae3b-109">[**エクスポート\>の設定**] で、[バッチの**エクスポート**] ドロップダウンリストからバッチ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-109">In **Export \> Setup**, select the batch name from the **Export batch** drop-down list.</span></span> 
    
2. <span data-ttu-id="8ae3b-110">[バッチ名のエクスポート] の右にある [**バッチ履歴**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-110">To the right of the export batch name, select the **Batch history** icon:</span></span> 
    
    ![[バッチ履歴のエクスポート] アイコン](media/a14f6ef9-0c3c-4851-b65d-9380f2d8a38a.gif)
  
    <span data-ttu-id="8ae3b-112">[バッチ履歴] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-112">The Batch history dialog is displayed.</span></span>
    
    ![バッチ履歴のエクスポート](media/04c5b75c-348c-491d-b4fe-716659333890.png)
  
3. <span data-ttu-id="8ae3b-p102">前のセッションをロールバックする必要がある場合は、[**前回のセッションを元に戻す**] をクリックします。Rollback を複数回実行して、最後のセッションを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-p102">If it is necessary to roll back a previous session, click **Undo last session**. Rollback can be performed multiple times, which cancels the last session.</span></span>
    
4. <span data-ttu-id="8ae3b-116">以前に実行したエクスポートバッチセッションからいつでもデータをダウンロードする場合は、エクスポートする![必要のあるエクスポートバッチ](media/de69b920-a6ac-4ddb-b93e-e1cc5888e6c4.gif)の横にある [**ダウンロード**] アイコンエクスポートバッチ履歴のダウンロードアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-116">If you want to download data at any time from a previously executed export batch session, click the **Download** icon ![Export batch history download icon](media/de69b920-a6ac-4ddb-b93e-e1cc5888e6c4.gif) next to the desired export batch to be exported.</span></span> 
    
5. <span data-ttu-id="8ae3b-p103">[**共有アクセス署名**] ダイアログボックスが表示されたら、[**クリップボードにコピー** ] をクリックして、エクスポートセッションデータをローカルコンピューターにコピーし、[**閉じる**] をクリックします。Office 365 セキュリティ&amp;コンプライアンスセンターの**電子情報開示エクスポートツール**のダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-p103">When the **Shared access signature** dialog is displayed, click **Copy to clipboard** to copy the export session data to the local machine, and then click **Close**. The Office 365 Security &amp; Compliance Center **eDiscovery Export Tool** dialog is displayed.</span></span> 
    
    ![[電子情報開示のエクスポート] ダイアログボックス](media/01f79d2d-6da0-45e6-9c6f-ab12347572cb.gif)
  
6. <span data-ttu-id="8ae3b-120">[**電子情報開示エクスポートツール**] ダイアログボックスで、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-120">In the **eDiscovery Export Tool** dialog:</span></span> 
    
1. <span data-ttu-id="8ae3b-121">[**貼り付け元への接続に使用される共有アクセス署名**] に、以前にクリップボードにコピーした**共有アクセス署名**の値を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-121">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the **Shared access signature** value, which was previously copied to the clipboard.</span></span> 
    
2. <span data-ttu-id="8ae3b-122">[**参照**] をクリックして、ダウンロードしたエクスポートファイルをローカルコンピューターに保存するためのターゲットの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-122">Click **Browse** to select the target location for storing the downloaded export files on a local machine.</span></span> 
    
3. <span data-ttu-id="8ae3b-p104">[**開始**] をクリックします。エクスポートファイルがローカルコンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="8ae3b-p104">Click **Start**. The export files are downloaded to the local machine.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="8ae3b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ae3b-125">See also</span></span>

[<span data-ttu-id="8ae3b-126">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8ae3b-126">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8ae3b-127">結果のエクスポート</span><span class="sxs-lookup"><span data-stu-id="8ae3b-127">Exporting results </span></span>](export-results-in-advanced-ediscovery.md)

[<span data-ttu-id="8ae3b-128">レポート フィールドのエクスポート</span><span class="sxs-lookup"><span data-stu-id="8ae3b-128">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)

