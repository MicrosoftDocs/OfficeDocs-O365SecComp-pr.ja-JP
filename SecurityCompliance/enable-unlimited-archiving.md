---
title: Office 365 の管理者のヘルプで無制限のアーカイブを有効にします。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: '管理者: アーカイブを無制限のストレージとオンラインの Exchange メールボックスのユーザーを提供する、Office 365 で自動拡張を有効にする方法について説明します。組織全体または特定のユーザーのためだけにアーカイブを自動拡張を有効にできます。'
ms.openlocfilehash: 6dd49433a1692d3a0ba23af57e7e2d9544f8a2b1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531567"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a><span data-ttu-id="03197-104">Office 365 の管理者のヘルプで無制限のアーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="03197-104">Enable unlimited archiving in Office 365 - Admin Help</span></span>

<span data-ttu-id="03197-p102">Office 365 で自動展開する Exchange のオンライン アーカイブ機能を使用するにはアーカイブ メールボックスの無制限のストレージ ・ スペースを有効にします。アーカイブの自動拡張を有効にすると、格納域の制限に近づくと追加の記憶域がユーザーのアーカイブ メールボックスに自動的に追加します。無制限のメールボックスの容量になります。有効にできます、組織内の全員に対して、または特定のユーザーのためだけのアーカイブの自動拡張します。自動拡張の詳細については、 [Office 365 で無制限のアーカイブの概要](unlimited-archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03197-p102">You can use the Exchange Online auto-expanding archiving feature in Office 365 to enable unlimited storage space for archive mailboxes. When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit. The result is unlimited mailbox storage capacity. You can turn on auto-expanding archiving for everyone in your organization or just for specific users. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="03197-110">はじめに</span><span class="sxs-lookup"><span data-stu-id="03197-110">Before you begin</span></span>

- <span data-ttu-id="03197-p103">グローバル管理者、Office 365 の組織または組織全体または特定のユーザーをアーカイブする自動拡張を有効にするのには、Exchange Online 組織内の組織の管理役割グループのメンバーであります。代わりに、特定のユーザーのアーカイブを自動拡張を有効にするのには差し込み印刷の宛先役割が割り当てられている役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="03197-p103">You have to be a global administrator in your Office 365 organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users. Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>
    
- <span data-ttu-id="03197-p104">ユーザーのアーカイブ メールボックスは、アーカイブの自動拡張を有効にする前に有効にするのには。ユーザーには、アーカイブ メールボックスを有効にするのには、Exchange オンライン計画 2 ライセンスを割り当てる必要があります。ユーザーには、Exchange オンライン計画 1 ライセンスが割り当てられているが場合、は、アーカイブ メールボックスを有効にするのには別の Exchange Online Archiving のライセンスを割り当てる必要があります。参照してください[Office 365 のセキュリティのアーカイブ メールボックスを有効にする&amp;コンプライアンス センター](enable-archive-mailboxes.md)です。</span><span class="sxs-lookup"><span data-stu-id="03197-p104">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving. A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox. If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox. See [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md).</span></span>
    
- <span data-ttu-id="03197-p105">アーカイブ メールボックスを有効にするのに PowerShell を使用することもできます。組織内のすべてのユーザーのアーカイブ メールボックスを有効にするを使用することができます PowerShell コマンドの例については、[詳細について](#more-information)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="03197-p105">You can also use PowerShell to enable archive mailboxes. See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span> 
    
- <span data-ttu-id="03197-p106">アーカイブ自動拡張は、共有メールボックスをサポートします。共有されているメールボックスのアーカイブを有効にするには、Exchange オンライン計画 2 ライセンスまたは Exchange Online Archiving のライセンスを持つ Exchange オンライン計画 1 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="03197-p106">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>
    
- <span data-ttu-id="03197-p107">Exchange 管理センターまたはセキュリティを使用することはできません&amp;コンプライアンスの中央アーカイブの自動拡張を有効にします。Exchange オンライン PowerShell を使用する必要があります。リモート PowerShell を使用して Exchange Online 組織に接続するには、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03197-p107">You can't use the Exchange admin center or the Security &amp; Compliance Center to enable auto-expanding archiving. You have to use Exchange Online PowerShell. To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="03197-124">組織全体のアーカイブを自動拡張を有効にします。</span><span class="sxs-lookup"><span data-stu-id="03197-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="03197-p108">組織全体のアーカイブを自動拡張を有効にできます。有効にすると、アーカイブの自動拡張が有効にして作成される新しいユーザーのメールボックスのユーザーのメールボックスを既存の。新しいユーザーのメールボックスを作成する場合は、自動拡張のアーカイブ機能は新しいユーザーのメールボックスの使用、ユーザーのメインのアーカイブ メールボックスを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="03197-p108">You can enable auto-expanding archiving for your entire organization. After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created. When you create new user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature will work for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="03197-128">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="03197-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="03197-129">組織全体のアーカイブを自動拡張を有効にするのには、Exchange オンライン PowerShell では、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03197-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="03197-130">自動拡張の特定のユーザーのアーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="03197-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="03197-p109">組織内のすべてのユーザーのアーカイブを自動拡張を有効にするのではなくできるだけ有効にする特定のユーザーに対して。一部のユーザーだけでは非常に大規模なアーカイブ ・ ストレージが必要である可能性がありますのででこれを行う場合があります。</span><span class="sxs-lookup"><span data-stu-id="03197-p109">Instead of enabling auto-expanding archiving for every user in your organization, you can just enable it for specific users. You might do this because only some users might have a need for a very large archive storage.</span></span>
  
<span data-ttu-id="03197-133">自動拡張の特定のユーザーのアーカイブを有効にすると、以下 2 つの構成も変更されます。</span><span class="sxs-lookup"><span data-stu-id="03197-133">When you enable auto-expanding archiving for a specific user, the following two configurations changes are also made:</span></span>
  
- <span data-ttu-id="03197-134">(110 GB に 100 GB) から 10 GB では、ユーザーのアーカイブをプライマリ メールボックスの記憶域のクォータが増加します。</span><span class="sxs-lookup"><span data-stu-id="03197-134">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB).</span></span>
    
- <span data-ttu-id="03197-p110">(110 GB に 100 GB) からも、10 GB で、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダーの記憶域のクォータを増加します。この変更は、上にメールボックスを保持する場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="03197-p110">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB). This change is applicable only if the mailbox in on hold.</span></span>
    
<span data-ttu-id="03197-p111">自動拡張のアーカイブを準備する前に発生する記憶域の問題を防ぐためには、この追加の空き領域が追加されます。その追加のストレージ領域*は*前のセクションで説明したように、組織全体のアーカイブを自動拡張を有効にしたときに追加に注意してください。</span><span class="sxs-lookup"><span data-stu-id="03197-p111">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned. Note that additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span> 
  
1. [<span data-ttu-id="03197-139">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="03197-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="03197-p112">自動拡張の特定のユーザーのアーカイブを有効にする Exchange のオンライン PowerShell では、次のコマンドを実行します。説明したよう、ユーザーのアーカイブ メールボックス (メイン アーカイブ) する必要があります有効にするを有効にできます、ユーザーのアーカイブの自動拡張する前に。</span><span class="sxs-lookup"><span data-stu-id="03197-p112">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user. As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> <span data-ttu-id="03197-p113">Exchange ハイブリッド展開の場合では、設置型では、プライマリ メールボックスを持つユーザーの固有のアーカイブの自動拡張を有効にする**有効にするメールボックス AutoExpandingArchive**コマンドを使用することはできませんし、クラウド ベースのアーカイブ メールボックスは、します。コマンドを実行する**セット OrganizationConfig AutoExpandingArchive** Exchange オンライン アーカイブを自動拡張を有効にする PowerShell がある Exchange ハイブリッド展開でのクラウド ・ ベースのアーカイブ メールボックスのアーカイブを自動拡張を有効にするには、全体の組織です。主のユーザーのアーカイブ メールボックスは、クラウド ベースの両方は、場合は、特定のユーザーに対してアーカイブを自動拡張を有効にするのには、**有効にするメールボックス AutoExpandingArchive**コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="03197-p113">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for specific a user whose primary mailbox is on premises and their archive mailbox is cloud-based. To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization. If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span> 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="03197-145">アーカイブの自動拡張が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="03197-145">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="03197-146">組織のアーカイブの自動拡張が有効になっていることを確認するには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03197-146">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="03197-147">値の`True`、組織のアーカイブの自動拡張が有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="03197-147">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="03197-148">自動拡張が特定のユーザーに対して有効にすることを確認するには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03197-148">To verify that auto-expanding archiving is enable for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
<span data-ttu-id="03197-149">値の`True`のユーザーのアーカイブの自動拡張が有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="03197-149">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="03197-150">アーカイブの自動拡張を有効にした後、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="03197-150">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="03197-p114">組織のアーカイブを自動拡張を有効に**設定 OrganizationConfig AutoExpandingArchive**コマンドを実行する場合は個々 のメールボックスに**メールボックスが有効にする AutoExpandingArchive**を実行する必要はありません。組織は、 *AutoExpandingArchiveEnabled*のプロパティを変更するユーザーのメールボックスのアーカイブ自動拡張を有効に**設定 OrganizationConfig**コマンドレットを実行することに注意してください`True`。</span><span class="sxs-lookup"><span data-stu-id="03197-p114">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes. Note that running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to  `True`.</span></span>
    
- <span data-ttu-id="03197-p115">同様に、アーカイブの自動拡張を有効にすると、 *ArchiveQuota*と*ArchiveWarningQuota*のメールボックスのプロパティの値は変更されません。実際には、ユーザーのメールボックスのアーカイブを自動拡張を有効にして、 *AutoExpandingArchiveEnabled*プロパティ`True`、 *ArchiveQuota*および*ArchiveWarningQuota*プロパティは無視されます。ユーザーのメールボックスのアーカイブの自動拡張を有効にした後、これらのメールボックスのプロパティの例をここでは。</span><span class="sxs-lookup"><span data-stu-id="03197-p115">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving. In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are just ignored. Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 
    
    ![アーカイブの自動拡張を有効にした後、ArchiveQuota および ArchiveWarningQuota プロパティは無視されます。](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a><span data-ttu-id="03197-157">詳細情報</span><span class="sxs-lookup"><span data-stu-id="03197-157">More information</span></span>

- <span data-ttu-id="03197-p116">アーカイブ メールボックスを有効にするのに PowerShell を使用することもできます。などをオンラインで実行できる次のコマンド Exchange PowerShell のアーカイブ メールボックスが既に有効になっていないすべてのユーザーのアーカイブ メールボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="03197-p116">You can also use PowerShell to enable archive mailboxes. For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="03197-p117">有効にした後組織のまたは特定のユーザーのアーカイブの自動拡張、アーカイブ先のメールボックス (回復可能な項目] フォルダーを含む) が 90 GB に達すると、自動拡張のアーカイブ、アーカイブ メールボックスが変換されます。準備する追加の記憶域の最大 30 日間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="03197-p117">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB. It can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
- <span data-ttu-id="03197-162">を有効にするアーカイブの自動展開後は、オフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="03197-162">After you turn on auto-expanding archiving, it can't be turned off.</span></span>
    
- <span data-ttu-id="03197-p118">設置型のプライマリ メールボックスを持つユーザーに対して Exchange ハイブリッド展開でのクラウド ・ ベースのアーカイブ メールボックスには、アーカイブの自動拡張がサポートされています。ただし、クラウド ・ ベースのアーカイブ メールボックスのアーカイブの自動拡張を有効にすると、することはできませんオフボードそのアーカイブ先のメールボックスをオンプレミスの Exchange 組織に戻る。</span><span class="sxs-lookup"><span data-stu-id="03197-p118">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox. However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span>
    
- <span data-ttu-id="03197-165">ユーザーがアーカイブ メールボックスに追加のストレージ領域内の項目にアクセスするために使用できる Outlook クライアントのリストは、[無制限の概要については、Office 365 のアーカイブ](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)で「Outlook の自動展開されたアーカイブ内のアイテムにアクセスするための要件」セクションを参照してください。.</span><span class="sxs-lookup"><span data-stu-id="03197-165">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>
    
- <span data-ttu-id="03197-p119">これまで説明すると、10 GB がユーザーのアーカイブをプライマリ メールボックスの記憶域のクォータに追加されます (回復可能なアイテム] フォルダーに、メールボックスが存在する場合を保持) とコマンドを実行する**を有効にするメールボックスの AutoExpandingArchive**です。自動拡張記憶域を準備する (これは最大で 30 日間がかかることができます) になるまで、追加の記憶域を提供します。この追加の記憶域は、組織内のすべてのメールボックスのアーカイブを自動拡張を有効にする**セット OrganizationConfig AutoExpandingArchive**を実行するときに追加されません。アーカイブを組織全体については、自動拡張が有効になって、10 GB の追加の特定のユーザーの記憶域を追加する必要がある場合は、そのメールボックスに**メールボックスが有効にする AutoExpandingArchive**コマンドを実行できます。アーカイブの自動拡張が既に有効になって、ですが、追加のストレージ領域は、メールボックスに追加することを示すエラーが発生することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="03197-p119">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command. This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days). This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization. If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox. Note that you will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span> 
