---
title: Office 365 Cloud App Security を使用して app discovery レポートを作成する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: Office 365 クラウド アプリケーションのセキュリティを使用すると、Office 365 とその他のアプリケーションに、組織内のユーザーを使用する方法を理解するには、レポートを作成します。
ms.openlocfilehash: 6842912f42072e21608955bde5250f0774c7bba4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531568"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a>Office 365 Cloud App Security を使用して app discovery レポートを作成する

セキュリティ管理の高度な office 365 は、Office 365 のクラウド アプリケーションのセキュリティをされます。
  
|評価 * *\>**|計画 * *\>**|配置 * *\>**|使用率。|
|:-----|:-----|:-----|:-----|
|[評価を開始します。](office-365-cas-overview.md) <br/> |[計画の開始します。](get-ready-for-office-365-cas.md) <br/> |[展開を開始します。](turn-on-office-365-cas.md) <br/> |コースです!  <br/> [次の手順](#next-steps) <br/> |
   
Office 365 のクラウド アプリケーションのセキュリティは、グローバル管理者、セキュリティ管理者、およびセキュリティ リーダーが組織内のユーザーが使用しているクラウド サービスの把握に役立ちます。たとえば、データの量は、アプリケーションまたは Office 365 の外部にあるサービスにアップロードしています、ユーザーが保存してドキュメントで共同作業を行う場所を確認できます。
  
アプリケーションの探索レポートを生成するために手動でアップロードする、ファイアウォールやプロキシから、web トラフィックのログ ファイルと Office 365 のクラウド アプリケーションのセキュリティを解析し、レポートのこれらのファイルを分析しています。
  
> [!NOTE]
> この資料に記載されているタスクを実行するグローバル管理者、セキュリティ管理者、またはセキュリティのリーダーである必要があります。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。 
  
## <a name="create-a-report-with-app-discovery"></a>アプリケーションの検出とレポートを作成します。

アプリの探索レポートを作成するには、仕入先のデータ ソースの分析が、ログ ファイルを選択し、レポートを要求し、使用するログ ファイルを識別します。
  
> [!NOTE]
> 組織の使用法の最適な表現を取得するのにはピーク トラフィックは、web トラフィックのログ ファイルを使用します。 
  
1. お客様の[web トラフィックのログ、および Office 365 のクラウド アプリケーションのセキュリティのデータ ソース](web-traffic-logs-and-data-sources-for-ocas.md)を収集します。
    
2. [https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用してサインインします。 
    
3. セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。
    
4. **Office 365 のクラウド アプリケーションのセキュリティ**を選択します。
    
5. **検出**を選択して\>**新しいレポートを作成**します。
    
    ![Office 365 CA ポータルでは、検出を選択します](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
6. 名と、レポートの説明を指定し、[**データ ソース**] ボックスの一覧で、web トラフィックのログのデータ ソースを選択します。 
    
    ![O365 の CA で、検出を選択します\>新しいレポートを作成します。](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)
  
    > [!NOTE]
    > 使用するにはデータ ソースが一覧にない場合は、追加することを要求できます。[**その他**の**データ ソース**、およびアップロードしようとしているデータ ソースの名前を入力します。ログを確認、それを生成するデータ ソースのサポートを追加したことを確認でき、します。 
  
7. 収集したログ ファイルの場所を参照し、ファイルを選択します。ログ ファイルは、レポート用に選択したデータ ソースで生成されている必要があります。
    
8. レポート作成プロセスを開始する**を作成する**] をクリックします。 
    
9. レポートのステータスを表示するには、**レポートのスナップショットの管理**をクリックします。レポートの準備ができたら、[**レポートの表示**] オプションが表示されます。 
    
## <a name="next-steps"></a>次の手順

- [確認し、アラート アクションを実行](review-office-365-cas-alerts.md)
    
- [Office 365 Cloud App Security でアプリ検出結果を確認する](review-app-discovery-findings-in-ocas.md)
    
- [Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。
    

