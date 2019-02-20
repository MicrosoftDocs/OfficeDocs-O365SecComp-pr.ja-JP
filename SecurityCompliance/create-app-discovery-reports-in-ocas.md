---
title: Office 365 Cloud App Security を使用して app discovery レポートを作成する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: office 365 Cloud App Security を使用してレポートを作成します。これにより、組織内のユーザーが office 365 や他のアプリをどのように使用しているかを把握することができます。
ms.openlocfilehash: e0d515ddd9b08aa4a70276177060f273cc89949e
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087296"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a>Office 365 Cloud App Security を使用して app discovery レポートを作成する

|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |[展開を開始する](turn-on-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](#next-steps) <br/> |
   
Office 365 cloud App security では、全体管理者、セキュリティ管理者、およびセキュリティ閲覧者が組織内のユーザーが使用しているクラウドサービスについて洞察を得ることができます。たとえば、ユーザーがドキュメントを格納して共同作業する場所、および Office 365 の外部にあるアプリまたはサービスにアップロードされるデータの量を確認できます。
  
アプリ検出レポートを生成するには、ファイアウォールとプロキシから web トラフィックログファイルを手動でアップロードし、Office 365 Cloud app Security でレポートのファイルを解析して分析します。
  
> [!NOTE]
> この記事で説明されているタスクを実行するには、全体管理者、セキュリティ管理者、またはセキュリティリーダーである必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。 
  
## <a name="create-a-report-with-app-discovery"></a>アプリ検出を使用してレポートを作成する

アプリ検出レポートを作成するには、分析するログファイルのベンダーデータソースを特定し、ログファイルを選択して、レポートを要求します。
  
> [!NOTE]
> ピークのトラフィック期間を含む web トラフィックログファイルを使用して、組織での使用の最適な表現を取得します。 
  
1. [Office 365 Cloud App Security の web トラフィックログとデータソースを](web-traffic-logs-and-data-sources-for-ocas.md)収集します。
    
2. Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。 
       
3. [**検出** \> ] [**新しいレポートの作成**] を選択します。 <br>![Office 365 CAS ポータルで、[検出] を選択します。](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)<br>
  
4. レポートの名前と説明を指定し、[**データソース**] ボックスの一覧で web トラフィックログのデータソースを選択します。 <br>![O365 CAS で、[ディスカバー \> ] [新しいレポートの作成] を選択します。](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)<br>使用するデータソースが表示されていない場合は、追加するように要求することができます。[**データソース**] として [**その他**] を選択し、アップロードするデータソースの名前を入力します。ログを確認して、それを生成したデータソースのサポートを追加するかどうかを確認してみましょう。 
  
5. 収集したログファイルの場所に移動し、ファイルを選択します。ログファイルは、レポート用に選択したデータソースによって生成されている必要があります。
    
6. [**作成**] をクリックして、レポート作成プロセスを開始します。 
    
7. レポートの状態を表示するには、[**スナップショットレポートの管理**] をクリックします。レポートの準備が整ったら、[レポートの**表示**] オプションが表示されます。 
    
## <a name="next-steps"></a>次の手順

- [通知を確認して処理を実行する](review-office-365-cas-alerts.md)
    
- [Office 365 Cloud App Security でアプリ検出結果を確認する](review-app-discovery-findings-in-ocas.md)
    
- [Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する
    

