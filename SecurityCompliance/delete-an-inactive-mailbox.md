---
title: Office 365 で、非アクティブなメールボックスを削除します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: Office 365 の非アクティブなメールボックスの内容を保持するために不要になった場合は、保留リストを削除することによって、非アクティブなメールボックスを完全に削除できます。保留リストを削除した後には、非アクティブなメールボックスは削除用にマークされてし、それが処理された後は完全に削除します。
ms.openlocfilehash: a7284be650d7ec6c89a6fdc43d8614603d6f1e19
ms.sourcegitcommit: 82fd4c85b952819157fbb13175c7b2dbbdff510f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965254"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="ef184-104">Office 365 で、非アクティブなメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="ef184-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="ef184-p102">非アクティブなメールボックスは、彼または彼女が組織を離れた後に、以前の社員の電子メールを保持するために使用されます。非アクティブなメールボックスの内容を保存する必要がなくなった、保留リストを削除することによって、非アクティブなメールボックスを完全に削除できます。また、非アクティブなメールボックスに複数の保留リストを配置することが可能です。などの証拠保全し、埋め込みを保持する 1 つまたは複数、非アクティブなメールボックスを配置する可能性があります。Office 365 保持ポリシーさらに、(Office 365 のセキュリティで作成された&amp;コンプライアンス センター) 非アクティブなメールボックスに適用することがあります。削除する非アクティブなメールボックスからすべての保留リストと Office 365 の保持ポリシーを削除する必要が。保持し、保持ポリシーを削除した後非アクティブなメールボックスは削除用にマークし、それが処理された後は完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="ef184-p102">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization. When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. Additionally, an Office 365 retention policy (created in the Office 365 Security &amp; Compliance Center) might be applied to the inactive mailbox. You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it. After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ef184-p103">2017 年 7 月 1 日に終了する予定だった、メールボックスを非アクティブにするために新しいインプレース ホールドを作成できる期間を延長しました。しかし、今年の終わりごろまたは来年の初めごろには、新しいインプレース ホールドを Exchange Online 内で作成することはできなくなります。その時点で、非アクティブのメールボックスを作成するために使用できるのは、訴訟ホールドと Office 365 アイテム保持ポリシーだけになります。ただし、インプレース ホールドにある既存の非アクティブなメールボックスは引き続きサポートされます。また、引き続き非アクティブなメールボックスのインプレース ホールドを管理することができます。これには、インプレース ホールドの期間を変更すること、およびそのインプレース ホールドを削除することによって非アクティブなメールボックスを完全に削除することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ef184-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
<span data-ttu-id="ef184-117">保留リストが非アクティブなメールボックスから削除された結果の詳細については、「[詳細情報](delete-an-inactive-mailbox.md#moreinfo)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef184-117">See the [More information](delete-an-inactive-mailbox.md#moreinfo) section for a description of what happens after holds are removed from an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="ef184-118">開始する前に</span><span class="sxs-lookup"><span data-stu-id="ef184-118">Before you begin</span></span>

- <span data-ttu-id="ef184-p104">証拠保全を非アクティブなメールボックスから削除するのには Exchange のオンライン PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)を参照してください。非アクティブなメールボックスから、埋め込みの保持を削除するのには、Exchange オンライン PowerShell または、EAC を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef184-p104">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="ef184-p105">保留を解除し、非アクティブなメールボックスを削除する前に、非アクティブなメールボックスの内容を別のメールボックスにコピーできます。詳細については、 [Office 365 で、非アクティブなメールボックスの復元](restore-an-inactive-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef184-p105">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox. For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="ef184-p106">非アクティブなメールボックスから、保留中または Office 365 の保持ポリシーを削除すると、ソフト削除済みメールボックスの保存期間、メールボックスの有効期限が切れて、メールボックスを完全に削除されます。削除は元に戻せません。保留リストを削除する前にメールボックスの内容は必要がなくなったことを確認します。アクティブでないメールボックスを再アクティブ化する場合を回復することができます。詳細については、 [Office 365 で、非アクティブなメールボックスのリカバリ](recover-an-inactive-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef184-p106">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted. After it's deleted, it can't be recovered. Before you remove the hold, be sure that you no longer need the contents in the mailbox. If you want to re-activate an inactive mailbox, you can recover it. For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="ef184-130">非アクティブなメールボックスの詳細については、 [Office 365 でアクティブでないメールボックス](inactive-mailboxes-in-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef184-130">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="ef184-131">手順 1: 非アクティブなメールボックスに設定されているホールドを特定する</span><span class="sxs-lookup"><span data-stu-id="ef184-131">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="ef184-p107">前述のように、訴訟ホールド、インプレース ホールド、または Office 365 アイテム保持ポリシーが非アクティブなメールボックスに設定されていることがあります。最初の手順として、非アクティブなメールボックスのホールドを識別します。</span><span class="sxs-lookup"><span data-stu-id="ef184-p107">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox. The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="ef184-134">組織内のすべての非アクティブなメールボックスの保留リストの情報を表示するために、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ef184-134">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="ef184-p108">**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスが訴訟ホールドに設定されていることを示します。インプレース ホールドが非アクティブなメールボックスに設定されていると、保留リストの GUID が **InPlaceHolds** プロパティの値として表示されます。たとえば、2 つの非アクティブなメールボックスの次の結果は、1 つの訴訟ホールドが Ann Beebe に設定され、2 つのインプレース ホールドが Pilar Pinilla に設定されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="ef184-p108">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="ef184-p109">多くの場所を保持するが非アクティブなメールボックスに配置されている場合、埋め込み保持の Guid のすべてが表示されます。すべての埋め込みを保持の Guid を表示するのには、次のコマンドを実行することができます。`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="ef184-p109">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed. You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="ef184-140">手順 2:非アクティブなメールボックスから保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="ef184-140">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="ef184-p110">非アクティブなメールボックスにどの種類の保留リストが設定されているか (および複数の保留リストがあるかどうか) を特定したら、次の手順ではメールボックスの保留リストを削除します。前述のように、非アクティブなメールボックスを完全に削除するには、すべての保留リストを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef184-p110">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="ef184-143">訴訟ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="ef184-143">Remove a Litigation Hold</span></span>

<span data-ttu-id="ef184-p111">前述のように、非アクティブなメールボックスから訴訟ホールドを削除するには、Windows PowerShell を使用する必要があります。EAC は使用できません。次のコマンドを実行して、訴訟ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="ef184-p111">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="ef184-p112">非アクティブなメールボックスを特定するには、識別名または Exchange GUID 値を使用するのが最適です。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="ef184-p112">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="ef184-149">インプレース ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="ef184-149">Remove In-Place Holds</span></span>

 <span data-ttu-id="ef184-150">非アクティブなメールボックスからインプレース ホールドを削除する方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="ef184-150">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="ef184-151">**埋め込みを押しながらオブジェクトを削除**非アクティブなメールボックスを完全に削除するが、埋め込みの保持の唯一の元のメールボックスの場合は、埋め込みの保持オブジェクトだけで削除できます。</span><span class="sxs-lookup"><span data-stu-id="ef184-151">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ef184-p113">インプレース ホールド オブジェクトを削除する前に、保留リストを無効にする必要があります。保留リストを有効にしているインプレース ホールド オブジェクトを削除しようとすると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef184-p113">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="ef184-154">**インプレース ホールドのソース メールボックスとして非アクティブなメールボックスを削除する** インプレース ホールドの他のソース メールボックスを保持する場合は、ソース メールボックスのリストから非アクティブなメールボックスを削除して、インプレース ホールド オブジェクトを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="ef184-154">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="ef184-155">EAC を使用してインプレース ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="ef184-155">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="ef184-p114">削除するインプレース ホールドの名前が分かっている場合は、次の手順に進むことができます。そうでない場合は、次のコマンドを実行して、完全に削除する非アクティブなメールボックスに設定されているインプレース ホールドの名前を取得します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](delete-an-inactive-mailbox.md#step1) で取得したインプレース ホールドの GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef184-p114">If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="ef184-159">**コンプライアンス管理**には、EAC で\>**インプレース電子情報開示&amp;を保持**。</span><span class="sxs-lookup"><span data-stu-id="ef184-159">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="ef184-160">埋め込みの保留を削除する] を選択し、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="ef184-160">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="ef184-161">**、インプレース電子情報開示&amp;を保持**プロパティ ページで、**場所に保持**] をクリックして**で選択したメールボックスの検索クエリに一致する場所のコンテンツを保持する**] ボックスをオフにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef184-161">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="ef184-162">**埋め込み電子的証拠開示&amp;を保持**ページで、埋め込みの保持をもう一度選択し、[**削除**] をクリックし、![削除アイコン](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)。</span><span class="sxs-lookup"><span data-stu-id="ef184-162">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="ef184-163">警告が表示されたら、 **[はい]** をクリックして、インプレース保持を削除します。</span><span class="sxs-lookup"><span data-stu-id="ef184-163">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="ef184-164">Exchange Online PowerShell を使用してインプレース ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="ef184-164">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="ef184-p115">削除するインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](delete-an-inactive-mailbox.md#step1) で取得したインプレース保持の GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef184-p115">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="ef184-167">インプレース ホールドの保留リストを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ef184-167">Disable the hold on the In-Place Hold.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. <span data-ttu-id="ef184-168">インプレース ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="ef184-168">Delete the In-Place Hold.</span></span>
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="ef184-169">EAC を使用してインプレース ホールドから非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="ef184-169">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="ef184-p116">非アクティブなメールボックスに設定されたインプレース ホールドの名前が分かっている場合は、次の手順に進むことができます。そうでない場合は、次のコマンドを実行して、メールボックスに設定されたインプレース ホールドの名前を取得します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](delete-an-inactive-mailbox.md#step1) で取得したインプレース ホールドの GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef184-p116">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="ef184-173">**コンプライアンス管理**には、EAC で\>**インプレース電子情報開示&amp;を保持**。</span><span class="sxs-lookup"><span data-stu-id="ef184-173">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="ef184-174">非アクティブなメールボックスを配置する埋め込みの保留] を選択し、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="ef184-174">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="ef184-175">**、インプレース電子情報開示&amp;を保持**プロパティ] ページで、[**ソース**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef184-175">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="ef184-176">ソース メールボックスのリストで、削除する非アクティブなメールボックスの名前をクリックして、 **[削除]**![[削除] アイコン](media/adf01106-cc79-475c-8673-065371c1897b.gif)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef184-176">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="ef184-p117">**[保存]** をクリックして変更を保存します。操作が正常に完了したことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef184-p117">Click **Save** to save the change. A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="ef184-179">手順 1 から手順 6 を繰り返して、非アクティブなメールボックスに設定された他のインプレース保持を削除します。</span><span class="sxs-lookup"><span data-stu-id="ef184-179">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="ef184-180">Exchange Online PowerShell を使用してインプレース保持から非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="ef184-180">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="ef184-p118">インプレース ホールドに多数のソース メールボックスが含まれている場合、EAC の **[ソース]** ページに非アクティブなメールボックスがリストされないことがあります。インプレース ホールドを編集する場合、 **[ソース]** ページに最大 3,000 のメールボックスが表示されます。非アクティブなメールボックスが **[ソース]** ページにリストされない場合は、Exchange Online PowerShell を使用してインプレース ホールドから削除できます。</span><span class="sxs-lookup"><span data-stu-id="ef184-p118">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="ef184-p119">非アクティブなメールボックスに設定されたインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](delete-an-inactive-mailbox.md#step1) で取得したインプレース保持の GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef184-p119">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="ef184-186">非アクティブなメールボックスがインプレース ホールドのソース メールボックスとしてリストされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef184-186">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
```
  $InPlaceHold.Sources
```

   <span data-ttu-id="ef184-p120">**注:** 埋め込み保持の*ソース*のプロパティは、ユーザーの*LegacyExchangeDN*プロパティの移行元のメールボックスを識別します。このプロパティは、アクティブでないメールボックスを一意に識別ため、埋め込みの保持から*のソース*プロパティを使用して防ぐ間違ったメールボックスを削除します。これは、同じエイリアスまたは SMTP アドレスに 2 つのメールボックスがある場合は、問題を回避するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ef184-p120">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox. This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="ef184-p121">変数のソース メールボックスのリストから非アクティブなメールボックスを削除します。前の手順のコマンドで返された非アクティブなメールボックスの **LegacyExchangeDN** を必ず使用してください。</span><span class="sxs-lookup"><span data-stu-id="ef184-p121">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. <span data-ttu-id="ef184-192">変数のソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef184-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
```
  $InPlaceHold.Sources
```

5. <span data-ttu-id="ef184-193">非アクティブなメールボックスを含まないソース メールボックスの更新されたリストで、インプレース ホールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="ef184-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. <span data-ttu-id="ef184-194">インプレース ホールドのソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef184-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a><span data-ttu-id="ef184-195">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ef184-195">More information</span></span>

- <span data-ttu-id="ef184-p122">**非アクティブなメールボックスは、回復可能な削除によって削除されたメールボックスの一種です。** Exchange Onlineで、回復可能な削除によって削除されたメールボックスは、メールボックスが削除されてはいるものの、特定の保持期間内であれば回復することができます。Exchange Online で回復可能な削除によって削除されたメールボックスの保存期間は 30 日です。つまり、回復可能な削除によって削除されてから 30 日以内なら、メールボックスを復元できます。30 日が経過すると、回復可能な削除によって削除されたメールボックスは完全削除のマークが付けられ、回復できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ef184-p122">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="ef184-p123">**非アクティブなメールボックスに対する保留リストを削除した後はどうなりますか。** 非アクティブなメールボックスは、他の回復可能な削除によって削除されたメールボックスと同様に扱われ、回復可能な削除によって削除されたメールボックスの保持期間である 30 日が経過した後に完全削除のマークが付けられます。この保存期間は、メールボックスが最初に非アクティブになった日から始まります。この日付は、回復可能な削除によって削除された日付と呼ばれ、対応する Office 365 ユーザー アカウントが削除された日、またはExchange Online メールボックスが **Remove-Mailbox** コマンドレットを使用して削除された日になります。回復可能な削除によって削除された日は、保留リストを削除した日ではありません。</span><span class="sxs-lookup"><span data-stu-id="ef184-p123">**What happens after you remove the hold on an inactive mailbox?** The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires. This retention period starts on the date when the mailbox was first made inactive. This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet. The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="ef184-p124">**ホールドを解除した直後に、非アクティブなメールボックスは完全に削除されますか。** 非アクティブなメールボックスが回復可能な削除によって削除された日付が 30 日より前であっても、ホールドを解除するとすぐにメールボックスが完全に削除されるということはありません。メールボックスに完全に削除するようマークが付けられ、次に処理されるときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="ef184-p124">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="ef184-p125">**ソフト削除されたメールボックスの保存期間が非アクティブなメールボックスに影響しますか?** ソフト削除、非アクティブなメールボックスの日付が、保留が削除された日付より前に 30 日以上の場合は、メールボックスが完全に削除のマークされます。ですが、アクティブでないメールボックスには、過去 30 日以内のソフト削除された日付、保留を解除する場合は、ソフト削除済みメールボックスの保存期間の期限が切れるまで、メールボックスを回復できます。詳細については、[削除するかオンライン Exchange ユーザーのメールボックスの復元](https://go.microsoft.com/fwlink/?linkid=856835)を参照してください。ソフト削除されたメールボックスの保存期間を過ぎると、非アクティブなメールボックスを回復する手順を実行します。詳細については、 [Office 365 で、非アクティブなメールボックスのリカバリ](recover-an-inactive-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef184-p125">**How does the soft-deleted mailbox retention period affect inactive mailboxes?** If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion. But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires. For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox. For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="ef184-p126">**表示するには、非アクティブなメールボックスに関する情報の保持を削除した後ですか?** 保留リストが削除され、非アクティブなメールボックスは、ソフト削除されたメールボックスに戻されますが後は、、 **Get**コマンドレットの*InactiveMailboxOnly*パラメーターを使用して返されません。**Get メールボックス SoftDeletedMailbox**コマンドを使用してメールボックスに関する情報を表示することができます。例えば：</span><span class="sxs-lookup"><span data-stu-id="ef184-p126">**How do you display information about an inactive mailbox after the hold is removed?** After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet. But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command. For example:</span></span> 
    
```
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
```
  
<span data-ttu-id="ef184-p127">上の例では、 *WhenSoftDeleted*プロパティは、ソフト削除された日付であるこの例では 2014 年 10 月 30 日を識別します。このソフト削除されたメールボックスが、以前に、保留中の削除対象の非アクティブなメールボックスであった場合は完全に削除されてから 30 日後、 *WhenSoftDeleted*プロパティの値があります。この例では、2014 年 11 月 30 日後、メールボックスを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="ef184-p127">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014. If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property. In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

