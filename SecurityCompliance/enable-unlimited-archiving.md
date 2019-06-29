---
title: Office 365 で無制限アーカイブを有効にする - 管理者向けヘルプ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: Admin
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
description: '管理者向け: Exchange Online メールボックスで無制限の記憶領域をユーザーに提供する、Office 365 での自動拡張アーカイブを有効にする方法について説明します。 組織全体に対し、または特定のユーザーだけに対し、自動拡張アーカイブを有効にすることができます。'
ms.openlocfilehash: a6f1e0e43854372b2c7b93c22c1160a7c555a95f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154749"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a><span data-ttu-id="4432e-104">Office 365 で無制限アーカイブを有効にする - 管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="4432e-104">Enable unlimited archiving in Office 365 - Admin Help</span></span>

<span data-ttu-id="4432e-105">Office 365 の Exchange Online 自動拡張アーカイブ機能を使用して、アーカイブ メールボックスで無制限の記憶領域を有効化できます。</span><span class="sxs-lookup"><span data-stu-id="4432e-105">You can use the Exchange Online auto-expanding archiving feature in Office 365 to enable unlimited storage space for archive mailboxes.</span></span> <span data-ttu-id="4432e-106">自動拡張アーカイブが有効になっている場合、ユーザーのアーカイブ メールボックスが容量の上限に近づくと、追加の記憶領域が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4432e-106">After you enable auto-expanding archiving, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit.</span></span> <span data-ttu-id="4432e-107">無制限のメールボックス記憶容量が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4432e-107">The result is unlimited mailbox storage capacity.</span></span> <span data-ttu-id="4432e-108">組織の全ユーザーに対し、または特定のユーザーだけに対し、自動拡張アーカイブを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4432e-108">You can turn on auto-expanding archiving for everyone in your organization or just for specific users.</span></span> <span data-ttu-id="4432e-109">自動拡張アーカイブの詳細については、「[Office 365 での無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4432e-109">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365https://go.microsoft.com/fwlink/p/?linkid=844060](unlimited-archiving.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4432e-110">始める前に</span><span class="sxs-lookup"><span data-stu-id="4432e-110">Before you begin</span></span>

- <span data-ttu-id="4432e-111">組織全体または特定のユーザーの自動拡張アーカイブを有効にするには、Office 365 組織の全体管理者であるか、または Exchange Online 組織の組織管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4432e-111">You have to be a global administrator in your Office 365 organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users.</span></span> <span data-ttu-id="4432e-112">または、特定のユーザーに対する自動拡張アーカイブを有効にするには、メール受信者の役割を割り当てられた役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4432e-112">Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>
    
- <span data-ttu-id="4432e-113">自動拡張アーカイブを有効にする前に、ユーザーのアーカイブ メールボックスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4432e-113">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving.</span></span> <span data-ttu-id="4432e-114">アーカイブ メールボックスを有効にするには、ユーザーに Exchange Online プラン 2 のライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4432e-114">A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox.</span></span> <span data-ttu-id="4432e-115">ユーザーに Exchange Online プラン 1 のライセンスが割り当てられている場合、アーカイブ メールボックスを有効にするには、別の Exchange Online アーカイブ ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4432e-115">If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox.</span></span> <span data-ttu-id="4432e-116">「[セキュリティ/コンプライアンス センターでアーカイブ メールボックスを有効にする](enable-archive-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4432e-116">Enable archive mailboxes in the Security &  Compliance Center</span></span>
    
- <span data-ttu-id="4432e-117">PowerShell を使って、アーカイブ メールボックスを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4432e-117">You can also configure a different archive name when you use Windows PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="4432e-118">組織内のすべてのユーザーのアーカイブ メールボックスを有効するために使用できる PowerShell コマンドの例については、「[詳細情報](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4432e-118">See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span> 
    
- <span data-ttu-id="4432e-119">アーカイブの自動拡張では、共有メールボックスもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4432e-119">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="4432e-120">共有メールボックスのアーカイブを有効にするには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving のライセンスの付いた Exchange Online プラン 1 のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4432e-120">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>
    
- <span data-ttu-id="4432e-121">Exchange 管理センターまたはセキュリティ/コンプライアンスセンターを使用して自動拡張アーカイブを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4432e-121">You can't use the Exchange admin center or the Security & Compliance Center to enable auto-expanding archiving.</span></span> <span data-ttu-id="4432e-122">Exchange Online PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4432e-122">You have to use Exchange Online PowerShell.</span></span> <span data-ttu-id="4432e-123">リモート PowerShell を使って Exchange Online 組織に接続する方法については、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4432e-123">To connect to Exchange Online using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="4432e-124">自動拡張アーカイブを組織全体で有効にする</span><span class="sxs-lookup"><span data-stu-id="4432e-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="4432e-125">組織全体の自動拡張アーカイブを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4432e-125">You can enable auto-expanding archiving for your entire organization.</span></span> <span data-ttu-id="4432e-126">いったん有効にすると、既存ユーザーのメールボックスと、作成される新規ユーザーのメールボックスに対し、自動拡張アーカイブが有効になります。</span><span class="sxs-lookup"><span data-stu-id="4432e-126">After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created.</span></span> <span data-ttu-id="4432e-127">新しいユーザー メールボックスを作成するときは、自動拡張アーカイブ機能が新しいユーザー メールボックスで機能するように、ユーザーのメイン アーカイブ メールボックスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4432e-127">When you create new user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature will work for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="4432e-128">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="4432e-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="4432e-129">自動拡張アーカイブを組織全体で有効にするには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4432e-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="4432e-130">自動拡張アーカイブを特定のユーザーに対して有効にする</span><span class="sxs-lookup"><span data-stu-id="4432e-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="4432e-131">組織内のすべてのユーザーの自動拡張アーカイブを有効にするのではなく、特定のユーザーについてだけ有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4432e-131">Instead of enabling auto-expanding archiving for every user in your organization, you can just enable it for specific users.</span></span> <span data-ttu-id="4432e-132">大容量のアーカイブ記憶領域を必要とするのが一部のユーザーのみの場合に、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="4432e-132">You might do this because only some users might have a need for a very large archive storage.</span></span>
  
<span data-ttu-id="4432e-133">特定のユーザーに対して自動拡張アーカイブを有効にした場合で、ユーザーのメールボックスが保留中であるか Office 365 保持ポリシーに割り当てられている場合、次の 2 つの構成変更が行われます。</span><span class="sxs-lookup"><span data-stu-id="4432e-133">When you enable auto-expanding archiving for a specific user and the user's mailbox in on hold or assigned to an Office 365 retention policy, the following two configurations changes are made:</span></span>
  
- <span data-ttu-id="4432e-134">ユーザーのプライマリ アーカイブ メールボックスの記憶領域のクォータが 10 GB 増加します (100 GB から 110 GB へ)。</span><span class="sxs-lookup"><span data-stu-id="4432e-134">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB).</span></span> <span data-ttu-id="4432e-135">また、アーカイブの警告クォータも 10 GB 増加します (90 GB から 100 GB へ)。</span><span class="sxs-lookup"><span data-stu-id="4432e-135">The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>
    
- <span data-ttu-id="4432e-136">ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダーの記憶領域のクォータは、10 GB 増加します (100 GB から 110 GB へ)。</span><span class="sxs-lookup"><span data-stu-id="4432e-136">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB).</span></span> <span data-ttu-id="4432e-137">回復可能なアイテムの警告クォータも、10 GB 増加します (90 GB から 100 GB へ)。</span><span class="sxs-lookup"><span data-stu-id="4432e-137">The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span> <span data-ttu-id="4432e-138">これらの変更は、メールボックスが保留中の場合、または Office 365 のアイテム保持ポリシーに割り当てられている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="4432e-138">These changes are applicable only if the mailbox in on hold or assigned to an Office 365 retention policy.</span></span>
    
<span data-ttu-id="4432e-139">この追加容量は、自動拡張アーカイブのプロビジョニングが行われる前に発生する可能性がある記憶領域の問題を防ぐために追加されるものです。</span><span class="sxs-lookup"><span data-stu-id="4432e-139">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned.</span></span> <span data-ttu-id="4432e-140">前のセクションで説明したように、自動拡張アーカイブを組織全体に対して有効にする場合は、追加記憶領域は追加*されない*ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4432e-140">Note that additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span> 
  
1. [<span data-ttu-id="4432e-141">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="4432e-141">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="4432e-142">自動拡張アーカイブを特定のユーザーに対して有効にするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4432e-142">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user.</span></span> <span data-ttu-id="4432e-143">前述のように、ユーザーの自動拡張アーカイブを有効にする前に、そのユーザーのアーカイブ メールボックス (メイン アーカイブ) を有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="4432e-143">As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> <span data-ttu-id="4432e-144">Exchange ハイブリッド展開では、ユーザーのプライマリメールボックスがオンプレミスにあり、かつアーカイブ メールボックスがクラウド ベースの特定のユーザーについては、**Enable-Mailbox -AutoExpandingArchive** コマンドを使用して自動拡張アーカイブを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4432e-144">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for specific a user whose primary mailbox is on premises and their archive mailbox is cloud-based.</span></span> <span data-ttu-id="4432e-145">クラウド ベースのアーカイブ メールボックスの自動拡張アーカイブを Exchange ハイブリッド展開で有効にするには、Exchange Online PowerShell で **Set-OrganizationConfig -AutoExpandingArchive** コマンドを実行して、組織全体に対して自動拡張アーカイブを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4432e-145">To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization.</span></span> <span data-ttu-id="4432e-146">ユーザーのプライマリ メールボックスとアーカイブ メールボックスが両方ともクラウド ベースの場合は、**Enable-Mailbox -AutoExpandingArchive** コマンドを使用してそのユーザーに対して自動拡張アーカイブを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4432e-146">If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span> 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="4432e-147">自動拡張アーカイブが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="4432e-147">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="4432e-148">自動拡張アーカイブが組織に対して有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4432e-148">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="4432e-149">値 `True` は、自動拡張アーカイブが組織に対して有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="4432e-149">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="4432e-150">自動拡張アーカイブが特定のユーザーに対して有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4432e-150">To verify that auto-expanding archiving is enable for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
<span data-ttu-id="4432e-151">値 `True` は、自動拡張アーカイブがそのユーザーに対して有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="4432e-151">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="4432e-152">自動拡張アーカイブを有効にした後は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4432e-152">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="4432e-153">**Set-OrganizationConfig -AutoExpandingArchive** コマンドを実行して自動拡張アーカイブを組織に対して有効化する場合は、個々のメールボックスに対して **Enable-Mailbox -AutoExpandingArchive** を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4432e-153">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes.</span></span> <span data-ttu-id="4432e-154">**Set-OrganizationConfig** コマンドレットを実行して組織の自動拡張アーカイブを有効にしても、ユーザー メールボックスの *AutoExpandingArchiveEnabled* プロパティは `True` に変わらないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="4432e-154">Note that running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to  `True`.</span></span>
    
- <span data-ttu-id="4432e-155">同様に、自動拡張アーカイブを有効にしても、メールボックスの *ArchiveQuota* プロパティと *ArchiveWarningQuota* プロパティの値も変更されません。</span><span class="sxs-lookup"><span data-stu-id="4432e-155">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving.</span></span> <span data-ttu-id="4432e-156">実際、ユーザー メールボックスの自動拡張アーカイブを有効にして、*AutoExpandingArchiveEnabled* プロパティを `True` に設定している場合、*ArchiveQuota* プロパティと *ArchiveWarningQuota* プロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="4432e-156">In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are just ignored.</span></span> <span data-ttu-id="4432e-157">ユーザーのメールボックスの自動拡張アーカイブを有効にした後のこれらのメールボックス プロパティの例を示します。</span><span class="sxs-lookup"><span data-stu-id="4432e-157">Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 
    
    ![自動拡張アーカイブを有効にした後、ArchiveQuota と ArchiveWarningQuota プロパティは無視されます。](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a><span data-ttu-id="4432e-159">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4432e-159">More information</span></span>

- <span data-ttu-id="4432e-160">PowerShell を使って、アーカイブ メールボックスを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4432e-160">You can also configure a different archive name when you use Windows PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="4432e-161">たとえば、Exchange Online PowerShell で次のコマンドを実行して、アーカイブ メールボックスがまだ有効になっていないすべてのユーザーのアーカイブ メールボックスを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4432e-161">For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="4432e-162">組織または特定のユーザーに対して自動拡張アーカイブを有効にした後、アーカイブ メールボックス ([回復可能なアイテム] フォルダーを含む) が 90 GB に達すると、アーカイブ メールボックスは自動拡張アーカイブに変換されます。</span><span class="sxs-lookup"><span data-stu-id="4432e-162">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB.</span></span> <span data-ttu-id="4432e-163">追加記憶領域がプロビジョニングされるには、最大 30 日かかります。</span><span class="sxs-lookup"><span data-stu-id="4432e-163">Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
- <span data-ttu-id="4432e-164">自動拡張アーカイブを有効にした後は、無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4432e-164">After you turn on auto-expanding archiving, it can't be turned off.</span></span>
    
- <span data-ttu-id="4432e-165">自動拡張アーカイブは、オンプレミスのプライマリメールボックスを持つユーザーについて、Exchange ハイブリッド展開のクラウド ベースのアーカイブ メールボックスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4432e-165">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox.</span></span> <span data-ttu-id="4432e-166">ただし、クラウド ベースのアーカイブ メールボックスに対して自動拡張アーカイブを有効にした後は、そのアーカイブ メールボックスをオフボードしてオンプレミスの Exchange 組織に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="4432e-166">However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span> <span data-ttu-id="4432e-167">Exchange Server 2010 のオンプレミスのメールボックスでは、自動拡張アーカイブはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4432e-167">Note that auto-expanding archiving isn't supported for on-premises mailboxes in Exchange Server 2010.</span></span>
    
- <span data-ttu-id="4432e-168">アーカイブ メールボックスの追加記憶領域内のアイテムにアクセスするためにユーザーが使用できる Outlook クライアントの一覧については、「[Office 365 での無制限アーカイブの概要](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)」の「自動拡張アーカイブ内のアイテムにアクセスするための Outlook の要件」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4432e-168">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>
    
- <span data-ttu-id="4432e-169">前述のように、**Enable-Mailbox -AutoExpandingArchive** コマンドを実行すると、ユーザーのプライマリ アーカイブ メールボックス (および、メールボックスが保留中の場合は、[回復可能なアイテム] フォルダー) の記憶領域のクォータ に 10 GB が追加されます。</span><span class="sxs-lookup"><span data-stu-id="4432e-169">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command.</span></span> <span data-ttu-id="4432e-170">これにより、自動拡張記憶領域がプロビジョニングされるまで (最大で30 日間かかります)、追加の記憶領域が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4432e-170">This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days).</span></span> <span data-ttu-id="4432e-171">**Set-OrganizationConfig -AutoExpandingArchive** を実行して組織のすべてのメールボックスに対して自動拡張アーカイブを有効化した場合は、追加記憶領域は追加されません。</span><span class="sxs-lookup"><span data-stu-id="4432e-171">This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization.</span></span> <span data-ttu-id="4432e-172">自動拡張アーカイブを組織全体に対して有効化した場合でも、特定のユーザーの記憶領域に 10 GB を追加する必要がある場合は、そのメールボックスに対して **Enable-Mailbox -AutoExpandingArchive** コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4432e-172">If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox.</span></span> <span data-ttu-id="4432e-173">自動拡張アーカイブが既に有効化されているというエラー メッセージが表示されますが、メールボックスには追加記憶領域が追加されます。</span><span class="sxs-lookup"><span data-stu-id="4432e-173">Note that you will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span> 

- <span data-ttu-id="4432e-174">管理者は、記憶領域のクォータを調整できません。</span><span class="sxs-lookup"><span data-stu-id="4432e-174">Administrators can't adjust the storage quota.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4432e-175">自動拡張アーカイブがサポートされているのは、個々のユーザーのメールボックスまたは 1 日あたりの成長率が 1 GB 未満の共有メールボックスのみです。</span><span class="sxs-lookup"><span data-stu-id="4432e-175">Auto-expanding archiving is only supported for mailboxes used for individual users or shared mailboxes with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="4432e-176">アーカイブ目的のために、ジャーナリング、トランスポート ルール、または自動転送ルールを使用してメッセージをアーカイブ メールボックスにコピーすることは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="4432e-176">Using journaling, transport rules, or auto-forwarding rules to copy messages to an Exchange Online mailbox for the purposes of archiving is not permitted.</span></span> <span data-ttu-id="4432e-177">ユーザーのアーカイブ メールボックスは、そのユーザー専用です。</span><span class="sxs-lookup"><span data-stu-id="4432e-177">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="4432e-178">Microsoft は、ユーザーのアーカイブ メールボックスを使用して他のユーザーのアーカイブ データを格納する、インスタンスでの無制限アーカイブを拒否する権利を有します。</span><span class="sxs-lookup"><span data-stu-id="4432e-178">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users.</span></span>
