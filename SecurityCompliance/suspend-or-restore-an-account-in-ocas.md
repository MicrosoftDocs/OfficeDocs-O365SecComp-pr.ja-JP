---
title: Office 365 Cloud App Security でユーザー アカウントを停止または復元する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Office 365 Cloud App Security では、ユーザーアカウントの中断または停止解除を行うことができるガバナンスアクションがあります。 '
ms.openlocfilehash: 10da1385f850fadf077b4e3f9e3a00e9e4629fdd
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862449"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="1b36c-103">Office 365 Cloud App Security でユーザー アカウントを停止または復元する</span><span class="sxs-lookup"><span data-stu-id="1b36c-103">Suspend or restore a user account in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="1b36c-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1b36c-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="1b36c-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1b36c-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="1b36c-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1b36c-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="1b36c-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="1b36c-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="1b36c-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="1b36c-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="1b36c-109">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="1b36c-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="1b36c-110">展開を開始する</span><span class="sxs-lookup"><span data-stu-id="1b36c-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="1b36c-111">ここでは、</span><span class="sxs-lookup"><span data-stu-id="1b36c-111">You are here!</span></span>  <br/> [<span data-ttu-id="1b36c-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="1b36c-112">Next steps</span></span>](#next-steps)<br/> |
   
<span data-ttu-id="1b36c-113">Office 365 用の組織のユーザーアカウントのいずれかが侵害されたという警告が表示されたとします。</span><span class="sxs-lookup"><span data-stu-id="1b36c-113">Suppose that you receive an alert that one of your organization's user accounts for Office 365 has been compromised.</span></span> <span data-ttu-id="1b36c-114">または、ユーザーアカウントで問題が発生したことを示す通知を受信したとします。</span><span class="sxs-lookup"><span data-stu-id="1b36c-114">Or, suppose that you've received an alert that indicates something is wrong with a user account.</span></span> <span data-ttu-id="1b36c-115">Office 365 Cloud App Security では、受信した通知を調査した後、ユーザーアカウントを中断してから復元することができます。</span><span class="sxs-lookup"><span data-stu-id="1b36c-115">With Office 365 Cloud App Security, you can suspend a user account and later restore it after you have investigated the alerts you receive.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1b36c-116">office 365 Cloud App Security は office 365 Enterprise E5 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="1b36c-116">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="1b36c-117">組織で別の office 365 Enterprise サブスクリプションを使用している場合、office 365 Cloud App Security をアドオンとして購入することができます。</span><span class="sxs-lookup"><span data-stu-id="1b36c-117">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="1b36c-118">(全体管理者として、Office 365 管理センターで、[**課金** \>の**サブスクリプションの追加**] を選択します。)詳細については、「office 365 プラットフォームサービスの説明」を参照してください[。 office 365 セキュリティ&amp;コンプライアンスセンター](https://technet.microsoft.com/en-us/library/dn933793.aspx)で、 [office 365 for business のアドオンを購入または編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)します。</span><span class="sxs-lookup"><span data-stu-id="1b36c-118">(As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="1b36c-119">Office 365 Cloud App Security でユーザーアカウントを中断するには</span><span class="sxs-lookup"><span data-stu-id="1b36c-119">To suspend a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="1b36c-120">ユーザーアカウントを中断すると、ユーザーが再度サインインするのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="1b36c-120">When you suspend a user account, you prevent the user from signing in again.</span></span> <span data-ttu-id="1b36c-121">Office 365 で直接ユーザーアカウントを編集して、サインインが**ブロック**されるようにサインイン状態を設定するのと同じです。</span><span class="sxs-lookup"><span data-stu-id="1b36c-121">It's the same as editing the user account directly in Office 365 to set the Sign-in status to **Sign-in blocked**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1b36c-122">ユーザーが office 365 にサインインすることを禁止している場合、中止することによって、またはサインイン状態を編集することによって、ユーザーのすべてのデバイスとクライアント ([Office 365 でユーザーを編集または変更](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)する) が有効になるまでに時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1b36c-122">If you block a user from signing in to Office 365, either by suspending them or by editing their sign-in status, be aware that it can take an hour or so to take effect on all of the user's devices and clients ([Edit or change a user in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)).</span></span> <span data-ttu-id="1b36c-123">ユーザーが office 365 にサインインしている場合、office 365 が再度サインインする必要がある場合は常にブロックが有効になります。</span><span class="sxs-lookup"><span data-stu-id="1b36c-123">If the user is signed in to Office 365, the block will take effect whenever Office 365 requires them to sign in again.</span></span> 
  
1. <span data-ttu-id="1b36c-124">[全体管理者またはセキュリティ管理者](permissions-in-the-security-and-compliance-center.md)とし[https://protection.office.com](https://protection.office.com)て、に移動し、職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1b36c-124">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> <span data-ttu-id="1b36c-125">(これにより、セキュリティ&amp;コンプライアンスセンターに移動できます。)</span><span class="sxs-lookup"><span data-stu-id="1b36c-125">(This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="1b36c-126">セキュリティ&amp; /コンプライアンスセンターで、[**警告** \>の**管理] [詳細通知の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b36c-126">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="1b36c-127">[ **Office 365 Cloud App Security に移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b36c-127">Choose **Go to Office 365 Cloud App Security**.</span></span><br><span data-ttu-id="1b36c-128">![セキュリティ&amp; /コンプライアンスセンターで、[高度な通知の管理] を選択して Office 365 Cloud App Security に移動します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="1b36c-128">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br>
  
4. <span data-ttu-id="1b36c-129">画面上部のナビゲーションバーで、[**通知**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b36c-129">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
5. <span data-ttu-id="1b36c-130">[**警告**] 列で、特定のユーザーアカウントに関連する警告をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b36c-130">In the **Alert** column, double-click an alert that pertains to a specific user account.</span></span> 
    
6. <span data-ttu-id="1b36c-131">[**アカウント**] の [**状態**] 列で、 ![[設定](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \>の設定] アイコン [**中断ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b36c-131">Under **Accounts**, in the **Status** column, choose Settings ![settings icon](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **Suspend user**.</span></span>
    
## <a name="to-restore-a-user-account"></a><span data-ttu-id="1b36c-132">ユーザーアカウントを復元するには</span><span class="sxs-lookup"><span data-stu-id="1b36c-132">To restore a user account</span></span>

<span data-ttu-id="1b36c-133">「 [Office のユーザーの復元 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b36c-133">See [Restore a user in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="1b36c-134">次の手順</span><span class="sxs-lookup"><span data-stu-id="1b36c-134">Next steps</span></span>

- [<span data-ttu-id="1b36c-135">Office 365 Cloud App Security の警告の確認と処理</span><span class="sxs-lookup"><span data-stu-id="1b36c-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="1b36c-136">Office 365 Cloud App Security を使用して OAuth アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="1b36c-136">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
    
- <span data-ttu-id="1b36c-137">[Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する</span><span class="sxs-lookup"><span data-stu-id="1b36c-137">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

