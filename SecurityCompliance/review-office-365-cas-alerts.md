---
title: Office 365 Cloud App Security の警告の確認と処理
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
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: Office 365 Cloud App Security の [通知] ページを使用して、潜在的な問題を表示し、処理を実行します。 通知を破棄または解決し、必要に応じてユーザーアカウントを中断することができます。
ms.openlocfilehash: ddef10293fca7b722a13babdca5c05bbe2398cb3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261482"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a>Office 365 Cloud App Security の警告の確認と処理
  
|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |[展開を開始する](turn-on-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](#next-steps) <br/> |
   
Office 365 Cloud App Security の [通知] ページを使用して、潜在的な問題を表示したり、必要に応じてアクションを実行したりできます。
  
> [!NOTE]
> この記事に記載されているタスクを実行するには、全体管理者またはセキュリティ管理者である必要があります。 「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可」を](permissions-in-the-security-and-compliance-center.md)参照してください。 
  
## <a name="how-to-get-to-the-alerts-page"></a>[通知] ページにアクセスする方法

1. Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。
  
2. 画面上部のナビゲーションバーで、[**通知**] を選択します。<br/>![[通知] ページには、トリガーされた通知と実行されたアクションが表示されます。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
 
> [!NOTE]
> Cloud App security alerts は、Security & コンプライアンスセンターにも表示されます ([**アラート** > **表示**] [アラート] に移動します。 ただし、現時点では、Cloud App security ポータルと security & コンプライアンスセンターの両方でこれらのアラートを解決する必要があります。 詳細については、「 [Cloud App Security alerts を表示](alert-policies.md#viewing-cloud-app-security-alerts)する」を参照してください)。 
 
## <a name="review-and-handle-alerts"></a>通知を確認して処理する

通知は、さらに調べる必要がある Office 365 クラウド環境内のアクティビティを識別するのに役立ちます。 表示される通知に基づいて、新しいポリシーを作成したり、既存のポリシーを編集したりすることもできます。 たとえば、奇妙な場所からログオンしている管理者が表示された場合は、管理者が特定の場所から Office 365 にサインインできないようにするポリシーを設定することができます。
  
> [!TIP]
> 最も重要なものを最初に管理できるように、アラートを**カテゴリ**または**重要度**別にフィルター処理できます。 
  
各警告について、どのようなアクションを実行するかを決定できるようにするために、原因を調べます。 アラートの解決やユーザーアカウントの中断など、アラートの詳細を確認し、アクションを実行するには、通知を選択して [詳細] ページを開きます。 [詳細] ページでは、通知に関連するアクティビティログ、アカウント、およびユーザーを確認し、次のような操作を実行できます。
  
- **アラームを消す**警告が誤検知であった場合は、それを閉じます。 必要に応じて、省略した理由を説明するコメントを追加することもできます。 
    
- **アラートの解決**脅威ではないと判断された通知が発生した場合は、それを解決します。 必要に応じて、解決理由を説明するコメントを追加することもできます。 
    
- **Suspend**アカウントに対して認証されていないサインインが疑われる場合、たとえば他の国からサインインしている場合は、その人物が物理的にローカルオフィスにいることがわかっている場合は、何が起こっているのかを調査している間、[そのアカウントを中断](suspend-or-restore-an-account-in-ocas.md)することができます。 
    
## <a name="next-steps"></a>次のステップ

- [アクティビティを調べる](investigate-an-activity-in-office-365-cas.md)
    
- [ユーザーアカウントを中断または復元する](suspend-or-restore-an-account-in-ocas.md)
    
- サポートされている[Web トラフィックログとデータソース](web-traffic-logs-and-data-sources-for-ocas.md)の一覧を表示する
    
- [Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する
    

