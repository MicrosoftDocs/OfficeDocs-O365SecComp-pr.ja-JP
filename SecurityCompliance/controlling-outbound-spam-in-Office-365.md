---
title: Office 365 で送信スパムを制御する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/18/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: 組織では、スパムとしてマークされている迷惑メールの多くを送信する場合は Office 365 で電子メールを送信することから禁止を取得でした。このような理由と何ができるかについての詳細については、この資料を参照してください。
ms.openlocfilehash: 947ea4ed7a37b2ba1c5332aa07582fa4c4949eb0
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972249"
---
# <a name="controlling-outbound-spam-in-office-365"></a><span data-ttu-id="ba73c-104">Office 365 で送信スパムを制御する</span><span class="sxs-lookup"><span data-stu-id="ba73c-104">Controlling outbound spam in Office 365</span></span>

<span data-ttu-id="ba73c-p102">共有サービスは、私たちのために深刻な迷惑メールの送信を管理するを取得します。 1 人の顧客は、迷惑メールの送信を送信する場合送信 IP 評価サービスの低下し、他のお客様の e メールの成功の提に影響を与える、リソースの共有プールの背後にある多くのお客様があります。顧客 B の spams し、さまざまなサード パーティ製 IP ブロック リスト既にを使用している IP アドレスを一覧表示する場合は、顧客 A に公平ではありません。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p102">We take managing outbound spam seriously because ours is a shared service.  There are many customers behind a shared pool of resources, where if one customer sends outbound spam, it can degrade the outbound IP reputation of the service and affects the successful deliverability of email for other customers. It is unfair to Customer A if Customer B spams and various 3rd party IP blocklists list the IP address that it uses.</span></span>

## <a name="what-admins-can-do-to-control-outbound-spam"></a><span data-ttu-id="ba73c-108">迷惑メールの送信を制御するのには管理者が実行できます。</span><span class="sxs-lookup"><span data-stu-id="ba73c-108">What admins can do to control outbound spam</span></span>

- <span data-ttu-id="ba73c-p103">**アカウントがスパムを送信するか、シャット ダウンしたときに通知を有効に**します。管理者は、メッセージが送信スパムとしてマークされているし、危険度の高いプール経由で送信されるたびに、bcc'ed を取得できます。このメールボックスを監視することによって、管理者は、ネットワークのセキュリティを侵害されたアカウントを持っている場合、または迷惑メール フィルターが自分の電子メールをスパムとしてマークする誤っている場合を検出できます。 送信スパム ポリシーを設定する方法についてを参照して[ここで](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p103">**Enable notifications when an account is sending spam or shut down**. Administrators can get bcc’ed whenever a message is marked as outbound spam and sent through the High Risk pool. By monitoring this mailbox, an admin can detect if they have a compromised account in their network or if the spam filter is mistakenly marking their email as spam.  More information on setting up the outbound spam policy can be found [here](configure-the-outbound-spam-policy.md).</span></span>
 
- <span data-ttu-id="ba73c-p104">**サード パーティの電子メール プロバイダーからの迷惑メールの苦情を手動で確認**してください。Outlook.com、yahoo、AOL のようなサード パーティ メール サービスが多くは、迷惑メールとして弊社のサービスからのメール ・ サービスのすべてのユーザー場合は、メッセージ パッケージ化あり、私たちに送信する校閲用のフィードバックを提供します。Outlook.com の送信者のサポートの詳細についてをクリックして[ここ](https://sendersupport.olc.protection.outlook.com/pm/services.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p104">**Manually review spam complaints from 3rd party email providers**. Many 3rd party email services like Outlook.com, Yahoo and AOL provide a Feedback Loop where if any user in their service marks an email from our service as spam, the message is packaged up and sent back to us for review. To learn more about sender support for Outlook.com, click [here](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).</span></span>

## <a name="what-eop-does-to-control-outbound-spam"></a><span data-ttu-id="ba73c-116">EOP がスパムの送信を制御するのには</span><span class="sxs-lookup"><span data-stu-id="ba73c-116">What EOP does to control outbound spam</span></span> 

1. <span data-ttu-id="ba73c-p105">**Ip アドレスのプールを個別に発信トラフィックを分離**します。お客様がサービスを介して送信されるすべてのメッセージがスパムのスキャンされます。メッセージがスパムである場合は、高リスク配信プールを通じてルーティングされます。この IP プールには、配信不能状態の通知や迷惑メールが含まれています。多くのサード パーティを受け付けません e メール e メールの品質を出力するために、目的の受信者への配信は保証されません。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p105">**Segregation of outbound traffic into separate pools of IPs**. Every message that customers send outbound through the service is scanned for spam. If the message is spam, it is routed through the High Risk Delivery pool. This IP pool contains non-deliverable status notifications and spam. Delivery to the intended recipient is not guaranteed as many third parties will not accept email because the quality of email it emits.</span></span><br/><br/><span data-ttu-id="ba73c-p106">トラフィックをこのように分割は、低品質の電子メール (スパム、backscatter Ndr) が通常の送信電子メールのプールの評判をドラッグしないことを保証します。危険度の高いプールは、ユニバーサルではありませんが通常低評価と、インターネット上の多数の受信者には。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p106">Splitting the traffic this way ensures that the lower quality email (spam, backscatter NDRs) does not drag down the reputation of the regular outbound email pools. The high risk pool typically has low reputation at many receivers around the Internet, although this is not universal.</span></span> 

2. <span data-ttu-id="ba73c-p107">**IP の監視評価**します。Office 365 は、さまざまなサード パーティ製 IP ブロック リスト既にを照会し、それらに示されて、送信 ip アドレスのいずれかの場合にアラートを生成します。これにより、スパムが当社の評判を低下させる原因となったときに迅速に対処することができます。アラートが生成されると、ある内部ドキュメントの他除外されるを取得するためにどのような手順です。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p107">**Monitoring of IP reputation**. Office 365 queries various 3rd party IP blocklists and generates alerts if any of our outbound IPs are listed on them. This allows us to react quickly when spam has caused our reputation to degrade. When an alert is generated, we have internal documentation outlying what steps to take to get delisted.</span></span> 

3. <span data-ttu-id="ba73c-p108">**大量の電子メールを送信するときに問題のあるアカウントの無効化は、スパムとしてマーク**されます。スパムと 2 つの独立した送信 IP プールの非スパムを分離することも、電子メール アカウントではいつまでも迷惑メールを送信できません。監視するアカウントがスパムを送信して、非公開の制限値を超えている場合、アカウントがブロックされたスパムを送信します。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p108">**Disabling of offending accounts when they send too much email marked as spam**. Even though we segregate our spam and non-spam into two separate outbound IP pools,  the email accounts cannot send spam indefinitely. We monitor which accounts are sending spam and if it exceeds an undisclosed limit, the account is blocked from sending spam.</span></span><br/><br/><span data-ttu-id="ba73c-p109">1 つのメッセージには、迷惑メールが、スパムのエンジンとも呼ばれる誤検知する誤判別にすることがあるがマークされています。アウトの機会を与えることに危険度の高いプールを介した送信します。ただし、短時間でメッセージの数が多い問題と現象が発生する時期を示している可能性は、ブロックしますから、複数の電子メールを送信するアカウント。集計全体のテナントのようにも、個々 の電子メール アカウントに存在している別のしきい値があります。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p109">A single message marked as spam may be a misclassification by the spam engine and also known as a false positive. We send it through the High Risk pool to give it a chance of going out; however, a large number of messages in a short time frame is indicative of a problem and when that occurs, we block the account from sending any more email. There are different thresholds that exist for individual email accounts as well as in aggregate for the entire tenant.</span></span>

4. <span data-ttu-id="ba73c-p110">**短い時間で大量の電子メールを送信するときに問題のあるアカウントの無効化**します。スパムとしてマークされたメッセージの割合の表示上の制限、他のメッセージがスパムとしてマークされたかどうかに関係なく、全体の制限値に到達したときにアカウントをブロックするための制限もあります。この制限が存在する理由は、侵害されたアカウントがスパム フィルターによって失われている 0 日スパムを送信できなかったためにです。難しいので、場合によって正当なマス メール キャンペーンと大規模なスパム キャンペーンの間で違いを見分けることは、不可能の場合、任意の潜在的な損害を限定するのにはこれらの制限が有効にします。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p110">**Disabling of offending accounts when they send too much email in too short a time frame**. In addition to the limits above that look for a proportion of messages marked as spam, there are also limits that block accounts when they reach an overall limit regardless of whether or not the messages are marked as spam. The reason this limit exists is because a compromised account could send zero-day spam that is missed by the spam filter. Because it is difficult, if not impossible, to sometimes tell the difference between a legitimate mass mailing campaign and a massive spam campaign, these limits activate to limit any potential damage.</span></span>

> [!NOTE]
> <span data-ttu-id="ba73c-p111">3 と 4 の両方の正確な制限を公示しません。 これは、ゲーム システムからのスパムを防ぐためにしているように制限を変更できます。制限は、十分に高く、一般的なビジネス ユーザーがそれらをヒットしないように十分に低く、スパムの被害のほとんどが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p111">For both #3 and #4, we do not advertise the exact limits.  This is to prevent spammers from gaming the system and to ensure that we can change the limits when we need to. The limits are high enough such that an average business user will never hit them and low enough that it contains most of the damage a spammer can do.</span></span> 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a><span data-ttu-id="ba73c-141">EOP を介して電子メールの送信を希望お客様に対して推奨される回避策</span><span class="sxs-lookup"><span data-stu-id="ba73c-141">Recommended workarounds for customers who want to send outbound a lot of email through EOP</span></span>

<span data-ttu-id="ba73c-p112">大量のアカウントが危険にさらされたと低下] ボックスの一覧の取得・ プラクティスを発進からサービスを保護すると電子メールの送信を希望お客様の間でバランスをとることは困難です。もう一度、サード パーティのブロック リストに着陸、発信 IP のコストは、送信電子メールを送信することから顧客のブロックよりも高いです。[Exchange のオンライン サービスの説明](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits)で説明したとおり、EOP を使用して、一括メールではありませんを送信する、サポートされているサービスの使用し、「ベスト ・ エフォート」単位でのみ許可されていますいます。一括メール送信を希望お客様には、次のお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p112">It is difficult to strike a balance between customers who want to send a large volume of email vs. protecting the service from compromised accounts and bulk emailers with poor list acquisition practices. Again, the cost of an outbound IP landing on a 3rd party blocklist is higher than blocking a customer from sending outbound email. As described in the [Exchange Online Service Description](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits), using EOP to send bulk email is not a supported use of the service and is only permitted on a “best-effort” basis. For customers who do want to send bulk email, we recommend the following:</span></span>

1. <span data-ttu-id="ba73c-p113">**独自のオンプレミスのメール サーバーで一括メールを送信**します。これは、お客様がこの電子メールの種類の独自の電子メール インフラストラクチャを維持する必要ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p113">**Send the bulk email through its own on-premise mail servers**. This means that the customer will have to maintain its own email infrastructure for this type of email.</span></span>

2. <span data-ttu-id="ba73c-p114">**サードパーティの大容量の通信を送信するための一括メールを使用**します。いくつかサード パーティ製発進一括メールを送信することが唯一のビジネスがあります。お客様はきちんとメールがあることを強制するのには専用のリソースがあることを確認して、操作できます。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p114">**Use a 3rd party bulk emailer to send the mass communication**. There are several 3rd party bulk emailers whose sole business it is to send bulk email. They can work with customers to ensure that they have good emailing practices and they have resources dedicated to enforcing it.</span></span> 

<span data-ttu-id="ba73c-p115">そのメンバーシップの名簿を発行する、メッセージング、モバイル、マルウェア対策ソフトウェアの使用方法を間違えたワーキング グループ (MAAWG)[は、ここ](http://www.maawg.org/about/roster)です。いくつかの一括電子メール プロバイダー一覧に、インターネット市民の責任者として知られています。</span><span class="sxs-lookup"><span data-stu-id="ba73c-p115">The Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publishes its membership roster [here](http://www.maawg.org/about/roster). Several bulk email providers are on the list and are known to be responsible Internet citizens.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="ba73c-153">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ba73c-153">For more information</span></span>

[<span data-ttu-id="ba73c-154">送信者が送信スパムの送信をブロックされる場合の通知例</span><span class="sxs-lookup"><span data-stu-id="ba73c-154">Sample notification when a sender is blocked sending outbound spam</span></span>](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[<span data-ttu-id="ba73c-155">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="ba73c-155">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="ba73c-156">Office 365 でのスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="ba73c-156">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)

[<span data-ttu-id="ba73c-157">Spam Confidence Level</span><span class="sxs-lookup"><span data-stu-id="ba73c-157">Spam confidence levels</span></span>](spam-confidence-levels.md)
