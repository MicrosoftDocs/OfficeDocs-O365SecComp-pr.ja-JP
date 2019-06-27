---
title: メールボックスの監査を管理する
ms.author: chrisda
author: chrisda
manager: serdars
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: メールボックス監査ログは、Microsoft 365 で既定で有効化されています (既定メールボックス監査または既定によるメールボックス監査の有効化とも呼ばれます)。 これは、メールボックスの所有者、代理人、および管理者が実行する特定の操作は自動的にログに記録され、このログではメールボックスに対して実行されたアクティビティを検索できることを意味します。
ms.openlocfilehash: f100fa1eb8244aeaea463440025ee489ec019406
ms.sourcegitcommit: ef2657e4221296be7032191f2d91e8ff727523c6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "35117692"
---
# <a name="manage-mailbox-auditing"></a><span data-ttu-id="4601e-104">メールボックスの監査を管理する</span><span class="sxs-lookup"><span data-stu-id="4601e-104">Manage mailbox auditing</span></span>

<span data-ttu-id="4601e-105">2019 年 1 月以降、Microsoft は、Microsoft 365 を使用するすべての組織でメールボックス監査を既定で有効化します。</span><span class="sxs-lookup"><span data-stu-id="4601e-105">Starting in January 2019, Microsoft is turning on mailbox audit logging by default for all Microsoft 365 organizations.</span></span> <span data-ttu-id="4601e-106">これにより、メールボックスの所有者、代理人、および管理者が実行する特定の操作は自動的にログに記録され、メールボックス監査ログでそれらの操作を検索する際に対応するメールボックス監査レコードにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4601e-106">This means that certain actions performed by mailbox owners, delegates, and admins are automatically logged, and the corresponding mailbox audit records will be available when you search for them in the mailbox audit log.</span></span> <span data-ttu-id="4601e-107">メールボックス監査が既定で有効化される前は、ユーザーは組織内のユーザー メールボックスを 1 つずつ手動で有効化する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="4601e-107">Before mailbox auditing was turned on by default, you had to manually enable it for every user mailbox in your organization.</span></span>

<span data-ttu-id="4601e-108">既定によるメールボックス監査の有効化には次のメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="4601e-108">Here are some benefits of mailbox auditing on by default:</span></span>

- <span data-ttu-id="4601e-109">新しいメールボックスを作成すると、監査が自動的に有効化されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-109">Auditing is automatically enabled when you create a new mailbox.</span></span> <span data-ttu-id="4601e-110">新しいユーザーについて、監査を手動で有効にする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="4601e-110">You don't need to manually enable it for new users.</span></span>

- <span data-ttu-id="4601e-111">監査対象メールボックスのメールボックス操作を管理する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="4601e-111">You don't need to manage the mailbox actions that are audited.</span></span> <span data-ttu-id="4601e-112">各ログオンの種類 (管理者、代理人、および所有者) について、事前定義済みのメールボックス操作のセットが既定で監査されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-112">A predefined set of mailbox actions are audited by default for each logon type (Admin, Delegate, and Owner).</span></span>

- <span data-ttu-id="4601e-113">Microsoft が新しいメールボックス操作 (特に、組織を保護し、法的捜査に役立つ操作) をリリースした場合は、既定で監査されるメールボックス操作のリストに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-113">When Microsoft releases a new mailbox action (particularly actions that help protect your organization and help with forensic investigations), the action is automatically added to the list of mailbox actions that are audited by default.</span></span> <span data-ttu-id="4601e-114">これは、メールボックスの監査や新しい操作の追加を行う必要がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4601e-114">This means you don't need to monitor add new actions on mailboxes.</span></span>

- <span data-ttu-id="4601e-115">すべてのメールボックスについて同じ操作が監査されるため、組織全体で一貫性のあるメールボックス監査ポリシーを実現できます。</span><span class="sxs-lookup"><span data-stu-id="4601e-115">You have a consistent mailbox auditing policy across your organization (because you're auditing the same actions for all mailboxes).</span></span>

> [!TIP]
> <span data-ttu-id="4601e-116">既定によるメールボックス監査の有効化のリリースに関しては、メールボックス監査を管理するためにユーザーが行う必要がある操作は何もないということを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="4601e-116">The important thing to remember about the release of mailbox auditing on by default is: you don't need to do anything to manage mailbox auditing.</span></span> <span data-ttu-id="4601e-117">このトピックでは、詳細をさらに理解し、メールボックス監査の既定の設定を変更してカスタマイズし、また監査を無効にするための説明をします。</span><span class="sxs-lookup"><span data-stu-id="4601e-117">However, to learn more, customize mailbox auditing from the default settings, or turn it off altogether, this topic can help you.</span></span>

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a><span data-ttu-id="4601e-118">既定によるメールボックス監査の有効化がオンになっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="4601e-118">Verify mailbox auditing on by default is turned on</span></span>

<span data-ttu-id="4601e-119">既定によるメールボックス監査の有効化が組織でオンになっていることを確認するには、[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4601e-119">To verify that mailbox auditing on by default is turned on for your organization, run the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):</span></span>

```
Get-OrganizationConfig | Format-List AuditDisabled
```

<span data-ttu-id="4601e-120">値 **False** は、既定によるメールボックス監査の有効化が組織でオンになっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="4601e-120">The value **False** indicates that mailbox auditing on by default is enabled for the organization.</span></span> <span data-ttu-id="4601e-121">この、既定で有効化する組織単位の値は、特定のメールボックスでのメールボックス監査の設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4601e-121">This on by default organizational value overrides the mailbox auditing setting on specific mailboxes.</span></span> <span data-ttu-id="4601e-122">たとえば、メールボックスでメールボックス監査が無効になっている場合でも (そのメールボックスの *AuditEnabled* プロパティは **False** です)、既定によるメールボックス監査の有効化が組織でオンになっているため、メールボックスでは既定のメールボックス操作が引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-122">For example, if mailbox auditing is disabled for a mailbox (the *AuditEnabled* property is **False** on the mailbox), the default mailbox actions will still be audited for the mailbox, because mailbox auditing on by default is enabled for the organization.</span></span>

<span data-ttu-id="4601e-123">特定のメールボックスでメールボックス監査の無効設定を維持するには、メールボックスの所有者またはメールボックスへのアクセスを委任された他のユーザーについて、メールボックス監査のバイパスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4601e-123">To keep mailbox auditing disabled for specific mailboxes, you configure mailbox auditing bypass for the mailbox owner and other users who have been delegated access to the mailbox.</span></span> <span data-ttu-id="4601e-124">詳細については、このトピックの「[メールボックス監査ログをバイパスする](#bypass-mailbox-audit-logging)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4601e-124">For more information, see the [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) section in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="4601e-125">既定によるメールボックス監査の有効化を組織でオンにしても、影響を受けるメールボックスの *AuditEnabled* プロパティは **False** から **True** に変わりません。</span><span class="sxs-lookup"><span data-stu-id="4601e-125">When mailbox auditing on by default is turned on for the organization, the *AuditEnabled* property for affected mailboxes won't be changed from **False** to **True**.</span></span> <span data-ttu-id="4601e-126">つまり、既定によるメールボックス監査の有効化は、メールボックスの *AuditEnabled* プロパティを無視します。</span><span class="sxs-lookup"><span data-stu-id="4601e-126">In other words, mailbox auditing on by default ignores the *AuditEnabled* property on mailboxes.</span></span>

## <a name="supported-mailbox-types"></a><span data-ttu-id="4601e-127">サポートされているメールボックスの種類</span><span class="sxs-lookup"><span data-stu-id="4601e-127">Supported mailbox types</span></span>

<span data-ttu-id="4601e-128">既定によるメールボックス監査の有効化で現在サポートされているメールボックスの種類を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="4601e-128">The following table shows the mailbox types that are currently supported by mailbox auditing on by default:</span></span>

|<span data-ttu-id="4601e-129">**メールボックスの種類**</span><span class="sxs-lookup"><span data-stu-id="4601e-129">\*\*\*\* Mailbox type limitations</span></span>|<span data-ttu-id="4601e-130">**サポートされている**</span><span class="sxs-lookup"><span data-stu-id="4601e-130">**Supported**</span></span>|<span data-ttu-id="4601e-131">**サポートされていない**</span><span class="sxs-lookup"><span data-stu-id="4601e-131">**Not supported**</span></span>|
|:---------|:---------:|:---------:|
|<span data-ttu-id="4601e-132">ユーザー メールボックス</span><span class="sxs-lookup"><span data-stu-id="4601e-132">User mailboxes</span></span>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="4601e-134">共有メールボックス</span><span class="sxs-lookup"><span data-stu-id="4601e-134">Shared mailboxes</span></span>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="4601e-136">Office 365 グループ メールボックス</span><span class="sxs-lookup"><span data-stu-id="4601e-136">Office 365 Group cmdlets</span></span>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="4601e-138">リソース メールボックス</span><span class="sxs-lookup"><span data-stu-id="4601e-138">Resource mailboxes</span></span>||![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="4601e-140">パブリック フォルダー メールボックス</span><span class="sxs-lookup"><span data-stu-id="4601e-140">Public folder mailboxes</span></span>||![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a><span data-ttu-id="4601e-142">ログオンの種類とメールボックス操作</span><span class="sxs-lookup"><span data-stu-id="4601e-142">Logon types and mailbox actions</span></span>

<span data-ttu-id="4601e-143">ログオンの種類は、メールボックスで監査対象操作を実行したユーザーを分類します。</span><span class="sxs-lookup"><span data-stu-id="4601e-143">Logon types classify the user that did the audited actions on the mailbox.</span></span> <span data-ttu-id="4601e-144">次の一覧では、メールボックス監査ログで使用されるログオンの種類を説明します。</span><span class="sxs-lookup"><span data-stu-id="4601e-144">The following list describes the logon types that are used in mailbox audit logging:</span></span>

- <span data-ttu-id="4601e-145">**所有者**: メールボックスの所有者 (メールボックスに関連付けられているアカウント)。</span><span class="sxs-lookup"><span data-stu-id="4601e-145">**Owner**: The mailbox owner (the account that's associated with the mailbox).</span></span>

- <span data-ttu-id="4601e-146">**代理人**:</span><span class="sxs-lookup"><span data-stu-id="4601e-146">Delegate</span></span>

  - <span data-ttu-id="4601e-147">別のメールボックスへの、SentAs、SendOnBehalf、または FullAccess のアクセス許可が割り当てられているユーザー。</span><span class="sxs-lookup"><span data-stu-id="4601e-147">A user who's been assigned the SendAs, SendOnBehalf, or FullAccess permission to another mailbox.</span></span>

  - <span data-ttu-id="4601e-148">特定のユーザーのメールボックスへの FullAccess アクセス許可が割り当てられている管理者。</span><span class="sxs-lookup"><span data-stu-id="4601e-148">An admin who's been assigned the FullAccess permission to a user's mailbox.</span></span>

- <span data-ttu-id="4601e-149">**管理者**:</span><span class="sxs-lookup"><span data-stu-id="4601e-149">Admin</span></span>

  - <span data-ttu-id="4601e-150">メールボックスは、次の Microsoft 電子情報開示ツールのいずれかを使用して検索されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-150">The mailbox is searched with one of the following Microsoft eDiscovery tools:</span></span>

    - <span data-ttu-id="4601e-151">コンプライアンス センターのコンプライアンス検索。</span><span class="sxs-lookup"><span data-stu-id="4601e-151">Content Search in the Compliance center.</span></span>

    - <span data-ttu-id="4601e-152">コンプライアンス センターの電子情報開示または 高度な電子情報開示。</span><span class="sxs-lookup"><span data-stu-id="4601e-152">eDiscovery or Advanced eDiscovery in the Compliance center.</span></span>

    - <span data-ttu-id="4601e-153">Exchange Online のインプレース電子情報開示。</span><span class="sxs-lookup"><span data-stu-id="4601e-153">In-Place eDiscovery in Exchange Online</span></span>

  - <span data-ttu-id="4601e-154">[Microsoft Exchange Server MAPI エディター](https://go.microsoft.com/fwlink/p/?linkId=204086)を使用してメールボックスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4601e-154">The mailbox is accessed by using the [Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086).</span></span>

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a><span data-ttu-id="4601e-155">ユーザー メールボックスおよび共有メールボックスのメールボックス操作</span><span class="sxs-lookup"><span data-stu-id="4601e-155">Mailbox actions for user mailboxes and shared mailboxes</span></span>

<span data-ttu-id="4601e-156">次の表では、ユーザー メールボックスおよび共有メールボックスのメールボックス監査ログで利用できるメールボックス操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4601e-156">The following table describes the mailbox actions that are available in mailbox audit logging for user mailboxes and shared mailboxes.</span></span>

- <span data-ttu-id="4601e-157">チェック マーク (</span><span class="sxs-lookup"><span data-stu-id="4601e-157">A check mark (</span></span> ![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="4601e-159">) は、ログオンの種類について、メールボックス操作をログに記録できることを示します (すべての操作をすべての種類で利用できるわけではありません)。</span><span class="sxs-lookup"><span data-stu-id="4601e-159">) indicates the mailbox action can be logged for the logon type (not all actions are available for all logon types).</span></span>

- <span data-ttu-id="4601e-160">チェック マークの後ろのアスタリスク ( <sup>\*</sup> ) は、ログオンの種類について、メールボックス操作が既定でログに記録されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="4601e-160">An asterisk ( <sup>\*</sup> ) after the check mark indicates the mailbox action is logged by default for the logon type.</span></span>

- <span data-ttu-id="4601e-161">メールボックスへのフル アクセス許可を持つ管理者は、代理人と見なされる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4601e-161">Remember, an admin with Full Access permission to a mailbox is considered a delegate.</span></span>

|<span data-ttu-id="4601e-162">**メールボックス操作**</span><span class="sxs-lookup"><span data-stu-id="4601e-162">**Mailbox 1 action**</span></span>|<span data-ttu-id="4601e-163">**説明**</span><span class="sxs-lookup"><span data-stu-id="4601e-163">**Description**</span></span>|<span data-ttu-id="4601e-164">**管理者**</span><span class="sxs-lookup"><span data-stu-id="4601e-164">**Admin**</span></span>|<span data-ttu-id="4601e-165">**代理人**</span><span class="sxs-lookup"><span data-stu-id="4601e-165">**Delegate**</span></span>|<span data-ttu-id="4601e-166">**Owner**</span><span class="sxs-lookup"><span data-stu-id="4601e-166">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="4601e-167">**AddFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="4601e-167">**AddFolderPermissions**</span></span>|<span data-ttu-id="4601e-168">**注**: この値はメールボックス操作として認識されていますが、この値はすでに **UpdateFolderPermissions** 操作に含まれているため、別途監査されることはありません。</span><span class="sxs-lookup"><span data-stu-id="4601e-168">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="4601e-169">このため、この値は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="4601e-169">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="4601e-170">**ApplyRecord**</span><span class="sxs-lookup"><span data-stu-id="4601e-170">**ApplyRecord**</span></span>|<span data-ttu-id="4601e-171">アイテムをレコードとしてラベル付けします。</span><span class="sxs-lookup"><span data-stu-id="4601e-171">When an item is labeled as a record, four things happen:</span></span>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="4601e-175">**Copy**</span><span class="sxs-lookup"><span data-stu-id="4601e-175">**Copy**</span></span>|<span data-ttu-id="4601e-176">メッセージが別のフォルダーにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="4601e-176">A message was copied to another folder.</span></span>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|<span data-ttu-id="4601e-178">**Create**</span><span class="sxs-lookup"><span data-stu-id="4601e-178">**Create**</span></span>|<span data-ttu-id="4601e-179">アイテムが、メールボックスの予定表、連絡先、メモ、またはタスク フォルダーに作成されます (たとえば、新しい会議出席依頼が作成されます)。</span><span class="sxs-lookup"><span data-stu-id="4601e-179">An item is created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox; for example, a new meeting request is created. Note that message or folder creation isn't audited.</span></span> <span data-ttu-id="4601e-180">なお、メッセージの作成、送信、または受信は監査されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4601e-180">Note that creating, sending, or receiving a message isn't audited.</span></span> <span data-ttu-id="4601e-181">また、メールボックス フォルダーの作成も監査されません。</span><span class="sxs-lookup"><span data-stu-id="4601e-181">Also, creating a mailbox folder is not audited.</span></span>|<span data-ttu-id="4601e-182">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-182">Check mark</span></span>|<span data-ttu-id="4601e-183">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-183">Check mark</span></span>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="4601e-185">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="4601e-185">**Folder.Bind**</span></span>|<span data-ttu-id="4601e-p113">メールボックス フォルダーがアクセスされました。この操作は、管理者または委任されたユーザーがメールボックスを開いたときにも記録されます。 </span><span class="sxs-lookup"><span data-stu-id="4601e-p113">A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox. </span></span><br/><br/> <span data-ttu-id="4601e-188">**注**: 代理人により実行されたフォルダー バインド操作の監査レコードは統合されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-188">   Entries for folder bind actions performed by delegates are consolidated.</span></span> <span data-ttu-id="4601e-189">24 時間の間に行われたフォルダーへの個別のアクセスについて、監査レコードが 1 つ生成されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-189">One audit record is generated for individual folder access within 24 hour period.</span></span>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="4601e-192">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="4601e-192">**Hard-delete**</span></span>|<span data-ttu-id="4601e-193">メッセージが [回復可能なアイテム] フォルダーから削除されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-193">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="4601e-194">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-194">Check mark</span></span>|<span data-ttu-id="4601e-195">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-195">Check mark</span></span>|<span data-ttu-id="4601e-196">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-196">Check mark</span></span>|
|<span data-ttu-id="4601e-197">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="4601e-197">**MailboxLogin**</span></span>|<span data-ttu-id="4601e-198">ユーザーが自分のメールボックスにサインインしました。</span><span class="sxs-lookup"><span data-stu-id="4601e-198">The user signed in to their mailbox.</span></span> |||![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="4601e-200">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="4601e-200">**MessageBind**</span></span>|<span data-ttu-id="4601e-201">メッセージがプレビュー ウィンドウに表示されたか、開かれました。</span><span class="sxs-lookup"><span data-stu-id="4601e-201">A message was viewed in the preview pane or opened.</span></span>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|<span data-ttu-id="4601e-203">**ModifyFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="4601e-203">**ModifyFolderPermissions**</span></span>|<span data-ttu-id="4601e-204">**注**: この値はメールボックス操作として認識されていますが、この値はすでに **UpdateFolderPermissions** 操作に含まれているため、別途監査されることはありません。</span><span class="sxs-lookup"><span data-stu-id="4601e-204">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="4601e-205">このため、この値は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="4601e-205">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="4601e-206">**Move**</span><span class="sxs-lookup"><span data-stu-id="4601e-206">**Move**</span></span>|<span data-ttu-id="4601e-207">メッセージが別のフォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-207">A message was moved to another folder.</span></span>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="4601e-211">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="4601e-211">**MoveToDeletedItems**</span></span>|<span data-ttu-id="4601e-212">メッセージが削除され、削除済みアイテム フォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-212">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="4601e-213">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-213">Check mark</span></span>|<span data-ttu-id="4601e-214">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-214">Check mark</span></span>|<span data-ttu-id="4601e-215">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-215">Check mark</span></span>|
|<span data-ttu-id="4601e-216">**RecordDelete**</span><span class="sxs-lookup"><span data-stu-id="4601e-216">**RecordDelete**</span></span>|<span data-ttu-id="4601e-217">レコードとしてラベル付けされているアイテムが論理的に削除 ([回復可能なアイテム] フォルダーに移動) されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-217">An item that's labeled as a record was soft-deleted (moved to the Recoverable Items folder).</span></span> <span data-ttu-id="4601e-218">レコードとしてラベル付けされているアイテムは、完全に削除 ([回復可能なアイテム] フォルダーから削除) することはできません。</span><span class="sxs-lookup"><span data-stu-id="4601e-218">Items labeled as records can't be permanently deleted (purged from the Recoverable Items folder).</span></span>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="4601e-222">**RemoveFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="4601e-222">**RemoveFolderPermissions**</span></span>|<span data-ttu-id="4601e-223">**注**: この値はメールボックス操作として認識されていますが、この値はすでに **UpdateFolderPermissions** 操作に含まれているため、別途監査されることはありません。</span><span class="sxs-lookup"><span data-stu-id="4601e-223">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="4601e-224">このため、この値は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="4601e-224">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="4601e-225">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="4601e-225">**SendAs**</span></span>|<span data-ttu-id="4601e-p118">メッセージが、メールボックス所有者として送信するアクセス許可を使用して送信されました。これは、メールボックスの所有者から送信されているかのように、別のユーザーがメッセージを送信したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4601e-p118">A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.</span></span>|<span data-ttu-id="4601e-228">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-228">Check mark</span></span>|<span data-ttu-id="4601e-229">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-229">Check mark</span></span>||
|<span data-ttu-id="4601e-230">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="4601e-230">**SendOnBehalf**</span></span>|<span data-ttu-id="4601e-p119">SendOnBehalf アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者の代理人としてメッセージを送信しました)。この場合は、メッセージの名目上の送信者と実際の送信者が受信者に示されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-p119">A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>|<span data-ttu-id="4601e-234">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-234">Check mark</span></span>|<span data-ttu-id="4601e-235">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-235">Check mark</span></span>||
|<span data-ttu-id="4601e-236">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="4601e-236">**SoftDelete**</span></span>|<span data-ttu-id="4601e-p120">メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-p120">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="4601e-239">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-239">Check mark</span></span>|<span data-ttu-id="4601e-240">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-240">Check mark</span></span>|<span data-ttu-id="4601e-241">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-241">Check mark</span></span>|
|<span data-ttu-id="4601e-242">**Update**</span><span class="sxs-lookup"><span data-stu-id="4601e-242">**Update**</span></span>|<span data-ttu-id="4601e-243">メッセージまたはそのプロパティが変更されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-243">A message or its properties was changed.</span></span>|<span data-ttu-id="4601e-244">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-244">Check mark</span></span>|<span data-ttu-id="4601e-245">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-245">Check mark</span></span>|<span data-ttu-id="4601e-246">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-246">Check mark</span></span>|
|<span data-ttu-id="4601e-247">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="4601e-247">**UpdateCalendarDelegation**</span></span>|<span data-ttu-id="4601e-p121">メールボックスに予定表の委任が割り当てられました。予定表の委任により、同じ組織の他のユーザーに、メールボックス所有者の予定表を管理する権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-p121">A calendar delegation was assigned to a mailbox. Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>|<span data-ttu-id="4601e-250">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-250">Check mark</span></span>||<span data-ttu-id="4601e-251">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-251">Check mark</span></span>|
|<span data-ttu-id="4601e-252">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="4601e-252">**UpdateFolderPermissions**</span></span>|<span data-ttu-id="4601e-253">フォルダーのアクセス許可が変更されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-253">A folder permission was changed.</span></span> <span data-ttu-id="4601e-254">フォルダーのアクセス許可では、メールボックス内のフォルダーとそれらのフォルダーに格納されているメッセージにアクセスできる組織内のユーザーを制限します。</span><span class="sxs-lookup"><span data-stu-id="4601e-254">Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>|<span data-ttu-id="4601e-255">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-255">Check mark</span></span>|<span data-ttu-id="4601e-256">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-256">Check mark</span></span>|<span data-ttu-id="4601e-257">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-257">Check mark</span></span>|
|<span data-ttu-id="4601e-258">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="4601e-258">**UpdateInboxRules**</span></span>|<span data-ttu-id="4601e-259">受信トレイのルールが追加、削除、または変更されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-259">An inbox rule was added, removed, or changed.</span></span> <span data-ttu-id="4601e-260">受信トレイ ルールを使用して、指定された条件に基づいて受信トレイ内のメッセージを処理し、ルールの条件と一致した場合は、指定されたフォルダーへのメッセージの移動やメッセージの削除などの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4601e-260">An inbox rule has been added, removed, or changed. Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>|<span data-ttu-id="4601e-261">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-261">Check mark</span></span>|<span data-ttu-id="4601e-262">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-262">Check mark</span></span>|<span data-ttu-id="4601e-263">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-263">Check mark</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="4601e-264">いずれかのログオンの種類について、既定によるメールボックス監査の有効化を組織でオンにする*以前*にメールボックス操作をカスタマイズした場合は、カスタマイズした設定はメールボックスで保持され、このセクションで説明する既定のメールボックス操作はそれをオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="4601e-264">If you customized the mailbox actions to audit for any logon type *before* mailbox auditing on by default was enabled in your organization, the customized settings are preserved on the mailbox and aren't overwritten by the default mailbox actions as described in this section.</span></span> <span data-ttu-id="4601e-265">監査メールボックス操作を規定値に戻すには (これはいつでも行えます)、このトピックで後述する「[既定のメールボックス操作を復元する](#restore-the-default-mailbox-actions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4601e-265">To revert the audit mailbox actions to their default values (which you can do at any time), see the [Restore the default mailbox actions](#restore-the-default-mailbox-actions) section later in this topic.</span></span>

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a><span data-ttu-id="4601e-266">Office 365 グループ メールボックスでのメールボックス操作</span><span class="sxs-lookup"><span data-stu-id="4601e-266">Mailbox actions for Office 365 Group mailboxes</span></span>

<span data-ttu-id="4601e-267">既定によるメールボックス監査の有効化は Office 365 のグループ メールボックスでのメールボックス監査郎ログを可能にしますが、ログの内容はカスタマイズできません (いずれのログオンの種類についても、メールボックス操作を追加したり削除したりすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="4601e-267">Mailbox auditing on by default brings mailbox audit logging to Office 365 Group mailboxes, but you can't customize what's being logged (you can't add or remove mailbox actions that are logged for any logon type).</span></span>

<span data-ttu-id="4601e-268">次の表では、Office 365 のグループ メールボックスで、ログオンの種類ごとに既定でログに記録されるメールボックス操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4601e-268">The following table describes the mailbox actions that are logged by default on Office 365 Group mailboxes for each logon type.</span></span>

<span data-ttu-id="4601e-269">Office 365 のグループ メールボックスへのフル アクセス許可を持つ管理者は、代理人と見なされる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4601e-269">Remember, an admin with Full Access permission to an Office 365 Group mailbox is considered a delegate.</span></span>

|<span data-ttu-id="4601e-270">**メールボックス操作**</span><span class="sxs-lookup"><span data-stu-id="4601e-270">**Mailbox 1 action**</span></span>|<span data-ttu-id="4601e-271">**説明**</span><span class="sxs-lookup"><span data-stu-id="4601e-271">**Description**</span></span>|<span data-ttu-id="4601e-272">**管理者**</span><span class="sxs-lookup"><span data-stu-id="4601e-272">**Admin**</span></span>|<span data-ttu-id="4601e-273">**代理人**</span><span class="sxs-lookup"><span data-stu-id="4601e-273">**Delegate**</span></span>|<span data-ttu-id="4601e-274">**Owner**</span><span class="sxs-lookup"><span data-stu-id="4601e-274">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="4601e-275">**Create**</span><span class="sxs-lookup"><span data-stu-id="4601e-275">**Create**</span></span>|<span data-ttu-id="4601e-276">予定表アイテムを作成します。</span><span class="sxs-lookup"><span data-stu-id="4601e-276">Creation of a calendar Item.</span></span> <span data-ttu-id="4601e-277">なお、メッセージの作成、送信、または受信は監査されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4601e-277">Note that creating, sending, or receiving a message isn't audited.</span></span>|<span data-ttu-id="4601e-278">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-278">Check mark</span></span>|<span data-ttu-id="4601e-279">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-279">Check mark</span></span>||
|<span data-ttu-id="4601e-280">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="4601e-280">**Hard-delete**</span></span>|<span data-ttu-id="4601e-281">メッセージが [回復可能なアイテム] フォルダーから削除されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-281">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="4601e-282">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-282">Check mark</span></span>|<span data-ttu-id="4601e-283">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-283">Check mark</span></span>|<span data-ttu-id="4601e-284">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-284">Check mark</span></span>|
|<span data-ttu-id="4601e-285">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="4601e-285">**MoveToDeletedItems**</span></span>|<span data-ttu-id="4601e-286">メッセージが削除され、削除済みアイテム フォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-286">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="4601e-287">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-287">Check mark</span></span>|<span data-ttu-id="4601e-288">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-288">Check mark</span></span>|<span data-ttu-id="4601e-289">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-289">Check mark</span></span>|
|<span data-ttu-id="4601e-290">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="4601e-290">**SendAs**</span></span>|<span data-ttu-id="4601e-291">SendAs アクセス許可を使用してメッセージが送信されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-291">A message was sent using the SendAs permission.</span></span>|<span data-ttu-id="4601e-292">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-292">Check mark</span></span>|<span data-ttu-id="4601e-293">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-293">Check mark</span></span>||
|<span data-ttu-id="4601e-294">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="4601e-294">**SendOnBehalf**</span></span>|<span data-ttu-id="4601e-295">SendOnBehalf アクセス許可を使用してメッセージが送信されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-295">A message was sent using the SendOnBehalf permission.</span></span> |<span data-ttu-id="4601e-296">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-296">Check mark</span></span>|<span data-ttu-id="4601e-297">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-297">Check mark</span></span>||
|<span data-ttu-id="4601e-298">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="4601e-298">**SoftDelete**</span></span>|<span data-ttu-id="4601e-p126">メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-p126">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="4601e-301">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-301">Check mark</span></span>|<span data-ttu-id="4601e-302">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-302">Check mark</span></span>|<span data-ttu-id="4601e-303">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-303">Check mark</span></span>|
|<span data-ttu-id="4601e-304">**Update**</span><span class="sxs-lookup"><span data-stu-id="4601e-304">**Update**</span></span>|<span data-ttu-id="4601e-305">メッセージまたはそのプロパティが変更されました。</span><span class="sxs-lookup"><span data-stu-id="4601e-305">A message or its properties was changed.</span></span>|<span data-ttu-id="4601e-306">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-306">Check mark</span></span>|<span data-ttu-id="4601e-307">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-307">Check mark</span></span>|<span data-ttu-id="4601e-308">![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4601e-308">Check mark</span></span>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a><span data-ttu-id="4601e-309">ログオンの種類ごとの既定のメールボックス操作が記録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4601e-309">Verify that default mailbox actions are being logged for each logon type</span></span>

<span data-ttu-id="4601e-310">既定によるメールボックス監査の有効化により、すべてのメールボックスに新しい *DefaultAuditSet* プロパティが追加されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-310">Mailbox auditing on by defaults adds a new *DefaultAuditSet* property to all mailboxes.</span></span> <span data-ttu-id="4601e-311">このプロパティの値は、メールボックスで (Microsoft が管理する) 既定のメールボックス操作が監査 対象になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4601e-311">The value of this property indicates whether the default mailbox actions (managed by Microsoft) are being audited on the mailbox.</span></span>

<span data-ttu-id="4601e-312">ユーザー メールボックスまたは共有メールボックスの値を表示するには、\<MailboxIdentity\> をメールボックスの名前、エイリアス、メール アドレス、またはユーザー プリンシパル名 (username) で置き換え、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4601e-312">To display the value on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox and run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

<span data-ttu-id="4601e-313">Office 365 のグループ メールボックスの値を表示するには、\<MailboxIdentity\> を共有メールボックスの名前、エイリアス、またはメール アドレスで置き換え、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4601e-313">To display the value on Office 365 group mailboxes, replace \<MailboxIdentity\> with the name, alias, or email address of the shared mailbox and run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

<span data-ttu-id="4601e-314">値 `Admin, Delegate, Owner` は次を示します。</span><span class="sxs-lookup"><span data-stu-id="4601e-314">The value `Admin, Delegate, Owner` indicates:</span></span>

- <span data-ttu-id="4601e-315">3 つすべてのログオンの種類の既定メールボックス操作が監査対象になっています。</span><span class="sxs-lookup"><span data-stu-id="4601e-315">The default mailbox actions for all three logon types are being audited.</span></span> <span data-ttu-id="4601e-316">Office 365 のグループ メールボックスについて表示される値は、この値のみです。</span><span class="sxs-lookup"><span data-stu-id="4601e-316">Note that this is the only value you'll see on Office 365 Group mailboxes.</span></span>

- <span data-ttu-id="4601e-317">管理者は、ユーザー メールボックスまたは共有メールボックスで、いずれのログオンの種類についても監査対象のメールボックス操作を*まだ*変更していません。</span><span class="sxs-lookup"><span data-stu-id="4601e-317">An admin *has not* changed the audited mailbox actions for any logon type on a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="4601e-318">これは、既定によるメールボックス監査の有効化が最初に有効化されたときの既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="4601e-318">Note this is the default state after mailbox auditing on by default is initially turned on in your organization.</span></span>

<span data-ttu-id="4601e-319">監査対象のメールボックス操作を特定のログオンの種類について管理者が少しでも変更した場合は (**Set-Mailbox** コマンドレットで *AuditAdmin*、*AuditDelegate*、または *AuditOwner* のパラメーターを使用して)、異なるプロパティ値になります。</span><span class="sxs-lookup"><span data-stu-id="4601e-319">If an admin has ever changed the mailbox actions that are audited for a logon type (by using the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet), the property value will be different.</span></span>

<span data-ttu-id="4601e-320">たとえば、ユーザー メールボックスまたは共有メールボックスでの *DefaultAuditSet* プロパティの値が `Owner` の場合は、次を示します。</span><span class="sxs-lookup"><span data-stu-id="4601e-320">For example, the value `Owner` for the *DefaultAuditSet* property on a user mailbox or shared mailbox indicates:</span></span>

- <span data-ttu-id="4601e-321">メールボックス所有者の既定メールボックス操作が監査対象になっています。</span><span class="sxs-lookup"><span data-stu-id="4601e-321">The default mailbox actions for the mailbox owner are being audited.</span></span>

- <span data-ttu-id="4601e-322">ログオンの種類 `Delegate` および `Admin` の監査対象のメールボックス操作は、既定の操作から変更されています。</span><span class="sxs-lookup"><span data-stu-id="4601e-322">The audited mailbox actions for the `Delegate` and `Admin` logon types have been changed from the default actions.</span></span>

<span data-ttu-id="4601e-323">*DefaultAuditSet* プロパティの値が空白の場合は、ユーザー メールボックスまたは共有メールボックスで 3 つすべてのログオンの種類のメールボックス操作が変更されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="4601e-323">A blank value for the *DefaultAuditSet* property indicates the mailbox actions for all three logon types have been changed on the user mailbox or a shared mailbox.</span></span>

<span data-ttu-id="4601e-324">詳細については、このトピック内の「[既定でログに記録されるメールボックス操作を変更または復元する](#change-or-restore-mailbox-actions-logged-by-default)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4601e-324">For more information, see the [Change or restore mailbox actions logged by default](#change-or-restore-mailbox-actions-logged-by-default) section in this topic</span></span>

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a><span data-ttu-id="4601e-325">ログへの記録対象となっている、メールボックスでのメールボックス操作を表示する</span><span class="sxs-lookup"><span data-stu-id="4601e-325">Display the mailbox actions that are being logged on mailboxes</span></span>

<span data-ttu-id="4601e-326">現在ログへの記録対象となっている、ユーザー メールボックスまたは共有メールボックスでのメールボックス操作を表示するには、\<MailboxIdentity\> をメールボックスの名前、エイリアス、メール アドレス、またはユーザー プリンシパル名 (username) で置き換え、Exchange Online PowerShell で次のコマンドを 1 つまたは複数実行します。</span><span class="sxs-lookup"><span data-stu-id="4601e-326">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="4601e-327">Office 365 グループ メールボックスについて、次の **Get-Mailbox** コマンドに `-GroupMailbox` スイッチを追加できますが、表示される値は無視してください。</span><span class="sxs-lookup"><span data-stu-id="4601e-327">Although you can add the `-GroupMailbox` switch to the following **Get-Mailbox** commands for Office 365 Group mailboxes, don't believe the values you see.</span></span> <span data-ttu-id="4601e-328">Office 365 のグループ メールボックスでの監査対象の既定の静的なメールボックス操作については、このトピックで前述の「[Office 365 グループ メールボックスでのメールボックス操作](#mailbox-actions-for-office-365-group-mailboxes)」セクションで説明しています。</span><span class="sxs-lookup"><span data-stu-id="4601e-328">The default and static mailbox actions that are audited for Office 365 Group mailboxes are described in the [Mailbox actions for Office 365 Group mailboxes](#mailbox-actions-for-office-365-group-mailboxes) section earlier in this topic.</span></span>

#### <a name="owner-actions"></a><span data-ttu-id="4601e-329">所有者操作</span><span class="sxs-lookup"><span data-stu-id="4601e-329">Owner actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a><span data-ttu-id="4601e-330">代理人操作</span><span class="sxs-lookup"><span data-stu-id="4601e-330">Delegate actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a><span data-ttu-id="4601e-331">管理者操作</span><span class="sxs-lookup"><span data-stu-id="4601e-331">Admin actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a><span data-ttu-id="4601e-332">既定でログに記録されるメールボックス操作を変更または復元する</span><span class="sxs-lookup"><span data-stu-id="4601e-332">Change or restore mailbox actions logged by default</span></span>

<span data-ttu-id="4601e-333">前述のように、既定によるメールボックス監査の有効化のメリットの 1 つは、監査対象メールボックス操作の管理が必要ないことです。</span><span class="sxs-lookup"><span data-stu-id="4601e-333">As previously explained, one of the key benefits of having mailbox auditing on by default is: you don't need to manage the mailboxes actions that are audited.</span></span> <span data-ttu-id="4601e-334">管理は Microsoft により自動的に行われ、既定で監視対象となる新しいメールボックス操作がリリースされると、それが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-334">Microsoft does this for you and we'll automatically add new mailbox actions to be audited by default as they're released.</span></span>

<span data-ttu-id="4601e-335">ただし、ユーザー メールボックスおよび共有メールボックスについて、別のメールボックス操作のセットを監査することが組織で要求されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4601e-335">However, your organization might be required to audit a different set of mailbox actions for user mailboxes and shared mailboxes.</span></span> <span data-ttu-id="4601e-336">このセクションの手順では、各ログオンの種類について監査対象のメールボックス操作を変更する方法と、Microsoft が管理する既定の操作に戻す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4601e-336">The procedures in this section show you how to change the mailbox actions that are audited for each logon type, and how to revert back to the Microsoft-managed default actions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4601e-337">ユーザー メールボックスまたは共有メールボックスについてログに記録されるメールボックス操作を次の手順に従ってカスタマイズする場合、Microsoft がリリースする新しい既定のメールボックス操作は、これらのメールボックスでは自動的に監査されません。</span><span class="sxs-lookup"><span data-stu-id="4601e-337">If you use the following procedures to customize the mailbox actions that are logged on user mailboxes or shared mailboxes, any new default mailbox actions released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="4601e-338">新しいメールボックス操作は、操作のカスタム リストに手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4601e-338">You'll need to manually add any new mailbox actions to your customized list of actions.</span></span>

### <a name="change-the-mailbox-actions-to-audit"></a><span data-ttu-id="4601e-339">監査するメールボックス操作を変更する</span><span class="sxs-lookup"><span data-stu-id="4601e-339">Change the mailbox actions to audit</span></span>

<span data-ttu-id="4601e-340">**Set-Mailbox** コマンドレットで *AuditAdmin*、*AuditDelegate*、または *AuditOwner* のパラメーターを使用すると、監査対象になっているメールボックス操作をユーザー メールボックスおよび共有メールボックスについて変更できます (Office 365 のグループ メールボックスの監査対象操作はカスタマイズできません)。</span><span class="sxs-lookup"><span data-stu-id="4601e-340">You can use the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet to change the mailbox actions that are audited for user mailboxes and shared mailboxes (audited actions for Office 365 group mailboxes can't be customized).</span></span>

<span data-ttu-id="4601e-341">2 つの方法によってメールボックス操作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4601e-341">You can use two different methods to specify the mailbox actions:</span></span>

- <span data-ttu-id="4601e-342">次の構文を使用して、既存のメールボックス操作を*置き換え*ます (上書き)します: `action1,action2,...actionN`。</span><span class="sxs-lookup"><span data-stu-id="4601e-342">*Replace* (overwrite) the existing mailbox actions by using this syntax: `action1,action2,...actionN`.</span></span>

- <span data-ttu-id="4601e-343">次のいずれかの構文を使用して、他の既存の値に影響を与えることなくメールボックス操作を*追加または削除*します: `@{Add="action1","action2",..."actionN"}` または`@{Remove="action1","action2",..."actionN"}`。　</span><span class="sxs-lookup"><span data-stu-id="4601e-343">*Add or remove* mailbox actions without affecting other existing values by using this syntax: `@{Add="action1","action2",..."actionN"}` or `@{Remove="action1","action2",..."actionN"}`.</span></span>

<span data-ttu-id="4601e-344">この例では、既定操作を SoftDelete および HardDelete で置き換えることにより、"Gabriela Laureano" という名前のメールボックスについて管理者のメールボックス操作を変更します。</span><span class="sxs-lookup"><span data-stu-id="4601e-344">This example changes the admin mailbox actions for the mailbox named "Gabriela Laureano" by overwriting the default actions with SoftDelete and HardDelete.</span></span>

```
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

<span data-ttu-id="4601e-345">この例では、laura@contoso.onmicrosoft.com に MailboxLogin という所有者操作を追加します。</span><span class="sxs-lookup"><span data-stu-id="4601e-345">This example adds the MailboxLogin owner action to the mailbox laura@contoso.onmicrosoft.com.</span></span>

```
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

<span data-ttu-id="4601e-346">この例では、"Team Discussion" というメールボックスについて、MoveToDeletedItems という代理人操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="4601e-346">This example removes the MoveToDeletedItems delegate action for the Team Discussion mailbox.</span></span>

```
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

<span data-ttu-id="4601e-347">いずれの方法を使用した場合でも、ユーザー メールボックスまたは共有メールボックスでの監査対象のメールボックス操作をカスタマイズすると、次のことが起こります。</span><span class="sxs-lookup"><span data-stu-id="4601e-347">Regardless of the method you use, customizing the audited mailbox actions on user mailboxes or shared mailboxes has the following results:</span></span>

- <span data-ttu-id="4601e-348">カスタマイズしたログオンの種類に関しては、監査対象のメールボックス操作は Microsoft では管理されなくなります。</span><span class="sxs-lookup"><span data-stu-id="4601e-348">For the logon type that you customized, the audited mailbox actions are no longer managed by Microsoft.</span></span>

- <span data-ttu-id="4601e-349">[上で説明した通り](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)、カスタマイズしたログオンの種類は、メールボックスの *DefaultAuditSet* プロパティの値で表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="4601e-349">The logon type that you customized is no longer displayed in the *DefaultAuditSet* property value for the mailbox as [previously described](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).</span></span>

### <a name="restore-the-default-mailbox-actions"></a><span data-ttu-id="4601e-350">既定のメールボックスを復元する</span><span class="sxs-lookup"><span data-stu-id="4601e-350">Restore the default mailbox actions</span></span>

<span data-ttu-id="4601e-351">監査対象になっている、ユーザー メールボックスまたは共有メールボックスについてのメールボックス操作をカスタマイズした場合、1 つまたは複数のログオンの種類について、次の構文を使用して既定のメールボックス操作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="4601e-351">If you customized the mailbox actions that are audited on a user mailbox or a shared mailbox, you can restore the default mailbox actions for one or all logon types by using this syntax:</span></span>

```
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

<span data-ttu-id="4601e-352">複数の *DefaultAuditSet* の値をコンマで区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="4601e-352">You can specify multiple values separated by commas.</span></span>

<span data-ttu-id="4601e-353">**注**: 次の手順は、Office 365 のグループ メールボックスには適用されません ([こちら](#mailbox-actions-for-office-365-group-mailboxes)で説明するように、これらのメールボックスは既定の操作に制限されています)。</span><span class="sxs-lookup"><span data-stu-id="4601e-353">**Note**: The following procedures don't apply to Office 365 Group mailboxes (they're limited to the default actions as described [here](#mailbox-actions-for-office-365-group-mailboxes)).</span></span>

<span data-ttu-id="4601e-354">この例では、mark@contoso.onmicrosoft.com というメールボックスで、すべてのログオンの種類について既定の監査対象メールボックス操作を復元します。</span><span class="sxs-lookup"><span data-stu-id="4601e-354">This example restores the default audited mailbox actions for all logon types on the mailbox mark@contoso.onmicrosoft.com.</span></span>

```
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

<span data-ttu-id="4601e-355">この例では、chris@contoso.onmicrosoft.com というメールボックスで、管理者のログオンの種類について既定の監査対象メールボックス操作を復元します。代理人および所有者のログオンの種類については、カスタマイズした監査対象メールボックス操作を残します。</span><span class="sxs-lookup"><span data-stu-id="4601e-355">This example restores the default audited mailbox actions for the Admin logon type on the mailbox chris@contoso.onmicrosoft.com, but leaves the customized audited mailbox actions for the Delegate and Owner logon types.</span></span>

```
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

<span data-ttu-id="4601e-356">既定の監査対象メールボックス操作をいずれかのログオンの種類について復元すると、次のことが起こります。</span><span class="sxs-lookup"><span data-stu-id="4601e-356">Restoring he default audited mailbox actions for a logon type has the following results:</span></span>

- <span data-ttu-id="4601e-357">そのログオンの種類について、現在のメールボックス操作のリストは既定のメールボックス操作に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="4601e-357">The current list of mailbox actions is replaced with the default mailbox actions for the logon type.</span></span>

- <span data-ttu-id="4601e-358">Microsoft がリリースする新しいメールボックス操作は、そのログオンの種類について監査対象操作のリストに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-358">Any new mailbox actions that are released by Microsoft are automatically added to the list of audited actions for the logon type.</span></span>

- <span data-ttu-id="4601e-359">復元されたログオンの種類が含まれるよう、メールボックスの *DefaultAuditSet* プロパティの値が更新されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-359">The *DefaultAuditSet* property value for the mailbox is updated to include the restored logon type.</span></span>

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a><span data-ttu-id="4601e-360">既定によるメールボックス監査の有効化を組織で無効にする</span><span class="sxs-lookup"><span data-stu-id="4601e-360">Turn off mailbox auditing on by default for your organization</span></span>

<span data-ttu-id="4601e-361">次のコマンドを Exchange Online PowerShell で実行すると、既定によるメールボックス監査の有効化を組織で無効にできます。</span><span class="sxs-lookup"><span data-stu-id="4601e-361">You can turn off mailbox auditing on by default for your entire organization by running the following command in Exchange Online PowerShell:</span></span>

```
Set-OrganizationConfig -AuditDisabled $true
```

<span data-ttu-id="4601e-362">既定によるメールボックス監査の有効化を無効にすると、次のことが起こります。</span><span class="sxs-lookup"><span data-stu-id="4601e-362">Turning off mailbox auditing on by default has the following results:</span></span>

- <span data-ttu-id="4601e-363">メールボックスの監査が組織で無効になります。</span><span class="sxs-lookup"><span data-stu-id="4601e-363">Mailbox auditing is disabled for your organization.</span></span>

- <span data-ttu-id="4601e-364">既定によるメールボックス監査の有効化を無効にした時点から、個別のメールボックスで監査が有効化されている場合 (メールボックスの *AuditEnabled* プロパティは **True** です) でも、メールボックス操作は監査されなくなります。</span><span class="sxs-lookup"><span data-stu-id="4601e-364">From the time you disabled mailbox auditing on by default, no mailbox actions are audited, even if auditing is enabled on a mailbox (the *AuditEnabled* property on the mailbox is **True**).</span></span>

- <span data-ttu-id="4601e-365">新しいメールボックスでメールボックス監査が有効化されず、新しいまたは既存のメールボックスで *AuditEnabled* プロパティを **True** に設定しても、無視されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-365">Mailbox auditing is not enabled for new mailboxes and setting the *AuditEnabled* property on a new or existing mailbox to **True** will be ignored.</span></span>

- <span data-ttu-id="4601e-366">(**MailboxAuditBypassAssociation** コマンドレットを使用して構成された) メールボックスの監査バイパスの関連付けの設定が無視されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-366">Any mailbox audit bypass association settings (configured by using the **Set-MailboxAuditBypassAssociation** cmdlet) are ignored.</span></span>

- <span data-ttu-id="4601e-367">既存のメールボックス監査レコードは、レコードの監査ログ有効期限が切れるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-367">Existing mailbox audit records are retained until the audit log age limit for the the record expires.</span></span>

### <a name="turn-on-mailbox-auditing-on-by-default"></a><span data-ttu-id="4601e-368">既定によるメールボックス監査の有効化をオンにする</span><span class="sxs-lookup"><span data-stu-id="4601e-368">Turn on mailbox auditing on by default</span></span>

<span data-ttu-id="4601e-369">既定によるメールボックス監査の有効化を再び組織でオンにするには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4601e-369">To turn mailbox auditing back on for your organization, run the following command in Exchange Online PowerShell:</span></span>

```
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a><span data-ttu-id="4601e-370">メールボックス監査ログをバイパスする</span><span class="sxs-lookup"><span data-stu-id="4601e-370">Bypass a user account from mailbox audit logging</span></span>

<span data-ttu-id="4601e-371">現時点では、既定によるメールボックス監査の有効化が組織でオンになっている場合は、特定のメールボックスでメールボックス監査を無効にできません。</span><span class="sxs-lookup"><span data-stu-id="4601e-371">Currently, you can't disable mailbox auditing for specific mailboxes when mailbox auditing on by default is turned on in your organization.</span></span> <span data-ttu-id="4601e-372">たとえば、 メールボックス プロパティ *AuditEnabled* を **False** に設定しても、無視されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-372">For example, setting the *AuditEnabled* mailbox property to **False** is ignored.</span></span>

<span data-ttu-id="4601e-373">ただし、*Exchange Online PowerShell* で **Set-MailboxAuditBypassAssociation** コマンドレットを使用すると、操作が行われた場所に関わらず、特定のユーザーによるすべてのメールボックス操作がログに記録されないようにできます。</span><span class="sxs-lookup"><span data-stu-id="4601e-373">However, you can still use the **Set-MailboxAuditBypassAssociation** cmdlet in Exchange Online PowerShell to prevent *any and all* mailbox actions by the specified users from being logged, regardless where the actions occur.</span></span> <span data-ttu-id="4601e-374">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4601e-374">For example:</span></span>

- <span data-ttu-id="4601e-375">バイパスされたユーザーが実行するメールボックス所有者操作はログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="4601e-375">Mailbox owner actions performed by the bypassed users aren't logged.</span></span>

- <span data-ttu-id="4601e-376">バイパスされたユーザーが他のユーザーのメールボックス (共有メールボックスを含む) で実行する代理人操作はログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="4601e-376">Delegate actions performed by the bypassed users on other users' mailboxes (including shared mailboxes) aren't logged.</span></span>

- <span data-ttu-id="4601e-377">バイパスされたユーザーが実行する管理者操作はログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="4601e-377">Admin actions performed by the bypassed users aren't logged.</span></span>

<span data-ttu-id="4601e-378">特定のユーザーについてメールボックス監査ログをバイパスするには、\<MailboxIdentity\> をそのユーザーの名前、メール アドレス、エイリアス、またはユーザー プリンシパル名 (username) で置き換え、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4601e-378">To bypass mailbox audit logging for a specific user, replace \<MailboxIdentity\> with the name, email address, alias, or user principal name (username) of the user and run the following command:</span></span>

```
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

<span data-ttu-id="4601e-379">特定のユーザーについて監査がバイパスされていることを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4601e-379">To verify that auditing is bypassed for the specified user, run the following command:</span></span>

```
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

<span data-ttu-id="4601e-380">値 **True** は、そのユーザーについてメールボックス監査ログがバイパスされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="4601e-380">The value **True** indicates that mailbox audit logging is bypassed for the user.</span></span>

## <a name="more-information"></a><span data-ttu-id="4601e-381">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4601e-381">More information</span></span>

- <span data-ttu-id="4601e-382">既定では、メールボックス監査ログ レコードは 90 日間保持された後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4601e-382">By default, mailbox audit log entries are retained in the mailbox for 90 days and then deleted.</span></span> <span data-ttu-id="4601e-383">Exchange Online PowerShell を使用して **Set-mailbox** コマンドレットで *AuditLogAgeLimit* のパラメーターを使用すると、監査ログ レコードの有効期限を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4601e-383">You can change the age limit for audit log records by using the *AuditLogAgeLimit* parameter on the **Set-Mailbox** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="4601e-384">ただし、この値を大きくしても、Microsoft 365 監査ログで 90 日より古いイベントを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="4601e-384">However, increasing this value doesn't allow you to search for events that are older than 90 days in the Microsoft 365 audit log.</span></span>

  <span data-ttu-id="4601e-385">有効期限を延ばす場合、90 日より古いレコードをユーザーのメールボックス監査ログで検索するには、Exchange Online PowerShell で [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4601e-385">If you increase the age limit, you need to use the [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) cmdlet in Exchange Online PowerShell to search the user's mailbox audit log for records that are older than 90 days.</span></span>

- <span data-ttu-id="4601e-386">既定によるメールボックス監査の有効化を組織でオンにする以前に特定のメールボックスの *AuditLogAgeLimit* プロパティを変更した場合は、そのメールボックスの既存の監査ログの有効期限は変更されません。</span><span class="sxs-lookup"><span data-stu-id="4601e-386">If you've changed the *AuditLogAgeLimit* property for a mailbox prior to mailbox auditing on by default being turned on for organization, the mailbox's existing audit log age limit isn't changed.</span></span> <span data-ttu-id="4601e-387">つまり、既定によるメールボックス監査の有効化は、メールボックスの監査記録の現在の有効期限に影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="4601e-387">In other words, mailbox auditing on by default doesn't effect the current age limit for mailbox audit records.</span></span>

- <span data-ttu-id="4601e-388">Office 365 のグループ メールボックスで *AuditLogAgeLimit* の値を変更するには、**Set-mailbox** コマンドに `-GroupMailbox` スイッチを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4601e-388">To change the *AuditLogAgeLimit* value on an Office 365 Group mailbox, you need to include the `-GroupMailbox` switch in the **Set-Mailbox** command.</span></span>

- <span data-ttu-id="4601e-389">メールボックス監査ログ レコードは、各ユーザーのメールボックス内の [回復可能なアイテム] フォルダー内のサブフォルダー ([*Audits*] という名前) に保存されています。</span><span class="sxs-lookup"><span data-stu-id="4601e-389">Mailbox audit log records are stored in a subfolder (named *Audits*) in the Recoverable Items folder in each user's mailbox.</span></span> <span data-ttu-id="4601e-390">メールボックス監査レコードと [回復可能なアイテム] フォルダーについては、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4601e-390">Keep the following things in mind about mailbox audit records and the Recoverable Items folder:</span></span>

  - <span data-ttu-id="4601e-391">メールボックス監査レコードは、既定で 30 GB (警告表示クォータは 20 GB) となっている [回復可能なアイテム] フォルダーの記憶域のクォータを消費します。</span><span class="sxs-lookup"><span data-stu-id="4601e-391">Mailbox audit records count against the storage quota of the Recoverable Items folder, which is 30GB by default (the warning quota is 20 GB).</span></span> <span data-ttu-id="4601e-392">次の場合に、記憶域のクォータは自動的に 100 GB (警告表示クォータは 90 GB) に増えます:</span><span class="sxs-lookup"><span data-stu-id="4601e-392">The storage quota is automatically increased to 100 GB (with a 90 GB warning quota) when:</span></span>

    - <span data-ttu-id="4601e-393">メールボックスがホールドの対象となった場合。</span><span class="sxs-lookup"><span data-stu-id="4601e-393">A hold is placed on a mailbox.</span></span>

    - <span data-ttu-id="4601e-394">コンプライアンス センターで、メールボックスがアイテム保持ポリシーに割り当てられている場合。</span><span class="sxs-lookup"><span data-stu-id="4601e-394">The mailbox is assigned to a retention policy in the Compliance Center.</span></span>

  - <span data-ttu-id="4601e-395">メールボックス監査レコードは、[[回復可能なアイテム] フォルダーでのフォルダーの制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="4601e-395">Mailbox audit records also count against the [folder limit for the Recoverable Items folder](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits).</span></span> <span data-ttu-id="4601e-396">[Audits] サブフォルダーは、最大 300 万件のアイテム (監査レコード) を格納できます。</span><span class="sxs-lookup"><span data-stu-id="4601e-396">A maximum of 3 million items (audit records) can be stored in the Audits subfolder.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4601e-397">記憶域のクォータや回復可能なアイテム フォルダーのフォルダー制限が既定によるメールボックス監査の有効化の影響を受けることは、通常ありません。</span><span class="sxs-lookup"><span data-stu-id="4601e-397">It's unlikely that mailbox auditing on by default will impact the storage quota or the folder limit for the Recoverable Items folder.</span></span>

    - <span data-ttu-id="4601e-398">[回復可能なアイテム] フォルダー内の [Audits] サブフォルダー内のアイテムのサイズと数を表示するには、Exchange PowerShell で次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4601e-398">You can run the following command in Exchange Online PowerShell to display the size and number of items in the Audits subfolder in the Recoverable Items folder:</span></span>

      ```
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - <span data-ttu-id="4601e-399">[回復可能なアイテム] フォルダー内の監査ログ レコードに直接アクセスすることはできません。メールボックス監査レコードを検索して表示するには、**Search-MailboxAuditLog** コマンドレットを使用するか、Microsoft 365 監査ログを検索します。</span><span class="sxs-lookup"><span data-stu-id="4601e-399">You can't directly access an audit log record in the Recoverable Items folder; instead, you use the **Search-MailboxAuditLog** cmdlet or search the Microsoft 365 audit log to find and view mailbox audit records.</span></span>

- <span data-ttu-id="4601e-400">メールボックスがホールドの対象になっていたり、コンプライアンス センターでアイテム保持ポリシーに割り当てられていたりする場合でも、監査ログ レコードは、メールボックスの *AuditLogAgeLimit* プロパティが指定する期間 (既定では 90 日間) 保持されます。　</span><span class="sxs-lookup"><span data-stu-id="4601e-400">If a mailbox is placed on hold or assigned to a retention policy in the Compliance Center, audit log records are still retained for the duration that's defined by the mailbox's *AuditLogAgeLimit* property (90 days by default).</span></span> <span data-ttu-id="4601e-401">ホールドの対象になっているメールボックスの監査ログ レコードをより長期間保持するには、メールボックスの *AuditLogAgeLimit* 値を大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4601e-401">To retain audit log records longer for mailboxes on hold, you need to increase mailbox's *AuditLogAgeLimit* value.</span></span>
