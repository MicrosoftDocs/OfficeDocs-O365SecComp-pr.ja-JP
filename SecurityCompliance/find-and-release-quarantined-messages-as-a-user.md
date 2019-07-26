---
title: Office 365 のユーザーとして検疫済みメッセージを検出して解放する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/19/2018
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: Office 365 のユーザーとして、次の 2 つのうちいずれかの方法で独自のスパム検疫メッセージを管理することができます。1 つは送信されたスパム通知に直接応答する方法 (管理者がこの機能を設定している場合) で、もう 1 つはセキュリティ &amp; コンプライアンス センターでスパム検疫機能を使用する方法です。
ms.openlocfilehash: 20758876dbfe51f47d66c3c1eef4dcb3cee49768
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854581"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="56704-103">Office 365 のユーザーとして検疫済みメッセージを検出して解放する</span><span class="sxs-lookup"><span data-stu-id="56704-103">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="56704-104">Office 365 のユーザーとして、自分にではなく、検疫に送られたメッセージを次の 2 つのうちいずれかの方法で管理できます。1 つは [送信されたスパム通知に直接応答する方法](use-spam-notifications-to-release-and-report-quarantined-messages.md) (管理者がこの機能を設定している場合) で、もう 1 つはセキュリティ &amp; コンプライアンス センターでスパム検疫機能を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="56704-104">End users can manage messages that were sent to quarantine instead of sent to them in one of two ways: by responding to spam notifications sent to the end user directly (if the administrator has set this up), or by using the Security &amp; Compliance Center.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="56704-105">管理者の場合は、組織内の他のユーザーのために [検疫済みメッセージを管理する](manage-quarantined-messages-and-files.md) ことができます。</span><span class="sxs-lookup"><span data-stu-id="56704-105">If you're an admin, you can [manage quarantined messages](manage-quarantined-messages-and-files.md) for other people in your organization.</span></span> 
  
## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a><span data-ttu-id="56704-106">自分にではなく、検疫に送信されたメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="56704-106">View messages that were sent to quarantine instead of to you</span></span>

1. <span data-ttu-id="56704-107">Office 365 にサインインし、職場または学校のアカウントを使用して [セキュリティ/コンプライアンス センター](go-to-the-securitycompliance-center.md)に進みます。</span><span class="sxs-lookup"><span data-stu-id="56704-107">Sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md) using your work or school account.</span></span> 
    
2. <span data-ttu-id="56704-108">左側の **[脅威の管理]** を展開し、**[レビュー]** を選択して、**[検疫]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="56704-108">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="56704-109">セキュリティ &amp; コンプライアンス センターの **[検疫]** ページに直接移動するには、次の URL を使用します。[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="56704-109">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
<span data-ttu-id="56704-110">既定では、セキュリティ &amp; コンプライアンスセンターには、スパムとして検疫されたすべてのメール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="56704-110">By default, the Security &amp; Compliance Center displays all email messages that have been quarantined as spam.</span></span> <span data-ttu-id="56704-111">メッセージは、受信の **日付** に基づいて、最新のものから順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="56704-111">The messages are sorted from newest to oldest based on the **Date** the message was received.</span></span> <span data-ttu-id="56704-112">**[送信者]**、**[件名]**、および有効期限 (**[有効期限]**) がメッセージごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="56704-112">**Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message.</span></span> <span data-ttu-id="56704-113">フィールドを並べ替えるには、列のヘッダーをクリックします。ヘッダーをもう一度クリックすると、逆順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="56704-113">You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span> 
  
<span data-ttu-id="56704-114">検疫済みメッセージの一覧を表示することもできます。また、フィルターを使用して特定のメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="56704-114">You can view a list of all quarantined messages, or you can search for specific messages by specifying filter criteria (filtering can also help reduce your result set if you have more than 500 messages).</span></span> <span data-ttu-id="56704-115">一括操作は 100 件以下のアイテムにのみ実行できます。100 件を越える場合は、フィルターを使って結果セットを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="56704-115">You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that.</span></span> <span data-ttu-id="56704-116">ドロップダウン リストからオプションを選択すると、1 つの検疫に対してメッセージをすばやくフィルターにかけることができます。</span><span class="sxs-lookup"><span data-stu-id="56704-116">You can quickly filter messages for a single quarantine reason by choosing an option from the drop-down list.</span></span> <span data-ttu-id="56704-117">オプションは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56704-117">Options include:</span></span>
  
- <span data-ttu-id="56704-118">スパムと識別されたメール。</span><span class="sxs-lookup"><span data-stu-id="56704-118">Mail identified as spam.</span></span> <span data-ttu-id="56704-119">検疫済みメッセージは既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="56704-119">These quarantined messages are shown by default.</span></span>
    
- <span data-ttu-id="56704-120">バルク メールと識別されたメール。</span><span class="sxs-lookup"><span data-stu-id="56704-120">Mail identified as bulk mail.</span></span>
    
<span data-ttu-id="56704-121">特定の検疫済みメッセージをダブルクリックし、詳細を表示して、処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="56704-121">After you find a specific quarantined message, click the message to view details about it, and take actions.</span></span> <span data-ttu-id="56704-122">メッセージをメールボックスに解放、メッセージをプレビュー、メッセージをダウンロード、またはメッセージを検疫から削除することができます。</span><span class="sxs-lookup"><span data-stu-id="56704-122">You can release the message to your mailbox, preview the message, download the message, or delete the message from quarantine immediately.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56704-123">他のユーザーに送信された検疫済みメッセージを処理するには、Office 365 の管理者アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="56704-123">You must have admin permissions in Office 365 to work with quarantined messages that were sent to other users.</span></span> 
  
## <a name="to-filter-and-find-quarantined-messages"></a><span data-ttu-id="56704-124">検疫済みメッセージのフィルターと検出</span><span class="sxs-lookup"><span data-stu-id="56704-124">To filter and find quarantined messages</span></span>

<span data-ttu-id="56704-125">検疫されたアイテムが多数ある場合は、フィルター処理をして、管理できる数まで減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="56704-125">If you have a lot of quarantined items, you can reduce the number to a manageable set by filtering them.</span></span>
  
1. <span data-ttu-id="56704-126">**[検疫]** ページで、**スパム** または **バルク** 検閲メッセージを表示するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="56704-126">On the **Quarantine** page, choose whether you want to view **spam** or **bulk** quarantined messages.</span></span> 
    
2. <span data-ttu-id="56704-127">**[結果の並べ替え]** で、該当するフィルターを設定して条件の任意の組み合わせを選びます (ここではワイルドカードを使用できません)。</span><span class="sxs-lookup"><span data-stu-id="56704-127">Under **Sort results by**, choose any combination of conditions by setting the appropriate filter or filters (you can't use wildcards at this time).</span></span> <span data-ttu-id="56704-128">次のような、複数の条件を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="56704-128">There are several conditions you can choose, including the following:</span></span>
    
  - <span data-ttu-id="56704-129">**メッセージ ID** メッセージ ID がわかっている特定のメッセージを選択するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="56704-129">**Message ID** Use this to select a specific message when you know the message ID.</span></span> 
    
    <span data-ttu-id="56704-130">たとえば、目的のメッセージの送信者または宛先が組織内のユーザーで、宛先に届かない場合、メッセージ追跡を使用してメッセージを検索できます (「[メッセージ追跡を実行し、結果を表示する](https://go.microsoft.com/fwlink/?LinkId=799737)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="56704-130">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reaches its destination, you can search for the message using the message trace feature.</span></span> <span data-ttu-id="56704-131">メッセージがルールと一致、またはスパムとして識別されたために検疫に送信されたことが判明した場合は、メッセージ ID を指定して検疫内でそのメッセージを簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="56704-131">If you discover that the message was sent to the quarantine, perhaps because it matched a rule or was identified as spam, you can then easily find this message in the quarantine by specifying its Message ID.</span></span> <span data-ttu-id="56704-132">完全なメッセージ ID 文字列を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="56704-132">Be sure to include the full Message ID string.</span></span> <span data-ttu-id="56704-133">メッセージ ID には、次のように、山かっこ (\<\>) が含まれる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="56704-133">This might include angle brackets (\<\>).</span></span>
    
    <span data-ttu-id="56704-134">\<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\></span><span class="sxs-lookup"><span data-stu-id="56704-134">\<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\></span></span>
    
  - <span data-ttu-id="56704-135">**送信者のメール アドレス** 1 つの送信者のメール アドレスによってフィルター処理する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="56704-135">**Sender email address** Choose to filter by a single sender email address.</span></span> 
    
  - <span data-ttu-id="56704-136">**受信者のメール アドレス** 1 つの受信者のメール アドレスによってフィルター処理する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="56704-136">**Recipient email address** Choose to filter by a single recipient email address.</span></span> 
    
  - <span data-ttu-id="56704-137">**件名** 検索するメール アドレスの件名を入力します。</span><span class="sxs-lookup"><span data-stu-id="56704-137">**Subject** Enter the subject of an email address you want to find.</span></span> 
    
  - <span data-ttu-id="56704-138">**日付範囲** メッセージが検疫に送信された日付別にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="56704-138">**Date range** You can choose to filter by the date the message was sent to quarantine.</span></span> <span data-ttu-id="56704-139">日付または日付範囲を指定することができます (時間も指定できます)。</span><span class="sxs-lookup"><span data-stu-id="56704-139">You can specify the date or a date range, including the time.</span></span> 
    
  - <span data-ttu-id="56704-140">**有効期限** 有効期限によってフィルター処理する場合は、**[詳細フィルター]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="56704-140">**Expiration date** To filter by expiration date, choose **Advanced filter**.</span></span> <span data-ttu-id="56704-141">24 時間以内 (**今日**)、48 時間以内 (**2 日以内**)、1 週間以内 (**7 日以内**) に検疫から削除されるメッセージを選択することができます。また、カスタムの期間を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="56704-141">Expires You can select that the message will be deleted from the quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval during which the message will be deleted from the quarantine.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="56704-142">既定では、スパムやバルクメッセージは、検疫に 30 日間保存されます。</span><span class="sxs-lookup"><span data-stu-id="56704-142">By default, spam and bulk messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="56704-143">ただし、この期間は設定可能なため、管理者が異なる検疫期間を設定している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="56704-143">However, this time period is configurable and your admin might have set a different quarantine retention period.</span></span> <span data-ttu-id="56704-144">Office 365 で検疫からメッセージを削除すると、元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="56704-144">When Office 365 deletes a message from quarantine, you can't get it back.</span></span> 
  
## <a name="view-details-for-a-specific-message"></a><span data-ttu-id="56704-145">特定のメッセージの詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="56704-145">View the details for a specific event</span></span>

<span data-ttu-id="56704-146">メッセージを選択すると、ページの右側にあるウィンドウにメッセージのプロパティの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="56704-146">After you select a message, you'll see a summary of the message properties in a pane on the right side of the page.</span></span>
  
- <span data-ttu-id="56704-147">**メッセージ ID:** メッセージの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="56704-147">**Message ID:** The unique identifier for the message.</span></span> 
    
- <span data-ttu-id="56704-148">**送信者のアドレス:** メッセージの送信者。</span><span class="sxs-lookup"><span data-stu-id="56704-148">**Sender Address:** Who sent the message.</span></span> 
    
- <span data-ttu-id="56704-149">**受信日:** メッセージを受信した日付。</span><span class="sxs-lookup"><span data-stu-id="56704-149">**Received** The date on which the message was received by the quarantine.</span></span> 
    
- <span data-ttu-id="56704-150">**件名:** メッセージの件名欄のテキスト。</span><span class="sxs-lookup"><span data-stu-id="56704-150">**Subject:** The text of the Subject line in the message.</span></span> 
    
- <span data-ttu-id="56704-151">**検疫理由:** メッセージが **スパム** または **バルク** として識別されたかを表示します。</span><span class="sxs-lookup"><span data-stu-id="56704-151">**Quarantine reason:** Shows if a message has been identified as **Spam** or **Bulk**.</span></span>
    
- <span data-ttu-id="56704-152">**有効期限:** 検疫からメッセージが削除される日付。</span><span class="sxs-lookup"><span data-stu-id="56704-152">**Expires** The date when the message will be deleted from the quarantine.</span></span> 
    
- <span data-ttu-id="56704-153">**解放されました:** メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="56704-153">**Released to:** All email addresses (if any) to which the message has been released.</span></span> 
    
- <span data-ttu-id="56704-154">**まだ解放されていません:** メッセージが解放されていないすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="56704-154">**Not yet released to:** All email addresses (if any) to which the message has not been released.</span></span> <span data-ttu-id="56704-155">メッセージをメールボックスに解放する場合、**[解放する]** を選択できます (メッセージの解放の詳細については、次のセクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="56704-155">You can choose **Release** if you want to release the message to your mailbox (more about releasing messages in the next section).</span></span> 
    
<span data-ttu-id="56704-156">メッセージについてさらに詳しい情報を確認するには、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="56704-156">You can get even more details about the message by choosing one of the following options:</span></span>
  
- <span data-ttu-id="56704-157">**メッセージ ヘッダーを表示** メッセージ ヘッダー テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="56704-157">**View message header** Choose this to see the message header text.</span></span> <span data-ttu-id="56704-158">ヘッダーを詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、 **[Microsoft メッセージ ヘッダー アナライザー]** を選択して、[リモート接続アナライザー] に移動します (このタスクを完了するまで Office 365 を閉じたくない場合は、右クリックして [新しいタブで開く] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="56704-158">To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose Open in a new tab if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="56704-159">メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、[ヘッダーの分析] を選択します。</span><span class="sxs-lookup"><span data-stu-id="56704-159">Paste the message header onto the page in the Message Header Analyzer section, and choose Analyze headers.</span></span> 
    
- <span data-ttu-id="56704-160">**メッセージのプレビュー** メッセージ本文の raw バージョンまたは HTML バージョンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="56704-160">**Preview message** Lets you see raw or HTML versions of the message body text.</span></span> <span data-ttu-id="56704-161">HTML バージョンを表示する場合、リンクは無効です。</span><span class="sxs-lookup"><span data-stu-id="56704-161">In the HTML view, links are disabled.</span></span> 
    
## <a name="manage-your-quarantined-messages"></a><span data-ttu-id="56704-162">検疫されたメッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="56704-162">Manage your quarantined messages</span></span>

<span data-ttu-id="56704-163">メッセージまたはメッセージのグループを選択したら、検疫内のメッセージを管理するためのいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="56704-163">After you select a message or group of messages, you have several options for managing messages in quarantine.</span></span>
  
- <span data-ttu-id="56704-164">何もしない。</span><span class="sxs-lookup"><span data-stu-id="56704-164">Do nothing.</span></span> <span data-ttu-id="56704-165">何もしないを選択すると、メッセージは有効期限日に Office 365 によって自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="56704-165">If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration.</span></span> <span data-ttu-id="56704-166">Office 365 で検疫からメッセージを削除すると、元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="56704-166">Remember, when Office 365 deletes a message from quarantine, you can't get it back.</span></span>
    
- <span data-ttu-id="56704-167">**リリースメッセージ** メッセージがメールボックスに送信されるように、検疫されたメッセージ (または一連のメッセージ) を解放します。</span><span class="sxs-lookup"><span data-stu-id="56704-167">**Release message** Release a quarantined message (or set of messages) so that the message is sent to your mailbox.</span></span> <span data-ttu-id="56704-168">メッセージを解放する場合、メッセージを分析のために Microsoft に報告するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="56704-168">When you release a message, you have the option to report the message to Microsoft for analysis.</span></span> 
    
    <span data-ttu-id="56704-169">メッセージを報告するオプションを選択すると、誤検出としてもメッセージを報告する、というメッセージが表示され、メッセージは Microsoft スパム分析チームに報告されます。</span><span class="sxs-lookup"><span data-stu-id="56704-169">When you choose to report a message, also called reporting a message as a false positive, the message is reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="56704-170">チームは誤検出メッセージを評価および分析し、分析結果に応じて、そのメッセージを許可するようにサービス全体のスパム コンテンツ フィルター ルールを調整する場合があります。</span><span class="sxs-lookup"><span data-stu-id="56704-170">The team evaluates and analyzes false positive messages, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow these messages through.</span></span>
    
- <span data-ttu-id="56704-171">**メッセージをダウンロードする** .eml ファイルとしてメッセージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="56704-171">**Download message** Lets you download the message as a .eml file.</span></span> <span data-ttu-id="56704-172">メッセージをダウンロードした後は、メール クライアントを使用して .eml ファイルを確認してから、メッセージを解放します。</span><span class="sxs-lookup"><span data-stu-id="56704-172">Once you download a message, you can review the .eml file using your email client prior to releasing the message.</span></span> 
    
- <span data-ttu-id="56704-173">**検閲から削除する**メッセージは検疫から削除され、メールボックスには解放されません。</span><span class="sxs-lookup"><span data-stu-id="56704-173">**Remove from quarantine** Deletes the message immediately from quarantine without releasing the message to your mailbox.</span></span> 
    

