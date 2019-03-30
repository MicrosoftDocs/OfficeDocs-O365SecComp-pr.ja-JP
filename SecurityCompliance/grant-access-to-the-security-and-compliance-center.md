---
title: Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権をユーザーに付与する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: ユーザーは、セキュリティまたはコンプライアンス機能を管理する&amp;前に、Office 365 セキュリティコンプライアンスセンターでアクセス許可を割り当てる必要があります。
ms.openlocfilehash: 08b3781ceb48b9a8d5933a075106d7bd3b9ab17d
ms.sourcegitcommit: 799a958fcac643f62dfac6fa04020f2f4758635c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30997239"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="7402a-103">Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権をユーザーに付与する</span><span class="sxs-lookup"><span data-stu-id="7402a-103">Give users access to the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="7402a-104">ユーザーは、セキュリティまたはコンプライアンス機能を管理する&amp;前に、Office 365 セキュリティコンプライアンスセンターでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7402a-104">Users need to be assigned permissions in the Office 365 Security &amp; Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="7402a-105">セキュリティ&amp; /コンプライアンスセンターでは、Office 365 のグローバル管理者または組織の管理役割グループのメンバーとして、これらのアクセス許可をユーザーに与えることができます。</span><span class="sxs-lookup"><span data-stu-id="7402a-105">As an Office 365 global admin or member of the OrganizationManagement role group in the Security &amp; Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="7402a-106">ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。</span><span class="sxs-lookup"><span data-stu-id="7402a-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="7402a-107">セキュリティ/コンプライアンスセンターでユーザーに付与できるさまざまなアクセス許可の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターでアクセス許可](permissions-in-the-security-and-compliance-center.md)を確認する」を参照してください。 &amp;</span><span class="sxs-lookup"><span data-stu-id="7402a-107">For more information about the different permissions you can give to users in the Security &amp; Compliance Center, check out [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7402a-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="7402a-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7402a-109">この記事に記載されている手順を完了するには、Office 365 グローバル管理者である&amp;か、または、セキュリティコンプライアンスセンターの組織管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7402a-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security &amp; Compliance Center, to complete the steps in this article.</span></span>
    
- <span data-ttu-id="7402a-110">セキュリティ&amp; /コンプライアンスセンターの役割グループの名前は Exchange Online の役割グループと似ている場合がありますが、同じではありません。</span><span class="sxs-lookup"><span data-stu-id="7402a-110">Role groups for the Security &amp; Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span> 
    
- <span data-ttu-id="7402a-111">役割グループのメンバーシップは、Exchange Online とセキュリティ&amp;センターコンプライアンスセンターとの間で共有されません。</span><span class="sxs-lookup"><span data-stu-id="7402a-111">Role group memberships aren't shared between Exchange Online and the Security &amp; Compliance Center.</span></span>
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="7402a-112">Office 365 管理センターを使用して、別のユーザーにセキュリティ&amp;コンプライアンスセンターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="7402a-112">Use the Office 365 admin center to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="7402a-113">[Office 365 にサインインし、管理センターに移動し](https://go.microsoft.com/fwlink/p/?LinkId=525275)ます。</span><span class="sxs-lookup"><span data-stu-id="7402a-113">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>
    
2. <span data-ttu-id="7402a-114">Office 365 管理センターで、**管理センター**を開き、[**セキュリティ&amp;のコンプライアンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7402a-114">In the Office 365 admin center, open **Admin centers** and then click **Security &amp; Compliance**.</span></span> 
    
3. <span data-ttu-id="7402a-115">セキュリティ&amp; /コンプライアンスセンターで、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7402a-115">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
4. <span data-ttu-id="7402a-116">リストからユーザーを追加する役割グループを選択し、[編集] [ \*\*\*\* ![編集] アイコン](media/O365_MDM_CreatePolicy_EditIcon.gif)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7402a-116">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
5. <span data-ttu-id="7402a-117">役割グループのプロパティページの [**メンバー**] で、 \*\*\*\*![[追加]](media/ITPro-EAC-AddIcon.gif)アイコンをクリックし、追加するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="7402a-117">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span> 
    
6. <span data-ttu-id="7402a-118">役割グループに追加するすべてのユーザーを選択したら、[ **\>追加**] をクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7402a-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>
    
7. <span data-ttu-id="7402a-119">**[保存]** をクリックして、役割グループに加えた変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="7402a-119">Click **Save** to save the changes to the role group.</span></span> 
    
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7402a-120">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="7402a-120">How do you know this worked?</span></span>

1. <span data-ttu-id="7402a-121">セキュリティ&amp; /コンプライアンスセンターで、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7402a-121">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
2. <span data-ttu-id="7402a-122">リストから、メンバーを表示する役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="7402a-122">From the list, select the role group to view the members.</span></span>
    
3. <span data-ttu-id="7402a-123">右側の役割グループの詳細では、役割グループのメンバーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7402a-123">On the right, in the role group details, you can view the members of the role group.</span></span>
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="7402a-124">PowerShell を使用して、セキュリティ&amp; /コンプライアンスセンターへのアクセス権を別のユーザーに付与する</span><span class="sxs-lookup"><span data-stu-id="7402a-124">Use PowerShell to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="7402a-125">[Office 365 Security & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="7402a-125">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="7402a-126">次の例で示すように、**Add-RoleGroupMember** コマンドを使用して、ユーザーを Organization Management の役割に追加できます。</span><span class="sxs-lookup"><span data-stu-id="7402a-126">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span> 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 <span data-ttu-id="7402a-127">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="7402a-127">**Parameters**</span></span>
  
- <span data-ttu-id="7402a-128">_-Identity_ は、メンバーを追加する役割グループです。</span><span class="sxs-lookup"><span data-stu-id="7402a-128">_-Identity_ is the role group to add a member to.</span></span> 
    
- <span data-ttu-id="7402a-129">_Member_は、役割グループに追加するメールボックス、ユニバーサルセキュリティグループ (USG)、またはコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="7402a-129">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="7402a-130">一度に 1 メンバーしか指定できません。</span><span class="sxs-lookup"><span data-stu-id="7402a-130">You can specify only one member at a time.</span></span> 
    
<span data-ttu-id="7402a-131">構文とパラメーターの詳細については、「 [add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7402a-131">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7402a-132">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="7402a-132">How do you know this worked?</span></span>

<span data-ttu-id="7402a-133">ユーザーにセキュリティ&amp;コンプライアンスセンターへのアクセス権が与えられたことを確認するには、次の例に示すように、 **add-rolegroupmember**コマンドレットを使用して組織の管理役割グループのメンバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="7402a-133">To verify that you've given users access to the Security &amp; Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span> 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

<span data-ttu-id="7402a-134">構文とパラメーターの詳細については、「 [add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7402a-134">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
  

