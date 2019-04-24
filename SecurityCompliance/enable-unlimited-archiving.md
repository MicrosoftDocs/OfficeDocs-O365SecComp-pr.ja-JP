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
description: '管理者向け: Office 365 で自動拡張アーカイブを有効にする方法について説明します。これにより、ユーザーに Exchange Online メールボックスのための無制限のストレージが提供されます。 自動拡張アーカイブは、組織全体に対して、または特定のユーザーに対してのみ有効にすることができます。'
ms.openlocfilehash: e41ebc0605b7e6ce2178791de27421a82e2b6cf6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256842"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a><span data-ttu-id="d7174-104">Office 365 で無制限のアーカイブを有効にする-管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="d7174-104">Enable unlimited archiving in Office 365 - Admin Help</span></span>

<span data-ttu-id="d7174-105">Office 365 の Exchange Online 自動拡張アーカイブ機能を使用して、アーカイブメールボックスの無制限の記憶域スペースを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7174-105">You can use the Exchange Online auto-expanding archiving feature in Office 365 to enable unlimited storage space for archive mailboxes.</span></span> <span data-ttu-id="d7174-106">自動拡張アーカイブが有効になっている場合は、記憶域の制限に近づいたときに、ユーザーのアーカイブメールボックスに追加の記憶域が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d7174-106">When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit.</span></span> <span data-ttu-id="d7174-107">その結果、メールボックスの格納容量は無制限になります。</span><span class="sxs-lookup"><span data-stu-id="d7174-107">The result is unlimited mailbox storage capacity.</span></span> <span data-ttu-id="d7174-108">自動拡張アーカイブは、組織内のすべてのユーザーに対して、または特定のユーザーに対してのみ有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7174-108">You can turn on auto-expanding archiving for everyone in your organization or just for specific users.</span></span> <span data-ttu-id="d7174-109">自動拡張アーカイブの詳細については、「 [Office 365 の無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7174-109">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d7174-110">始める前に</span><span class="sxs-lookup"><span data-stu-id="d7174-110">Before you begin</span></span>

- <span data-ttu-id="d7174-111">組織全体または特定のユーザーに対して自動拡張アーカイブを有効にするには、Office 365 組織のグローバル管理者、または Exchange Online 組織の organization Management 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7174-111">You have to be a global administrator in your Office 365 organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users.</span></span> <span data-ttu-id="d7174-112">または、特定のユーザーに対して自動拡張アーカイブを有効にするために、メール受信者の役割が割り当てられている役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7174-112">Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>
    
- <span data-ttu-id="d7174-113">自動拡張アーカイブを有効にするには、ユーザーのアーカイブメールボックスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7174-113">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving.</span></span> <span data-ttu-id="d7174-114">アーカイブメールボックスを有効にするには、ユーザーに Exchange Online プラン2ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7174-114">A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox.</span></span> <span data-ttu-id="d7174-115">ユーザーに exchange online プラン1ライセンスが割り当てられている場合は、アーカイブメールボックスを有効にするために別の exchange online アーカイブライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7174-115">If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox.</span></span> <span data-ttu-id="d7174-116">「 [Security & コンプライアンスセンターでアーカイブメールボックスを有効にする](enable-archive-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7174-116">See [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md).</span></span>
    
- <span data-ttu-id="d7174-117">PowerShell を使用してアーカイブメールボックスを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d7174-117">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="d7174-118">組織内のすべてのユーザーに対してアーカイブメールボックスを有効にするために使用できる PowerShell コマンドの例については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7174-118">See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span> 
    
- <span data-ttu-id="d7174-119">アーカイブの自動拡張では、共有メールボックスもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d7174-119">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="d7174-120">共有メールボックスのアーカイブを有効にするには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving のライセンスの付いた Exchange Online プラン 1 のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d7174-120">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>
    
- <span data-ttu-id="d7174-121">Exchange 管理センターまたはセキュリティ & コンプライアンスセンターを使用して、自動拡張アーカイブを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d7174-121">You can't use the Exchange admin center or the Security & Compliance Center to enable auto-expanding archiving.</span></span> <span data-ttu-id="d7174-122">Exchange Online PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7174-122">You have to use Exchange Online PowerShell.</span></span> <span data-ttu-id="d7174-123">リモート powershell を使用して exchange online 組織に接続するには、「 [exchange online powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7174-123">To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="d7174-124">組織全体で自動拡張アーカイブを有効にする</span><span class="sxs-lookup"><span data-stu-id="d7174-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="d7174-125">組織全体で自動拡張アーカイブを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7174-125">You can enable auto-expanding archiving for your entire organization.</span></span> <span data-ttu-id="d7174-126">オンにすると、既存のユーザーメールボックスおよび作成された新しいユーザーメールボックスに対して、自動拡張アーカイブが有効になります。</span><span class="sxs-lookup"><span data-stu-id="d7174-126">After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created.</span></span> <span data-ttu-id="d7174-127">新しいユーザーメールボックスを作成するときは、自動拡張アーカイブ機能が新しいユーザーメールボックスに対して機能するように、ユーザーのメインアーカイブメールボックスを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="d7174-127">When you create new user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature will work for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="d7174-128">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="d7174-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="d7174-129">Exchange Online PowerShell で次のコマンドを実行して、組織全体の自動拡張アーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7174-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="d7174-130">特定のユーザーに対して自動拡張アーカイブを有効にする</span><span class="sxs-lookup"><span data-stu-id="d7174-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="d7174-131">組織内のすべてのユーザーに対して自動拡張アーカイブを有効にする代わりに、特定のユーザーに対して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7174-131">Instead of enabling auto-expanding archiving for every user in your organization, you can just enable it for specific users.</span></span> <span data-ttu-id="d7174-132">これは、一部のユーザーのみが大規模なアーカイブストレージを必要とする場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="d7174-132">You might do this because only some users might have a need for a very large archive storage.</span></span>
  
<span data-ttu-id="d7174-133">特定のユーザーおよびユーザーのメールボックスの自動拡張アーカイブを有効にしたり、Office 365 アイテム保持ポリシーに割り当てたりすると、次の2つの構成変更が行われます。</span><span class="sxs-lookup"><span data-stu-id="d7174-133">When you enable auto-expanding archiving for a specific user and the user's mailbox in on hold or assigned to an Office 365 retention policy, the following two configurations changes are made:</span></span>
  
- <span data-ttu-id="d7174-134">ユーザーのプライマリアーカイブメールボックスの記憶域クォータが 10 gb 増加します (100 gb から 110 gb)。</span><span class="sxs-lookup"><span data-stu-id="d7174-134">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB).</span></span> <span data-ttu-id="d7174-135">アーカイブ警告クォータも、10 gb 増加します (90 gb から 100 gb まで)。</span><span class="sxs-lookup"><span data-stu-id="d7174-135">The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>
    
- <span data-ttu-id="d7174-136">ユーザーのプライマリメールボックスの回復可能なアイテムフォルダーの記憶域のクォータは、10 gb 増加します (100 gb から 110 gb にもなります)。</span><span class="sxs-lookup"><span data-stu-id="d7174-136">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB).</span></span> <span data-ttu-id="d7174-137">回復可能なアイテムの警告クォータも、10 gb 増加します (90 gb から 100 gb まで)。</span><span class="sxs-lookup"><span data-stu-id="d7174-137">The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span> <span data-ttu-id="d7174-138">これらの変更は、メールボックスがオンに保持されている場合、または Office 365 アイテム保持ポリシーに割り当てられている場合にのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="d7174-138">These changes are applicable only if the mailbox in on hold or assigned to an Office 365 retention policy.</span></span>
    
<span data-ttu-id="d7174-139">この追加容量は、自動拡張アーカイブがプロビジョニングされる前に発生する可能性のある記憶域の問題を防ぐために追加されています。</span><span class="sxs-lookup"><span data-stu-id="d7174-139">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned.</span></span> <span data-ttu-id="d7174-140">前のセクションで説明したように、組織全体で自動拡張アーカイブを有効にする場合は、追加の記憶域が追加され*ない*ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d7174-140">Note that additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span> 
  
1. [<span data-ttu-id="d7174-141">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="d7174-141">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="d7174-142">Exchange Online PowerShell で次のコマンドを実行して、特定のユーザーの自動拡張アーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7174-142">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user.</span></span> <span data-ttu-id="d7174-143">前述のように、ユーザーのアーカイブメールボックス (メインアーカイブ) は、そのユーザーの自動拡張アーカイブを有効にする前に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7174-143">As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> <span data-ttu-id="d7174-144">Exchange ハイブリッド展開では、**メールボックス-autoexpandingarchive**コマンドを使用して、プライマリメールボックスがオンプレミスの特定のユーザーに対して自動拡張アーカイブを有効にし、そのアーカイブメールボックスがクラウドベースであることを確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7174-144">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for specific a user whose primary mailbox is on premises and their archive mailbox is cloud-based.</span></span> <span data-ttu-id="d7174-145">exchange ハイブリッド展開でクラウドベースのアーカイブメールボックスの自動拡張アーカイブを有効にするには、の自動拡張アーカイブを有効にするために、exchange Online の PowerShell で [**設定-組織の構成-autoexpandingarchive** ] コマンドを実行する必要があります。組織全体。</span><span class="sxs-lookup"><span data-stu-id="d7174-145">To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization.</span></span> <span data-ttu-id="d7174-146">ユーザーのプライマリメールボックスとアーカイブメールボックスの両方がクラウドベースである場合は、その特定のユーザーに対して自動拡張アーカイブを有効にするために、**メールボックス-autoexpandingarchive**コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7174-146">If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span> 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="d7174-147">自動拡張アーカイブが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="d7174-147">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="d7174-148">組織で自動拡張アーカイブが有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d7174-148">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="d7174-149">の`True`値は、自動拡張アーカイブが組織に対して有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d7174-149">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="d7174-150">特定のユーザーに対して自動拡張アーカイブが有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d7174-150">To verify that auto-expanding archiving is enable for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
<span data-ttu-id="d7174-151">の`True`値は、自動拡張アーカイブがユーザーに対して有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d7174-151">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="d7174-152">自動拡張アーカイブを有効にした後は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d7174-152">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="d7174-153">組織の自動拡張アーカイブを有効にするために、**グループの設定-autoexpandingarchive**コマンドを実行する場合は、個々のメールボックスで**autoexpandingarchive**を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d7174-153">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes.</span></span> <span data-ttu-id="d7174-154">組織の自動拡張アーカイブを有効にするために、**グループの設定**コマンドレットを実行しても、ユーザーメールボックスの*autoexpanding書庫 enabled*プロパティはに`True`変更されません。</span><span class="sxs-lookup"><span data-stu-id="d7174-154">Note that running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to  `True`.</span></span>
    
- <span data-ttu-id="d7174-155">同様に、自動拡張アーカイブを有効にすると、 *ArchiveQuota*プロパティと*アーカイブ警告クォータ*メールボックスのプロパティの値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="d7174-155">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving.</span></span> <span data-ttu-id="d7174-156">実際には、ユーザーメールボックスの自動拡張アーカイブを有効にし、 *autoexpanding書庫 enabled*プロパティがに`True`設定されている場合、 *ArchiveQuota*プロパティと*アーカイブ警告クォータ*プロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="d7174-156">In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are just ignored.</span></span> <span data-ttu-id="d7174-157">ユーザーのメールボックスに対して自動拡張アーカイブが有効になった後のメールボックスプロパティの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d7174-157">Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 
    
    ![自動拡張アーカイブを有効にした後、ArchiveQuota およびアーカイブの警告クォータのプロパティは無視されます。](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a><span data-ttu-id="d7174-159">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d7174-159">More information</span></span>

- <span data-ttu-id="d7174-160">PowerShell を使用してアーカイブメールボックスを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d7174-160">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="d7174-161">たとえば、Exchange Online PowerShell で次のコマンドを実行すると、アーカイブメールボックスがまだ有効になっていないすべてのユーザーのアーカイブメールボックスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7174-161">For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="d7174-162">組織の自動拡張アーカイブを有効にした後、または特定のユーザーの場合、アーカイブメールボックス (回復可能なアイテムフォルダーを含む) が 90 GB に達したときにアーカイブメールボックスが自動拡張アーカイブに変換されます。</span><span class="sxs-lookup"><span data-stu-id="d7174-162">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB.</span></span> <span data-ttu-id="d7174-163">追加のストレージ容量をプロビジョニングするには、最大30日間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d7174-163">It can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
- <span data-ttu-id="d7174-164">自動拡張アーカイブを有効にした後は、オフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d7174-164">After you turn on auto-expanding archiving, it can't be turned off.</span></span>
    
- <span data-ttu-id="d7174-165">オンプレミスのプライマリメールボックスを持つユーザーの Exchange ハイブリッド展開では、クラウドベースのアーカイブメールボックスに対して、自動拡張アーカイブがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d7174-165">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox.</span></span> <span data-ttu-id="d7174-166">ただし、クラウドベースのアーカイブメールボックスに対して自動拡張アーカイブが有効になっている場合、メールボックスをオンプレミスの Exchange 組織に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="d7174-166">However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span> <span data-ttu-id="d7174-167">自動拡張アーカイブは、Exchange Server 2010 の社内メールボックスではサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d7174-167">Note that auto-expanding archiving isn't supported for on-premises mailboxes in Exchange Server 2010.</span></span>
    
- <span data-ttu-id="d7174-168">ユーザーがアーカイブメールボックス内の追加のストレージ領域にあるアイテムへのアクセスに使用できる outlook クライアントの一覧については、「 [Office 2010 での無制限アーカイブの概要](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)」の「自動拡張アーカイブのアイテムにアクセスするための outlook 要件」セクションを参照してください365.</span><span class="sxs-lookup"><span data-stu-id="d7174-168">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>
    
- <span data-ttu-id="d7174-169">前述したように、**メールボックス-autoexpandingarchive**コマンドを実行すると、ユーザーのプライマリアーカイブメールボックスの記憶域クォータ (およびメールボックスが保留中の場合は、回復可能なアイテムフォルダー) に 10 GB が追加されます。</span><span class="sxs-lookup"><span data-stu-id="d7174-169">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command.</span></span> <span data-ttu-id="d7174-170">これにより、自動拡張された記憶域がプロビジョニングされるまで、追加の記憶域が提供されます (最大30日間かかることがあります)。</span><span class="sxs-lookup"><span data-stu-id="d7174-170">This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days).</span></span> <span data-ttu-id="d7174-171">この追加記憶域は、組織内のすべてのメールボックスの自動拡張アーカイブを有効にするために、**グループ設定-autoexpandingarchive**を実行するときには追加されません。</span><span class="sxs-lookup"><span data-stu-id="d7174-171">This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization.</span></span> <span data-ttu-id="d7174-172">組織全体で自動拡張アーカイブを有効にしているが、特定のユーザーに対して追加の 10 GB の記憶域を追加する必要がある場合は、そのメールボックスで**メールボックス-autoexpandingarchive**コマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="d7174-172">If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox.</span></span> <span data-ttu-id="d7174-173">自動拡張アーカイブが既に有効になっていることを示すエラーが表示されますが、追加の記憶域がメールボックスに追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d7174-173">Note that you will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span> 

- <span data-ttu-id="d7174-174">管理者は、記憶域のクォータを調整できません。</span><span class="sxs-lookup"><span data-stu-id="d7174-174">Administrators can't adjust the storage quota.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7174-175">自動拡張アーカイブは、個々のユーザーに使用されるメールボックス、または1日あたり 1 GB を超える成長率を持つ共有メールボックスに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d7174-175">Auto-expanding archiving is only supported for mailboxes used for individual users or shared mailboxes with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="d7174-176">アーカイブの目的で、ジャーナリング、トランスポートルール、または自動転送ルールを使用してアーカイブメールボックスにメッセージをコピーすることは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="d7174-176">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox for the purposes of archiving is not permitted.</span></span> <span data-ttu-id="d7174-177">ユーザーのアーカイブ メールボックスは、そのユーザー専用です。</span><span class="sxs-lookup"><span data-stu-id="d7174-177">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="d7174-178">Microsoft は、ユーザーのアーカイブ メールボックスを使用して他のユーザーのアーカイブ データを格納する、インスタンスでの無制限アーカイブを拒否する権利を有します。</span><span class="sxs-lookup"><span data-stu-id="d7174-178">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users.</span></span>
