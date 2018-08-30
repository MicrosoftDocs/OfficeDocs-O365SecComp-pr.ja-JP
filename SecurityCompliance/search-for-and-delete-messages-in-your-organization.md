---
title: 検索し、Office 365 の組織の管理のヘルプで電子メール メッセージを削除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/25/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 検索を使用し、Office 365 のセキュリティの機能を削除&amp;コンプライアンス ・ センターを検索し、組織内のすべてのメールボックスから電子メール メッセージを削除します。
ms.openlocfilehash: 8bba4be473977afc229f64dfba6fd1514b86ecd2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531954"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a><span data-ttu-id="dc118-103">検索し、Office 365 の組織の管理のヘルプで電子メール メッセージを削除</span><span class="sxs-lookup"><span data-stu-id="dc118-103">Search for and delete email messages in your Office 365 organization - Admin Help</span></span>

<span data-ttu-id="dc118-104">**この資料では、管理者用です。削除するメールボックスのアイテムを検索しようとしていますか。[メッセージまたはインスタント検索を使用してアイテムを検索](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)を参照してください。**|</span><span class="sxs-lookup"><span data-stu-id="dc118-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span></span>
   
<span data-ttu-id="dc118-p101">Office 365 のコンテンツの検索機能を使用するにを検索し、組織内のすべてのメールボックスから電子メール メッセージを削除します。これを検索して、次のように、有害なまたは危険度の高い電子メールを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="dc118-p101">You can use the Content Search feature in Office 365 to search for and delete an email message from all mailboxes in your organization. This can help you find and remove potentially harmful or high-risk email, such as:</span></span>
  
- <span data-ttu-id="dc118-107">危険性のある添付ファイルやウイルスを含むメッセージ</span><span class="sxs-lookup"><span data-stu-id="dc118-107">Messages that contain dangerous attachment or virus</span></span>
    
- <span data-ttu-id="dc118-108">フィッシング メッセージ</span><span class="sxs-lookup"><span data-stu-id="dc118-108">Phishing messages</span></span>
    
- <span data-ttu-id="dc118-109">機密データを含むメッセージ</span><span class="sxs-lookup"><span data-stu-id="dc118-109">Messages that contain sensitive data</span></span>
    
> [!CAUTION]
> <span data-ttu-id="dc118-110">検索と削除は、強力な機能により、すべてのユーザーを組織内のメールボックスから電子メール メッセージを削除するのには必要なアクセス許可が割り当てられているです。</span><span class="sxs-lookup"><span data-stu-id="dc118-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="dc118-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="dc118-111">Before you begin</span></span>

- <span data-ttu-id="dc118-p102">作成し、コンテンツの検索を実行するには、**電子的証拠開示マネージャー**の役割グループのメンバーであるか、**コンプライアンス検索**の管理役割を割り当てる必要があります。メッセージを削除するには、**組織の管理**役割グループのメンバーであるか、**検索および削除**の管理役割を割り当てる必要があります。ユーザーを役割グループに追加する方法の詳細についてを参照してください[Office 365 のセキュリティにアクセスできるように&amp;コンプライアンス センター](grant-access-to-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="dc118-p102">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role. To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role. For information about adding users to a role group, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="dc118-p103">セキュリティを使用する必要が&amp;メッセージを削除するのにはセンター PowerShell を遵守します。接続する方法について、[手順 2](#step-2-connect-to-security-amp-compliance-center-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc118-p103">You have to use Security &amp; Compliance Center PowerShell to delete messages. See [Step 2](#step-2-connect-to-security-amp-compliance-center-powershell) for instructions about how to connect.</span></span>
    
- <span data-ttu-id="dc118-p104">メールボックスあたり 10 個のアイテムの最大値を同時に削除できます。検索してメッセージを削除する機能は、インシデント対応ツールになるようとしているためこの制限により、メールボックスからメッセージが削除されます簡単にできます。この機能は、ユーザーのメールボックスをクリーンアップするのにはありません。10 個を超えるアイテムを削除するには、Exchange オンライン PowerShell で**検索メールボックス DeleteContent**コマンドを使用できます。[検索して削除するメッセージの管理のヘルプ](search-for-and-delete-messagesadmin-help.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc118-p104">A maximum of 10 items per mailbox can be removed at one time. Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes. This feature isn't intended to clean up user mailboxes. To delete more than 10 items, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell. See [Search for and delete messages - Admin help](search-for-and-delete-messagesadmin-help.md).</span></span>
    
- <span data-ttu-id="dc118-p105">コンテンツの検索を使用している内の項目を削除するには、検索を行うとアクションを削除することでメールボックスの最大数は、50,000 です。([手順 1](#step-1-create-a-content-search-to-find-the-message-to-delete)で作成) をコンテンツの検索には、50,000 以上のソース メールボックスがある、(手順 3 で作成する場合) を削除操作が失敗します。検索を実行する方法についてのヒントの[詳細について](#more-information)はを参照してくださいし、50,000 以上のメールボックスでの操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="dc118-p105">The maximum number of mailboxes in a Content Search that you can delete items in by doing a search and purge action is 50,000. If the Content Search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) has more than 50,000 source mailboxes, the purge action (that you create in Step 3) will fail. See the [More information](#more-information) section for a tip on performing a search and purge operation on more than 50,000 mailboxes.</span></span> 
    
- <span data-ttu-id="dc118-p106">この資料の手順は、Exchange Online のメールボックスおよびパブリック フォルダー内のアイテムを削除するのにのみ使用できます。SharePoint または OneDrive からビジネス サイトのコンテンツを削除するのには使用できません。</span><span class="sxs-lookup"><span data-stu-id="dc118-p106">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders. You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="dc118-127">手順 1: コンテンツ検索を作成して、削除するメッセージを探す</span><span class="sxs-lookup"><span data-stu-id="dc118-127">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="dc118-p107">作成し、組織内のメールボックスから削除するメッセージを検索するコンテンツの検索を実行するのには、まず。セキュリティを使用して検索を作成することができます&amp;コンプライアンス センターか**新規 ComplianceSearch**および**開始 ComplianceSearch**コマンドレットを実行しています。この検索のクエリに一致するメッセージは、[手順 3](#step-3-delete-the-message)で**新規 ComplianceSearchAction**コマンドレットを実行することによって削除されます。コンテンツの検索を作成して、検索クエリを構成する方法については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc118-p107">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization. You can create the search by using the Security &amp; Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets. The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction** cmdlet in [Step 3](#step-3-delete-the-message). For information about creating a Content Search and configuring search queries, see the following topics:</span></span> 
  
- [<span data-ttu-id="dc118-132">Office 365 でのコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="dc118-132">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="dc118-133">コンテンツ検索用のキーワード クエリ</span><span class="sxs-lookup"><span data-stu-id="dc118-133">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="dc118-134">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="dc118-134">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [<span data-ttu-id="dc118-135">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="dc118-135">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> <span data-ttu-id="dc118-p108">この手順で作成したコンテンツの検索に検索対象となるコンテンツの場所は、ビジネス サイトの SharePoint または OneDrive を含めることはできません。電子メール メッセージに使用されるコンテンツの検索では、メールボックスとパブリック フォルダーのみを含めることができます。コンテンツの検索には、サイトが含まれている場合、エラーが返さステップ 3 で**新規 ComplianceSearchAction**コマンドレットを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="dc118-p108">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites. You can include only mailboxes and public folders in a Content Search that will be used to email messages. If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span> 
  
### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="dc118-139">削除するメッセージの検索に関するヒント</span><span class="sxs-lookup"><span data-stu-id="dc118-139">Tips for finding messages to remove</span></span>

<span data-ttu-id="dc118-p109">検索クエリの目標は、削除するメッセージだけに検索結果を絞り込むことです。次にヒントを示します。</span><span class="sxs-lookup"><span data-stu-id="dc118-p109">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>
  
- <span data-ttu-id="dc118-142">正確な語句、メッセージの件名行で使用されている場合は、検索クエリの**Subject**プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc118-142">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span> 
    
- <span data-ttu-id="dc118-143">メッセージの正確な日付 (または期間) がわかる場合は、検索クエリに **Received** プロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="dc118-143">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span> 
    
- <span data-ttu-id="dc118-144">メッセージの送信者がわかる場合は、検索クエリに **From** プロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="dc118-144">If you know who sent the message, include the **From** property in the search query.</span></span> 
    
- <span data-ttu-id="dc118-145">検索に、メッセージ (またはメッセージ) のみが返されることを確認するのには検索結果をプレビュー表示を削除します。</span><span class="sxs-lookup"><span data-stu-id="dc118-145">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>
    
- <span data-ttu-id="dc118-146">見積もり、検索の統計を使用して (セキュリティでの検索の詳細ウィンドウに表示されている&amp;コンプライアンス センターまたは[Get ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934)コマンドレットを使用して) 結果の合計数のカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="dc118-146">Use the search estimate statistics (displayed in the details pane of the search in the Security &amp; Compliance Center or by using the [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) to get a count of the total number of results.</span></span> 
    
<span data-ttu-id="dc118-147">不審な電子メール メッセージを検索するクエリの 2 つの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc118-147">Here are two examples of queries to find suspicious email messages.</span></span>
  
- <span data-ttu-id="dc118-148">このクエリは、2016 年 4 月 13 日から 2016 年 4 月 14 日までの間にユーザーが受信し、単語 "action" と "required" が件名に含まれるメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="dc118-148">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- <span data-ttu-id="dc118-149">このクエリは、chatsuwloginsset12345@outlook.com から送信され、完全に一致する語句 "Update your account information" (アカウント情報を更新してください) が件名に含まれているメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="dc118-149">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security-amp-compliance-center-powershell"></a><span data-ttu-id="dc118-150">ステップ 2: 接続セキュリティ&amp;コンプライアンス センター PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc118-150">Step 2: Connect to Security &amp; Compliance Center PowerShell</span></span>

<span data-ttu-id="dc118-p110">セキュリティへの接続を次の手順は、 &amp; 、組織のコンプライアンス センターの PowerShell。手順についてを参照してください[Office 365 のセキュリティへの接続&amp;コンプライアンス センター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="dc118-p110">The next step is to connect to Security &amp; Compliance Center PowerShell for your organization. For step-by-step instructions, see [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="dc118-p111">Office 365 アカウントでは、多要素認証 (MFA) またはフェデレーション認証を使用する場合セキュリティへの接続の前のトピックでの手順を使うことはできません&amp;コンプライアンス センター PowerShell。代わりに、トピックの指示を参照してください[Office 365 のセキュリティへの接続&amp;コンプライアンス センター PowerShell の多要素認証を使用して](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="dc118-p111">If your Office 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security &amp; Compliance Center PowerShell. Instead, see the instructions in the topic [Connect to Office 365 Security &amp; Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-3-delete-the-message"></a><span data-ttu-id="dc118-155">ステップ 3: メッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="dc118-155">Step 3: Delete the message</span></span>

<span data-ttu-id="dc118-p112">作成しを削除するのにはセキュリティに接続しているメッセージが返されるコンテンツの検索を改良した後&amp;コンプライアンス センター PowerShell では、最後に、メッセージを削除するのには**新規 ComplianceSearchAction**コマンドレットを実行します。削除されたメッセージは、ユーザーの回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="dc118-p112">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security &amp; Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message. Deleted messages are moved to a user's Recoverable Items folder.</span></span> 
  
<span data-ttu-id="dc118-158">次の例では、"Remove Phishing Message"(フィッシング メッセージの削除) という名前のコンテンツ検索によって返された検索結果がコマンドによって削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc118-158">In the following example, the command will delete the search results returned by a Content Search named "Remove Phishing Message".</span></span> 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```
  
<span data-ttu-id="dc118-159">*SearchName*パラメーターで指定された検索では、手順 1 で作成したコンテンツの検索がされます。</span><span class="sxs-lookup"><span data-stu-id="dc118-159">The search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span> 
  
<span data-ttu-id="dc118-160">詳細については、[新規 ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc118-160">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).</span></span>
  

## <a name="more-information"></a><span data-ttu-id="dc118-161">詳細情報</span><span class="sxs-lookup"><span data-stu-id="dc118-161">More information</span></span>

- <span data-ttu-id="dc118-162">**検索のステータスを取得および操作を削除する方法**</span><span class="sxs-lookup"><span data-stu-id="dc118-162">**How do you get status on the search and remove operation?**</span></span>

    <span data-ttu-id="dc118-p113">削除操作の状態を取得する**Get ComplianceSearchAction**を実行します。この形式を使用して**新規 ComplianceSearchAction**コマンドレットを実行するときに作成されるオブジェクトの名前はことに注意してください: `<name of Content Search>_Purge`。</span><span class="sxs-lookup"><span data-stu-id="dc118-p113">Run the **Get-ComplianceSearchAction** to get the status on the delete operation. Note that the object that is created when you run the **New-ComplianceSearchAction** cmdlet is named by using this format:  `<name of Content Search>_Purge`.</span></span> 
    
- <span data-ttu-id="dc118-165">**メッセージを削除した後はどうなるか**</span><span class="sxs-lookup"><span data-stu-id="dc118-165">**What happens after you delete a message?**</span></span>

    <span data-ttu-id="dc118-p114">使用して削除されたメッセージ、`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`コマンドは、ユーザーの回復可能なアイテム] フォルダーの削除フォルダーに移動します。されていない、Office 365 から直ちにパージされます。ユーザーは、メールボックスに対して構成されている削除済みアイテムの保持期間に基づいて、期間の削除済みアイテム フォルダー内のメッセージを回復できます。この保存期間の有効期限が切れた (または期限が切れたユーザーの前にメッセージを削除する場合)、メッセージは削除フォルダーに移動され、ユーザーが再びアクセスすることができます。1 回パージ] フォルダーでメッセージもう一度は保持されます、メールボックスの単一アイテムの回復が有効になっている場合は、メールボックスの構成されている削除済みアイテムの保存期間に基づいて、期間の。(、Office 365 で単一アイテムの回復は既定で有効に新しいメールボックスが作成されるときです。)削除済みアイテムの保存期間を過ぎると、メッセージが完全に削除のマークされているし、次のように、メールボックスが管理フォルダー アシスタントによって処理されたときに Office 365 からパージされます。</span><span class="sxs-lookup"><span data-stu-id="dc118-p114">A message that is deleted by using the  `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command is moved to the Deletions folder in the user's Recoverable Items folder. It isn't immediately purged from Office 365. The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox. After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user. Once in the Purges folder, the message is again retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox. (In Office 365, single item recovery is enabled by default when a new mailbox is created. ) After the deleted item retention period expires, the message is marked from permanent deletion and will be purged from Office 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span> 
    
- <span data-ttu-id="dc118-173">**すればメッセージが削除され、ユーザーの回復可能な項目] フォルダーに移動しますか。**</span><span class="sxs-lookup"><span data-stu-id="dc118-173">**How do you know that messages are deleted and moved to the users' Recoverable Items folder?**</span></span>

    <span data-ttu-id="dc118-p115">メッセージを削除した後、同じコンテンツの検索を実行する場合は、同じ数の検索結果が表示されますが、ユーザーのメールボックスからメッセージが削除されていないことを考えるかもしれませんが、)。これは、コンテンツの検索は、[回復可能な項目] フォルダーを検索するため、削除されたメッセージの移動先を実行した後は、`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`コマンドです。回復可能な項目] フォルダーに移動する場合にメッセージを確認するには、探索メールボックスに (とを使用して同じソース メールボックス検索条件として、コンテンツの検索は、手順 1 で作成)、埋め込み電子的証拠開示検索と検索結果のコピーを実行できます。検出メールボックスに検索結果を表示し、メッセージが回復可能なアイテム] フォルダーに移動されたことを確認できます。元のメールボックスおよびコンテンツの検索からの検索クエリのリストを使用する埋め込みの電子的証拠開示検索を作成する方法については[、電子的証拠開示ワークフロー内のコンテンツの検索を使用](use-content-search-in-ediscovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc118-p115">If you run the same Content Search after you delete a message, you will still see the same number of search results (and might assume that the message wasn't deleted from user mailboxes). This is because a Content Search searches the Recoverable Items folder, which is where the deleted message is moved to after you run the  `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command. To verify that messages where moved to the Recoverable Items folder, you can run an In-Place eDiscovery search (using the same source mailboxes and search criteria as the Content Search created in Step 1) and the copy the search results to discovery mailbox. Then you can view the search results in the discovery mailbox and verify that the messages was moved to the Recoverable Items folder. See [Use Content Search in your eDiscovery workflow](use-content-search-in-ediscovery.md) for details about creating an In-Place eDiscovery search that uses the list of source mailboxes and search query from a Content Search.</span></span> 
    
- <span data-ttu-id="dc118-179">**ある場合は 50,000 人を超えるメールボックスからメッセージを削除しますか。**</span><span class="sxs-lookup"><span data-stu-id="dc118-179">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

    <span data-ttu-id="dc118-p116">前述したように、検索を実行し、最大 50,000 のメールボックスでの操作を削除できます。検索を実行し、50,000 を超えるメールボックスでの操作を削除する必要がある場合は、50,000 未満のメールボックスを検索するメールボックスの数を削減する一時的な検索のアクセス許可フィルターを作成することを検討します。などの組織では、さまざまな部門、状態、または国でのメールボックスが含まれている場合は、組織内のメールボックスのサブセットを検索するのにはこれらのメールボックスのプロパティのいずれかに基づいて、メールボックス検索のアクセス許可のフィルターを作成できます。検索のアクセス許可フィルターを作成した後 (手順 1 で説明した) 検索を作成し、(手順 3 で説明した) メッセージを削除します。検索し、別の一連のメールボックスにメッセージを削除するフィルターを編集できます。検索のアクセス許可のフィルターを作成する方法の詳細については、[アクセス許可を構成するコンテンツの検索のフィルター処理](permissions-filtering-for-content-search.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc118-p116">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes. If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that would reduce the number of mailboxes that would be searched to less than 50,000 mailboxes. For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization. After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3). Then you can edit the filter to search for and purge messages in a different set of mailboxes. For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
    
- <span data-ttu-id="dc118-186">**検索結果に含まれるインデックスの項目は削除されます。**</span><span class="sxs-lookup"><span data-stu-id="dc118-186">**Will unindexed items included in the search results be deleted?**</span></span>

    <span data-ttu-id="dc118-187">残念ですが、`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`コマンドは、インデックスを持たないアイテムを削除しません。</span><span class="sxs-lookup"><span data-stu-id="dc118-187">No, the  `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command doesn't delete unindexed items.</span></span> 
    
- <span data-ttu-id="dc118-188">**インプレース保持または訴訟を保持していますか、Office 365 のリテンション ・ ポリシーに割り当てられているメールボックスからメッセージを削除するとどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="dc118-188">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Office 365 retention policy?**</span></span>

    <span data-ttu-id="dc118-p117">(ユーザー、または削除済みアイテムの保存期間が終了した後)、メッセージがパージされると、保留期間が経過するまで、メッセージが保持されます。保留期間が制限されている場合は、保留リストを削除または保持期間を変更するまで、アイテムは保持されます。</span><span class="sxs-lookup"><span data-stu-id="dc118-p117">After the message is purged (either by the user or after the deleted item retention period expires), the message is retained until the hold duration expires. If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>
    
- <span data-ttu-id="dc118-191">**理由検索と削除のワークフローに分割されている別のセキュリティ&amp;コンプライアンス センターの役割のグループですか。**</span><span class="sxs-lookup"><span data-stu-id="dc118-191">**Why is the search and remove workflow divided among different Security &amp; Compliance Center role groups?**</span></span>

    <span data-ttu-id="dc118-p118">説明したように電子的証拠開示マネージャーの役割グループのメンバーであるか、メールボックスを検索するのには、コンプライアンス検索管理の役割を割り当てられる人があります。人にメッセージを削除するには、組織の管理役割グループのメンバーであるか、検索および削除の管理役割を割り当てるには。これにより、管理する組織内のメールボックスを検索することができ、メッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="dc118-p118">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes. To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role. This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span> 
