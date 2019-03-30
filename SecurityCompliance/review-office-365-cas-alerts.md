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
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000040"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="23fcb-104">Office 365 Cloud App Security の警告の確認と処理</span><span class="sxs-lookup"><span data-stu-id="23fcb-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="23fcb-105">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="23fcb-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="23fcb-106">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="23fcb-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="23fcb-107">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="23fcb-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="23fcb-108">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="23fcb-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="23fcb-109">評価の開始</span><span class="sxs-lookup"><span data-stu-id="23fcb-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="23fcb-110">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="23fcb-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="23fcb-111">展開を開始する</span><span class="sxs-lookup"><span data-stu-id="23fcb-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="23fcb-112">ここでは、</span><span class="sxs-lookup"><span data-stu-id="23fcb-112">You are here!</span></span>  <br/> [<span data-ttu-id="23fcb-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="23fcb-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="23fcb-114">Office 365 Cloud App Security の [通知] ページを使用して、潜在的な問題を表示したり、必要に応じてアクションを実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="23fcb-115">この記事に記載されているタスクを実行するには、全体管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="23fcb-115">You must be a global administrator or security administrator to perform the tasks in this article.</span></span> <span data-ttu-id="23fcb-116">「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可」を](permissions-in-the-security-and-compliance-center.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="23fcb-116">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="23fcb-117">[通知] ページにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="23fcb-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="23fcb-118">Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="23fcb-118">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="23fcb-119">画面上部のナビゲーションバーで、[**通知**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23fcb-119">In the navigation bar across the top of the screen, choose **Alerts**.</span></span><br/><span data-ttu-id="23fcb-120">![[通知] ページには、トリガーされた通知と実行されたアクションが表示されます。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span><span class="sxs-lookup"><span data-stu-id="23fcb-120">![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span></span>
 
> [!NOTE]
> <span data-ttu-id="23fcb-121">Cloud App security alerts は、Security & コンプライアンスセンターにも表示されます ([**アラート** > **表示**] [アラート] に移動します。</span><span class="sxs-lookup"><span data-stu-id="23fcb-121">Cloud App Security alerts are also visible in the Security & Compliance Center (go to **Alerts** > **View alerts**.</span></span> <span data-ttu-id="23fcb-122">ただし、現時点では、Cloud App security ポータルと security & コンプライアンスセンターの両方でこれらのアラートを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23fcb-122">Currently, however, you must resolve these alerts in both the Cloud App Security portal and the Security & Compliance Center.</span></span> <span data-ttu-id="23fcb-123">詳細については、「 [Cloud App Security alerts を表示](alert-policies.md#viewing-cloud-app-security-alerts)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="23fcb-123">To learn more, see [Viewing Cloud App Security alerts](alert-policies.md#viewing-cloud-app-security-alerts).)</span></span> 
 
## <a name="review-and-handle-alerts"></a><span data-ttu-id="23fcb-124">通知を確認して処理する</span><span class="sxs-lookup"><span data-stu-id="23fcb-124">Review and handle alerts</span></span>

<span data-ttu-id="23fcb-125">通知は、さらに調べる必要がある Office 365 クラウド環境内のアクティビティを識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-125">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further.</span></span> <span data-ttu-id="23fcb-126">表示される通知に基づいて、新しいポリシーを作成したり、既存のポリシーを編集したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-126">You might also decide to create new policies or edit existing policies based on the alerts you see.</span></span> <span data-ttu-id="23fcb-127">たとえば、奇妙な場所からログオンしている管理者が表示された場合は、管理者が特定の場所から Office 365 にサインインできないようにするポリシーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-127">For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="23fcb-128">最も重要なものを最初に管理できるように、アラートを**カテゴリ**または**重要度**別にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-128">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="23fcb-129">各警告について、どのようなアクションを実行するかを決定できるようにするために、原因を調べます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-129">For each alert, look into what caused it so you can decide what action to take.</span></span> <span data-ttu-id="23fcb-130">アラートの解決やユーザーアカウントの中断など、アラートの詳細を確認し、アクションを実行するには、通知を選択して [詳細] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-130">To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page.</span></span> <span data-ttu-id="23fcb-131">[詳細] ページでは、通知に関連するアクティビティログ、アカウント、およびユーザーを確認し、次のような操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-131">On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="23fcb-132">**アラームを消す**警告が誤検知であった場合は、それを閉じます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-132">**Dismiss** If the alert was a false positive, dismiss it.</span></span> <span data-ttu-id="23fcb-133">必要に応じて、省略した理由を説明するコメントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-133">You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="23fcb-134">**アラートの解決**脅威ではないと判断された通知が発生した場合は、それを解決します。</span><span class="sxs-lookup"><span data-stu-id="23fcb-134">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it.</span></span> <span data-ttu-id="23fcb-135">必要に応じて、解決理由を説明するコメントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-135">You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="23fcb-136">**Suspend**アカウントに対して認証されていないサインインが疑われる場合、たとえば他の国からサインインしている場合は、その人物が物理的にローカルオフィスにいることがわかっている場合は、何が起こっているのかを調査している間、[そのアカウントを中断](suspend-or-restore-an-account-in-ocas.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="23fcb-136">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="23fcb-137">次の手順</span><span class="sxs-lookup"><span data-stu-id="23fcb-137">Next steps</span></span>

- [<span data-ttu-id="23fcb-138">アクティビティを調べる</span><span class="sxs-lookup"><span data-stu-id="23fcb-138">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="23fcb-139">ユーザーアカウントを中断または復元する</span><span class="sxs-lookup"><span data-stu-id="23fcb-139">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="23fcb-140">サポートされている[Web トラフィックログとデータソース](web-traffic-logs-and-data-sources-for-ocas.md)の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="23fcb-140">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="23fcb-141">[Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する</span><span class="sxs-lookup"><span data-stu-id="23fcb-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

