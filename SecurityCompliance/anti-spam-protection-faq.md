---
title: スパム対策保護 FAQ
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: ここでは、スパム対策保護に関するよく寄せられる質問と回答について説明します。 回答は、Microsoft Exchange Online と Exchange Online Protection (EOP) のお客様に当てはまります。
ms.openlocfilehash: 8c374efcf109baa97755447ff1dc6fb20b253063
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598243"
---
# <a name="anti-spam-protection-faq"></a><span data-ttu-id="d9b18-104">スパム対策保護 FAQ</span><span class="sxs-lookup"><span data-stu-id="d9b18-104">Anti-spam protection FAQ</span></span>

<span data-ttu-id="d9b18-p102">ここでは、スパム対策保護に関するよく寄せられる質問と回答について説明します。 回答は、Microsoft Exchange Online と Exchange Online Protection (EOP) のお客様に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p102">This topic provides frequently asked questions and answers about anti-spam protection. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection (EOP) customers.</span></span> 
  
> [!TIP]
> <span data-ttu-id="d9b18-p103">差出人セーフ リストと受信拒否リストに関する質問と回答については、「[Exchange Online の差出人セーフ リストと受信拒否リスト](safe-sender-and-blocked-sender-lists-faq.md)」を参照してください。 検疫に関する質問と回答については、「[検疫に関する FAQ](quarantine-faq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p103">For questions and answers about safe sender and blocked sender lists, see [Safe sender and blocked sender lists in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md). For questions and answers about the quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span> 
  
 <span data-ttu-id="d9b18-109">**Q. 既定では、スパム検出メッセージはどのように処理されますか?**</span><span class="sxs-lookup"><span data-stu-id="d9b18-109">**Q. By default, what happens to a spam-detected message?**</span></span>
  
<span data-ttu-id="d9b18-p104">A. **着信メッセージの場合、** スパムの大部分は、送信者の IP アドレスに基づき、接続フィルタを介して削除されます。 次に、このサービスはメッセージのコンテンツを検査します。 既定では、コンテンツ フィルターで処理されたスパムは受信者の迷惑メール フォルダーに送信されます。 既定のアクションを変更できます。 たとえば、コンテンツ フィルター ポリシーで構成することにより、スパム メッセージを検疫に送信できます。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p104">A. **For inbound messages:** The majority of spam is deleted via connection filtering, which is based on the IP address of the sender. The service then inspects the contents of the message. By default, content-filtered spam is sent to the recipient's Junk Email folder. You can change this action. For example, you can choose to send spam messages to the quarantine instead by configuring the content filter policy.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d9b18-116">EOP スタンドアロンのお客様の場合: [**迷惑メールフォルダーにメッセージを移動**します] アクションがオンプレミスのメールボックスと連携するようにするには、オンプレミスのサーバー上で2つの Exchange メールフロールール (トランスポートルールとも呼ばれます) を設定して検出する必要があります。EOP によって追加されたスパムヘッダー。</span><span class="sxs-lookup"><span data-stu-id="d9b18-116">For EOP standalone customers: In order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="d9b18-117">詳細については、「 [スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b18-117">For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
 <span data-ttu-id="d9b18-118">**送信メッセージの場合、** メッセージは、より危険度の高い配信プール経由でルーティングされるか、戻ってきて配信されないかのいずれかです。後者の場合は、送信者がメッセージを配信できなかったことを知らせる配信状態通知 (DSN) メッセージを受け取るはずです。</span><span class="sxs-lookup"><span data-stu-id="d9b18-118">**For outbound messages:** The message is either routed through the higher risk delivery pool or is bounced and not delivered, in which case the sender should receive a delivery status notification (DSN) message telling them that the message couldn't be delivered.</span></span> 
  
 <span data-ttu-id="d9b18-119">**Q. ゼロデイ スパム バリアントとは何ですか。また、サービスはそれをどのように処理しますか。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-119">**Q. What's a zero-day spam variant and how is it handled by the service?**</span></span>
  
<span data-ttu-id="d9b18-p106">A. ゼロデイ スパム バリアントは、これまで収集または分析が行われたことのない第 1 世代の未知のバリアントであり、弊社のスパム コンテンツ フィルターはその検出に必要な情報を把握していません。 弊社のスパム分析者によってゼロデイ スパムのサンプルが収集および分析されてから、それがスパム分類基準を満たしている場合は、弊社のスパム コンテンツ フィルターがそれを検出するように更新され、"ゼロデイ" と見なされなくなります ( **メモ:** ゼロデイ スパム バリアントの可能性があるというメッセージが表示された場合は、サービスの向上を支援するために、「 [スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」に記載された方法のいずれかを使用して、そのメッセージを Microsoft に送信してください)。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p106">A. A zero-day spam variant is a first generation, previously unknown variant of spam that's never been captured or analyzed, so our spam content filters don't yet have any information available for detecting it. After a zero-day spam sample is captured and analyzed by our spam analysts, if it meets the spam classification criteria, our spam content filters are updated to detect it, and it's no longer considered "zero-day." ( **Note:** If you receive a message that may be a zero-day spam variant, in order to help us improve the service, please submit the message to Microsoft using one of the methods described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).)</span></span>
  
 <span data-ttu-id="d9b18-124">**Q. スパム対策保護を提供するサービスを構成する必要はありますか?**</span><span class="sxs-lookup"><span data-stu-id="d9b18-124">**Q. Do I need to configure the service to provide anti-spam protection?**</span></span>
  
<span data-ttu-id="d9b18-p107">A. サービスのサインアップを行い、ドメインを追加すると、既定のスパム対策ポリシーにより、会社全体でスパム フィルタリングが自動的に有効になります。 既定のポリシーは、(前述の EOP スタンドアロンのお客様の場合を除いて) 付加的な設定をしなくても保護されるよう調整されています。 管理者は、既定のスパム対策ポリシーを編集して、組織の実際の必要を最も良く満たすように調整することができます。 よりきめ細かく制御する場合は、カスタム コンテンツ フィルター ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p107">A. After you sign up for the service and add your domain, spam filtering is automatically enabled company-wide through the default anti-spam policies. The default policies are tuned to protect you without needing any additional configuration (aside from the exception noted above for EOP standalone customers). As an admin, you can edit the default anti-spam policies so that they're tailored to best meet the needs of your organization. For greater granularity, you can also create custom content filter policies and apply them to specified users, groups, or domains in your organization. Custom policies always take precedence over the default policy, but you can change the priority (that is, the running order) of your custom policies.</span></span>
  
<span data-ttu-id="d9b18-131">スパム対策ポリシーの構成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b18-131">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="d9b18-132">接続フィルター ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="d9b18-132">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="d9b18-133">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="d9b18-133">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="d9b18-134">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="d9b18-134">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
 <span data-ttu-id="d9b18-135">**Q. スパム対策ポリシーを変更した場合、変更を保存してからその変更が反映されるまで、どれ位かかりますか?**</span><span class="sxs-lookup"><span data-stu-id="d9b18-135">**Q. If I make a change to an anti-spam policy, how long does it take after I save my changes for them to take effect?**</span></span>
  
<span data-ttu-id="d9b18-p108">A. 変更が有効になるまで最大 1 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p108">A. It may take up to 1 hour for the changes to take effect.</span></span>
  
 <span data-ttu-id="d9b18-138">**Q. バルク メールのフィルタリングは自動的に有効になりますか?**</span><span class="sxs-lookup"><span data-stu-id="d9b18-138">**Q. Is bulk email filtering automatically enabled?**</span></span>
  
<span data-ttu-id="d9b18-p109">A. 新しいお客様の場合は、既定で、 **[バルク メール]** という高度なスパム フィルタリング オプションが有効になっています。 移行したお客様の場合、この設定はご使用の FOPE 構成と一致します。 バルク メールの詳細については、「 [迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p109">A. By default, the **Bulk mail** advanced spam filtering option is enabled for new customers. For migrated customers, this setting will match your FOPE configuration. For more information about bulk email, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>
  
 <span data-ttu-id="d9b18-143">**Q. このサービスでは URL フィルター機能が提供されますか?**</span><span class="sxs-lookup"><span data-stu-id="d9b18-143">**Q. Does the service provide URL filtering?**</span></span>
  
<span data-ttu-id="d9b18-p110">A. はい。このサービスには、メッセージ中の URL を検査する URL フィルターが含まれています。 既知のスパムまたは悪質なコンテンツに関連する URL が検出された場合、そのメッセージはスパムとしてマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p110">A. Yes the service has a URL filter that checks for URLs within messages. If URLs associated with known spam or malicious content are detected then the message is marked as spam.</span></span>
  
 <span data-ttu-id="d9b18-147">**Q. サービス使用中の顧客が Microsoft へ偽陰性 (スパム) メッセージおよび偽陽性 (スパムでない) メッセージを送信するにはどうしますか。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-147">**Q. How can customers using the service send false negative (spam) and false positive (non-spam) messages to Microsoft?**</span></span>
  
<span data-ttu-id="d9b18-p111">A. スパムとスパムではないメッセージを分析のために Microsoft に送信するには、いくつかの方法があります。 詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p111">A. Spam and non-spam messages can be submitted to Microsoft for analysis in several ways. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> 
  
 <span data-ttu-id="d9b18-151">**Q. スパム報告を取得できますか?**</span><span class="sxs-lookup"><span data-stu-id="d9b18-151">**Q. Can I get spam reports?**</span></span>
  
<span data-ttu-id="d9b18-152">A.</span><span class="sxs-lookup"><span data-stu-id="d9b18-152">A.</span></span> <span data-ttu-id="d9b18-153">はい。たとえば、Microsoft 365 管理センターでスパム検出レポートを取得できます。</span><span class="sxs-lookup"><span data-stu-id="d9b18-153">Yes, for example you can get a spam detection report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d9b18-154">このレポートでは、スパムボリュームが一意のメッセージ数として表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9b18-154">This report shows spam volume as a count of unique messages.</span></span> <span data-ttu-id="d9b18-155">レポートの詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b18-155">For more information about reporting, see the following links:</span></span>
  
<span data-ttu-id="d9b18-156">Exchange Online のお客様: [Exchange online での監視、レポート、メッセージ追跡](http://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)</span><span class="sxs-lookup"><span data-stu-id="d9b18-156">Exchange Online customers: [Monitoring, Reporting, and Message Tracing in Exchange Online](http://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)</span></span>
  
<span data-ttu-id="d9b18-157">Exchange Online Protection のお客様: [Exchange Online protection でのレポート作成とメッセージ追跡](eop/reporting-and-message-trace-in-exchange-online-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d9b18-157">Exchange Online Protection customers: [Reporting and message trace in Exchange Online Protection](eop/reporting-and-message-trace-in-exchange-online-protection.md)</span></span>
  
 <span data-ttu-id="d9b18-158">**Q. 誰かが私にメッセージを送りましたが、そのメッセージを見つけられません。 スパムとして検出された可能性があります。 調べるためのツールはありますか?**</span><span class="sxs-lookup"><span data-stu-id="d9b18-158">**Q. Someone sent me a message and I can't find it. I suspect that it may have been detected as spam. Is there a tool that I can use to find out?**</span></span>
  
<span data-ttu-id="d9b18-p113">A. はい。メッセージ追跡機能を使用して、サービスを通過するメール メッセージを追跡し、メール メッセージがどのように処理されたのかを確認できます。 メッセージ追跡ツールを使用して、スパムとしてメッセージが設定された理由を調べる方法の詳細については、「[メッセージはスパムとしてマークされましたか?](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="d9b18-p113">A. Yes, the message trace tool enables you to follow email messages as they pass through the service, in order to find out what happened to them. For more information about how to use the message trace tool to find out why a message was marked as spam, see [Was a message marked as spam? ](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam)</span></span>
  
 <span data-ttu-id="d9b18-162">**Q. ユーザーがスパムを送信した場合、サービスはメールを調整 (速度制限) しますか?**</span><span class="sxs-lookup"><span data-stu-id="d9b18-162">**Q. Will the service throttle (rate limit) my mail if my users send outbound spam?**</span></span>
  
<span data-ttu-id="d9b18-p114">A.特定の時間枠 (たとえば、1 時間ごと) 内でサービスを使用してユーザーから送信されたメールの半数以上が、Office 365 によってスパムと判断された場合、ユーザーはメッセージを送信できなくなります。ほとんどの場合、送信メッセージがスパムと判断された場合、そのメッセージは高リスク配信プールを通じてルーティングされます。この結果、通常の送信 IP プールが禁止リストに追加される可能性は減少します。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p114">A. If more than half of the mail that is sent from a user through the service within a certain time frame (for example, per hour), is determined to be spam by Office 365, the user will be blocked from sending messages. In most cases, if an outbound message is determined to be spam, it is routed through the high-risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span>
  
<span data-ttu-id="d9b18-p115">送信者が送信スパムの送信をブロックされている場合、指定したメール アドレスに通知を送信できます。 この設定の詳細については、「[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p115">You can send a notification to a specified email address when a sender is blocked sending outbound spam. For more information about this setting, see [Configure the outbound spam policy](configure-the-outbound-spam-policy.md).</span></span>
  
 <span data-ttu-id="d9b18-168">**Q. サードパーティのスパム対策およびマルウェア対策プロバイダーを Exchange Online と併用できますか。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-168">**Q. Can I use a third-party anti-spam and anti-malware provider in conjunction with Exchange Online?**</span></span>
  
<span data-ttu-id="d9b18-p116">A. できます。Exchange Online のメールボックスを保護するために、別のスパムおよびマルウェア フィルタリング サービスを構成できます。 着信メールに対してこれを構成するには、MX レコードをサードパーティ プロバイダーを指すように変更して電子メール メッセージをサードパーティ プロバイダーにリダイレクトし、その後そのメッセージを EOP にリダイレクトしてさらに処理を行う必要があります。 送信メールに対して構成するには、[Scenario: Outbound Smart Hosting](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx) に示すように、メッセージの配信先をサードパーティ プロバイダー (スマート ホスト) に設定してください。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p116">A. Yes, you may configure another spam and malware filtering service to protect your Exchange Online mailboxes. To do this for inbound mail, you should redirect your email messages to the third-party provider by changing your MX records to point to the third-party provider, and then redirect the messages to EOP for additional processing. To do this for outbound mail, please configure the message delivery destination to the third-party provider (smart host), as shown in [Scenario: Outbound Smart Hosting](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx).</span></span>
  
 <span data-ttu-id="d9b18-173">**Q。 マイクロソフトには、フィッシング詐欺から自分を守る方法に関するドキュメントはありますか。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-173">**Q. Does Microsoft have any documentation about how I can protect myself from phishing scams?**</span></span>
  
<span data-ttu-id="d9b18-p117">A. はいあります。次の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p117">A. Yes we do, please consult the following articles:</span></span>
  
[<span data-ttu-id="d9b18-176">フィッシング詐欺、宝くじ詐欺、その他の詐欺に関するヘルプを取得する</span><span class="sxs-lookup"><span data-stu-id="d9b18-176">Get help with phishing scams, lottery fraud, and other types of scams</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=325606)
  
[<span data-ttu-id="d9b18-177">電子メールおよび Web 詐欺: 自分を守る方法</span><span class="sxs-lookup"><span data-stu-id="d9b18-177">Email and web scams: How to help protect yourself</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=325607)
  
 <span data-ttu-id="d9b18-178">**Q. スパム メッセージおよびマルウェア メッセージの送信元に関する調査や、法執行機関への転送は行っていますか?**</span><span class="sxs-lookup"><span data-stu-id="d9b18-178">**Q. Are spam and malware messages being investigated as to who sent them, or being transferred to law enforcement entities?**</span></span>
  
<span data-ttu-id="d9b18-p118">A. サービスの中心はスパムやマルウェアの検出と除去ですが、特に危険で破壊力が大きい一連のスパムまたは攻撃については、加害者を調査および追跡する場合があります。 たとえば、Microsoft の法律部門やデジタル犯罪対策部門と連携して悪意のあるボットネットを削除したり、加害者がサービスを使用できないようにしたり (そのサービスが外部への電子メール送信に使用されている場合)、刑事告発のために法執行機関に情報を提供したりします。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p118">A. The service focuses on spam and malware detection and removal, though we may occasionally investigate especially dangerous or damaging spam or attack campaigns and pursue the perpetrators. This may involve working with our legal and digital crime units to take down a spammer botnet, blocking the spammer from using the service (if they're using it for sending outbound email), and passing the information on to law enforcement for criminal prosecution.</span></span>
  
 <span data-ttu-id="d9b18-182">**Q. メールが確実に配信されるようにするための、送信メールに関するベスト プラクティスは?**</span><span class="sxs-lookup"><span data-stu-id="d9b18-182">**Q. What are a set of best outbound mailing practices that will ensure that my mail is delivered?**</span></span>
  
<span data-ttu-id="d9b18-p119">A. 以下に示すガイドラインは、送信メール メッセージを送信するためのベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p119">A. The guidelines presented below are best practices for sending outbound email messages.</span></span>
  
1. <span data-ttu-id="d9b18-185">**電子メールの送信元のドメインの DNS で解決する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-185">**The sending domain of the email should resolve in DNS.**</span></span>
    
    <span data-ttu-id="d9b18-186">たとえば、送信者が user@example.com であり、ドメイン example.com が IP アドレス 192.0.43.10 に解決されるとします。</span><span class="sxs-lookup"><span data-stu-id="d9b18-186">For example, if the sender is user@example.com, the domain example.com resolves to the IP address 192.0.43.10.</span></span> <span data-ttu-id="d9b18-187">DNS で送信者のドメインの A-record と MX レコードが存在しない場合、メッセージのコンテンツがスパムであるなしにかかわらず、サービスはより危険度の高い配信プール経由でメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d9b18-187">If a sending domain has no A-record and no MX record in DNS, the service will route the message through its higher risk delivery pool regardless of whether or not the content of the message is spam.</span></span> <span data-ttu-id="d9b18-188">より危険度の高い配信プールの詳細については、「[送信メッセージ用の高リスク配信プール](high-risk-delivery-pool-for-outbound-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b18-188">For more information about the higher risk delivery pool, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span> 
    
2. <span data-ttu-id="d9b18-189">**送信メール サーバーの送信 IP アドレスには、逆引き DNS (PTR) エントリが必要です。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-189">**The sending IP address of the outbound mail server should have a reverse DNS (PTR) entry.**</span></span>
    
    <span data-ttu-id="d9b18-190">たとえば、IP アドレス 192.0.43.10 から送信されると、この IP の逆引き DNS エントリは 43-10.any.icann.org です。</span><span class="sxs-lookup"><span data-stu-id="d9b18-190">For example, if sending from the IP address 192.0.43.10, the reverse DNS entry for this IP is 43-10.any.icann.org.</span></span> 
    
3. <span data-ttu-id="d9b18-191">**HELO/EHLO および MAIL FROM コマンドに整合性があり、IP アドレスではなくドメイン名の形式で表現される必要があります。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-191">**The HELO/EHLO and MAIL FROM commands should be consistent and be present in the form of a domain name rather than an IP address.**</span></span>
    
    <span data-ttu-id="d9b18-192">HELO/EHLO コマンドは送信 IP アドレスの逆引き DNS と一致するように構成する必要があります。このようにすることで、メッセージ ヘッダーのあらゆる部分でドメインが同一に保たれます。</span><span class="sxs-lookup"><span data-stu-id="d9b18-192">The HELO/EHLO command should be configured to match the reverse DNS of the sending IP address so that the domain remains the same across the various parts of the message headers.</span></span>
    
4. <span data-ttu-id="d9b18-193">**適切な SPF レコードが DNS に設定されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-193">**Ensure that proper SPF records are set up in DNS.**</span></span>
    
    <span data-ttu-id="d9b18-p121">SPF レコードとは、ドメインから送信されたメールがそのドメインから実際に送信されていること、なりすましではないことを確認するためのメカニズムです。 SPF レコードの詳細については、以下のリンクを参照してください:</span><span class="sxs-lookup"><span data-stu-id="d9b18-p121">SPF records are a mechanism for validating that mail sent from a domain really is coming from that domain and is not spoofed. For more information about SPF records, see the following links:</span></span>
    
    [<span data-ttu-id="d9b18-196">スプーフィングを防止するために Office 365 で SPF を設定する</span><span class="sxs-lookup"><span data-stu-id="d9b18-196">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
    
    <span data-ttu-id="d9b18-197">「[Office 365 の DNS レコードを作成する](https://go.microsoft.com/fwlink/?LinkID=275414)」</span><span class="sxs-lookup"><span data-stu-id="d9b18-197">[Create DNS records for Office 365](https://go.microsoft.com/fwlink/?LinkID=275414)</span></span>
    
5. <span data-ttu-id="d9b18-198">**DKIM で電子メールを署名する場合、relaxed 正規化で署名します。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-198">**Signing email with DKIM, sign with relaxed canonicalization.**</span></span>
    
    <span data-ttu-id="d9b18-p122">送信者が Domain Keys Identified Mail (DKIM) を使用してメッセージに署名し、サービスを通じて送信メールを送信する場合、送信者は relaxed ヘッダー正規化アルゴリズムを使用して署名する必要があります。 strict ヘッダー正規化で署名することにより、メッセージがサービスを通過するときに署名が無効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p122">If a sender wants to sign their messages using Domain Keys Identified Mail (DKIM) and they want to send outbound mail through the service, they should sign using the relaxed header canonicalization algorithm. Signing with strict header canonicalization may invalidate the signature when it passes through the service.</span></span>
    
6. <span data-ttu-id="d9b18-201">**ドメイン所有者は、WHOIS データベースに正確な情報が必要です。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-201">**Domain owners should have accurate information in the WHOIS database.**</span></span>
    
    <span data-ttu-id="d9b18-202">これにより、安定した親会社、連絡先、およびネーム サーバーを入力することで、ドメインの所有者と問い合わせ方法が特定されます。</span><span class="sxs-lookup"><span data-stu-id="d9b18-202">This identifies the owners of the domain and how to contact them by entering the stable parent company, point of contact, and name servers.</span></span>
    
7. <span data-ttu-id="d9b18-203">**バルク メール業者にとって、From: 名は メッセージの送信者を表し、メッセージの件名行はメッセージの内容の概要である必要があります。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-203">**For bulk mailers, the From: name should reflect who is sending the message, while the subject line of the message should be a brief summary on what the message is about.**</span></span>
    
    <span data-ttu-id="d9b18-p123">メッセージの本文は、提供、サービス、製品の分かりやすい説明である必要があります。 たとえば、送信者が Contoso 会社のバルク メールを送信している場合、電子メールの差出人および件名は以下のようになります:</span><span class="sxs-lookup"><span data-stu-id="d9b18-p123">The message body should have a clear indication of the offering, service, or product. For example, if a sender is sending out a bulk mailing for the Contoso company, the following is what the email From and Subject should resemble:</span></span>
    
    <span data-ttu-id="d9b18-206">From: marketing@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d9b18-206">From: marketing@contoso.com</span></span>
    
    <span data-ttu-id="d9b18-207">件名: クリスマス シーズンの最新カタログ!</span><span class="sxs-lookup"><span data-stu-id="d9b18-207">Subject: New updated catalog for the Christmas season!</span></span> 
    
    <span data-ttu-id="d9b18-208">以下の例は説明的ではないため、バルク メールとしては不適切です。</span><span class="sxs-lookup"><span data-stu-id="d9b18-208">The following is an example of what not to do because it is not descriptive:</span></span>
    
    <span data-ttu-id="d9b18-209">From: user@hotmail.com</span><span class="sxs-lookup"><span data-stu-id="d9b18-209">From: user@hotmail.com</span></span>
    
    <span data-ttu-id="d9b18-210">件名: カタログ</span><span class="sxs-lookup"><span data-stu-id="d9b18-210">Subject: Catalogs</span></span>
    
8. <span data-ttu-id="d9b18-211">**バルク メールが多数の受信者に送信されるもので、メッセージが広報形式である場合、メッセージの最下部に登録解除手段が存在する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-211">**If sending a bulk mailing to many recipients and the message is in newsletter format, there should be a way of unsubscribing at the bottom of the message.**</span></span>
    
    <span data-ttu-id="d9b18-212">登録解除オプションは次のように表示されるはずです:</span><span class="sxs-lookup"><span data-stu-id="d9b18-212">The unsubscribe option should resemble the following:</span></span>
    
    <span data-ttu-id="d9b18-p124">このメッセージは、sender@fabrikam.com から example@contoso.com に送信されました。Update Profile/Email Address | Instant removal with **SafeUnsubscribe** | Privacy Policy</span><span class="sxs-lookup"><span data-stu-id="d9b18-p124">This message was sent to example@contoso.com by sender@fabrikam.com. Update Profile/Email Address | Instant removal with **SafeUnsubscribe**™ | Privacy Policy</span></span>
    
9. <span data-ttu-id="d9b18-215">**バルク メールを送信する場合、ダブル オプトインを使用してリスト取得を実行する必要があります。バルク メールの送信者にとって、ダブル オプトインは業界のベスト プラクティスです。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-215">**If sending bulk email, list acquisition should be performed using double opt-in. If you are a bulk mailer, double opt-in is an industry best practice.**</span></span>
    
    <span data-ttu-id="d9b18-216">ダブル オプトインでは、ユーザーがマーケティング メールの会員になるには、2 つのアクションを実行する必要があります:</span><span class="sxs-lookup"><span data-stu-id="d9b18-216">Double opt-in is the practice of requiring a user to take two actions to sign up for marketing mail:</span></span>
    
1. <span data-ttu-id="d9b18-217">1 回目は、ユーザーが以前にオンではなかったチェックボックスをクリックすることにより、ユーザーが業者からの広告やメール メッセージを今後も受け取ることを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9b18-217">Once when the user clicks on a previously unchecked check box where they opt-in to receive further offers or email messages from the marketer.</span></span>
    
2. <span data-ttu-id="d9b18-218">2 回目は、ユーザーが入力したメール アドレスに確認メールを業者が送信します。この確認メールにある時間制限付きリンクをユーザーがクリックすることにより、確認が完了します。</span><span class="sxs-lookup"><span data-stu-id="d9b18-218">A second time when the marketer sends a confirmation email to the user's provided email address asking them to click on a time-sensitive link that will complete their confirmation.</span></span>
    
    <span data-ttu-id="d9b18-219">ダブル オプトインを使用することで、バルク メール送信業者としての良好な評価を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="d9b18-219">Using double opt-in builds a good reputation for bulk email senders.</span></span>
    
10. <span data-ttu-id="d9b18-220">**バルク送信業者は、説明責任を負うことが可能な透過的コンテンツを作成する必要があります:**</span><span class="sxs-lookup"><span data-stu-id="d9b18-220">**Bulk senders should create transparent content for which they can be held accountable:**</span></span>
    
1. <span data-ttu-id="d9b18-221">アドレス帳に送信者を追加するようメール受信者に何度もお願いしても、それがメールの配信を保証しないことは明らかです。</span><span class="sxs-lookup"><span data-stu-id="d9b18-221">Verbiage requesting that recipients add the sender to the address book should clearly state that such action is not a guarantee of delivery.</span></span>
    
2. <span data-ttu-id="d9b18-222">メッセージ本文でリダイレクトを作成するときには、一貫したリンク スタイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9b18-222">When constructing redirects in the body of the message, use a consistent link style.</span></span>
    
3. <span data-ttu-id="d9b18-223">サイズの大きな画像や添付ファイル、画像だけのメッセージは送信しません。</span><span class="sxs-lookup"><span data-stu-id="d9b18-223">Don't send large images or attachments, or messages that are solely composed of an image.</span></span>
    
4. <span data-ttu-id="d9b18-224">トラッキング ピクセル (Web バグ、ビーコン) を使用する場合には、プライバシー ポリシー、P3P 設定にトラッキング ピクセルが存在することを明記します。</span><span class="sxs-lookup"><span data-stu-id="d9b18-224">When employing tracking pixels (web bugs or beacons), clearly state their presence in your public privacy or P3P settings.</span></span>
    
11. <span data-ttu-id="d9b18-225">**送信方向の配信状態通知の書式を設定します。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-225">**Format outbound delivery status notifications.**</span></span>
    
    <span data-ttu-id="d9b18-226">配信状態通知メッセージを生成するとき、送信業者は「[RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715)」で指定されるバウンス メールの形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9b18-226">When generating delivery status notification messages, senders should follow the format of a bounce as specified in [RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715).</span></span>
    
12. <span data-ttu-id="d9b18-227">**存在しないユーザーのバウンスされたメール アドレスを削除します。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-227">**Remove bounced email addresses for non-existent users.**</span></span>
    
    <span data-ttu-id="d9b18-p125">メール アドレスが使用されていないことを示す NDR を受信したら、存在しないメール エイリアスを一覧から削除します。 メール アドレスは時間とともに変化し、ユーザーはメール アドレスを破棄することがあります。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p125">If you receive an NDR indicating that an email address is no longer in use, remove the non-existent email alias from your list. Email addresses change over time, and people sometimes discard them.</span></span>
    
13. <span data-ttu-id="d9b18-230">**Hotmail の Smart Network Data Services (SNDS) プログラムを使用します。**</span><span class="sxs-lookup"><span data-stu-id="d9b18-230">**Use Hotmail's Smart Network Data Services (SNDS) program.**</span></span>
    
    <span data-ttu-id="d9b18-p126">Hotmail は Smart Network Data Services というプログラムを使用します。このプログラムにより、送信業者はエンド ユーザーが送信したクレームをチェックできます。 SNDS は、Hotmail の配信の問題をトラブルシューティングするための第一のポータルです。</span><span class="sxs-lookup"><span data-stu-id="d9b18-p126">Hotmail uses a program called Smart Network Data Services that allows senders to check complaints submitted by end users. The SNDS is the primary portal for troubleshooting delivery problems to Hotmail.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="d9b18-233">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d9b18-233">For more information</span></span>

[<span data-ttu-id="d9b18-234">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="d9b18-234">Office 365 Email Anti-Spam Protection</span></span>](https://support.office.com/article/6a601501-a6a8-4559-b2e7-56b59c96a586)
  
[<span data-ttu-id="d9b18-235">Exchange Online の差出人セーフ リストと受信拒否リスト</span><span class="sxs-lookup"><span data-stu-id="d9b18-235">Safe sender and blocked sender lists in Exchange Online</span></span>](safe-sender-and-blocked-sender-lists-faq.md)
  
[<span data-ttu-id="d9b18-236">スパム対策メッセージ ヘッダー</span><span class="sxs-lookup"><span data-stu-id="d9b18-236">Anti-spam message headers</span></span>](anti-spam-message-headers.md)
  
[<span data-ttu-id="d9b18-237">バックスキャター メッセージと EOP</span><span class="sxs-lookup"><span data-stu-id="d9b18-237">Backscatter messages and EOP</span></span>](backscatter-messages-and-eop.md)
  

