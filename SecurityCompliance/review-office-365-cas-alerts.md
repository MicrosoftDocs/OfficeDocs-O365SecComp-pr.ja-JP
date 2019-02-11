---
title: Office 365 Cloud App Security の警告の確認と処理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: Office 365 のクラウド アプリケーションのセキュリティに潜在的な懸案事項を表示し、アクションを実行するのには [通知] ページを使用します。閉じるし、アラートを解決するまたは必要に応じて、ユーザー アカウントを一時停止できます。
ms.openlocfilehash: ff20b913553414d796f9653108ac9b8a3d84cb74
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603678"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a>Office 365 Cloud App Security の警告の確認と処理
  
|評価 * *\>**|計画 * *\>**|配置 * *\>**|使用率。|
|:-----|:-----|:-----|:-----|
|[評価を開始します。](office-365-cas-overview.md) <br/> |[計画の開始します。](get-ready-for-office-365-cas.md) <br/> |[展開を開始します。](turn-on-office-365-cas.md) <br/> |コースです!  <br/> [次の手順](#next-steps) <br/> |
   
Office 365 のクラウド アプリケーションのセキュリティで [通知] ページを使用するには潜在的な懸案事項を表示し、必要な場合は、アクションを実行します。
  
> [!NOTE]
> この記事でタスクを実行するには、グローバル ・ アドミニストレーターまたはセキュリティ管理者である必要があります。参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。 
  
## <a name="how-to-get-to-the-alerts-page"></a>[通知] ページを表示する方法

1. クラウド アプリケーションのセキュリティ関連ポータルに移動 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) し、サインインします。
  
2. 画面の上部にナビゲーション ・ バーの**アラート**を選択します。<br/>![[アラート] ページで、トリガーされたアラートと行った操作を確認できます。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
## <a name="review-and-handle-alerts"></a>アラートの確認とハンドル

アラートでは、さらに調査することも、Office 365 のクラウド環境での活動を識別できます。新しいポリシーを作成または表示するアラートに基づく既存のポリシーを編集することもできます。たとえば、奇妙な場所からログオンする管理者を参照するくださいと、管理者が特定の場所から Office 365 にサインインすることを防止するポリシーを設定するのにはするがあります。
  
> [!TIP]
> 最初の最も重要なものを管理できるように、**カテゴリ****重要度**のアラートをフィルターできます。 
  
各アラートには、何が原因で実行するアクションを決定するために参照してください。アラートの詳細についてを参照して、アラートの解決や、ユーザー アカウントを一時中断するなどのアクションを実行する詳細ページを表示するアラートを選択します。[詳細] ページで、アクティビティ ・ ログ、アカウント、およびアラートに関連するユーザーを確認し、次の操作を実行できます。
  
- **消す**アラートが誤検出の場合は、それを無視します。却下の理由を説明するコメントを追加することができます。 
    
- **アラートを解決します。** わかっている活動に脅威がないによって警告が発生した場合、それを解決します。解決の理由を説明するコメントを追加することができます。 
    
- **中断**その人がわかっている場合、他の国から署名などの他のユーザー アカウントをローカル オフィスでは物理的に、許可されていない記号が疑われる場合することができます[、アカウントを一時停止](suspend-or-restore-an-account-in-ocas.md)の処理状況を調査するときにします。 
    
## <a name="next-steps"></a>次のステップ

- [アクティビティを調査します。](investigate-an-activity-in-office-365-cas.md)
    
- [サスペンド モードまたはユーザー アカウントを復元します。](suspend-or-restore-an-account-in-ocas.md)
    
- サポートされている[Web トラフィックのログとデータ ソース](web-traffic-logs-and-data-sources-for-ocas.md)の一覧を表示します。
    
- [Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。
    

