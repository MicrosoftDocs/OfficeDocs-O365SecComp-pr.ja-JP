---
title: メッセージを検索して削除する - 管理者向けヘルプ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 管理者は Search-Mailbox コマンドレットを使って、ユーザーのメールボックスを検索し、メールボックスからメッセージを削除できます。
ms.openlocfilehash: abf7e7f39fe719ecc6c23565e284c01aed8822ee
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260985"
---
# <a name="search-for-and-delete-messages---admin-help"></a><span data-ttu-id="a417a-103">メッセージを検索して削除する - 管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="a417a-103">Search for and delete messages - Admin help</span></span>
  
<span data-ttu-id="a417a-104">管理者は **Search-Mailbox** コマンドレットを使って、ユーザーのメールボックスを検索し、メールボックスからメッセージを削除できます。</span><span class="sxs-lookup"><span data-stu-id="a417a-104">Administrators can use the **Search-Mailbox** cmdlet to search user mailboxes and then delete messages from a mailbox.</span></span> 
  
<span data-ttu-id="a417a-p101">1 回の手順でメッセージを検索して削除するには、 **Search-Mailbox** コマンドレットに  _DeleteContent_ スイッチを指定して実行します。ただし、これを実行する場合、検索によって返される結果をプレビューしたり、メッセージのログを生成したりすることはできないため、削除するつもりのないメッセージを誤って削除してしまう可能性があります。メッセージが削除される前に、検索で見つかったメッセージのログをプレビューするには、 **Search-Mailbox** コマンドレットに  _LogOnly_ スイッチを指定して実行します。</span><span class="sxs-lookup"><span data-stu-id="a417a-p101">To search and delete messages in one step, run the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch. However, when you do this, you can't preview search results or generate a log of messages that will be returned by the search, and you may inadvertently delete messages that you didn't intend to. To preview a log of the messages found in the search before they're deleted, run the **Search-Mailbox** cmdlet with the  _LogOnly_ switch.</span></span> 
  
<span data-ttu-id="a417a-p102">追加の予防手段として、 _TargetMailbox_ および  _TargetFolder_ パラメーターを使用して、最初にメッセージを別のメールボックスにコピーすることができます。これにより、削除されたメッセージに再度アクセスすることが必要になる場合のために、削除されたメッセージのコピーを保持できます。</span><span class="sxs-lookup"><span data-stu-id="a417a-p102">As an additional safeguard, you can first copy the messages to another mailbox by using the  _TargetMailbox_ and  _TargetFolder_ parameters. By doing this, you retain a copy of the deleted messages in case you need to access them again.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="a417a-110">始める前に</span><span class="sxs-lookup"><span data-stu-id="a417a-110">Before you begin</span></span>

- <span data-ttu-id="a417a-p103">予想所要時間 : 10 分。実際の時間は、メールボックスのサイズと検索クエリによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a417a-p103">Estimated time to complete: 10 minutes. The actual time may vary depending on the size of the mailbox and the search query.</span></span>
    
- <span data-ttu-id="a417a-p104">Exchange 管理センター (EAC) を使用して、これらの手順を実行することはできません。シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a417a-p104">You can't use the Exchange admin center (EAC) to perform these procedures. You must use the Shell.</span></span>
    
- <span data-ttu-id="a417a-115">ユーザーのメールボックスにあるメッセージを検索し、削除するためには、次の両方の管理役割を割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a417a-115">You need to be assigned both of the following management roles to search for and delete messages in users' mailboxes:</span></span>
    
  - <span data-ttu-id="a417a-116">**メールボックスの検索**-この役割を使用すると、組織内の複数のメールボックス間でメッセージを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="a417a-116">**Mailbox Search**- This role allows you to search for messages across multiple mailboxes in your organization.</span></span> <span data-ttu-id="a417a-117">既定ではこの役割は管理者には割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="a417a-117">Administrators aren't assigned this role by default.</span></span> <span data-ttu-id="a417a-118">メールボックスを検索できるようにこの役割を自分自身に割り当てるには、探索管理役割グループのメンバーとして自身を追加します。</span><span class="sxs-lookup"><span data-stu-id="a417a-118">To assign yourself this role so that you can search mailboxes, add yourself as a member of the Discovery Management role group.</span></span> <span data-ttu-id="a417a-119">「[ユーザーを Discovery Management 役割グループに追加する」を](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a417a-119">See [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span></span>
    
  - <span data-ttu-id="a417a-120">**メールボックスインポートエクスポート**-この役割を使用すると、ユーザーのメールボックスからメッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a417a-120">**Mailbox Import Export** - This role allows you to delete messages from a user's mailbox.</span></span> <span data-ttu-id="a417a-121">既定では、この役割はどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="a417a-121">By default, this role isn't assigned to any role group.</span></span> <span data-ttu-id="a417a-122">ユーザーのメールボックスからメッセージを削除するために、"Mailbox Import Export" 役割を "組織管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="a417a-122">To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="a417a-123">詳細については、「 [Manage role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) 」の「役割グループに役割を追加する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a417a-123">For more information, see the "Add a role to a role group" section in [Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span></span> 
    
- <span data-ttu-id="a417a-p107">メッセージの削除を行うメールボックスで単一アイテムの回復が有効になっている場合は、最初にその機能を無効にする必要があります。詳細については、「[メールボックスの単一アイテムの回復を有効または無効にする](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a417a-p107">If the mailbox from which you want to delete messages has single item recovery enabled, you must first disable the feature. For more information, see [Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span></span>
    
- <span data-ttu-id="a417a-126">メッセージの削除を行うメールボックスがホールドの対象になっている場合は、ホールドを解除してメールボックスのコンテンツを削除する前に、レコード管理または法務部門に確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a417a-126">If the mailbox from which you want to delete messages is placed on hold, we recommend that you check with your records management or legal department before removing the hold and deleting the mailbox content.</span></span> <span data-ttu-id="a417a-127">承認を得た後、「[回復可能なアイテム」フォルダーをクリーンアップ](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)するトピックに記載されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a417a-127">After you obtain approval, follow the steps listed in the topic [Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span></span>
    
- <span data-ttu-id="a417a-p109">**Search-Mailbox** コマンドレットを使用して、最大 10,000 個のメールボックスを検索できます。10,000 以上のメールボックスを持つ Exchange Online 組織の場合は、コンプライアンス検索機能 (または対応する **New-ComplianceSearch** コマンドレット) を使用して無制限の数のメールボックスを検索できます。その後、 **New-ComplianceSearchAction** コマンドレットを使用して、コンプライアンス検索によって返されたメッセージを削除できます。詳細については、「 [Office 365 組織でメール メッセージの検索と削除を行う - 管理者向けヘルプ](https://go.microsoft.com/fwlink/p/?LinkId=786856)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a417a-p109">You can search a maximum of 10,000 mailboxes using the **Search-Mailbox** cmdlet. If you're an Exchange Online organization and have more than 10,000 mailboxes, you can use the Compliance Search feature (or the corresponding **New-ComplianceSearch** cmdlet) to search an unlimited number of mailboxes. Then you can use the **New-ComplianceSearchAction** cmdlet to delete the messages returned by a compliance search. For more information, see [Search for and delete email messages from your Office 365 organization](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span></span>
    
- <span data-ttu-id="a417a-p110">( *SearchQuery*  パラメーターを使用していて) 検索クエリが含まれている場合、 **Search-Mailbox** コマンドレットは、検索結果で最大 10,000 個のアイテムを返します。したがって、検索クエリを含める場合は、 **Search-Mailbox** コマンドを複数回実行して 10,000 を超えるアイテムを削除する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="a417a-p110">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
    
- <span data-ttu-id="a417a-134">**Search-Mailbox** コマンドレットを実行すると、ユーザーのアーカイブ メールボックスも検索されます。</span><span class="sxs-lookup"><span data-stu-id="a417a-134">The user's archive mailbox will also be searched when you run the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="a417a-135">同様に、  **DeleteContent** スイッチと併せて _Search-Mailbox_ コマンドレットを使用すると、プライマリ アーカイブ メールボックス内のアイテムは削除されます。</span><span class="sxs-lookup"><span data-stu-id="a417a-135">Similarly, items in the primary archive mailbox will be deleted when you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch.</span></span> <span data-ttu-id="a417a-136">これを防ぐために、  *DoNotIncludeArchive*  スイッチを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a417a-136">To prevent this, you can include the  *DoNotIncludeArchive*  switch.</span></span> <span data-ttu-id="a417a-137">また、予期しないデータ損失が発生する可能性があるため、自動拡張アーカイブが有効になっている Exchange Online メールボックス内のメッセージを削除する場合は、 _DeleteContent_スイッチを使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a417a-137">Also, we recommend that you don't use the  _DeleteContent_ switch to delete messages in Exchange Online mailboxes that have auto-expanding archiving enabled because unexpected data loss may occur.</span></span> 
    
## <a name="search-messages-and-log-the-search-results"></a><span data-ttu-id="a417a-138">メッセージを検索し、検索結果をログに記録する</span><span class="sxs-lookup"><span data-stu-id="a417a-138">Search messages and log the search results</span></span>

<span data-ttu-id="a417a-p112">この例は、April Stewart のメールボックスに対し、件名フィールドに「Your bank statement」という語句が含まれるメッセージを検索し、その結果を、管理者のメールボックスの SearchAndDeleteLog フォルダーに記録します。メッセージは、対象のメールボックスにコピーまたは対象のメールボックスから削除されません。</span><span class="sxs-lookup"><span data-stu-id="a417a-p112">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and logs the search results in the SearchAndDeleteLog folder of the administrator's mailbox. Messages aren't copied to or deleted from the target mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="a417a-141">次の使用例は、組織内の全メールボックスでファイル名に「Trojan」という言葉が含まれるあらゆる種類の添付ファイルが付いたメッセージを検索し、管理者のメールボックスにログ メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a417a-141">This example searches all mailboxes in the organization for messages that have any type of attached file that contains the word "Trojan" in the filename and sends a log message to the administrator's mailbox.</span></span>
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="a417a-142">構文およびパラメーターの詳細については、「[Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a417a-142">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
 
## <a name="search-and-delete-messages"></a><span data-ttu-id="a417a-143">メッセージを検索して削除する</span><span class="sxs-lookup"><span data-stu-id="a417a-143">Search and delete messages</span></span>

<span data-ttu-id="a417a-p113">この例は、April Stewart のメールボックスに対し、件名フィールドに「Your bank statement」という語句が含まれるメッセージを検索し、検索結果を別のフォルダーにコピーせずに、そのメッセージをソース メールボックスから削除します。前述のように、ユーザーのメールボックスからメッセージを削除するためには、"Mailbox Import Export" 役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a417a-p113">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and deletes the messages from the source mailbox without copying the search results to another folder. As previously explained, you need to be assigned the Mailbox Import Export management role to delete messages from a user's mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a417a-p114">**Search-Mailbox** コマンドレットに  _DeleteContent_ スイッチを指定して使用すると、メッセージはソース メールボックスから完全に削除されます。メッセージを完全に削除する前に、  _LogOnly_ スイッチを使用して検索で見つかったメッセージが削除される前にログを生成するか、またはメッセージがソース メールボックスから削除される前に別のメールボックスにコピーするかのいずれかを推奨します。</span><span class="sxs-lookup"><span data-stu-id="a417a-p114">When you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch, messages are permanently deleted from the source mailbox. Before you permanently delete messages, we recommend that you either use the  _LogOnly_ switch to generate a log of the messages found in the search before they're deleted or copy the messages to another mailbox before deleting them from the source mailbox.</span></span> 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

<span data-ttu-id="a417a-148">この例は、April Stewart のメールボックスに対し、件名フィールドに「Your bank statement」という語句が含まれるメッセージを検索し、その結果をメールボックス BackupMailbox の AprilStewart-DeletedMessages フォルダーにコピーして、そのメッセージを April のメールボックスから削除します。</span><span class="sxs-lookup"><span data-stu-id="a417a-148">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field, copies the search results to the folder AprilStewart-DeletedMessages in the mailbox BackupMailbox, and deletes the messages from April's mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

<span data-ttu-id="a417a-149">次の使用例は、組織内の全メールボックスで件名が「このファイルをダウンロード」というメッセージを検索してから、完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="a417a-149">This example searches all mailboxes in the organization for messages with the subject line "Download this file", and then permanently deletes them.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

<span data-ttu-id="a417a-150">構文およびパラメーターの詳細については、「[Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a417a-150">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>

## <a name="using-the--loglevel-full-parameter"></a><span data-ttu-id="a417a-151">-LogLevel Full パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="a417a-151">Using the -LogLevel Full parameter</span></span>

<span data-ttu-id="a417a-p115">前のいくつかの例では、 _Search-Mailbox_ コマンドレットによって返された結果に関する詳細情報をログ記録するため、  `Full` 値を指定した  **LogLevel** パラメーターを使用しています。 このパラメーターを含めると、メール メッセージが作成され、  _TargetMailbox_ パラメーターによって指定されたメールボックスに送信されます。ログ ファイル (Search Results.csv という名前の CSV 形式のファイル) はこのメール メッセージに添付され、  _TargetFolder_ パラメーターによって指定されたフォルダーに配置されます。ログ ファイルには、 **Search-Mailbox** コマンドレットを実行すると、検索結果に含まれる各メッセージの行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a417a-p115">In some of the previous examples, the  _LogLevel_ parameter, with the  `Full` value is used to log detailed information about the results returned by the **Search-Mailbox** cmdlet. When you included this parameter, an email message is created and sent to the mailbox specified by the  _TargetMailbox_ parameter. The log file (which is a CSV-formatted file named Search Results.csv) is attached to this email message, and will be located in the folder specified by the  _TargetFolder_ parameter. The log file contains a row for each message that's included in the search results when you run the **Search-Mailbox** cmdlet.</span></span> 
