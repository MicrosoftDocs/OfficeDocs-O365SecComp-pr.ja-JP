---
title: IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: など、物理的なオフィスの IP アドレスでは、Office 365 のクラウド アプリケーションのセキュリティ、使用する IP アドレスのセットを簡単に識別するには、IP アドレスの範囲のグループを設定できます。
ms.openlocfilehash: 42a62d2dd9771fb7d3ac992f4e0f8b5f6826efe3
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603738"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a>IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する
  
|評価 * *\>**|計画 * *\>**|配置 * *\>**|使用率。|
|:-----|:-----|:-----|:-----|
|[評価を開始します。](office-365-cas-overview.md) <br/> |[計画の開始します。](get-ready-for-office-365-cas.md) <br/> |コースです!  <br/> [次の手順](#next-steps) <br/> |[使用します。](utilization-activities-for-ocas.md) <br/> |
   
など、物理的なオフィスの IP アドレスでは、Office 365 のクラウド アプリケーションのセキュリティ、使用する IP アドレスのセットを簡単に識別するには、IP アドレスの範囲のグループを設定できます。これらの範囲の使用を定義するタグ付けして分類したり、タグを使用することができますしと、アクティビティのログし、警告をカスタマイズするのにはカテゴリが表示され、調査します。
  
IP の範囲の各グループ タグを設定するを選択して、IP のカテゴリ (企業、管理、Risky、VPN など) の既定のリストに基づいたタグを分類できますし、タグ名です。IPv4 と IPv6 アドレスの両方がサポートされます。
  
> [!NOTE]
> この資料の手順を実行するには、グローバル ・ アドミニストレーターまたはセキュリティ管理者である必要があります。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a>Office 365 のクラウド アプリケーションのセキュリティでは、IP アドレスの範囲を設定するには

1. グローバル管理者またはセキュリティ管理者は、クラウド アプリケーションのセキュリティ関連ポータルに移動する ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) し、サインインします。
    
2. ページの右上、上の [**設定**] をクリックします\> **IP アドレスの範囲**です。<br>![O365 クラウド アプリケーションのセキュリティでは、システムおよびデータの設定にアクセスするための設定を選択します](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)<br>
  
3. プラス記号のような新しい] ボタンをクリックして ( **+**)。
    
4. ウィンドウで、**新しい IP アドレスの範囲**は、次の値を指定します。 
    
|**フィールドまたはリスト**|**行うこと**|
|:-----|:-----|
|**名前** <br/> |IP アドレスの範囲と設定を管理するのにには、このフィールドを使用します。(アクティビティ ログには、この値は表示されません)。  <br/> |
|**IP アドレスの範囲** <br/> |ネットワーク プレフィックス表記法 (CIDR 表記法とも呼ばれます) を使用して範囲を指定します。たとえば、192.168.1.0/27 には、192.168.1.0 192.168.1.31 (両端を含む) での値の範囲が含まれています。  <br/> |
|**場所**と**ISP の登録** <br/> |IP アドレスの範囲のインターネット サービス プロバイダー (ISP) と保存場所を指定します。これよりも優先アドレスに対して定義されているパブリック フィールドなど、アイルランドで一般に公開と見なされますが、米国では実際には、IP アドレスがある場合は、役に立つは  <br/> |
|**タグ** <br/> |タグを使用すると、IP アドレスのグループの名前を指定します。(「名前」フィールドと異なりが表示されるタグ アクティビティ ログに記録します。)タグを使用する語句を入力します。各 IP アドレスの範囲を好きなように多くのタグを追加することができます。既に設定したタグと、この IP アドレス範囲を追加する、入力を開始するように表示される現在のタグの一覧から選択します。  <br/> |
|**カテゴリ** <br/> | 特定の IP アドレスからの活動を認識しやすくには、タグにカテゴリを割り当てます。次のオプションから選択します。<br/> **管理**すべての管理者の IP アドレスです。  <br/> **クラウド プロバイダー**クラウドで、プロキシの IP アドレスです。  <br/> **企業**すべての IP アドレスしますの内部ネットワーク、支店、および、Wi-fi ローミングのアドレス。  <br/> **危険**不審な IP アドレスをするなど、何らかの危険性をすることを検討する任意の IP アドレスは、以前は、競合企業のネットワークで IP アドレスを見たし、に。既定では、何らかの危険性のカテゴリには、IP の 2 つのタグが含まれます:**匿名のプロキシ**と**Tor** <br/> **VPN**リモート作業者が使用する IP アドレスです。  <br/> |
   
7. **[保存]** を選択します。
    
IP アドレスの範囲を設定した後は、これらの変更のみの今後のイベントが発生することに留意してください。
  
## <a name="next-steps"></a>次のステップ

- [活動ポリシーとアラート](activity-policies-and-alerts.md)
    
- [異常検出のポリシー](anomaly-detection-policies-in-ocas.md)
    
- [SIEM サーバーを統合します。](integrate-your-siem-server-with-office-365-cas.md)
    
- [Office 365 Cloud App Security の警告の確認と処理](review-office-365-cas-alerts.md)
    

