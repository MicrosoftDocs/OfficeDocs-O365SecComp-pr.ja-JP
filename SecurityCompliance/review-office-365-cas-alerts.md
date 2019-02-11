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
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="0d1a3-104">Office 365 Cloud App Security の警告の確認と処理</span><span class="sxs-lookup"><span data-stu-id="0d1a3-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="0d1a3-105">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0d1a3-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="0d1a3-106">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0d1a3-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="0d1a3-107">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0d1a3-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="0d1a3-108">使用率。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="0d1a3-109">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="0d1a3-110">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="0d1a3-111">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="0d1a3-112">コースです!</span><span class="sxs-lookup"><span data-stu-id="0d1a3-112">You are here!</span></span>  <br/> [<span data-ttu-id="0d1a3-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="0d1a3-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="0d1a3-114">Office 365 のクラウド アプリケーションのセキュリティで [通知] ページを使用するには潜在的な懸案事項を表示し、必要な場合は、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0d1a3-p102">この記事でタスクを実行するには、グローバル ・ アドミニストレーターまたはセキュリティ管理者である必要があります。参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-p102">You must be a global administrator or security administrator to perform the tasks in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="0d1a3-117">[通知] ページを表示する方法</span><span class="sxs-lookup"><span data-stu-id="0d1a3-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="0d1a3-118">クラウド アプリケーションのセキュリティ関連ポータルに移動 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-118">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="0d1a3-119">画面の上部にナビゲーション ・ バーの**アラート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-119">In the navigation bar across the top of the screen, choose **Alerts**.</span></span><br/><span data-ttu-id="0d1a3-120">![[アラート] ページで、トリガーされたアラートと行った操作を確認できます。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span><span class="sxs-lookup"><span data-stu-id="0d1a3-120">![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span></span>
  
## <a name="review-and-handle-alerts"></a><span data-ttu-id="0d1a3-121">アラートの確認とハンドル</span><span class="sxs-lookup"><span data-stu-id="0d1a3-121">Review and handle alerts</span></span>

<span data-ttu-id="0d1a3-p103">アラートでは、さらに調査することも、Office 365 のクラウド環境での活動を識別できます。新しいポリシーを作成または表示するアラートに基づく既存のポリシーを編集することもできます。たとえば、奇妙な場所からログオンする管理者を参照するくださいと、管理者が特定の場所から Office 365 にサインインすることを防止するポリシーを設定するのにはするがあります。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-p103">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further. You might also decide to create new policies or edit existing policies based on the alerts you see. For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="0d1a3-125">最初の最も重要なものを管理できるように、**カテゴリ\*\*\*\*重要度**のアラートをフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-125">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="0d1a3-p104">各アラートには、何が原因で実行するアクションを決定するために参照してください。アラートの詳細についてを参照して、アラートの解決や、ユーザー アカウントを一時中断するなどのアクションを実行する詳細ページを表示するアラートを選択します。[詳細] ページで、アクティビティ ・ ログ、アカウント、およびアラートに関連するユーザーを確認し、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-p104">For each alert, look into what caused it so you can decide what action to take. To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page. On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="0d1a3-p105">**消す**アラートが誤検出の場合は、それを無視します。却下の理由を説明するコメントを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-p105">**Dismiss** If the alert was a false positive, dismiss it. You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="0d1a3-p106">**アラートを解決します。** わかっている活動に脅威がないによって警告が発生した場合、それを解決します。解決の理由を説明するコメントを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-p106">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it. You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="0d1a3-133">**中断**その人がわかっている場合、他の国から署名などの他のユーザー アカウントをローカル オフィスでは物理的に、許可されていない記号が疑われる場合することができます[、アカウントを一時停止](suspend-or-restore-an-account-in-ocas.md)の処理状況を調査するときにします。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-133">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="0d1a3-134">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0d1a3-134">Next steps</span></span>

- [<span data-ttu-id="0d1a3-135">アクティビティを調査します。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-135">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="0d1a3-136">サスペンド モードまたはユーザー アカウントを復元します。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-136">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="0d1a3-137">サポートされている[Web トラフィックのログとデータ ソース](web-traffic-logs-and-data-sources-for-ocas.md)の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-137">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="0d1a3-138">[Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="0d1a3-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

