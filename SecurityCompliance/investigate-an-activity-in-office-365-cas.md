---
title: Office 365 Cloud App Security のアクティビティの調査
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: 'office 365 Cloud App Security では、アクティビティとアカウントを調べて調査することで、office 365 環境で起こっていることを確認できます。 '
ms.openlocfilehash: 0cc3860d953b40b0b0c247af6fb2b157d1abb235
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218967"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a>Office 365 Cloud App Security のアクティビティの調査
  
|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |[展開を開始する](turn-on-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](#next-steps) <br/> |
   
office 365 Cloud App Security は[office 365 監査ログ](detailed-properties-in-the-office-365-audit-log.md)と連携して動作します。office 365 Cloud App Security では、全体管理者またはセキュリティ管理者として、アクティビティログページを使用して、組織が Office 365 を使用する方法に関する潜在的な問題を確認できます。
  
## <a name="how-to-get-to-the-activity-log-page"></a>アクティビティログページにアクセスする方法

1. Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。
  
2. 画面上部のナビゲーションバーで、[**アクティビティログ**の**調査** \> ] を選択します。<br/>![O365 CAS ポータルで、[調査] を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="review-and-investigate-activities"></a>アクティビティの確認と調査

[アクティビティログ] ページには、Office 365 を使用して組織内で実行されているさまざまなアクティビティの一覧が表示されます。画面の上部でフィルターを使用して、特定の種類のアクティビティまたは特定のユーザーに焦点を当てることができます。たとえば、次の図は、組織の Office 365 管理者アカウントのパスワード変更に関する情報を示しています。
  
![Office 365 Cloud App Security で、[アクティビティ\>ログの調査] を選択します。](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
アクティビティログの各アイテムを確認するときに、省略記号をクリックして、関連するその他のアクティビティを検索できます。たとえば、同じ IP アドレスまたは同じ国/地域の同じ種類の他のアクティビティを表示できます。
  
その他のさまざまなアクティビティについての情報を表示することもできます。たとえば、アクティビティログに表示できるアクティビティのいくつかを次に示します。
  
- グループに追加された、またはグループから削除されたメンバー
    
- ユーザーライセンスの変更
    
- 内部または外部で共有しているファイルまたはフォルダー
    
- 作成または削除されたサイトまたはサイトコレクション
    
- メール転送ルール
    
アクティビティログページを使用すると、組織内のユーザーが Office 365 をどのように使用しているか、また、どのような問題が発生しているかについて理解できます。
  
## <a name="next-steps"></a>次の手順

- [Office 365 Cloud App Security の警告の確認と処理](review-office-365-cas-alerts.md)
    
- [Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する
    

