---
title: Office 365 の管理者として検疫済みメッセージおよびファイルを管理する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
description: '管理者は、Office 365 で誤検知済みの肯定メッセージを表示、リリース、および報告することができます。Office 365 がメッセージをフィルター処理して、複数の理由で検疫にメッセージを送信するようにポリシーを設定できます。これは、スパム、バルク、フィッシング、マルウェア、またはメールフロールールと一致したためです。 '
ms.openlocfilehash: d62aded09f3560de6ba4485757c1bb5ce3f8cb6d
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219197"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a><span data-ttu-id="29817-104">Office 365 の管理者として検疫済みメッセージおよびファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="29817-104">Manage quarantined messages and files as an administrator in Office 365</span></span>

<span data-ttu-id="29817-p102">管理者は、検疫済みメッセージを表示、解放、および削除し、Office 365 で誤検知された肯定メッセージを報告することができます。SharePoint Online、OneDrive for business、Microsoft Teams の詳細な脅威保護 (ATP) によってキャプチャされた検疫済みファイルの表示、ダウンロード、削除を行うこともできます。Office 365 がメッセージをフィルター処理して、いくつかの理由で検疫にメッセージを送信するようにポリシーを設定できます。これは、スパム、バルクメール、フィッシングメール、マルウェアを含む、またはメールフロールールに一致したためです。</span><span class="sxs-lookup"><span data-stu-id="29817-p102">As an admin, you can view, release, and delete quarantined messages, and report false positive quarantined messages in Office 365. You can also view, download, and delete quarantined files captured by Advance Threat Protection (ATP) for SharePoint Online, OneDrive for Business, and Microsoft Teams. You can set up policies so that Office 365 filters messages and sends them to quarantine for several reasons: Because they were identified as spam, bulk mail, phishing mail, containing malware, or because they matched a mail flow rule.</span></span>
  
<span data-ttu-id="29817-p103">既定では、Office 365 はマルウェアを含むフィッシングメッセージおよびメッセージを検疫に直接送信します。その他のフィルター処理されたメッセージは、検疫に送信するポリシーを設定しない限り、ユーザーの迷惑メールフォルダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="29817-p103">By default, Office 365 sends phishing messages and messages containing malware directly to quarantine. Other filtered messages are sent to users' Junk Email folder unless you set up a policy to send them to quarantine.</span></span>
  
<span data-ttu-id="29817-110">他のユーザーに送信された検疫済みメッセージを処理し、検疫済みファイルを操作するには、Office 365 にグローバル管理者 (GA) のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="29817-110">You must have global administrator (GA) permissions in Office 365 to work with quarantined messages that were sent to other users and to work with quarantined files.</span></span>
  
> [!IMPORTANT]
><span data-ttu-id="29817-p104">既定では、スパム、バルクメッセージ、およびフィッシングメッセージは、30日間検疫に保持されます。メールフロールールに一致したために検疫されたメッセージは、7日間検疫に保持されます。マルウェアメッセージは、15日間検疫に保持されます。セキュリティ&amp; /コンプライアンスセンターのスパム対策設定でスパム検疫時間をカスタマイズできます。Office 365 では、検疫からメッセージを削除しても、それを取得することはできません。必要に応じて、スパム対策フィルターポリシーの検疫済みメッセージの保持期間を変更することができます。詳細については、この記事の「[検疫の保存期間の設定](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29817-p104">By default, spam, bulk and phishing messages are kept in quarantine for 30 days. Messages that are quarantined because they matched a mail flow rule are kept in quarantine for 7 days. Malware messages are kept in quarantine for 15 days. You can customize the spam quarantine time in anti-spam settings in the Security &amp; Compliance Center. When Office 365 deletes a message from quarantine, you can't get it back. If you like, you can change the retention period for quarantined messages in your anti-spam filter policies. For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span> 
  
## <a name="view-your-organizations-quarantined-messages"></a><span data-ttu-id="29817-118">組織の検疫済みメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="29817-118">View your organization's quarantined messages</span></span>

1. <span data-ttu-id="29817-119">office 365 組織の全体管理者特権を持つ職場または学校のアカウントを使用して、office 365 にサインインして[、セキュリティ/コンプライアンスセンターに移動](go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="29817-119">Using a work or school account that has global administrator privileges in your Office 365 organization, sign into Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="29817-120">左側のリストで、[脅威の**管理**] を展開し、[**確認**] を選択してから、[**検疫**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29817-120">In the list on the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="29817-121">セキュリティ&amp; /コンプライアンスセンターの [**検疫**] ページに直接移動するには、次の URL を使用します。 >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="29817-121">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
    <span data-ttu-id="29817-p105">既定では、セキュリティ&amp;コンプライアンスセンターには、スパムとして検疫されたすべての電子メールメッセージが表示されます。メッセージは、メッセージが受信された**日付**に基づいて、降順から最古に並べ替えられます。**送信者**、**件名**、および有効期限 (**有効**期限) は、メッセージごとにも表示されます。対応する列見出しをクリックすると、フィールドに対して並べ替えを行うことができます。並べ替え順序を逆にするには、列見出しをもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="29817-p105">By default, the Security &amp; Compliance Center displays all email messages that have been quarantined as spam. The messages are sorted from newest to oldest based on the **Date** the message was received. **Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message. You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span> 
    
3. <span data-ttu-id="29817-p106">すべての検疫済みメッセージの一覧を表示したり、フィルター処理によって結果セットを減らすことができます。一括操作は最大100個のアイテムに対してのみ実行できます。そのため、フィルター処理を行うと、より多くの場合に結果セットを減らすことができます。ページの上部にあるフィルタからオプションを選択することにより、1つの検査理由により、メッセージを簡単にフィルター処理できます。次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="29817-p106">You can view a list of all quarantined messages, or you can reduce the result set by filtering. You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that. You can quickly filter messages for a single quarantine reason by choosing an option from the filter at the top of the page. Options include:</span></span>
    
  - <span data-ttu-id="29817-130">スパムとして識別されたメール</span><span class="sxs-lookup"><span data-stu-id="29817-130">Mail identified as spam</span></span>
    
  - <span data-ttu-id="29817-131">メールフロールール (トランスポートルールとも呼ばれる) によって設定されたポリシーに一致したため、メールが検疫される</span><span class="sxs-lookup"><span data-stu-id="29817-131">Mail quarantined because it matched a policy set by a mail flow rule (also called a transport rule)</span></span>
    
  - <span data-ttu-id="29817-132">バルクメールとして識別されたメール</span><span class="sxs-lookup"><span data-stu-id="29817-132">Mail identified as bulk mail</span></span>
    
  - <span data-ttu-id="29817-133">フィッシングメールとして識別されたメール</span><span class="sxs-lookup"><span data-stu-id="29817-133">Mail identified as phishing mail</span></span>
    
  - <span data-ttu-id="29817-134">マルウェアを含むメールの検疫</span><span class="sxs-lookup"><span data-stu-id="29817-134">Mail quarantined because it contains malware</span></span>
    
<span data-ttu-id="29817-p107">さらに、管理者として、組織のすべてのメッセージをフィルター処理するか、自分に送信されたメッセージのみをフィルター処理するかを選択できます。エンドユーザーは、それらに送信されたメッセージの表示と操作のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="29817-p107">In addition, as an admin, you can choose to filter all messages for your organization or only messages sent to you. End users can only view and work with messages sent to them.</span></span>
  
<span data-ttu-id="29817-p108">特定のメッセージを検索するために結果をフィルター処理することもできます。ヒントについては、この記事の「[結果をフィルター処理して、検疫済みのメッセージおよびファイルを検索するに](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)は」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29817-p108">You can also filter your results to find specific messages. For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span> 
  
<span data-ttu-id="29817-139">特定の検疫済みメッセージを見つけた後、メッセージをクリックしてそのメッセージの詳細を表示し、他のユーザーのメールボックスにメッセージを解放するなどのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="29817-139">After you find a specific quarantined message, click the message to view details about it, and take actions, like releasing the message to someone's mailbox.</span></span>
  
## <a name="view-your-organizations-quarantined-files"></a><span data-ttu-id="29817-140">組織の検疫済みファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="29817-140">View your organization's quarantined files</span></span>

1. <span data-ttu-id="29817-141">office 365 組織のグローバル管理者特権を持つ職場または学校のアカウントを使用して、office 365 にサインインし、[セキュリティ/コンプライアンスセンターに移動](go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="29817-141">Using a work or school account that has global administrator privileges in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="29817-142">左側の [脅威の**管理**] を展開し、[**確認**] を選択して、[**検疫**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29817-142">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span> <br/>
    > [!TIP]
    > <span data-ttu-id="29817-143">セキュリティ&amp; /コンプライアンスセンターの [**検疫**] ページに直接移動するには、次の URL を使用します。 >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="29817-143">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
3. <span data-ttu-id="29817-p109">既定では、ページには検疫された電子メールメッセージが表示されます。検疫されたファイルを表示するには、ページの上部にあるフィルターを、**マルウェア**によって検疫された**ファイル**を表示するように設定します。検疫済みファイルを操作するには、Office 365 で管理者権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="29817-p109">By default, the page displays quarantined email messages. To view quarantined files, set the filters at the top of the page to show **files**, quarantined due to **malware**. You must have admin permissions in Office 365 to work with quarantined files.</span></span> 
    
4. <span data-ttu-id="29817-p110">ファイルは、ファイルが検疫された日付に基づいて、最新から最古の順に並べ替えられます。ファイルを最後に変更した**ユーザー** 、ファイルが投稿された**サービス**、ファイル**名**、**場所**、**ファイルのサイズ**、有効期限 (**有効**期限) は、各ファイルにも表示されます。ヘッダーをクリックすることで、フィールドに対して並べ替えを行うことができます。並べ替え順序を逆にするには、列見出しをもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="29817-p110">The files are sorted from newest to oldest based on the date the file was quarantined. The **User** who last modified the file, the **Service** to which the file was posted, the **File Name**, **Location**, **File Size**, and the expiration date ( **Expires**) are also listed for each file. You can sort on a field by clicking a header; click a column header a second time to reverse the sort order.</span></span>
    
<span data-ttu-id="29817-p111">検疫されたすべてのファイルの一覧を表示することも、フィルター処理によって特定のファイルを検索することもできます。メッセージと同様に、一括操作は最大100アイテムに対してのみ実行できます。現在、セキュリティ&amp;コンプライアンスセンターでは、マルウェアが含まれていると識別されるため、検疫内のファイルを表示および管理できます。ヒントについては、この記事の「[結果をフィルター処理して、検疫済みのメッセージおよびファイルを検索するに](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)は」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29817-p111">You can view a list of all quarantined files, or you can search for specific files by filtering. Just like messages, you can only do bulk operations on up to 100 items. Currently, the Security &amp; Compliance Center lets you view and manage files that are in quarantine because they have been identified as containing malware. For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span> 
  
## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a><span data-ttu-id="29817-154">結果をフィルター処理して、検疫済みのメッセージおよびファイルを検索するには</span><span class="sxs-lookup"><span data-stu-id="29817-154">To filter results and find quarantined messages and files</span></span>
<span data-ttu-id="29817-155"><a name="BKMK_AdvSearch"> </a></span><span class="sxs-lookup"><span data-stu-id="29817-155"></span></span>

<span data-ttu-id="29817-p112">設定によっては、検疫されたメッセージとファイルが多数存在することがあります。特定のメッセージまたはファイル、あるいは一連のメッセージまたはファイルを検索するには、さまざまな追加情報に基づいて検疫済みアイテムをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="29817-p112">Depending on your settings, there may be a lot of quarantined messages and files. To find a specific message or file or set of messages or files, you can filter quarantined items based on a variety of additional information.</span></span>
  
1. <span data-ttu-id="29817-158">[**検疫**] ページで、フィルターの先頭行が、必要に応じてメッセージまたはファイルを表示するように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29817-158">On the **Quarantine** page, ensure that the top row of filters is set to display messages or files as appropriate:</span></span> 
    
      - <span data-ttu-id="29817-159">ファイルを検索するには、**マルウェア**によって検疫された**ファイル**を表示するようにフィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="29817-159">To search for files, set the filters to show **files** quarantined due to **malware**.</span></span><br/>
    <span data-ttu-id="29817-160">検疫されたファイルの場合、ページには、表示するように指示されているかどうかにかかわらず、自分だけでなく、すべての検疫済みファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="29817-160">For quarantined files, the page displays all quarantined files, not just your own, regardless of what you tell it to show.</span></span>
    
      - <span data-ttu-id="29817-p113">検疫済みメッセージを検索するには、**すべて**の\*\*\*\* **メール**を表示するようにフィルターを設定します。最後のフィルターの場合は、探している検疫済みメッセージの種類を選択します。メールフローや**トランスポートルール**、**バルク**メール、**フィッシング**メール、または**マルウェア**が含まれるメールに一致するメッセージに対して、**スパム**として識別された検疫済みメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="29817-p113">To search for quarantined messages, set filters to show **all** or **only my** **email**. For the last filter choose the type of quarantined message that you're looking for. You can search for quarantined messages that have been identified as **spam**, for messages that matched a mail flow or **transport rule**, **bulk** mail, **phishing** mail, or mail that contains **malware**.</span></span>
    
2. <span data-ttu-id="29817-p114">[**結果の並べ替え**] で、ドロップダウンリストから検索するために使用するフィルターを選択します。オプションは、ファイルまたはメッセージを検索するかどうかに応じて異なります。この時点では、検索フィールドではワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="29817-p114">Under **Sort results by**, choose the filter or filters you want to use to search from the drop-down lists. The options vary based on whether you are searching for files or messages. Wildcards are not supported in search fields at this time.</span></span><br/><br/><span data-ttu-id="29817-p115">ファイルとメッセージの両方について、メッセージまたはファイルが検疫に送信された日付によってフィルター処理することを選択できます。時刻を含む日付または日付の範囲を指定できます。また、ファイルまたはメッセージが検疫から削除される有効期限の日付で検索結果をフィルター処理したり、フィルターの組み合わせを使用したりすることもできます。有効期限を指定して検索するには、[**高度なフィルター**] を選択します。[**有効期限**] の下で、次の週に、今後24時間以内 (**今日**)、次の週 (次の\*\*\*\* **7**日) 以内に削除するメッセージを選択できます。または、カスタムの時間間隔を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="29817-p115">For both files and messages, you can choose to filter by the date the message or file was sent to quarantine. You can specify the date or a date range, including the time. You can also filter your search results by the expiration date on which the file or message will be deleted from quarantine, or you can use a combination of filters. To search by expiration date, choose **Advanced filter**. Under **Expires**, you can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span><br/><br/><span data-ttu-id="29817-172">メッセージの場合は、次の追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="29817-172">For messages, you have the following additional options:</span></span>
    
      - <span data-ttu-id="29817-p116">**メッセージ ID**。これを使用して、メッセージ ID がわかっている場合に特定のメッセージを特定します。</span><span class="sxs-lookup"><span data-stu-id="29817-p116">**Message ID**. Use this to identify a specific message when you know the message ID.</span></span><br/><br/><span data-ttu-id="29817-p117">たとえば、特定のメッセージが組織内のユーザーによって送信された場合、またはそのユーザーが送信先に到達していない場合は、メッセージの追跡を使用してメッセージを検索できます (「[メッセージの追跡を実行し、結果を表示する](https://go.microsoft.com/fwlink/?LinkId=799737)」を参照してください)。メッセージが検疫に送信されたことがわかった場合は、メールフロールールと一致した、またはスパムとして識別されたために、メッセージ ID を指定することによって、このメッセージを検疫で簡単に見つけることができます。完全なメッセージ ID 文字列を含めるようにしてください。これには、次の\<\>例のような山かっこ () が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="29817-p117"> For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Run a Message trace and View Results](https://go.microsoft.com/fwlink/?LinkId=799737)). If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its message ID. Be sure to include the full message ID string. This might include angle brackets (\<\>), for example:</span></span><br/>
    `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`
    
      - <span data-ttu-id="29817-p118">**送信者の電子メールアドレス**。単一の送信者の電子メールアドレスによるフィルター処理を選択します。</span><span class="sxs-lookup"><span data-stu-id="29817-p118">**Sender email address**. Choose to filter by a single sender email address.</span></span> 
    
      - <span data-ttu-id="29817-p119">**受信者の電子メールアドレス**。単一の受信者の電子メールアドレスによるフィルター処理を選択します。</span><span class="sxs-lookup"><span data-stu-id="29817-p119">**Recipient email address**. Choose to filter by a single recipient email address.</span></span> 
    
      - <span data-ttu-id="29817-p120">**件名**。検索するメールアドレスの件名を入力します。ワイルドカード検索はサポートされていないため、検索でメッセージを結果に返すためには、メッセージの件名全体を使用する必要があります。検索では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="29817-p120">**Subject**. Enter the subject of an email address you want to find. Since wildcard searching is not supported, you must use the entire subject of the message in order for search to return the message in the results. The search is not case-sensitive.</span></span> 
    
## <a name="view-details-about-quarantined-messages-and-files"></a><span data-ttu-id="29817-187">検疫されたメッセージとファイルの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="29817-187">View details about quarantined messages and files</span></span>

<span data-ttu-id="29817-188">検疫リストに表示されているアイテムを選択すると、そのプロパティの概要が、セキュリティ\*\*\*\* &amp;コンプライアンスセンターの右側の詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="29817-188">When you select an item displayed in the quarantine list, you'll see a summary of its properties in the **Details** pane on the right side of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="29817-189">**検疫済みメッセージに関して表示される詳細情報**</span><span class="sxs-lookup"><span data-stu-id="29817-189">**Details displayed for quarantined messages**</span></span>
  
- <span data-ttu-id="29817-p121">**メッセージ ID**。メッセージの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="29817-p121">**Message ID**. The unique identifier for the message.</span></span> 
    
- <span data-ttu-id="29817-p122">**送信者のアドレス**。メッセージを送信したユーザー。</span><span class="sxs-lookup"><span data-stu-id="29817-p122">**Sender Address**. Who sent the message.</span></span> 
    
- <span data-ttu-id="29817-p123">**受信しました**。メッセージが受信された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="29817-p123">**Received**. The date and time the message was received.</span></span> 
    
- <span data-ttu-id="29817-p124">**件名**。メッセージの件名行のテキスト。</span><span class="sxs-lookup"><span data-stu-id="29817-p124">**Subject**. The text of the subject line of the message.</span></span> 
    
- <span data-ttu-id="29817-p125">**種類**。メッセージが**スパム**、 **Bulk**、**フィッシング**、メールフロールール (**トランスポートルール**) と一致した、または**マルウェア**が含まれていると識別されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="29817-p125">**Type**. Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule ( **Transport rule**), or was identified as containing **Malware**.</span></span>
    
- <span data-ttu-id="29817-p126">**有効期限が切れ**ます。メッセージが自動的に検疫から削除される日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="29817-p126">**Expires**. The date and time when the message will automatically be deleted from quarantine.</span></span> 
    
- <span data-ttu-id="29817-p127">**にリリース**されました。メッセージがリリースされたすべての電子メールアドレス (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="29817-p127">**Released to**. All email addresses (if any) to which the message has been released.</span></span> 
    
- <span data-ttu-id="29817-p128">**まだにリリースされていません**。メッセージがまだリリースされていないすべての電子メールアドレス (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="29817-p128">**Not yet released to**. All email addresses (if any) to which the message has not yet been released.</span></span> 
    
 <span data-ttu-id="29817-206">**検疫されたファイルの詳細情報**</span><span class="sxs-lookup"><span data-stu-id="29817-206">**Details displayed for quarantined files**</span></span>
  
- <span data-ttu-id="29817-207">**ファイル名**検疫に含まれるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="29817-207">**File Name** The name of the file in quarantine.</span></span> 
    
- <span data-ttu-id="29817-208">**サイトパス**Office 365 でのファイルの場所を定義する URL。</span><span class="sxs-lookup"><span data-stu-id="29817-208">**Site path** URL that defines the location of the file in Office 365.</span></span> 
    
- <span data-ttu-id="29817-209">**検出された日付/時刻**ファイルが検疫された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="29817-209">**Detected Date / Time** The date and time the file was quarantined.</span></span> 
    
- <span data-ttu-id="29817-210">**期限切れ**メッセージが検疫から削除される日付。</span><span class="sxs-lookup"><span data-stu-id="29817-210">**Expires** The date when the message will be deleted from quarantine.</span></span> 
    
- <span data-ttu-id="29817-p129">**検出者**ファイル内のマルウェアを検出するために使用されるメソッド。ATP (Advanced Threat Protection) または Microsoft のマルウェア対策エンジンのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29817-p129">**Detected By** The method used to detect the malware in the file. This can be either ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span> 
    
- <span data-ttu-id="29817-213">**リリース**ファイルがリリースされているかどうかを表します。</span><span class="sxs-lookup"><span data-stu-id="29817-213">**Released** Describes whether or not the file has been released.</span></span> 
    
- <span data-ttu-id="29817-214">**マルウェアの名前**ファイル内で検出されたマルウェアのファミリと名前。</span><span class="sxs-lookup"><span data-stu-id="29817-214">**Malware Name** Family and name of the malware detected in the file.</span></span> 
    
- <span data-ttu-id="29817-215">**ドキュメント ID**ドキュメントの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="29817-215">**Document ID** A unique identifier for the document.</span></span> 
    
- <span data-ttu-id="29817-216">**ファイルサイズ**ファイルのサイズ (KB 単位)。</span><span class="sxs-lookup"><span data-stu-id="29817-216">**File Size** The size of the file in KB.</span></span> 
    
- <span data-ttu-id="29817-217">**組織**Office 365 の組織の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="29817-217">**Organization** Your organization's unique ID in Office 365.</span></span> 
    
- <span data-ttu-id="29817-218">**更新者**ファイルを最後に変更したユーザーの職場または学校のアカウント。</span><span class="sxs-lookup"><span data-stu-id="29817-218">**Modified By** The work or school account of the user who last modified the file.</span></span> 
    
- <span data-ttu-id="29817-219">**ファイルサイズ**ファイルのサイズ (KB 単位)。</span><span class="sxs-lookup"><span data-stu-id="29817-219">**File Size** The size of the file in KB.</span></span> 
    
- <span data-ttu-id="29817-p130">**SHA256 ハッシュ**ファイルのハッシュ。これを使用して、他の評価ストアを検索することもできます。または、ファイルが環境内に存在する可能性があることを調査します。</span><span class="sxs-lookup"><span data-stu-id="29817-p130">**SHA256 Hash** The hash of the file. You can use this to look up other reputation stores you may have or investigate where else the file might be in your environment.</span></span> 
    
## <a name="managing-messages-and-files-in-quarantine"></a><span data-ttu-id="29817-222">検疫でのメッセージとファイルの管理</span><span class="sxs-lookup"><span data-stu-id="29817-222">Managing messages and files in quarantine</span></span>
<span data-ttu-id="29817-223"><a name="BKMK_ManageQuarantinedItem"> </a></span><span class="sxs-lookup"><span data-stu-id="29817-223"></span></span>

<span data-ttu-id="29817-224">メッセージまたはメッセージのグループを選択したら、検疫内のメッセージを管理するためのいくつかのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29817-224">After you select a message or group of messages you have several options for managing messages in quarantine.</span></span>
  
- <span data-ttu-id="29817-p131">何も行いません。何もしない場合は、有効期限が切れたときに Office 365 によってメッセージが自動的に削除されます。既定では、メールフロールールに一致したために検疫されたスパム、バルク、マルウェア、フィッシング、メッセージは、30日間検疫に保存されます。Office 365 では、検疫からメッセージを削除しても、それを取得することはできません。必要に応じて、スパム対策ポリシーの [**スパムを保持する (日)** ] の設定を構成することによって、検疫済みメッセージの保持期間を変更できます。詳細については、この記事の「[検疫の保存期間の設定](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29817-p131">Do nothing. If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration. By default, spam, bulk, malware, phishing, and messages quarantined because they matched a mail flow rule are kept in quarantine for 30 days. When Office 365 deletes a message from quarantine, you can't get it back. If you like, you can change the retention period for quarantined messages by configuring the **Retain spam for (days)** setting in your anti-spam policies. For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span> 
    
- <span data-ttu-id="29817-p132">**メッセージヘッダーを表示**するメッセージヘッダーのテキストを表示するには、このリンクを選択します。ヘッダーを詳細に分析するには、メッセージヘッダーのテキストをクリップボードにコピーし、[ **Microsoft メッセージヘッダーアナライザー** ] を選択して、リモート接続アナライザーに移動します (Office を終了しない場合は、右クリックして [**新しいタブで開く]** を選択します)このタスクを完了するには、365。メッセージヘッダーを [メッセージヘッダーアナライザー] セクションのページに貼り付け、[**ヘッダーの分析**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29817-p132">**View message header** Choose this link to see the message header text. To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**.</span></span>
    
- <span data-ttu-id="29817-p133">**プレビューメッセージ**メッセージ本文の raw または HTML バージョンを表示できます。HTML ビューでは、リンクは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="29817-p133">**Preview message** Lets you see raw or HTML versions of the message body text. In the HTML view, links are disabled.</span></span> 
    
- <span data-ttu-id="29817-p134">**メッセージをダウンロード**するか、**ファイルをダウンロード**します。このオプションを選択すると、メッセージまたはファイルのコピーがローカルデバイスにダウンロードされます。許可する前に、検疫からのアイテムのダウンロードに関連するリスクを理解していることを確認する必要があります。メッセージは、指定したフォルダーに .eml 形式で保存されます。検疫済みファイルは、元の形式で保存されます。</span><span class="sxs-lookup"><span data-stu-id="29817-p134">**Download message** or **Download file**. Choose this option to download a copy of the message or file to your local device. You'll need to confirm that you understand the risks associated with downloading items from quarantine before you'll be allowed to do so. Messages are saved in .eml format to a folder you specify. Quarantined files are saved in their original format.</span></span>
    
- <span data-ttu-id="29817-p135">**削除**必要に応じて、Office 365 によって設定された有効期限を待つ代わりに、検疫されたアイテム (またはアイテムのセット) をすぐに削除できます。メッセージまたはファイルを削除するには、[検疫] ボックスの一覧でアイテムを選択し、[**削除**] を選択します。一度に複数のアイテムを削除するには、[検疫] リスト内のアイテムの左側にあるチェックボックスをオンにし、表示される [**一括アクション**] ページで、[選択した**メッセージを削除**する] または [**選択したファイルを削除**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29817-p135">**Delete** If you want, you can immediately delete a quarantined item (or set of items) instead of waiting for the expiration date set by Office 365. To delete a message or file, in the quarantine list, select the item and then choose **Delete**. To delete multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Delete selected messages** or **Delete selected files**.</span></span>
    
- <span data-ttu-id="29817-243">**リリース**検疫されたアイテム (またはアイテムのセット) を解放し、そのアイテムを誤検知 (誤検知) として Microsoft に報告します。</span><span class="sxs-lookup"><span data-stu-id="29817-243">**Release** Release a quarantined item (or set of items) and report the items as falsely quarantined (false positives) to Microsoft.</span></span> 
    
    <span data-ttu-id="29817-p136">1つのメッセージまたはファイルを解放して報告するには、[検疫] の一覧でアイテムを選択し、[**ファイルの解放**] または [**メッセージの解放**] を選択します。次のページで、[分析の**ために microsoft に**、または**ファイル**を分析用に microsoft に報告する] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29817-p136">To release and report a single message or file, in the quarantine list, select the item, choose **Release file** or **Release message**. On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span> 
    
    <span data-ttu-id="29817-p137">一度に複数のアイテムを解放するには、[検疫] リスト内のアイテムの左側にあるチェックボックスをオンにし、表示される [**一括アクション**] ページで、[**ファイルの解放**] または [**メッセージの解放**] を選択します。次のページで、[分析の**ために microsoft に**、または**ファイル**を分析用に microsoft に報告する] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29817-p137">To release multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Release files** or **Release messages**. On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span> 
    
<span data-ttu-id="29817-248">メッセージを解放するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="29817-248">When you're releasing messages, be aware of the following:</span></span>
  
- <span data-ttu-id="29817-p138">一度に複数のメッセージの一括リリースを実行すると、メッセージは元に識別されたすべての受信者に解放されます。特定の受信者にのみメッセージを解放する場合は、一度に1つずつメッセージを解放し、受信者を個別に特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29817-p138">When you perform a bulk release of multiple messages at once, the messages are released to all originally identified recipients. If you only want to release messages only to specific recipients, you need to release the messages one at a time and identify the recipients individually.</span></span>
    
- <span data-ttu-id="29817-251">同じ受信者に2回以上メッセージを解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="29817-251">A message cannot be released more than once to the same recipient.</span></span>
    
- <span data-ttu-id="29817-252">複数の受信者にメッセージを解放すると、メッセージを受信していない受信者のみが、潜在的な受信者の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="29817-252">When you're releasing a message to more than one recipient, only recipients who have not previously received the message will appear in the list of potential recipients.</span></span>
    
- <span data-ttu-id="29817-p139">誤検知を報告することを選択すると、解放されたメッセージまたはメッセージがスパム、バルク、フィッシング、またはマルウェアを含むものとして検疫された場合、そのメッセージも Microsoft スパム分析チームに報告されます。チームはメッセージの評価と分析を行い、分析結果によっては、サービス全体のスパムコンテンツフィルタールールを調整してメッセージを通過できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="29817-p139">When you choose to report false positives, if the message or messages you release were quarantined as spam, bulk, phishing, or as containing malware, the message will also be reported to the Microsoft Spam Analysis Team. The team will evaluate and analyze the message, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
    
## <a name="setting-the-quarantine-retention-period"></a><span data-ttu-id="29817-255">検疫の保存期間の設定</span><span class="sxs-lookup"><span data-stu-id="29817-255">Setting the quarantine retention period</span></span>
<span data-ttu-id="29817-256"><a name="BKMK_ModQuarantineTime"> </a></span><span class="sxs-lookup"><span data-stu-id="29817-256"></span></span>

<span data-ttu-id="29817-p140">期限切れになるまでに、メッセージおよびファイルを検疫に保持する期間を構成できます。既定では、検疫済みアイテムは30日間保持されます。この設定は、作成するポリシーごとに構成します。この記事で説明されているように、既定のポリシーの値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="29817-p140">You can configure how long messages and files will remain in quarantine before they expire. By default, quarantined items are kept for 30 days. You configure this setting for each policy that you create. You can also modify the value for the default policy as described in this article.</span></span> 
  
### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a><span data-ttu-id="29817-261">セキュリティ/コンプライアンスセンターで既定のスパムフィルターポリシーの検疫保持期間を変更するには</span><span class="sxs-lookup"><span data-stu-id="29817-261">To modify the quarantine retention period for the default spam filter policy in the Security and Compliance Center</span></span>

1. <span data-ttu-id="29817-262">office 365 組織のグローバル管理者特権を持つ職場または学校のアカウントを使用して、office 365 にサインインし、[セキュリティ/コンプライアンスセンターに移動](go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="29817-262">Using a work or school account that has global administrator privileges in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="29817-263">左側の [脅威の**管理**] を展開し、[**ポリシー**] を選択してから、[**スパム対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29817-263">On the left, expand **Threat Management**, choose **Policy**, and then choose **Anti-spam**.</span></span> <br/>
    > [!TIP]
    > <span data-ttu-id="29817-264">セキュリティ&amp; /コンプライアンスセンターの [**スパム対策**] ページに直接移動するには、次の URL を使用します。 >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span><span class="sxs-lookup"><span data-stu-id="29817-264">To go directly to the **anti-spam** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span></span>
  
3. <span data-ttu-id="29817-265">[**カスタム**] を選択して、[**カスタム設定**] タブを表示します。</span><span class="sxs-lookup"><span data-stu-id="29817-265">Choose **Custom** to display the **Custom settings** tab.</span></span> 
    
4. <span data-ttu-id="29817-266">**[既定のスパムフィルターポリシー (always ON)** ] 行を展開します。</span><span class="sxs-lookup"><span data-stu-id="29817-266">Expand the **Default spam filter policy (always ON)** row.</span></span> 
    
5. <span data-ttu-id="29817-p141">[**ポリシーの編集**] を選択します。既定のスパムフィルターポリシーの設定が新しいページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="29817-p141">Choose **Edit policy**. The settings for the default spam filter policy appear in a new page.</span></span>
    
6. <span data-ttu-id="29817-269">**[スパムと一括アクション] を**展開します。</span><span class="sxs-lookup"><span data-stu-id="29817-269">Expand **Spam and bulk actions**.</span></span>
    
7. <span data-ttu-id="29817-p142">[**検疫**] の [以下**の期間スパムを保持する (日)** ] テキストボックスに、Office 365 でメッセージおよびファイルを検疫に保持する時間の長さを入力します。既定値は30日です。これは最大値でもあります。</span><span class="sxs-lookup"><span data-stu-id="29817-p142">Under **Quarantine**, in the **Retain spam for (days)** text box, enter the amount of time you want Office 365 to retain messages and files in quarantine. The default is 30 days. This is also the maximum.</span></span> 
    
8. <span data-ttu-id="29817-273">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29817-273">Choose **Save**.</span></span>
    

