---
title: Office 365 Cloud App Security を有効にする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ba919c73-d021-404d-9850-eec57e78678c
description: この記事では、office 365 cloud app security を有効にする方法について説明します。これは、cloud app security by Microsoft Azure で提供されています。
ms.openlocfilehash: 1227545b1e4d1521dc1820342f09aabdf16ec2c6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220367"
---
# <a name="turn-on-office-365-cloud-app-security"></a>Office 365 Cloud App Security を有効にする
  
|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](activity-policies-and-alerts.md) <br/> |[利用を開始する](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a>Office 365 Cloud App Security を有効にする

> [!IMPORTANT]
> 次のタスクを実行するには、全体管理者またはセキュリティ管理者である必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。office 365 Cloud App Security を正しく動作させるには、office 365 環境の**監査ログを有効にする必要があり**ます。詳細については、「 [Office 365 監査ログ検索をオンまたはオフにする](turn-audit-log-search-on-or-off.md)」を参照してください。 
  
1. グローバル管理者またはセキュリティ管理者とし[https://protection.office.com](https://security.microsoft.com)て、Office 365 の職場または学校アカウントを使用してサインインします。(これにより、セキュリティ&amp;コンプライアンスセンターに移動できます。) 
    
2. [**アラート** \> ] **[advanced alerts の管理**] に移動します。
    
3. [ **Office 365 Cloud App Security を有効にする**] を選択します。
    
4. [ **Office 365 Cloud App Security に移動**] を選択します。<br/>![セキュリティ&amp; /コンプライアンスセンターで、[高度な通知の管理] を選択して Office 365 Cloud App Security に移動します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>これにより、Office 365 Cloud App Security ポータルに移動します。ここで、レポートを表示したり、ポリシーを作成または編集したりすることができます。

Office 365 cloud app security を有効にした後は、cloud app security ポータルにアクセス[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)して、サインインします。
    
> [!NOTE]
> office 365 Cloud app security を有効にすると、office 365 のユーザーアカウントとユーザーアクティビティに関する監査情報が[Microsoft Cloud App security](https://aka.ms/whatiscas)に転送されます。これにより、Office 365 は高度な通知、フィルタリング、およびその他の機能を提供して、情報を取得し、疑わしいアクティビティに関するアクションを実行できるようにします。 
  
## <a name="next-steps"></a>次の手順

- [アクティビティポリシー](activity-policies-and-alerts.md)
    
- [異常検出ポリシー](anomaly-detection-policies-in-ocas.md)
    
- [SIEM サーバーの統合](integrate-your-siem-server-with-office-365-cas.md)
    
- [IP アドレスをグループ化して管理を簡素化する](group-your-ip-addresses-in-ocas.md)
    

