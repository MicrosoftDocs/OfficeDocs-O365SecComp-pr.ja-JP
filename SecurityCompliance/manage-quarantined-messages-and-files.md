---
title: Office 365 の管理者として検疫されたメッセージやファイルを管理します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
description: '管理者として表示、離すと、して Office 365 の正偽の検疫済みメッセージを報告できます。Office 365 は、メッセージをフィルター処理し、いくつかの理由を検査するそれらを送信するようポリシーを設定することができます: 迷惑メール、一括、フィッシング、マルウェアと、認識されたため、またはメール フロー ルールに一致するためです。 '
ms.openlocfilehash: be6384d8937e25aec55d82d8212c49d25b64b9a1
ms.sourcegitcommit: d85fc77cba3a17d5ddf215e2f506f61b499e0cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "23839101"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a><span data-ttu-id="650d5-104">Office 365 の管理者として検疫されたメッセージやファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="650d5-104">Manage quarantined messages and files as an administrator in Office 365</span></span>

<span data-ttu-id="650d5-p102">管理者としてはことができます表示、およびを離すと、検疫済みのメッセージ、およびレポート false 正検疫済みのメッセージには、Office 365 を削除します。ことができますも表示、ダウンロード、および SharePoint のオンライン、OneDrive のビジネス、およびマイクロソフトのチームの高度脅威保護 (ATP) によってをキャプチャする検疫済みファイルを削除します。Office 365 は、メッセージをフィルター処理し、いくつかの理由を検査するそれらを送信するようポリシーを設定することができます: スパム、迷惑メール、フィッシング詐欺メール、マルウェアが含まれていると、認識されたため、またはメール フロー ルールに一致するためです。</span><span class="sxs-lookup"><span data-stu-id="650d5-p102">As an admin, you can view, release, and delete quarantined messages, and report false positive quarantined messages in Office 365. You can also view, download, and delete quarantined files captured by Advance Threat Protection (ATP) for SharePoint Online, OneDrive for Business, and Microsoft Teams. You can set up policies so that Office 365 filters messages and sends them to quarantine for several reasons: Because they were identified as spam, bulk mail, phishing mail, containing malware, or because they matched a mail flow rule.</span></span>
  
<span data-ttu-id="650d5-p103">既定では、Office 365 は、フィッシング詐欺メールとマルウェアを含むメッセージを検疫に直接送信します。その他のフィルター処理されたメッセージは、検疫に送信するポリシーを設定する場合を除き、ユーザーの迷惑メール フォルダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="650d5-p103">By default, Office 365 sends phishing messages and messages containing malware directly to quarantine. Other filtered messages are sent to users' Junk Email folder unless you set up a policy to send them to quarantine.</span></span>
  
<span data-ttu-id="650d5-110">他のユーザーに送信された検疫済みのメッセージを処理して、検疫済みのファイルを操作するのには、Office 365 の管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="650d5-110">You must have admin permissions in Office 365 to work with quarantined messages that were sent to other users and to work with quarantined files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="650d5-p104">既定では、迷惑メール、一括、マルウェア、フィッシング、およびメール フロー ルールに一致するために検疫されたメッセージは検疫で 30 日間保存します。スパム対策の設定、セキュリティでの検査時間をカスタマイズすることができます&amp;コンプライアンス センターです。Office 365 は、検疫からのメッセージを削除と、することはできませんを元に戻します。必要な場合は、スパム対策フィルター ポリシーに、検疫されたメッセージの保存期間を変更できます。詳細については、この資料で[検疫保存期間を設定する](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="650d5-p104">By default, spam, bulk, malware, phishing, and messages that were quarantined because they matched a mail flow rule are kept in quarantine for 30 days. You can customize the quarantine time in anti-spam settings in the Security &amp; Compliance Center. When Office 365 deletes a message from quarantine, you can't get it back. If you like, you can change the retention period for quarantined messages in your anti-spam filter policies. For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span> 
  
## <a name="view-your-organizations-quarantined-messages"></a><span data-ttu-id="650d5-116">組織の検疫済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="650d5-116">View your organization's quarantined messages</span></span>

1. <span data-ttu-id="650d5-117">グローバル管理者権限を持つ、Office 365 の組織で、職場、学校のアカウントを使用するは、Office 365 と[、セキュリティとコンプライアンス センター](go-to-the-securitycompliance-center.md)に署名します。</span><span class="sxs-lookup"><span data-stu-id="650d5-117">Using a work or school account that has global administrator privileges in your Office 365 organization, sign into Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="650d5-118">左側のボックスの一覧で**脅威の管理**] を展開、**レビュー**を選択し、**検査**します。</span><span class="sxs-lookup"><span data-stu-id="650d5-118">In the list on the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="650d5-119">セキュリティ**検査**のページに直接移動するのには&amp;コンプライアンス センターでは、この URL を使用して: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="650d5-119">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
    <span data-ttu-id="650d5-p105">既定では、セキュリティ&amp;コンプライアンス センターでは、スパムとして検疫されたすべての電子メール メッセージが表示されます。メッセージに基づいて並べ替えられます。 から順にメッセージが受信された**日付**。各メッセージの**送信者**、**件名**、および有効期限の日付 ([**期限切れ日時**) が表示されますも。フィールドを対応する列ヘッダーをクリックして並べ替えることができます。並べ替え順序を逆にするには列ヘッダーをもう一度をクリックします。</span><span class="sxs-lookup"><span data-stu-id="650d5-p105">By default, the Security &amp; Compliance Center displays all email messages that have been quarantined as spam. The messages are sorted from newest to oldest based on the **Date** the message was received. **Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message. You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span> 
    
3. <span data-ttu-id="650d5-p106">すべての検疫済みのメッセージの一覧を表示することができますか、結果セットをフィルタ リングを減らすことができます。のみ実行できますので、フィルター処理も軽減できます、結果セットの多くのことがある場合、最大 100 個のアイテムに対して操作を一括します。迅速にページの上部にあるフィルターのオプションを選択して 1 つの検査の理由でメッセージをフィルターできます。オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="650d5-p106">You can view a list of all quarantined messages, or you can reduce the result set by filtering. You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that. You can quickly filter messages for a single quarantine reason by choosing an option from the filter at the top of the page. Options include:</span></span>
    
  - <span data-ttu-id="650d5-128">メールが迷惑メールとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="650d5-128">Mail identified as spam</span></span>
    
  - <span data-ttu-id="650d5-129">メール フロー ルール (トランスポート ルールとも呼ばれます) によって設定されたポリシーに一致するために検疫されたメールは、</span><span class="sxs-lookup"><span data-stu-id="650d5-129">Mail quarantined because it matched a policy set by a mail flow rule (also called a transport rule)</span></span>
    
  - <span data-ttu-id="650d5-130">メールが迷惑メールとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="650d5-130">Mail identified as bulk mail</span></span>
    
  - <span data-ttu-id="650d5-131">メールのフィッシング詐欺メールとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="650d5-131">Mail identified as phishing mail</span></span>
    
  - <span data-ttu-id="650d5-132">マルウェアが含まれているために検疫されたメール</span><span class="sxs-lookup"><span data-stu-id="650d5-132">Mail quarantined because it contains malware</span></span>
    
<span data-ttu-id="650d5-p107">さらに、管理者として、組織のすべてのメッセージまたは送信メッセージのみにフィルターを適用することができます。ユーザーが専用のビューを終了し、メッセージを送信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="650d5-p107">In addition, as an admin, you can choose to filter all messages for your organization or only messages sent to you. End users can only view and work with messages sent to them.</span></span>
  
<span data-ttu-id="650d5-p108">特定のメッセージを検索する検索結果を抽出することもできます。ヒントについては、この資料の[結果をフィルター処理し、検疫済みのメッセージとファイルを検索して](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)参照してください。</span><span class="sxs-lookup"><span data-stu-id="650d5-p108">You can also filter your results to find specific messages. For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span> 
  
<span data-ttu-id="650d5-137">特定の検疫済みのメッセージを確認した後、詳細を表示するメッセージをクリックし、他のユーザーの受信トレイにメッセージを解放するように、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="650d5-137">After you find a specific quarantined message, click the message to view details about it, and take actions, like releasing the message to someone's inbox.</span></span>
  
## <a name="view-your-organizations-quarantined-files"></a><span data-ttu-id="650d5-138">組織の検疫済みファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="650d5-138">View your organization's quarantined files</span></span>

1. <span data-ttu-id="650d5-139">グローバル管理者権限を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Office 365[のセキュリティとコンプライアンスの中央に移動](go-to-the-securitycompliance-center.md)してサインインします。</span><span class="sxs-lookup"><span data-stu-id="650d5-139">Using a work or school account that has global administrator privileges in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="650d5-140">、左側の**脅威の管理**] を展開、**レビュー**、を選択し、**検査**します。</span><span class="sxs-lookup"><span data-stu-id="650d5-140">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="650d5-141">セキュリティ**検査**のページに直接移動するのには&amp;コンプライアンス センターでは、この URL を使用して: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="650d5-141">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
3. <span data-ttu-id="650d5-p109">既定では、ページには、検疫済みの電子メール メッセージが表示されます。検疫済みファイルを表示するには、**ファイル**を**マルウェア**によって検疫を表示するページの上部にあるフィルターを設定します。検疫済みのファイルを操作するのには Office 365 の管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="650d5-p109">By default, the page displays quarantined email messages. To view quarantined files, set the filters at the top of the page to show **files**, quarantined due to **malware**. You must have admin permissions in Office 365 to work with quarantined files.</span></span> 
    
4. <span data-ttu-id="650d5-p110">ファイルはに基づいて並べ替えられますから順に、ファイルが検疫された日付。最後の**ユーザー**は、ファイル、**サービス**ファイルが転記されると、**ファイル名**、**場所**、**ファイルのサイズ**、有効期限 (**有効期限**) が表示されてもファイルごとに変更。。 ヘッダーをクリックすると、フィールドを並べ替えることができます並べ替え順序を逆にするには列ヘッダーをもう一度をクリックします。</span><span class="sxs-lookup"><span data-stu-id="650d5-p110">The files are sorted from newest to oldest based on the date the file was quarantined. The **User** who last modified the file, the **Service** to which the file was posted, the **File Name**, **Location**, **File Size**, and the expiration date ( **Expires**) are also listed for each file. You can sort on a field by clicking a header; click a column header a second time to reverse the sort order.</span></span>
    
<span data-ttu-id="650d5-p111">すべての検疫済みファイルの一覧を表示またはフィルターを使用して特定のファイルを検索することができます。メッセージと同じように行うことができますのみ一括最大 100 個のアイテムを操作します。セキュリティでは現在、&amp;コンプライアンス センターでは、表示し、マルウェアが含まれていると識別されたので検疫にあるファイルを管理できます。。ヒントについては、この資料の[結果をフィルター処理し、検疫済みのメッセージとファイルを検索して](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)参照してください。</span><span class="sxs-lookup"><span data-stu-id="650d5-p111">You can view a list of all quarantined files, or you can search for specific files by filtering. Just like messages, you can only do bulk operations on up to 100 items. Currently, the Security &amp; Compliance Center lets you view and manage files that are in quarantine because they have been identified as containing malware. For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span> 
  
## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a><span data-ttu-id="650d5-152">結果をフィルター処理し、検疫済みのメッセージとファイルを検索するには</span><span class="sxs-lookup"><span data-stu-id="650d5-152">To filter results and find quarantined messages and files</span></span>
<span data-ttu-id="650d5-153"><a name="BKMK_AdvSearch"> </a></span><span class="sxs-lookup"><span data-stu-id="650d5-153"></span></span>

<span data-ttu-id="650d5-p112">設定によっては、検疫されたメッセージやファイルの多くがある可能性があります。特定のメッセージまたはファイル、または一連のメッセージまたはファイルを検索するには、さまざまなその他の情報に基づき、検疫済みのアイテムをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="650d5-p112">Depending on your settings, there may be a lot of quarantined messages and files. To find a specific message or file or set of messages or files, you can filter quarantined items based on a variety of additional information.</span></span>
  
1. <span data-ttu-id="650d5-156">[**検疫**] ページで、適切なメッセージやファイルを表示するフィルターの一番上の行が設定されているを確認します。</span><span class="sxs-lookup"><span data-stu-id="650d5-156">On the **Quarantine** page, ensure that the top row of filters is set to display messages or files as appropriate:</span></span> 
    
  - <span data-ttu-id="650d5-157">ファイルを検索するには、**マルウェア**によって検疫された**ファイル**を表示するフィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="650d5-157">To search for files, set the filters to show **files** quarantined due to **malware**.</span></span>
    
    <span data-ttu-id="650d5-158">検疫済みファイルは、ページは、ここに指示するに関係なく、独自の it を表示するだけでなく、検疫されたすべてのファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="650d5-158">For quarantined files, the page displays all quarantined files, not just your own, regardless of what you tell it to show.</span></span>
    
  - <span data-ttu-id="650d5-p113">検疫されたメッセージを検索するに**すべて**を表示するフィルターを設定または**のみ、** **メール**。最後のフィルター選択検疫済みのメッセージの種類を探しています。**迷惑メール**、メール フローまたは**トランスポート ルール**、**迷惑**メール、**フィッシング詐欺**メール、または**マルウェア**が含まれているメールに一致したメッセージとして識別された検疫済みのメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="650d5-p113">To search for quarantined messages, set filters to show **all** or **only my** **email**. For the last filter choose the type of quarantined message that you're looking for. You can search for quarantined messages that have been identified as **spam**, for messages that matched a mail flow or **transport rule**, **bulk** mail, **phishing** mail, or mail that contains **malware**.</span></span>
    
2. <span data-ttu-id="650d5-p114">[**による結果の並べ替え**、フィルターまたはフィルターのドロップダウン ・ リストから検索を使用するを選択します。オプションは、ファイルまたはメッセージを検索するかどうかに応じて異なります。この時点では、検索フィールドにワイルドカードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="650d5-p114">Under **Sort results by**, choose the filter or filters you want to use to search from the drop-down lists. The options vary based on whether you are searching for files or messages. Wildcards are not supported in search fields at this time.</span></span>
    
    <span data-ttu-id="650d5-p115">ファイルとメッセージの両方のメッセージを日付でフィルター処理することができます。 またはファイルを検疫に送られました。日付または時刻を含む日付の範囲を指定することができます。ファイルまたはメッセージを検疫から削除されますまたはフィルターの組み合わせを使用する有効期限の日付で検索結果を抽出することもできます。有効期限の日付で検索するには、**高度なフィルター**を選択します。[**期限切れ日時**を 24 時間以内 (**現在**)、48 時間以内 (**次の 2 日間**)、次の週 (**次の 7 日間**)、検疫から削除されるメッセージを選択することができます。 またはカスタム時間間隔を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="650d5-p115">For both files and messages, you can choose to filter by the date the message or file was sent to quarantine. You can specify the date or a date range, including the time. You can also filter your search results by the expiration date on which the file or message will be deleted from quarantine, or you can use a combination of filters. To search by expiration date, choose **Advanced filter**. Under **Expires**, you can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>
    
    <span data-ttu-id="650d5-170">メッセージは、次の追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="650d5-170">For messages, you have the following additional options:</span></span>
    
  - <span data-ttu-id="650d5-p116">**メッセージ ID**です。メッセージ ID がわかっている場合は、特定のメッセージを識別するのにときに使用します。</span><span class="sxs-lookup"><span data-stu-id="650d5-p116">**Message ID**. Use this to identify a specific message when you know the message ID.</span></span> 
    
    <span data-ttu-id="650d5-p117">などの場合は、特定のメッセージを送信、または、組織内のユーザーを対象としていますが、その先に決して到達しない、ことができますメッセージを検索、メッセージのトレースを使用して、([メッセージのトレースと結果の表示を実行する](https://go.microsoft.com/fwlink/?LinkId=799737)を参照してください)。検疫、おそらくメール フロー ルールに一致するか、または迷惑メールとして識別されたためにメッセージが送信されたことを発見した場合、簡単にわかりますこのメッセージ検疫でのメッセージ ID を指定することによってメッセージ ID 文字列全体を含めることを確認します。山かっこが挙げられます (\<\>)、たとえば。</span><span class="sxs-lookup"><span data-stu-id="650d5-p117">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Run a Message trace and View Results](https://go.microsoft.com/fwlink/?LinkId=799737)). If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its message ID. Be sure to include the full message ID string. This might include angle brackets (\<\>), for example:</span></span>
    
    <span data-ttu-id="650d5-177">\<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\></span><span class="sxs-lookup"><span data-stu-id="650d5-177">\<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\></span></span>
    
  - <span data-ttu-id="650d5-p118">**送信者の電子メール アドレス**です。1 人の送信者の電子メール アドレスでフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="650d5-p118">**Sender email address**. Choose to filter by a single sender email address.</span></span> 
    
  - <span data-ttu-id="650d5-p119">**受信者の電子メール アドレス**です。1 つの受信者の電子メール アドレスを使用してフィルターを適用する」を選択します。</span><span class="sxs-lookup"><span data-stu-id="650d5-p119">**Recipient email address**. Choose to filter by a single recipient email address.</span></span> 
    
  - <span data-ttu-id="650d5-p120">**件名**です。検索する電子メール アドレスの件名を入力します。ワイルドカード検索がサポートされていないため検索するために結果のメッセージが返されるメッセージの全体の件名を使用してください。検索では大文字小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="650d5-p120">**Subject**. Enter the subject of an email address you want to find. Since wildcard searching is not supported, you must use the entire subject of the message in order for search to return the message in the results. The search is not case-sensitive.</span></span> 
    
## <a name="view-details-about-quarantined-messages-and-files"></a><span data-ttu-id="650d5-186">検疫済みのメッセージとファイルの詳細を表示</span><span class="sxs-lookup"><span data-stu-id="650d5-186">View details about quarantined messages and files</span></span>
<span data-ttu-id="650d5-187"><a name="BKMK_ViewDetails"> </a></span><span class="sxs-lookup"><span data-stu-id="650d5-187"></span></span>

<span data-ttu-id="650d5-188">検疫リストに表示されている項目を選択すると、セキュリティの右側にある**詳細**ペインでそのプロパティの概要が表示されます&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="650d5-188">When you select an item displayed in the quarantine list, you'll see a summary of its properties in the **Details** pane on the right side of the Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="650d5-189">**検疫されたメッセージの表示の詳細**</span><span class="sxs-lookup"><span data-stu-id="650d5-189">**Details displayed for quarantined messages**</span></span>
  
- <span data-ttu-id="650d5-p121">**メッセージ ID**です。メッセージの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="650d5-p121">**Message ID**. The unique identifier for the message.</span></span> 
    
- <span data-ttu-id="650d5-p122">**センダーのアドレス**です。メッセージを送信したとします。</span><span class="sxs-lookup"><span data-stu-id="650d5-p122">**Sender Address**. Who sent the message.</span></span> 
    
- <span data-ttu-id="650d5-p123">**受信**します。日付と時刻、メッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="650d5-p123">**Received**. The date and time the message was received.</span></span> 
    
- <span data-ttu-id="650d5-p124">**件名**です。メッセージの件名行のテキストです。</span><span class="sxs-lookup"><span data-stu-id="650d5-p124">**Subject**. The text of the subject line of the message.</span></span> 
    
- <span data-ttu-id="650d5-p125">**型**です。**迷惑メール**、**一括**、**フィッシング**、メール フロー ルール (**トランスポート ルール**) に一致するか、**マルウェア**が含まれていると識別されたメッセージが確認されたかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="650d5-p125">**Type**. Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule ( **Transport rule**), or was identified as containing **Malware**.</span></span>
    
- <span data-ttu-id="650d5-p126">**有効期限が切れる**。日付と時刻、メッセージは検疫から自動的に削除されますとします。</span><span class="sxs-lookup"><span data-stu-id="650d5-p126">**Expires**. The date and time when the message will automatically be deleted from quarantine.</span></span> 
    
- <span data-ttu-id="650d5-p127">**リリースしました**。すべて電子メール アドレス (該当する場合)、メッセージがリリースされています。</span><span class="sxs-lookup"><span data-stu-id="650d5-p127">**Released to**. All email addresses (if any) to which the message has been released.</span></span> 
    
- <span data-ttu-id="650d5-p128">**リリースされていない**。すべて電子メール アドレス (該当する場合) に、メッセージがまだリリースされていません。</span><span class="sxs-lookup"><span data-stu-id="650d5-p128">**Not yet released to**. All email addresses (if any) to which the message has not yet been released.</span></span> 
    
 <span data-ttu-id="650d5-206">**検疫済みファイルの表示の詳細**</span><span class="sxs-lookup"><span data-stu-id="650d5-206">**Details displayed for quarantined files**</span></span>
  
- <span data-ttu-id="650d5-207">**ファイル名**検疫にあるファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="650d5-207">**File Name** The name of the file in quarantine.</span></span> 
    
- <span data-ttu-id="650d5-208">**サイトのパス**Office 365 で、ファイルの場所を定義する URL です。</span><span class="sxs-lookup"><span data-stu-id="650d5-208">**Site path** URL that defines the location of the file in Office 365.</span></span> 
    
- <span data-ttu-id="650d5-209">**の日付を検出/時間**日付と時刻、ファイルが検疫されました。</span><span class="sxs-lookup"><span data-stu-id="650d5-209">**Detected Date / Time** The date and time the file was quarantined.</span></span> 
    
- <span data-ttu-id="650d5-210">**有効期限が切れる**メッセージが検疫から削除されるときの日付。</span><span class="sxs-lookup"><span data-stu-id="650d5-210">**Expires** The date when the message will be deleted from quarantine.</span></span> 
    
- <span data-ttu-id="650d5-p129">**によって検出されました。** ファイルにマルウェアを検出するために使用するメソッドです。ATP (脅威の高度な保護) またはマイクロソフトのマルウェア対策エンジンのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="650d5-p129">**Detected By** The method used to detect the malware in the file. This can be either ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span> 
    
- <span data-ttu-id="650d5-213">**リリース**ファイルがリリースされているかどうかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="650d5-213">**Released** Describes whether or not the file has been released.</span></span> 
    
- <span data-ttu-id="650d5-214">**マルウェア名**ファミリであり、ファイル内で検出されたマルウェアの名前。</span><span class="sxs-lookup"><span data-stu-id="650d5-214">**Malware Name** Family and name of the malware detected in the file.</span></span> 
    
- <span data-ttu-id="650d5-215">**ドキュメント ID**ドキュメントの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="650d5-215">**Document ID** A unique identifier for the document.</span></span> 
    
- <span data-ttu-id="650d5-216">**ファイルのサイズ**KB のファイルのサイズ。</span><span class="sxs-lookup"><span data-stu-id="650d5-216">**File Size** The size of the file in KB.</span></span> 
    
- <span data-ttu-id="650d5-217">**組織**Office 365 で、組織の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="650d5-217">**Organization** Your organization's unique ID in Office 365.</span></span> 
    
- <span data-ttu-id="650d5-218">**によって変更されました。** 職場または学校の最後のユーザー アカウントは、ファイルを修正します。</span><span class="sxs-lookup"><span data-stu-id="650d5-218">**Modified By** The work or school account of the user who last modified the file.</span></span> 
    
- <span data-ttu-id="650d5-219">**ファイルのサイズ**KB のファイルのサイズ。</span><span class="sxs-lookup"><span data-stu-id="650d5-219">**File Size** The size of the file in KB.</span></span> 
    
- <span data-ttu-id="650d5-p130">**SHA256 ハッシュ**ファイルのハッシュです。したか、環境内のファイルがある別の方法を調査するその他の評判のストアを検索するには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="650d5-p130">**SHA256 Hash** The hash of the file. You can use this to look up other reputation stores you may have or investigate where else the file might be in your environment.</span></span> 
    
## <a name="managing-messages-and-files-in-quarantine"></a><span data-ttu-id="650d5-222">検査内のメッセージやファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="650d5-222">Managing messages and files in quarantine</span></span>
<span data-ttu-id="650d5-223"><a name="BKMK_ManageQuarantinedItem"> </a></span><span class="sxs-lookup"><span data-stu-id="650d5-223"></span></span>

<span data-ttu-id="650d5-224">メッセージまたはメッセージのグループを選択した後は、検査中のメッセージを管理するためのいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="650d5-224">After you select a message or group of messages you have several options for managing messages in quarantine.</span></span>
  
- <span data-ttu-id="650d5-p131">何もしません。何もしないを選択した場合、メッセージは削除されます Office 365 によって自動的に有効期限になります。既定では、迷惑メール、一括、マルウェア、フィッシング、およびメール フロー ルールに一致するために検疫されたメッセージは検疫で 30 日間保存します。Office 365 は、検疫からのメッセージを削除と、することはできませんを元に戻します。必要な場合は、迷惑メール対策ポリシーに、 **(日単位) を保持するの迷惑メール**設定を構成することによって、検疫されたメッセージの保存期間を変更できます。詳細については、この資料で[検疫保存期間を設定する](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="650d5-p131">Do nothing. If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration. By default, spam, bulk, malware, phishing, and messages quarantined because they matched a mail flow rule are kept in quarantine for 30 days. When Office 365 deletes a message from quarantine, you can't get it back. If you like, you can change the retention period for quarantined messages by configuring the **Retain spam for (days)** setting in your anti-spam policies. For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span> 
    
- <span data-ttu-id="650d5-p132">**メッセージ ヘッダーの表示**メッセージ ヘッダーのテキストを表示するには、このリンクを選択します。深さのヘッダーを分析するには、メッセージのヘッダー テキストをクリップボードにコピーし、リモート接続アナライザーに移動するのには**Microsoft のメッセージ ヘッダーの分析**を選択 (右クリックし、Office のままにしたくない場合は**新しいタブで開く**を選択365 このタスクを完了する)。メッセージ ヘッダーの分析] で、ページ上にメッセージのヘッダーをペーストし、**ヘッダーの分析**を選択します。</span><span class="sxs-lookup"><span data-stu-id="650d5-p132">**View message header** Choose this link to see the message header text. To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**.</span></span>
    
- <span data-ttu-id="650d5-p133">**メッセージをプレビュー表示**生の「」を参照、またはメッセージ本文のテキストの HTML バージョンにできます。HTML ビューで、リンクが無効になります。</span><span class="sxs-lookup"><span data-stu-id="650d5-p133">**Preview message** Lets you see raw or HTML versions of the message body text. In the HTML view, links are disabled.</span></span> 
    
- <span data-ttu-id="650d5-p134">**メッセージをダウンロード**するか、**ファイルをダウンロード**します。ローカル デバイスにメッセージやファイルのコピーをダウンロードするには、このオプションを選択します。許可がこれを行う前に、検疫からアイテムをダウンロードすることに伴うリスクを理解することを確認する必要があります。メッセージは、指定したフォルダーに .eml 形式で保存されます。検疫済みのファイルは、元の形式で保存されます。</span><span class="sxs-lookup"><span data-stu-id="650d5-p134">**Download message** or **Download file**. Choose this option to download a copy of the message or file to your local device. You'll need to confirm that you understand the risks associated with downloading items from quarantine before you'll be allowed to do so. Messages are saved in .eml format to a folder you specify. Quarantined files are saved in their original format.</span></span>
    
- <span data-ttu-id="650d5-p135">**削除**する場合は、Office 365 によって設定された有効期限日付を待っているのではなく、検疫済みの項目 (または項目のセット) をすぐに削除できます。メッセージまたはファイルの検疫] ボックスの一覧で、削除するには、アイテムを選択してし、[**削除**] をクリックします。複数の項目を一度に削除するには、検疫] ボックスの一覧で、項目の左側にチェック ボックスをオンし、**一括操作**、表示されるページ上の**選択したメッセージを削除**するか、**選択したファイルの削除**を選択します。</span><span class="sxs-lookup"><span data-stu-id="650d5-p135">**Delete** If you want, you can immediately delete a quarantined item (or set of items) instead of waiting for the expiration date set by Office 365. To delete a message or file, in the quarantine list, select the item and then choose **Delete**. To delete multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Delete selected messages** or **Delete selected files**.</span></span>
    
- <span data-ttu-id="650d5-243">**リリース**検疫済みの項目 (または項目のセット) をリリースし、アイテムを誤って隔離された (偽陽性) としてマイクロソフトに報告します。</span><span class="sxs-lookup"><span data-stu-id="650d5-243">**Release** Release a quarantined item (or set of items) and report the items as falsely quarantined (false positives) to Microsoft.</span></span> 
    
    <span data-ttu-id="650d5-p136">解放し、1 つのメッセージまたはファイルの検疫] ボックスの一覧で、報告の項目を選択、**ファイルを解放**または**解放メッセージ**を選択します。次のページでは、**分析のためのマイクロソフトにレポート メッセージ**または**分析のためのマイクロソフトにレポート ファイル**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="650d5-p136">To release and report a single message or file, in the quarantine list, select the item, choose **Release file** or **Release message**. On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span> 
    
    <span data-ttu-id="650d5-p137">解放するには複数のアイテムを一度に検疫] ボックスの一覧で、項目の左側のチェック ボックスを選択し、表示される**一括操作**ページで、**ファイルを解放**または**メッセージを解放**します。次のページでは、**分析のためのマイクロソフトにレポート メッセージ**または**分析のためのマイクロソフトにレポート ファイル**が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="650d5-p137">To release multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Release files** or **Release messages**. On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span> 
    
<span data-ttu-id="650d5-248">メッセージを解放している場合は、次の注意してください。</span><span class="sxs-lookup"><span data-stu-id="650d5-248">When you're releasing messages, be aware of the following:</span></span>
  
- <span data-ttu-id="650d5-p138">一度に複数のメッセージの一括リリースを実行すると、メッセージが最初に特定されたすべての受信者に解放されます。特定の受信者のみにメッセージを解放する場合は、一度に 1 つのメッセージを解放し、受信者を個別に識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="650d5-p138">When you perform a bulk release of multiple messages at once, the messages are released to all originally identified recipients. If you only want to release messages only to specific recipients, you need to release the messages one at a time and identify the recipients individually.</span></span>
    
- <span data-ttu-id="650d5-251">同じ受信者にメッセージを複数回解放できません。</span><span class="sxs-lookup"><span data-stu-id="650d5-251">A message cannot be released more than once to the same recipient.</span></span>
    
- <span data-ttu-id="650d5-252">複数の受信者にメッセージを解放する場合、受信者のみがメッセージを以前受信していない潜在的な受信者の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="650d5-252">When you're releasing a message to more than one recipient, only recipients who have not previously received the message will appear in the list of potential recipients.</span></span>
    
- <span data-ttu-id="650d5-p139">メッセージまたはメッセージを解放するには迷惑メール、一括、フィッシング、マルウェアが含まれているまたは検疫された場合、誤を報告するを選択すると、マイクロソフトのスパム分析チームにもメッセージが報告されます。チームを評価し、メッセージの分析し、分析の結果によってを介してメッセージを許可するサービス全体のスパム コンテンツ フィルターのルールを調整することがあります。</span><span class="sxs-lookup"><span data-stu-id="650d5-p139">When you choose to report false positives, if the message or messages you release were quarantined as spam, bulk, phishing, or as containing malware, the message will also be reported to the Microsoft Spam Analysis Team. The team will evaluate and analyze the message, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
    
## <a name="setting-the-quarantine-retention-period"></a><span data-ttu-id="650d5-255">検疫保存期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="650d5-255">Setting the quarantine retention period</span></span>
<span data-ttu-id="650d5-256"><a name="BKMK_ModQuarantineTime"> </a></span><span class="sxs-lookup"><span data-stu-id="650d5-256"></span></span>

<span data-ttu-id="650d5-p140">メッセージをどのくらいの時間を構成することができ、期限が切れる前に、検疫のファイルに残ります。既定では、検疫済みのアイテムは 30 日間保存されます。ポリシーごとに作成するには、この設定を構成するとします。この資料で説明するよう、既定のポリシーの値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="650d5-p140">You can configure how long messages and files will remain in quarantine before they expire. By default, quarantined items are kept for 30 days. You configure this setting for each policy that you create. You can also modify the value for the default policy as described in this article.</span></span> 
  
### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a><span data-ttu-id="650d5-261">セキュリティとコンプライアンス センターで迷惑メール フィルターの既定のポリシーの検疫保存期間を変更するのには</span><span class="sxs-lookup"><span data-stu-id="650d5-261">To modify the quarantine retention period for the default spam filter policy in the Security and Compliance Center</span></span>

1. <span data-ttu-id="650d5-262">グローバル管理者権限を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Office 365[のセキュリティとコンプライアンスの中央に移動](go-to-the-securitycompliance-center.md)してサインインします。</span><span class="sxs-lookup"><span data-stu-id="650d5-262">Using a work or school account that has global administrator privileges in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="650d5-263">、左側の**脅威の管理**を展開し、**ポリシー**を選択し、**スパム対策**します。</span><span class="sxs-lookup"><span data-stu-id="650d5-263">On the left, expand **Threat Management**, choose **Policy**, and then choose **Anti-spam**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="650d5-264">セキュリティで**スパム対策**のページに直接移動するのには&amp;コンプライアンス センターでは、この URL を使用して: >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span><span class="sxs-lookup"><span data-stu-id="650d5-264">To go directly to the **anti-spam** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span></span>
  
3. <span data-ttu-id="650d5-265">[**カスタム設定**] タブを表示する**ユーザー設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="650d5-265">Choose **Custom** to display the **Custom settings** tab.</span></span> 
    
4. <span data-ttu-id="650d5-266">**既定の迷惑メール フィルター ポリシー (常に ON)** の行を展開します。</span><span class="sxs-lookup"><span data-stu-id="650d5-266">Expand the **Default spam filter policy (always ON)** row.</span></span> 
    
5. <span data-ttu-id="650d5-p141">**ポリシーを編集**を選択します。迷惑メール フィルターの既定のポリシーの設定は、新しいページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="650d5-p141">Choose **Edit policy**. The settings for the default spam filter policy appear in a new page.</span></span>
    
6. <span data-ttu-id="650d5-269">展開**迷惑メールの操作を一括して**。</span><span class="sxs-lookup"><span data-stu-id="650d5-269">Expand **Spam and bulk actions**.</span></span>
    
7. <span data-ttu-id="650d5-p142">**検疫**、下の **(日) の迷惑メールを保持する**テキスト ボックスで、検査中のメッセージやファイルを保持するのには Office 365 を時間を入力します。既定では 30 日間です。最大値です。</span><span class="sxs-lookup"><span data-stu-id="650d5-p142">Under **Quarantine**, in the **Retain spam for (days)** text box, enter the amount of time you want Office 365 to retain messages and files in quarantine. The default is 30 days. This is also the maximum.</span></span> 
    
8. <span data-ttu-id="650d5-273">[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="650d5-273">Choose **Save**.</span></span>
    

