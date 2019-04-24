---
title: Office 365 のバッチ履歴を表示して過去の結果をエクスポートする高度な電子情報開示
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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243513"
---
# <a name="view-batch-history-and-export-past-results-in-office-365-advanced-ediscovery"></a>Office 365 のバッチ履歴を表示して過去の結果をエクスポートする高度な電子情報開示

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
次のセクションでは、高度な電子情報開示でのデータの一括表示およびエクスポートの追加オプションについて説明します。 
  
## <a name="viewing-export-batch-history-and-exporting-previous-batches"></a>バッチのエクスポート履歴を表示し、以前のバッチをエクスポートする

[エクスポート履歴] ダイアログは、選択したエクスポートバッチセッションの詳細情報を提供します。また、最後のセッションを取り消すこともできます。
  
1. [**エクスポート\>の設定**] で、[バッチの**エクスポート**] ドロップダウンリストからバッチ名を選択します。 
    
2. [バッチ名のエクスポート] の右にある [**バッチ履歴**] アイコンを選択します。 
    
    ![[バッチ履歴のエクスポート] アイコン](media/a14f6ef9-0c3c-4851-b65d-9380f2d8a38a.gif)
  
    [バッチ履歴] ダイアログが表示されます。
    
    ![バッチ履歴のエクスポート](media/04c5b75c-348c-491d-b4fe-716659333890.png)
  
3. 前のセッションをロールバックする必要がある場合は、[**前回のセッションを元に戻す**] をクリックします。 Rollback を複数回実行して、最後のセッションを取り消すことができます。
    
4. 以前に実行したエクスポートバッチセッションからいつでもデータをダウンロードする場合は、エクスポートする![必要のあるエクスポートバッチ](media/de69b920-a6ac-4ddb-b93e-e1cc5888e6c4.gif)の横にある [**ダウンロード**] アイコンエクスポートバッチ履歴のダウンロードアイコンをクリックします。 
    
5. [**共有アクセス署名**] ダイアログボックスが表示されたら、[**クリップボードにコピー** ] をクリックして、エクスポートセッションデータをローカルコンピューターにコピーし、[**閉じる**] をクリックします。 Office 365 セキュリティ&amp;コンプライアンスセンターの**電子情報開示エクスポートツール**のダイアログボックスが表示されます。 
    
    ![[電子情報開示のエクスポート] ダイアログボックス](media/01f79d2d-6da0-45e6-9c6f-ab12347572cb.gif)
  
6. [**電子情報開示エクスポートツール**] ダイアログボックスで、次のようになります。 
    
1. [**貼り付け元への接続に使用される共有アクセス署名**] に、以前にクリップボードにコピーした**共有アクセス署名**の値を貼り付けます。 
    
2. [**参照**] をクリックして、ダウンロードしたエクスポートファイルをローカルコンピューターに保存するためのターゲットの場所を選択します。 
    
3. [**開始**] をクリックします。 エクスポートファイルがローカルコンピューターにダウンロードされます。 
    
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[結果のエクスポート](export-results-in-advanced-ediscovery.md)

[レポート フィールドのエクスポート](export-report-fields-in-advanced-ediscovery.md)

