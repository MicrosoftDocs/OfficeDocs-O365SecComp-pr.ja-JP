---
title: 保持中のメールボックスの [回復可能なアイテム] のクォータを拡大する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 'Office 365 のメールボックスの回復可能なアイテムフォルダーのサイズを大きくするには、アーカイブメールボックスを有効にして、自動拡張アーカイブをオンにします。 '
ms.openlocfilehash: 701821074294441525315c3db77daeccd5700935
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296540"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="57827-103">保持中のメールボックスの [回復可能なアイテム] のクォータを拡大する</span><span class="sxs-lookup"><span data-stu-id="57827-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="57827-p101">既定の mrm policy という名前の既定のアイテム保持ポリシー (Exchange Online の新しいメールボックスに自動的に適用される) には、「回復可能なアイテム」という名前の保持タグが含まれており、14日でアーカイブに移動します。この保持タグは、アイテムの14日の保存期間が経過した後、ユーザーのプライマリメールボックスの回復可能なアイテムフォルダーからユーザーのアーカイブメールボックスの回復可能なアイテムフォルダーにアイテムを移動します。これを行うには、ユーザーのアーカイブメールボックスが有効になっている必要があります。アーカイブメールボックスが有効になっていない場合、操作は実行されず、保留中のメールボックスの [回復可能なアイテム] フォルダー内のアイテムは、14日の保持期間が経過した後はアーカイブメールボックスに移動されません。保留中のメールボックスからは何も削除されないため、特にユーザーのアーカイブメールボックスが有効になっていない場合は、回復可能なアイテムフォルダーの記憶域のクォータを超過する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57827-p101">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive. This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item. For this to happen, the user's archive mailbox must be enabled. If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires. Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="57827-p102">この制限を超える可能性を減らすために、Exchange Online のメールボックスに保留が設定されている場合、回復可能なアイテムフォルダーの記憶域のクォータは自動的に 30 gb から 100 GB に増加します。アーカイブメールボックスが有効になっている場合、アーカイブメールボックス内の回復可能なアイテムフォルダーの記憶域クォータも 30 gb から 100 gb に増加します。Exchange Online の自動拡張アーカイブ機能が有効になっている場合、ユーザーのアーカイブ内の回復可能なアイテムフォルダーの記憶域のクォータは無制限になります。</span><span class="sxs-lookup"><span data-stu-id="57827-p102">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online. If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB. If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="57827-112"> [回復可能なアイテム] フォルダーの記憶域クォータを次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="57827-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="57827-113">**[回復可能なアイテム] フォルダーの場所**</span><span class="sxs-lookup"><span data-stu-id="57827-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="57827-114">**保持中でないメールボックス**</span><span class="sxs-lookup"><span data-stu-id="57827-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="57827-115">**保持中のメールボックス**</span><span class="sxs-lookup"><span data-stu-id="57827-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57827-116">プライマリ メールボックス</span><span class="sxs-lookup"><span data-stu-id="57827-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="57827-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="57827-117">30 GB</span></span>  <br/> |<span data-ttu-id="57827-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="57827-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="57827-119">アーカイブメールボックス<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="57827-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="57827-120">無制限</span><span class="sxs-lookup"><span data-stu-id="57827-120">Unlimited</span></span>  <br/> |<span data-ttu-id="57827-121">無制限</span><span class="sxs-lookup"><span data-stu-id="57827-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="57827-122">**[回復可能なアイテム] フォルダーの記憶域クォータの合計**</span><span class="sxs-lookup"><span data-stu-id="57827-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="57827-123">無制限</span><span class="sxs-lookup"><span data-stu-id="57827-123">Unlimited</span></span>  <br/> |<span data-ttu-id="57827-124">無制限</span><span class="sxs-lookup"><span data-stu-id="57827-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="57827-p103"><sup>\*</sup>Exchange Online (Plan 2) ライセンスを持つユーザーの場合、アーカイブメールボックスの初期格納域のクォータは 100 GB です。ただし、保留中のメールボックスに対して自動拡張アーカイブが有効になっている場合、アーカイブメールボックスと回復可能なアイテムフォルダーの両方の記憶域クォータは 110 GB に増加します。必要に応じて、アーカイブストレージの容量が無制限にプロビジョニングされます。自動拡張アーカイブの詳細については、「 [Office 365 の無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57827-p103"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license. However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB. Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="57827-129">保持中のメールボックスのプライマリ メールボックスに含まれる [回復可能なアイテム] フォルダーの記憶域クォータが上限に近づいたら、次の対策を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="57827-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="57827-p104">アーカイブ**メールボックスを有効にして自動拡張アーカイブを**有効にする-アーカイブメールボックスを有効にし、Exchange の自動拡張アーカイブ機能をオンにして、回復可能なアイテムフォルダーの記憶域の容量を無制限に有効にすることができます。オンライン。この結果、プライマリメールボックスの回復可能なアイテムフォルダーでは 110 GB、ユーザーのアーカイブ内の回復可能なアイテムフォルダーの記憶域の容量に制限はありません。「方法: office [365 セキュリティ&amp;コンプライアンスセンターでアーカイブメールボックスを有効](enable-archive-mailboxes.md)にする」および「 [office 365 で無制限のアーカイブを有効](enable-unlimited-archiving.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57827-p104">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online. This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive. See how: [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="57827-p105">回復可能なアイテムフォルダーの記憶域のクォータを超えているメールボックスのアーカイブを有効にした後、管理フォルダーアシスタントを実行して、メールボックスを処理するようにアシスタントを手動でトリガーし、期限切れのアイテムが移動されるようにすることができます。アーカイブメールボックス内の回復可能なアイテムフォルダー。手順4については、[手順 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)を参照してください。ユーザーのメールボックス内の他のアイテムが新しいアーカイブメールボックスに移動される場合があることに注意してください。アーカイブメールボックスを有効にした後にこれが発生する可能性があることをユーザーに通知することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="57827-p105">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox. See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions. Note that other items in the user's mailbox might be moved to the new archive mailbox. Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="57827-p106">メール**ボックスのカスタムアイテム保持ポリシーを作成**する。アーカイブメールボックスとメールボックスの自動拡張アーカイブを訴訟ホールドまたはインプレースホールドで有効にすることに加えて、メールボックス用にカスタムアイテム保持ポリシーを作成することもできます。収める.これにより、ホールドしていないメールボックスに適用される既定の mrm ポリシーとは異なるメールボックスにアイテム保持ポリシーを適用することができます。これにより、メールボックス専用に設計された保持タグを保持することができます。これには、回復可能なアイテムフォルダーの新しい保持タグの作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="57827-p106">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold. This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold. This lets you to apply retention tags that are specifically designed for mailboxes on hold. This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="57827-141">このトピックの残りの部分では、保持中のメールボックスのカスタム保存ポリシーを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="57827-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
<span data-ttu-id="57827-142">[手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="57827-142">[Step 1: Create a custom retention tag for the Recoverable Items folder](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span></span>

<span data-ttu-id="57827-143">[[手順 2: 保留中のメールボックスの新しいアイテム保持ポリシーを作成する](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="57827-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="57827-144">手順 3:保持中のメールボックスに新しいアイテム保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="57827-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="57827-145">(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する</span><span class="sxs-lookup"><span data-stu-id="57827-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="57827-146">手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する</span><span class="sxs-lookup"><span data-stu-id="57827-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="57827-p107">最初の手順として、回復可能なアイテムフォルダーのカスタム保持タグ (アイテム保持ポリシータグまたは RPT と呼ばれる) を作成します。前述したように、この RPT では、ユーザーのプライマリメールボックスの回復可能なアイテムフォルダーから、ユーザーのアーカイブメールボックスの回復可能なアイテムフォルダーにアイテムを移動します。回復可能なアイテムフォルダーの RPT を作成するには、PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="57827-p107">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder. As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox. You have to use PowerShell to create an RPT for the Recoverable Items folder. You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="57827-151">リモート PowerShell による Exchange Online への接続</span><span class="sxs-lookup"><span data-stu-id="57827-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="57827-152">[回復可能なアイテム] フォルダーの新しい RPT を作成するには、次のコマンドを実行します。 </span><span class="sxs-lookup"><span data-stu-id="57827-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="57827-p108">たとえば、次のコマンドを実行すると、[回復可能なアイテム] フォルダー用に "Recoverable Items 30 days for mailboxes on hold" という名前の RPT が作成され、保持期間が 30 日間に設定されます。これは、アイテムが [回復可能なアイテム] フォルダーに移動されてから 30 日後に、そのアイテムがユーザーのアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されるということです。</span><span class="sxs-lookup"><span data-stu-id="57827-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="57827-p109">回復可能なアイテム rpt の保存期間 ( _agelimitforretention_パラメーターで定義) は、rpt が適用されるメールボックスの削除済みアイテムの保存期間と同じであることをお勧めします。これにより、ユーザーは、削除済みアイテムの保存期間を、アーカイブメールボックスに移動する前に削除されたアイテムを復元することができます。前の例では、メールボックスの削除済みアイテムの保存期間も30日であるという前提に基づいて、保存期間は30日に設定されていました。Exchange Online メールボックスは、既定では、削除済みアイテムを14日間保持するように構成されています。ただし、この設定は最大30日に変更できます。詳細については、「 [Exchange Online のメールボックスの削除済みアイテムの保存期間を変更する](https://go.microsoft.com/fwlink/p/?LinkId=286940)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57827-p109">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to. This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox. In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days. An Exchange Online mailbox is configured to retain deleted items for 14 days, by default. But you can change this setting to a maximum of 30 days. For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="57827-161">手順 2: 保持中のメールボックスの新しいアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="57827-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="57827-p110">次の手順では、新しいアイテム保持ポリシーを作成し、そのポリシーに保持タグ (手順 1 で作成した回復可能なアイテムの RPT を含む) を追加します。この新しいポリシーは、次の手順で保持中のメールボックスに適用します。 </span><span class="sxs-lookup"><span data-stu-id="57827-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="57827-p111">新しいアイテム保持ポリシーを作成する前に、追加する保持タグを決定します。Default MRM Policy に追加されている保持タグの一覧、および新しい保持タグを作成する方法については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57827-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="57827-166">Exchange Online の既定のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="57827-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="57827-167">アイテム保持ポリシー タグをサポートする既定のフォルダー</span><span class="sxs-lookup"><span data-stu-id="57827-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="57827-168">「[アイテム保持ポリシーの作成](https://go.microsoft.com/fwlink/p/?LinkId=404422)」の「保持タグを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57827-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="57827-169">EAC または Exchange Online の PowerShell を使用して、アイテム保持ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="57827-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="57827-170">EAC を使用してアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="57827-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="57827-171">EAC で、[**コンプライアンス管理** \> \*\*\*\* ![] [**アイテム保持ポリシー**] の順に移動し](media/ITPro-EAC-AddIcon.gif)、[追加] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="57827-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="57827-172">**[新しい保持ポリシー]** ページの **[名前]** に、アイテム保持ポリシーの目的を説明する名前 (例: **MRM Policy for Mailboxes on Hold**) を入力します。 </span><span class="sxs-lookup"><span data-stu-id="57827-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="57827-173">[**保持タグ**] で\*\*\*\* ![、[追加](media/ITPro-EAC-AddIcon.gif)] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="57827-173">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="57827-174">保持タグの一覧で、手順 1 で作成した回復可能なアイテムの RPT を選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57827-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![カスタムの [回復可能なアイテム] 保持タグを選択する](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="57827-p112">アイテム保持ポリシーに追加する保持タグを選択します。たとえば、Default MRM Policy に含まれているのと同じタグを追加します。</span><span class="sxs-lookup"><span data-stu-id="57827-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="57827-178">保持タグの追加が完了したら、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57827-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="57827-179">**[保存]** をクリックして新しいアイテム保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="57827-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="57827-180">アイテム保持ポリシーにリンクされている保持タグが詳細ウィンドウに表示されることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="57827-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![アイテム保持ポリシーにリンクした保持タグが詳細ウィンドウに表示される](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="57827-182">Exchange Online の PowerShell を使用してアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="57827-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="57827-183">保持中のメールボックスの新しいアイテム保持ポリシーを作成するには、次のコマンドを実行します。 </span><span class="sxs-lookup"><span data-stu-id="57827-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="57827-184">たとえば次のコマンドを実行すると、前の図に示されているアイテム保持ポリシーとそれにリンクされている保持タグが作成されます。</span><span class="sxs-lookup"><span data-stu-id="57827-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="57827-185">手順 3:保持中のメールボックスに新しいアイテム保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="57827-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="57827-p113">最後の手順として、手順2で作成した新しいアイテム保持ポリシーを組織内のメールボックス保留リストに適用します。EAC または Exchange Online の PowerShell を使用して、1つのメールボックスまたは複数のメールボックスにアイテム保持ポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="57827-p113">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization. You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="57827-188">EAC を使用して新しい保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="57827-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="57827-189">**[受信者]** \> **[メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="57827-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="57827-190">リストビューで、アイテム保持ポリシーを適用するメールボックスを選択し、[編集アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)の**編集** ![] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57827-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="57827-191">**[ユーザー メールボックス]** ページで、**[メールボックスの機能]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57827-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="57827-192">**[アイテム保持ポリシー]** から、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57827-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="57827-193">EAC を使用して、アイテム保持ポリシーを複数のメールボックスに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="57827-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="57827-194">**[受信者]** \> **[メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="57827-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="57827-195">リスト ビューで、Shift キーまたは Ctrl キーを使用して複数のメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="57827-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="57827-196">詳細ウィンドウで、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57827-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="57827-197">**[アイテム保持ポリシー]** 下で **[更新]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57827-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="57827-198">**[アイテム保持ポリシーの一括割り当て]** ページで、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="57827-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="57827-199">Exchange Online PowerShell を使用して新しいアイテム保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="57827-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="57827-p114">Exchange Online PowerShell を使用して、単一のメールボックスに新しいアイテム保持ポリシーを適用することができます。ただし、PowerShell の本当の威力は、これを使用して組織内のすべてのメールボックスを迅速に特定して、訴訟ホールドまたはインプレース保持のいずれかに設定し、保留中のすべてのメールボックスに新しいアイテム保持ポリシーを1つのコマンドで適用できることです。Exchange PowerShell を使用して1つ以上のメールボックスにアイテム保持ポリシーを適用する例を次に示します。すべての例は、手順2で作成したアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="57827-p114">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox. But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command. Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes. All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="57827-204">この例では、Pilar Pinilla のメールボックスに新しいアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="57827-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="57827-205">この例では、組織内の訴訟ホールド中のすべてのメールボックスに新しいアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="57827-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="57827-206">この例では、組織内のインプレース ホールド中のすべてのメールボックスに新しいアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="57827-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="57827-207">**Get-Mailbox** コマンドレットを使用すると、新しいアイテム保持ポリシーが適用されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="57827-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="57827-208">以下は、前の例で実行したコマンドを使用して、"MRM Policy for Mailboxes on Hold" というアイテム保持ポリシーが、訴訟ホールド中のメールボックスとインプレース ホールド中のメールボックスに適用されたことを確認する例です。</span><span class="sxs-lookup"><span data-stu-id="57827-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="57827-209">(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する</span><span class="sxs-lookup"><span data-stu-id="57827-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="57827-p115">保留中のメールボックスに新しいアイテム保持ポリシーを適用した後、管理フォルダーアシスタントが新しいアイテム保持ポリシーの設定を使用してこれらのメールボックスを処理するには、Exchange Online で最大7日かかることがあります。管理フォルダーアシスタントの実行を待つ代わりに、**開始-managedfolderassistant**コマンドレットを使用して、新しいアイテム保持ポリシーを適用したメールボックスを処理するようにアシスタントを手動でトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="57827-p115">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy. Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="57827-212">Pilar Pinilla のメールボックスに対して管理フォルダー アシスタントを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57827-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="57827-213">保持中のすべてのメールボックスに対して管理フォルダー アシスタントを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57827-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="57827-214">詳細情報</span><span class="sxs-lookup"><span data-stu-id="57827-214">More information</span></span>

- <span data-ttu-id="57827-p116">ユーザーのアーカイブメールボックスを有効にした後、ユーザーにメールボックス内の他のアイテム (回復可能なアイテムフォルダー内のアイテムだけでなく) がアーカイブメールボックスに移動する可能性があることを通知します。これは、Exchange Online メールボックスに割り当てられている既定の mrm ポリシーには、アイテムがメールボックスに配信された日から2年後にアーカイブメールボックスにアイテムを移動する保持タグ (既定では、アーカイブに移動する) が含まれているためです。マニュアル.詳細については、「[既定のアイテム保持ポリシー (Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954) )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57827-p116">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox. This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="57827-p117">ユーザーのアーカイブメールボックスを有効にした後、ユーザーに対して、アーカイブメールボックス内の [回復可能なアイテム] フォルダーにある削除済みのアイテムを復元できることを通知することもできます。Outlook でこの操作を行うには、アーカイブメールボックスの [**削除済みアイテム**] フォルダーを選択し、[**ホーム**] タブの [**サーバーからの削除済みアイテムの回復**] をクリックします。削除済みアイテムの復元の詳細については、「 [Windows 版 Outlook で削除済みアイテムを復元する](https://go.microsoft.com/fwlink/p/?LinkId=624829)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57827-p117">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox. They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
