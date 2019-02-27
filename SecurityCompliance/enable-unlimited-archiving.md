---
title: Office 365 で無制限のアーカイブを有効にする-管理者向けヘルプ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: '管理者向け: Office 365 で自動拡張アーカイブを有効にする方法について説明します。これにより、ユーザーに Exchange Online メールボックスのための無制限のストレージが提供されます。自動拡張アーカイブは、組織全体に対して、または特定のユーザーに対してのみ有効にすることができます。'
ms.openlocfilehash: 96e9fdd4b645df9e52cf9e11c3a43a80ef029ffa
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296030"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a><span data-ttu-id="f647e-104">Office 365 で無制限のアーカイブを有効にする-管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="f647e-104">Enable unlimited archiving in Office 365 - Admin Help</span></span>

<span data-ttu-id="f647e-p102">Office 365 の Exchange Online 自動拡張アーカイブ機能を使用して、アーカイブメールボックスの無制限の記憶域スペースを有効にすることができます。自動拡張アーカイブが有効になっている場合は、記憶域の制限に近づいたときに、ユーザーのアーカイブメールボックスに追加の記憶域が自動的に追加されます。その結果、メールボックスの格納容量は無制限になります。自動拡張アーカイブは、組織内のすべてのユーザーに対して、または特定のユーザーに対してのみ有効にすることができます。自動拡張アーカイブの詳細については、「 [Office 365 の無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f647e-p102">You can use the Exchange Online auto-expanding archiving feature in Office 365 to enable unlimited storage space for archive mailboxes. When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit. The result is unlimited mailbox storage capacity. You can turn on auto-expanding archiving for everyone in your organization or just for specific users. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f647e-110">はじめに</span><span class="sxs-lookup"><span data-stu-id="f647e-110">Before you begin</span></span>

- <span data-ttu-id="f647e-p103">組織全体または特定のユーザーに対して自動拡張アーカイブを有効にするには、Office 365 組織のグローバル管理者、または Exchange Online 組織の organization Management 役割グループのメンバーである必要があります。または、特定のユーザーに対して自動拡張アーカイブを有効にするために、メール受信者の役割が割り当てられている役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f647e-p103">You have to be a global administrator in your Office 365 organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users. Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>
    
- <span data-ttu-id="f647e-p104">自動拡張アーカイブを有効にするには、ユーザーのアーカイブメールボックスを有効にする必要があります。アーカイブメールボックスを有効にするには、ユーザーに Exchange Online プラン2ライセンスが割り当てられている必要があります。ユーザーに exchange online プラン1ライセンスが割り当てられている場合は、アーカイブメールボックスを有効にするために別の exchange online アーカイブライセンスを割り当てる必要があります。「 [Office 365 セキュリティ&amp;コンプライアンスセンターでアーカイブメールボックスを有効にする](enable-archive-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f647e-p104">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving. A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox. If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox. See [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md).</span></span>
    
- <span data-ttu-id="f647e-p105">PowerShell を使用してアーカイブメールボックスを有効にすることもできます。組織内のすべてのユーザーに対してアーカイブメールボックスを有効にするために使用できる PowerShell コマンドの例については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f647e-p105">You can also use PowerShell to enable archive mailboxes. See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span> 
    
- <span data-ttu-id="f647e-p106">自動拡張アーカイブは、共有メールボックスもサポートします。共有メールボックスのアーカイブを有効にするには、exchange online プラン2ライセンスまたは exchange online プラン1ライセンスを持つ exchange online プラン1ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="f647e-p106">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>
    
- <span data-ttu-id="f647e-p107">Exchange 管理センターまたはセキュリティ&amp;コンプライアンスセンターを使用して、自動拡張アーカイブを有効にすることはできません。Exchange Online PowerShell を使用する必要があります。リモート powershell を使用して exchange online 組織に接続するには、「 [exchange online powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f647e-p107">You can't use the Exchange admin center or the Security &amp; Compliance Center to enable auto-expanding archiving. You have to use Exchange Online PowerShell. To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="f647e-124">組織全体で自動拡張アーカイブを有効にする</span><span class="sxs-lookup"><span data-stu-id="f647e-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="f647e-p108">組織全体で自動拡張アーカイブを有効にすることができます。オンにすると、既存のユーザーメールボックスおよび作成された新しいユーザーメールボックスに対して、自動拡張アーカイブが有効になります。新しいユーザーメールボックスを作成するときは、自動拡張アーカイブ機能が新しいユーザーメールボックスに対して機能するように、ユーザーのメインアーカイブメールボックスを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="f647e-p108">You can enable auto-expanding archiving for your entire organization. After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created. When you create new user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature will work for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="f647e-128">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="f647e-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="f647e-129">Exchange Online PowerShell で次のコマンドを実行して、組織全体の自動拡張アーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f647e-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="f647e-130">特定のユーザーに対して自動拡張アーカイブを有効にする</span><span class="sxs-lookup"><span data-stu-id="f647e-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="f647e-p109">組織内のすべてのユーザーに対して自動拡張アーカイブを有効にする代わりに、特定のユーザーに対して有効にすることができます。これは、一部のユーザーのみが大規模なアーカイブストレージを必要とする場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="f647e-p109">Instead of enabling auto-expanding archiving for every user in your organization, you can just enable it for specific users. You might do this because only some users might have a need for a very large archive storage.</span></span>
  
<span data-ttu-id="f647e-133">特定のユーザーおよびユーザーのメールボックスの自動拡張アーカイブを有効にしたり、Office 365 アイテム保持ポリシーに割り当てたりすると、次の2つの構成変更が行われます。</span><span class="sxs-lookup"><span data-stu-id="f647e-133">When you enable auto-expanding archiving for a specific user and the user's mailbox in on hold or assigned to an Office 365 retention policy, the following two configurations changes are made:</span></span>
  
- <span data-ttu-id="f647e-p110">ユーザーのプライマリアーカイブメールボックスの記憶域クォータが 10 gb 増加します (100 gb から 110 gb)。アーカイブ警告クォータも、10 gb 増加します (90 gb から 100 gb まで)。</span><span class="sxs-lookup"><span data-stu-id="f647e-p110">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB). The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>
    
- <span data-ttu-id="f647e-p111">ユーザーのプライマリメールボックスの回復可能なアイテムフォルダーの記憶域のクォータは、10 gb 増加します (100 gb から 110 gb にもなります)。回復可能なアイテムの警告クォータも、10 gb 増加します (90 gb から 100 gb まで)。これらの変更は、メールボックスがオンに保持されている場合、または Office 365 アイテム保持ポリシーに割り当てられている場合にのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="f647e-p111">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB). The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB). These changes are applicable only if the mailbox in on hold or assigned to an Office 365 retention policy.</span></span>
    
<span data-ttu-id="f647e-p112">この追加容量は、自動拡張アーカイブがプロビジョニングされる前に発生する可能性のある記憶域の問題を防ぐために追加されています。前のセクションで説明したように、組織全体で自動拡張アーカイブを有効にする場合は、追加の記憶域が追加され*ない*ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f647e-p112">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned. Note that additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span> 
  
1. [<span data-ttu-id="f647e-141">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="f647e-141">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="f647e-p113">Exchange Online PowerShell で次のコマンドを実行して、特定のユーザーの自動拡張アーカイブを有効にします。前述のように、ユーザーのアーカイブメールボックス (メインアーカイブ) は、そのユーザーの自動拡張アーカイブを有効にする前に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f647e-p113">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user. As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> <span data-ttu-id="f647e-p114">Exchange ハイブリッド展開では、**メールボックス-autoexpandingarchive**コマンドを使用して、プライマリメールボックスがオンプレミスの特定のユーザーに対して自動拡張アーカイブを有効にし、そのアーカイブメールボックスがクラウドベースであることを確認することはできません。exchange ハイブリッド展開でクラウドベースのアーカイブメールボックスの自動拡張アーカイブを有効にするには、の自動拡張アーカイブを有効にするために、exchange Online の PowerShell で [**設定-組織の構成-autoexpandingarchive** ] コマンドを実行する必要があります。組織全体。ユーザーのプライマリメールボックスとアーカイブメールボックスの両方がクラウドベースである場合は、その特定のユーザーに対して自動拡張アーカイブを有効にするために、**メールボックス-autoexpandingarchive**コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f647e-p114">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for specific a user whose primary mailbox is on premises and their archive mailbox is cloud-based. To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization. If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span> 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="f647e-147">自動拡張アーカイブが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="f647e-147">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="f647e-148">組織で自動拡張アーカイブが有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f647e-148">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="f647e-149">の`True`値は、自動拡張アーカイブが組織に対して有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="f647e-149">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="f647e-150">特定のユーザーに対して自動拡張アーカイブが有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f647e-150">To verify that auto-expanding archiving is enable for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
<span data-ttu-id="f647e-151">の`True`値は、自動拡張アーカイブがユーザーに対して有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="f647e-151">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="f647e-152">自動拡張アーカイブを有効にした後は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f647e-152">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="f647e-p115">組織の自動拡張アーカイブを有効にするために、**グループの設定-autoexpandingarchive**コマンドを実行する場合は、個々のメールボックスで**autoexpandingarchive**を実行する必要はありません。組織の自動拡張アーカイブを有効にするために、**グループの設定**コマンドレットを実行しても、ユーザーメールボックスの*autoexpanding書庫 enabled*プロパティはに`True`変更されません。</span><span class="sxs-lookup"><span data-stu-id="f647e-p115">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes. Note that running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to  `True`.</span></span>
    
- <span data-ttu-id="f647e-p116">同様に、自動拡張アーカイブを有効にすると、 *ArchiveQuota*プロパティと*アーカイブ警告クォータ*メールボックスのプロパティの値は変更されません。実際には、ユーザーメールボックスの自動拡張アーカイブを有効にし、 *autoexpanding書庫 enabled*プロパティがに`True`設定されている場合、 *ArchiveQuota*プロパティと*アーカイブ警告クォータ*プロパティは無視されます。ユーザーのメールボックスに対して自動拡張アーカイブが有効になった後のメールボックスプロパティの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f647e-p116">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving. In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are just ignored. Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 
    
    ![自動拡張アーカイブを有効にした後、ArchiveQuota およびアーカイブの警告クォータのプロパティは無視されます。](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a><span data-ttu-id="f647e-159">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f647e-159">More information</span></span>

- <span data-ttu-id="f647e-p117">PowerShell を使用してアーカイブメールボックスを有効にすることもできます。たとえば、Exchange Online PowerShell で次のコマンドを実行すると、アーカイブメールボックスがまだ有効になっていないすべてのユーザーのアーカイブメールボックスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f647e-p117">You can also use PowerShell to enable archive mailboxes. For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="f647e-p118">組織の自動拡張アーカイブを有効にした後、または特定のユーザーの場合、アーカイブメールボックス (回復可能なアイテムフォルダーを含む) が 90 GB に達したときにアーカイブメールボックスが自動拡張アーカイブに変換されます。追加のストレージ容量をプロビジョニングするには、最大30日間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f647e-p118">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB. It can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
- <span data-ttu-id="f647e-164">自動拡張アーカイブを有効にした後は、オフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f647e-164">After you turn on auto-expanding archiving, it can't be turned off.</span></span>
    
- <span data-ttu-id="f647e-p119">オンプレミスのプライマリメールボックスを持つユーザーの Exchange ハイブリッド展開では、クラウドベースのアーカイブメールボックスに対して、自動拡張アーカイブがサポートされます。ただし、クラウドベースのアーカイブメールボックスに対して自動拡張アーカイブが有効になっている場合、メールボックスをオンプレミスの Exchange 組織に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f647e-p119">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox. However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span>
    
- <span data-ttu-id="f647e-167">ユーザーがアーカイブメールボックス内の追加のストレージ領域にあるアイテムへのアクセスに使用できる outlook クライアントの一覧については、「 [Office 2010 での無制限アーカイブの概要](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)」の「自動拡張アーカイブのアイテムにアクセスするための outlook 要件」セクションを参照してください365.</span><span class="sxs-lookup"><span data-stu-id="f647e-167">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>
    
- <span data-ttu-id="f647e-p120">前述したように、**メールボックス-autoexpandingarchive**コマンドを実行すると、ユーザーのプライマリアーカイブメールボックスの記憶域クォータ (およびメールボックスが保留中の場合は、回復可能なアイテムフォルダー) に 10 GB が追加されます。これにより、自動拡張された記憶域がプロビジョニングされるまで、追加の記憶域が提供されます (最大30日間かかることがあります)。この追加記憶域は、組織内のすべてのメールボックスの自動拡張アーカイブを有効にするために、**グループ設定-autoexpandingarchive**を実行するときには追加されません。組織全体で自動拡張アーカイブを有効にしているが、特定のユーザーに対して追加の 10 GB の記憶域を追加する必要がある場合は、そのメールボックスで**メールボックス-autoexpandingarchive**コマンドを実行することができます。自動拡張アーカイブが既に有効になっていることを示すエラーが表示されますが、追加の記憶域がメールボックスに追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f647e-p120">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command. This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days). This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization. If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox. Note that you will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span> 
