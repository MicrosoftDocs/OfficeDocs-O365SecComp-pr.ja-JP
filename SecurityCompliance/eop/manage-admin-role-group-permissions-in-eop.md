---
title: EOP で管理役割グループのアクセス許可を管理する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 管理者は、exchange Online Protection の Exchange 管理センター (EAC) でアクセス許可を割り当てる、または削除する方法を学習できます。
ms.openlocfilehash: 7bd1a6959dd03a118608dfe45faa253fd56539d4
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676727"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="889a7-103">EOP で管理役割グループのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="889a7-103">Manage admin role group permissions in EOP</span></span>
  
<span data-ttu-id="889a7-p101">Microsoft Exchange Online Protection (EOP) では、Exchange 管理センター (EAC) を使用して、特定の管理タスクを実行するアクセス許可を割り当てるために、ユーザーを役割グループのメンバーにすることができます。また、EAC を使用して、ユーザーを役割グループから削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="889a7-p101">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="889a7-106">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="889a7-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="889a7-107">予想所要時間 : 5 ～ 10 分</span><span class="sxs-lookup"><span data-stu-id="889a7-107">Estimated time to complete: 5-10 minutes</span></span>

- <span data-ttu-id="889a7-108">Exchange 管理センターを開くには、「exchange [Online Protection の exchange 管理センター](../exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="889a7-108">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="889a7-p102">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「ユーザー、連絡先、および役割グループ」。</span><span class="sxs-lookup"><span data-stu-id="889a7-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="889a7-111">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="889a7-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="889a7-112">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="889a7-112">Having problems?</span></span> <span data-ttu-id="889a7-113">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。</span><span class="sxs-lookup"><span data-stu-id="889a7-113">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>
  
## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="889a7-114">EAC を使用してメンバーを管理役割グループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="889a7-114">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="889a7-115">EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、ユーザーを追加する役割グループをクリックしてから、[ \*\*\*\* ![編集] 編集](../media/ITPro-EAC-EditIcon.gif)アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="889a7-115">In the EAC, go to **Permissions** \> **Admin roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="889a7-116">[メンバー] で\*\*\*\* ![、[追加](../media/ITPro-EAC-AddIcon.gif)] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="889a7-116">Under Members, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="889a7-117">[メンバーの選択] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="889a7-117">The Select Members window will appear.</span></span>

3. <span data-ttu-id="889a7-118">追加するユーザーを検索するか、または一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="889a7-118">Search for the user or users that you wish to add, or select them from the list.</span></span>

4. <span data-ttu-id="889a7-p105">追加するユーザーを選択したら、 **[追加]**、 **[OK]** の順にクリックします。[メンバーの選択] ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="889a7-p105">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>

5. <span data-ttu-id="889a7-p106">ユーザーが **[メンバー]** ウィンドウに追加された状態になります。 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889a7-p106">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="889a7-123">役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="889a7-123">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="889a7-124">EAC を使用して管理役割グループからメンバーを削除する</span><span class="sxs-lookup"><span data-stu-id="889a7-124">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="889a7-125">EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、ユーザーを削除する役割グループをクリックしてから、[ \*\*\*\* ![編集アイコン](../media/ITPro-EAC-EditIcon.gif)の編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889a7-125">In the EAC, go to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="889a7-126">[メンバー] で削除するユーザーを選択し、[削除] [ \*\*\*\* ![削除] アイコン](../media/ITPro-EAC-RemoveIcon.gif)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889a7-126">Under Members, select the user or users that you want to remove and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="889a7-p107">**[保存]** をクリックして役割グループに対する変更内容を保存し、 **[管理役割]** ページに戻ります。ユーザーが管理者役割グループから正常に削除されているかは、選択した役割グループの詳細ウィンドウの [メンバー] に、該当するメンバーが表示されていないことで確認します。</span><span class="sxs-lookup"><span data-stu-id="889a7-p107">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span>

   > [!NOTE]
   > <span data-ttu-id="889a7-129">役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="889a7-129">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="889a7-130">詳細情報</span><span class="sxs-lookup"><span data-stu-id="889a7-130">For more information</span></span>

[<span data-ttu-id="889a7-131">EOP の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="889a7-131">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
