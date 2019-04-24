---
title: Office 365 Cloud App Security のアクティビティ ポリシーと警告
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
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: Office 365 Cloud App Security を使用してアクティビティポリシーを定義し、特定のアクティビティが頻繁に発生したときにトリガーされる通知を設定します。 通知をトリガーするポリシーを設定すると、特定のアクティビティについて通知を受け、監視することができます。
ms.openlocfilehash: cfa58182ea35551ca3a3807c23e09c9f87c7be82
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242724"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="c5e75-104">Office 365 Cloud App Security のアクティビティ ポリシーと警告</span><span class="sxs-lookup"><span data-stu-id="c5e75-104">Activity policies and alerts in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="c5e75-105">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c5e75-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="c5e75-106">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c5e75-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="c5e75-107">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c5e75-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="c5e75-108">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="c5e75-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="c5e75-109">評価の開始</span><span class="sxs-lookup"><span data-stu-id="c5e75-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="c5e75-110">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="c5e75-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="c5e75-111">ここでは、</span><span class="sxs-lookup"><span data-stu-id="c5e75-111">You are here!</span></span>  <br/> [<span data-ttu-id="c5e75-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="c5e75-112">Next step</span></span>](anomaly-detection-policies-in-ocas.md) <br/> |[<span data-ttu-id="c5e75-113">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="c5e75-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="c5e75-114">Office 365 cloud App Security では、高度なクラウド管理ポリシーによって、発生した、または頻繁に発生した特定のアクティビティについてのアラートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="c5e75-114">With Office 365 Cloud App Security, advanced cloud management policies trigger alerts for specific activities that happen or happen too frequently.</span></span> <span data-ttu-id="c5e75-115">たとえば、ユーザーが Office 365 にサインインしようとし、1分間に70回失敗したとします。</span><span class="sxs-lookup"><span data-stu-id="c5e75-115">For example, suppose a user tries to sign in to Office 365 and fails 70 times in one minute.</span></span> <span data-ttu-id="c5e75-116">別のユーザーが、別の場所にいると想定されている場合、7000ファイルをダウンロードするか、カナダからサインインするように表示されるとします。</span><span class="sxs-lookup"><span data-stu-id="c5e75-116">Suppose that another user downloads 7,000 files, or appears to be signed in from Canada, when that user is supposed to be in another location.</span></span> <span data-ttu-id="c5e75-117">さらに悪いことは、ユーザーのアカウントが侵害されており、攻撃者がそのアカウントを使用して組織のクラウドアプリや機密データにアクセスしているということです。</span><span class="sxs-lookup"><span data-stu-id="c5e75-117">Or worse, suppose that someone's account has been compromised, and an attacker is using that account to access your organization's cloud apps and sensitive data.</span></span>
  
<span data-ttu-id="c5e75-118">[グローバル管理者またはセキュリティ管理者](permissions-in-the-security-and-compliance-center.md)の場合は、このようなイベントが発生したときにアクティビティの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5e75-118">If you are a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), activity alerts notify you when events like these occur.</span></span> <span data-ttu-id="c5e75-119">その後、何が起こったのかを調査できるまで、ユーザーアカウントの中断など、特定のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c5e75-119">You can then take specific actions, such as suspending a user account until you can investigate what happened.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c5e75-120">office 365 Cloud App security ポリシーは[、office 365 セキュリティ&amp;コンプライアンスセンターのアラートポリシーと](alert-policies.md)は異なります。</span><span class="sxs-lookup"><span data-stu-id="c5e75-120">Office 365 Cloud App Security policies are different from [alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md).</span></span> <span data-ttu-id="c5e75-121">この記事で説明するアクティビティポリシーは、Office 365 cloud App Security ポータルで定義されており、組織のクラウド環境をより適切に管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c5e75-121">The activity policies described in this article are defined in the Office 365 Cloud App Security portal, and can help you better manage your organization's cloud environment.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c5e75-122">始める前に</span><span class="sxs-lookup"><span data-stu-id="c5e75-122">Before you begin</span></span>

<span data-ttu-id="c5e75-123">以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c5e75-123">Make sure that:</span></span>
  
- <span data-ttu-id="c5e75-124">組織に[Office 365 Cloud App Security](office-365-cas-overview.md)があり、サービスがオン[になっ](turn-on-office-365-cas.md)ている。</span><span class="sxs-lookup"><span data-stu-id="c5e75-124">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="c5e75-125">Office 365 環境では、[監査ログ](turn-audit-log-search-on-or-off.md)が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="c5e75-125">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="c5e75-126">Office 365 の全体管理者またはセキュリティ管理者であること。</span><span class="sxs-lookup"><span data-stu-id="c5e75-126">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="create-a-new-activity-policy"></a><span data-ttu-id="c5e75-127">新しいアクティビティポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c5e75-127">Create a new activity policy</span></span>

1. <span data-ttu-id="c5e75-128">グローバル管理者またはセキュリティ管理者は、Cloud App security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) にアクセスして、サインインします。</span><span class="sxs-lookup"><span data-stu-id="c5e75-128">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> <br><span data-ttu-id="c5e75-129">これにより、Office 365 Cloud App Security Policies ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5e75-129">This takes you to the Office 365 Cloud App Security Policies page.</span></span><br><span data-ttu-id="c5e75-130">![Office 365 Cloud App Security ポータルに移動するときに、[ポリシー] ページから始めます。](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span><span class="sxs-lookup"><span data-stu-id="c5e75-130">![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span></span>
  
2. <span data-ttu-id="c5e75-131">[**ポリシーの作成**] をクリックし、[**アクティビティポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-131">Click **Create policy**, and then select **Activity policy**.</span></span><br><span data-ttu-id="c5e75-132">![O365 CAS でポリシーを作成するときは、アクティビティポリシーと異常検出ポリシーのいずれかを選択できます。](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)</span><span class="sxs-lookup"><span data-stu-id="c5e75-132">![When you create a policy in O365 CAS, you can choose between Activity policies and Anomaly Detection policies.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)</span></span>
  
3. <span data-ttu-id="c5e75-133">[**アクティビティポリシーの作成**] ページで、**ポリシーの名前**と**説明**を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-133">On the **Create activity policy** page, specify the **Policy name** and **Description**.</span></span> <span data-ttu-id="c5e75-134">ポリシーを既定のテンプレートに基づいて作成するには、[**ポリシーテンプレート**] の一覧からポリシーを選択するか、テンプレートを使用せずに独自のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-134">To base your policy on a default template, choose one in the **Policy template** list, or create your own policy without using a template.</span></span><br><span data-ttu-id="c5e75-135">![Office 365 Cloud App Security を使用してアクティビティポリシーを作成できます。](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)</span><span class="sxs-lookup"><span data-stu-id="c5e75-135">![You can create activity policies with Office 365 Cloud App Security.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)</span></span>
  
4. <span data-ttu-id="c5e75-136">このポリシーによって警告がトリガーされた場合に、深刻な事態を測定する**ポリシーの重要度**(低、中、高) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-136">Choose a **Policy severity** (Low, Medium, or High) that measures how serious it is to you if this policy triggers an alert.</span></span> <span data-ttu-id="c5e75-137">これは、後でメッセージを確認しているときに通知をフィルター処理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c5e75-137">This will help you filter alerts when you're reviewing them later.</span></span> 
    
5. <span data-ttu-id="c5e75-138">このポリシーの**カテゴリ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-138">Choose a **Category** for this policy.</span></span> <span data-ttu-id="c5e75-139">これにより、トリガーされた通知をフィルター処理したり並べ替えたり、変更を行うために確認しているときにグループポリシーに分類することができます。</span><span class="sxs-lookup"><span data-stu-id="c5e75-139">This will help you filter and sort alerts that have been triggered, or to group policies when you're reviewing them to make changes.</span></span> 
    
6. <span data-ttu-id="c5e75-140">このポリシーに基づいて通知をトリガーする他のアクションまたは指標を設定するには、[**アクティビティフィルター** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-140">Choose **Activity filters** to set up other actions or metrics that will trigger an alert based on this policy.</span></span> 
    
7. <span data-ttu-id="c5e75-141">[**アクティビティ一致パラメーター**] で、1つのアクティビティがフィルターに一致したときにポリシー違反が発生するかどうか、またはアラートがトリガーされるまでに指定した数の繰り返しアクティビティが必要な場合に、ポリシー違反をトリガーするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-141">Under **Activity match parameters**, specify whether a policy violation will be triggered when a single activity matches the filters, or if a specified number of repeated activities is required before the alert triggers.</span></span><br><span data-ttu-id="c5e75-142">**繰り返しアクティビティ**を選択する場合は、アクティビティの数、時間枠、および特定のアプリ内のユーザー、または任意のアプリを使用しているユーザーに対して違反がカウントされるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-142">If you select **Repeated activity**, specify the number of activities, the time frame, and whether a violation will count for a user within a specific app or for the same user with any app.</span></span>
    
8. <span data-ttu-id="c5e75-143">必要に応じて、[**警告の作成**] を選択して、このポリシーから通知を受信する追加の通知を作成できます (電子メール、テキストメッセージ、またはその両方を使用)。</span><span class="sxs-lookup"><span data-stu-id="c5e75-143">Optionally, you can select **Create alert** to create additional alerts to receive notifications from this policy (via email, text message, or both).</span></span><br><span data-ttu-id="c5e75-144">**メールプロバイダーがから`no-reply@cloudappsecurity.com`送信されるメールをブロックしないように**します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-144">**Make sure that your email provider doesn't block emails sent from `no-reply@cloudappsecurity.com`**.</span></span> 
  
9. <span data-ttu-id="c5e75-145">通知がトリガーされたときに実行する**アクション**を選択して、ユーザーを中断したり、ユーザーが Office 365 アプリに再度サインインするように要求します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-145">Choose the **Actions** that should be taken when an alert is triggered to suspend the user or require the user to sign in again to Office 365 apps.</span></span> 
    
10. <span data-ttu-id="c5e75-146">[**作成**] を選択して、ポリシーの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="c5e75-146">Choose **Create** to finish creating your policy.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="c5e75-147">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c5e75-147">Next steps</span></span>

- [<span data-ttu-id="c5e75-148">異常検出ポリシー</span><span class="sxs-lookup"><span data-stu-id="c5e75-148">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="c5e75-149">SIEM サーバーの統合</span><span class="sxs-lookup"><span data-stu-id="c5e75-149">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="c5e75-150">通知を確認して処理を実行する</span><span class="sxs-lookup"><span data-stu-id="c5e75-150">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="c5e75-151">IP アドレスをグループ化して管理を簡素化する</span><span class="sxs-lookup"><span data-stu-id="c5e75-151">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

