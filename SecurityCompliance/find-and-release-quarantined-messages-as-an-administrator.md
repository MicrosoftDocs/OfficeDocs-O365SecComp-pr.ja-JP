---
title: 管理者として検疫済みメッセージを検索して解放する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: このトピックでは、Exchange Online and Exchange Online Protection (EOP) の管理者が、Exchange 管理センター (EAC) の検疫済みメッセージに入っているメッセージの検索、解放、報告を行う方法について説明します。
ms.openlocfilehash: 9bf821885ad8d4ec89aa3c349a6c072f78f6c57a
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699352"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a><span data-ttu-id="c13ef-103">管理者として検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="c13ef-103">Find and release quarantined messages as an administrator</span></span>

<span data-ttu-id="c13ef-104">このトピックでは、Exchange Online and Exchange Online Protection (EOP) の管理者が、Exchange 管理センター (EAC) の検疫済みメッセージに入っているメッセージの検索、解放、報告を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-104">This topic describes how Exchange Online and Exchange Online Protection (EOP) admins can find, release, and report on quarantined messages in the Exchange admin center (EAC).</span></span> <span data-ttu-id="c13ef-105">Office 365 は、スパムとして識別されたか、メールフロールール (トランスポートルールとも呼ばれる) と一致したために、メッセージを検疫するように指示します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-105">Office 365 directs messages to quarantine either because they were identified as spam or they matched a mail flow rule (also known as a transport rule).</span></span> 
  
<span data-ttu-id="c13ef-p102">Use the Security &amp; Compliance Center instead of the EAC to complete any of these tasks as well as view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span><span class="sxs-lookup"><span data-stu-id="c13ef-p102">Use the Security &amp; Compliance Center instead of the EAC to complete any of these tasks as well as view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span></span>
  
<span data-ttu-id="c13ef-p103">検疫済みメッセージは EAC の **[検疫]** ページに一覧表示されます。既定では、メッセージは **[受信]** フィールドの降順で並べ替えられます。 **[送信者]**、 **[件名]**、および **[有効期限]** の値もメッセージごとに表示されます。フィールドは、ヘッダーをクリックして並べ替えることができます。見出しをもう一度クリックすると、逆の順序で並べ替えられます。 **[検疫]** ページには最大で 500 個のメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p103">Quarantined messages are listed on the **quarantine** page in EAC. By default, messages are sorted from newest to oldest on the **RECEIVED** field. **SENDER**, **SUBJECT**, and **EXPIRES** values are also listed for each message. You can sort on any of these fields by clicking their headers. If you click a column header a second time, the sort order reverses. The **quarantine** page displays a maximum of 500 messages.</span></span> 
  
<span data-ttu-id="c13ef-p104">すべての検疫メッセージの一覧を表示するか、フィルタ条件を指定して特定のメッセージを検索することができます (500 以上のメッセージがある場合はフィルタリングによって結果セットを削減することが可能)。検疫されたメッセージを検索して特定したら、メッセージに関する詳細を表示できます。次のようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p104">You can view a list of all quarantined messages, or you can search for specific messages by specifying filter criteria (filtering can also help reduce your result set if you have more than 500 messages). After searching for and locating a specific quarantined message, you can view details about the message. You can also:</span></span>
  
- <span data-ttu-id="c13ef-p105">1 人以上の受信者にメッセージを解放し、オプションとして、メッセージを偽陽性のメッセージ (迷惑メールではないメール) として Microsoft スパム分析チームに報告します。Microsoft スパム分析チームは、メッセージを評価し分析します。分析結果によっては、このメッセージが許可されるようにサービス全体のスパム コンテンツ フィルター ルールが調整されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p105">Release the message to one or more recipients, and optionally report it as a false positive (not junk) message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
    
- <span data-ttu-id="c13ef-119">メッセージを解放し、その送信者からの将来のメッセージをすべて許可します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-119">Release the message and allow all future messages from that sender.</span></span>
    
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c13ef-120">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c13ef-120">What do you need to know before you begin?</span></span>
<span data-ttu-id="c13ef-121"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="c13ef-121"></span></span>

- <span data-ttu-id="c13ef-122">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c13ef-122">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="c13ef-123">必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「検疫」エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13ef-123">To see what permissions you need, see the "Quarantine" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
    
- <span data-ttu-id="c13ef-p107">**[検疫]** ページでは、一度に複数のメッセージを解放または報告することができません。代わりに、このタスクを実行するリモート Windows PowerShell スクリプトを作成することができます。メッセージを検索する場合は [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) コマンドレットを使用し、それらを解放する場合は [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p107">You can release or report multiple messages at once on the **quarantine** page. Alternatively you can create a remote Windows PowerShell script to accomplish this task. Use the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for messages, and the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet to release them.</span></span> 
    
- <span data-ttu-id="c13ef-127">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13ef-127">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
    
> [!TIP]
> <span data-ttu-id="c13ef-128">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="c13ef-128">Having problems?</span></span> <span data-ttu-id="c13ef-129">Exchange のフォーラムで質問してください。</span><span class="sxs-lookup"><span data-stu-id="c13ef-129">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="c13ef-130">> 一般法人向け Office 365 の管理者の場合は、サポートに問い合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-130">Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a><span data-ttu-id="c13ef-131">高度な検索を使用して検疫済みメッセージをフィルター処理して特定する</span><span class="sxs-lookup"><span data-stu-id="c13ef-131">Use advanced search to filter and locate quarantined messages</span></span>
<span data-ttu-id="c13ef-132"><a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a></span><span class="sxs-lookup"><span data-stu-id="c13ef-132"></span></span>

<span data-ttu-id="c13ef-p109">Exchange 管理センター (EAC) では、高度な検索を使用してさまざまな条件に基づいて検疫済みアイテムをフィルター処理することができます。これらの条件は、個別に使用することも、組み合わせて使用することもできます。検索によって、すべてのフィルター条件を満たすメッセージのリストが返されます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p109">In the Exchange admin center (EAC), you can filter quarantined items based on several different conditions using advanced search. You can use these conditions separately or in combination with one another. The search will provide a list of messages that meet all your filter criteria.</span></span>
  
1. <span data-ttu-id="c13ef-136">EAC で、 **[保護]** \> **[検疫]** と移動し、 **[高度な検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-136">In EAC, navigate to **Protection** \> **quarantine**, and then click **Advanced search**.</span></span>
    
2. <span data-ttu-id="c13ef-p110">**[高度な検索]** ウィンドウで、次の条件の任意の組み合わせを選択します。各条件を有効にするには、関連するチェック ボックスをオンにします。ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p110">In the **Advanced search** window, select any combination of the following conditions. Select the associated check box to enable each condition. Wildcards aren't supported.</span></span> 
    
1. <span data-ttu-id="c13ef-p111">**[メッセージ ID]** このパラメーターは、特定のメッセージにターゲットを絞った検索を実行するために使用できます。たとえば、組織のユーザーが特定のメッセージを送信したか、組織のユーザーに向けて特定のメッセージを送信したものの、宛先に届かない場合は、メッセージの追跡機能を使用してメッセージを検索できます。詳細については、「 [メッセージの追跡を実行し、結果を表示する](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx)」をご覧ください。メッセージがルールと一致したりスパムとして識別されたために検疫に送信されたことが判明した場合は、メッセージ ID を指定して検疫内でそのメッセージを簡単に見つけることができます。完全なメッセージ ID 文字列を含める必要があります。メッセージ ID には、山かっこ (\<\>) が含まれる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p111">**Message ID** You can use this parameter to perform a targeted search for a specific message. For example, if a specific message is sent by, or intended for, a user in your organization, but it never reaches its destination, you can search for the message using the message trace feature. For details, see [Run a Message Trace and View Results](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx). If you discover that the message was sent to the quarantine, perhaps because it matched a rule or was identified as spam, you can then easily find this message in the quarantine by specifying its Message ID. Be sure to include the full Message ID string. This might include angle brackets (\<\>).</span></span> 
    
2. <span data-ttu-id="c13ef-146">**[送信者のメール アドレス]** メッセージを送信した人物のメール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-146">**Sender email address** Specify the email address of the person who sent the message.</span></span> 
    
3. <span data-ttu-id="c13ef-147">**[受信者のメール アドレス]** メッセージの意図した受信者の電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-147">**Recipient email address** Specify the email address of the intended recipient of the message.</span></span> 
    
4. <span data-ttu-id="c13ef-148">**[件名]** メッセージの件名行のテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-148">**Subject** Specify the subject line text of the message.</span></span> 
    
5. <span data-ttu-id="c13ef-149">**[受信日時]** メッセージが検疫に到着したのが過去 24 時間以内 ( **[今日]**) か、過去 48 時間以内 ( **[過去 2 日間]**) か、過去 1 週間以内 ( **[過去 7 日間]**) かを選択したり、メッセージが検疫に到着した期間を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-149">**Received** You can select that the message was received by quarantine within the past 24 hours ( **Today**), within the past 48 hours ( **Last 2 days**), within the past week ( **Last 7 days**), or you can select a custom time interval during which the message was received by the quarantine.</span></span> 
    
6. <span data-ttu-id="c13ef-150">**[有効期限]** メッセージが検疫から削除されるのが今後 24 時間以内 ( **[今日]**) か、今後 48 時間以内 ( **[今後 2 日間]**) か、今後 1 週間以内 ( **[今後 7 日間]**) かを選択したり、メッセージが検疫から削除される期間を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-150">**Expires** You can select that the message will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval during which the message will be deleted from quarantine.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c13ef-151">既定では、スパム検疫メッセージは15日間検疫に保持され、メールフロールールと一致した検疫メッセージは7日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-151">By default, spam-quarantined messages are kept in quarantine for 15 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for 7 days.</span></span> <span data-ttu-id="c13ef-152">この期間が経過したら、Office 365 はメッセージを削除し、メッセージは取得不能になります。</span><span class="sxs-lookup"><span data-stu-id="c13ef-152">After this period of time Office 365 deletes the messages and they are not retrievable.</span></span> <span data-ttu-id="c13ef-153">メールフロールールと一致した検疫済みメッセージの保持期間は構成できません。</span><span class="sxs-lookup"><span data-stu-id="c13ef-153">The retention period for quarantined messages that matched a mail flow rule is not configurable.</span></span> <span data-ttu-id="c13ef-154">ただし、スパム検疫メッセージの保持期間は、コンテンツ フィルター ポリシーの **[次の期間スパムを保持する (日)]** の設定によって短縮できます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-154">However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies.</span></span> <span data-ttu-id="c13ef-155">詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13ef-155">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> 
  
7. <span data-ttu-id="c13ef-156">**種類\*\*\*\*スパム**として識別された検疫済みメッセージを検索するかどうか、またはメールフロールール (**トランスポートルール**) に一致したメッセージを検索するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-156">**Type** You can specify whether to search for quarantined messages that have been identified as **Spam**, or whether to search for messages that matched a mail flow rule (**Transport rule**).</span></span>
    
3. <span data-ttu-id="c13ef-157">高度な検索の実行を開始するには、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-157">Click **OK** to start running the advanced search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c13ef-158">検索条件をクリアして、検疫内のすべてのメッセージを表示するには、 **[高度な検索]** ウィンドウ内のすべてのチェック ボックスをオフにして、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-158">To clear your search criteria and view all messages in the quarantine, clear all the check boxes in the **Advanced search** window, and then click **OK**.</span></span> 
  
<span data-ttu-id="c13ef-p113">メッセージの検索後、指定した基準に一致する結果がユーザー インターフェイスに表示されます。EAC には、最大で 500 個のメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p113">After searching for messages, the results that match your specified criteria will display in the user interface. A maximum of 500 messages can be displayed in the EAC.</span></span> 
  
## <a name="view-details-about-a-specific-quarantined-message"></a><span data-ttu-id="c13ef-161">特定の検疫済みメッセージの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="c13ef-161">View details about a specific quarantined message</span></span>
<span data-ttu-id="c13ef-162"><a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a></span><span class="sxs-lookup"><span data-stu-id="c13ef-162"></span></span>

<span data-ttu-id="c13ef-163">**[検疫]** ページで検疫済みメッセージを特定した後、その詳細を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-163">After locating a specific quarantined message on the **quarantine** page, you can view details about it.</span></span> 
  
1. <span data-ttu-id="c13ef-164">**[検疫]** ページで特定のメッセージを選択すると、そのメッセージのプロパティの概要が画面右側の詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-164">On the **quarantine** page, select a specific message and a summary of the properties of that message appear in the details pane on the right side of the screen.</span></span> 
    
    <span data-ttu-id="c13ef-165">**[メッセージの状態]** の値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="c13ef-165">The **Message status** values are as follows:</span></span> 
    
  - <span data-ttu-id="c13ef-166">**種類**メッセージが**スパム**として識別されたかどうか、またはメールフロールール (**トランスポートルール**) に一致したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-166">**Type** Denotes whether the message has been identified as **Spam** or matched a mail flow rule (**Transport rule**).</span></span>
    
  - <span data-ttu-id="c13ef-167">**[有効期限]** メッセージが検疫から削除される日付。</span><span class="sxs-lookup"><span data-stu-id="c13ef-167">**Expires** The date when the message will be deleted from the quarantine.</span></span> 
    
    <span data-ttu-id="c13ef-168">**[メッセージの詳細]** の値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="c13ef-168">The **Message details** values are as follows:</span></span> 
    
  - <span data-ttu-id="c13ef-169">**[送信者]** メッセージの送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="c13ef-169">**Sender** The email address of the person who sent the message.</span></span> 
    
  - <span data-ttu-id="c13ef-170">**[件名]** メッセージの件名のテキスト。</span><span class="sxs-lookup"><span data-stu-id="c13ef-170">**Subject** The subject line text of the message.</span></span> 
    
  - <span data-ttu-id="c13ef-171">**[受信日時]** 検疫でメッセージが受信された日付。</span><span class="sxs-lookup"><span data-stu-id="c13ef-171">**Received** The date on which the message was received by the quarantine.</span></span> 
    
  - <span data-ttu-id="c13ef-172">**[サイズ]** キロバイト (KB) 単位のメッセージのサイズ。メッセージ サイズが 999 KB より大きい場合はメガバイト (MB) 単位。</span><span class="sxs-lookup"><span data-stu-id="c13ef-172">**Size** The size of the message, in kilobytes (KB), or, if the message size is greater than 999 KBs, in megabytes (MB).</span></span> 
    
  - <span data-ttu-id="c13ef-p114">**[メッセージ ヘッダーの表示]** このリンクをクリックすると **[メッセージ ヘッダー]** ダイアログ ボックスが開かれ、メッセージ ヘッダー テキストが表示可能されます。メッセージ ヘッダー テキストをクリップボードにコピーして [メッセージ ヘッダー アナライザー](https://testconnectivity.microsoft.com/?tabid=mha)に貼り付けることもできます。メッセージ ヘッダー アナライザー ツールに貼り付ければ、 **[ヘッダーの分析]** をクリックしてヘッダーに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p114">**View message header** Click this link to open the **message header** dialog box, which lets you view the message header text. You can also copy the message header text to your clipboard and paste it into the [Message Header Analyzer](https://testconnectivity.microsoft.com/?tabid=mha). Once in the Message Header Analyzer tool, click **Analyze headers** in order to retrieve information about the header.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="c13ef-176">サービスによって挿入される特定のスパム対策メッセージ ヘッダー フィールドの詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13ef-176">For information about specific anti-spam message header fields inserted by the service, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
  - <span data-ttu-id="c13ef-177">**[メール メッセージのプレビュー]** このリンクをクリックして、メッセージのテキストを確認します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-177">**Preview email message** Click this link to review the text of the message.</span></span> 
    
2. <span data-ttu-id="c13ef-178">検疫済みメッセージをダブルクリックすると、 **[検疫済みメッセージ]** ウィンドウが開き、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-178">If you double-click a quarantined message, the **Quarantined message** window opens and displays the following information:</span></span> 
    
  - <span data-ttu-id="c13ef-179">**[解放されました]** メッセージが解放されたすべてのメール アドレス (存在する場合) の一覧。</span><span class="sxs-lookup"><span data-stu-id="c13ef-179">**Released to** A list of all email addresses to whom the message has been released, if any.</span></span> 
    
  - <span data-ttu-id="c13ef-p115">**まだ解放されていません** メッセージが解放されていないすべての電子メール アドレス (存在する場合) の一覧。メッセージを解放するには、 **[解放する]** リンクをクリックします。メッセージの解放に関する詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p115">**Not yet released to** A list of all email addresses to whom the message has not been released, if any. You can click the **Release to** link in order to release the message; for more information about releasing a message, see the next section.</span></span> 
    
  - <span data-ttu-id="c13ef-182">**[メッセージ ID]** メッセージのヘッダーに表示されるインターネット メッセージ ID (クライアント ID とも呼ばれる)。</span><span class="sxs-lookup"><span data-stu-id="c13ef-182">**Message ID** The Internet Message ID (also known as the Client ID) found in the header of the message.</span></span> 
    
    <span data-ttu-id="c13ef-183">**[閉じる]** をクリックしてメインの検疫ウィンドウに戻ります。</span><span class="sxs-lookup"><span data-stu-id="c13ef-183">Click **Close** to return to the main quarantine pane.</span></span> 
    
## <a name="release-messages-from-quarantine"></a><span data-ttu-id="c13ef-184">メッセージの検疫からの解放</span><span class="sxs-lookup"><span data-stu-id="c13ef-184">Release messages from quarantine</span></span>
<span data-ttu-id="c13ef-185"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="c13ef-185"></span></span>

<span data-ttu-id="c13ef-186">受信者宛てのメッセージを解放する場合のオプションは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c13ef-186">If you want to release messages to recipients, your options are:</span></span>
  
- [<span data-ttu-id="c13ef-187">検疫済みメッセージを解放し、この送信者からの将来のメッセージを許可する</span><span class="sxs-lookup"><span data-stu-id="c13ef-187">Release a quarantined message and allow future messages from the sender</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [<span data-ttu-id="c13ef-188">検疫済みメッセージを誤検知として報告せずに特定の受信者に解放する</span><span class="sxs-lookup"><span data-stu-id="c13ef-188">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [<span data-ttu-id="c13ef-189">1 つ以上の検疫済みメッセージをすべての受信者に解放する</span><span class="sxs-lookup"><span data-stu-id="c13ef-189">Release one or more quarantined messages to all recipients</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [<span data-ttu-id="c13ef-190">Release one or more quarantined messages to all recipients and report false positives</span><span class="sxs-lookup"><span data-stu-id="c13ef-190">Release one or more quarantined messages to all recipients and report false positives</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a><span data-ttu-id="c13ef-191">検疫済みメッセージを解放し、この送信者からの将来のメッセージを許可する</span><span class="sxs-lookup"><span data-stu-id="c13ef-191">Release a quarantined message and allow future messages from the sender</span></span>
<span data-ttu-id="c13ef-192"><a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a></span><span class="sxs-lookup"><span data-stu-id="c13ef-192"></span></span>

1. <span data-ttu-id="c13ef-193">EAC で、 **[保護]** \> **[検疫]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-193">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="c13ef-194">メッセージをクリックして選択し、次のスクリーン ショットに示される **[メッセージの解放]** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-194">Click on a message to select it and then click the **Release Message** icon as shown in the following screen shot.</span></span> 
  
![[メッセージの解放] アイコンが強調表示され、解放オプションが示されている検疫ページを表示しています](media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
<span data-ttu-id="c13ef-196">**[選択したメッセージを解放し、送信者を許可します]** をドロップダウン リストからクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-196">Click **Release selected message and allow sender** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="c13ef-197">**[メッセージを解放し、送信者を許可する]** ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-197">The **release message and allow sender** dialog box opens.</span></span> <span data-ttu-id="c13ef-198">オプションで、メッセージを Microsoft に報告することを選択し、その後、 **[解放して許可する]** をクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-198">Optionally, you can choose to report the message to Microsoft, then click **release and allow**.</span></span> <span data-ttu-id="c13ef-199">メッセージは、アドレス指定されるすべての受信者に解放され、この送信者からの将来のメッセージはすべて許可されます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-199">The message will be released to all recipients it's addressed to and all future messages from this sender will be allowed.</span></span> <span data-ttu-id="c13ef-200">ただし、このメッセージがメールフロールールまたはブロックされる送信者によって検疫された場合、今後のメッセージの送信者は引き続きブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-200">However, if this message was quarantined because of a mail flow rule or blocked sender, the sender will continue to be blocked for future messages.</span></span> 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a><span data-ttu-id="c13ef-201">検疫済みメッセージを誤検知として報告せずに特定の受信者に解放する</span><span class="sxs-lookup"><span data-stu-id="c13ef-201">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>
<span data-ttu-id="c13ef-202"><a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a></span><span class="sxs-lookup"><span data-stu-id="c13ef-202"></span></span>

1. <span data-ttu-id="c13ef-203">EAC で、 **[保護]** \> **[検疫]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-203">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="c13ef-204">メッセージを選択し、 **[メッセージの解放]** アイコンをクリックして、ドロップダウン リストから **[特定の受信者にメッセージを解放します]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="c13ef-204">Select a message, click the **Release Message** icon, and then click **Release message to specific recipients** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="c13ef-205">**[メッセージの解放]** ダイアログ ボックスで、次のオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-205">In the **release message** dialog box, select one of the following options:</span></span> 
    
  - <span data-ttu-id="c13ef-p117">**すべての受信者にメッセージを解放する** このオプションを選択する場合、同じ受信者に 2 回以上メッセージを解放することはできないので注意してください。受信者が既にメッセージを受け取っていた場合、メッセージがその受信者にもう一度解放されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p117">**Release message to all recipients** When you select this option, be aware that a message cannot be released more than once to the same recipient. If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
  - <span data-ttu-id="c13ef-p118">**特定の受信者にメッセージを解放する** メッセージを解放できる受信者を選択します。メッセージは各受信者に 1 回しか解放できないため、解放先とすることができるユーザーのみがこの一覧に表示されます。複数選択がサポートされています。受信者を選択し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p118">**Release message to specified recipients** Select the recipient(s) to whom the message can be released. Because a message can only be released once to each recipient, only recipients to whom it can be released appear in this list. Multi-selection is supported. After making your recipient selections, click **add**.</span></span>
    
4. <span data-ttu-id="c13ef-212">**[解放]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-212">Click **release**.</span></span> 
    
<span data-ttu-id="c13ef-213">**[最新の情報に更新]**![[最新の情報に更新] アイコン](media/ITPro-EAC-RefreshIcon.gif) アイコンをクリックしてデータを更新してから、メッセージをダブルクリックすると、それが目的の受信者に解放されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-213">If you click the **Refresh**![Refresh Icon](media/ITPro-EAC-RefreshIcon.gif) icon to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span> 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a><span data-ttu-id="c13ef-214">1 つ以上の検疫済みメッセージをすべての受信者に解放する</span><span class="sxs-lookup"><span data-stu-id="c13ef-214">Release one or more quarantined messages to all recipients</span></span>
<span data-ttu-id="c13ef-215"><a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a></span><span class="sxs-lookup"><span data-stu-id="c13ef-215"></span></span>

1. <span data-ttu-id="c13ef-216">EAC で、 **[保護]** \> **[検疫]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-216">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="c13ef-p119">メッセージをクリックして選択するか、SHIFT キーを使用して複数のメッセージを選択します。 **[メッセージの解放]** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p119">Click on a message to select it, or use the shift key to select multiple messages. Then click the **Release Message** icon.</span></span> 
    
3. <span data-ttu-id="c13ef-219">**[選択したメッセージをすべての受信者に解放します]** をドロップダウン リストからクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-219">Click **Release selected message(s) to ALL recipients** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="c13ef-p120">警告ダイアログ ボックスが開きます。警告を読み、次に進む場合は **[はい]** を選択します。このオプションを選択する場合、同じ受信者に 2 回以上メッセージを解放することはできないので注意してください。受信者が既にメッセージを受け取っていた場合、メッセージがその受信者にもう一度解放されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p120">The warning dialog box opens. Read the warning and select **Yes** if you want to proceed. When you select this option, be aware that a message cannot be released more than once to the same recipient. If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a><span data-ttu-id="c13ef-224">すべての受信者に 1 つ以上の検疫済みメッセージを解放し、誤検知として報告する</span><span class="sxs-lookup"><span data-stu-id="c13ef-224">Release one or more quarantined messages to all recipients and report false positives</span></span>
<span data-ttu-id="c13ef-225"><a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a></span><span class="sxs-lookup"><span data-stu-id="c13ef-225"></span></span>

1. <span data-ttu-id="c13ef-226">EAC で、 **[保護]** \> **[検疫]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c13ef-226">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="c13ef-p121">メッセージをクリックして選択するか、SHIFT キーを使用して複数のメッセージを選択します。 **[メッセージの解放]** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p121">Click on a message to select it, or use the shift key to select multiple messages. Then click the **Release Message** icon.</span></span> 
    
3. <span data-ttu-id="c13ef-229">**[選択したメッセージを解放し、誤検知として報告します]** をドロップダウン リストからクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-229">Click **Release selected message(s) and report as false positive** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="c13ef-p122">警告ダイアログ ボックスが開きます。警告を読み、次に進む場合は **[はい]** を選択します。このオプションを選択する場合、同じ受信者に 2 回以上メッセージを解放することはできないので注意してください。受信者が既にメッセージを受け取っていた場合、メッセージがその受信者にもう一度解放されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p122">The warning dialog box opens. Read the warning and select **Yes** if you want to proceed. When you select this option, be aware that a message cannot be released more than once to the same recipient. If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
     <span data-ttu-id="c13ef-p123">このオプションを選択する場合、そのメッセージをまだ受信していないすべての受信者にメッセージが解放されます。スパム検疫済みメッセージの場合は、メッセージの評価と分析を行う Microsoft スパム分析チームに報告されます。分析結果によっては、このメッセージが許可されるようにサービス全体のスパム コンテンツ フィルター ルールが調整されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c13ef-p123">When you choose this option, the message will be released to all recipients who have not yet received it. If it's a spam-quarantined message, it will also be reported to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span> 
    
> [!TIP]
> <span data-ttu-id="c13ef-237">「[メッセージがスパムとしてマークされないようにする方法](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)」の手順に従って、メッセージがスパムとしてマークされないようにします。</span><span class="sxs-lookup"><span data-stu-id="c13ef-237">Help ensure that a message isn't marked as spam by following the steps in [How to help ensure that a message isn't marked as spam](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md).</span></span> 
  
<span data-ttu-id="c13ef-238">**[最新の情報に更新]**![[最新の情報に更新] アイコン](media/ITPro-EAC-RefreshIcon.gif) アイコンをクリックしてデータを更新してから、メッセージをダブルクリックすると、それが目的の受信者に解放されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="c13ef-238">If you click the **Refresh**![Refresh Icon](media/ITPro-EAC-RefreshIcon.gif) icon to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="c13ef-239">関連情報</span><span class="sxs-lookup"><span data-stu-id="c13ef-239">For more information</span></span>
<span data-ttu-id="c13ef-240"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="c13ef-240"></span></span>

[<span data-ttu-id="c13ef-241">検疫に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="c13ef-241">Quarantine FAQ</span></span>](quarantine-faq.md)
  

