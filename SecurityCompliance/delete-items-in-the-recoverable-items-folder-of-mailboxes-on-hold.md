---
title: クラウドベースのメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除する-管理者向けヘルプ
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: '管理者の場合: Exchange Online メールボックスのユーザーの回復可能なアイテムフォルダーのアイテムを削除します (法的情報保留に設定されている場合も含む)。 これは、Office 365 に誤ってこぼれたデータを削除する効果的な方法です。'
ms.openlocfilehash: a1abfd73d96db6d67e1e1fe13d5487ac55c40344
ms.sourcegitcommit: c0d4fe3e43e22353f30034567ade28330266bcf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900116"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="c0906-104">クラウドベースのメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除する-管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="c0906-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="c0906-105">Exchange Online メールボックスの回復可能なアイテムフォルダーは、偶発的または悪意のある削除から保護するために存在します。</span><span class="sxs-lookup"><span data-stu-id="c0906-105">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="c0906-106">また、保存されていて、Office 365 コンプライアンス機能 (保留や電子情報開示の検索など) によってアクセスされるアイテムを格納するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="c0906-106">It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="c0906-107">ただし、状況によっては、削除する必要のある回復可能なアイテムフォルダーに誤って保持されていたデータが組織に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-107">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="c0906-108">たとえば、ユーザーが気付かないうちに機密情報や情報が含まれる電子メールメッセージを知らずに送信または転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="c0906-108">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="c0906-109">メッセージが完全に削除された場合でも、メールボックスに法的情報保持が設定されているため、無期限に保持される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-109">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="c0906-110">このシナリオは、データが Office 365 に誤って含まれていたため、データ流出と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c0906-110">This scenario is known as data spillage because data has been unintentionally spilled into Office 365.</span></span> <span data-ttu-id="c0906-111">このような状況では、Exchange Online メールボックスのユーザーの回復可能なアイテムフォルダーのアイテムを削除することができます。これは、Office 365 のさまざまな保留機能のいずれかを使用して、そのメールボックスが保持されている場合でも削除できます。</span><span class="sxs-lookup"><span data-stu-id="c0906-111">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="c0906-112">これらの種類には、訴訟ホールド、インプレースホールド、電子情報開示の保持、office 365 セキュリティ&amp;コンプライアンスセンターで作成された office 365 アイテム保持ポリシーなどがあります。</span><span class="sxs-lookup"><span data-stu-id="c0906-112">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the Office 365 Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="c0906-113">この記事では、保留中のクラウドベースのメールボックスの [回復可能なアイテム] フォルダーからアイテムを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0906-113">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="c0906-114">この手順では、メールボックスへのアクセスを無効にし、単一アイテムの回復を無効にし、管理フォルダーアシスタントを無効にして、メールボックスの処理を一時的に解除し、回復可能なアイテムフォルダーからアイテムを削除してから、元に戻す必要があります。メールボックスを以前の構成に設定します。</span><span class="sxs-lookup"><span data-stu-id="c0906-114">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="c0906-115">プロセスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c0906-115">Here's the process:</span></span> 
  
[<span data-ttu-id="c0906-116">手順 1: メールボックスに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="c0906-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="c0906-117">手順 2: メールボックスを準備する</span><span class="sxs-lookup"><span data-stu-id="c0906-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="c0906-118">手順 3: メールボックスからすべての保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="c0906-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="c0906-119">手順 4: メールボックスから遅延保持を削除する</span><span class="sxs-lookup"><span data-stu-id="c0906-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="c0906-120">手順 5: 回復可能なアイテムフォルダーのアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="c0906-120">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="c0906-121">手順 6: メールボックスを以前の状態に戻す</span><span class="sxs-lookup"><span data-stu-id="c0906-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="c0906-122">この記事に記載されている手順により、Exchange Online メールボックスからデータが完全に削除 (パージ) されます。</span><span class="sxs-lookup"><span data-stu-id="c0906-122">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="c0906-123">これは、回復可能なアイテムフォルダーから削除されたメッセージを回復できず、法的証拠開示やその他の法令遵守のために利用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c0906-123">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="c0906-124">office 365 セキュリティ&amp;コンプライアンスセンターで作成された訴訟ホールド、インプレースホールド、電子情報開示のホールド、または office 365 アイテム保持ポリシーの一部として保留になっているメールボックスからのメッセージを削除する場合は、レコード管理または法務に確認してください。保持を削除する前の部署。</span><span class="sxs-lookup"><span data-stu-id="c0906-124">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the Office 365 Security &amp; Compliance Center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="c0906-125">組織には、保留中のメールボックスとデータ流出インシデントのどちらを優先するかを定義するポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="c0906-125">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c0906-126">はじめに</span><span class="sxs-lookup"><span data-stu-id="c0906-126">Before you begin</span></span>

- <span data-ttu-id="c0906-127">手順5で [回復可能なアイテム] フォルダーからメッセージを検索して削除するには、Exchange Online の次の両方の管理役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-127">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 5.</span></span>
    
  - <span data-ttu-id="c0906-128">**メールボックス検索**-この役割を使用すると、組織内のメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c0906-128">**Mailbox Search** - This role lets you to search mailboxes in your organization.</span></span> <span data-ttu-id="c0906-129">既定では、Exchange 管理者はこの役割を割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="c0906-129">Exchange administrators aren't assigned this role by default.</span></span> <span data-ttu-id="c0906-130">この役割を自分自身に割り当てるには、Exchange Online の "Discovery Management/検出の管理" 役割グループのメンバーとして自分自身を追加します。</span><span class="sxs-lookup"><span data-stu-id="c0906-130">To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="c0906-131">**メールボックスインポートエクスポート**-この役割を使用すると、ユーザーのメールボックスからメッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c0906-131">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox.</span></span> <span data-ttu-id="c0906-132">既定では、この役割はどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="c0906-132">By default, this role isn't assigned to any role group.</span></span> <span data-ttu-id="c0906-133">ユーザーのメールボックスからメッセージを削除するには、Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加します。</span><span class="sxs-lookup"><span data-stu-id="c0906-133">To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="c0906-134">この記事で説明する手順は、非アクティブなメールボックスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c0906-134">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="c0906-135">これは、削除した後、非アクティブなメールボックスに保留 (または Office 365 アイテム保持ポリシー) を再適用できないためです。</span><span class="sxs-lookup"><span data-stu-id="c0906-135">That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="c0906-136">非アクティブなメールボックスからホールドを削除すると、その保留中のメールボックスは通常の回復可能な削除によって削除され、管理フォルダーアシスタントによる処理後は組織から完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c0906-136">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="c0906-137">保持ロックでロックされている Office 365 アイテム保持ポリシーに割り当てられているメールボックスに対して、この手順を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0906-137">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock.</span></span> <span data-ttu-id="c0906-138">これは、保持ロックによって、Office 365 アイテム保持ポリシーからメールボックスを削除または除外したり、メールボックス上の管理フォルダーアシスタントを無効にしたりすることができないためです。</span><span class="sxs-lookup"><span data-stu-id="c0906-138">That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="c0906-139">保持ポリシーのロックの詳細については、「[アイテム保持ポリシーのロック](retention-policies.md#locking-a-retention-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-139">For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="c0906-140">メールボックスが保持されていない (または単一アイテムの回復が有効になっていない) 場合は、単に回復可能なアイテムフォルダーからアイテムを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c0906-140">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="c0906-141">これを行う方法の詳細については、「[メッセージを検索して削除](https://go.microsoft.com/fwlink/?linkid=852453)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-141">For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="c0906-142">手順 1: メールボックスに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="c0906-142">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="c0906-143">最初の手順では、この手順に影響する、ターゲットメールボックスから選択したプロパティを収集します。</span><span class="sxs-lookup"><span data-stu-id="c0906-143">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="c0906-144">これらのプロパティの一部を変更し、[回復可能なアイテム] フォルダーからアイテムを削除した後に、手順6で元の値に戻すことができるように、これらの設定を書き留めておくか、テキストファイルに保存してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-144">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="c0906-145">収集する必要があるメールボックスのプロパティの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c0906-145">Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="c0906-146">*singleitemrecoveryenabled*および*RetainDeletedItemsFor* ;必要に応じて、1回の回復を無効にして、手順3で削除済みアイテムの保存期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="c0906-146">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="c0906-147">*LitigationHoldEnabled*および*InPlaceHolds* ;手順3で一時的に削除できるように、メールボックスに配置されているすべての保留リストを識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-147">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="c0906-148">メールボックスに配置される可能性のある型保持を特定する方法については、「[詳細情報](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-148">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="c0906-149">また、この手順の実行中に所有者 (または他のユーザー) がメールボックスにアクセスできないように、メールボックスクライアントアクセスの設定を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-149">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="c0906-150">最後に、[回復可能なアイテム] フォルダー内のアイテムの現在のサイズと数を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c0906-150">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="c0906-151">手順5で [回復可能なアイテム] フォルダー内のアイテムを削除した後、この情報を使用してアイテムが実際に削除されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0906-151">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="c0906-152">[Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="c0906-152">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="c0906-153">Exchange Online で適切な管理役割が割り当てられている管理者アカウントには、必ずユーザー名とパスワードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-153">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="c0906-154">単一アイテムの回復と削除済みアイテムの保存期間に関する情報を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-154">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="c0906-155">単一アイテムの回復が有効になっている場合は、手順2で無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-155">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="c0906-156">削除済みアイテムの保存期間が30日間 (Exchange Online の最大値) に設定されていない場合は、手順2で増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="c0906-156">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="c0906-157">次のコマンドを実行して、メールボックスのメールボックスアクセス設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0906-157">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="c0906-158">手順2では、これらのアクセス方法をすべて無効にします。</span><span class="sxs-lookup"><span data-stu-id="c0906-158">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="c0906-159">次のコマンドを実行して、メールボックスに適用されている保留リストと Office 365 アイテム保持ポリシーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0906-159">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="c0906-160">*InPlaceHolds*プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行してそれぞれの値を別々の行に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c0906-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="c0906-161">組織全体の Office 365 保持ポリシーに関する情報を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-161">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="c0906-162">組織全体で Office 365 のアイテム保持ポリシーを使用している場合は、手順3でこれらのポリシーからメールボックスを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-162">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="c0906-163">*InPlaceHolds*プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行してそれぞれの値を別々の行に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c0906-163">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="c0906-164">次のコマンドを実行して、ユーザーのプライマリメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0906-164">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="c0906-165">ユーザーのアーカイブメールボックスが有効になっている場合は、次のコマンドを実行して、アーカイブメールボックス内の [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0906-165">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="c0906-166">手順5でアイテムを削除する場合、ユーザーのプライマリアーカイブメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除するか、削除するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c0906-166">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="c0906-167">メールボックスに対して自動拡張アーカイブが有効になっている場合、補助アーカイブメールボックス内のアイテムは削除されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-167">Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="c0906-168">手順 2: メールボックスを準備する</span><span class="sxs-lookup"><span data-stu-id="c0906-168">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="c0906-169">メールボックスに関する情報を収集して保存した後、次の手順では、次のタスクを実行してメールボックスを準備します。</span><span class="sxs-lookup"><span data-stu-id="c0906-169">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="c0906-170">メールボックス**へのクライアントアクセスを無効**にして、メールボックスの所有者がメールボックスにアクセスできないようにして、この手順の実行中にメールボックスデータを変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="c0906-170">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="c0906-171">**削除済みアイテムの保存期間**を30日間 (Exchange Online の最大値) に増やして、手順5でアイテムを回復可能なアイテムフォルダーから削除されないようにします。</span><span class="sxs-lookup"><span data-stu-id="c0906-171">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="c0906-172">手順5で [回復可能なアイテム] フォルダーからアイテムを削除した後に、アイテムが保持されないように、**単一アイテムの回復を無効**にします (削除済みアイテムの保存期間中)。</span><span class="sxs-lookup"><span data-stu-id="c0906-172">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="c0906-173">**管理フォルダーアシスタントを無効**にして、メールボックスが処理されず、手順5で削除されたアイテムを保持するようにします。</span><span class="sxs-lookup"><span data-stu-id="c0906-173">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="c0906-174">Exchange Online PowerShell で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-174">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="c0906-175">次のコマンドを実行して、メールボックスへのすべてのクライアントアクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c0906-175">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="c0906-176">コマンド構文では、すべてのクライアントアクセスメソッドがメールボックスで有効になっていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c0906-176">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="c0906-177">メールボックスへのすべてのクライアントアクセス方法を無効にするには、最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-177">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="c0906-178">これらのアクセス方法を無効にしても、現在サインインしているメールボックスの所有者が切断されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-178">Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in.</span></span> <span data-ttu-id="c0906-179">所有者がサインインしていない場合、これらのアクセス方法を無効にした後はメールボックスにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="c0906-179">If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="c0906-180">次のコマンドを実行して、削除済みアイテムの保存期間を最大で30日に増やします。</span><span class="sxs-lookup"><span data-stu-id="c0906-180">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="c0906-181">これは、現在の設定が30日未満であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c0906-181">This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="c0906-182">次のコマンドを実行して、単一アイテムの回復を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c0906-182">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="c0906-183">単一アイテムの回復を無効にするには、最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-183">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="c0906-184">この期間が経過するまで、[回復可能なアイテム] フォルダー内のアイテムを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="c0906-184">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="c0906-185">管理フォルダーアシスタントがメールボックスを処理できないようにするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-185">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="c0906-186">前述したように、保持ロックが設定された Office 365 アイテム保持ポリシーがメールボックスに適用されていない場合にのみ、管理フォルダーアシスタントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c0906-186">As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="c0906-187">手順 3: メールボックスからすべての保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="c0906-187">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="c0906-188">回復可能なアイテムフォルダーからアイテムを削除する前の最後の手順は、メールボックスに配置されたすべてのホールド (手順1で特定した) を削除することです。</span><span class="sxs-lookup"><span data-stu-id="c0906-188">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="c0906-189">[回復可能なアイテム] フォルダーからアイテムを削除した後は、アイテムが保持されないように、すべての保留リストを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-189">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="c0906-190">次のセクションでは、メールボックスにさまざまな種類の保留リストを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0906-190">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="c0906-191">メールボックスに配置される可能性のある型保持を特定する方法については、「[詳細情報](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-191">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="c0906-192">詳細については、「 [Exchange Online メールボックスに配置されたホールドの種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-192">For additional information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c0906-193">前述したように、メールボックスから保留リストを削除する前に、レコード管理または法務部門に確認してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-193">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="c0906-194">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="c0906-194">Litigation Hold</span></span>
  
<span data-ttu-id="c0906-195">Exchange Online PowerShell で次のコマンドを実行して、メールボックスから訴訟ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0906-195">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="c0906-196">クライアントアクセス方法と単一アイテムの回復を無効にする場合と同様に、訴訟ホールドを削除するには最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-196">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="c0906-197">この期間が経過するまで、[回復可能なアイテム] フォルダーからアイテムを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="c0906-197">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="c0906-198">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="c0906-198">In-Place Hold</span></span>
  
<span data-ttu-id="c0906-199">Exchange Online PowerShell で次のコマンドを実行して、メールボックスに配置されているインプレースホールドを識別します。</span><span class="sxs-lookup"><span data-stu-id="c0906-199">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="c0906-200">手順1で特定したインプレースホールドの GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0906-200">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="c0906-201">インプレースホールドを識別した後、exchange 管理センター (EAC) または exchange Online PowerShell を使用して、保留リストからメールボックスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c0906-201">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="c0906-202">詳細については、「[インプレース保持を作成または削除する](https://go.microsoft.com/fwlink/?linkid=852668)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-202">For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="c0906-203">特定のメールボックスに適用される Office 365 アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="c0906-203">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="c0906-204">[office 365 セキュリティ&amp;コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、メールボックスに適用されている office 365 アイテム保持ポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="c0906-204">Run the following command in [Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="c0906-205">手順1で特定したアイテム`mbx`保持`skp`ポリシーの GUID (またはプレフィックスを含まない) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0906-205">Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="c0906-206">アイテム\*\*\*\* 保持ポリシーを特定した後、セキュリティ&amp;コンプライアンスセンターの [ガバナンス\>の**日付**] ページに移動し、前の手順で識別したアイテム保持ポリシーを編集します。また、リストからメールボックスを削除するには、アイテム保持ポリシーに含まれている受信者。</span><span class="sxs-lookup"><span data-stu-id="c0906-206">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="c0906-207">組織全体の Office 365 のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="c0906-207">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="c0906-208">組織全体および Exchange 全体の Office 365 保持ポリシーは、組織内のすべてのメールボックスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c0906-208">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="c0906-209">これらは、(メールボックスレベルではなく) 組織レベルで適用され、手順1で取得した組織レベルの**config**コマンドレットを実行したときに返されます。</span><span class="sxs-lookup"><span data-stu-id="c0906-209">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="c0906-210">[セキュリティ&amp;コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、組織全体の Office 365 保持ポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="c0906-210">Run the following command in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="c0906-211">手順1で特定した組織`mbx`全体のアイテム保持ポリシーの GUID (プレフィックスを含まない) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0906-211">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="c0906-212">組織全体\*\*\*\* の Office 365 アイテム保持ポリシーを特定した後、セキュリティ&amp;コンプライアンスセンターの [ガバナンス\>の**日付**] ページに移動して、組織全体のアイテム保持ポリシーを編集します。前の手順を実行し、除外された受信者のリストにメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="c0906-212">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="c0906-213">この操作を行うと、ユーザーのメールボックスがアイテム保持ポリシーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c0906-213">Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="office-365-retention-labels"></a><span data-ttu-id="c0906-214">Office 365 保持ラベル</span><span class="sxs-lookup"><span data-stu-id="c0906-214">Office 365 retention labels</span></span>

<span data-ttu-id="c0906-215">ユーザーがコンテンツを保持するように設定されているラベルを適用するか、メールボックス内のフォルダーまたはアイテムを保持した後にコンテンツを削除すると、 *ComplianceTagHoldApplied* mailbox プロパティが**True**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c0906-215">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="c0906-216">このような場合、メールボックスは、訴訟ホールドの対象として、または Office 365 アイテム保持ポリシーに割り当てられているかのように、保留中であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="c0906-216">When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span>

<span data-ttu-id="c0906-217">*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-217">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="c0906-218">フォルダーまたはアイテムに保持ラベルが適用されているためにメールボックスが保留になっていることを確認した後、Security & コンプライアンスセンターのコンテンツ検索ツールを使用して、ComplianceTag の検索条件を使用してラベル付けされたアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c0906-218">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the Security & Compliance Center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="c0906-219">詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)」の「検索条件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-219">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="c0906-220">ラベルの詳細については、「 [Office 365 ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-220">For more information about labels, see [Overview of Office 365 labels](labels.md).</span></span>

 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="c0906-221">電子情報開示ケースの保持</span><span class="sxs-lookup"><span data-stu-id="c0906-221">eDiscovery case holds</span></span>
  
<span data-ttu-id="c0906-222">[セキュリティ&amp;コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、メールボックスに適用される電子情報開示ケースに関連付けられている保留リストを識別します。</span><span class="sxs-lookup"><span data-stu-id="c0906-222">Run the following commands in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox.</span></span> <span data-ttu-id="c0906-223">手順1で特定した電子`UniH`情報開示ホールドの GUID (プレフィックスを含まない) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0906-223">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="c0906-224">2番目のコマンドには、保留が関連付けられている電子情報開示ケースの名前が表示されることに注意してください。3番目のコマンドは、保留の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0906-224">Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="c0906-225">電子情報開示のケースとホールドの名前を特定したら、セキュリティ&amp;コンプライアンスセンターの [**検索&amp;調査** \>用**電子情報開示**] ページに移動し、ケースを開き、保留リストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0906-225">After you've identified the name of the eDiscovery case and the hold, go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="c0906-226">詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のケースを管理する](manage-ediscovery-cases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-226">For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="c0906-227">手順 4: メールボックスから遅延保持を削除する</span><span class="sxs-lookup"><span data-stu-id="c0906-227">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="c0906-228">メールボックスから何らかの種類の保留が解除されると、 *DelayHoldApplied* mailbox プロパティの値は**True**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c0906-228">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="c0906-229">これは、管理フォルダーアシスタントが次回メールボックスを処理し、ホールドが削除されたことを検出したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="c0906-229">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="c0906-230">これは*遅延ホールド*と呼ばれ、データがメールボックスから完全に削除されないようにするために、保留リストの実際の削除が30日間延期されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c0906-230">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="c0906-231">(遅延保持の目的は、保留が解除された後に削除されるメールボックスアイテムを、管理者が検索または復旧する機会を管理者に提供することです)。 メールボックスに遅延保持が設定されている場合でも、メールボックスが訴訟ホールドの対象であったかのように、無期限に保持されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="c0906-231">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="c0906-232">30日後、遅延保持が有効期限切れになり、Office 365 は遅延保持を自動的に削除します ( *DelayHoldApplied*プロパティを**False**に設定する)。保留が実際に削除されるようにします。</span><span class="sxs-lookup"><span data-stu-id="c0906-232">After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold is actually removed.</span></span> 

<span data-ttu-id="c0906-233">手順5でアイテムを削除する前に、メールボックスから遅延ホールドを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-233">Before you can delete items in Step 5, you have to remove the delay hold from the mailbox.</span></span> <span data-ttu-id="c0906-234">最初に、Exchange Online PowerShell で次のコマンドを実行して、遅延保持がメールボックスに適用されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c0906-234">First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="c0906-235">*DelayHoldApplied*プロパティの値が**False**に設定されている場合、遅延保持はメールボックスに配置されていません。</span><span class="sxs-lookup"><span data-stu-id="c0906-235">If the value of the *DelayHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox.</span></span> <span data-ttu-id="c0906-236">[回復可能なアイテム] フォルダー内のアイテムを削除するには、手順5に進みます。</span><span class="sxs-lookup"><span data-stu-id="c0906-236">You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="c0906-237">*DelayHoldApplied*プロパティの値が**True**に設定されている場合は、次のコマンドを実行して遅延保持を削除します。</span><span class="sxs-lookup"><span data-stu-id="c0906-237">If the value of the *DelayHoldApplied* property is set to **True**, run the following command to remove the delay hold:</span></span>

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="c0906-238">*RemoveDelayHoldApplied*パラメーターを使用するには、Exchange Online で法的情報保留の役割が割り当てられている必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-238">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="c0906-239">手順 5: 回復可能なアイテムフォルダーのアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="c0906-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="c0906-240">これで、Exchange Online の PowerShell で[検索-メールボックス](https://go.microsoft.com/fwlink/?linkid=852595)コマンドレットを使用して、回復可能なアイテムフォルダーのアイテムを実際に削除する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="c0906-240">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="c0906-241">**検索-メールボックス**コマンドレットを実行すると、次の3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c0906-241">You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="c0906-242">アイテムを削除する前に、対象のメールボックスにコピーしてから、必要に応じて削除する前にアイテムを確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c0906-242">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="c0906-243">アイテムをターゲットメールボックスにコピーし、同じコマンドで削除します。</span><span class="sxs-lookup"><span data-stu-id="c0906-243">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="c0906-244">ターゲットメールボックスにコピーせずにアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0906-244">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="c0906-245">ユーザーのプライマリアーカイブメールボックスの [回復可能なアイテム] フォルダー内のアイテムは、**検索-メールボックス**コマンドレットを実行したときにも削除されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-245">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="c0906-246">これを防ぐために、  *DoNotIncludeArchive*  スイッチを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c0906-246">To prevent this, you can include the  *DoNotIncludeArchive*  switch.</span></span> <span data-ttu-id="c0906-247">前述したように、メールボックスの自動拡張アーカイブが有効になっている場合、\* \* 検索-メールボックス \* \* コマンドレットは補助アーカイブメールボックス内のアイテムを削除しません。</span><span class="sxs-lookup"><span data-stu-id="c0906-247">And as previously stated, if auto-expanding archiving is enabled for the mailbox, the \*\* Search-Mailbox \*\* cmdlet doesn't deleted items in an auxiliary archive mailbox.</span></span> <span data-ttu-id="c0906-248">自動拡張アーカイブの詳細については、「 [Office 365 の無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-248">For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0906-p137">( *SearchQuery*  パラメーターを使用していて) 検索クエリが含まれている場合、 **Search-Mailbox** コマンドレットは、検索結果で最大 10,000 個のアイテムを返します。したがって、検索クエリを含める場合は、 **Search-Mailbox** コマンドを複数回実行して 10,000 を超えるアイテムを削除する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="c0906-p137">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="c0906-251">次の例は、これらの各オプションのコマンド構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="c0906-251">The following examples show the command syntax for each of these options.</span></span> <span data-ttu-id="c0906-252">これらの例で`-SearchQuery size>0`は、パラメーター値を使用して、回復可能なアイテムフォルダー内のすべてのサブフォルダーからすべてのアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0906-252">These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder.</span></span> <span data-ttu-id="c0906-253">特定の条件に一致するアイテムのみを削除する必要がある場合は、 *searchquery*パラメーターを使用して、メッセージの件名、日付の範囲など、他の条件を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0906-253">If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range.</span></span> <span data-ttu-id="c0906-254">[その他の searchquery パラメーターの使用例](#other-examples-of-using-the-searchquery-parameter)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-254">See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="c0906-255">例 1</span><span class="sxs-lookup"><span data-stu-id="c0906-255">Example 1</span></span>

<span data-ttu-id="c0906-256">この例では、ユーザーの回復可能なアイテムフォルダー内のすべてのアイテムを組織の探索検索メールボックス内のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c0906-256">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox.</span></span> <span data-ttu-id="c0906-257">これにより、アイテムを完全に削除する前に確認することができます。</span><span class="sxs-lookup"><span data-stu-id="c0906-257">This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="c0906-258">前の例では、アイテムを探索検索メールボックスにコピーする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c0906-258">In the previous example, it isn't required to copy items to the Discovery Search Mailbox.</span></span> <span data-ttu-id="c0906-259">任意のターゲットメールボックスにメッセージをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="c0906-259">You can copy messages to any target mailbox.</span></span> <span data-ttu-id="c0906-260">ただし、機密性の高いメールボックスデータにアクセスできないようにするには、権限のある人物にアクセスが制限されたメールボックスにメッセージをコピーすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0906-260">However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel.</span></span> <span data-ttu-id="c0906-261">既定では、既定の探索検索メールボックスへのアクセスは、Exchange Online の "discovery Management/検出の管理" 役割グループのメンバーに制限されています。</span><span class="sxs-lookup"><span data-stu-id="c0906-261">By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="c0906-262">例 2</span><span class="sxs-lookup"><span data-stu-id="c0906-262">Example 2</span></span>

<span data-ttu-id="c0906-263">この例では、ユーザーの回復可能なアイテムフォルダー内のすべてのアイテムを組織の探索検索メールボックス内のフォルダーにコピーし、ユーザーの回復可能なアイテムフォルダーからアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0906-263">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="c0906-264">例 3</span><span class="sxs-lookup"><span data-stu-id="c0906-264">Example 3</span></span>

<span data-ttu-id="c0906-265">この例では、ユーザーの回復可能なアイテムフォルダー内のすべてのアイテムをターゲットメールボックスにコピーせずに削除します。</span><span class="sxs-lookup"><span data-stu-id="c0906-265">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="c0906-266">searchquery パラメーターを使用する他の例</span><span class="sxs-lookup"><span data-stu-id="c0906-266">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="c0906-267">次に、 *searchquery*パラメーターを使用して特定のメッセージを検索する例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="c0906-267">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages.</span></span> <span data-ttu-id="c0906-268">*searchquery*パラメーターを使用して特定のアイテムを検索する場合は、検索結果を確認し、必要に応じてクエリを修正してから検索結果を削除することができるように、検索結果をターゲットメールボックスにコピーすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-268">If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="c0906-269">この例では、[件名] フィールドに特定の語句が含まれるメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="c0906-269">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="c0906-270">この例では、指定した日付範囲内に送信されたメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="c0906-270">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="c0906-271">この例では、指定したユーザーに送信されたメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="c0906-271">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="c0906-272">アイテムが削除されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="c0906-272">Verify that items were deleted</span></span>

<span data-ttu-id="c0906-273">メールボックスの [回復可能なアイテム] フォルダーからアイテムが正常に削除されたことを確認するには、Exchange Online PowerShell で**get-mailboxfolderstatistics**コマンドレットを使用して、回復可能なアイテムフォルダー内のアイテムのサイズと数を確認します。</span><span class="sxs-lookup"><span data-stu-id="c0906-273">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="c0906-274">これらの統計情報は、手順1で収集したものと比較できます。</span><span class="sxs-lookup"><span data-stu-id="c0906-274">You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="c0906-275">で次のコマンドを実行して、ユーザーのプライマリメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0906-275">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="c0906-276">次のコマンドを実行して、ユーザーのアーカイブメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0906-276">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="c0906-277">手順 6: メールボックスを以前の状態に戻す</span><span class="sxs-lookup"><span data-stu-id="c0906-277">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="c0906-278">最後の手順では、メールボックスを以前の構成に戻します。</span><span class="sxs-lookup"><span data-stu-id="c0906-278">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="c0906-279">これは、手順2で変更したプロパティをリセットし、手順3で削除した保留リストを再適用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="c0906-279">This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3.</span></span> <span data-ttu-id="c0906-280">これには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0906-280">This includes:</span></span>
  
- <span data-ttu-id="c0906-281">削除済みアイテムの保存期間を以前の値に戻します。</span><span class="sxs-lookup"><span data-stu-id="c0906-281">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="c0906-282">または、Exchange Online の最大値の30日間に設定しておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="c0906-282">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="c0906-283">単一アイテムの回復を再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="c0906-283">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="c0906-284">所有者が自分のメールボックスにアクセスできるように、クライアントアクセス方法を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="c0906-284">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="c0906-285">削除した保留リストと Office 365 アイテム保持ポリシーを再適用します。</span><span class="sxs-lookup"><span data-stu-id="c0906-285">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="c0906-286">管理フォルダーアシスタントを再度有効にして、メールボックスを処理します。</span><span class="sxs-lookup"><span data-stu-id="c0906-286">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="c0906-287">管理フォルダーアシスタントを再度有効にしてメールボックスを処理する前に、保持ポリシーまたは Office 365 アイテム保持ポリシーを再適用してから24時間待機することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0906-287">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="c0906-288">Exchange Online PowerShell で次の手順を実行します (指定された順序で)。</span><span class="sxs-lookup"><span data-stu-id="c0906-288">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="c0906-289">削除済みアイテムの保存期間を元の値に戻すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-289">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="c0906-290">これは、前の設定が30日未満であることを前提としています。たとえば、14日間。</span><span class="sxs-lookup"><span data-stu-id="c0906-290">This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="c0906-291">単一アイテムの回復を再び有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-291">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="c0906-292">次のコマンドを実行して、すべてのクライアントアクセス方法をメールボックスに再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="c0906-292">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="c0906-293">手順3で削除した保留を再度適用します。</span><span class="sxs-lookup"><span data-stu-id="c0906-293">Re-apply the holds that you removed in Step 3.</span></span> <span data-ttu-id="c0906-294">保留の種類に応じて、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0906-294">Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="c0906-295">**訴訟ホールド**</span><span class="sxs-lookup"><span data-stu-id="c0906-295">**Litigation Hold**</span></span>
    
    <span data-ttu-id="c0906-296">メールボックスの訴訟ホールドを再び有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-296">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="c0906-297">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="c0906-297">**In-Place Hold**</span></span>
    
    <span data-ttu-id="c0906-298">EAC (または Exchange Online PowerShell) を使用して、メールボックスをインプレース保持に戻します。</span><span class="sxs-lookup"><span data-stu-id="c0906-298">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="c0906-299">**特定のメールボックスに適用される Office 365 アイテム保持ポリシー**</span><span class="sxs-lookup"><span data-stu-id="c0906-299">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="c0906-300">セキュリティ&amp; /コンプライアンスセンターを使用して、メールボックスを Office 365 アイテム保持ポリシーに戻します。</span><span class="sxs-lookup"><span data-stu-id="c0906-300">Use the Security &amp; Compliance Center to add the mailbox back to the Office 365 retention policy.</span></span> <span data-ttu-id="c0906-301">セキュリティ&amp; /コンプライアンスセンターの [**ガバナンス** \> **保持期間**] ページに移動し、アイテム保持ポリシーを編集して、アイテム保持ポリシーが適用されている受信者のリストにメールボックスを追加し直します。</span><span class="sxs-lookup"><span data-stu-id="c0906-301">Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="c0906-302">**組織全体の Office 365 のアイテム保持ポリシー**</span><span class="sxs-lookup"><span data-stu-id="c0906-302">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="c0906-303">組織全体または Exchange 全体のアイテム保持ポリシーをポリシーから除外して削除した場合は、セキュリティ&amp;コンプライアンスセンターを使用して、除外するユーザーのリストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0906-303">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security &amp; Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="c0906-304">セキュリティ&amp; /コンプライアンスセンターの [**ガバナンス** \> **保持**期間] ページに移動し、組織全体のアイテム保持ポリシーを編集して、除外された受信者のリストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0906-304">Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="c0906-305">これを行うと、ユーザーのメールボックスにアイテム保持ポリシーが再適用されます。</span><span class="sxs-lookup"><span data-stu-id="c0906-305">Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="c0906-306">**電子情報開示ケースの保持**</span><span class="sxs-lookup"><span data-stu-id="c0906-306">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="c0906-307">セキュリティ&amp; /コンプライアンスセンターを使用して、電子情報開示ケースに関連付けられている保留リストにメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="c0906-307">Use the Security &amp; Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="c0906-308">セキュリティ&amp; /コンプライアンスセンターの [**検索&amp;調査** \>用**電子情報開示**] ページに移動し、ケースを開き、メールボックスを保持に戻します。</span><span class="sxs-lookup"><span data-stu-id="c0906-308">Go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="c0906-309">管理フォルダーアシスタントがメールボックスを再度処理できるようにするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-309">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="c0906-310">前述したように、管理フォルダーアシスタントを再度有効にする前に、保留リストまたは Office 365 アイテム保持ポリシーを再適用してから24時間待ってから再開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0906-310">As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="c0906-311">メールボックスが以前の構成に戻されたことを確認するには、次のコマンドを実行し、設定を手順1で収集したものと比較します。</span><span class="sxs-lookup"><span data-stu-id="c0906-311">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="c0906-312">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c0906-312">More information</span></span>

<span data-ttu-id="c0906-313">次の表は、 *InPlaceHolds*プロパティの値に基づいて、**メールボックスの取得**または取得、または**取得-組織の構成**のコマンドレットを実行した場合に、さまざまな種類の保留を識別する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c0906-313">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="c0906-314">詳細については、「 [Exchange Online メールボックスに配置されたホールドの種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-314">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="c0906-315">前述のとおり、[回復可能なアイテム] フォルダー内のアイテムを正常に削除する前に、すべてのホールドポリシーと Office 365 アイテム保持ポリシーをメールボックスから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-315">As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="c0906-316">**ホールドの種類**</span><span class="sxs-lookup"><span data-stu-id="c0906-316">**Hold type**</span></span>|<span data-ttu-id="c0906-317">**値の例**</span><span class="sxs-lookup"><span data-stu-id="c0906-317">**Example value**</span></span>|<span data-ttu-id="c0906-318">**保留リストを識別する方法**</span><span class="sxs-lookup"><span data-stu-id="c0906-318">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0906-319">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="c0906-319">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="c0906-320">*LitigationHoldEnabled*  プロパティが  `True` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c0906-320">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="c0906-321">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="c0906-321">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="c0906-322">*InPlaceHolds*プロパティには、メールボックスに配置されたインプレースホールドの GUID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0906-322">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="c0906-323">GUID はプレフィックスで始まっていないため、これはインプレースホールドであることを伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="c0906-323">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="c0906-324">Exchange Online の PowerShell `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`でコマンドを使用して、メールボックスのインプレース保持に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c0906-324">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="c0906-325">特定のメールボックスに適用さ&amp;れるセキュリティコンプライアンスセンターの Office 365 アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="c0906-325">Office 365 retention policies in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="c0906-326">または</span><span class="sxs-lookup"><span data-stu-id="c0906-326">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="c0906-327">**メールボックスの取得**コマンドレットを実行すると、 *InPlaceHolds*プロパティには、メールボックスに適用されている Office 365 アイテム保持ポリシーの guid も含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0906-327">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox.</span></span> <span data-ttu-id="c0906-328">GUID が`mbx`プレフィックスで始まっているため、アイテム保持ポリシーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="c0906-328">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="c0906-329">アイテム保持ポリシーの GUID が`skp`プレフィックスで始まっている場合は、アイテム保持ポリシーが Skype for business の会話に適用されることを示すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-329">Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="c0906-330">メールボックスに適用されている Office 365 アイテム保持ポリシーを識別するには、セキュリティ&amp;コンプライアンスセンターの PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-330">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="c0906-331">このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-331">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="c0906-332">セキュリティ&amp; /コンプライアンスセンターの組織全体にわたる Office 365 のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="c0906-332">Organization-wide Office 365 retention policies in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="c0906-333">値なし</span><span class="sxs-lookup"><span data-stu-id="c0906-333">No value</span></span>  <br/> <span data-ttu-id="c0906-334">または</span><span class="sxs-lookup"><span data-stu-id="c0906-334">or</span></span>  <br/>  <span data-ttu-id="c0906-335">`-mbxe9b52bf7ab3b46a286308ecb29624696`(メールボックスが組織全体のポリシーから除外されていることを示します)</span><span class="sxs-lookup"><span data-stu-id="c0906-335">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="c0906-336">InPlaceHolds コマンドレットの実行時に\*\* プロパティが空\*\*\*\* の場合でも、メールボックスに適用されている組織全体の Office 365 保持ポリシーが1つ以上存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0906-336">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="c0906-337">このことを確認するには、 `Get-OrganizationConfig | FL InPlaceHolds` Exchange Online PowerShell でコマンドを実行して、組織全体の Office 365 アイテム保持ポリシーの guid の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0906-337">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="c0906-338">Exchange メールボックスに適用される組織全体のアイテム保持ポリシーの GUID `mbx`は、接頭辞で始まります。例`mbxa3056bb15562480fadb46ce523ff7b02`を示します。</span><span class="sxs-lookup"><span data-stu-id="c0906-338">The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="c0906-339">メールボックスに適用されている組織全体の Office 365 アイテム保持ポリシーを識別するには、セキュリティ&amp;コンプライアンスセンターの PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-339">To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="c0906-340">メールボックスが組織全体の Office 365 アイテム保持ポリシーから除外されている場合は、**メールボックス取得**コマンドレットを実行すると、ユーザーのメールボックスの*InPlaceHolds*プロパティにアイテム保持ポリシーの GUID が表示されることに注意してください。プレフィックス`-mbx`によって識別されます。例えば`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="c0906-340">Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="c0906-341">eDiscovery case hold in the Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="c0906-341">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="c0906-342">*InPlaceHolds*プロパティには、メールボックスに配置される可能性がある、セキュリティ&amp;センターの電子情報開示ケースに関連付けられた保留の GUID も含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0906-342">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security &amp; Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="c0906-343">GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="c0906-343">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="c0906-344">セキュリティ&amp;コンプライアンスセンターの`Get-CaseHoldPolicy` PowerShell でコマンドレットを使用すると、メールボックスの保留リストに関連付けられている電子情報開示ケースに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c0906-344">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="c0906-345">たとえば、コマンド`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`を実行して、メールボックスにあるケースホールドの名前を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c0906-345">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="c0906-346">Be sure to remove the  `UniH` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="c0906-346">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="c0906-347">メールボックスの保留リストが関連付けられている電子情報開示ケースを識別するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0906-347">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


