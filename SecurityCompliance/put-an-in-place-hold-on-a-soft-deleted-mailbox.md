---
title: Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 削除済みメールボックス (回復可能) のインプレース ホールドを非アクティブにして、その内容を保存する方法について説明します。Microsoft 電子情報開示ツールを使用して、非アクティブなメールボックスを検索できるようになります。
ms.openlocfilehash: 70feb265e95741406dbf170c6be70bd83b2ec081
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223526"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="2f4de-104">Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する</span><span class="sxs-lookup"><span data-stu-id="2f4de-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="2f4de-p102">削除済みメールボックス (回復可能) のインプレース ホールドを非アクティブにして、その内容を保存する方法について説明します。Microsoft 電子情報開示ツールを使用して、非アクティブなメールボックスを検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2f4de-p102">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f4de-p103">exchange online (Office 365 および exchange online スタンドアロンプラン) に新しいインプレースホールドを作成する期限を延期しました。しかし今年度以降では、Exchange Online に新しいインプレースホールドを作成することはできません。インプレース保持を使用する代わりに、Office 365 セキュリティ&amp;コンプライアンスセンターで[電子情報開示ケース](https://go.microsoft.com/fwlink/?linkid=780738)または[アイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=827811)を使用することができます。新しいインプレースホールドを廃止した後でも、既存のインプレース保持を変更したり、exchange Server 2013 に新しいインプレースホールドを作成したり、exchange ハイブリッド展開を引き続きサポートすることができます。また、メールボックスを訴訟ホールドの対象にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2f4de-p103">We've postponed the deadline for creating new In-Place Holds in Exchange Online (in Office 365 and Exchange Online standalone plans). But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Office 365 Security &amp; Compliance Center. After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported. And, you'll still be able to place mailboxes on Litigation Hold.</span></span> 
  
<span data-ttu-id="2f4de-p104">ユーザーが組織を離れていて、対応するユーザーアカウントとメールボックスが削除されている場合があります。その後、メールボックスに保持する必要がある情報があることを認識します。できること削除済みメールボックスの保持期間が期限切れになっていない場合は、削除済みメールボックス (回復可能な削除によって削除されたメールボックスと呼ばれる) にインプレースホールドを設定して、非アクティブなメールボックスにします。*非アクティブなメールボックス*は、退職後に元従業員の電子メールを保持するために使用されます。非アクティブなメールボックスのコンテンツは、削除済みメールボックスが非アクティブになったときに、削除されたメールボックスに配置されたインプレースホールドの期間中保持されます。メールボックスが非アクティブになった後は、Exchange online のインプレース電子情報開示、Office 365 セキュリティ&amp;コンプライアンスセンターのコンテンツ検索、または SharePoint Online の電子情報開示センターを使用して、メールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="2f4de-p104">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Office 365 Security &amp; Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2f4de-p105">Exchange Online では、削除済みメールボックス (回復可能) は、メールボックスが削除されていても、特定の保存期間内であれば回復することができます。Exchange Online の削除済みメールボックス (回復可能) の保存期間は 30 日です。つまり、削除してから 30 日以内なら、メールボックスは復元できます (または、非アクティブなメールボックスにできます)。30 日が経過すると、削除済みメールボックスには完全削除のマークが付けられ、回復または非アクティブにすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="2f4de-p105">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="2f4de-123">はじめに</span><span class="sxs-lookup"><span data-stu-id="2f4de-123">Before you begin</span></span>

- <span data-ttu-id="2f4de-p106">削除済みメールボックス (回復可能) にインプレース ホールドを設定するには、Windows PowerShell で **New-MailboxSearch** コマンドレットを使う必要があります。Exchange 管理センター (EAC) または SharePoint Online の電子情報開示センターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f4de-p106">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 
    
- <span data-ttu-id="2f4de-126">Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f4de-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="2f4de-127">組織内の削除済みメールボックス (回復可能) の識別情報を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f4de-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="2f4de-128">非アクティブなメールボックスの詳細については、「 [Office 365 の非アクティブなメールボックスの概要](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f4de-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="2f4de-129">削除済みメールボックス (回復可能) にインプレース ホールドを適用し、非アクティブなメールボックスにする</span><span class="sxs-lookup"><span data-stu-id="2f4de-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="2f4de-p107">**New-MailboxSearch** コマンドレットを使用して、削除済みメールボックス (回復可能) を非アクティブなメールボックスにします。詳細については、「 [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f4de-p107">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="2f4de-132">削除済みメールボックス (回復可能) のプロパティを含む変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="2f4de-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span> 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="2f4de-p108">上記のコマンドでは、 **DistinguishedName** または **ExchangeGuid** プロパティの値を使用して削除済みメールボックス (回復可能) を識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと削除済みメールボックス (回復可能) でプライマリ SMTP アドレスが等しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f4de-p108">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="2f4de-p109">インプレース ホールドを作成し、削除済みメールボックス (回復可能) に適用します。この例では、保存期間が指定されていません。この場合、アイテムは無制限に、または非アクティブなメールボックスからホールドが解除されるまで保存されます。</span><span class="sxs-lookup"><span data-stu-id="2f4de-p109">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   <span data-ttu-id="2f4de-p110">インプレース ホールドを作成するときに、保存期間を指定することもできます。この例では、非アクティブなメールボックスのアイテムを約 7 年間保持します。</span><span class="sxs-lookup"><span data-stu-id="2f4de-p110">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="2f4de-140">しばらくしてから、次のコマンドのいずれかを実行して削除済みメールボックス (回復可能) が、非アクティブなメールボックスになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f4de-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="2f4de-141">または</span><span class="sxs-lookup"><span data-stu-id="2f4de-141">Or</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="2f4de-142">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2f4de-142">More information</span></span>

<span data-ttu-id="2f4de-p111">削除済みメールボックス (回復可能) を非アクティブなメールボックスにしてから、いろいろな方法でメールボックスを管理することができます。詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f4de-p111">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="2f4de-145">非アクティブなメールボックスの保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="2f4de-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [<span data-ttu-id="2f4de-146">非アクティブなメールボックスを回復する</span><span class="sxs-lookup"><span data-stu-id="2f4de-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)
    
- [<span data-ttu-id="2f4de-147">非アクティブなメールボックスを復元する</span><span class="sxs-lookup"><span data-stu-id="2f4de-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)
    
- <span data-ttu-id="2f4de-148">[非アクティブなメールボックスを削除する](delete-an-inactive-mailbox.md)(保留リストを削除する)</span><span class="sxs-lookup"><span data-stu-id="2f4de-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
