---
title: ユーザーに Office 365 セキュリティ センターとコンプライアンス センターへのアクセス権を付与する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
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
description: ユーザーがセキュリティまたはコンプライアンス機能を管理する前に、Office 365 セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。
ms.openlocfilehash: 7963a8c3db64e83566960abe9298b9a2d636ae53
ms.sourcegitcommit: 6302a43d947a908dd10a8e40550b806f491692fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2019
ms.locfileid: "35645122"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a><span data-ttu-id="e7188-103">ユーザーに Office 365 セキュリティ センターとコンプライアンス センターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="e7188-103">Give users access to the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="e7188-104">ユーザーがセキュリティまたはコンプライアンス機能を管理する前に、Office 365 セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7188-104">Users need to be assigned permissions in the Office 365 Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="e7188-105">セキュリティ & コンプライアンスセンターで、Office 365 グローバル管理者または組織の組織の管理役割グループのメンバーとして、これらのアクセス許可をユーザーに与えることができます。</span><span class="sxs-lookup"><span data-stu-id="e7188-105">As an Office 365 global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="e7188-106">ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。</span><span class="sxs-lookup"><span data-stu-id="e7188-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="e7188-107">セキュリティ & コンプライアンスセンターでユーザーに付与できるさまざまなアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7188-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e7188-108">事前に必要な知識</span><span class="sxs-lookup"><span data-stu-id="e7188-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e7188-109">この記事に記載されている手順を完了するには、Office 365 グローバル管理者であるか、またはセキュリティ & コンプライアンスセンターの組織の組織の管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7188-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="e7188-110">セキュリティ & コンプライアンスセンターの役割グループには、Exchange Online の役割グループと同じような名前が付いている場合がありますが、これらは同じではありません。</span><span class="sxs-lookup"><span data-stu-id="e7188-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="e7188-111">役割グループのメンバーシップは、Exchange Online とセキュリティ & コンプライアンスセンターとの間で共有されません。</span><span class="sxs-lookup"><span data-stu-id="e7188-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="e7188-112">(AOBO) 権限を持つ代理アクセス許可 (DAP) パートナーは、セキュリティ & コンプライアンスセンターにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="e7188-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="e7188-113">Office 365 管理センターを使用して、別のユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="e7188-113">Use the Office 365 admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="e7188-114">[Office 365 にサインインし、管理センターに移動し](https://go.microsoft.com/fwlink/p/?LinkId=525275)ます。</span><span class="sxs-lookup"><span data-stu-id="e7188-114">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>

2. <span data-ttu-id="e7188-115">Office 365 管理センターで、**管理センター**を開き、[**セキュリティ & コンプライアンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7188-115">In the Office 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="e7188-116">[セキュリティ & コンプライアンスセンター] で、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7188-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="e7188-117">リストからユーザーを追加する役割グループを選択し、[編集] [ \*\*\*\* ![編集] アイコン](media/O365-MDM-CreatePolicy-EditIcon.gif)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7188-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="e7188-118">役割グループのプロパティページの [**メンバー**] で、 \*\*\*\*![[追加]](media/ITPro-EAC-AddIcon.gif)アイコンをクリックし、追加するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7188-118">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="e7188-119">役割グループに追加するすべてのユーザーを選択したら、[ **\>追加**] をクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7188-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="e7188-120">**[保存]** をクリックして、役割グループに加えた変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="e7188-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e7188-121">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="e7188-121">How do you know this worked?</span></span>

1. <span data-ttu-id="e7188-122">[セキュリティ & コンプライアンスセンター] で、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7188-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="e7188-123">リストから、メンバーを表示する役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7188-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="e7188-124">右側の役割グループの詳細では、役割グループのメンバーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e7188-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="e7188-125">PowerShell を使用して、別のユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="e7188-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="e7188-126">[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="e7188-126">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="e7188-127">次の例で示すように、**Add-RoleGroupMember** コマンドを使用して、ユーザーを Organization Management の役割に追加できます。</span><span class="sxs-lookup"><span data-stu-id="e7188-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="e7188-128">**パラメーター**:</span><span class="sxs-lookup"><span data-stu-id="e7188-128">**Parameters**:</span></span>
  
   - <span data-ttu-id="e7188-129">_Identity_は、メンバーを追加する役割グループです。</span><span class="sxs-lookup"><span data-stu-id="e7188-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="e7188-130">_Member_は、役割グループに追加するメールボックス、ユニバーサルセキュリティグループ (USG)、またはコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="e7188-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="e7188-131">一度に 1 メンバーしか指定できません。</span><span class="sxs-lookup"><span data-stu-id="e7188-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="e7188-132">構文とパラメーターの詳細については、「 [add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7188-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e7188-133">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="e7188-133">How do you know this worked?</span></span>

<span data-ttu-id="e7188-134">ユーザーにセキュリティ & コンプライアンスセンターへのアクセス権が与えられたことを確認するには、次の例に示すように、 **add-rolegroupmember**コマンドレットを使用して組織の管理役割グループのメンバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="e7188-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>
  
```
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="e7188-135">構文とパラメーターの詳細については、「 [add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7188-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
