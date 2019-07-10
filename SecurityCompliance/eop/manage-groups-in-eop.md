---
title: EOP でグループを管理する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: Exchange Online Protection (EOP) を使用すれば、Exchange 組織のメールが有効なグループを作成できます。 また、EOP を使用してメンバーシップ、電子メール アドレス、グループのその他の側面を指定するグループのプロパティを定義または更新することもできます。
ms.openlocfilehash: 2763ca35456bb40b5b11e38eb2e7497934115d5f
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599643"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="f22f4-104">EOP でグループを管理する</span><span class="sxs-lookup"><span data-stu-id="f22f4-104">Manage groups in EOP</span></span>

 <span data-ttu-id="f22f4-p102">Exchange Online Protection (EOP) を使用すれば、Exchange 組織のメールが有効なグループを作成できます。また、EOP を使用してメンバーシップ、電子メール アドレス、グループのその他の側面を指定するグループのプロパティを定義または更新することもできます。必要に応じて配布グループとセキュリティ グループを作成できます。これらのグループは、Exchange 管理センター (EAC) を使用するか、リモートの Windows PowerShell を介して作成できます。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p102">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span> 
  
## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="f22f4-109">メールが有効なグループの種類</span><span class="sxs-lookup"><span data-stu-id="f22f4-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="f22f4-110">Exchange 組織では、2 種類のグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f22f4-110">You can create two types of groups for your Exchange organization:</span></span>
  
- <span data-ttu-id="f22f4-p103">[EAC でグループを作成する](manage-groups-in-eop.md) ( 配布グループとも言う) は、共通の関心領域に関する電子メールを送受信する必要のあるチームやその他の専門グループなどの電子メール ユーザーの集まりです。配布グループは電子メール メッセージの配布専用です。EOP では、配布グループは、セキュリティに関連するかどうかにかかわらず、すべてのメールが有効なグループを意味します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p103">[Create a group in the EAC](manage-groups-in-eop.md) (also known as distribution groups) are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest. Distribution groups are exclusively for distributing email messages. In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>
    
- <span data-ttu-id="f22f4-p104">[EAC でグループを編集または削除する](manage-groups-in-eop.md) ( セキュリティ グループとも言う) は、管理者役割のアクセス許可が必要な電子メール ユーザーの集まりです。たとえば、特定のユーザー グループに管理者役割アクセス許可を付与して、スパム対策設定とマルウェア対策設定を構成できるようにする場合があります。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p104">[Edit or remove a group in the EAC](manage-groups-in-eop.md) (also known as security groups) are collections of email users who need access permissions for Admin roles. For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f22f4-p105">既定では、メールが有効なすべての新しいセキュリティ グループで、すべての送信者を認証する必要があります。これにより、外部の送信者はメールが有効なセキュリティ グループに対してメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p105">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="f22f4-118">開始する前に</span><span class="sxs-lookup"><span data-stu-id="f22f4-118">Before you begin</span></span>

- <span data-ttu-id="f22f4-p106">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「配布グループとセキュリティ グループ」。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="f22f4-121">リモートの PowerShell コマンドレットを使用してグループの作成および管理を行う際、調整が発生することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f22f4-121">Be aware that when creating and managing groups by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="f22f4-122">このコマンドレットはバッチ処理方法を使用しており、コマンドレットの結果が表示されるまで数分の送信遅延が生じます。</span><span class="sxs-lookup"><span data-stu-id="f22f4-122">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="f22f4-123">Windows PowerShell を使用して Exchange Online Protection に接続する方法については、「[リモート PowerShell を使用して Exchange Online Protection に接続する](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22f4-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
    
- <span data-ttu-id="f22f4-124">このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22f4-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="f22f4-p107">問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p107">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="f22f4-128">EAC でグループを作成する</span><span class="sxs-lookup"><span data-stu-id="f22f4-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="f22f4-129">Exchange 管理センター (EAC) で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-129">In the Exchange admin center (EAC), go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="f22f4-p108">**[新規]**![[追加] アイコン](../media/ITPro-EAC-AddIcon.gif) をクリックしてから、必要に応じて、 **[配布グループ]** または **[セキュリティ グループ]** をクリックします。違いについては、「 [メールが有効なグループの種類](manage-groups-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p108">Click **New**![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs. See [Types of mail-enabled groups](manage-groups-in-eop.md) for the distinction.</span></span> 
    
3. <span data-ttu-id="f22f4-132">**[配布グループの新規作成]** ページまたは **[新しいセキュリティ グループ]** ページで、次のフィールドにデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-132">On the **New distribution group** or **New security group** page, complete the following fields:</span></span> 
    
  - <span data-ttu-id="f22f4-p109">**[表示名]** 組織に固有で、EOP ユーザーにとって意味のある表示名を入力します。表示名は必須です。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p109">**Display name** Type a display name that's unique to your organization and meaningful to EOP users. The display name is required.</span></span> 
    
  - <span data-ttu-id="f22f4-p110">**[エイリアス]** 組織に固有で、最大 64 文字のグループのエイリアスを入力します。EOP ユーザーが電子メール メッセージの宛先行にエイリアスを入力すると、グループの表示名に解読されます。エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが追加されます。エイリアスは必須です。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p110">**Alias** Type a group alias of up to 64 characters that's unique to your organization. EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name. If you change the alias, the primary SMTP address for the group also changes and will contain the new alias. The alias is required.</span></span> 
    
  - <span data-ttu-id="f22f4-139">**[説明]** グループの目的がわかるようにグループの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-139">**Description** Type a description of the group so that people will know the purpose of the group.</span></span> 
    
  - <span data-ttu-id="f22f4-p111">**[所有者]** 既定では、グループを作成したユーザーがその所有者です。所有者を追加するには、 **[追加]**![[追加] アイコン](../media/ITPro-EAC-AddIcon.gif) を選択します。グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p111">**Owners** By default, the person who creates the group is the owner. You can add an owner by choosing **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif). All groups must have at least one owner.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f22f4-143">所有者はグループのメンバーである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f22f4-143">Owners don't have to be members of the group.</span></span> 
  
  - <span data-ttu-id="f22f4-p112">**[メンバー]** このセクションは、グループ メンバーを追加したり、ユーザーがグループに参加または脱退するときに承認が必要かどうかを指定したりするために使用します。グループにメンバーを追加するには、 **[追加]**![[追加] アイコン](../media/ITPro-EAC-AddIcon.gif) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p112">**Members** Use this section to add group members and to specify whether approval is required for people to join or leave the group. To add members to the group, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="f22f4-146">**[OK]** をクリックして元のページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="f22f4-146">Click **OK** to return to the original page.</span></span> 
    
5. <span data-ttu-id="f22f4-p113">完了したら、 **[保存]** をクリックしてグループを作成します。新しいグループがグループの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p113">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span> 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="f22f4-149">EAC でグループを編集または削除する</span><span class="sxs-lookup"><span data-stu-id="f22f4-149">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="f22f4-150">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-150">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="f22f4-151">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-151">Do one of the following:</span></span>
    
  - <span data-ttu-id="f22f4-152">グループを編集するには、グループの一覧で、表示または変更する配布グループまたはセキュリティグループをクリックし、[ \*\*\*\* ![編集] 編集](../media/ITPro-EAC-EditIcon.gif)アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f22f4-152">To edit a group: In the list of groups, click the distribution or security group that you want to view or change, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="f22f4-153">必要に応じて、全般設定を更新したり、グループ所有者を追加または削除したり、グループメンバーを追加または削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="f22f4-153">You can update general settings, add or remove group owners, and add or remove group members, as needed.</span></span>
    
  - <span data-ttu-id="f22f4-154">グループを削除するには、次の手順を実行します。グループを選択して、 **[削除]**![[削除] アイコン](../media/ITPro-EAC-RemoveIcon.gif) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f22f4-154">To remove a group: Select the group and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>
    
3. <span data-ttu-id="f22f4-155">変更が完了したら、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f22f4-155">When you're finished making your changes, click **Save**.</span></span>
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="f22f4-156">リモートの Windows PowerShell を使用してグループを作成、編集、または削除する</span><span class="sxs-lookup"><span data-stu-id="f22f4-156">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="f22f4-p115">このセクションでは、リモートの Windows PowerShell を使用してグループを作成し、そのプロパティを変更する方法について説明します。また、既存のグループを削除する方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p115">This section provides information about creating groups and changing their properties by using remote Windows PowerShell. It also shows how to remove an existing group.</span></span> 
  
 <span data-ttu-id="f22f4-159">**リモートの Windows PowerShell を使用してグループを作成するには**</span><span class="sxs-lookup"><span data-stu-id="f22f4-159">**To create a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="f22f4-p116">この例では、コマンドレット [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) を使用して、エイリアスが「itadmin」、名前が「IT Administrators」の配布グループを作成します。また、ユーザーをグループのメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p116">This example uses the [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span> 
  
```Powershell
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

<span data-ttu-id="f22f4-162">配布グループではなくセキュリティ グループを作成するには、代わりに  `-Type "Security"` を指定します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-162">To create a security group instead of a distribution group, specify  `-Type "Security"` instead.</span></span> 
  
<span data-ttu-id="f22f4-163">正常に IT Administrators グループを作成したことを確認するには、コマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) を実行して新しいグループの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-163">To verify that you've successfully created the IT Administrators group, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to display information about the new group:</span></span> 
  
```Powershell
Get-Recipient "IT Administrators" | Format-List

```

<span data-ttu-id="f22f4-164">グループ内のメンバーの一覧を取得するには、次のようにコマンドレット [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) を実行します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-164">To get a list of members in the group, run the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-DistributionGroupMember "IT Administrators"

```

<span data-ttu-id="f22f4-165">すべてのグループの完全な一覧を取得するには、次のように [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-165">To get a full list of all your groups, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 <span data-ttu-id="f22f4-166">**リモートの Windows PowerShell を使用してグループのプロパティを変更するには**</span><span class="sxs-lookup"><span data-stu-id="f22f4-166">**To change the properties of a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="f22f4-p117">コマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) および [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) を使用して、グループのプロパティを表示し、変更します。EAC ではなくリモートの PowerShell を使用する利点は、複数のグループのプロパティを変更できることです。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p117">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlets to view and change properties for groups. An advantage of using remote PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span> 
  
<span data-ttu-id="f22f4-169">リモートの Windows PowerShell を使用してグループのプロパティを変更する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-169">Here are some examples of using remote Windows PowerShell to change group properties.</span></span>
  
<span data-ttu-id="f22f4-170">この例では、コマンドレット [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) を使用して、シアトルの従業員グループのプライマリ SMTP アドレス (返信アドレスともいう) を sea.employees@contoso.com に変更します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-170">This example uses the [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet to change the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span> 
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

<span data-ttu-id="f22f4-p118">グループのプロパティが正常に変更されたことを確認するには、コマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) を使用して変更を確認します。リモートの PowerShell を使用する利点の 1 つは、複数のグループの複数のプロパティを参照できる点です。前にプライマリ SMTP アドレス グループが変更された例で、次のコマンドを実行して新しい値を確認します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p118">To verify that you've successfully changed the properties for a group, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. One advantage of using remote PowerShell is that you can view multiple properties for multiple groups. In the previous example where the primary SMTP address group was changed, run the following command to verify the new value:</span></span> 
  
```Powershell
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

<span data-ttu-id="f22f4-p119">この例では、コマンドレット [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) を使用して、シアトルの従業員グループの全メンバーを更新します。全メンバーをコンマを使用して区切ります。</span><span class="sxs-lookup"><span data-stu-id="f22f4-p119">This example uses the [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) cmdlet to update all the members of the Seattle Employees group. Use a comma to separate all members.</span></span> 
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

<span data-ttu-id="f22f4-176">シアトルの従業員グループの全メンバーの一覧を取得するには、次のようにコマンドレット [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-176">To get the list of all the members in the group Seattle Employees, use the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"

```

 <span data-ttu-id="f22f4-177">**リモートの Windows PowerShell を使用してグループを削除するには**</span><span class="sxs-lookup"><span data-stu-id="f22f4-177">**To remove a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="f22f4-178">この例では、コマンドレット [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) を使用して、IT Administrators という名前の配布グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-178">This example uses the [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) cmdlet to remove a distribution group named IT Administrators.</span></span> 
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

<span data-ttu-id="f22f4-179">グループが削除されたことを確認するには、次のようにコマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) を実行し、グループ (この場合は「IT Administrators」) が削除されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f22f4-179">To verify that the group was removed, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows, and confirm that the group (in this case "It Administrators") was deleted.</span></span> 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


