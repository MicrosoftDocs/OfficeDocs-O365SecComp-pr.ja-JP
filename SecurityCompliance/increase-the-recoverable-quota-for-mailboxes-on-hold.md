---
title: 保持中のメールボックスの [回復可能なアイテム] のクォータを拡大する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 'アーカイブ先のメールボックスを有効にして、Office 365 のメールボックスの回復可能なアイテム] フォルダーのサイズを大きくにはアーカイブの自動拡張を有効にします。 '
ms.openlocfilehash: a347155645d7c058080b1db7fd47f7ea16249724
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522278"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="6d5cf-103">保持中のメールボックスの [回復可能なアイテム] のクォータを拡大する</span><span class="sxs-lookup"><span data-stu-id="6d5cf-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="6d5cf-p101">デフォルトの保持ポリシー、MRM ポリシーを既定の名前-は Exchange Online のメールボックス新規作成] を自動的に適用されているにはには、名前付きのアイテムの回復可能な 14 日間の移動をアーカイブする保持タグが含まれています。この保持タグは、14 日間の保存期間は、アイテムの有効期限が切れる後アイテムをユーザーのプライマリ メールボックスの回復可能なアイテム] フォルダーから、ユーザーのアーカイブ メールボックスの回復可能なアイテム] フォルダーに移動します。これを実現するには、ユーザーのアーカイブ メールボックスを有効にする必要があります。アーカイブ先のメールボックスが有効でない場合何も起こりません、上のメールボックスのフォルダーを保持する回復可能なアイテムのアイテムは、14 日間の保存期間が終了した後アーカイブ メールボックスに移動されていないことを意味します。保留中のメールボックスからは削除されず、ためことは、回復可能なアイテム] フォルダーの記憶域のクォータを超えた可能性があるユーザーのアーカイブ メールボックスが有効になっていない場合に特に。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p101">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive. This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item. For this to happen, the user's archive mailbox must be enabled. If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires. Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="6d5cf-p102">この制限を超える可能性を減らすためには、回復可能なアイテム] フォルダーの記憶域のクォータが自動的に増加 30 GB から 100 GB を保留リストに格納されるメールボックス Exchange オンライン。アーカイブ先のメールボックスが有効な場合、アーカイブ メールボックスの回復可能なアイテム フォルダーの記憶域のクォータも増加 30 GB から 100 GB にします。アーカイブの自動拡張機能の Exchange でオンラインになって、ユーザーのアーカイブの回復可能なアイテム フォルダーの記憶域のクォータの制限が解除されます。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p102">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online. If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB. If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="6d5cf-112"> [回復可能なアイテム] フォルダーの記憶域クォータを次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="6d5cf-113">**[回復可能なアイテム] フォルダーの場所**</span><span class="sxs-lookup"><span data-stu-id="6d5cf-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="6d5cf-114">**保持中でないメールボックス**</span><span class="sxs-lookup"><span data-stu-id="6d5cf-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="6d5cf-115">**保持中のメールボックス**</span><span class="sxs-lookup"><span data-stu-id="6d5cf-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d5cf-116">プライマリ メールボックス</span><span class="sxs-lookup"><span data-stu-id="6d5cf-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="6d5cf-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="6d5cf-117">30 GB</span></span>  <br/> |<span data-ttu-id="6d5cf-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="6d5cf-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="6d5cf-119">アーカイブ先のメールボックス<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6d5cf-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="6d5cf-120">無制限</span><span class="sxs-lookup"><span data-stu-id="6d5cf-120">Unlimited</span></span>  <br/> |<span data-ttu-id="6d5cf-121">無制限</span><span class="sxs-lookup"><span data-stu-id="6d5cf-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="6d5cf-122">**[回復可能なアイテム] フォルダーの記憶域クォータの合計**</span><span class="sxs-lookup"><span data-stu-id="6d5cf-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="6d5cf-123">無制限</span><span class="sxs-lookup"><span data-stu-id="6d5cf-123">Unlimited</span></span>  <br/> |<span data-ttu-id="6d5cf-124">無制限</span><span class="sxs-lookup"><span data-stu-id="6d5cf-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="6d5cf-p103"><sup>\*</sup>アーカイブ先のメールボックスの最初の記憶域のクォータでは、100 GB を Exchange Online (プラン 2) のライセンスを持つユーザーです。ただし、アーカイブの自動拡張がオンの保留中のメールボックス、アーカイブ メールボックスと、回復可能なアイテム] フォルダーの両方の記憶域のクォータは 110 GB に増加します。追加のアーカイブ ・ ストレージ ・ スペースが必要な場合に準備されますされ、アーカイブ ・ ストレージの無制限の量です。自動拡張の詳細については、 [Office 365 で無制限のアーカイブの概要](unlimited-archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p103"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license. However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB. Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="6d5cf-129">保持中のメールボックスのプライマリ メールボックスに含まれる [回復可能なアイテム] フォルダーの記憶域クォータが上限に近づいたら、次の対策を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="6d5cf-p104">**アーカイブ先のメールボックスを有効にしてアーカイブの自動拡張を有効にする**だけで、アーカイブ メールボックスを有効にして、Exchange の自動拡張のアーカイブ機能をオンにし、回復可能なアイテム] フォルダーに、無制限のストレージ容量を有効にできますオンライン。これは、結果、110 GB のプライマリ メールボックスとユーザーのアーカイブの回復可能なアイテム フォルダーのストレージ容量の無制限の量で回復可能なアイテムのフォルダーにします。参照してください方法: [Office 365 のセキュリティのアーカイブ メールボックスを有効にする&amp;コンプライアンス センター](enable-archive-mailboxes.md)し、 [Office 365 で無制限のアーカイブを有効に](enable-unlimited-archiving.md)します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p104">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online. This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive. See how: [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6d5cf-p105">期限切れアイテムが移動されるため、メールボックスを処理するため、アシスタントを手動で開始する管理フォルダー アシスタントを実行する場合、回復可能なアイテム] フォルダーの記憶域のクォータを超えるの近くにあるメールボックスのアーカイブを有効にした後、アーカイブ メールボックスの回復可能なアイテム] フォルダーです。手順については、[手順 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)を参照してください。新しいアーカイブ メールボックスにユーザーのメールボックス内のアイテムを移動する場合があることに注意してください。アーカイブ メールボックスを有効にした後、この可能性があります発生することをユーザーに示すことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p105">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox. See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions. Note that other items in the user's mailbox might be moved to the new archive mailbox. Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="6d5cf-p106">**上のメールボックスのユーザー設定の保持ポリシーの保持を作成する**のに加えて、アーカイブ メールボックスを有効にして、証拠保全や場所に置くと、上のメールボックスのアーカイブの自動拡張することも上のメールボックスのカスタムのリテンション ・ ポリシーを作成するには保持します。これは、みましょうする保持ポリシーを適用する保留リストに登録されていないメールボックスに適用される既定の MRM ポリシーとは異なる保留中のメールボックスに。これにより、保留中のメールボックス用に設計された保持タグを適用することができます。[回復可能なアイテム] フォルダーに新しい保持タグの作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p106">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold. This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold. This lets you to apply retention tags that are specifically designed for mailboxes on hold. This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="6d5cf-141">このトピックの残りの部分では、保持中のメールボックスのカスタム保存ポリシーを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
<span data-ttu-id="6d5cf-142">[手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="6d5cf-142">[Step 1: Create a custom retention tag for the Recoverable Items folder](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span></span>

<span data-ttu-id="6d5cf-143">[[手順 2: 保留中のメールボックスの新しい保存ポリシーを作成する](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="6d5cf-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="6d5cf-144">手順 3:保持中のメールボックスに新しいアイテム保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="6d5cf-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="6d5cf-145">(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する</span><span class="sxs-lookup"><span data-stu-id="6d5cf-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="6d5cf-146">手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する</span><span class="sxs-lookup"><span data-stu-id="6d5cf-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="6d5cf-p107">最初のステップでは、回復可能なアイテム] フォルダーのカスタム保持期間タグ (RPT の保持ポリシー タグと呼ばれます) を作成します。説明したようは、この RPT は、ユーザーのプライマリ メールボックスの回復可能なアイテム] フォルダーからアイテムをユーザーのアーカイブ メールボックスの回復可能なアイテム] フォルダーに移動します。[回復可能なアイテム] フォルダーに RPT を作成する PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p107">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder. As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox. You have to use PowerShell to create an RPT for the Recoverable Items folder. You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="6d5cf-151">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d5cf-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="6d5cf-152">[回復可能なアイテム] フォルダーの新しい RPT を作成するには、次のコマンドを実行します。 </span><span class="sxs-lookup"><span data-stu-id="6d5cf-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="6d5cf-p108">たとえば、次のコマンドを実行すると、[回復可能なアイテム] フォルダー用に "Recoverable Items 30 days for mailboxes on hold" という名前の RPT が作成され、保持期間が 30 日間に設定されます。これは、アイテムが [回復可能なアイテム] フォルダーに移動されてから 30 日後に、そのアイテムがユーザーのアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されるということです。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="6d5cf-p109">回復可能なアイテム RPT の保存期間 ( _AgeLimitForRetention_パラメーターで定義されている) が RPT を適用するメールボックスの削除済みアイテムの保存期間と同じことをお勧めします。これにより、ユーザー全体の削除済みアイテムの保持期間、アーカイブ メールボックスに移動する前に削除済みアイテムを回復します。前の例では、保存期間は、メールボックスの削除済みアイテムの保存期間は 30 日でもあるという前提に基づいて、30 日に設定されました。既定の 14 日間は、削除済みアイテムを保持する Exchange Online のメールボックスを構成するとします。最大 30 日以内にこの設定を変更することができます。詳細については、 [Exchange オンラインのメールボックスの削除済みアイテムの保存期間の変更](https://go.microsoft.com/fwlink/p/?LinkId=286940)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p109">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to. This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox. In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days. An Exchange Online mailbox is configured to retain deleted items for 14 days, by default. But you can change this setting to a maximum of 30 days. For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="6d5cf-161">手順 2: 保持中のメールボックスの新しいアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6d5cf-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="6d5cf-p110">次の手順では、新しいアイテム保持ポリシーを作成し、そのポリシーに保持タグ (手順 1 で作成した回復可能なアイテムの RPT を含む) を追加します。この新しいポリシーは、次の手順で保持中のメールボックスに適用します。 </span><span class="sxs-lookup"><span data-stu-id="6d5cf-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="6d5cf-p111">新しいアイテム保持ポリシーを作成する前に、追加する保持タグを決定します。Default MRM Policy に追加されている保持タグの一覧、および新しい保持タグを作成する方法については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="6d5cf-166">既定の保持ポリシーでは、Exchange オンライン</span><span class="sxs-lookup"><span data-stu-id="6d5cf-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="6d5cf-167">アイテム保持ポリシー タグをサポートする既定のフォルダー</span><span class="sxs-lookup"><span data-stu-id="6d5cf-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="6d5cf-168">[保持ポリシーの作成](https://go.microsoft.com/fwlink/p/?LinkId=404422)」の「保持タグを作成する」セクションです。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="6d5cf-169">EAC または Exchange のオンライン PowerShell を使用すると、保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="6d5cf-170">EAC を使用してアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6d5cf-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="6d5cf-171">EAC では、**コンプライアンスの管理**に移動\> **・ リテンション ・ ポリシー**の**追加**] をクリックし、![アイコンの追加](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="6d5cf-172">**[新しい保持ポリシー]** ページの **[名前]** に、アイテム保持ポリシーの目的を説明する名前 (例: **MRM Policy for Mailboxes on Hold**) を入力します。 </span><span class="sxs-lookup"><span data-stu-id="6d5cf-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="6d5cf-173">**保持タグ**では、下の [**追加**] をクリックします![アイコンの追加](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-173">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="6d5cf-174">保持タグの一覧で、手順 1 で作成した回復可能なアイテムの RPT を選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![カスタムの [回復可能なアイテム] 保持タグを選択する](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="6d5cf-p112">アイテム保持ポリシーに追加する保持タグを選択します。たとえば、Default MRM Policy に含まれているのと同じタグを追加します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="6d5cf-178">保持タグの追加が完了したら、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="6d5cf-179">**[保存]** をクリックして新しいアイテム保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="6d5cf-180">アイテム保持ポリシーにリンクされている保持タグが詳細ウィンドウに表示されることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![アイテム保持ポリシーにリンクした保持タグが詳細ウィンドウに表示される](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="6d5cf-182">Exchange オンライン PowerShell を使用して、保持ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="6d5cf-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="6d5cf-183">保持中のメールボックスの新しいアイテム保持ポリシーを作成するには、次のコマンドを実行します。 </span><span class="sxs-lookup"><span data-stu-id="6d5cf-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="6d5cf-184">たとえば次のコマンドを実行すると、前の図に示されているアイテム保持ポリシーとそれにリンクされている保持タグが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="6d5cf-185">手順 3:保持中のメールボックスに新しいアイテム保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="6d5cf-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="6d5cf-p113">最後のステップでは、組織内で保留中のメールボックスに手順 2 で作成した新しい保持ポリシーを適用します。EAC または Exchange のオンライン PowerShell を使用するには、メールボックスを 1 つまたは複数のメールボックスに保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p113">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization. You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="6d5cf-188">EAC を使用して新しい保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="6d5cf-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="6d5cf-189">**[受信者]** \> **[メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="6d5cf-190">リスト ビューで、リテンション ・ ポリシーを適用するメールボックスを選択し、し、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="6d5cf-191">**[ユーザー メールボックス]** ページで、**[メールボックスの機能]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="6d5cf-192">**[アイテム保持ポリシー]** から、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="6d5cf-193">EAC を使用して、アイテム保持ポリシーを複数のメールボックスに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="6d5cf-194">**[受信者]** \> **[メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="6d5cf-195">リスト ビューで、Shift キーまたは Ctrl キーを使用して複数のメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="6d5cf-196">詳細ウィンドウで、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="6d5cf-197">**[アイテム保持ポリシー]** 下で **[更新]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="6d5cf-198">**[アイテム保持ポリシーの一括割り当て]** ページで、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="6d5cf-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="6d5cf-199">Exchange オンライン PowerShell を使用して、新しい保持ポリシーを適用するのには</span><span class="sxs-lookup"><span data-stu-id="6d5cf-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="6d5cf-p114">Exchange オンライン PowerShell を使用すると、1 つのメールボックスに新しいアイテム保持ポリシーを適用します。PowerShell の真の力を使えること、1 つのコマンドで、インプレース保持、または証拠保全は、すべてのメールボックスへの新しい保存ポリシーを適用する組織内のメールボックスを保持するすべてを迅速に特定します。Exchange PowerShell を使用する 1 つまたは複数のメールボックスに保持ポリシーを適用するいくつかの例を次に示します。すべての例は、手順 2 で作成した保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p114">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox. But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command. Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes. All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="6d5cf-204">この例では、Pilar Pinilla のメールボックスに新しいアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="6d5cf-205">この例では、組織内の訴訟ホールド中のすべてのメールボックスに新しいアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="6d5cf-206">この例では、組織内のインプレース ホールド中のすべてのメールボックスに新しいアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="6d5cf-207">**Get-Mailbox** コマンドレットを使用すると、新しいアイテム保持ポリシーが適用されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="6d5cf-208">以下は、前の例で実行したコマンドを使用して、"MRM Policy for Mailboxes on Hold" というアイテム保持ポリシーが、訴訟ホールド中のメールボックスとインプレース ホールド中のメールボックスに適用されたことを確認する例です。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="6d5cf-209">(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する</span><span class="sxs-lookup"><span data-stu-id="6d5cf-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="6d5cf-p115">保留中のメールボックスを新しい保存ポリシーを適用すると、かかることが最大 7 日間 Exchange オンライン管理フォルダー アシスタントの新しい保存ポリシーの設定を使用してこれらのメールボックスを処理します。待たず、管理フォルダー アシスタントを実行するのに新しい保持ポリシーを適用したメールボックスを処理するのには、アシスタントを手動で開始するのに**開始 ManagedFolderAssistant**コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p115">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy. Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="6d5cf-212">Pilar Pinilla のメールボックスに対して管理フォルダー アシスタントを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="6d5cf-213">保持中のすべてのメールボックスに対して管理フォルダー アシスタントを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="6d5cf-214">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6d5cf-214">More information</span></span>

- <span data-ttu-id="6d5cf-p116">ユーザーのアーカイブ メールボックスを有効にした後は、(回復可能なアイテム] フォルダー内だけでなくアイテム) は、自分のメールボックス内のアイテムをアーカイブ メールボックスに移動する可能性があることをユーザーに示すことを検討します。これは、Exchange Online のメールボックスに割り当てられている既定の MRM ポリシーには、アイテムがメールボックスに配信されるかによって作成された日付より後の 2 年間アーカイブ メールボックスにアイテムを移動する保持タグ (名前付きの既定の 2 年間は、アーカイブに移動) が含まれているため、ユーザーです。詳細については、 [Exchange のオンラインでの保持ポリシーの既定値](https://go.microsoft.com/fwlink/p/?LinkId=746954)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p116">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox. This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="6d5cf-p117">ユーザーのアーカイブ メールボックスを有効にした後は、回復できることをユーザーのアーカイブ メールボックスの回復可能なアイテム フォルダー内のアイテムを削除するも伝えることがあります。Outlook のアーカイブ先のメールボックスの**削除済みアイテム**フォルダーを選択し、[**ホーム**] タブの [**サーバーから削除済みアイテムの回復**では、ことができます。削除済みアイテムの回復の詳細については、[回復は、Outlook のウィンドウ内の項目を削除](https://go.microsoft.com/fwlink/p/?LinkId=624829)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-p117">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox. They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
