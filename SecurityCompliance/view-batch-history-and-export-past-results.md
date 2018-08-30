---
title: バッチ履歴を表示し以前の Office 365 Advanced eDiscovery の結果をエクスポートする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d52b41-75ab-4144-9edf-31e11453bd5d
description: '選択したエクスポートのバッチのセッションの詳細情報を表示する方法と電子的証拠開示の Office 365 の詳細設定の最後のエクスポート ・ セッションを元に戻す方法について説明します。  '
ms.openlocfilehash: 545449e296789508c5f13f8f012549129969d282
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532553"
---
# <a name="view-batch-history-and-export-past-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="6efa3-103">バッチ履歴を表示し以前の Office 365 Advanced eDiscovery の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="6efa3-103">View batch history and export past results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="6efa3-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="6efa3-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="6efa3-106">次のセクションでは、バッチの表示と高度な電子的証拠開示でのデータのエクスポートの追加のオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6efa3-106">The following section describes additional options for batch viewing and export of data in Advanced eDiscovery.</span></span> 
  
## <a name="viewing-export-batch-history-and-exporting-previous-batches"></a><span data-ttu-id="6efa3-107">エクスポート バッチ履歴を表示して、前回のバッチのエクスポート</span><span class="sxs-lookup"><span data-stu-id="6efa3-107">Viewing Export batch history and exporting previous batches</span></span>

<span data-ttu-id="6efa3-108">履歴のエクスポート] ダイアログは、選択したエクスポートのバッチのセッションの詳細情報を提供し、最後のセッションを元に戻す機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="6efa3-108">The Export history dialog provides detailed information of selected export batch sessions and also provides the ability to undo the last session.</span></span>
  
1. <span data-ttu-id="6efa3-109">**エクスポート\>セットアップ**、**バッチのエクスポート**」ドロップ ダウン リストからバッチの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="6efa3-109">In **Export \> Setup**, select the batch name from the **Export batch** drop-down list.</span></span> 
    
2. <span data-ttu-id="6efa3-110">エクスポート バッチ名の右側に、**バッチ履歴**アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6efa3-110">To the right of the export batch name, select the **Batch history** icon:</span></span> 
    
    ![[バッチ履歴のエクスポート] アイコン](media/a14f6ef9-0c3c-4851-b65d-9380f2d8a38a.gif)
  
    <span data-ttu-id="6efa3-112">バッチ履歴] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6efa3-112">The Batch history dialog is displayed.</span></span>
    
    ![バッチ履歴のエクスポート](media/04c5b75c-348c-491d-b4fe-716659333890.png)
  
3. <span data-ttu-id="6efa3-p102">以前のセッションをロールバックする必要がある場合は、**最後のセッションを元に戻す**] をクリックします。ロールバックを実行できます複数回は、前回のセッションをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="6efa3-p102">If it is necessary to roll back a previous session, click **Undo last session**. Rollback can be performed multiple times, which cancels the last session.</span></span>
    
4. <span data-ttu-id="6efa3-116">エクスポートを実行したバッチのセッションからいつでもデータをダウンロードするには、**ダウンロード**アイコンをクリックします。![エクスポート バッチ履歴のダウンロード アイコン](media/de69b920-a6ac-4ddb-b93e-e1cc5888e6c4.gif)エクスポートに必要なエクスポートのバッチの横にあります。</span><span class="sxs-lookup"><span data-stu-id="6efa3-116">If you want to download data at any time from a previously executed export batch session, click the **Download** icon ![Export batch history download icon](media/de69b920-a6ac-4ddb-b93e-e1cc5888e6c4.gif) next to the desired export batch to be exported.</span></span> 
    
5. <span data-ttu-id="6efa3-p103">**共有アクセス署名**ダイアログ ボックスが表示されたら、セッション データのエクスポートをローカル コンピューターにコピーするのには**クリップボードにコピー** ] をクリックし、[**閉じる**] をクリックします。Office 365 のセキュリティ&amp;コンプライアンス センター **eDiscovery ツールのエクスポート**] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6efa3-p103">When the **Shared access signature** dialog is displayed, click **Copy to clipboard** to copy the export session data to the local machine, and then click **Close**. The Office 365 Security &amp; Compliance Center **eDiscovery Export Tool** dialog is displayed.</span></span> 
    
    ![[電子情報開示のエクスポート] ダイアログボックス](media/01f79d2d-6da0-45e6-9c6f-ab12347572cb.gif)
  
6. <span data-ttu-id="6efa3-120">**EDiscovery ツールのエクスポート**] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6efa3-120">In the **eDiscovery Export Tool** dialog:</span></span> 
    
1. <span data-ttu-id="6efa3-121">**ソースへの接続に使用される、共有アクセス署名を貼り付ける**には、以前はクリップボードにコピーされた**共有アクセス署名**の値を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6efa3-121">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the **Shared access signature** value, which was previously copied to the clipboard.</span></span> 
    
2. <span data-ttu-id="6efa3-122">ローカル マシンにダウンロードしたエクスポート ファイルを保存するターゲットの場所を選択する**参照**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6efa3-122">Click **Browse** to select the target location for storing the downloaded export files on a local machine.</span></span> 
    
3. <span data-ttu-id="6efa3-p104">[**開始**] をクリックします。エクスポート ファイルは、ローカル コンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="6efa3-p104">Click **Start**. The export files are downloaded to the local machine.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="6efa3-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6efa3-125">See also</span></span>

[<span data-ttu-id="6efa3-126">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6efa3-126">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="6efa3-127">結果のエクスポート</span><span class="sxs-lookup"><span data-stu-id="6efa3-127">Exporting results </span></span>](export-results-in-advanced-ediscovery.md)

[<span data-ttu-id="6efa3-128">レポートのフィールドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6efa3-128">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)

