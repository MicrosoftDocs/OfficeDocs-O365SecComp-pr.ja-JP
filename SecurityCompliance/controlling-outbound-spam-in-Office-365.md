---
title: Office 365 で送信スパムを制御する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 09/18/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: 組織がスパムとしてマークされている大量のバルクメールを送信すると、Office 365 での電子メールの送信がブロックされることがあります。このような状況についての詳細と、その理由については、この記事を参照してください。
ms.openlocfilehash: 476e1ddff73493881708e050fb7834e6bd6b272a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217337"
---
# <a name="controlling-outbound-spam-in-office-365"></a><span data-ttu-id="fc091-104">Office 365 で送信スパムを制御する</span><span class="sxs-lookup"><span data-stu-id="fc091-104">Controlling outbound spam in Office 365</span></span>

<span data-ttu-id="fc091-p102">私たちは共有サービスであるため、送信スパムを真剣に管理しています。 共有されたリソースプールの背後に多くのお客様がいる場合、あるユーザーが送信スパムを送信すると、そのサービスの発信 IP の評価が低下し、他のユーザーの電子メールの成功 deliverability に影響を与える可能性があります。顧客 B spams とさまざまなサードパーティの ip ブロック一覧に、使用する ip アドレスがある場合は、unfair にお客様に提供されます。</span><span class="sxs-lookup"><span data-stu-id="fc091-p102">We take managing outbound spam seriously because ours is a shared service.  There are many customers behind a shared pool of resources, where if one customer sends outbound spam, it can degrade the outbound IP reputation of the service and affects the successful deliverability of email for other customers. It is unfair to Customer A if Customer B spams and various 3rd party IP blocklists list the IP address that it uses.</span></span>

## <a name="what-admins-can-do-to-control-outbound-spam"></a><span data-ttu-id="fc091-108">管理者が送信スパムを制御する方法</span><span class="sxs-lookup"><span data-stu-id="fc091-108">What admins can do to control outbound spam</span></span>

- <span data-ttu-id="fc091-p103">**アカウントがスパムを送信しているとき、またはシャットダウンしたときに通知を有効に**します。メッセージが送信スパムとしてマークされ、高リスクプールを経由して送信されるときに、管理者は bcc を取得できます。このメールボックスを監視することにより、管理者は、ネットワークに侵害されたアカウントがあるかどうか、またはスパムフィルターが誤って電子メールをスパムとしてマークしたかどうかを検出できます。 送信スパムポリシーの設定の詳細については、[こちら](configure-the-outbound-spam-policy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc091-p103">**Enable notifications when an account is sending spam or shut down**. Administrators can get bcc’ed whenever a message is marked as outbound spam and sent through the High Risk pool. By monitoring this mailbox, an admin can detect if they have a compromised account in their network or if the spam filter is mistakenly marking their email as spam.  More information on setting up the outbound spam policy can be found [here](configure-the-outbound-spam-policy.md).</span></span>
 
- <span data-ttu-id="fc091-p104">**サードパーティの電子メールプロバイダーからスパムの苦情を手動で確認**します。Outlook.com、Yahoo および AOL などのサードパーティの電子メールサービスにはフィードバックループが用意されています。サービスのユーザーがメールをスパムとしてマークした場合は、メッセージがパッケージ化されて、レビューのためにマイクロソフトに送り返されます。Outlook.com の送信者のサポートの詳細については、[ここ](https://sendersupport.olc.protection.outlook.com/pm/services.aspx)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="fc091-p104">**Manually review spam complaints from 3rd party email providers**. Many 3rd party email services like Outlook.com, Yahoo and AOL provide a Feedback Loop where if any user in their service marks an email from our service as spam, the message is packaged up and sent back to us for review. To learn more about sender support for Outlook.com, click [here](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).</span></span>

## <a name="what-eop-does-to-control-outbound-spam"></a><span data-ttu-id="fc091-116">送信スパムを制御する EOP</span><span class="sxs-lookup"><span data-stu-id="fc091-116">What EOP does to control outbound spam</span></span> 

1. <span data-ttu-id="fc091-p105">**送信トラフィックの独立した ip プールへの**分離。顧客がサービス経由で送信するすべてのメッセージは、スパムに対してスキャンされます。メッセージがスパムである場合は、高リスク配信プールを経由してルーティングされます。この IP プールには、成果物以外の状態通知とスパムが含まれています。送信される電子メールの品質が原因で、多くのサードパーティが電子メールを受け入れないようにすることは保証されません。</span><span class="sxs-lookup"><span data-stu-id="fc091-p105">**Segregation of outbound traffic into separate pools of IPs**. Every message that customers send outbound through the service is scanned for spam. If the message is spam, it is routed through the High Risk Delivery pool. This IP pool contains non-deliverable status notifications and spam. Delivery to the intended recipient is not guaranteed as many third parties will not accept email because the quality of email it emits.</span></span><br/><br/><span data-ttu-id="fc091-p106">このようにトラフィックを分割することによって、低品質の電子メール (スパム、バックスキャッター ndr) は、通常の送信電子メールプールの評価を下にドラッグしないようにします。通常、高リスクプールはインターネット周辺の多くの受信者に低い評価を行いますが、これはユニバーサルではありません。</span><span class="sxs-lookup"><span data-stu-id="fc091-p106">Splitting the traffic this way ensures that the lower quality email (spam, backscatter NDRs) does not drag down the reputation of the regular outbound email pools. The high risk pool typically has low reputation at many receivers around the Internet, although this is not universal.</span></span> 

2. <span data-ttu-id="fc091-p107">**IP 評価の監視**。Office 365 は、さまざまなサードパーティの IP ブロックリストを照会し、送信 ip のいずれかがリストに含まれている場合にアラートを生成します。これにより、スパムによる評価が低下した場合に迅速に対応することができます。通知が生成されると、delisted を取得するために必要なその他の手順が内部ドキュメントにあります。</span><span class="sxs-lookup"><span data-stu-id="fc091-p107">**Monitoring of IP reputation**. Office 365 queries various 3rd party IP blocklists and generates alerts if any of our outbound IPs are listed on them. This allows us to react quickly when spam has caused our reputation to degrade. When an alert is generated, we have internal documentation outlying what steps to take to get delisted.</span></span> 

3. <span data-ttu-id="fc091-p108">**スパムとしてマークされている電子メールの数が多すぎると、問題のあるアカウントを無効に**します。スパムと非スパムは2つの別々の送信 IP プールに分離されていても、電子メールアカウントはスパムを無期限に送信できません。スパムを送信しているアカウントを監視し、undisclosed いうの制限を超えている場合、そのアカウントはスパムの送信をブロックされます。</span><span class="sxs-lookup"><span data-stu-id="fc091-p108">**Disabling of offending accounts when they send too much email marked as spam**. Even though we segregate our spam and non-spam into two separate outbound IP pools,  the email accounts cannot send spam indefinitely. We monitor which accounts are sending spam and if it exceeds an undisclosed limit, the account is blocked from sending spam.</span></span><br/><br/><span data-ttu-id="fc091-p109">スパムとしてマークされた1つのメッセージは、スパムエンジンによって誤った分類になることがあり、誤検知とも呼ばれます。高リスクプールを経由して送信することにより、移行の機会を得ることができます。ただし、短い時間枠に大量のメッセージがある場合は、問題が発生していることを示しているため、そのような場合には、アカウントによる電子メールの送信をブロックします。個々の電子メールアカウントにはさまざまなしきい値があり、テナント全体に対して集計にも存在します。</span><span class="sxs-lookup"><span data-stu-id="fc091-p109">A single message marked as spam may be a misclassification by the spam engine and also known as a false positive. We send it through the High Risk pool to give it a chance of going out; however, a large number of messages in a short time frame is indicative of a problem and when that occurs, we block the account from sending any more email. There are different thresholds that exist for individual email accounts as well as in aggregate for the entire tenant.</span></span>

4. <span data-ttu-id="fc091-p110">**電子メールの送信時間が短すぎる場合に、問題のあるアカウントを無効にする**。上記の制限に加えて、スパムとしてマークされたメッセージの割合に加えて、メッセージがスパムとしてマークされているかどうかに関係なく、全体の制限に達したときにアカウントをブロックする制限もあります。この制限が存在する理由は、危険にさらされたアカウントがスパムフィルターによって欠落したゼロ日スパムを送信する可能性があるためです。これは、不可能である場合でも、非常に少ない場合に、正当な大量郵送キャンペーンと大規模なスパムキャンペーンの違いを伝えることが困難であるため、これらの制限を有効にして潜在的な損害を制限します。</span><span class="sxs-lookup"><span data-stu-id="fc091-p110">**Disabling of offending accounts when they send too much email in too short a time frame**. In addition to the limits above that look for a proportion of messages marked as spam, there are also limits that block accounts when they reach an overall limit regardless of whether or not the messages are marked as spam. The reason this limit exists is because a compromised account could send zero-day spam that is missed by the spam filter. Because it is difficult, if not impossible, to sometimes tell the difference between a legitimate mass mailing campaign and a massive spam campaign, these limits activate to limit any potential damage.</span></span>

> [!NOTE]
> <span data-ttu-id="fc091-p111">#3 と #4 のどちらの場合も、正確な制限は提供されません。 これは、スパム送信者がシステムをゲームしないようにし、必要なときに制限を変更できるようにするためです。この制限は、平均的なビジネスユーザーがそれをヒットせず、スパム発信者が実行できる損害の大部分を含んでいることがない程度に大きくなっています。</span><span class="sxs-lookup"><span data-stu-id="fc091-p111">For both #3 and #4, we do not advertise the exact limits.  This is to prevent spammers from gaming the system and to ensure that we can change the limits when we need to. The limits are high enough such that an average business user will never hit them and low enough that it contains most of the damage a spammer can do.</span></span> 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a><span data-ttu-id="fc091-141">EOP を介して大量の電子メールを送信することを希望するお客様のための推奨される回避策</span><span class="sxs-lookup"><span data-stu-id="fc091-141">Recommended workarounds for customers who want to send outbound a lot of email through EOP</span></span>

<span data-ttu-id="fc091-p112">大量の電子メールの送信を希望しているお客様と、侵害されたアカウントやバルク電子メールによってサービスを保護することが不十分なリスト取得の手法を使用して、バランスを取ることは困難です。この場合も、サードパーティの blocklist での送信 IP ランディングのコストは、お客様が送信電子メールを送信するのをブロックするより高くなります。「 [Exchange Online サービスの説明](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits)」に記載されているように、EOP を使用してバルクメールを送信することは、サービスの使用をサポートしておらず、"ベストエフォート" ベースでのみ許可されています。バルクメールを送信する場合は、次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fc091-p112">It is difficult to strike a balance between customers who want to send a large volume of email vs. protecting the service from compromised accounts and bulk emailers with poor list acquisition practices. Again, the cost of an outbound IP landing on a 3rd party blocklist is higher than blocking a customer from sending outbound email. As described in the [Exchange Online Service Description](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits), using EOP to send bulk email is not a supported use of the service and is only permitted on a “best-effort” basis. For customers who do want to send bulk email, we recommend the following:</span></span>

1. <span data-ttu-id="fc091-p113">**専用の社内メールサーバーを使用して、バルクメールを送信**します。これは、お客様がこの種の電子メールのために独自の電子メールインフラストラクチャを維持する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fc091-p113">**Send the bulk email through its own on-premises mail servers**. This means that the customer will have to maintain its own email infrastructure for this type of email.</span></span>

2. <span data-ttu-id="fc091-p114">**サードパーティのバルク emailer を使用して、大量通信を送信**します。大量の電子メールを送信する必要があるサードパーティ製のバルクメールを提供している場合があります。お客様は、お客様と協力してメールを適切に設定し、それを実行する専用のリソースを用意することができます。</span><span class="sxs-lookup"><span data-stu-id="fc091-p114">**Use a 3rd party bulk emailer to send the mass communication**. There are several 3rd party bulk emailers whose sole business it is to send bulk email. They can work with customers to ensure that they have good emailing practices and they have resources dedicated to enforcing it.</span></span> 

<span data-ttu-id="fc091-p115">メッセージング、モバイル、マルウェア対策行為グループ (maawg) は、メンバーシップ名簿を[ここ](http://www.maawg.org/about/roster)に公開します。複数のバルクメールプロバイダーがリストにあり、インターネット市民を担当することがわかっています。</span><span class="sxs-lookup"><span data-stu-id="fc091-p115">The Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publishes its membership roster [here](http://www.maawg.org/about/roster). Several bulk email providers are on the list and are known to be responsible Internet citizens.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="fc091-153">関連情報</span><span class="sxs-lookup"><span data-stu-id="fc091-153">For more information</span></span>

[<span data-ttu-id="fc091-154">送信者が送信スパムの送信をブロックされる場合の通知例</span><span class="sxs-lookup"><span data-stu-id="fc091-154">Sample notification when a sender is blocked sending outbound spam</span></span>](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[<span data-ttu-id="fc091-155">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="fc091-155">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="fc091-156">Office 365 でのスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="fc091-156">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)

[<span data-ttu-id="fc091-157">Spam Confidence Level</span><span class="sxs-lookup"><span data-stu-id="fc091-157">Spam confidence levels</span></span>](spam-confidence-levels.md)
