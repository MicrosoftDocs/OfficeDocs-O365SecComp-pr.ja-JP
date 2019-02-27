---
title: Office 365 でメールボックスの監査を有効にする
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: Office 365 では、メールボックス監査ログを有効にして、メールボックスの所有者、代理人、および管理者によるメールボックスへのアクセスをログに記録できます。既定では、Office 365 のメールボックスの監査は有効になっていません。メールボックスのメールボックス監査ログを有効にした後、メールボックスに対して実行されたアクティビティの Office 365 監査ログを検索することができます。
ms.openlocfilehash: a9bc84bad8532dd546d5ce3e2f149151967050d6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295920"
---
# <a name="enable-mailbox-auditing-in-office-365"></a><span data-ttu-id="0667c-105">Office 365 でメールボックスの監査を有効にする</span><span class="sxs-lookup"><span data-stu-id="0667c-105">Enable mailbox auditing in Office 365</span></span>
  
<span data-ttu-id="0667c-p102">Office 365 では、メールボックス監査ログを有効にして、メールボックスの所有者、代理人、および管理者によるメールボックスへのアクセスをログに記録できます。既定では、Office 365 のメールボックスの監査は有効になっていません。これは、Office 365 監査ログでメールボックスアクティビティを検索したときに、メールボックス監査イベントが結果に表示されないことを意味します。ただし、ユーザーメールボックスのメールボックス監査ログを有効にした後は、メールボックスアクティビティの監査ログを検索することができます。さらに、メールボックス監査ログが有効になっている場合、管理者、代理人、および所有者によって実行される操作の中には、既定で記録されるものがあります。その他の操作をログに記録して検索するには、「手順3」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0667c-p102">In Office 365, you can turn on mailbox audit logging to log mailbox access by mailbox owners, delegates, and administrators. By default, mailbox auditing in Office 365 isn't turned on. That means mailbox auditing events won't appear in the results when you search the Office 365 audit log for mailbox activity. But after you turn on mailbox audit logging for a user mailbox, you can search the audit log for mailbox activity. Additionally, when mailbox audit logging is turned on, some actions performed by administrators, delegates, and owners are logged by default. To log (and then search for) additional actions, see Step 3.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0667c-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="0667c-112">Before you begin</span></span>
  
- <span data-ttu-id="0667c-p103">メールボックス監査ログを有効にするには、Exchange Online PowerShell を使用する必要があります。Office 365 セキュリティ&amp;コンプライアンスセンターまたは Exchange 管理センターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0667c-p103">You have to use Exchange Online PowerShell to enable mailbox audit logging. You can't use the Office 365 Security &amp; Compliance Center or the Exchange admin center.</span></span>
    
- <span data-ttu-id="0667c-115">Office 365 グループまたは Microsoft Teams のチームに関連付けられているメールボックスのメールボックス監査ログを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0667c-115">You can't enable mailbox audit logging for the mailbox that's associated with an Office 365 Group or a team in Microsoft Teams.</span></span>
    
- <span data-ttu-id="0667c-116">ユーザーのメールボックスに対するフル アクセスのアクセス許可を割り当てられた管理者が代理人ユーザーと見なされます。</span><span class="sxs-lookup"><span data-stu-id="0667c-116">An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span>
  
## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="0667c-117">手順 1: Exchange Online PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="0667c-117">Step 1: Connect to Exchange Online PowerShell</span></span>

1. <span data-ttu-id="0667c-118">ローカル コンピューターで、Windows PowerShell を開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0667c-118">On your local computer, open Windows PowerShell and run the following command.</span></span>
   
    ```
    $UserCredential = Get-Credential
    ```

2. <span data-ttu-id="0667c-119">**[Windows PowerShell 資格情報の要求]** ダイアログ ボックスで、Office 365 のグローバル管理者アカウントのユーザー名とパスワードを入力し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0667c-119">In the **Windows PowerShell Credential Request** dialog box, type user name and password for an Office 365 global admin account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="0667c-120">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0667c-120">Run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="0667c-121">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0667c-121">Run the following command.</span></span>

    ```
    Import-PSSession $Session
    ```
   
4. <span data-ttu-id="0667c-122">Exchange Online 組織に接続されたことを検証するために、次のコマンドを実行して、組織内のすべてのメールボックスのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="0667c-122">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```
  
<span data-ttu-id="0667c-123">詳細については、または Exchange Online 組織への接続に関する問題がある場合は、「[リモート PowerShell による Exchange への接続](https://go.microsoft.com/fwlink/p/?LinkId=517283)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0667c-123">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span>
  
## <a name="step-2-enable-mailbox-audit-logging"></a><span data-ttu-id="0667c-124">手順 2: メールボックス監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="0667c-124">Step 2: Enable mailbox audit logging</span></span>

<span data-ttu-id="0667c-p104">Exchange Online 組織に接続した後、PowerShell を使用してメールボックスのメールボックス監査ログを有効にします。または、組織内のすべてのメールボックスに対してメールボックスの監査を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0667c-p104">After you connect to your Exchange Online organization, use PowerShell to enable mailbox audit logging for a mailbox. Alternatively, you can enable mailbox auditing for all mailboxes in your organization.</span></span>
  
<span data-ttu-id="0667c-127">この例では、Pilar Pinilla のメールボックスのメールボックス監査ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0667c-127">This example enables mailbox audit logging for Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

<span data-ttu-id="0667c-128">この例では、組織内のすべてのユーザー メールボックスに対して、メールボックス監査ログを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="0667c-128">This example enables mailbox audit logging for all user mailboxes in your organization.</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a><span data-ttu-id="0667c-129">手順 3: 監査する所有者の操作を指定する</span><span class="sxs-lookup"><span data-stu-id="0667c-129">Step 3: Specify owner actions to audit</span></span>

<span data-ttu-id="0667c-p105">メールボックスの監査を有効にすると、メールボックスの所有者によって実行される操作の一部が既定で監査されます。監査する他の所有者アクションを指定する必要があります。既定でログに記録される所有者操作の一覧と、監査可能なその他の操作については、「 [Mailbox auditing actions](#mailbox-auditing-actions) 」セクションの表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0667c-p105">When you enable auditing for a mailbox, some actions performed by the mailbox owner are audited by default. You have to specify other owner actions to audit. See the table in the [Mailbox auditing actions](#mailbox-auditing-actions) section for a list and description of owner actions that are logged by default and the other actions that can be audited.</span></span> 
  
<span data-ttu-id="0667c-p106">この例では、Pilar Pinilla のメールボックスのメールボックス監査に、 **MailboxLogin**および**ハード削除**の所有者アクションを追加します。この例では、メールボックスの監査がこのメールボックスで既に有効になっていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0667c-p106">This example adds the **MailboxLogin** and **HardDelete** owner actions to mailbox auditing for Pilar Pinilla's mailbox. This example assumes that mailbox auditing has already been enabled for this mailbox.</span></span> 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

<span data-ttu-id="0667c-p107">この例では、Don Hall のメールボックスのメールボックス監査ログを有効にし、メールボックスの所有者によって実行された**MailboxLogin**アクションのみがログに記録されるように指定します。この例では、既定の updatefolderpermissions アクションを上書きすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0667c-p107">This example enables mailbox audit logging for Don Hall's mailbox and specifies that only the **MailboxLogin** action performed by the mailbox owner will be logged. Note that this example overwrites the default UpdateFolderPermissions action.</span></span> 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
<span data-ttu-id="0667c-p108">この例では、組織内のすべてのメールボックスに**MailboxLogin**、**ハード削除**、および**softdelete** owner アクションを追加します。この例では、メールボックスの監査がすべてのメールボックスに対して既に有効になっていると仮定します。</span><span class="sxs-lookup"><span data-stu-id="0667c-p108">This example adds the **MailboxLogin**, **HardDelete**, and **SoftDelete** owner actions to all mailboxes in the organization. This example assumes that mailbox auditing has already been enabled for all mailboxes.</span></span> 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="0667c-139">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="0667c-139">How do you know this worked?</span></span>

<span data-ttu-id="0667c-140">あるメールボックスに対してメールボックス監査ログが正常に有効にされたかを確認するには、**Get-Mailbox** コマンドレットを実行して、そのメールボックスの監査設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="0667c-140">To verify that you have successfully enabled mailbox audit logging for a mailbox, use the **Get-Mailbox** cmdlet to retrieve the auditing settings for that mailbox.</span></span> 
  
<span data-ttu-id="0667c-141">この例では、Pilar Pinilla の監査設定を取得しています。</span><span class="sxs-lookup"><span data-stu-id="0667c-141">This example retrieves the auditing settings for Pilar Pinilla.</span></span>

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
<span data-ttu-id="0667c-142">この例では、組織内のすべてのユーザー メールボックスの監査設定を取得しています。</span><span class="sxs-lookup"><span data-stu-id="0667c-142">This example retrieves the auditing settings for all user mailboxes in your organization.</span></span>

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
<span data-ttu-id="0667c-143">**auditenabled**プロパティの値を**True**に設定すると、メールボックス監査ログが有効になっていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="0667c-143">A value of **True** for the **AuditEnabled** property verifies that mailbox audit logging is enabled.</span></span> 
    
## <a name="mailbox-auditing-actions"></a><span data-ttu-id="0667c-144">メールボックス監査アクション</span><span class="sxs-lookup"><span data-stu-id="0667c-144">Mailbox auditing actions</span></span>
  
<span data-ttu-id="0667c-p109">次の表に、メールボックス監査ログによって記録できるアクションを示します。表には、さまざまなユーザーログオンの種類に対してログに記録できるアクションが記載されています。表の [**いいえ**] は、そのログオンの種類に対してアクションをログに記録できないことを示します。アスタリスク ( **\*** ) は、メールボックスのメールボックス監査ログが有効になっている場合に、アクションが既定でログに記録されることを示します。</span><span class="sxs-lookup"><span data-stu-id="0667c-p109">The following table lists the actions that can be logged by mailbox audit logging. The table includes which action can be logged for the different user logon types. In the table, a **No** indicates that an action can't be logged for that logon type. An asterisk ( **\*** ) indicates that the action is logged by default when mailbox audit logging is enabled for the mailbox.</span></span> 
  
|<span data-ttu-id="0667c-149">**操作**</span><span class="sxs-lookup"><span data-stu-id="0667c-149">**Action**</span></span>|<span data-ttu-id="0667c-150">**説明**</span><span class="sxs-lookup"><span data-stu-id="0667c-150">**Description**</span></span>|<span data-ttu-id="0667c-151">**管理者**</span><span class="sxs-lookup"><span data-stu-id="0667c-151">**Admin**</span></span>|<span data-ttu-id="0667c-152">**代理人\*\*\***</span><span class="sxs-lookup"><span data-stu-id="0667c-152">**Delegate\*\*\***</span></span>|<span data-ttu-id="0667c-153">**所有者**</span><span class="sxs-lookup"><span data-stu-id="0667c-153">**Owner**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0667c-154">**コピーする**</span><span class="sxs-lookup"><span data-stu-id="0667c-154">**Copy**</span></span> <br/> |<span data-ttu-id="0667c-155">メッセージが別のフォルダーにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="0667c-155">A message was copied to another folder.</span></span>  <br/> |<span data-ttu-id="0667c-156">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-156">Yes</span></span>  <br/> |<span data-ttu-id="0667c-157">×</span><span class="sxs-lookup"><span data-stu-id="0667c-157">No</span></span>  <br/> |<span data-ttu-id="0667c-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="0667c-158">No</span></span>  <br/> |
|<span data-ttu-id="0667c-159">**Create**</span><span class="sxs-lookup"><span data-stu-id="0667c-159">**Create**</span></span> <br/> |<span data-ttu-id="0667c-p110">メールボックスの予定表、連絡先、メモ、または仕事フォルダーでアイテムが作成されます。たとえば、新しい会議出席依頼が作成されます。メッセージの作成、送信、または受信は監査されないことにご注意ください。また、メールボックス フォルダーの作成も監視されません。</span><span class="sxs-lookup"><span data-stu-id="0667c-p110">An item is created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox; for example, a new meeting request is created. Note that creating, sending, or receiving a message isn't audited. Also, creating a mailbox folder is not audited.</span></span>  <br/> |<span data-ttu-id="0667c-163">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-163">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-164">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-164">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-165">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-165">Yes</span></span>  <br/> |
|<span data-ttu-id="0667c-166">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="0667c-166">**FolderBind**</span></span> <br/> |<span data-ttu-id="0667c-p111">メールボックス フォルダーがアクセスされました。この操作は、管理者または委任されたユーザーがメールボックスを開いたときにも記録されます。</span><span class="sxs-lookup"><span data-stu-id="0667c-p111">A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox.</span></span>  <br/> |<span data-ttu-id="0667c-169">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-169">Yes</span></span>  <br/> |<span data-ttu-id="0667c-170">はい\*\*</span><span class="sxs-lookup"><span data-stu-id="0667c-170">Yes\*\*</span></span>  <br/> |<span data-ttu-id="0667c-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="0667c-171">No</span></span>  <br/> |
|<span data-ttu-id="0667c-172">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="0667c-172">**HardDelete**</span></span> <br/> |<span data-ttu-id="0667c-173">メッセージが [回復可能なアイテム] フォルダーから削除されました。</span><span class="sxs-lookup"><span data-stu-id="0667c-173">A message was purged from the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="0667c-174">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-174">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-175">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-175">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-176">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-176">Yes</span></span>  <br/> |
|<span data-ttu-id="0667c-177">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="0667c-177">**MailboxLogin**</span></span> <br/> |<span data-ttu-id="0667c-178">ユーザーが自分のメールボックスにサインインしました。</span><span class="sxs-lookup"><span data-stu-id="0667c-178">The user signed in to their mailbox.</span></span>  <br/> |<span data-ttu-id="0667c-179">いいえ</span><span class="sxs-lookup"><span data-stu-id="0667c-179">No</span></span>  <br/> |<span data-ttu-id="0667c-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="0667c-180">No</span></span>  <br/> |<span data-ttu-id="0667c-181">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-181">Yes</span></span>  <br/> |
|<span data-ttu-id="0667c-182">**messagebind**</span><span class="sxs-lookup"><span data-stu-id="0667c-182">**MessageBind**</span></span> <br/> |<span data-ttu-id="0667c-183">メッセージがプレビュー ウィンドウに表示されました (または開かれました)。</span><span class="sxs-lookup"><span data-stu-id="0667c-183">A message was viewed in the preview pane or opened.</span></span>  <br/> |<span data-ttu-id="0667c-184">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-184">Yes</span></span>  <br/> |<span data-ttu-id="0667c-185">×</span><span class="sxs-lookup"><span data-stu-id="0667c-185">No</span></span>  <br/> |<span data-ttu-id="0667c-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="0667c-186">No</span></span>  <br/> |
|<span data-ttu-id="0667c-187">**移動する**</span><span class="sxs-lookup"><span data-stu-id="0667c-187">**Move**</span></span> <br/> |<span data-ttu-id="0667c-188">メッセージが別のフォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="0667c-188">A message was moved to another folder.</span></span>  <br/> |<span data-ttu-id="0667c-189">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-189">Yes</span></span>  <br/> |<span data-ttu-id="0667c-190">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-190">Yes</span></span>  <br/> |<span data-ttu-id="0667c-191">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-191">Yes</span></span>  <br/> |
|<span data-ttu-id="0667c-192">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="0667c-192">**MoveToDeletedItems**</span></span> <br/> |<span data-ttu-id="0667c-193">メッセージが削除され、削除済みアイテム フォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="0667c-193">A message was deleted and moved to the Deleted Items folder.</span></span>  <br/> |<span data-ttu-id="0667c-194">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-194">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-195">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-195">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-196">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-196">Yes</span></span>  <br/> |
|<span data-ttu-id="0667c-197">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="0667c-197">**SendAs**</span></span> <br/> |<span data-ttu-id="0667c-p112">メッセージが、メールボックス所有者として送信するアクセス許可を使用して送信されました。これは、メールボックスの所有者から送信されているかのように、別のユーザーがメッセージを送信したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0667c-p112">A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.</span></span>  <br/> |<span data-ttu-id="0667c-200">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-200">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-201">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-201">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="0667c-202">No</span></span>  <br/> |
|<span data-ttu-id="0667c-203">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="0667c-203">**SendOnBehalf**</span></span> <br/> |<span data-ttu-id="0667c-p113">SendOnBehalf アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者の代理人としてメッセージを送信しました)。この場合は、メッセージの名目上の送信者と実際の送信者が受信者に示されます。</span><span class="sxs-lookup"><span data-stu-id="0667c-p113">A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>  <br/> |<span data-ttu-id="0667c-207">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-207">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-208">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-208">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="0667c-209">No</span></span>  <br/> |
|<span data-ttu-id="0667c-210">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="0667c-210">**SoftDelete**</span></span> <br/> |<span data-ttu-id="0667c-p114">メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="0667c-p114">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="0667c-213">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-213">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-214">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-214">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-215">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-215">Yes</span></span>  <br/> |
|<span data-ttu-id="0667c-216">**更新する**</span><span class="sxs-lookup"><span data-stu-id="0667c-216">**Update**</span></span> <br/> |<span data-ttu-id="0667c-217">メッセージまたはそのプロパティが変更されました。</span><span class="sxs-lookup"><span data-stu-id="0667c-217">A message or its properties was changed.</span></span>  <br/> |<span data-ttu-id="0667c-218">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-218">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-219">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-219">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-220">はい</span><span class="sxs-lookup"><span data-stu-id="0667c-220">Yes</span></span>  <br/> |
|<span data-ttu-id="0667c-221">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="0667c-221">**UpdateCalendarDelegation**</span></span> <br/> |<span data-ttu-id="0667c-p115">メールボックスに予定表の委任が割り当てられました。予定表の委任により、同じ組織の他のユーザーに、メールボックス所有者の予定表を管理する権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="0667c-p115">A calendar delegation was assigned to a mailbox. Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>  <br/> |<span data-ttu-id="0667c-224">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-224">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-225">いいえ</span><span class="sxs-lookup"><span data-stu-id="0667c-225">No</span></span>  <br/> |<span data-ttu-id="0667c-226">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-226">Yes\*</span></span>  <br/> |
|<span data-ttu-id="0667c-227">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="0667c-227">**UpdateFolderPermissions**</span></span> <br/> |<span data-ttu-id="0667c-p116">フォルダーのアクセス許可が変更されました。フォルダーのアクセス許可は、組織内のどのユーザーがメールボックス内のフォルダーにアクセスできるか、およびそれらのフォルダーに格納されているメッセージを制御します。</span><span class="sxs-lookup"><span data-stu-id="0667c-p116">A folder permission was changed. Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>  <br/> |<span data-ttu-id="0667c-230">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-230">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-231">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-231">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-232">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-232">Yes\*</span></span>  <br/> |
|<span data-ttu-id="0667c-233">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="0667c-233">**UpdateInboxRules**</span></span> <br/> |<span data-ttu-id="0667c-p117">受信トレイ ルールが、追加、削除、または変更されました。受信トレイ ルールを使用して、指定された条件に基づいて受信ボックス内のメッセージを処理し、ルールの条件と一致した場合は、指定されたフォルダーへのメッセージの移動やメッセージの削除などのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0667c-p117">An inbox rule has been added, removed, or changed. Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>  <br/> |<span data-ttu-id="0667c-236">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-236">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-237">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-237">Yes\*</span></span>  <br/> |<span data-ttu-id="0667c-238">はい\*</span><span class="sxs-lookup"><span data-stu-id="0667c-238">Yes\*</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="0667c-239"><sup>\*</sup>メールボックスの監査が有効になっている場合は、既定で監査されます。</span><span class="sxs-lookup"><span data-stu-id="0667c-239"><sup>\*</sup> Audited by default if auditing is enabled for a mailbox.</span></span><br/><br/>  <span data-ttu-id="0667c-p118"><sup>\*\*</sup>代理人が実行したフォルダーバインド操作のエントリは統合されます。24時間の期間内の個々のフォルダーへのアクセスに対して1つのログエントリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0667c-p118"><sup>\*\*</sup> Entries for folder bind actions performed by delegates are consolidated. One log entry is generated for individual folder access within a time span of 24 hours.</span></span><br/><br/><span data-ttu-id="0667c-242"><sup>\*\*\*</sup>ユーザーのメールボックスに対するフルアクセスのアクセス許可を割り当てられた管理者は、代理人ユーザーと見なされます。</span><span class="sxs-lookup"><span data-stu-id="0667c-242"><sup>\*\*\*</sup> An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span> 
  
<span data-ttu-id="0667c-p119">特定の種類のメールボックスの操作を監査する必要がなくなった場合は、メールボックスの監査ログ構成を変更して、それらの操作を無効にする必要があります。監査ログエントリの保持期限に達するまで、既存のログエントリは削除されません。監査ログエントリの保持期間の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md#before-you-begin)」の「開始する前に」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0667c-p119">If you no longer require certain types of mailbox actions to be audited, you should modify the mailbox's audit logging configuration to disable those actions. Existing log entries aren't purged until the retention age limit for audit log entries is reached. For more information about the retention age for audit log entries, see the "Before you begin" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#before-you-begin).</span></span>
  
## <a name="more-infotab"></a>[<span data-ttu-id="0667c-246">詳細</span><span class="sxs-lookup"><span data-stu-id="0667c-246">More info</span></span>](#tab/)
  
- <span data-ttu-id="0667c-p120">Office 365 監査ログを使用して、ログに記録されたメールボックスアクティビティを検索します。特定のユーザーメールボックスのアクティビティを検索できます。次のスクリーンショットは、Office 365 監査ログで検索できるメールボックスアクティビティの一覧を示しています。これらのアクティビティは、このトピックの「Mailbox auditing actions」セクションで説明されている操作と同じです。</span><span class="sxs-lookup"><span data-stu-id="0667c-p120">Use the Office 365 audit log to search for mailbox activity that have been logged. You can search for activity for a specific user mailbox. The following screenshot shows a list of mailbox activities that you can search for in the Office 365 audit log. Note that these activities are the same actions that are described in the "Mailbox auditing actions" section in this topic.</span></span>
    
    ![[アクティビティ] ドロップダウンリストで [Exchange メールボックスのアクティビティ] を選択することによって、メールボックス監査アクションの Office 365 監査ログを検索できます。](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    <span data-ttu-id="0667c-252">次の表は、検索できる各メールボックスのアクティビティと、対応するメールボックスの監査アクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="0667c-252">The following table describes each mailbox activity that you can search for and shows the corresponding mailbox auditing action.</span></span>
    
    |<span data-ttu-id="0667c-253">**監査ログでのアクティビティ**</span><span class="sxs-lookup"><span data-stu-id="0667c-253">**Activity in the audit log**</span></span>|<span data-ttu-id="0667c-254">**メールボックスの監査アクション**</span><span class="sxs-lookup"><span data-stu-id="0667c-254">**Mailbox auditing action**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0667c-255">メールボックス アイテムの作成</span><span class="sxs-lookup"><span data-stu-id="0667c-255">Created mailbox item</span></span>  <br/> |<span data-ttu-id="0667c-256">Create</span><span class="sxs-lookup"><span data-stu-id="0667c-256">Create</span></span>  <br/> |
    |<span data-ttu-id="0667c-257">別のフォルダーへのメッセージのコピー</span><span class="sxs-lookup"><span data-stu-id="0667c-257">Copied messages to another folder</span></span>  <br/> |<span data-ttu-id="0667c-258">Copy</span><span class="sxs-lookup"><span data-stu-id="0667c-258">Copy</span></span>  <br/> |
    |<span data-ttu-id="0667c-259">メールボックスへのユーザーのサインイン</span><span class="sxs-lookup"><span data-stu-id="0667c-259">User signed in to mailbox</span></span>  <br/> |<span data-ttu-id="0667c-260">MailboxLogin</span><span class="sxs-lookup"><span data-stu-id="0667c-260">MailboxLogin</span></span>  <br/> |
    |<span data-ttu-id="0667c-261">代理送信権限を使ったメッセージの送信</span><span class="sxs-lookup"><span data-stu-id="0667c-261">Sent message using Send On Behalf permissions</span></span>  <br/> |<span data-ttu-id="0667c-262">SendOnBehalf</span><span class="sxs-lookup"><span data-stu-id="0667c-262">SendOnBehalf</span></span>  <br/> |
    |<span data-ttu-id="0667c-263">メールボックスからのメッセージの消去</span><span class="sxs-lookup"><span data-stu-id="0667c-263">Purged messages from the mailbox</span></span>  <br/> |<span data-ttu-id="0667c-264">HardDelete</span><span class="sxs-lookup"><span data-stu-id="0667c-264">HardDelete</span></span>  <br/> |
    |<span data-ttu-id="0667c-265">削除済みアイテム フォルダーへのメッセージの移動</span><span class="sxs-lookup"><span data-stu-id="0667c-265">Moved messages to Deleted Items folder</span></span>  <br/> |<span data-ttu-id="0667c-266">MoveToDeletedItems</span><span class="sxs-lookup"><span data-stu-id="0667c-266">MoveToDeletedItems</span></span>  <br/> |
    |<span data-ttu-id="0667c-267">別のフォルダーへのメッセージの移動</span><span class="sxs-lookup"><span data-stu-id="0667c-267">Moved messages to another folder</span></span>  <br/> |<span data-ttu-id="0667c-268">Move</span><span class="sxs-lookup"><span data-stu-id="0667c-268">Move</span></span>  <br/> |
    |<span data-ttu-id="0667c-269">送信者権限を使ったメッセージの送信</span><span class="sxs-lookup"><span data-stu-id="0667c-269">Sent message using Send As permissions</span></span>  <br/> |<span data-ttu-id="0667c-270">SendAs</span><span class="sxs-lookup"><span data-stu-id="0667c-270">SendAs</span></span>  <br/> |
    |<span data-ttu-id="0667c-271">メッセージの更新</span><span class="sxs-lookup"><span data-stu-id="0667c-271">Updated message</span></span>  <br/> |<span data-ttu-id="0667c-272">Update</span><span class="sxs-lookup"><span data-stu-id="0667c-272">Update</span></span>  <br/> |
    |<span data-ttu-id="0667c-273">削除済みアイテム フォルダーからのメッセージの削除</span><span class="sxs-lookup"><span data-stu-id="0667c-273">Deleted messages from Deleted Items folder</span></span>  <br/> |<span data-ttu-id="0667c-274">SoftDelete</span><span class="sxs-lookup"><span data-stu-id="0667c-274">SoftDelete</span></span>  <br/> |
    |<span data-ttu-id="0667c-275">フォルダーにアクセス許可を追加しました</span><span class="sxs-lookup"><span data-stu-id="0667c-275">Added permissions to folder</span></span>  <br/> |<span data-ttu-id="0667c-276">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="0667c-276">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="0667c-277">フォルダーの変更された権限</span><span class="sxs-lookup"><span data-stu-id="0667c-277">Modified permissions of folder</span></span>  <br/> |<span data-ttu-id="0667c-278">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="0667c-278">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="0667c-279">フォルダーから権限を削除しました</span><span class="sxs-lookup"><span data-stu-id="0667c-279">Removed permissions from folder</span></span>  <br/> |<span data-ttu-id="0667c-280">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="0667c-280">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="0667c-281">予定表フォルダーへの代理人アクセス権を持つユーザーを追加または削除しました</span><span class="sxs-lookup"><span data-stu-id="0667c-281">Added or removed user with delegate access to calendar folder</span></span>  <br/> |<span data-ttu-id="0667c-282">UpdateCalendarDelegation</span><span class="sxs-lookup"><span data-stu-id="0667c-282">UpdateCalendarDelegation</span></span>  <br/> |
   
    <span data-ttu-id="0667c-p121">前のスクリーンショットに示されている**代理メールボックス**のアクセス許可を追加したり、**代理人メールボックスのアクセス許可を削除**したりしても、メールボックスの監査アクションとは関係ありません。これらは、管理者が fullaccess メールボックスのアクセス許可を割り当てたり削除したりしたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0667c-p121">Note that the **Added delegate mailbox permissions** and **Removed delegate mailbox permissions** activities shown in the previous screenshot aren't related to mailbox auditing actions. They indicate whether an administrator assigned or removed the FullAccess mailbox permission.</span></span> 
    
    <span data-ttu-id="0667c-285">office 365 監査ログの詳細については、「 [office 365 セキュリティ&amp;コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0667c-285">For information about the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
- <span data-ttu-id="0667c-286">以下のシナリオでは、メールボックスに管理者のみがアクセスするものと見なしています。</span><span class="sxs-lookup"><span data-stu-id="0667c-286">Mailboxes are considered to be accessed by an administrator only in the following scenarios:</span></span>
    
  - <span data-ttu-id="0667c-287">メールボックスを検索するには、Exchange Online のインプレース電子情報開示または Office 365 のコンテンツ検索を使用します。</span><span class="sxs-lookup"><span data-stu-id="0667c-287">In-Place eDiscovery in Exchange Online or Content Search in Office 365 is used to search a mailbox.</span></span>
    
  - <span data-ttu-id="0667c-288">[Microsoft Exchange Server MAPI エディター](https://go.microsoft.com/fwlink/p/?linkId=204086)を使用してメールボックスにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="0667c-288">[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) is used to access the mailbox.</span></span> 
    
- <span data-ttu-id="0667c-289">メールボックスの監査ログを有効にすると、ログオンの種類 (管理者、代理人、または所有者) ごとにログに記録するユーザー操作 (メッセージへのアクセス、移動、削除など) も指定できます。 </span><span class="sxs-lookup"><span data-stu-id="0667c-289">When you enable audit logging for a mailbox, you can also specify which user actions (for example, accessing, moving, or deleting a message) will be logged for each logon type (admin, delegate, or owner).</span></span>
    
- <span data-ttu-id="0667c-290">メールボックス監査ログを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0667c-290">To disable mailbox audit logging, run the following command:</span></span>

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- <span data-ttu-id="0667c-p122">各種類のユーザーに対して監査されるアクションは、**メールボックスの取得**コマンドレットを実行しても表示されません。ただし、次のコマンドを実行すると、特定のユーザーログオンの種類に関するすべての監査操作を表示できます。</span><span class="sxs-lookup"><span data-stu-id="0667c-p122">The actions that are audited for each type of user aren't displayed when you run the **Get-Mailbox** cmdlet. But you can run the following commands to display all the audited actions for a specific user logon type.</span></span> 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- <span data-ttu-id="0667c-p123">メールボックス監査ログをエクスポートして、1人以上のユーザーに含めるエントリを指定することもできます。レポートおよび監査ログの各エントリには、アクションを実行したユーザーと、アクションが実行された日時、およびアクションが成功したかどうかに関する情報が含まれています。詳細については、「[メールボックス監査ログのエクスポート](https://go.microsoft.com/fwlink/p/?LinkID=404104)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0667c-p123">You can also export a mailbox audit log and specify the entries to include for one or more users. Each entry in the report and the audit log includes information about who performed the action and when, the action performed , and whether the action was successful. For more information, see [Export mailbox audit logs](https://go.microsoft.com/fwlink/p/?LinkID=404104).</span></span>
