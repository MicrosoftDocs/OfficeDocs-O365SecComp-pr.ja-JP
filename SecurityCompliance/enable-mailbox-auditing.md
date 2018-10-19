---
title: Office 365 でメールボックスの監査を有効にする
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 、Office 365 では、メールボックス監査ログの記録によって、メールボックスの所有者、デリゲート、および管理者のメールボックスへのアクセスをログに記録するのにできます。既定では、Office 365 のメールボックスの監査有効になっていないです。メールボックスのログ出力のメールボックスの監査を有効にした後、Office 365 の監査ログ メールボックスで実行されるアクティビティを検索できます。
ms.openlocfilehash: 6d3de226e7c0e03be824b14e1b16fadaae3f040e
ms.sourcegitcommit: 8294182d4dd124f035a221de0b90159ef7eec4ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2018
ms.locfileid: "25639666"
---
# <a name="enable-mailbox-auditing-in-office-365"></a><span data-ttu-id="f5d73-105">Office 365 でメールボックスの監査を有効にする</span><span class="sxs-lookup"><span data-stu-id="f5d73-105">Enable mailbox auditing in Office 365</span></span>
  
<span data-ttu-id="f5d73-p102">、Office 365 では、メールボックス監査ログの記録によって、メールボックスの所有者、デリゲート、および管理者のメールボックスへのアクセスをログに記録するのにできます。既定では、Office 365 のメールボックスの監査有効になっていないです。つまり、Office 365 の監査ログ メールボックス アクティビティを検索すると、結果のイベントを監査するメールボックスが表示されません。ログオン ユーザーのメールボックスのメールボックス監査を有効にすると、メールボックス アクティビティの監査ログを検索することができます。さらに、メールボックスの監査ログを有効に、管理者、代理人によって実行されるいくつかのアクションと所有者が既定でログに記録されます。ログなどを検索する追加のアクションは、手順 3 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p102">In Office 365, you can turn on mailbox audit logging to log mailbox access by mailbox owners, delegates, and administrators. By default, mailbox auditing in Office 365 isn't turned on. That means mailbox auditing events won't appear in the results when you search the Office 365 audit log for mailbox activity. But after you turn on mailbox audit logging for a user mailbox, you can search the audit log for mailbox activity. Additionally, when mailbox audit logging is turned on, some actions performed by administrators, delegates, and owners are logged by default. To log (and then search for) additional actions, see Step 3.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f5d73-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="f5d73-112">Before you begin</span></span>
  
- <span data-ttu-id="f5d73-p103">Exchange オンライン PowerShell を使用してメールボックスを有効にする必要があるログを監査します。Office 365 のセキュリティを使用することはできません&amp;コンプライアンス センターまたは、Exchange 管理センターです。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p103">You have to use Exchange Online PowerShell to enable mailbox audit logging. You can't use the Office 365 Security &amp; Compliance Center or the Exchange admin center.</span></span>
    
- <span data-ttu-id="f5d73-115">Office 365 グループまたはマイクロソフトのチームでチームに関連付けられているメールボックスのログ出力のメールボックスの監査を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f5d73-115">You can't enable mailbox audit logging for the mailbox that's associated with an Office 365 Group or a team in Microsoft Teams.</span></span>
    
- <span data-ttu-id="f5d73-116">ユーザーのメールボックスに対するフル アクセスのアクセス許可を割り当てられた管理者が代理人ユーザーと見なされます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-116">An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span>
  
## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="f5d73-117">オンライン PowerShell を交換する手順 1: 接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-117">Step 1: Connect to Exchange Online PowerShell</span></span>

1. <span data-ttu-id="f5d73-118">ローカル コンピューターで、Windows PowerShell を開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-118">On your local computer, open Windows PowerShell and run the following command.</span></span>
   
    ```
    $UserCredential = Get-Credential
    ```

2. <span data-ttu-id="f5d73-119">**[Windows PowerShell 資格情報の要求]** ダイアログ ボックスで、Office 365 のグローバル管理者アカウントのユーザー名とパスワードを入力し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5d73-119">In the **Windows PowerShell Credential Request** dialog box, type user name and password for an Office 365 global admin account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="f5d73-120">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-120">Run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="f5d73-121">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-121">Run the following command.</span></span>

    ```
    Import-PSSession $Session
    ```
   
4. <span data-ttu-id="f5d73-122">Exchange Online 組織に接続されたことを検証するために、次のコマンドを実行して、組織内のすべてのメールボックスのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-122">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```
  
<span data-ttu-id="f5d73-123">詳細については、または Exchange Online 組織への接続に関する問題がある場合は、「[リモート PowerShell による Exchange への接続](https://go.microsoft.com/fwlink/p/?LinkId=517283)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5d73-123">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span>
  
## <a name="step-2-enable-mailbox-audit-logging"></a><span data-ttu-id="f5d73-124">手順 2: メールボックス監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="f5d73-124">Step 2: Enable mailbox audit logging</span></span>

<span data-ttu-id="f5d73-p104">オンラインの Exchange 組織に接続した後、メールボックスの監査ログ メールボックスを有効にするのに PowerShell を使用します。代わりに、組織内のすべてのメールボックスに対するメールボックスの監査を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p104">After you connect to your Exchange Online organization, use PowerShell to enable mailbox audit logging for a mailbox. Alternatively, you can enable mailbox auditing for all mailboxes in your organization.</span></span>
  
<span data-ttu-id="f5d73-127">この例では、メールボックスの監査ログ Pilar Pinilla のメールボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f5d73-127">This example enables mailbox audit logging for Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

<span data-ttu-id="f5d73-128">この例では、組織内のすべてのユーザー メールボックスに対して、メールボックス監査ログを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="f5d73-128">This example enables mailbox audit logging for all user mailboxes in your organization.</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a><span data-ttu-id="f5d73-129">手順 3: 監査する所有者の操作を指定する</span><span class="sxs-lookup"><span data-stu-id="f5d73-129">Step 3: Specify owner actions to audit</span></span>

<span data-ttu-id="f5d73-p105">メールボックスの監査を有効にすると、既定でメールボックスの所有者によって実行されるいくつかの操作が監査されます。監査するには、他の所有者アクションを指定する必要があります。ボックスの一覧と既定でログに記録される操作を所有者とその他のアクションを監査することの説明については、[メールボックスの監査アクション](#mailbox-auditing-actions)」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p105">When you enable auditing for a mailbox, some actions performed by the mailbox owner are audited by default. You have to specify other owner actions to audit. See the table in the [Mailbox auditing actions](#mailbox-auditing-actions) section for a list and description of owner actions that are logged by default and the other actions that can be audited.</span></span> 
  
<span data-ttu-id="f5d73-p106">この例では、 **MailboxLogin**と**HardDelete**の所有者の操作を監査 Pilar Pinilla のメールボックスをメールボックスに追加します。次の使用例では、メールボックスの監査が既に有効になっているこのメールボックスを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p106">This example adds the **MailboxLogin** and **HardDelete** owner actions to mailbox auditing for Pilar Pinilla's mailbox. This example assumes that mailbox auditing has already been enabled for this mailbox.</span></span> 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

<span data-ttu-id="f5d73-p107">この例では、ログ Don Hall のメールボックスのメールボックス監査を有効にし、メールボックスの所有者によって実行される**MailboxLogin**の操作だけを記録することを指定します。この例で UpdateFolderPermissions の既定のアクションが上書きされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p107">This example enables mailbox audit logging for Don Hall's mailbox and specifies that only the **MailboxLogin** action performed by the mailbox owner will be logged. Note that this example overwrites the default UpdateFolderPermissions action.</span></span> 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
<span data-ttu-id="f5d73-p108">この例では、 **MailboxLogin**、 **HardDelete**、および**SoftDelete**の所有者の操作を組織内のすべてのメールボックスに追加します。次の使用例は、メールボックスの監査が既に有効になっているすべてのメールボックスのものとします。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p108">This example adds the **MailboxLogin**, **HardDelete**, and **SoftDelete** owner actions to all mailboxes in the organization. This example assumes that mailbox auditing has already been enabled for all mailboxes.</span></span> 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f5d73-139">これが機能したことを知る方法</span><span class="sxs-lookup"><span data-stu-id="f5d73-139">How do you know this worked?</span></span>

<span data-ttu-id="f5d73-140">あるメールボックスに対してメールボックス監査ログが正常に有効にされたかを確認するには、**Get-Mailbox** コマンドレットを実行して、そのメールボックスの監査設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-140">To verify that you have successfully enabled mailbox audit logging for a mailbox, use the **Get-Mailbox** cmdlet to retrieve the auditing settings for that mailbox.</span></span> 
  
<span data-ttu-id="f5d73-141">この例では、Pilar Pinilla の監査設定を取得しています。</span><span class="sxs-lookup"><span data-stu-id="f5d73-141">This example retrieves the auditing settings for Pilar Pinilla.</span></span>

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
<span data-ttu-id="f5d73-142">この例では、組織内のすべてのユーザー メールボックスの監査設定を取得しています。</span><span class="sxs-lookup"><span data-stu-id="f5d73-142">This example retrieves the auditing settings for all user mailboxes in your organization.</span></span>

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
<span data-ttu-id="f5d73-143">**AuditEnabled**プロパティの値が**True**のメールボックスの監査を確認するログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f5d73-143">A value of **True** for the **AuditEnabled** property verifies that mailbox audit logging is enabled.</span></span> 
    
## <a name="mailbox-auditing-actions"></a><span data-ttu-id="f5d73-144">メールボックスの監査アクション</span><span class="sxs-lookup"><span data-stu-id="f5d73-144">Mailbox auditing actions</span></span>
  
<span data-ttu-id="f5d73-p109">次の表に、メールボックスがログに記録されるアクションのログを監査します。テーブルは、別のユーザー ログオンの種類のアクションを記録することが含まれています。テーブルでは、 **No**は、そのログオンの種類のアクションを記録できないことを示します。アスタリスク ( **\*** ) ことを示します、メールボックスのメールボックス監査ログ収集時に、既定でアクションを記録するが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p109">The following table lists the actions that can be logged by mailbox audit logging. The table includes which action can be logged for the different user logon types. In the table, a **No** indicates that an action can't be logged for that logon type. An asterisk ( **\*** ) indicates that the action is logged by default when mailbox audit logging is enabled for the mailbox.</span></span> 
  
|<span data-ttu-id="f5d73-149">**操作**</span><span class="sxs-lookup"><span data-stu-id="f5d73-149">**Action**</span></span>|<span data-ttu-id="f5d73-150">**説明**</span><span class="sxs-lookup"><span data-stu-id="f5d73-150">**Description**</span></span>|<span data-ttu-id="f5d73-151">**管理者**</span><span class="sxs-lookup"><span data-stu-id="f5d73-151">**Admin**</span></span>|<span data-ttu-id="f5d73-152">**代理人\*\*\***</span><span class="sxs-lookup"><span data-stu-id="f5d73-152">**Delegate\*\*\***</span></span>|<span data-ttu-id="f5d73-153">**所有者**</span><span class="sxs-lookup"><span data-stu-id="f5d73-153">**Owner**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f5d73-154">**コピーする**</span><span class="sxs-lookup"><span data-stu-id="f5d73-154">**Copy**</span></span> <br/> |<span data-ttu-id="f5d73-155">メッセージが別のフォルダーにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="f5d73-155">A message was copied to another folder.</span></span>  <br/> |<span data-ttu-id="f5d73-156">○</span><span class="sxs-lookup"><span data-stu-id="f5d73-156">Yes</span></span>  <br/> |<span data-ttu-id="f5d73-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="f5d73-157">No</span></span>  <br/> |<span data-ttu-id="f5d73-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="f5d73-158">No</span></span>  <br/> |
|<span data-ttu-id="f5d73-159">**Create**</span><span class="sxs-lookup"><span data-stu-id="f5d73-159">**Create**</span></span> <br/> |<span data-ttu-id="f5d73-p110">アイテムが、メールボックスの予定表、連絡先、メモ、または仕事フォルダーの作成します。たとえば、新しい会議出席依頼が作成されます。作成、送信、またはメッセージの受信が監査されていないことに注意してください。また、メールボックス フォルダーの作成は監査されません。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p110">An item is created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox; for example, a new meeting request is created. Note that creating, sending, or receiving a message isn't audited. Also, creating a mailbox folder is not audited.</span></span>  <br/> |<span data-ttu-id="f5d73-163">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-163">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-164">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-164">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-165">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-165">Yes</span></span>  <br/> |
|<span data-ttu-id="f5d73-166">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="f5d73-166">**FolderBind**</span></span> <br/> |<span data-ttu-id="f5d73-p111">メールボックス フォルダーがアクセスされました。この操作は、管理者または委任されたユーザーがメールボックスを開いたときにも記録されます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p111">A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox.</span></span>  <br/> |<span data-ttu-id="f5d73-169">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-169">Yes</span></span>  <br/> |<span data-ttu-id="f5d73-170">はい\*\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-170">Yes\*\*</span></span>  <br/> |<span data-ttu-id="f5d73-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="f5d73-171">No</span></span>  <br/> |
|<span data-ttu-id="f5d73-172">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="f5d73-172">**HardDelete**</span></span> <br/> |<span data-ttu-id="f5d73-173">メッセージが [回復可能なアイテム] フォルダーから削除されました。</span><span class="sxs-lookup"><span data-stu-id="f5d73-173">A message was purged from the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="f5d73-174">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-174">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-175">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-175">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-176">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-176">Yes</span></span>  <br/> |
|<span data-ttu-id="f5d73-177">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="f5d73-177">**MailboxLogin**</span></span> <br/> |<span data-ttu-id="f5d73-178">ユーザーが自分のメールボックスにサインインしました。</span><span class="sxs-lookup"><span data-stu-id="f5d73-178">The user signed in to their mailbox.</span></span>  <br/> |<span data-ttu-id="f5d73-179">X</span><span class="sxs-lookup"><span data-stu-id="f5d73-179">No</span></span>  <br/> |<span data-ttu-id="f5d73-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="f5d73-180">No</span></span>  <br/> |<span data-ttu-id="f5d73-181">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-181">Yes</span></span>  <br/> |
|<span data-ttu-id="f5d73-182">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="f5d73-182">**MessageBind**</span></span> <br/> |<span data-ttu-id="f5d73-183">メッセージがプレビュー ウィンドウに表示されました (または開かれました)。</span><span class="sxs-lookup"><span data-stu-id="f5d73-183">A message was viewed in the preview pane or opened.</span></span>  <br/> |<span data-ttu-id="f5d73-184">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-184">Yes</span></span>  <br/> |<span data-ttu-id="f5d73-185">いいえ</span><span class="sxs-lookup"><span data-stu-id="f5d73-185">No</span></span>  <br/> |<span data-ttu-id="f5d73-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="f5d73-186">No</span></span>  <br/> |
|<span data-ttu-id="f5d73-187">**移動する**</span><span class="sxs-lookup"><span data-stu-id="f5d73-187">**Move**</span></span> <br/> |<span data-ttu-id="f5d73-188">メッセージが別のフォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="f5d73-188">A message was moved to another folder.</span></span>  <br/> |<span data-ttu-id="f5d73-189">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-189">Yes</span></span>  <br/> |<span data-ttu-id="f5d73-190">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-190">Yes</span></span>  <br/> |<span data-ttu-id="f5d73-191">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-191">Yes</span></span>  <br/> |
|<span data-ttu-id="f5d73-192">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="f5d73-192">**MoveToDeletedItems**</span></span> <br/> |<span data-ttu-id="f5d73-193">メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="f5d73-193">A message was deleted and moved to the Deleted Items folder.</span></span>  <br/> |<span data-ttu-id="f5d73-194">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-194">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-195">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-195">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-196">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-196">Yes</span></span>  <br/> |
|<span data-ttu-id="f5d73-197">**送信者**</span><span class="sxs-lookup"><span data-stu-id="f5d73-197">**SendAs**</span></span> <br/> |<span data-ttu-id="f5d73-p112">SendAs アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者を装ってメッセージを送信しました)。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p112">A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.</span></span>  <br/> |<span data-ttu-id="f5d73-200">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-200">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-201">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-201">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="f5d73-202">No</span></span>  <br/> |
|<span data-ttu-id="f5d73-203">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="f5d73-203">**SendOnBehalf**</span></span> <br/> |<span data-ttu-id="f5d73-p113">SendOnBehalf アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者の代理人としてメッセージを送信しました)。この場合は、メッセージの名目上の送信者と実際の送信者が受信者に示されます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p113">A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>  <br/> |<span data-ttu-id="f5d73-207">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-207">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-208">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-208">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="f5d73-209">No</span></span>  <br/> |
|<span data-ttu-id="f5d73-210">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="f5d73-210">**SoftDelete**</span></span> <br/> |<span data-ttu-id="f5d73-p114">メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p114">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="f5d73-213">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-213">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-214">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-214">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-215">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-215">Yes</span></span>  <br/> |
|<span data-ttu-id="f5d73-216">**更新する**</span><span class="sxs-lookup"><span data-stu-id="f5d73-216">**Update**</span></span> <br/> |<span data-ttu-id="f5d73-217">メッセージまたはそのプロパティが変更されました。</span><span class="sxs-lookup"><span data-stu-id="f5d73-217">A message or its properties was changed.</span></span>  <br/> |<span data-ttu-id="f5d73-218">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-218">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-219">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-219">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-220">はい</span><span class="sxs-lookup"><span data-stu-id="f5d73-220">Yes</span></span>  <br/> |
|<span data-ttu-id="f5d73-221">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="f5d73-221">**UpdateCalendarDelegation**</span></span> <br/> |<span data-ttu-id="f5d73-p115">カレンダーの委任は、メールボックスに割り当てられていました。カレンダーの委任には、他のユーザーにメールボックス所有者の予定表を管理するために同じ組織の権限が与えられます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p115">A calendar delegation was assigned to a mailbox. Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>  <br/> |<span data-ttu-id="f5d73-224">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-224">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-225">いいえ</span><span class="sxs-lookup"><span data-stu-id="f5d73-225">No</span></span>  <br/> |<span data-ttu-id="f5d73-226">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-226">Yes\*</span></span>  <br/> |
|<span data-ttu-id="f5d73-227">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="f5d73-227">**UpdateFolderPermissions**</span></span> <br/> |<span data-ttu-id="f5d73-p116">フォルダーのアクセス許可が変更されました。フォルダーのアクセス許可のコントロールは、組織内のどのユーザーがメールボックスとそれらのフォルダー内にあるメッセージのフォルダーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p116">A folder permission was changed. Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>  <br/> |<span data-ttu-id="f5d73-230">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-230">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-231">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-231">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-232">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-232">Yes\*</span></span>  <br/> |
|<span data-ttu-id="f5d73-233">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="f5d73-233">**UpdateInboxRules**</span></span> <br/> |<span data-ttu-id="f5d73-p117">受信トレイのルールが追加、削除、または変更します。受信トレイ ルールは、指定した条件に基づいて、ユーザーの受信トレイでメッセージを処理するために使用および指定したフォルダーにメッセージを移動またはメッセージを削除するなど、ルールの条件が満たされるときにアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p117">An inbox rule has been added, removed, or changed. Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>  <br/> |<span data-ttu-id="f5d73-236">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-236">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-237">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-237">Yes\*</span></span>  <br/> |<span data-ttu-id="f5d73-238">はい\*</span><span class="sxs-lookup"><span data-stu-id="f5d73-238">Yes\*</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="f5d73-239"><sup>\*</sup>メールボックスの監査が有効になっている場合は、既定で監査されます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-239"><sup>\*</sup> Audited by default if auditing is enabled for a mailbox.</span></span><br/><br/>  <span data-ttu-id="f5d73-p118"><sup>\*\*</sup>デリゲートによって実行される、フォルダー バインド操作のエントリは統合されます。24 時間の期間内の個々 のフォルダーへのアクセスには、1 つのログ エントリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p118"><sup>\*\*</sup> Entries for folder bind actions performed by delegates are consolidated. One log entry is generated for individual folder access within a time span of 24 hours.</span></span><br/><br/><span data-ttu-id="f5d73-242"><sup>\*\*\*</sup>ユーザーのメールボックスにフル アクセスのアクセス許可が割り当てられている管理者は、代理ユーザーと見なされます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-242"><sup>\*\*\*</sup> An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span> 
  
<span data-ttu-id="f5d73-p119">特定の種類のメールボックス操作を監査することが必要なくなった場合は、これらの操作を無効にするメールボックスの監査ログの構成を変更します。既存のログ エントリは、監査ログ ・ エントリーの保存期間保存期間の制限に到達するまでパージは。監査ログ エントリの保有期間の詳細については、[監査ログが Office 365 のセキュリティとコンプライアンス センターで](search-the-audit-log-in-security-and-compliance.md#before-you-begin)検索」を開始する前に」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p119">If you no longer require certain types of mailbox actions to be audited, you should modify the mailbox's audit logging configuration to disable those actions. Existing log entries aren't purged until the retention age limit for audit log entries is reached. For more information about the retention age for audit log entries, see the "Before you begin" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#before-you-begin).</span></span>
  
## <a name="more-infotab"></a>[<span data-ttu-id="f5d73-246">詳細</span><span class="sxs-lookup"><span data-stu-id="f5d73-246">More info</span></span>](#tab/)
  
- <span data-ttu-id="f5d73-p120">メールボックス アクティビティが記録されていないことを検索するには、Office 365 の監査ログを使用します。特定のユーザーのメールボックスの利用状況を検索できます。次のスクリーン ショットは、Office 365 の監査ログを検索することができますメールボックス アクティビティの一覧を表示します。これらのアクティビティには、このトピックの「メールボックスの監査アクション」セクションに記載されているのと同じ動作に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p120">Use the Office 365 audit log to search for mailbox activity that have been logged. You can search for activity for a specific user mailbox. The following screenshot shows a list of mailbox activities that you can search for in the Office 365 audit log. Note that these activities are the same actions that are described in the "Mailbox auditing actions" section in this topic.</span></span>
    
    ![アクティビティ」ドロップ ダウン リストで「メールボックス アクティビティを交換する」を選択して、Office 365 の監査ログ メールボックス監査アクションを検索することができます](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    <span data-ttu-id="f5d73-252">次の表は、各メールボックスの利用状況を検索してアクションを監査の対応するメールボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-252">The following table describes each mailbox activity that you can search for and shows the corresponding mailbox auditing action.</span></span>
    
    |<span data-ttu-id="f5d73-253">**監査ログ内のアクティビティ**</span><span class="sxs-lookup"><span data-stu-id="f5d73-253">**Activity in the audit log**</span></span>|<span data-ttu-id="f5d73-254">**メールボックスの監査アクション**</span><span class="sxs-lookup"><span data-stu-id="f5d73-254">**Mailbox auditing action**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f5d73-255">作成されたメールボックス アイテム</span><span class="sxs-lookup"><span data-stu-id="f5d73-255">Created mailbox item</span></span>  <br/> |<span data-ttu-id="f5d73-256">Create</span><span class="sxs-lookup"><span data-stu-id="f5d73-256">Create</span></span>  <br/> |
    |<span data-ttu-id="f5d73-257">別のフォルダーにコピーされたメッセージ</span><span class="sxs-lookup"><span data-stu-id="f5d73-257">Copied messages to another folder</span></span>  <br/> |<span data-ttu-id="f5d73-258">Copy</span><span class="sxs-lookup"><span data-stu-id="f5d73-258">Copy</span></span>  <br/> |
    |<span data-ttu-id="f5d73-259">ユーザーのメールボックスにサインイン</span><span class="sxs-lookup"><span data-stu-id="f5d73-259">User signed in to mailbox</span></span>  <br/> |<span data-ttu-id="f5d73-260">MailboxLogin</span><span class="sxs-lookup"><span data-stu-id="f5d73-260">MailboxLogin</span></span>  <br/> |
    |<span data-ttu-id="f5d73-261">代理送信アクセス許可を使用してメッセージを送信</span><span class="sxs-lookup"><span data-stu-id="f5d73-261">Sent message using Send On Behalf permissions</span></span>  <br/> |<span data-ttu-id="f5d73-262">SendOnBehalf</span><span class="sxs-lookup"><span data-stu-id="f5d73-262">SendOnBehalf</span></span>  <br/> |
    |<span data-ttu-id="f5d73-263">メールボックスから削除されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="f5d73-263">Purged messages from the mailbox</span></span>  <br/> |<span data-ttu-id="f5d73-264">HardDelete</span><span class="sxs-lookup"><span data-stu-id="f5d73-264">HardDelete</span></span>  <br/> |
    |<span data-ttu-id="f5d73-265">メッセージを削除済みアイテム フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-265">Moved messages to Deleted Items folder</span></span>  <br/> |<span data-ttu-id="f5d73-266">MoveToDeletedItems</span><span class="sxs-lookup"><span data-stu-id="f5d73-266">MoveToDeletedItems</span></span>  <br/> |
    |<span data-ttu-id="f5d73-267">メッセージを別のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-267">Moved messages to another folder</span></span>  <br/> |<span data-ttu-id="f5d73-268">Move</span><span class="sxs-lookup"><span data-stu-id="f5d73-268">Move</span></span>  <br/> |
    |<span data-ttu-id="f5d73-269">送信者アクセス許可を使用してメッセージを送信</span><span class="sxs-lookup"><span data-stu-id="f5d73-269">Sent message using Send As permissions</span></span>  <br/> |<span data-ttu-id="f5d73-270">送信者</span><span class="sxs-lookup"><span data-stu-id="f5d73-270">SendAs</span></span>  <br/> |
    |<span data-ttu-id="f5d73-271">更新されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="f5d73-271">Updated message</span></span>  <br/> |<span data-ttu-id="f5d73-272">Update</span><span class="sxs-lookup"><span data-stu-id="f5d73-272">Update</span></span>  <br/> |
    |<span data-ttu-id="f5d73-273">削除済みアイテム フォルダーから削除されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="f5d73-273">Deleted messages from Deleted Items folder</span></span>  <br/> |<span data-ttu-id="f5d73-274">SoftDelete</span><span class="sxs-lookup"><span data-stu-id="f5d73-274">SoftDelete</span></span>  <br/> |
    |<span data-ttu-id="f5d73-275">フォルダーに対するアクセス許可を追加しました</span><span class="sxs-lookup"><span data-stu-id="f5d73-275">Added permissions to folder</span></span>  <br/> |<span data-ttu-id="f5d73-276">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="f5d73-276">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="f5d73-277">フォルダーのアクセス許可を変更しました。</span><span class="sxs-lookup"><span data-stu-id="f5d73-277">Modified permissions of folder</span></span>  <br/> |<span data-ttu-id="f5d73-278">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="f5d73-278">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="f5d73-279">フォルダーから削除されたアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f5d73-279">Removed permissions from folder</span></span>  <br/> |<span data-ttu-id="f5d73-280">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="f5d73-280">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="f5d73-281">予定表フォルダーを代理人アクセス権を持つユーザーを追加または削除されました。</span><span class="sxs-lookup"><span data-stu-id="f5d73-281">Added or removed user with delegate access to calendar folder</span></span>  <br/> |<span data-ttu-id="f5d73-282">UpdateCalendarDelegation</span><span class="sxs-lookup"><span data-stu-id="f5d73-282">UpdateCalendarDelegation</span></span>  <br/> |
   
    <span data-ttu-id="f5d73-p121">前のスクリーン ショットに示すように**代理人のメールボックスのアクセス許可を追加**および**削除済みメールボックス アクセス許可の委任**のアクティビティが操作を監査するメールボックスと関連付けられていないことに注意してください。管理者が割り当てられているまたは FullAccess メールボックスのアクセス許可を削除するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p121">Note that the **Added delegate mailbox permissions** and **Removed delegate mailbox permissions** activities shown in the previous screenshot aren't related to mailbox auditing actions. They indicate whether an administrator assigned or removed the FullAccess mailbox permission.</span></span> 
    
    <span data-ttu-id="f5d73-285">Office 365 の監査ログの詳細についてを参照してください[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。</span><span class="sxs-lookup"><span data-stu-id="f5d73-285">For information about the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
- <span data-ttu-id="f5d73-286">以下のシナリオでは、メールボックスに管理者のみがアクセスするものと見なしています。</span><span class="sxs-lookup"><span data-stu-id="f5d73-286">Mailboxes are considered to be accessed by an administrator only in the following scenarios:</span></span>
    
  - <span data-ttu-id="f5d73-287">Exchange Online または Office 365 のコンテンツの検索でのインプレース電子証拠開示を使用して、メールボックスを検索します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-287">In-Place eDiscovery in Exchange Online or Content Search in Office 365 is used to search a mailbox.</span></span>
    
  - <span data-ttu-id="f5d73-288">[Microsoft Exchange Server MAPI エディター](https://go.microsoft.com/fwlink/p/?linkId=204086)を使用してメールボックスにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="f5d73-288">[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) is used to access the mailbox.</span></span> 
    
- <span data-ttu-id="f5d73-289">メールボックスの監査ログを有効にすると、ログオンの種類 (管理者、代理人、または所有者) ごとにログに記録するユーザー操作 (メッセージへのアクセス、移動、削除など) も指定できます。 </span><span class="sxs-lookup"><span data-stu-id="f5d73-289">When you enable audit logging for a mailbox, you can also specify which user actions (for example, accessing, moving, or deleting a message) will be logged for each logon type (admin, delegate, or owner).</span></span>
    
- <span data-ttu-id="f5d73-290">メールボックス監査ログを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5d73-290">To disable mailbox audit logging, run the following command:</span></span>

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- <span data-ttu-id="f5d73-p122">**Get メールボックス**コマンドレットを実行すると、ユーザーの種類ごとに監査する操作は表示されません。ですが、特定のユーザーのログオンの種類のすべての監査アクションを表示するのには、次のコマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p122">The actions that are audited for each type of user aren't displayed when you run the **Get-Mailbox** cmdlet. But you can run the following commands to display all the audited actions for a specific user logon type.</span></span> 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- <span data-ttu-id="f5d73-p123">メールボックスの監査ログをエクスポートし、1 つまたは複数のユーザーへのエントリを指定できます。レポートと監査ログの各エントリには、アクションを実行したユーザーのアクションを実行するときは、および操作が成功したかどうかの情報が含まれています。詳細については、[メールボックス監査ログのエクスポート](https://go.microsoft.com/fwlink/p/?LinkID=404104)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5d73-p123">You can also export a mailbox audit log and specify the entries to include for one or more users. Each entry in the report and the audit log includes information about who performed the action and when, the action performed , and whether the action was successful. For more information, see [Export mailbox audit logs](https://go.microsoft.com/fwlink/p/?LinkID=404104).</span></span>
