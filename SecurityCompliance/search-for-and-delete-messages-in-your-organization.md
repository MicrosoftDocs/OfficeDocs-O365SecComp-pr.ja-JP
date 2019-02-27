---
title: Office 365 組織の電子メールメッセージを検索して削除する-管理者向けヘルプ
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
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Office 365 セキュリティ&amp;コンプライアンスセンターの検索と削除機能を使用して、組織内のすべてのメールボックスから電子メールメッセージを検索し、削除します。
ms.openlocfilehash: 15d67e42e4bdc63838f7ec1701d643391fa5c552
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296860"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a><span data-ttu-id="4230d-103">Office 365 組織の電子メールメッセージを検索して削除する-管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="4230d-103">Search for and delete email messages in your Office 365 organization - Admin Help</span></span>

<span data-ttu-id="4230d-104">**この記事は、管理者を対象としています。削除するメールボックス内のアイテムを検索しようとしていますか?「[クイック検索を使用してメッセージまたはアイテムを検索する」を](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)参照してください。**|</span><span class="sxs-lookup"><span data-stu-id="4230d-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span></span>
   
<span data-ttu-id="4230d-p101">Office 365 のコンテンツ検索機能を使用して、組織内のすべてのメールボックスから電子メールメッセージを検索し、削除することができます。これにより、次のような危険または危険性の高い電子メールを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4230d-p101">You can use the Content Search feature in Office 365 to search for and delete an email message from all mailboxes in your organization. This can help you find and remove potentially harmful or high-risk email, such as:</span></span>
  
- <span data-ttu-id="4230d-107">危険な添付ファイルまたはウイルスを含むメッセージ</span><span class="sxs-lookup"><span data-stu-id="4230d-107">Messages that contain dangerous attachments or viruses</span></span>
    
- <span data-ttu-id="4230d-108">フィッシング メッセージ</span><span class="sxs-lookup"><span data-stu-id="4230d-108">Phishing messages</span></span>
    
- <span data-ttu-id="4230d-109">機密データを含むメッセージ</span><span class="sxs-lookup"><span data-stu-id="4230d-109">Messages that contain sensitive data</span></span>
    
> [!CAUTION]
> <span data-ttu-id="4230d-110">検索と削除は、必要なアクセス許可が割り当てられているユーザーが組織内のメールボックスから電子メールメッセージを削除できるようにするための強力な機能です。</span><span class="sxs-lookup"><span data-stu-id="4230d-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="4230d-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="4230d-111">Before you begin</span></span>

- <span data-ttu-id="4230d-p102">コンテンツ検索を作成して実行するには、**電子情報開示マネージャー**の役割グループのメンバーであるか、または**コンプライアンス検索**管理役割が割り当てられている必要があります。メッセージを削除するには、**組織の管理**役割グループのメンバーであるか、または**検索と削除**の管理役割が割り当てられている必要があります。役割グループへのユーザーの追加の詳細については、「[ユーザーに Office 365 セキュリティ & コンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-p102">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role. To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role. For information about adding users to a role group, see [Give users access to the Office 365 Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="4230d-p103">メッセージを削除するには、Security & コンプライアンスセンター PowerShell を使用する必要があります。接続方法については、[手順 2](#step-2-connect-to-security-amp-compliance-center-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-p103">You have to use Security & Compliance Center PowerShell to delete messages. See [Step 2](#step-2-connect-to-security-amp-compliance-center-powershell) for instructions about how to connect.</span></span>
    
- <span data-ttu-id="4230d-p104">一度に削除できるアイテムは、メールボックスごとに10個までです。メッセージを検索して削除する機能はインシデント対応ツールとして使用することを目的としているため、この制限によって、メッセージがメールボックスからすぐに削除されます。この機能は、ユーザーメールボックスをクリーンアップすることを意図したものではありません。10を超えるアイテムを削除するには、Exchange Online PowerShell で**DeleteContent**コマンドを使用します。「[メッセージを検索して削除する-管理者ヘルプ](search-for-and-delete-messagesadmin-help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-p104">A maximum of 10 items per mailbox can be removed at one time. Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes. This feature isn't intended to clean up user mailboxes. To delete more than 10 items, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell. See [Search for and delete messages - Admin help](search-for-and-delete-messagesadmin-help.md).</span></span>
    
- <span data-ttu-id="4230d-p105">検索と削除の操作を実行して、コンテンツ検索でアイテムを削除できる最大メールボックス数は5万です。[手順 1](#step-1-create-a-content-search-to-find-the-message-to-delete)で作成したコンテンツ検索に5万個を超えるソースメールボックスがある場合、削除アクション (手順3で作成したもの) は失敗します。5万を超えるメールボックスで検索と削除の操作を実行する際のヒントについては、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-p105">The maximum number of mailboxes in a Content Search that you can delete items in by doing a search and purge action is 50,000. If the Content Search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) has more than 50,000 source mailboxes, the purge action (that you create in Step 3) will fail. See the [More information](#more-information) section for a tip on performing a search and purge operation on more than 50,000 mailboxes.</span></span> 
    
- <span data-ttu-id="4230d-p106">この記事の手順は、Exchange Online メールボックスおよびパブリックフォルダー内のアイテムを削除する場合にのみ使用できます。これを使用して SharePoint または OneDrive for business サイトからコンテンツを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="4230d-p106">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders. You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="4230d-127">手順 1: コンテンツ検索を作成して、削除するメッセージを探す</span><span class="sxs-lookup"><span data-stu-id="4230d-127">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="4230d-p107">最初の手順として、コンテンツ検索を作成して実行し、組織内のメールボックスから削除するメッセージを検索します。セキュリティ&amp;コンプライアンスセンターを使用するか、 **new-compliancesearch**および**new-compliancesearch**コマンドレットを実行することによって、検索を作成できます。この検索のクエリに一致するメッセージは、[手順 3](#step-3-delete-the-message)で**new-compliancesearchaction-Purge**コマンドを実行することによって削除されます。コンテンツ検索の作成および検索クエリの構成の詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-p107">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization. You can create the search by using the Security &amp; Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets. The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message). For information about creating a Content Search and configuring search queries, see the following topics:</span></span> 
  
- [<span data-ttu-id="4230d-132">Office 365 でのコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="4230d-132">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="4230d-133">コンテンツ検索のキーワードクエリ</span><span class="sxs-lookup"><span data-stu-id="4230d-133">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="4230d-134">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="4230d-134">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [<span data-ttu-id="4230d-135">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="4230d-135">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> <span data-ttu-id="4230d-p108">この手順で作成するコンテンツ検索で検索されるコンテンツの場所には、SharePoint または OneDrive for business サイトを含めることはできません。電子メールメッセージに使用するコンテンツ検索には、メールボックスとパブリックフォルダーのみを含めることができます。コンテンツ検索にサイトが含まれている場合、 **new-compliancesearchaction**コマンドレットを実行すると、手順3でエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4230d-p108">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites. You can include only mailboxes and public folders in a Content Search that will be used to email messages. If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span> 
  
### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="4230d-139">削除するメッセージを検索するためのヒント</span><span class="sxs-lookup"><span data-stu-id="4230d-139">Tips for finding messages to remove</span></span>

<span data-ttu-id="4230d-p109">検索クエリの目標は、削除するメッセージだけに検索結果を絞り込むことです。次にヒントを示します。</span><span class="sxs-lookup"><span data-stu-id="4230d-p109">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>
  
- <span data-ttu-id="4230d-142">メッセージの件名に使用されているテキストまたは語句が正確にわかっている場合は、検索クエリの**subject**プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="4230d-142">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span> 
    
- <span data-ttu-id="4230d-143">メッセージの正確な日付 (または期間) がわかる場合は、検索クエリに **Received** プロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="4230d-143">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span> 
    
- <span data-ttu-id="4230d-144">メッセージの送信者がわかる場合は、検索クエリに **From** プロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="4230d-144">If you know who sent the message, include the **From** property in the search query.</span></span> 
    
- <span data-ttu-id="4230d-145">検索結果をプレビューして、削除するメッセージのみが検索によって返されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4230d-145">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>
    
- <span data-ttu-id="4230d-146">検索の推定統計 (セキュリティ&amp;コンプライアンスセンターでの検索の詳細ウィンドウ、または[new-compliancesearch](https://go.microsoft.com/fwlink/p/?LinkId=517934)コマンドレットを使用) を使用して、結果の合計数のカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="4230d-146">Use the search estimate statistics (displayed in the details pane of the search in the Security &amp; Compliance Center or by using the [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) to get a count of the total number of results.</span></span> 
    
<span data-ttu-id="4230d-147">不審な電子メール メッセージを検索するクエリの 2 つの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4230d-147">Here are two examples of queries to find suspicious email messages.</span></span>
  
- <span data-ttu-id="4230d-148">このクエリは、2016 年 4 月 13 日から 2016 年 4 月 14 日までの間にユーザーが受信し、単語 "action" と "required" が件名に含まれるメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="4230d-148">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- <span data-ttu-id="4230d-149">このクエリは、chatsuwloginsset12345@outlook.com から送信され、完全に一致する語句 "Update your account information" (アカウント情報を更新してください) が件名に含まれているメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="4230d-149">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="4230d-150">手順 2: Security & コンプライアンスセンター PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="4230d-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="4230d-p110">次の手順では、組織の Security & コンプライアンスセンター PowerShell に接続します。詳細な手順については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターの PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-p110">The next step is to connect to Security & Compliance Center PowerShell for your organization. For step-by-step instructions, see [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="4230d-p111">Office 365 アカウントで多要素認証 (MFA) またはフェデレーション認証を使用している場合は、「Security & コンプライアンスセンター PowerShell への接続」に記載されている前のトピックの手順を使用することはできません。その代わりに、「 [Office 365 セキュリティ & コンプライアンスセンターの PowerShell への接続に多要素認証を使用する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-p111">If your Office 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell. Instead, see the instructions in the topic [Connect to Office 365 Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-3-delete-the-message"></a><span data-ttu-id="4230d-155">手順 3: メッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="4230d-155">Step 3: Delete the message</span></span>

<span data-ttu-id="4230d-p112">削除してセキュリティ&amp;コンプライアンスセンターの PowerShell に接続されているメッセージを返すようにコンテンツ検索を作成して調整した後、最後の手順として、 **new-compliancesearchaction**コマンドレットを実行してメッセージを削除します。メッセージをソフトまたはハード削除することができます。回復可能な削除によって削除されたメッセージは、ユーザーの回復可能なアイテムフォルダーに移動され、削除済みアイテムの保存期間が経過するまで保持されます。物理的に削除されたメッセージは、メールボックスから完全に削除するようマークが付けられ、管理フォルダーアシスタントによって次回メールボックスが処理されるときに完全に削除されます。メールボックスの単一アイテムの回復が有効になっている場合は、削除済みアイテムの保存期間の期限が切れた後、完全に削除されたアイテムが完全に削除されます。メールボックスがホールドの対象になっている場合、削除されたメッセージは、アイテムの保持期間が満了するか、保持がメールボックスから削除されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="4230d-p112">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security &amp; Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message. You can soft- or hard-delete the message. A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires. Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant. If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires. If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>
  
<span data-ttu-id="4230d-162">次の例では、"フィッシング詐欺メッセージの削除" という名前のコンテンツ検索によって返された検索結果がコマンドによって削除されます。</span><span class="sxs-lookup"><span data-stu-id="4230d-162">In the following example, the command will soft-delete the search results returned by a Content Search named "Remove Phishing Message".</span></span> 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="4230d-163">"フィッシングメッセージの削除" コンテンツ検索によって返されるアイテムを物理的に削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4230d-163">To hard-deleted the items returned by the  "Remove Phishing Message" content search, you would run this command:</span></span>

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="4230d-164">前のコマンドを実行してメッセージをソフトまたは物理的に削除すると、 *searchname*パラメーターで指定された検索は、手順1で作成したコンテンツ検索になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-164">Note that when you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span> 
  
<span data-ttu-id="4230d-165">詳細については、「 [new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-165">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="4230d-166">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4230d-166">More information</span></span>

- <span data-ttu-id="4230d-167">**検索と削除の操作の状態を取得するには、どうすればよいですか。**</span><span class="sxs-lookup"><span data-stu-id="4230d-167">**How do you get status on the search and remove operation?**</span></span>

    <span data-ttu-id="4230d-p113">**new-compliancesearchaction**を実行して、削除操作の状態を取得します。**new-compliancesearchaction**コマンドレットを実行するときに作成されるオブジェクトは、次`<name of Content Search>_Purge`の形式を使用して指定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-p113">Run the **Get-ComplianceSearchAction** to get the status on the delete operation. Note that the object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span> 
    
- <span data-ttu-id="4230d-170">**メッセージを削除した後はどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="4230d-170">**What happens after you delete a message?**</span></span>

   <span data-ttu-id="4230d-p114">`New-ComplianceSearchAction -Purge -PurgeType HardDelete`コマンドを使用して削除されたメッセージは、削除フォルダーに移動され、ユーザーがアクセスすることはできません。メッセージが [削除] フォルダーに移動された後、メールボックスに対して単一アイテムの回復が有効になっている場合は、削除済みアイテムの保存期間中はメッセージが保持されます。(Office 365 では、新しいメールボックスが作成されるときに、単一アイテムの回復が既定で有効になっています。)削除済みアイテムの保存期間の期限が切れると、メッセージは永続的な削除のマークが付けられ、次回メールボックスが管理フォルダーアシスタントによって処理されたときに Office 365 から削除されます。</span><span class="sxs-lookup"><span data-stu-id="4230d-p114">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user. After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox. (In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span> 

   <span data-ttu-id="4230d-p115">`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`コマンドを使用すると、メッセージはユーザーの回復可能なアイテムフォルダーの削除フォルダーに移動されます。Office 365 からすぐに削除されることはありません。ユーザーは、メールボックスに対して構成された削除済みアイテムの保存期間に基づいて、削除済みアイテムフォルダー内のメッセージを復元することができます。この保存期間が過ぎると (または、ユーザーが期限切れになる前にメッセージを削除すると)、メッセージはパージフォルダーに移動され、ユーザーがアクセスできなくなります。[削除] フォルダーで、メールボックスに対して単一アイテムの回復が有効になっている場合に、メールボックスに対して構成された削除済みアイテムの保存期間に基づいて、メッセージは保持期間中保持されます。(Office 365 では、新しいメールボックスが作成されるときに、単一アイテムの回復が既定で有効になっています。)削除済みアイテムの保存期間の期限が切れると、メッセージは永続的な削除のマークが付けられ、次回メールボックスが管理フォルダーアシスタントによって処理されたときに Office 365 から削除されます。</span><span class="sxs-lookup"><span data-stu-id="4230d-p115">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder. It isn't immediately purged from Office 365. The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox. After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user. Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox. (In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span> 
    
- <span data-ttu-id="4230d-180">**5万を超えるメールボックスからメッセージを削除する必要がある場合はどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="4230d-180">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

    <span data-ttu-id="4230d-p116">前述したように、最大5万のメールボックスで検索と削除の操作を実行できます。5万を超えるメールボックスで検索と削除の操作を実行する必要がある場合は、検索対象のメールボックスの数が5万未満になるようにするための、一時検索アクセス許可フィルターを作成することを検討してください。たとえば、組織のメールボックスが異なる部署、都道府県、または国に含まれている場合は、これらのいずれかのメールボックスのプロパティに基づいてメールボックス検索アクセス許可フィルターを作成し、組織内のメールボックスのサブセットを検索することができます。検索アクセス許可フィルターを作成したら、手順1で説明した検索を作成し、メッセージを削除します (手順3を参照)。その後、フィルターを編集して、別のメールボックスのセット内のメッセージを検索し、削除することができます。検索アクセス許可フィルターの作成の詳細については、「 [Configure permissions filtering for Content search](permissions-filtering-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4230d-p116">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes. If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that would reduce the number of mailboxes that would be searched to less than 50,000 mailboxes. For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization. After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3). Then you can edit the filter to search for and purge messages in a different set of mailboxes. For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
    
- <span data-ttu-id="4230d-187">**検索結果に含まれるインデックスのないアイテムは削除されますか。**</span><span class="sxs-lookup"><span data-stu-id="4230d-187">**Will unindexed items included in the search results be deleted?**</span></span>

    <span data-ttu-id="4230d-188">いいえ。 ' new-compliancesearchaction-削除コマンドは、インデックスが作成されていないアイテムを削除しません。</span><span class="sxs-lookup"><span data-stu-id="4230d-188">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span> 
    
- <span data-ttu-id="4230d-189">**インプレース保持または訴訟ホールドの対象となっているメールボックスから、または Office 365 アイテム保持ポリシーに割り当てられているメッセージが削除された場合はどうなりますか?**</span><span class="sxs-lookup"><span data-stu-id="4230d-189">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Office 365 retention policy?**</span></span>

    <span data-ttu-id="4230d-p117">メッセージが削除されて、[削除] フォルダーに移動されると、保持期間が経過するまで、メッセージは保持されます。保持期間が無制限の場合、アイテムは保持が削除されるか保持期間が変更されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="4230d-p117">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires. If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>
    
- <span data-ttu-id="4230d-192">**検索と削除のワークフローが異なるセキュリティ & コンプライアンスセンターの役割グループに分かれているのはなぜですか。**</span><span class="sxs-lookup"><span data-stu-id="4230d-192">**Why is the search and remove workflow divided among different Security & Compliance Center role groups?**</span></span>

    <span data-ttu-id="4230d-p118">前述したように、ユーザーは、電子情報開示マネージャーの役割グループのメンバーであるか、またはメールボックスを検索するためのコンプライアンス検索管理役割を割り当てられている必要があります。メッセージを削除するには、ユーザーが組織の管理役割グループのメンバーであるか、または検索と削除の管理役割を割り当てられている必要があります。これにより、組織内のメールボックスを検索したり、メッセージを削除したりできるユーザーを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="4230d-p118">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes. To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role. This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span> 
