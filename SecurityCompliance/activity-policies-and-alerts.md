---
title: Office 365 Cloud App Security のアクティビティ ポリシーと警告
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
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: アクティビティの特定の活動の発生または発生する頻度が高すぎる場合に発生する警告を設定するのには Office 365 のクラウド アプリケーションのセキュリティとポリシーを定義します。ポリシーを設定すると、警告をトリガーするでは、に関する通知を受け取ることができ、特定の活動を監視します。
ms.openlocfilehash: 6f5039d09dea98de970ab4bd28e95a6cfad73db4
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015009"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="5e57e-104">Office 365 Cloud App Security のアクティビティ ポリシーと警告</span><span class="sxs-lookup"><span data-stu-id="5e57e-104">Activity policies and alerts in Office 365 Cloud App Security</span></span>

<span data-ttu-id="5e57e-105">セキュリティ管理の高度な office 365 は、Office 365 のクラウド アプリケーションのセキュリティをされます。</span><span class="sxs-lookup"><span data-stu-id="5e57e-105">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="5e57e-106">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="5e57e-106">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="5e57e-107">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="5e57e-107">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="5e57e-108">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="5e57e-108">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="5e57e-109">使用率。</span><span class="sxs-lookup"><span data-stu-id="5e57e-109">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="5e57e-110">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="5e57e-111">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="5e57e-112">コースです!</span><span class="sxs-lookup"><span data-stu-id="5e57e-112">You are here!</span></span>  <br/> [<span data-ttu-id="5e57e-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="5e57e-113">Next step</span></span>](anomaly-detection-policies-in-ocas.md) <br/> |[<span data-ttu-id="5e57e-114">使用します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="5e57e-p102">Office 365 のクラウド アプリケーションのセキュリティ、頻繁に発生するか発生する特定の活動の警告をトリガーする高度なクラウドの管理ポリシーです。たとえば、ユーザーが Office 365 にサインインしようとして 1 分以内に 70 回失敗するとします。ほかのユーザーが、7,000 のファイルをダウンロードまたは、署名されている、カナダから別の場所でそのユーザーをサポートしているときに表示されますと仮定します。または、さらにすると他のユーザーのアカウントが侵害されている攻撃者は、組織のクラウド アプリケーションの機密データにアクセスするのにはそのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-p102">With Office 365 Cloud App Security, advanced cloud management policies trigger alerts for specific activities that happen or happen too frequently. For example, suppose a user tries to sign in to Office 365 and fails 70 times in one minute. Suppose that another user downloads 7,000 files, or appears to be signed in from Canada, when that user is supposed to be in another location. Or worse, suppose that someone's account has been compromised, and an attacker is using that account to access your organization's cloud apps and sensitive data.</span></span>
  
<span data-ttu-id="5e57e-p103">[グローバル ・ アドミニストレーターまたはセキュリティ管理者](permissions-in-the-security-and-compliance-center.md)は場合、イベントには、このようなときに発生するアクティビティのアラートに通知します。何が起こったかを調べることができますまでは、ユーザー アカウントを一時中断するなど、特定のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5e57e-p103">If you are a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), activity alerts notify you when events like these occur. You can then take specific actions, such as suspending a user account until you can investigate what happened.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e57e-p104">Office 365 のクラウド アプリケーションのセキュリティ ポリシーとは異なる[では、Office 365 のセキュリティ ポリシーの警告&amp;コンプライアンス センター](alert-policies.md)です。この資料に記載されているポリシーは、Office 365 のクラウド アプリケーションのセキュリティ ・ ポータルで定義され、効率よく活動は、組織のクラウド環境を管理します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-p104">Office 365 Cloud App Security policies are different from [alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md). The activity policies described in this article are defined in the Office 365 Cloud App Security portal, and can help you better manage your organization's cloud environment.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="5e57e-123">はじめに</span><span class="sxs-lookup"><span data-stu-id="5e57e-123">Before you begin</span></span>

<span data-ttu-id="5e57e-124">以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5e57e-124">Make sure that:</span></span>
  
- <span data-ttu-id="5e57e-125">組織の[Office 365 のクラウド アプリケーションのセキュリティ](office-365-cas-overview.md)、およびサービスは、[有効に](turn-on-office-365-cas.md)します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-125">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="5e57e-126">[監査ログ](turn-audit-log-search-on-or-off.md)有効にする、Office 365 環境に。</span><span class="sxs-lookup"><span data-stu-id="5e57e-126">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="5e57e-127">グローバル アドミニストレーターまたはセキュリティ管理者は、Office 365 としています。</span><span class="sxs-lookup"><span data-stu-id="5e57e-127">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="create-a-new-activity-policy"></a><span data-ttu-id="5e57e-128">新しい活動ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-128">Create a new activity policy</span></span>

1. <span data-ttu-id="5e57e-129">グローバル管理者またはセキュリティ管理者に移動します。[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5e57e-129">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="5e57e-130">セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="5e57e-130">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="5e57e-131">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-131">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    <span data-ttu-id="5e57e-132">Office 365 のクラウド アプリケーションのセキュリティ ポリシーのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-132">This takes you to the Office 365 Cloud App Security Policies page.</span></span>
    
    ![ポリシー] ページで開始する場合、Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに移動すると、](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
4. <span data-ttu-id="5e57e-134">**ポリシーの作成**をクリックし、**アクティビティのポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-134">Click **Create policy**, and then select **Activity policy**.</span></span>
    
    ![O365 CA でポリシーを作成するときにアクティビティのポリシーと異常検出のポリシーの間で選択できます。](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
5. <span data-ttu-id="5e57e-p105">**活動ポリシーの作成**] ページで、[**ポリシーの名前**および**説明**を指定します。既定のテンプレートに基づいてポリシーを確立を**ポリシー テンプレート**の一覧でいずれかを選択するか、テンプレートを使用せず、独自のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-p105">On the **Create activity policy** page, specify the **Policy name** and **Description**. To base your policy on a default template, choose one in the **Policy template** list, or create your own policy without using a template.</span></span> 
    
    ![Office 365 のクラウド アプリケーションのセキュリティでは、アクティビティのポリシーを作成できます。](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
6. <span data-ttu-id="5e57e-p106">**ポリシーの重要度**(低、中、または高) どの程度深刻にする場合はこのポリシーは、アラートをトリガーするかを測定するを選択します。こうと、後で読んでいるときにアラートをフィルターします。</span><span class="sxs-lookup"><span data-stu-id="5e57e-p106">Choose a **Policy severity** (Low, Medium, or High) that measures how serious it is to you if this policy triggers an alert. This will help you filter alerts when you're reviewing them later.</span></span> 
    
7. <span data-ttu-id="5e57e-p107">このポリシーの**カテゴリ**を選択します。これにより、フィルターと並べ替えのアラートがトリガーされた、またはグループ ポリシーの変更を加えることを確認しているときにします。</span><span class="sxs-lookup"><span data-stu-id="5e57e-p107">Choose a **Category** for this policy. This will help you filter and sort alerts that have been triggered, or to group policies when you're reviewing them to make changes.</span></span> 
    
8. <span data-ttu-id="5e57e-143">他のアクションや、このポリシーに基づいてアラートをトリガーするメトリックを設定するには、**アクティビティのフィルター**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-143">Choose **Activity filters** to set up other actions or metrics that will trigger an alert based on this policy.</span></span> 
    
9. <span data-ttu-id="5e57e-144">**パラメーターに一致するアクティビティ**は、[繰り返しのアクティビティの指定した数が、アラートがトリガーする前に必要な場合または 1 つのアクティビティのフィルターに一致すると、ポリシー違反がトリガーされるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-144">Under **Activity match parameters**, specify whether a policy violation will be triggered when a single activity matches the filters, or if a specified number of repeated activities is required before the alert triggers.</span></span>
    
    <span data-ttu-id="5e57e-145">**繰り返し活動**を選択する場合は、アクティビティ、時間枠の数を指定し、特定のアプリケーション内のユーザーまたは他のアプリケーションで同じユーザーに対しての違反の数かどうか。</span><span class="sxs-lookup"><span data-stu-id="5e57e-145">If you select **Repeated activity**, specify the number of activities, the time frame, and whether a violation will count for a user within a specific app or for the same user with any app.</span></span>
    
10. <span data-ttu-id="5e57e-146">必要に応じて、(e メール、テキスト メッセージ、またはその両方) には、このポリシーから通知を受信するのには追加の通知を作成する**作成するアラート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-146">Optionally, you can select **Create alert** to create additional alerts to receive notifications from this policy (via email, text message, or both).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="5e57e-147">電子メール プロバイダーが no-reply@cloudappsecurity.com から送信された電子メールをブロックしないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-147">Make sure that your email provider doesn't block emails sent from no-reply@cloudappsecurity.com.</span></span> 
  
11. <span data-ttu-id="5e57e-148">ユーザーを一時停止またはアプリケーションを Office 365 にサインインするユーザーを必要とするアラートがトリガーされたときに実行される**アクション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-148">Choose the **Actions** that should be taken when an alert is triggered to suspend the user or require the user to sign in again to Office 365 apps.</span></span> 
    
12. <span data-ttu-id="5e57e-149">ポリシーの作成を完了する**を作成する**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-149">Choose **Create** to finish creating your policy.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="5e57e-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="5e57e-150">Next steps</span></span>

- [<span data-ttu-id="5e57e-151">異常検出のポリシー</span><span class="sxs-lookup"><span data-stu-id="5e57e-151">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="5e57e-152">SIEM サーバーを統合します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-152">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="5e57e-153">確認し、アラート アクションを実行</span><span class="sxs-lookup"><span data-stu-id="5e57e-153">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="5e57e-154">管理を簡略化する IP アドレスをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="5e57e-154">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

