---
title: 管理者ヘルプの保留中のクラウド ベースのメールボックスの回復可能なアイテム] フォルダー内の項目を削除します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: '管理者: 法的保存要件にそのメールボックスが配置された場合でも、Exchange Online のメールボックスに対するユーザーの回復可能なアイテム] フォルダー内の項目を削除します。これは、データが誤ってこぼした Office 365 にするを削除するのには効果的な方法です。'
ms.openlocfilehash: a10965ad088da98b4e4d84d823c124e5b192d505
ms.sourcegitcommit: b164d4af65709133e0b512a4327a70fae13a974d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2018
ms.locfileid: "25577086"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="bc138-104">管理者ヘルプの保留中のクラウド ベースのメールボックスの回復可能なアイテム] フォルダー内の項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="bc138-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="bc138-p102">過失または悪意による削除から保護するために Exchange Online のメールボックスの [回復可能な項目] フォルダーが存在しています。保持される、検索を保留リストと電子情報開示など、Office 365 のコンプライアンス機能によってアクセスされるアイテムを保存するにも使用します。ただし、状況によっては、組織はそれらを削除する必要がありますが回復可能なアイテム] フォルダーに誤って保持されているデータがあります。ユーザーが知らないうちに送信など、機密情報や企業が深刻な影響の可能性がある情報を含む電子メール メッセージを転送します。場合でも、メッセージが完全に削除されると、それが無期限に保持され法的差し押さえがメールボックスに格納されているためです。このシナリオは、データが誤ってこぼした Office 365 にあるために、データのこぼしたと呼ばれます。このような場合は、Office 365 の保留中のさまざまな機能の 1 つの保留中のメールボックスが配置された場合でも、Exchange Online のメールボックスに対するユーザーの回復可能なアイテム] フォルダー内の項目を削除できます。保留のこれらの種類には、証拠保全、インプレースを保持して、電子的証拠開示の保留、および Office 365 のセキュリティで作成した Office 365 の保持ポリシーが含まれます&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="bc138-p102">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions. It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches. However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete. For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences. Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox. This scenario is known as data spillage because data has been unintentionally spilled into Office 365. In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365. These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the Office 365 Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="bc138-p103">この資料では、保留中では、クラウド ベースのメールボックスの回復可能なアイテム] フォルダーからアイテムを削除する方法について説明します。この手順は、メールボックスへのアクセスを無効にして、単一アイテムの回復、管理フォルダー アシスタントからメールボックスを処理、保留リストを一時的に削除する、回復可能なアイテム] フォルダーからアイテムを削除して、[元に戻すを無効にするを無効にする必要があります。以前の構成のためのメールボックス。プロセスを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p103">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold. This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration. Here's the process:</span></span> 
  
[<span data-ttu-id="bc138-116">手順 1: メールボックス情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="bc138-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="bc138-117">手順 2: メールボックスを準備します。</span><span class="sxs-lookup"><span data-stu-id="bc138-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="bc138-118">手順 3: メールボックスからすべての保留を削除します。</span><span class="sxs-lookup"><span data-stu-id="bc138-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="bc138-119">ステップ 4: メールボックスからの遅延の保留中を削除します。</span><span class="sxs-lookup"><span data-stu-id="bc138-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

<span data-ttu-id="bc138-120">[手順 5: 回復可能なアイテム] フォルダー内のアイテムを削除します。](#step-5-delete-items-in-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="bc138-120">[Step 5: Delete items in the Recoverable Items folder](#step-5-delete-items-in-the-recoverable-items-folder)</span></span>

[<span data-ttu-id="bc138-121">手順 6: 以前の状態のためのメールボックスを元に戻す</span><span class="sxs-lookup"><span data-stu-id="bc138-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="bc138-p104">この資料に記載された手順と、データは完全に削除 (パージ)、Exchange Online のメールボックスから。つまり、回復可能なアイテム] フォルダーから削除したメッセージは、回復できないので、法的証拠開示やその他のコンプライアンスのために使用できることはできません。証拠保全、インプレース保持の一部として保留中に配置されているメールボックスからメッセージを削除する場合は、電子的証拠開示、または保持ポリシーを Office 365 は、Office 365 のセキュリティで作成された&amp;コンプライアンス センターでは、レコード管理または法的にチェック保留リストを削除する前に部門です。上にメールボックスを保持するかどうかを定義するポリシーを持つ組織もあります。 またはデータのこぼしたインシデントが優先します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p104">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox. That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes. If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the Office 365 Security &amp; Compliance Center, check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="bc138-126">はじめに</span><span class="sxs-lookup"><span data-stu-id="bc138-126">Before you begin</span></span>

- <span data-ttu-id="bc138-127">割り当てられる次の管理役割の両方の Exchange オンラインを検索し、手順 5 で回復可能なアイテム] フォルダーからメッセージを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc138-127">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 5.</span></span>
    
  - <span data-ttu-id="bc138-p105">**メールボックスの検索**- この役割では、組織内のメールボックスを検索することができます。Exchange 管理者は、既定でこの役割を割り当てられない。自分にこの役割を割り当てるには、自分で検出の管理役割グループのメンバーとして Exchange オンライン追加します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p105">**Mailbox Search** - This role lets you to search mailboxes in your organization. Exchange administrators aren't assigned this role by default. To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="bc138-p106">**メールボックスのインポートのエクスポート**- このロールには、ユーザーのメールボックスからメッセージを削除することができます。既定では、このロールはない任意の役割グループに割り当てられます。ユーザーのメールボックスからメッセージを削除するには、ことが役割を追加するメールボックスのインポート エクスポートの組織の管理役割グループに Exchange オンライン。</span><span class="sxs-lookup"><span data-stu-id="bc138-p106">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="bc138-p107">この資料で説明する手順は、非アクティブなメールボックスに対してサポートされていません。です保留中 (または Office 365 のリテンション ・ ポリシー) を適用することはできません再、非アクティブなメールボックスを削除した後。非アクティブなメールボックスから保留を解除するときは通常のソフト削除されたメールボックスに変更しは完全に削除、組織内の管理フォルダー アシスタントによって処理された後。</span><span class="sxs-lookup"><span data-stu-id="bc138-p107">The procedure described in this article isn't supported for inactive mailboxes. That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it. When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="bc138-p108">保持ロックでロックされている Office 365 の保持ポリシーに割り当てられているメールボックスに対してこの手順を実行することはできません。削除するか、管理フォルダー アシスタントでメールボックスを無効にして、Office 365 の保持ポリシーからメールボックスを除外することはできません保持ロックするためです。リテンション ・ ポリシーのロックの詳細については、[リテンション ・ ポリシーのロック](retention-policies.md#locking-a-retention-policy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p108">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock. That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox. For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="bc138-p109">メールボックス保留リストに配置されていない (または単一アイテムの回復が有効になっているがない) 場合は、回復可能なアイテム] フォルダーからだけでアイテムを削除できます。これを行う方法の詳細については、[検索および削除するメッセージ](https://go.microsoft.com/fwlink/?linkid=852453)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p109">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder. For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="bc138-142">手順 1: メールボックス情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="bc138-142">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="bc138-p110">この最初の手順は、次の手順に影響を与える対象のメールボックスから選択したプロパティを収集するためです。これらの設定を記録したり、これらのプロパティの一部を変更し、回復可能なアイテム] フォルダーからアイテムを削除した後に手順 6 では、元の値に戻すことがあるためテキスト ファイルに保存することを確認します。ここでは、収集する必要がありますメールボックスのプロパティの一覧です。</span><span class="sxs-lookup"><span data-stu-id="bc138-p110">This first step is to collect selected properties from the target mailbox that will affect this procedure. Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder. Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="bc138-146">*SingleItemRecoveryEnabled*と*RetainDeletedItemsFor*です。必要に応じて、1 つのリカバリを無効にして、手順 3 で削除済みアイテムの保存期間を変更します。</span><span class="sxs-lookup"><span data-stu-id="bc138-146">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="bc138-p111">*LitigationHoldEnabled*と*InPlaceHolds*です。手順 3 で一時的に削除することができるように、メールボックスにすべての保留リストを識別する必要があります。メールボックスに配置する場合があります型保留リストを識別する方法に関するヒントについては、[詳細について](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p111">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3. See the [More information](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="bc138-p112">またを一時的に無効にできますので、この処理中にメールボックスにアクセスできません、所有者 (または他のユーザー) があるために、メールボックスのクライアント アクセスの設定を取得する必要があります。最後に、回復可能なアイテム] フォルダーには、現在のサイズとアイテム数を取得できます。手順 5 で [回復可能な項目] フォルダー内の項目を削除した後は、項目が実際に削除されることを確認するのにはこの情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p112">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure. Finally, you can get the current size and number of items in the Recoverable Items folder. After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="bc138-p113">[オンライン PowerShell を Exchange に接続](https://go.microsoft.com/fwlink/?linkid=396554)します。Exchange Online 内の適切な管理ロールに割り当てられている管理者アカウントのユーザー名とパスワードを使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p113">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="bc138-154">1 つのアイテムを復元し、削除済みアイテムの保存期間に関する情報を取得するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-154">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="bc138-p114">単一アイテムの回復が有効な場合は、手順 2 で無効にする必要があります。30 日の削除済みアイテムの保存期間が設定されていないかどうか (Exchange Online の最大の値)、手順 2 で増やすことができますし、します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p114">If single item recovery is enabled, you'll have to disable it in Step 2. If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="bc138-157">メールボックス、メールボックスのアクセスの設定を取得する次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-157">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="bc138-158">手順 2 では、これらのアクセス方法のすべてを無効にします。</span><span class="sxs-lookup"><span data-stu-id="bc138-158">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="bc138-159">保持し、Office 365 のメールボックスに適用されるリテンション ・ ポリシーに関する情報を取得するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-159">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="bc138-160">実行することができる場合は、 *InPlaceHolds*プロパティの値が多すぎますがあり、それらのすべてが表示されます、`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`コマンドを別の行に各値を表示します。</span><span class="sxs-lookup"><span data-stu-id="bc138-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="bc138-161">組織全体の Office 365 リテンション ・ ポリシーに関する情報を取得するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-161">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="bc138-162">組織に、組織全体の Office 365 の保持ポリシーがある場合は、手順 3 で、これらのポリシーからメールボックスを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc138-162">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="bc138-163">実行することができる場合は、 *InPlaceHolds*プロパティの値が多すぎますがあり、それらのすべてが表示されます、`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`コマンドを別の行に各値を表示します。</span><span class="sxs-lookup"><span data-stu-id="bc138-163">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="bc138-164">フォルダーおよびユーザーのプライマリ メールボックスの回復可能なアイテム] フォルダー内のサブフォルダーの現在のサイズとアイテムの合計数を取得する次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-164">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="bc138-165">ユーザーのアーカイブ メールボックスが有効な場合は、フォルダーとユーザーのアーカイブ メールボックスの回復可能なアイテム フォルダー内のサブフォルダーのサイズとアイテムの合計数を取得する次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-165">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="bc138-p115">手順 5 でアイテムを削除すると、削除するか、ユーザーの主なアーカイブ メールボックスの回復可能なアイテム] フォルダーにアイテムを削除することもできます。メールボックスのアーカイブの自動拡張が有効になっている場合、補助のアーカイブ メールボックス内のアイテムも削除されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p115">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox. Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="bc138-168">手順 2: メールボックスを準備します。</span><span class="sxs-lookup"><span data-stu-id="bc138-168">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="bc138-169">収集すると、メールボックスに関する情報を保存、次の手順は次のタスクを実行してメールボックスを準備するのにです。</span><span class="sxs-lookup"><span data-stu-id="bc138-169">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="bc138-170">**メールボックスへのクライアント アクセスを無効にする**メールボックスの所有者は自分のメールボックスにアクセスできず、この処理中にメールボックスのデータを変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bc138-170">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="bc138-171">30 日後に**削除済みアイテム保存期間を延長**を (Exchange のオンラインでの最大値) それらを削除するには手順 5 の前に、回復可能なアイテム] フォルダーからアイテムが削除されないようにします。</span><span class="sxs-lookup"><span data-stu-id="bc138-171">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="bc138-172">手順 5 で回復可能なアイテム] フォルダーからそれらを削除した後 (削除済みアイテムの保存期間の期間) のため、アイテムを**1 つのアイテムの復元を無効にする**には保持されません。</span><span class="sxs-lookup"><span data-stu-id="bc138-172">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="bc138-173">**管理フォルダー アシスタントを無効にする**ことは、メールボックスの処理し、手順 5 で削除したアイテムを保持しないようにします。</span><span class="sxs-lookup"><span data-stu-id="bc138-173">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="bc138-174">Exchange オンライン PowerShell で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-174">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="bc138-p116">クライアントからのすべてのメールボックスへのアクセスを無効にするのには、次のコマンドを実行します。コマンドの構文では、メールボックスのすべてのクライアント アクセスの方法が有効であると仮定しています。</span><span class="sxs-lookup"><span data-stu-id="bc138-p116">Run the following command to disable all client access to the mailbox. The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="bc138-p117">メールボックスにすべてのクライアント アクセスの方法を無効にするのには、最大 60 分かかる場合があります。これらのアクセス方法を無効にすることで現在サインインしたメールボックスの所有者を切断しないことに注意してください。所有者署名されていない場合、ことはできませんこれらのアクセス方法が無効にした後のメールボックスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bc138-p117">It might take up to 60 minutes to disable all client access methods to the mailbox. Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in. If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="bc138-p118">削除済みアイテムの保持期間の 30 日間の最大値を増やすには、次のコマンドを実行します。これは、現在の設定は、30 日以内であると仮定します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p118">Run the following command to increase the deleted item retention period the maximum of 30 days. This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="bc138-182">単一アイテムの回復を無効にするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-182">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="bc138-p119">単一アイテムの回復を無効にするのには、最大 60 分かかる場合があります。この期間が経過するまで、回復可能なアイテム フォルダー内のアイテムを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p119">It might take up to 60 minutes to disable single item recovery. Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="bc138-p120">管理フォルダー アシスタントがメールボックスを処理を防ぐために次のコマンドを実行します。説明したようを無効にできます、管理フォルダー アシスタントのみ保持ロックで、Office 365 の保持ポリシーはメールボックスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="bc138-p120">Run the following command to prevent the Managed Folder Assistant from processing the mailbox. As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="bc138-187">手順 3: メールボックスからすべての保留を削除します。</span><span class="sxs-lookup"><span data-stu-id="bc138-187">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="bc138-p121">回復可能なアイテム] フォルダーからアイテムを削除する前に最後のステップでは、すべての保留をするは、手順 1 で識別される)、メールボックスの配置を削除します。アイテムは、回復可能なアイテム] フォルダーからそれらを削除した後は保持されませんように、すべての保留を削除してください。次のセクションには、さまざまな種類のメールボックスの保留を削除することに関する情報が含まれます。メールボックスに配置する場合があります型保留リストを識別する方法に関するヒントについては、[詳細について](#more-information)はを参照してください。詳細については、 [Exchange Online のメールボックスに配置されているの種類を識別する方法を保持](identify-a-hold-on-an-exchange-online-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p121">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox. All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder. The following sections contain information about removing different types of holds on a mailbox. See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox. For additional information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="bc138-193">前述したように、保留リストをメールボックスから削除する前に、レコード管理または法務部門に確認してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-193">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="bc138-194">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="bc138-194">Litigation Hold</span></span>
  
<span data-ttu-id="bc138-195">次のコマンドを実行 Exchange オンライン PowerShell、証拠保全をメールボックスから削除するのには。</span><span class="sxs-lookup"><span data-stu-id="bc138-195">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="bc138-p122">クライアント アクセスの方法と 1 つのアイテムの復元を無効にすることと同様に、かかることがあります、証拠保全を削除するのには最大 60 分までです。この期間が経過するまで、回復可能なアイテム] フォルダーからアイテムを削除しません。</span><span class="sxs-lookup"><span data-stu-id="bc138-p122">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold. Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="bc138-198">インプレース保持</span><span class="sxs-lookup"><span data-stu-id="bc138-198">In-Place Hold</span></span>
  
<span data-ttu-id="bc138-p123">次のコマンドを実行 Exchange オンライン メールボックスに配置されている埋め込みの保持を識別する PowerShell。手順 1 で特定した埋め込み保持の GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p123">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="bc138-p124">埋め込みの保持を識別した後、保留リストからメールボックスを削除するのには、Exchange 管理センター (EAC) または Exchange のオンライン PowerShell を使用できます。詳細については、[作成または削除する、埋め込みの保持](https://go.microsoft.com/fwlink/?linkid=852668)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p124">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold. For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="bc138-203">Office 365 の保持ポリシーが特定のメールボックスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bc138-203">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="bc138-p125">次のコマンドを実行[Office 365 のセキュリティ&amp;コンプライアンス センター PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)メールボックスに適用されている Office 365 の保持ポリシーを識別します。GUID を使用して (を除いて、`mbx`または`skp`プレフィックス) 手順 1 で特定したリテンション ・ ポリシーの。</span><span class="sxs-lookup"><span data-stu-id="bc138-p125">Run the following command in [Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox. Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="bc138-206">リテンション ・ ポリシーを特定した後に、**日付のガバナンス ・** \> **の保存**] ページのセキュリティで&amp;コンプライアンス センターでは、前の手順では、リテンション ・ ポリシーを編集しの一覧からメールボックスを削除します。リテンション ・ ポリシーに含まれる受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="bc138-206">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="bc138-207">Office 365 の保持ポリシーを組織全体にわたる</span><span class="sxs-lookup"><span data-stu-id="bc138-207">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="bc138-p126">組織全体および Exchange 全体の Office 365 のリテンション ・ ポリシーは、組織内のすべてのメールボックスに適用されます。組織レベル (メールボックス レベルではなく) の適用は、手順 1 で**取得 OrganizationConfig**コマンドレットを実行する場合に返されます。次のコマンドを実行[セキュリティ&amp;コンプライアンス センター PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)組織の Office 365 のリテンション ・ ポリシーを識別します。GUID を使用して (を除いて、`mbx`プレフィックス) 手順 1 で特定した組織全体の保存ポリシーのです。</span><span class="sxs-lookup"><span data-stu-id="bc138-p126">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization. They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1. Run the following command in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies. Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="bc138-p127">組織の Office 365 のリテンション ・ ポリシーを特定した後に、**日付のガバナンス**\>セキュリティでの**保存期間**] ページ&amp;コンプライアンス センターで特定した各組織全体の保存ポリシーの編集、前ステップ、およびメールボックスを除外されている受信者の一覧に追加します。この操作を行うと、リテンション ・ ポリシーからユーザーのメールボックスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="bc138-p127">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients. Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="office-365-retention-labels"></a><span data-ttu-id="bc138-214">Office 365 保存ラベル</span><span class="sxs-lookup"><span data-stu-id="bc138-214">Office 365 retention labels</span></span>

<span data-ttu-id="bc138-p128">ユーザーが構成されているコンテンツを保持または保持し、任意のフォルダーまたはメールボックス内のアイテムにコンテンツを削除するラベルを適用するたびに、 *ComplianceTagHoldApplied*のメールボックスのプロパティが**True**に設定します。このような場合、メールボックスは、保留中の場合と同様に証拠保全がまたは Office 365 のリテンション ・ ポリシーに割り当てられていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="bc138-p128">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**. When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span>

<span data-ttu-id="bc138-217">*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-217">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="bc138-p129">上のメールボックスを特定したら、保存ラベルは、フォルダーまたはアイテムに適用されます、コンテンツの検索ツールを使用するには、セキュリティとコンプライアンス ・ センターを検索するというラベルの付いた項目 ComplianceTag の検索条件を使用しているためにを保持します。詳細については、[キーワード クエリとコンテンツの検索の検索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)で「検索条件」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p129">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the Security & Compliance Center to search for labeled items by using the ComplianceTag search condition. For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="bc138-220">ラベルの詳細については、 [Office 365 の概要のラベル](labels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-220">For more information about labels, see [Overview of Office 365 labels](labels.md).</span></span>

 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="bc138-221">電子的証拠開示のケースを保持します。</span><span class="sxs-lookup"><span data-stu-id="bc138-221">eDiscovery case holds</span></span>
  
<span data-ttu-id="bc138-p130">次のコマンドを実行[セキュリティ&amp;コンプライアンス センター PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)メールボックスに適用されている電子的証拠開示のサポート案件に関連付けられている保留リストを識別します。GUID を使用して (を除いて、`UniH`プレフィックス)、電子的証拠開示の手順 1 で識別することを保持します。2 番目のコマンドが保留リストに関連付けられては電子的証拠開示のケースの名前を表示することに注意してください。3 番目のコマンドは、保留リストの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p130">Run the following commands in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox. Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1. Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="bc138-p131">電子的証拠開示の場合、保留リストの名前を特定した後に、**検索&amp;調査**\>セキュリティで**電子的証拠開示**のページ&amp;コンプライアンス センター、ケースを開けるし、保留リストからメールボックスを削除します。詳細についてを参照してください[電子的証拠開示の場合は、Office 365 のセキュリティを管理する&amp;コンプライアンス センター](manage-ediscovery-cases.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc138-p131">After you've identified the name of the eDiscovery case and the hold, go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and remove the mailbox from the hold. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="bc138-227">ステップ 4: メールボックスからの遅延の保留中を削除します。</span><span class="sxs-lookup"><span data-stu-id="bc138-227">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="bc138-p132">保留中の任意の種類がメールボックスから削除されると、 *DelayHoldApplied*のメールボックスのプロパティの値が**True**に設定します。次に管理フォルダー アシスタントのメールボックスを処理し、保留リストが削除されたことを検出したとき発生します。これし、呼ばれ*遅延を保持*するデータがメールボックスから完全に削除されることを防止するのには 30 日間、保留中の実際の削除が遅れることを意味します。(遅延保持の目的を検索するか、保留が削除された後にパージされるメールボックス アイテムを回復する機会を管理者に提供するが)。 遅延ホールドがメールボックスに配置されると、メールボックスと見なされます上にある、無制限の期間の保持と証拠保全上にメールボックスがあったかどうか。30 日間、遅延の保持期限が切れる、および Office 365 は、( *DelayHoldApplied*プロパティを**False**に設定) によって遅延保持を削除するのには自動的に試みます保留リストが実際に削除されるようにします。</span><span class="sxs-lookup"><span data-stu-id="bc138-p132">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**. This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed. This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox. (The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold. After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold is actually removed.</span></span> 

<span data-ttu-id="bc138-p133">手順 5 でアイテムを削除するには、メールボックスから遅延保持を削除する必要があります。最初に、Exchange オンライン PowerShell で次のコマンドを実行して、メールボックスに遅延保留が適用されるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p133">Before you can delete items in Step 5, you have to remove the delay hold from the mailbox. First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="bc138-p134">場合は**false を指定**する*DelayHoldApplied*プロパティの値を設定すると、遅延の保留リストが配置メールボックスにされていません。手順 5 に移動し、回復可能なアイテム] フォルダー内の項目を削除できます。</span><span class="sxs-lookup"><span data-stu-id="bc138-p134">If the value of the *DelayHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox. You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="bc138-237">*DelayHoldApplied*プロパティの値は、 **True**に設定されている場合は、遅延の保留を解除するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-237">If the value of the *DelayHoldApplied* property is set to **True**, run the following command to remove the delay hold:</span></span>

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="bc138-238">する必要があります法的保持義務の役割を割り当てる Exchange オンライン*RemoveDelayHoldApplied*パラメーターを使用するのには注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-238">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="bc138-239">手順 5: 回復可能なアイテム] フォルダー内のアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="bc138-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="bc138-p135">PowerShell を使用して[検索メールボックス](https://go.microsoft.com/fwlink/?linkid=852595)コマンドレットでは、Exchange オンラインで実際には、回復可能なアイテム] フォルダー内のアイテムを削除する準備が整いました。**検索用メールボックス**のコマンドレットを実行するとき、3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="bc138-p135">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell. You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="bc138-242">それらを削除する前に、この項目では、必要に応じてを確認することができますそれらを削除する前に、アイテムを移動先のメールボックスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="bc138-242">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="bc138-243">アイテムを移動先のメールボックスにコピーし、同じコマンドを削除することです。</span><span class="sxs-lookup"><span data-stu-id="bc138-243">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="bc138-244">移動先のメールボックスにコピーすることのないアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="bc138-244">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="bc138-p136">ユーザーの主なアーカイブ メールボックスの回復可能なアイテム フォルダー内のアイテムをも削除を実行すると、\* \* 検索メールボックス \* \* コマンドレットです。これを防止するには、 *DoNotIncludeArchive*スイッチを含めることができます。前述したように場合は、アーカイブの自動拡張が有効なメールボックスの \* \* 検索メールボックス \* \* コマンドレットは、補助のアーカイブ メールボックス内のアイテムを削除しません。自動拡張の詳細については、アーカイブ、 [Office 365 で無制限のアーカイブの概要](unlimited-archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p136">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the \*\* Search-Mailbox \*\* cmdlet. To prevent this, you can include the  *DoNotIncludeArchive*  switch. And as previously stated, if auto-expanding archiving is enabled for the mailbox, the \*\* Search-Mailbox \*\* cmdlet doesn't deleted items in an auxiliary archive mailbox. For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc138-p137">( *SearchQuery*  パラメーターを使用していて) 検索クエリが含まれている場合、 **Search-Mailbox** コマンドレットは、検索結果で最大 10,000 個のアイテムを返します。したがって、検索クエリを含める場合は、 **Search-Mailbox** コマンドを複数回実行して 10,000 を超えるアイテムを削除する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="bc138-p137">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="bc138-p138">次の例では、これらのオプションのコマンドの構文を表示します。これらの例を使用して、`-SearchQuery size>0`パラメーターの値は、回復可能なアイテム] フォルダー内のすべてのサブフォルダーからすべてのアイテムを削除します。特定の条件に一致するアイテムのみを削除する場合は、または日付範囲のメッセージの件名など、他の条件を指定するのには、 *SearchQuery*パラメーターを使用することができますも。次の[SearchQuery パラメーターを使用するには、他の例](#other-examples-of-using-the-searchquery-parameter)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p138">The following examples show the command syntax for each of these options. These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder. If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range. See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="bc138-255">例 1</span><span class="sxs-lookup"><span data-stu-id="bc138-255">Example 1</span></span>

<span data-ttu-id="bc138-p139">この例では、組織の探索検索メールボックス内のフォルダーに、ユーザーの回復可能なアイテム] フォルダー内のすべての項目をコピーします。項目を完全に削除する前に確認できます。</span><span class="sxs-lookup"><span data-stu-id="bc138-p139">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox. This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="bc138-p140">前の例では、探索検索メールボックスにアイテムをコピーする必要はありません。移動先のメールボックスにメッセージをコピーすることができます。ただし、可能性のある機密性の高いメールボックス データへのアクセスを防ぐため、お勧めアクセス権限のある担当者に制限のあるメールボックスにメッセージをコピーします。既定では、既定の探索検索メールボックスへのアクセスが制限されている探索管理役割グループのメンバーに Exchange オンライン。</span><span class="sxs-lookup"><span data-stu-id="bc138-p140">In the previous example, it isn't required to copy items to the Discovery Search Mailbox. You can copy messages to any target mailbox. However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel. By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="bc138-262">例 2</span><span class="sxs-lookup"><span data-stu-id="bc138-262">Example 2</span></span>

<span data-ttu-id="bc138-263">この例では、組織の探索検索メールボックス内のフォルダーにユーザーの回復可能なアイテム] フォルダー内のすべての項目をコピーし、ユーザーの回復可能なアイテム] フォルダーからアイテムが削除されます。</span><span class="sxs-lookup"><span data-stu-id="bc138-263">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="bc138-264">例 3</span><span class="sxs-lookup"><span data-stu-id="bc138-264">Example 3</span></span>

<span data-ttu-id="bc138-265">この例では、移動先のメールボックスにコピーすることがなくユーザーの回復可能なアイテム] フォルダー内のすべての項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="bc138-265">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="bc138-266">SearchQuery パラメーターを使用するには、他の例</span><span class="sxs-lookup"><span data-stu-id="bc138-266">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="bc138-p141">*SearchQuery*パラメーターを使用して特定のメッセージを検索するがいくつかの例を次に示します。*SearchQuery*パラメーターを使用して特定の項目を検索する場合は、移動先のメールボックスに検索結果をコピーできるように、検索結果を確認して、クエリを変更に応じて、検索結果を削除する前に検討してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p141">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages. If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="bc138-269">この例では、[件名] フィールドで特定の語句を含むメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="bc138-269">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="bc138-270">この例では、指定した日付範囲内で送信されたメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="bc138-270">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="bc138-271">この例では、指定したユーザーに送信されたメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="bc138-271">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="bc138-272">アイテムが削除されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc138-272">Verify that items were deleted</span></span>

<span data-ttu-id="bc138-p142">メールボックスの回復可能なアイテム] フォルダーからアイテムを正常に削除したことを確認するには、PowerShell を使用**Get MailboxFolderStatistics**コマンドレット Exchange オンライン回復可能なアイテム] フォルダー内のアイテムの数とサイズを確認します。ステップ 1 で収集したもので、これらの統計を比較することができます。</span><span class="sxs-lookup"><span data-stu-id="bc138-p142">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder. You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="bc138-275">フォルダーおよびユーザーのプライマリ メールボックスの回復可能なアイテム] フォルダー内のサブフォルダーの現在のサイズとアイテムの合計数を取得する次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-275">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="bc138-276">フォルダーおよびユーザーのアーカイブ メールボックスの回復可能なアイテム] フォルダー内のサブフォルダーのサイズとアイテムの合計数を取得する次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-276">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="bc138-277">手順 6: 以前の状態のためのメールボックスを元に戻す</span><span class="sxs-lookup"><span data-stu-id="bc138-277">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="bc138-p143">最後の手順は、メールボックスを以前の構成を元に戻すには。これは、手順 2 で変更したプロパティをリセットして、手順 3 で削除する保留リストを再適用することを意味します。これが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bc138-p143">The final step is to revert the mailbox back to its previous configuration. This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3. This includes:</span></span>
  
- <span data-ttu-id="bc138-p144">削除済みアイテムの保持期間を変更する前の値にバックアップを作成します。または、することができますだけオンラインのままに Exchange で 30 日、最大値に設定。</span><span class="sxs-lookup"><span data-stu-id="bc138-p144">Changing the deleted item retention period back to its previous value. Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="bc138-283">1 つのアイテムの復元を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="bc138-283">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="bc138-284">所有者が自分のメールボックスにアクセスできるように、クライアント アクセスの方法を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="bc138-284">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="bc138-285">保持し、削除する保持ポリシーを Office 365 を再適用します。</span><span class="sxs-lookup"><span data-stu-id="bc138-285">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="bc138-286">管理フォルダー アシスタントにメールボックスの処理を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="bc138-286">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="bc138-287">保留中または Office 365 を再適用した後 24 時間を待機することをお勧めします。 保存ポリシーとそれが適用されていることを確認する) を再度有効にする、管理フォルダー アシスタントのメールボックスを処理する前にします。</span><span class="sxs-lookup"><span data-stu-id="bc138-287">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="bc138-288">Exchange オンライン PowerShell では、(、指定した順序で) 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-288">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="bc138-p145">削除済みアイテムの保持期間を変更するのには次のコマンドが元の値にバックアップを実行します。以前の設定には、30 日以内にこれを前提としていますたとえば 14 日間です。</span><span class="sxs-lookup"><span data-stu-id="bc138-p145">Run the following command to change the deleted item retention period back to its original value. This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="bc138-291">1 つのアイテムの復元を再度有効にするのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-291">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="bc138-292">メールボックスにすべてのクライアント アクセスの方法を再度有効にするのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-292">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="bc138-p146">手順 3 で削除する保留リストを再適用します。、保留リストの種類に応じて、次の手順のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p146">Re-apply the holds that you removed in Step 3. Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="bc138-295">**訴訟ホールド**</span><span class="sxs-lookup"><span data-stu-id="bc138-295">**Litigation Hold**</span></span>
    
    <span data-ttu-id="bc138-296">メールボックスの証拠の保全を再度有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc138-296">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="bc138-297">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="bc138-297">**In-Place Hold**</span></span>
    
    <span data-ttu-id="bc138-298">埋め込みの保持にメールボックスを追加するのには、EAC (または Exchange オンライン PowerShell) を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc138-298">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="bc138-299">**Office 365 の保持ポリシーが特定のメールボックスに適用されます。**</span><span class="sxs-lookup"><span data-stu-id="bc138-299">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="bc138-p147">セキュリティを使用して、 &amp; 、メールボックスを Office 365 のリテンション ・ ポリシーに追加するコンプライアンス センターです。**日付のガバナンス**に\>**の保存**] ページのセキュリティで&amp;コンプライアンス センターでは、リテンション ・ ポリシーを編集し、リテンション ・ ポリシーが適用される受信者のリストに戻る、メールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p147">Use the Security &amp; Compliance Center to add the mailbox back to the Office 365 retention policy. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="bc138-302">**Office 365 の保持ポリシーを組織全体にわたる**</span><span class="sxs-lookup"><span data-stu-id="bc138-302">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="bc138-p148">ポリシーから除外することによって、組織全体または Exchange 全体の保持ポリシーを削除する場合は、セキュリティを使用して&amp;の一覧からメールボックスを削除するのにはコンプライアンス センターは、ユーザーを除外します。**日ガバナンス**に\>**の保存**] ページのセキュリティで&amp;コンプライアンス センターでは、組織全体のリテンション ・ ポリシーを編集し、除外されている受信者の一覧からメールボックスを削除します。これは再、保持ポリシーの適用ユーザーのメールボックスにします。</span><span class="sxs-lookup"><span data-stu-id="bc138-p148">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security &amp; Compliance Center to remove the mailbox from the list of excluded users. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients. Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="bc138-306">**電子的証拠開示のケースを保持します。**</span><span class="sxs-lookup"><span data-stu-id="bc138-306">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="bc138-p149">セキュリティを使用して、 &amp; 、メールボックスを追加するのにはコンプライアンス センター電子的証拠開示のサポート案件に関連付けられている保留中のバックアップします。移動、**検索&amp;調査**\>セキュリティで**電子的証拠開示**ページ&amp;コンプライアンス ・ センター、ケースを開けるし、メールボックスを保留リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="bc138-p149">Use the Security &amp; Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case. Go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="bc138-p150">管理フォルダー アシスタント メールボックスをもう一度処理を許可するのには、次のコマンドを実行します。述べたように、保留中または Office 365 を再適用した後 24 時間を待機することをお勧めします。 保存ポリシーとそれが適用されていることを確認する) 前に、再度有効にする、管理フォルダー アシスタントです。</span><span class="sxs-lookup"><span data-stu-id="bc138-p150">Run the following command to allow the Managed Folder Assistant to process the mailbox again. As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="bc138-311">以前の状態に戻します、メールボックスが元に戻されたことを確認するには、次のコマンドを実行し、手順 1 で収集したものに設定を比較し、できます。</span><span class="sxs-lookup"><span data-stu-id="bc138-311">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="bc138-312">詳細情報</span><span class="sxs-lookup"><span data-stu-id="bc138-312">More information</span></span>

<span data-ttu-id="bc138-p151">ここでは、 **Get メールボックス**または**Get OrganizationConfig**コマンドレットを実行すると、 *InPlaceHolds*プロパティの値に基づいて保留の種類を識別する方法を説明した表です。詳細については、[の種類を識別する方法を Exchange Online のメールボックスに配置されている保持](identify-a-hold-on-an-exchange-online-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc138-p151">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets. For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="bc138-315">前に説明すると、すべての保留を削除するのにがありする前にメールボックスから保存ポリシーを Office 365 は、回復可能なアイテム] フォルダー内の項目を正常に削除できます。</span><span class="sxs-lookup"><span data-stu-id="bc138-315">As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="bc138-316">**ホールドの種類**</span><span class="sxs-lookup"><span data-stu-id="bc138-316">**Hold type**</span></span>|<span data-ttu-id="bc138-317">**値の例**</span><span class="sxs-lookup"><span data-stu-id="bc138-317">**Example value**</span></span>|<span data-ttu-id="bc138-318">**保留リストを識別する方法**</span><span class="sxs-lookup"><span data-stu-id="bc138-318">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bc138-319">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="bc138-319">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="bc138-320">*LitigationHoldEnabled*  プロパティが  `True` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="bc138-320">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="bc138-321">インプレース保持</span><span class="sxs-lookup"><span data-stu-id="bc138-321">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="bc138-p152">*InPlaceHolds*プロパティには、メールボックスに配置されている埋め込みの保持の GUID が含まれています。これは、埋め込みを保持するためプレフィックスを持つ GUID が起動しないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="bc138-p152">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="bc138-324">Exchange Online PowerShell で  \`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID></span><span class="sxs-lookup"><span data-stu-id="bc138-324">You can use the  \`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID></span></span> | <span data-ttu-id="bc138-325">FL' のメールボックス上の埋め込みの保持に関する情報を取得する Exchange のオンライン PowerShell コマンドです。</span><span class="sxs-lookup"><span data-stu-id="bc138-325">FL\` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="bc138-326">セキュリティで保存ポリシーを office 365&amp;コンプライアンス センターは、特定のメールボックスに適用</span><span class="sxs-lookup"><span data-stu-id="bc138-326">Office 365 retention policies in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="bc138-327">または</span><span class="sxs-lookup"><span data-stu-id="bc138-327">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="bc138-p153">**Get メールボックス**コマンドレットを実行すると Office 365 の Guid の保存ポリシーが、メールボックスに適用されるは、 *InPlaceHolds*プロパティも含まれます。リテンション ・ ポリシーを識別するには、GUID が始まるため、`mbx`のプレフィックスです。リテンション ・ ポリシーの GUID で始まる場合、 `skp` 、ビジネス会話を Skype にリテンション ・ ポリシーが適用されることを示すプレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="bc138-p153">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox. You can identify retention policies because the GUID starts with the  `mbx` prefix. Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.  </span></span><br/> <span data-ttu-id="bc138-331">セキュリティの次のコマンドを実行するメールボックスに適用されている保持ポリシーを Office 365 の id、&amp;コンプライアンス センター PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bc138-331">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/> <br/><span data-ttu-id="bc138-332">' Get RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="bc138-332">\`Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="bc138-333">FL 名`<br/><br/>Be sure to remove the  `mbx` or  `skp' このコマンドを実行するときにプレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="bc138-333">FL Name`<br/><br/>Be sure to remove the  `mbx` or  `skp\` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="bc138-334">セキュリティで Office 365 保存ポリシーを組織全体にわたる&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="bc138-334">Organization-wide Office 365 retention policies in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="bc138-335">値なし</span><span class="sxs-lookup"><span data-stu-id="bc138-335">No value</span></span>  <br/> <span data-ttu-id="bc138-336">または</span><span class="sxs-lookup"><span data-stu-id="bc138-336">or</span></span>  <br/>  <span data-ttu-id="bc138-337">`-mbxe9b52bf7ab3b46a286308ecb29624696`(メールボックスが組織全体にわたるポリシーから除外されていることを示します)</span><span class="sxs-lookup"><span data-stu-id="bc138-337">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="bc138-338">**Get メールボックス**コマンドレットを実行する*InPlaceHolds*プロパティが空であってもある可能性があります 1 つまたは複数のメールボックスに適用される組織の Office 365 リテンション ・ ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="bc138-338">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="bc138-339">実行することができますこれを確認するのには、' Get OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="bc138-339">To verify this, you can run the  \`Get-OrganizationConfig</span></span> | <span data-ttu-id="bc138-340">FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="bc138-340">FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="bc138-341">FL 名`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `・ mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696'</span><span class="sxs-lookup"><span data-stu-id="bc138-341">FL Name`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696\`</span></span> <br/> |
|<span data-ttu-id="bc138-342">電子的証拠開示の場合は、セキュリティの保持&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="bc138-342">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="bc138-p154">*InPlaceHolds*プロパティには、セキュリティ、電子的証拠開示のケースに関連付けられている保留状態の GUID も含まれています&amp;コンプライアンス センター メールボックスに配置する可能性があります。これは、GUID が始まるためにの電子的証拠開示サポート ・ リクエストの保留がわかる、`UniH`のプレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="bc138-p154">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security &amp; Compliance Center that might be placed on the mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="bc138-p155">使用することができます、`Get-CaseHoldPolicy`セキュリティのコマンドレット&amp;コンプライアンス センターの PowerShell のメールボックスの保留リストが関連付けられている電子的証拠開示のサポート案件に関する情報を取得します。コマンドを実行することができますたとえば、' Get CaseHoldPolicy<hold GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="bc138-p155">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with. For example, you can run the command  \`Get-CaseHoldPolicy <hold GUID without prefix></span></span> | <span data-ttu-id="bc138-347">FL 名` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get CaseHoldPolicy <hold GUID without prefix> `<br/><br/>`Get ComplianceCase $CaseHold.CaseId</span><span class="sxs-lookup"><span data-stu-id="bc138-347">FL Name` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId</span></span> | <span data-ttu-id="bc138-348">FL 名 '</span><span class="sxs-lookup"><span data-stu-id="bc138-348">FL Name\`</span></span>


