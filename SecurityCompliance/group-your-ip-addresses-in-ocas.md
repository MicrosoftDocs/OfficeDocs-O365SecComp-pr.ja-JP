---
title: IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: office 365 Cloud App Security で使用する ip アドレスのセット (物理的なオフィスの ip アドレスなど) を簡単に識別するには、ip アドレス範囲のグループを設定します。
ms.openlocfilehash: b8f5c1dd46b2e3990d53a65881d12ca8f3961b16
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220447"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a>IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する
  
|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](#next-steps) <br/> |[利用を開始する](utilization-activities-for-ocas.md) <br/> |
   
office 365 Cloud App Security で使用する ip アドレスのセット (物理的なオフィスの ip アドレスなど) を簡単に識別するには、ip アドレス範囲のグループを設定します。これらの範囲を定義すると、それらをタグ付けして分類することができます。次に、タグとカテゴリを使用して、アクティビティのログと通知の表示方法と調査方法をカスタマイズできます。
  
ip 範囲の各グループには、選択したタグ名でタグを付けることができます。その後、ip カテゴリの既定のリスト (企業、管理、リスク、および VPN) に基づいてタグを分類できます。IPv4 と IPv6 の両方のアドレスがサポートされています。
  
> [!NOTE]
> この記事の手順を実行するには、全体管理者またはセキュリティ管理者である必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a>Office 365 Cloud App Security で IP アドレス範囲を設定するには

1. グローバル管理者またはセキュリティ管理者は、Cloud App security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) にアクセスして、サインインします。
    
2. ページの右上で、[ **IP アドレス範囲**の**設定** \> ] をクリックします。<br>![O365 Cloud App Security で、[設定] を選択してシステムとデータの設定にアクセスします。](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)<br>
  
3. プラス記号 ( **+**) に似た [新規] ボタンをクリックします。
    
4. [**新しい IP アドレスの範囲**] ウィンドウで、次の値を指定します。 
    
|**フィールドまたはリスト**|**行うこと**|
|:-----|:-----|
|**名前** <br/> |このフィールドを使用して、IP アドレスの範囲と設定を管理します。(この値はアクティビティログに表示されません)。  <br/> |
|**IP アドレスの範囲** <br/> |ネットワークプレフィックス表記 (CIDR 表記とも呼ばれる) を使用して、範囲を指定します。たとえば、192.168.1.0/27 では、192.168.1.31 (包含) からの値の範囲が含まれています。  <br/> |
|**場所**と**登録されている ISP** <br/> |IP アドレスの範囲の場所とインターネットサービスプロバイダー (ISP) を指定します。これは、アドレスに対して定義されているパブリックフィールドを上書きします。これは、IP アドレスがアイルランドで公開されているものの、実際には米国で使用される場合に役立ちます。  <br/> |
|**タグ** <br/> |タグを使用して、IP アドレスのグループに名前を付けます。([名前] フィールドとは異なり、アクティビティログにタグが表示されます。)タグに使用する単語または語句を入力します。各 IP アドレス範囲に対して、必要な数のタグを追加できます。また、既にタグを設定している場合に、この IP アドレス範囲を追加するには、入力を開始したときに表示される現在のタグの一覧からタグを選択します。  <br/> |
|**カテゴリ** <br/> | タグに分類項目を割り当てることにより、特定の IP アドレスからのアクティビティを簡単に識別できるようにします。次のオプションから選択します。<br/> **管理**管理者のすべての IP アドレス。  <br/> **クラウドプロバイダー**クラウド内のプロキシの IP アドレス。  <br/> **企業**内部ネットワーク内のすべての IP アドレス、ブランチオフィス、および wi-fi ローミングアドレス。  <br/> **危険**危険性があると考えられるすべての ip アドレス (過去に表示された疑わしい ip アドレス、競合企業のネットワーク内の ip アドレスなど)。既定では、危険なカテゴリには、**匿名プロキシ**と**Tor**という2つの IP タグが含まれています。 <br/> **VPN**リモートワーカーが使用する任意の IP アドレス。  <br/> |
   
7. [**保存**] を選択します。
    
IP アドレスの範囲を設定した後は、これらの変更による影響を受けるのは将来のイベントだけであることに注意してください。
  
## <a name="next-steps"></a>次の手順

- [アクティビティポリシーとアラート](activity-policies-and-alerts.md)
    
- [異常検出ポリシー](anomaly-detection-policies-in-ocas.md)
    
- [SIEM サーバーの統合](integrate-your-siem-server-with-office-365-cas.md)
    
- [Office 365 Cloud App Security の警告の確認と処理](review-office-365-cas-alerts.md)
    

