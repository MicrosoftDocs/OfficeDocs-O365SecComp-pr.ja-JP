---
title: Office 365 Cloud App Security でユーザー アカウントを停止または復元する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Office 365 のクラウド アプリケーションのセキュリティ、実行できる管理操作を一時停止またはユーザー アカウントの一時中断を解除するのには。 '
ms.openlocfilehash: 09d6ae870aa1a6b0a619ccf20f8cc19b392e23a8
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014849"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="ac0b6-103">Office 365 Cloud App Security でユーザー アカウントを停止または復元する</span><span class="sxs-lookup"><span data-stu-id="ac0b6-103">Suspend or restore a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="ac0b6-104">セキュリティ管理の高度な office 365 は、Office 365 のクラウド アプリケーションのセキュリティをされます。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="ac0b6-105">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ac0b6-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="ac0b6-106">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ac0b6-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="ac0b6-107">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ac0b6-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="ac0b6-108">使用率。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="ac0b6-109">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="ac0b6-110">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="ac0b6-111">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="ac0b6-112">コースです!</span><span class="sxs-lookup"><span data-stu-id="ac0b6-112">You are here!</span></span>  <br/> [<span data-ttu-id="ac0b6-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="ac0b6-113">Next steps</span></span>](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="ac0b6-p101">Office 365 の組織のユーザー アカウントのいずれかが侵害されている警告が表示されると仮定します。または、ユーザー アカウントに問題があることを示すアラートを受信したと仮定します。Office 365 のクラウド アプリケーションのセキュリティ、ユーザー アカウントを中断でき、後で受信するアラートを調査した後に復元できます。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-p101">Suppose that you receive an alert that one of your organization's user accounts for Office 365 has been compromised. Or, suppose that you've received an alert that indicates something is wrong with a user account. With Office 365 Cloud App Security, you can suspend a user account and later restore it after you have investigated the alerts you receive.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac0b6-p102">Office 365 のクラウド アプリケーションのセキュリティは、Office 365 エンタープライズ E5 に使用できます。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合、Office 365 のクラウド アプリケーションのセキュリティがアドオンとして購入できます。(グローバル管理者は、Office 365 管理センターを選択して**請求** \> **サブスクリプションを追加**します)。詳細についてを参照してください[Office 365 のプラットフォーム サービスの説明: Office 365 のセキュリティ&amp;コンプライアンス センター](https://technet.microsoft.com/en-us/library/dn933793.aspx) [購入またはビジネスのための Office 365 のアドオンを編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)するとします。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-p102">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="ac0b6-120">Office 365 のクラウド アプリケーションのセキュリティでユーザー アカウントを中断するのには</span><span class="sxs-lookup"><span data-stu-id="ac0b6-120">To suspend a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="ac0b6-p103">ユーザー アカウントを一時停止するとから、もう一度サインイン ユーザーを防止します。直接**では、署名ブロック**にサインインしている状態を設定するのには Office 365 でユーザー アカウントを編集と同じです。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-p103">When you suspend a user account, you prevent the user from signing in again. It's the same as editing the user account directly in Office 365 to set the Sign-in status to **Sign-in blocked**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac0b6-p104">ユーザーがそれらを中断するか、サインイン状態を編集することによって、Office 365 にサインインをブロックする場合は、かかる場合が 1 時間、またはすべてのユーザーのデバイスとクライアント ([編集または Office 365 のユーザーを変更する](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)) を有効にするために注意します。場合は、ユーザーは、Office 365 にサインインしている、Office 365 でもう一度サインインするのには必要なときに、ブロックが反映されます。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-p104">If you block a user from signing in to Office 365, either by suspending them or by editing their sign-in status, be aware that it can take an hour or so to take effect on all of the user's devices and clients ([Edit or change a user in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)). If the user is signed in to Office 365, the block will take effect whenever Office 365 requires them to sign in again.</span></span> 
  
1. <span data-ttu-id="ac0b6-p105">[グローバル アドミニストレーターまたはセキュリティ管理者](permissions-in-the-security-and-compliance-center.md)に移動します。[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用してサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-p105">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="ac0b6-127">セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-127">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="ac0b6-128">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-128">Choose **Go to Office 365 Cloud App Security**.</span></span><br><span data-ttu-id="ac0b6-129">![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="ac0b6-129">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br>
  
4. <span data-ttu-id="ac0b6-130">画面の上部にナビゲーション ・ バーの**アラート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-130">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
5. <span data-ttu-id="ac0b6-131">[**アラート**] 列で、特定のユーザー アカウントに関連する警告をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-131">In the **Alert** column, double-click an alert that pertains to a specific user account.</span></span> 
    
6. <span data-ttu-id="ac0b6-132">[**アカウント**] で、[**状態**] 列の設定を選択![の設定アイコン](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **ユーザーの一時停止**します。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-132">Under **Accounts**, in the **Status** column, choose Settings ![settings icon](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **Suspend user**.</span></span>
    
## <a name="to-restore-a-user-account"></a><span data-ttu-id="ac0b6-133">ユーザー アカウントを復元するには</span><span class="sxs-lookup"><span data-stu-id="ac0b6-133">To restore a user account</span></span>

<span data-ttu-id="ac0b6-134">[Office 365 のユーザーを復元する](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-134">See [Restore a user in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="ac0b6-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="ac0b6-135">Next steps</span></span>

- [<span data-ttu-id="ac0b6-136">Office 365 Cloud App Security の警告の確認と処理</span><span class="sxs-lookup"><span data-stu-id="ac0b6-136">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="ac0b6-137">Office 365 Cloud App Security を使用して OAuth アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="ac0b6-137">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
    
- <span data-ttu-id="ac0b6-138">[Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="ac0b6-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

