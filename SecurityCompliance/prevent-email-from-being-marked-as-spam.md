---
title: Office 365 で誤検知が発生しないようにする方法
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: Strat_O365_IP
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Office 365 で誤検知が発生しないようにして、正しいメールが迷惑メールにならないようにする方法について説明します。
ms.openlocfilehash: d225f7ae3a97d497787c91ed6d4baab1b979f0c3
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410782"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a><span data-ttu-id="1de76-103">Office 365 でメールが迷惑メールとしてマークされるのを防ぐ方法</span><span class="sxs-lookup"><span data-stu-id="1de76-103">How to prevent real email from being marked as spam in Office 365</span></span>

 <span data-ttu-id="1de76-104">**Office 365 でメールが迷惑メールとしてマークされていますか? 以下のようにしてください。**</span><span class="sxs-lookup"><span data-stu-id="1de76-104">**Is your real email getting marked as spam in Office 365? Do this.**</span></span>
  
<span data-ttu-id="1de76-p101">誤検知が発生する場合は、「[迷惑メール報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)」ことにより Microsoft にそのメールを報告してください。または、メッセージを*添付ファイルとして* not_junk@office365.microsoft.com に転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="1de76-p101">If you get a false positive, you should report the message to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Additionally, you can forward the message *as an attachment* to not_junk@office365.microsoft.com.</span></span>

<span data-ttu-id="1de76-107">**重要**: メッセージを添付ファイルとして転送しなければ、ヘッダーがないために Office 365 の迷惑メール フィルターの改善ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="1de76-107">**Important** If you do not forward the messages as an attachment, then the headers will be missing and we will be unable to improve the junk mail filtering in Office 365.</span></span>
    
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a><span data-ttu-id="1de76-108">メッセージが迷惑メールとしてマークされた理由を判断する</span><span class="sxs-lookup"><span data-stu-id="1de76-108">Determine the reason why the message was marked as spam</span></span>

<span data-ttu-id="1de76-p102">Office 365 での迷惑メールに関する多くの問題は、[電子メール メッセージ ヘッダーの表示](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)によって解決し、何が原因か特定することができます。X-Forefront-Antispam-Report という名前のヘッダーを検索する必要があります。詳細については、「[スパム対策メッセージ ヘッダー](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de76-p102">Many issues with spam in Office 365 can be resolved by [View e-mail message headers](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) and determining what went wrong. You will need to look for a header named X-Forefront-Antispam-Report. You can [learn more about anti-spam message headers](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="1de76-112">ヘッダーで、次の見出しと値を探します。</span><span class="sxs-lookup"><span data-stu-id="1de76-112">In the header, look for the following headings and values.</span></span>
  
### <a name="x-forefront-antispam-report"></a><span data-ttu-id="1de76-113">X-Forefront-Antispam-Report</span><span class="sxs-lookup"><span data-stu-id="1de76-113">X-Forefront-Antispam-Report</span></span>

- <span data-ttu-id="1de76-114">**SFV:SPM** EOP のスパム対策フィルターにより、メッセージが迷惑メールとしてマークされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="1de76-114">**SFV:SPM** Indicates that the message was marked as spam because of the EOP spam filters.</span></span> 

- <span data-ttu-id="1de76-115">**SFV:BLK** 送信元アドレスが受信者の受信拒否リストにあるためにメッセージが迷惑メールとしてマークされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="1de76-115">**SFV:BLK** Indicates that the message was marked as spam because the sending address is on the recipient's Blocked Senders List.</span></span> 
    
- <span data-ttu-id="1de76-p103">**SFV:SKS** コンテンツ フィルターの前にメッセージが迷惑メールとしてマークされたことを示します。この場合は、メッセージを迷惑メールとしてマークするメール フロー ルール (別名: トランスポート ルール) が関係している可能性があります。メッセージ トレースを実行して、Spam Confidence Level (SCL) が高く設定されていそうなメール フロー ルールがトリガーされたかどうかを調べてください。</span><span class="sxs-lookup"><span data-stu-id="1de76-p103">**SFV:SKS** Indicates that the message was marked as spam prior to the content filter. This could include a mail flow rule (also known as a transport rule) marking the message as spam. Run a message trace to see if a mail flow rule triggered which may have set a high spam confidence level (SCL).</span></span> 
    
- <span data-ttu-id="1de76-119">**SFV:SKB** メッセージは迷惑メール フィルター ポリシーの拒否リストと一致したために迷惑メールとしてマークされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="1de76-119">**SFV:SKB** Indicates that the message was marked as spam because it matched a block list in the spam filter policy.</span></span> 
    
- <span data-ttu-id="1de76-p104">**SFV:BULK** x-microsoft-antispam ヘッダーにある Bulk Complaint Level (BCL) 値が、コンテンツ フィルターに設定されているバルクしきい値を超えていることを示します。バルク メールとは、ユーザーはサインアップした可能性があるとしても望ましくないと思われるメールのことです。メッセージ ヘッダーで、X-Microsoft-Antispam ヘッダーの中の BCL (Bulk Confidence Level) プロパティを見つけます。迷惑メール フィルターに設定されたしきい値よりも BCL 値の方が小さければ、これらのタイプのバルク メッセージを迷惑メールとしてマークするようにしきい値を調整することが必要になる場合があります。[バルク メールの処理](https://docs.microsoft.com/ja-JP/office365/SecurityCompliance/bulk-complaint-level-values)に関する許容度とユーザー設定はユーザーによって異なります。ユーザー設定ごとに異なるポリシーやルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1de76-p104">**SFV:BULK** Indicates that the Bulk Complaint Level (BCL) value located in the x-microsoft-antispam header is above the Bulk threshold that has been set for the content filter. Bulk email is email which users may have signed up for, but may still be undesirable. In the message header find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header. If the BCL value is less than the threshold set in the Spam Filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam. Different users have different tolerances and preferences for [how bulk email is handled](https://docs.microsoft.com/ja-JP/office365/SecurityCompliance/bulk-complaint-level-values). You can create different policies or rules for different user preferences.</span></span>
    
- <span data-ttu-id="1de76-p105">**CAT:SPOOF** または **CAT:PHISH** メッセージはなりすましと思われることを示します。つまり、メッセージ ソースは検証できないため、疑わしい可能性があるということです。有効であるなら、送信元は SPF と DKIM が適切に構成されていることを確認する必要があります。詳細については、Authentication-Results ヘッダーを確認してください。すべての送信元に適切なメール認証方法を使用させるのは難しいかもしれませんが、こうした確認を省略することは極めて危険であり、侵害の一番の原因です。</span><span class="sxs-lookup"><span data-stu-id="1de76-p105">**CAT:SPOOF** or **CAT:PHISH** Indicates that the message appears to be spoofed, meaning that the message source cannot be validated and could be suspicious. If valid, the sender will need to make sure that they have proper SPF and DKIM configuration. Check the Authentication-Results header for more information. Although it may be difficult to get all senders to use proper email authentication methods, bypassing these checks can be extremely dangerous and is the top cause of compromises.</span></span> 
    
### <a name="x-customspam"></a><span data-ttu-id="1de76-130">x-customspam</span><span class="sxs-lookup"><span data-stu-id="1de76-130">x-customspam</span></span>

- <span data-ttu-id="1de76-p106">このヘッダーがあるということは、迷惑メール フィルターでいずれかの[高度な迷惑メール オプションが有効になっている](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx)ためにメッセージが迷惑メールとしてマークされたことを示しています。これらの機能を必要としない限り、既定の設定を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1de76-p106">The presence of this header indicates that the message was marked as spam because one of the [advanced spam options is enabled](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) in your spam filter. Unless you need these features, we recommend that you use the default settings.</span></span> 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a><span data-ttu-id="1de76-133">大量の迷惑メールの他の原因の解決方法</span><span class="sxs-lookup"><span data-stu-id="1de76-133">Solutions to additional causes of too much spam</span></span>

<span data-ttu-id="1de76-p107">Exchange Online Protection (EOP) が効率的に機能するためには、いくつかのタスクを管理者が実行する必要があります。Office 365 テナントの管理者でなく、大量の迷惑メールを受け取っているユーザーは、これらのタスクを管理者と一緒に行うこともできます。そうしない場合は、ユーザーのセクションにスキップしてください。</span><span class="sxs-lookup"><span data-stu-id="1de76-p107">In order to work effectively, Exchange Online Protection (EOP) requires that administrators complete a few tasks. If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks. Otherwise, you can skip to the user section.</span></span>
  
### <a name="for-admins"></a><span data-ttu-id="1de76-137">管理者向け</span><span class="sxs-lookup"><span data-stu-id="1de76-137">For admins</span></span>

- <span data-ttu-id="1de76-p108">**DNS レコードが Office 365 を指すようにする** EOP が保護を提供するためには、すべてのドメインのメール エクスチェンジャー (MX) DNS レコードが Office 365 だけを指すようにする必要があります。お使いの MX が Office 365 を指していない場合、EOP はユーザーに迷惑メール フィルター機能を提供しません。別のサービスまたはアプライアンスを使用してドメインのための迷惑メールをフィルタリングする場合、EOP の迷惑メール保護を無効にすることを検討する必要があります。これを行うには、SCL 値を -1 に設定するメール フロー ルールを作成します。EOP を使用することを後で決定する場合は、このメール フロー ルールを必ず削除してください。</span><span class="sxs-lookup"><span data-stu-id="1de76-p108">**Point your DNS records to Office 365** In order for EOP to provide protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365. If your MX does not point to Office 365, then EOP will not provide spam filtering for your users. In the situation where you wish to use another service or appliance to provide spam filtering for your domain, you should consider disabling the spam protection in EOP. You can do this by creating a mail flow rule that sets the SCL value to -1. If you later decide to use EOP, make sure to remove this mail flow rule.</span></span> 
    
- <span data-ttu-id="1de76-p109">**ユーザーのメッセージ報告アドインをオンにする** [ユーザーのメッセージ報告アドインを有効にする](enable-the-report-message-add-in.md)ことを強くお勧めします。管理者は、ユーザーが送信しているフィードバックを調べ、あらゆるパターンを使用して、問題の原因と思われる設定を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="1de76-p109">**Turn on the report message add-in for users** We strongly recommend that you [enable the report message add-in for your users](enable-the-report-message-add-in.md). As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>
    
### <a name="for-users"></a><span data-ttu-id="1de76-145">ユーザー向け</span><span class="sxs-lookup"><span data-stu-id="1de76-145">For users</span></span>
    
- <span data-ttu-id="1de76-p110">**信頼できる差出人リストを作成する** 信頼できる差出人のアドレスを [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) または [Outlook on the web](https://go.microsoft.com/fwlink/p/?LinkId=294862) で信頼できる差出人リストに追加します。Outlook on the web でこの操作を行うには、**[設定]**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> \*\*[オプション] \*\* \> **[ブロックまたは許可]** の順に選びます。次の図は、信頼できる差出人リストにアドレスを追加する例です。</span><span class="sxs-lookup"><span data-stu-id="1de76-p110">**Create a safe sender list** Users can add addresses from senders that they trust to their safe sender list in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) or [Outlook on the Web](https://go.microsoft.com/fwlink/p/?LinkId=294862). To get started in Outlook on the Web, choose **Settings**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Options** \> **Block or allow**. The following diagram shows an example of adding something to a safe sender list.</span></span>
  
![Outlook on the web で信頼できる差出人を追加する](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
<span data-ttu-id="1de76-p111">EOP では、ユーザーの信頼できる差出人と宛先のリストは適用されますが、信頼できるドメインは適用されません。ドメインが Outlook on the web と Outlook のどちらで追加されたか、Outlook で追加してからディレクトリ同期によって同期されたかにかかわらず、適用されません。</span><span class="sxs-lookup"><span data-stu-id="1de76-p111">EOP will honor your users' Safe Senders and Recipients, but not Safe Domains. This is true regardless of whether the domain is added through the Outlook on the Web, or added in Outlook and synchronized using Directory Sync.</span></span>

- <span data-ttu-id="1de76-p112">**Outlook の SmartScreen フィルターを無効にする** ユーザーが古い Outlook デスクトップ クライアントを使用している場合、廃止されている SmartScreen フィルター機能を無効にする必要があります。有効にしておくと、誤検知の原因になることがあります。これは、更新されたデスクトップ Outlook クライアントを実行している場合は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1de76-p112">**Disable SmartScreen filtering in Outlook** If you are using an older Outlook desktop client, you should disable the SmartScreen filtering functionality, which has been discontinued. If enabled, it can cause false positives. This should not be required if running an updated desktop Outlook client.</span></span>

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a><span data-ttu-id="1de76-155">トラブルシューティング: EOP がメッセージを迷惑メールではないとマークしてもメッセージが迷惑メール フォルダーに送られる</span><span class="sxs-lookup"><span data-stu-id="1de76-155">Troubleshooting: A message ends up in the Junk folder even though EOP marked the message as non-spam</span></span>
<span data-ttu-id="1de76-156"><a name="TroubleshootingJunkEOPNonSpam"> </a></span><span class="sxs-lookup"><span data-stu-id="1de76-156"></span></span>

<span data-ttu-id="1de76-p113">ユーザーが Outlook のオプションで、[セーフ リストのみ: 差出人セーフ リストまたは宛先セーフ リストに登録されたユーザーやドメインからのメールのみを受信トレイに配信する] を有効にしている場合、受信者が信頼できる差出人のリストに登録していない差出人からのすべてのメールは、迷惑メールに送られます。EOP がメッセージを迷惑メールではないと判断したかどうか、または管理者がメッセージを迷惑メールではないと判断するルールを EOP に設定したかどうかにかかわらず、この処理は実行されます。</span><span class="sxs-lookup"><span data-stu-id="1de76-p113">If your users have the option in Outlook enabled for "Safe Lists Only: Only mail from people or domains on your Safe Senders list or Safe Recipients List will be delivered to your Inbox", then all email will go to the junk folder for a sender unless the sender is on the recipient's Safe Sender list. This will happen regardless of whether EOP marks a message as non-spam, or if you have set up a rule in EOP to mark a message as non-spam.</span></span>
  
<span data-ttu-id="1de76-159">Outlook ユーザーの [セーフ リストのみ] オプションを無効にするには、「[Outlook: 迷惑メール UI とフィルター処理機構を無効にするポリシー設定](https://support.microsoft.com/ja-JP/kb/2180568)」の指示に従って操作してください。</span><span class="sxs-lookup"><span data-stu-id="1de76-159">You can disable the Safe Lists Only option for your Outlook users by following the instructions in [Outlook: Policy setting to disable the Junk E-mail UI and filtering mechanism](https://support.microsoft.com/ja-JP/kb/2180568).</span></span>
  
<span data-ttu-id="1de76-160">Outlook on the web でメッセージを表示している場合、受信者の信頼できる差出人のリストに差出人が登録されていないため、メッセージが迷惑メール フォルダーに送られた、という黄色の安全性のヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1de76-160">If you view the message in Outlook on the Web, there will be a yellow safety tip that indicates that the message is in the Junk folder because the sender is not on the recipient's Safe Senders list.</span></span>
  
<span data-ttu-id="1de76-p114">メッセージのヘッダーに "SFV:SKN (IP Allow or ETR Allow)" または "SFV:NSPM (non-spam)" というスタンプが含まれていても、メッセージがユーザーの迷惑メール フォルダーに送られることがあります。メッセージ ヘッダーには、ユーザーが [セーフ リストのみ] を有効にしたことを示すものがありません。これは、Outlook でユーザーが設定した [セーフ リストのみ] オプションの方が、EOP 設定よりも優先されるために起こります。</span><span class="sxs-lookup"><span data-stu-id="1de76-p114">If you look at the header of a message, it may include the stamp SFV:SKN (IP Allow or ETR Allow) or SFV:NSPM (non-spam), but the message is still placed in the user's junk folder. There is nothing in the message header that indicates that the user has "Safe Lists Only" enabled. This happens because the "Safe Lists Only" option set by users in Outlook overrides the EOP setting.</span></span> 
  
 <span data-ttu-id="1de76-164">**信頼できる差出人からのメッセージがメッセージ ヘッダーでは迷惑メールではないとマークされているのに、最終的にはユーザーの迷惑メール フォルダーに送られる理由を検証するには**</span><span class="sxs-lookup"><span data-stu-id="1de76-164">**To verify why a message from a safe sender is marked as non-spam in the message header, but still ends up in the user's Junk folder**</span></span>
  
1. <span data-ttu-id="1de76-165">Exchange Online PowerShell への接続方法については、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de76-165">To learn how to connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> 
    
2. <span data-ttu-id="1de76-166">次のコマンドを実行して、ユーザーの迷惑メール構成設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="1de76-166">Run the following command to view the user's junk email configuration settings:</span></span>
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- <span data-ttu-id="1de76-167">TrustedListsOnly が True に設定されている場合、[セーフ リストのみ] が有効であることを示します。</span><span class="sxs-lookup"><span data-stu-id="1de76-167">If TrustedListsOnly is set to True, it means that this setting is enabled</span></span>
- <span data-ttu-id="1de76-168">ContactsTrusted が True の場合、ユーザーが連絡先と信頼できる差出人の両方を信頼していることを示します。</span><span class="sxs-lookup"><span data-stu-id="1de76-168">If ContactsTrusted is set to True, it means that the user trusts both Contacts and Safe Senders</span></span>
- <span data-ttu-id="1de76-169">TrustedSendersAndDomains では、ユーザーの信頼できる差出人のリストの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1de76-169">The TrustedSendersAndDomains lists the contents of the user's Safe Senders list</span></span>


## <a name="eop-only-customers-use-directory-synchronization"></a><span data-ttu-id="1de76-170">EOP のみのユーザー: ディレクトリ同期の使用</span><span class="sxs-lookup"><span data-stu-id="1de76-170">EOP-only customers: use directory synchronization</span></span>

<span data-ttu-id="1de76-p115">EOP のみのユーザーの場合、つまり、オンプレミス Exchange メール サーバーで使用するために EOP サービスにサブスクライブしている場合、ディレクトリ同期を使用して、ユーザー設定をサービスと同期することをお勧めします。こうすることで、信頼できる差出人のリストが EOP に適用されます。詳細については、「[EOP でメール ユーザーを管理する](https://go.microsoft.com/fwlink/?LinkId=534098)」の記事の「ディレクトリ同期を使用してメール ユーザーを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de76-p115">If you're an EOP-only customer, that is, you subscribe to the EOP service for use with your on-premises (Exchange) email server, you should sync user settings with the service by using directory synchronization. Doing this ensures that your safe senders lists are respected by EOP. For more information, see "Use directory synchronization to manage mail users" in [Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).</span></span>
