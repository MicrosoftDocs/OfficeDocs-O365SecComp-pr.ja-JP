---
title: Office 365 でメールが迷惑メールとしてマークされるのを防ぐ方法
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 34823bbc-a3e3-4949-ba42-97c73997eeed
description: Office 365 で、メールが迷惑メールにならないようにし、迷惑メールとしてマークされるのを防ぐ方法について説明します。
ms.openlocfilehash: f7ba560b4eb30abcda4c97617ead883659558bd8
ms.sourcegitcommit: 6d72cdb882b93edf6dfddb5ff2e6d8a16e2fa0bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2018
ms.locfileid: "25596720"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a><span data-ttu-id="ef74e-103">Office 365 でメールが迷惑メールとしてマークされるのを防ぐ方法</span><span class="sxs-lookup"><span data-stu-id="ef74e-103">How to prevent real email from being marked as spam in Office 365</span></span>

 <span data-ttu-id="ef74e-104">**Office 365 でメールが迷惑メールとしてマークされていますか? 以下のようにしてください。**</span><span class="sxs-lookup"><span data-stu-id="ef74e-104">**Is your real email getting marked as spam in Office 365? Do this.**</span></span>
  
<span data-ttu-id="ef74e-p101">Exchange Online Protection (EOP) は、迷惑メールをフィルターで除外して、ユーザーが見たくないコンテンツが受信トレイに入らないようにします。ただし、時には、ユーザーが本当に見たいものが EOP によってフィルターで除外されてしまうことがあります。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p101">Exchange Online Protection (EOP) attempts to filter out spam, keeping your Inbox clear of content that users don't want to see. But sometimes, EOP filters out things that you do want to see.</span></span>
  
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a><span data-ttu-id="ef74e-107">メッセージが迷惑メールとしてマークされた理由を判断する</span><span class="sxs-lookup"><span data-stu-id="ef74e-107">Determine the reason why the message was marked as spam</span></span>

<span data-ttu-id="ef74e-p102">Office 365 での迷惑メールに関する多くの問題は、[メールのメッセージ ヘッダーを調べ](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)、そうなった理由を判断することによって解決できます。文字列 SFV:NSPM を含む X-Forefront-Antispam-Report というメッセージ ヘッダーがある場合、Exchange Online Protection (EOP) はメッセージをスキャンしてそれを迷惑メールと見なしたことを意味します。この場合は、[メッセージ報告アドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)してフィルターが改善されるようにすることを強くお勧めします。この値がヘッダーにない場合は、メールが迷惑メール スキャンをパススルーしなかったか、構成の問題があったためにメッセージが迷惑メールとして誤って分類されたことが考えられます。[迷惑メール対策メッセージ ヘッダーに関する詳しい説明](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p102">Many issues with spam in Office 365 can be resolved by [View e-mail message headers](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) and determining what went wrong. If you see a message header named X-Forefront-Antispam-Report that contains the string SFV:NSPM, this means that Exchange Online Protection (EOP) scanned the message and thought it was spam. In this case, we strongly recommend that you [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) to help us improve our filters. If you don't see this value in the headers, it could mean either that the mail didn't pass through spam scanning, or that there was a configuration issue which caused the message to be incorrectly classified as spam. You can [learn more about anti-spam message headers](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="ef74e-113">ヘッダーで、次の見出しと値を探します。</span><span class="sxs-lookup"><span data-stu-id="ef74e-113">In the header, look for the following headings and values.</span></span>
  
### <a name="x-forefront-antispam-report"></a><span data-ttu-id="ef74e-114">X-Forefront-Antispam-Report</span><span class="sxs-lookup"><span data-stu-id="ef74e-114">X-Forefront-Antispam-Report</span></span>

- <span data-ttu-id="ef74e-115">**SFV:BLK** 送信元アドレスが受信者の受信拒否リストにあるためにメッセージが迷惑メールとしてマークされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ef74e-115">**SFV:BLK** Indicates that the message was marked as spam because the sending address is on the recipient's Blocked Senders List.</span></span> 
    
- <span data-ttu-id="ef74e-p103">**SFV:SKS** コンテンツ フィルターの前にメッセージが迷惑メールとしてマークされたことを示します。この場合は、メッセージを迷惑メールとしてマークするトランスポート ルールが関係している可能性があります。メッセージ トレースを実行して、Spam Confidence Level (SCL) が高く設定されていそうなトランスポート ルールがトリガーされたかどうかを調べてください。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p103">**SFV:SKS** Indicates that the message was marked as spam prior to the content filter. This could include a transport rule marking the message as spam. Run a message trace to see if a transport rule triggered which may have set a high spam confidence level (SCL).</span></span> 
    
- <span data-ttu-id="ef74e-119">**SFV:SKB** メッセージは迷惑メール フィルター ポリシーの拒否リストと一致したために迷惑メールとしてマークされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ef74e-119">**SFV:SKB** Indicates that the message was marked as spam because it matched a block list in the spam filter policy.</span></span> 
    
- <span data-ttu-id="ef74e-p104">**SFV:BULK** x-microsoft-antispam ヘッダーにある Bulk Complaint Level (BCL) 値が、コンテンツ フィルターに設定されているバルクしきい値を超えていることを示します。バルク メールとは、ユーザーはサインアップした可能性があるとしても望ましくないと思われるメールのことです。メッセージ ヘッダーで、X-Microsoft-Antispam ヘッダーの中の BCL (Bulk Confidence Level) プロパティを見つけます。迷惑メール フィルターに設定されたしきい値よりも BCL 値の方が小さければ、これらのタイプのバルク メッセージを迷惑メールとしてマークするようにしきい値を調整することが必要になる場合があります。[バルク メールの処理](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/)に関する許容度とユーザー設定はユーザーによって異なります。ユーザー設定ごとに異なるポリシーやルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p104">**SFV:BULK** Indicates that the Bulk Complaint Level (BCL) value located in the x-microsoft-antispam header is above the Bulk threshold that has been set for the content filter. Bulk email is email which users may have signed up for, but may still be undesirable. In the message header find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header. If the BCL value is less than the threshold set in the Spam Filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam. Different users have different tolerances and preferences for [how bulk email is handled](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/). You can create different policies or rules for different user preferences.</span></span>
    
- <span data-ttu-id="ef74e-p105">**CAT:SPOOF** または **CAT:PHISH** メッセージはなりすましと思われることを示します。つまり、メッセージ ソースは検証できないため、疑わしい可能性があるということです。有効であるなら、送信元は SPF と DKIM が適切に構成されていることを確認する必要があります。詳細については、Authentication-Results ヘッダーを確認してください。すべての送信元に適切なメール認証方法を使用させるのは難しいかもしれませんが、こうした確認を省略することは極めて危険であり、侵害の一番の原因です。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p105">**CAT:SPOOF** or **CAT:PHISH** Indicates that the message appears to be spoofed, meaning that the message source cannot be validated and could be suspicious. If valid, the sender will need to make sure that they have proper SPF and DKIM configuration. Check the Authentication-Results header for more information. Although it may be difficult to get all senders to use proper email authentication methods, bypassing these checks can be extremely dangerous and is the top cause of compromises.</span></span> 
    
### <a name="x-customspam"></a><span data-ttu-id="ef74e-130">x-customspam</span><span class="sxs-lookup"><span data-stu-id="ef74e-130">x-customspam</span></span>

- <span data-ttu-id="ef74e-p106">このヘッダーがあるということは、迷惑メール フィルターでいずれかの[高度な迷惑メール オプションが有効になっている](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx)ためにメッセージが迷惑メールとしてマークされたことを示しています。これらの機能を必要としない限り、既定の設定を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p106">The presence of this header indicates that the message was marked as spam because one of the [advanced spam options is enabled](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) in your spam filter. Unless you need these features, we recommend that you use the default settings.</span></span> 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a><span data-ttu-id="ef74e-133">大量の迷惑メールの他の原因の解決方法</span><span class="sxs-lookup"><span data-stu-id="ef74e-133">Solutions to additional causes of too much spam</span></span>

<span data-ttu-id="ef74e-p107">Exchange Online Protection (EOP) が効率的に機能するためには、いくつかのタスクを管理者が実行する必要があります。Office 365 テナントの管理者でなく、大量の迷惑メールを受け取っているユーザーは、これらのタスクを管理者と一緒に行うこともできます。そうしない場合は、ユーザーのセクションにスキップしてください。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p107">In order to work effectively, Exchange Online Protection (EOP) requires that administrators complete a few tasks. If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks. Otherwise, you can skip to the user section.</span></span>
  
### <a name="for-admins"></a><span data-ttu-id="ef74e-137">管理者向け</span><span class="sxs-lookup"><span data-stu-id="ef74e-137">For admins</span></span>

- <span data-ttu-id="ef74e-p108">**DNS レコードを Office 365 に向ける** EOP によって保護されるためには、すべてのドメインのメール エクスチェンジャー (MX) DNS レコードが Office 365 (Office 365 のみ) に向いていなければなりません。MX が Office 365 に向いていなければ、EOP はユーザーのための迷惑メール フィルター処理を行いません。別のサービスまたはアプライアンスを使用してドメインのための迷惑メール フィルター処理を行う場合は、EOP の迷惑メール保護を無効にすることを検討する必要があります。これを行うには、SCL 値を -1 に設定するトランスポート ルールを作成します。EOP を使用することを後で決定する場合は、このトランスポート ルールを必ず削除してください。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p108">**Point your DNS records to Office 365** In order for EOP to provide protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365. If your MX does not point to Office 365, then EOP will not provide spam filtering for your users. In the situation where you wish to use another service or appliance to provide spam filtering for your domain, you should consider disabling the spam protection in EOP. You can do this by creating a transport rule that sets the SCL value to -1. If you later decide to use EOP, make sure to remove this transport rule.</span></span> 
    
- <span data-ttu-id="ef74e-p109">**Outlook の SmartScreen フィルターを無効にする** ユーザーが Outlook デスクトップ クライアントを使用している場合、ユーザーは中断されている SmartScreen フィルター機能を無効にする必要があります。有効にしておくと、誤検知の原因になることがあります。これは、更新されたデスクトップ Outlook クライアントを実行している場合は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p109">**Disable SmartScreen filtering in Outlook** If your users are using the Outlook desktop client, they should disable the SmartScreen filtering functionality, which has been discontinued. If enabled, it can cause false positives. This should not be required if running an updated desktop Outlook client.</span></span> 
    
- <span data-ttu-id="ef74e-p110">**ユーザーのメッセージ報告アドインをオンにする** [ユーザーのメッセージ報告アドインを有効にする](enable-the-report-message-add-in.md)ことを強くお勧めします。管理者は、ユーザーが送信しているフィードバックを調べ、あらゆるパターンを使用して、問題の原因と思われる設定を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p110">**Turn on the report message add-in for users** We strongly recommend that you [enable the report message add-in for you users](enable-the-report-message-add-in.md). As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>
    
- <span data-ttu-id="ef74e-p111">**すぐに送信元を許可する** すぐに送信元を許可する必要がある場合は、**特定の送信元の IP アドレスのみ許可する**ことを強くお勧めします。あるいは、送信元を許可したうえで、送信元が SPF や DKIM のような認証検査に合格したことを確認する (送信元ドメインと成功した Authentication-Results ヘッダーの**両方**を求めるトランスポート ルールを作成する) こともできます。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p111">**Immediately allow a sender** In the case where you need to immediately allow a sender, we strongly recommend that you **ONLY allow a particular sender's IP address**. Alternately, you can allow a sender and also make sure that the sender passes an authentication check like SPF or DKIM by creating a transport rule that looks for **both** the sender domain and a successful Authentication-Results header.</span></span> 
    
### <a name="for-users"></a><span data-ttu-id="ef74e-150">ユーザー向け</span><span class="sxs-lookup"><span data-stu-id="ef74e-150">For users</span></span>

- <span data-ttu-id="ef74e-p112">**Microsoft に迷惑メールを報告する** [メッセージ報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) を使用して、Microsoft に迷惑メール メッセージを報告します。また、junk@office365.microsoft.com にメッセージを送信し、1 つ以上のメッセージをレポートに添付することができます。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p112">**Report spam to Microsoft** Report spam messages to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Additionally, you can send a message to junk@office365.microsoft.com and attach one or more messages to report.</span></span>
    
    <span data-ttu-id="ef74e-153">**重要** メッセージを添付ファイルとして転送しなければ、[ヘッダーがないために Office 365 の迷惑メール フィルターの改善ができなくなります](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/)。</span><span class="sxs-lookup"><span data-stu-id="ef74e-153">**Important** If you do not forward the messages as attachments, then [the headers will be missing and we will be unable to improve](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/) the junk mail filtering in Office 365.</span></span> 
    
- <span data-ttu-id="ef74e-p113">**許可リストに送信元を追加する (ただし慎重に使用する)** 最後の手段として、[ブロックまたは許可 (迷惑メール設定)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) を行えます。その場合は、対象となるフィッシング試行が受信トレイに入れられるようになる可能性があることに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef74e-p113">**Add a sender to your allow list - but use sparingly** As a last resort, you can [Block or allow (junk email settings)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). If you do so, you should beware that a targeted phishing attempt may be allowed into your inbox.</span></span>
    

