---
title: デバイス セキュリティ ポリシーを作成して展開する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/9/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewDevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: d310f556-8bfb-497b-9bd7-fe3c36ea2fd6
description: '作成し、モバイル デバイスの管理に役立つ Office 365 でのセキュリティ ポリシーを展開する手順は、Office 365 で、組織の情報を不正アクセスから保護します。 '
ms.openlocfilehash: ab1fc1960a3e55eb3080dde7df0ec742c58b2cc7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272072"
---
# <a name="create-and-deploy-device-security-policies"></a><span data-ttu-id="9daa7-103">デバイス セキュリティ ポリシーを作成して展開する</span><span class="sxs-lookup"><span data-stu-id="9daa7-103">Create and deploy device security policies</span></span>

<span data-ttu-id="9daa7-p101">Office 365 でモバイル デバイスの管理を使用するには Office 365 の組織の情報を不正アクセスから保護するセキュリティ ポリシーを作成します。デバイスのユーザーが Office 365 のライセンスが適用され、Office 365 の MDM のデバイスを登録するには、組織内で任意のモバイル デバイスにポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p101">You can use Mobile Device Management for Office 365 to create security policies that help protect your organization's information on Office 365 from unauthorized access. You can apply policies to any mobile device in your organization where the user of the device has an applicable Office 365 license and has enrolled the device in MDM for Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="9daa7-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="9daa7-106">Before you begin</span></span>

- <span data-ttu-id="9daa7-p102">デバイス、モバイル デバイスのアプリケーション、および Office 365 の MDM をサポートするセキュリティ設定について説明します。[Office 365 でモバイル デバイス管理の機能](capabilities-of-mobile-device-management.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p102">Learn about the devices, mobile device apps, and security settings that MDM for Office 365 supports. See [Capabilities of Mobile Device Management for Office 365](capabilities-of-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="9daa7-p103">ポリシーを適用する Office 365 のユーザーを含むセキュリティ グループを作成し、ユーザーの Office 365 へのアクセスをブロックから除外する場合します。新しいポリシーを組織に展開する前にテストすること、ポリシーで少数のユーザーに展開することをお勧めします。作成し、自分自身または小さい番号 Office 365 ユーザーのポリシーをテストすることをだけを含むセキュリティ グループを使用できます。セキュリティ グループの詳細については、[作成、編集、またはセキュリティ グループを削除する](https://go.microsoft.com/fwlink/p/?LinkId=518555)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p103">Create security groups that include Office 365 users that you want to deploy policies to and for users that you might want to exclude from being blocked access to Office 365. We recommend that before you deploy a new policy to your organization, you test the policy by deploying it to a small number of users. You can create and use a security group that includes just yourself or a small number Office 365 users that can test the policy for you. To learn more about security groups, see [Create, edit, or delete a security group](https://go.microsoft.com/fwlink/p/?LinkId=518555).</span></span>
    
- <span data-ttu-id="9daa7-p104">**重要な:** モバイル デバイスのポリシーを作成するには、アクティブにし、Office 365 の MDM を設定する必要があります。[Office 365 でモバイル デバイス管理の概要](overview-of-mdm.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p104">**Important:** Before you can create a mobile device policy, you must activate and set up MDM for Office 365. See [Overview of Mobile Device Management for Office 365](overview-of-mdm.md).</span></span>
    
- <span data-ttu-id="9daa7-115">作成し、Office 365 でモバイル デバイス管理のポリシーを展開、Office 365 のグローバル管理者にする必要があります。参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1)です。</span><span class="sxs-lookup"><span data-stu-id="9daa7-115">To create and deploy mobile device management policies in Office 365, you need to be an Office 365 global admin. See [Permissions in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1).</span></span>
    
- <span data-ttu-id="9daa7-p105">ポリシーを展開する前に、組織が Office 365 を MDM のデバイスを登録することの潜在的な影響を知ることができます。によってどのようにポリシーを設定すると、準拠していないデバイスは、Office 365 へのアクセスがブロックされることが、インストールされているアプリケーション、写真、および、登録されているデバイスでの個人情報を含むデータを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p105">Before you deploy policies, let your organization know the potential impacts of enrolling a device in MDM for Office 365. Depending on how you set up the policies, noncompliant devices can be blocked from accessing Office 365 and data, including installed applications, photos, and personal information on an enrolled device, can be deleted.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9daa7-p106">ポリシーおよび Office 365 の MDM で作成したアクセス ルールは、Exchange ActiveSync モバイル デバイス メールボックス ポリシーと Exchange 管理センターで作成されたデバイス アクセスのルールをオーバーライドします。デバイスが Exchange ActiveSync モバイル デバイス メールボックス ポリシーを使用すると、Office 365 の MDM に登録されているか、デバイスに適用するデバイス アクセス ルールは無視されます。Exchange ActiveSync の詳細については、 [Exchange のオンラインでの Exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p106">Policies and access rules created in MDM for Office 365 will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center. After a device is enrolled in MDM for Office 365, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored. To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).</span></span> 
  
## <a name="step-1-create-a-security-policy-and-deploy-to-a-test-group"></a><span data-ttu-id="9daa7-121">手順 1: セキュリティ ポリシーを作成し、テスト グループに展開</span><span class="sxs-lookup"><span data-stu-id="9daa7-121">Step 1: Create a security policy and deploy to a test group</span></span>

<span data-ttu-id="9daa7-p107">を起動する前にアクティブにしている Office 365 の MDM を設定を確認します。手順については、[概要のモバイル デバイスの管理](overview-of-mdm.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p107">Before you can start, make sure you have activated and set up MDM for Office 365. See [Overview of Mobile Device Management for Office 365](overview-of-mdm.md) for instructions.</span></span> 
  
1. <span data-ttu-id="9daa7-124">セキュリティで、Office 365 の&amp;コンプライアンス部門、**データ損失の防止**に\>**デバイスのセキュリティ ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="9daa7-124">In Office 365, in the Security &amp; Compliance Center, go to **Data loss prevention** \> **Device security policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9daa7-125">**デバイス セキュリティ ポリシー**は、モバイル デバイスの管理を有効にした後にのみ、メニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-125">The **Device security policies** will appear in the menu only after you have activated Mobile device management.</span></span> 
  
2. <span data-ttu-id="9daa7-126">**+ ポリシーの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-126">Choose **+ Create a policy**.</span></span>
    
    ![デバイス セキュリティ ポリシー] の下の MDN デバイス ポリシーを作成します。](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
3. <span data-ttu-id="9daa7-128">新しいポリシーの**名前**と**説明**を指定し、し、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-128">Specify a **Name** and **Description** for the new policy, and then choose **Next**.</span></span>
    
    ![デバイスのセキュリティ ポリシーの名前を設定します。](media/d382e845-4a7f-4f72-8a09-813ea4cbd0c4.png)
  
4. <span data-ttu-id="9daa7-130">**デバイスに必要な要件は何ですか?** ページで、組織内のモバイル デバイスに適用要件を指定し、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-130">On the **What requirements do you want to have on devices?** page, specify the requirements you want applied to mobile devices in your organization, and then choose **Next**.</span></span>
    
    ![デバイスのセキュリティ ポリシーの設定] ページ](media/186b3bd5-5e3d-4059-978f-94113111a8ca.png)
  
5. <span data-ttu-id="9daa7-132">**たい項目を構成する?** ページで、組織内のモバイル デバイスに適用する追加要件を指定し、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-132">On the **What do you want to configure?** page, specify any additional requirements you want applied to mobile devices in your organization, and then choose **Next**.</span></span>
    
6. <span data-ttu-id="9daa7-133">**今すぐこのポリシーを適用するか?** ページ、 **[はい]** をクリックし選択 **+ 追加**。</span><span class="sxs-lookup"><span data-stu-id="9daa7-133">On the **Do you want to apply this policy now?** page, choose **Yes**, and then choose **+ Add**.</span></span> 
    
    ![ポリシーを追加します。](media/89ab7cab-1b7a-4c78-9aa6-3db7d7667f8e.png)
  
7. <span data-ttu-id="9daa7-135">組織に展開し、[**追加**する前にポリシーをテストするグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-135">Select the group(s) who will test the policy before you deploy it to your organization, and then choose **Add**.</span></span>
    
8. <span data-ttu-id="9daa7-136">[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-136">Choose **Next**.</span></span>
    
9. <span data-ttu-id="9daa7-137">新しいデバイス ポリシーの詳細を確認して、**このポリシーの作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-137">Review and confirm the details of the new device policy, and then choose **Create this policy**.</span></span>
    
    ![Finsih のデバイス ポリシーを作成するのには、このポリシーの作成を選択します。](media/e410bcf3-8a36-44ed-9fea-00e742db06fb.png)
  
10. <span data-ttu-id="9daa7-139">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9daa7-139">Click **Close**.</span></span>
    
<span data-ttu-id="9daa7-p108">ポリシーを適用する各ユーザーは、次に、モバイル デバイスを使用して Office 365 にサインインするときにそのデバイスにプッシュするポリシーがあります。ユーザーにポリシーが適用する前に携帯電話がなかった場合、ポリシーを展開した後が表示されます通知[登録し、Office 365 の MDM をアクティブにする手順](https://go.microsoft.com/fwlink/?LinkId=615272)にはが含まれますデバイスにします。登録を完了するまで電子メールへのアクセス、OneDrive、およびその他のサービスとなります。Intune 会社のポータル アプリケーションを使用して登録を完了した後は、サービスを使用して行うことができるし、ポリシーは、そのデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p108">Each user that the policy applies to will have the policy pushed to their device the next time they sign in to Office 365 using their mobile device. If users haven't had a policy applied to their mobile device before, then after you deploy the policy, they'll get a notification on their device that includes the [steps to enroll and activate MDM for Office 365](https://go.microsoft.com/fwlink/?LinkId=615272). Until they complete enrollment, access to email, OneDrive, and other services will be restricted. After they complete enrollment using the Intune Company Portal app, they'll be able to use the services and the policy will be applied to their device.</span></span>
  
## <a name="step-2-verify-your-policy-works"></a><span data-ttu-id="9daa7-144">手順 2: は、ポリシーの動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-144">Step 2: Verify your policy works</span></span>

<span data-ttu-id="9daa7-145">セキュリティ ポリシーを作成したら、ポリシーが組織に展開する前に期待どおりに動作するかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9daa7-145">After you've created a security policy, you should check that the policy works as you expect before you deploy it to your organization.</span></span>
  
1. <span data-ttu-id="9daa7-146">Office 365 に移動**セキュリティ&amp;コンプライアンス センター** \> **データの損失防止** \> **デバイスの管理**です。</span><span class="sxs-lookup"><span data-stu-id="9daa7-146">In Office 365, go to **Security &amp; Compliance Center** \> **Data loss prevention** \> **Device management**.</span></span>
    
2. <span data-ttu-id="9daa7-p109">**Office 365 でモバイル デバイスの管理**] ページで、ポリシーが適用されているユーザー デバイスの状態を確認してください。フィルターまたは並べ替えすることができます**すべて**を表示するすべてのデバイス、またはブロックされたデバイスを表示するのには**ブロック**しています。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p109">On the **Mobile Device Management for Office 365** page, Check the status of user devices that have the policy applied. You can filter or sort by **All** to view all devices, or **Blocked** to view blocked devices.</span></span> 
    
    ![MDM によって管理されているデバイスを表示します。](media/5c9fd069-b716-40d8-9b36-f9cfeae2139f.png)
  
3. <span data-ttu-id="9daa7-p110">フル] または [選択したデバイスのワイプを行うことができます。手順については、 [Office 365 でモバイル デバイスをワイプする](wipe-a-mobile-device.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p110">You can also do a full or selective wipe on the device. For instructions, see [Wipe a mobile device in Office 365](wipe-a-mobile-device.md).</span></span>
    
## <a name="step-3-deploy-a-policy-to-your-organization"></a><span data-ttu-id="9daa7-152">ステップ 3: 組織にポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-152">Step 3: Deploy a policy to your organization</span></span>

<span data-ttu-id="9daa7-153">モバイル デバイスのポリシーを作成し、期待どおりに動作することを確認、したらは、組織に展開します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-153">After you've created a mobile device policy and verified that it works as expected, deploy it to your organization.</span></span>
  
1. <span data-ttu-id="9daa7-154">Office 365 に移動**セキュリティ&amp;コンプライアンス センター** \> **データの損失防止**\> **デバイスのセキュリティ ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="9daa7-154">In Office 365, go to **Security &amp; Compliance Center** \> **Data loss prevention**\> **Device security policies**.</span></span>
    
2. <span data-ttu-id="9daa7-155">、配置するポリシーを選択し、[**ポリシーの編集**」を選択、 \<_ポリシー名_\>パネルです。  </span><span class="sxs-lookup"><span data-stu-id="9daa7-155">Select the policy you want to deploy, and choose **Edit policy** in the \<  _policy name_\> panel.</span></span>
    
3. <span data-ttu-id="9daa7-156">**[展開]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-156">Select the **Deployment** tab.</span></span> 
    
4. <span data-ttu-id="9daa7-157">[**配置**] タブで **[はい]** の上に**1 つまたは複数のセキュリティ グループにこのポリシーを適用するユーザーを含む**、**追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-157">In the **Deployment** tab, choose **Yes** above **Select one or more security groups that contain the people you want to apply this policy to** and then **Add**.</span></span>
    
  - <span data-ttu-id="9daa7-p111">[**グループの選択**] パネルを追加するグループを検索することができます、エイリアスまたは表示名のいずれかにフィルターを適用することができます。**グループ**] ボックスの一覧から既存のグループを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p111">On the **Select Group** panel, you can search for a group to add, you can filter either by alias or by display name. You can also add an existing group from the **Groups** list.</span></span> 
    
    <span data-ttu-id="9daa7-160">ポリシーを適用するのには複数のグループを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-160">You can add multiple groups to apply the policy to.</span></span>
    
    <span data-ttu-id="9daa7-161">パネルの下部に**追加**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-161">Choose **Add** on the bottom of the panel.</span></span> 
    
5. <span data-ttu-id="9daa7-162">[**展開**] タブには、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-162">Choose **Save** on the **Deployment** tab.</span></span> 
    
    ![MDM のポリシーを組織に展開します。](media/dc3e7fe5-201a-4e45-abe3-fc93e0b59028.png)
  
<span data-ttu-id="9daa7-p112">ポリシーを適用する各ユーザーは、次に、モバイル デバイスから Office 365 にサインインするときにそのデバイスにプッシュするポリシーがあります。ユーザーに、モバイル デバイスに適用されるポリシーがなかった場合は、[デバイスに通知を受け取る](https://go.microsoft.com/fwlink/?LinkId=615272)を登録し、Office 365 の MDM のアクティブ化の手順を実行、します。登録を完了すると、ポリシーは、デバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p112">Each user that the policy applies to will have the policy pushed to their device the next time they sign in to Office 365 from their mobile device. If users haven't had a policy applied to their mobile device, they'll [get a notification on their device](https://go.microsoft.com/fwlink/?LinkId=615272) with steps to enroll and activate it for MDM for Office 365. After they've completed the enrollment, the policy will be applied to their device.</span></span> 
  
## <a name="step-4-block-email-access-for-unsupported-devices"></a><span data-ttu-id="9daa7-167">手順 4: サポートされていないデバイスの電子メール アクセスをブロック</span><span class="sxs-lookup"><span data-stu-id="9daa7-167">Step 4: Block email access for unsupported devices</span></span>

<span data-ttu-id="9daa7-p113">保護するには、組織の情報を遮断する Office 365 の電子メールを Office 365 の MDM によってサポートされていないモバイル デバイス用のアプリケーション アクセス。サポートされているデバイスの一覧については、 [Office 365 でモバイル デバイス管理の機能](capabilities-of-mobile-device-management.md)を参照してください。これを行うには。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p113">To help secure your organization's information, you should block app access to Office 365 email for mobile devices that are not supported by MDM for Office 365. See [Capabilities of built-in Mobile Device Management for Office 365](capabilities-of-mobile-device-management.md) for a list of devices that are supported. To do this:</span></span> 
  
1. <span data-ttu-id="9daa7-171">セキュリティに&amp;コンプライアンス センター\> **データの損失防止**\> **デバイスのセキュリティ ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="9daa7-171">Go to Security &amp; Compliance Center\> **Data loss prevention**\> **Device security policies**.</span></span>
    
2. <span data-ttu-id="9daa7-172">**組織全体のデバイス アクセス設定の管理**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-172">Select **Manage organization-wide device access settings**.</span></span>
    
    ![コンプライアンス センターを参照して\>デバイスと、デバイスのアクセス設定の管理] リンクをクリックします。](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. <span data-ttu-id="9daa7-174">サポートされていないデバイスをブロックするには、下にある**場合は、Office 365 の MDM によってデバイスがサポートされていないかを許可またはブロックすることから、組織の電子メールにアクセスするのには Exchange アカウントを使用して****ブロック**を選択して\>**を保存**します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-174">To block unsupported devices, choose **Block** under **If a device isn't supported by MDM for Office 365, do you want to allow or block it from using an Exchange account to access your organization's email** \> **Save**.</span></span>
  
## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a><span data-ttu-id="9daa7-175">手順 5:条件付きのアクセス チェックから除外するセキュリティ グループを選択する</span><span class="sxs-lookup"><span data-stu-id="9daa7-175">Step 5: Choose security groups to be excluded from conditional access checks</span></span>

<span data-ttu-id="9daa7-p114">モバイル デバイスに対する条件付きアクセス チェックから一部のユーザーを除外しようとして、それらのユーザー用に 1 つ以上のセキュリティ グループを作成した場合は、この手順でそのセキュリティ グループを追加します。これらのグループ内のユーザーには、サポートされているモバイル デバイスに関するポリシーが適用されません。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p114">If you want to exclude some people from conditional access checks on their mobile devices and you've created one or more security groups for those people, add the security groups here. The people in these groups will not have any policies enforced for their supported mobile devices.</span></span>
  
1. <span data-ttu-id="9daa7-178">セキュリティに&amp;コンプライアンス センター\> **データの損失防止**\> **デバイスのセキュリティ ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="9daa7-178">Go to Security &amp; Compliance Center\> **Data loss prevention**\> **Device security policies**.</span></span>
    
2. <span data-ttu-id="9daa7-179">**組織全体のデバイス アクセス設定の管理**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-179">Select **Manage organization-wide device access settings**.</span></span>
    
    ![コンプライアンス センターを参照して\>デバイスと、デバイスのアクセス設定の管理] リンクをクリックします。](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. <span data-ttu-id="9daa7-p115">Office 365 へのアクセスをブロックする対象から除外したいユーザーを持つセキュリティ グループを追加するのには**追加**を選択します。ユーザーは、このリストに追加されましたが、サポートされていないデバイスを使用すると Office 365 の電子メールにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p115">Select **Add** to add the security group that has users that you'd like to exclude from being blocked access to Office 365. When a user has been added to this list, they'll be able to access Office 365 email when using an unsupported device.</span></span> 
    
4. <span data-ttu-id="9daa7-183">**グループの選択**] パネルで使用するセキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-183">Select the security group you want to use in the **Select group** panel.</span></span> 
    
5. <span data-ttu-id="9daa7-184">名、および、**追加**を選択して\>**を保存**します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-184">Select the name, and then **Add** \> **Save**.</span></span>
    
6. <span data-ttu-id="9daa7-185">[**組織全体のデバイス アクセス設定**] パネルには、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9daa7-185">On the **Organization-wide device access settings** panel, choose **Save**.</span></span>
  
## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a><span data-ttu-id="9daa7-186">セキュリティ ポリシーは他のデバイスの種類にどのような影響を与えますか。</span><span class="sxs-lookup"><span data-stu-id="9daa7-186">What is the impact of security policies on different device types?</span></span>

<span data-ttu-id="9daa7-p116">ユーザーのデバイスにポリシーを適用する場合、各デバイスへの影響はさまざまなデバイスの種類間でいくらか異なります。さまざまなデバイスにおけるポリシーの影響の例については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p116">When you apply a policy to user devices, the impact on each device varies somewhat between different device types. See the following table for examples of the impact of policies on different devices.</span></span>
  


|<span data-ttu-id="9daa7-189">**セキュリティ ポリシー**</span><span class="sxs-lookup"><span data-stu-id="9daa7-189">**Security Policy**</span></span>|<span data-ttu-id="9daa7-190">**Windows Phone 8.1 +**</span><span class="sxs-lookup"><span data-stu-id="9daa7-190">**Windows Phone 8.1+**</span></span>|<span data-ttu-id="9daa7-191">**Android 4 以降**</span><span class="sxs-lookup"><span data-stu-id="9daa7-191">**Android 4+**</span></span>|<span data-ttu-id="9daa7-192">**Samsung 連盟ノックス ・**</span><span class="sxs-lookup"><span data-stu-id="9daa7-192">**Samsung Knox**</span></span>|<span data-ttu-id="9daa7-193">**IOS 6 +**</span><span class="sxs-lookup"><span data-stu-id="9daa7-193">**IOS 6+**</span></span>|<span data-ttu-id="9daa7-194">**メモ**</span><span class="sxs-lookup"><span data-stu-id="9daa7-194">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9daa7-195">暗号化されたバックアップが必要</span><span class="sxs-lookup"><span data-stu-id="9daa7-195">Require encrypted backup</span></span>  <br/> |<span data-ttu-id="9daa7-196">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-196">✖</span></span>  <br/> |<span data-ttu-id="9daa7-197">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-197">✖</span></span>  <br/> |<span data-ttu-id="9daa7-198">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-198">✔</span></span>  <br/> |<span data-ttu-id="9daa7-199">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-199">✔</span></span>  <br/> |<span data-ttu-id="9daa7-200">iOS の暗号化バックアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="9daa7-200">IOS encrypted backup required.</span></span>  <br/> |
|<span data-ttu-id="9daa7-201">クラウド バックアップの禁止</span><span class="sxs-lookup"><span data-stu-id="9daa7-201">Block cloud backup</span></span>  <br/> |<span data-ttu-id="9daa7-202">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-202">✖</span></span>  <br/> |<span data-ttu-id="9daa7-203">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-203">✔</span></span>  <br/> |<span data-ttu-id="9daa7-204">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-204">✔</span></span>  <br/> |<span data-ttu-id="9daa7-205">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-205">✔</span></span>  <br/> |<span data-ttu-id="9daa7-206">Android での Google バックアップが禁止され (淡色表示)、iOS でのクラウド バックアップが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-206">Block Google backup on Android (grayed out), cloud backup on iOS.</span></span>  <br/> |
|<span data-ttu-id="9daa7-207">ドキュメントの同期の禁止</span><span class="sxs-lookup"><span data-stu-id="9daa7-207">Block document synchronization</span></span>  <br/> |<span data-ttu-id="9daa7-208">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-208">✖</span></span>  <br/> |<span data-ttu-id="9daa7-209">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-209">✖</span></span>  <br/> |<span data-ttu-id="9daa7-210">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-210">✖</span></span>  <br/> |<span data-ttu-id="9daa7-211">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-211">✔</span></span>  <br/> |<span data-ttu-id="9daa7-212">iOS:クラウド内のドキュメントがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-212">iOS: Block documents in the cloud.</span></span>  <br/> |
|<span data-ttu-id="9daa7-213">写真の同期の禁止</span><span class="sxs-lookup"><span data-stu-id="9daa7-213">Block photo synchronization</span></span>  <br/> |<span data-ttu-id="9daa7-214">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-214">✖</span></span>  <br/> |<span data-ttu-id="9daa7-215">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-215">✖</span></span>  <br/> |<span data-ttu-id="9daa7-216">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-216">✖</span></span>  <br/> |<span data-ttu-id="9daa7-217">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-217">✔</span></span>  <br/> |<span data-ttu-id="9daa7-218">iOS (ネイティブ):写真ストリームがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-218">iOS (native): Block Photo Stream.</span></span>  <br/> |
|<span data-ttu-id="9daa7-219">画面キャプチャの禁止</span><span class="sxs-lookup"><span data-stu-id="9daa7-219">Block screen capture</span></span>  <br/> |<span data-ttu-id="9daa7-220">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-220">✔</span></span>  <br/> |<span data-ttu-id="9daa7-221">X</span><span class="sxs-lookup"><span data-stu-id="9daa7-221">X</span></span>  <br/> |<span data-ttu-id="9daa7-222">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-222">✔</span></span>  <br/> |<span data-ttu-id="9daa7-223">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-223">✔</span></span>  <br/> |<span data-ttu-id="9daa7-224">実行時にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-224">Blocked when attempted.</span></span>  <br/> |
|<span data-ttu-id="9daa7-225">ビデオ会議のブロック</span><span class="sxs-lookup"><span data-stu-id="9daa7-225">Block video conference</span></span>  <br/> |<span data-ttu-id="9daa7-226">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-226">✖</span></span>  <br/> |<span data-ttu-id="9daa7-227">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-227">✖</span></span>  <br/> |<span data-ttu-id="9daa7-228">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-228">✖</span></span>  <br/> |<span data-ttu-id="9daa7-229">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-229">✔</span></span>  <br/> |<span data-ttu-id="9daa7-230">iOS では FaceTime が禁止されます。Skype などは禁止されません。</span><span class="sxs-lookup"><span data-stu-id="9daa7-230">FaceTime blocked on iOS, not Skype or others.</span></span>  <br/> |
|<span data-ttu-id="9daa7-231">診断データの送信の禁止</span><span class="sxs-lookup"><span data-stu-id="9daa7-231">Block sending diagnostic data</span></span>  <br/> |<span data-ttu-id="9daa7-232">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-232">✖</span></span>  <br/> |<span data-ttu-id="9daa7-233">X</span><span class="sxs-lookup"><span data-stu-id="9daa7-233">X</span></span>  <br/> |<span data-ttu-id="9daa7-234">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-234">✔</span></span>  <br/> |<span data-ttu-id="9daa7-235">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-235">✔</span></span>  <br/> |<span data-ttu-id="9daa7-236">Android における Google のクラッシュ レポートの送信が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-236">Block sending Google crash report on Android.</span></span>  <br/> |
|<span data-ttu-id="9daa7-237">アプリ ストアへのアクセスの禁止</span><span class="sxs-lookup"><span data-stu-id="9daa7-237">Block access to app store</span></span>  <br/> |<span data-ttu-id="9daa7-238">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-238">✔</span></span>  <br/> |<span data-ttu-id="9daa7-239">X</span><span class="sxs-lookup"><span data-stu-id="9daa7-239">X</span></span>  <br/> |<span data-ttu-id="9daa7-240">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-240">✔</span></span>  <br/> |<span data-ttu-id="9daa7-241">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-241">✔</span></span>  <br/> |<span data-ttu-id="9daa7-242">[アプリ ストア] アイコンが、Android ではホーム ページに表示されません。Windows では無効になります。iOS では表示されません。</span><span class="sxs-lookup"><span data-stu-id="9daa7-242">App store icon missing on Android home page, disabled on Windows, missing on iOS.</span></span>  <br/> |
|<span data-ttu-id="9daa7-243">アプリ ストアにパスワードが必要</span><span class="sxs-lookup"><span data-stu-id="9daa7-243">Require password for app store</span></span>  <br/> |<span data-ttu-id="9daa7-244">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-244">✖</span></span>  <br/> |<span data-ttu-id="9daa7-245">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-245">✖</span></span>  <br/> |<span data-ttu-id="9daa7-246">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-246">✖</span></span>  <br/> |<span data-ttu-id="9daa7-247">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-247">✔</span></span>  <br/> |<span data-ttu-id="9daa7-248">iOS:iTunes の購入にパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="9daa7-248">iOS: Password required for iTunes purchases.</span></span>  <br/> |
|<span data-ttu-id="9daa7-249">リムーバブル記憶域への接続の禁止</span><span class="sxs-lookup"><span data-stu-id="9daa7-249">Block connection to removable storage</span></span>  <br/> |<span data-ttu-id="9daa7-250">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-250">✔</span></span>  <br/> |<span data-ttu-id="9daa7-251">X</span><span class="sxs-lookup"><span data-stu-id="9daa7-251">X</span></span>  <br/> |<span data-ttu-id="9daa7-252">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-252">✔</span></span>  <br/> |<span data-ttu-id="9daa7-253">該当なし</span><span class="sxs-lookup"><span data-stu-id="9daa7-253">NA</span></span>  <br/> |<span data-ttu-id="9daa7-254">Android:SD カードは設定で淡色表示され、Windows からユーザーに通知され、ここにインストールされたアプリは使用できません</span><span class="sxs-lookup"><span data-stu-id="9daa7-254">Android: SD card will be grayed out in settings, Windows notifies user, apps installed there are not available</span></span>  <br/> |
|<span data-ttu-id="9daa7-255">Bluetooth 接続の禁止</span><span class="sxs-lookup"><span data-stu-id="9daa7-255">Block Bluetooth connection</span></span>  <br/> |<span data-ttu-id="9daa7-256">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-256">✔</span></span>  <br/> |\*\*\*  <br/> |\*\*\*  <br/> |<span data-ttu-id="9daa7-257">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-257">✖</span></span>  <br/> |<span data-ttu-id="9daa7-p117">\*\*\*Android の設定として BlueTooth を無効にできません。BlueTooth を必要とするすべてのトランザクションを無効にして代わりに、: 高度なオーディオ配信、オーディオ/ビデオ リモート コントロール、ハンズフリー デバイス、ヘッドセット、電話帳へのアクセスとシリアル ポートです。次のいずれかを使用する場合は、ページの下部にある小さなトースト メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p117">\*\*\*We can't disable BlueTooth as a setting on Android. Instead, we disable all the transactions that require BlueTooth: Advanced Audio Distribution, Audio/Video Remote Control, hands-free devices, headset, Phone Book Access, and Serial Port. A small toast message appears at the bottom of the page when any of these are used.</span></span>  <br/> |
   
## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a><span data-ttu-id="9daa7-261">ポリシーを削除した場合やポリシーからユーザーを削除した場合に行われる処理</span><span class="sxs-lookup"><span data-stu-id="9daa7-261">What happens when you delete a policy or remove a user from the policy?</span></span>

<span data-ttu-id="9daa7-p118">ポリシーを削除した場合、またはポリシーの配置する先のグループからユーザーを削除すると、ユーザーのデバイスからポリシーの設定、Office 365 の電子メール プロファイルとキャッシュされた e メールを削除する場合があります。別のデバイスの種類の削除は、内容を確認するのには次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p118">When you delete a policy or remove a user from a group to which the policy was deployed to, the policy settings, Office 365 email profile and cached emails may be removed from the user's device. See the following table to see what is removed for the different device types:</span></span>
  
|<span data-ttu-id="9daa7-264">**削除される内容**</span><span class="sxs-lookup"><span data-stu-id="9daa7-264">**What's removed**</span></span>|<span data-ttu-id="9daa7-265">**Windows Phone 8.1 +**</span><span class="sxs-lookup"><span data-stu-id="9daa7-265">**Windows Phone 8.1+**</span></span>|<span data-ttu-id="9daa7-266">**iOS 6 +**</span><span class="sxs-lookup"><span data-stu-id="9daa7-266">**iOS 6+**</span></span>|<span data-ttu-id="9daa7-267">**Android 4 + (Samsung 連盟ノックス ・を含む)**</span><span class="sxs-lookup"><span data-stu-id="9daa7-267">**Android 4+ (including Samsung Knox)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9daa7-268">マネージ電子メール プロファイル\*</span><span class="sxs-lookup"><span data-stu-id="9daa7-268">Managed email profiles\*</span></span>  <br/> |<span data-ttu-id="9daa7-269">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-269">✖</span></span>  <br/> |<span data-ttu-id="9daa7-270">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-270">✔</span></span>  <br/> |<span data-ttu-id="9daa7-271">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-271">✖</span></span>  <br/> |
|<span data-ttu-id="9daa7-272">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="9daa7-272">Policy settings</span></span>  <br/> |<span data-ttu-id="9daa7-273">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-273">✔</span></span>  <br/>           <span data-ttu-id="9daa7-274">ただし、**[デバイスからの診断データ送信の禁止]** は除きます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-274">Except for **Block sending diagnostic data from device.**</span></span> <br/> |<span data-ttu-id="9daa7-275">✔</span><span class="sxs-lookup"><span data-stu-id="9daa7-275">✔</span></span>  <br/> |<span data-ttu-id="9daa7-276">✖</span><span class="sxs-lookup"><span data-stu-id="9daa7-276">✖</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9daa7-277">\*オプションを使用して、ポリシーが配置されている場合**電子メールのプロファイルを管理**し、管理対象の電子メール プロファイルを選択したし、キャッシュされ、e メールのプロファイルがユーザーのデバイスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="9daa7-277">\*If the policy was deployed with the option **Email profile is managed** selected, then the managed email profile and cached emails in that profile will be deleted from the user's device.</span></span> 
  
<span data-ttu-id="9daa7-p119">削除されたポリシーに適用する各ユーザーは、次回のモバイル デバイスを Office 365 の MDM を使用して確認、デバイスから削除するポリシーがあります。これらのユーザーのデバイスに適用する新しいポリシーを展開する場合は、Office 365 は、MDM に再登録する求めします。</span><span class="sxs-lookup"><span data-stu-id="9daa7-p119">Each user that the removed policy applied to will have the policy removed from their device the next time their mobile device checks in with MDM for Office 365 . If you deploy a new policy that applies to these users' devices, they'll be prompted to re-enroll in MDM for Office 365.</span></span>
  
<span data-ttu-id="9daa7-280">[デバイスをワイプ](wipe-a-mobile-device.md)することも、いずれかの方法を完全に、または選択的にワイプ、デバイスから組織の情報です。</span><span class="sxs-lookup"><span data-stu-id="9daa7-280">You can also [wipe a device](wipe-a-mobile-device.md), either completely, or selectively wipe organizational information from the device.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9daa7-281">関連項目</span><span class="sxs-lookup"><span data-stu-id="9daa7-281">Related Topics</span></span>

[<span data-ttu-id="9daa7-282">Office 365 用のモバイル デバイス管理の概要</span><span class="sxs-lookup"><span data-stu-id="9daa7-282">Overview of Mobile Device Management for Office 365</span></span>](overview-of-mdm.md)
  
[<span data-ttu-id="9daa7-283">Office 365 用のモバイル デバイス管理の機能</span><span class="sxs-lookup"><span data-stu-id="9daa7-283">Capabilities of Mobile Device Management for Office 365</span></span>](capabilities-of-mobile-device-management.md)
  

