---
title: 送信メッセージにおける危険度の高い配信プール
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/24/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
description: 顧客の電子メール システムがマルウェアまたは悪意のあるスパム攻撃によって侵害を受け、ホストされているフィルター サービスでスパムを送信していると、Office 365 データ センター サーバーの IP アドレスがサードパーティのブロック リストに表示されることがあります。
ms.openlocfilehash: 856db53b105379ea3e606e39bf3c2612afa803c3
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026624"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="aa50d-103">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="aa50d-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="aa50d-p101">顧客の電子メール システムがマルウェアまたは悪意のあるスパム攻撃によって侵害を受け、ホストされているフィルター サービスでスパムを送信していると、Office 365 データ センター サーバーの IP アドレスがサードパーティのブロック リストに表示されることがあります。ホストされているフィルター サービスは使用しなくても、このブロック リストを使用する宛先サーバーは、そのリストに追加された、ホストされているフィルター IP アドレスから送信されたすべての電子メールを拒否します。これを避けるために、スパムしきい値を超えるすべての送信メッセージが、危険度の高い配信プールで配信されます。この補助的な送信電子メール プールは、低品質になることがあるメッセージの送信にのみ使用されます。これは、送信 IP アドレスがブロックされる可能性が高いメッセージを残りのネットワークが送信しないように保護します。</span><span class="sxs-lookup"><span data-stu-id="aa50d-p101">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists. Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists. To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool. This secondary outbound email pool is only used to send messages that may be of low quality. This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="aa50d-p102">専用のより危険度の高い配信プールを使用すると、高品質であることがわかっているメッセージのみを通常の送信プールが送信するようになります。この補助的な IP プールを使用することにより、通常の送信 IP プールが禁止リストに追加される可能性が低くなります。より危険度の高い配信プールが禁止リストに含まれる危険性は残りますが、これは仕様です。</span><span class="sxs-lookup"><span data-stu-id="aa50d-p102">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality. Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list. The possibility of the high-risk delivery pool being placed on a blocked list remains a risk. This is by design.</span></span>
  
<span data-ttu-id="aa50d-113">送信側ドメインにアドレス レコード (A レコード、そのドメインの IP アドレスを提供する) がないメッセージ、および送信側ドメインに MX レコード (DNS に含まれる特定のドメインに対するメールを受信するサーバーへメールを送信するために役立つ) がないメッセージは、スパムの傾向に関係なく、常に危険度の高い配信プールでルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="aa50d-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="aa50d-114">カスタマイズ可能な配信状態通知 (DSN) メッセージについて</span><span class="sxs-lookup"><span data-stu-id="aa50d-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="aa50d-115">送信用の危険度の高い配信プールは、すべての「返送された」か「失敗した」かの (DSN) メッセージの配信を管理します。</span><span class="sxs-lookup"><span data-stu-id="aa50d-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="aa50d-116">DSN メッセージの急増の原因は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa50d-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="aa50d-117">サービスを使用しているいずれかの顧客に影響を与えるスプーフィング キャンペーン</span><span class="sxs-lookup"><span data-stu-id="aa50d-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="aa50d-118">ディレクトリ獲得攻撃</span><span class="sxs-lookup"><span data-stu-id="aa50d-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="aa50d-119">スパム攻撃</span><span class="sxs-lookup"><span data-stu-id="aa50d-119">A spam attack</span></span>
    
- <span data-ttu-id="aa50d-120">承認されていない SMTP サーバー</span><span class="sxs-lookup"><span data-stu-id="aa50d-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="aa50d-p103">これらのすべての問題により、サービスが処理する DSN メッセージの数が急増する結果となることがあります。多くの場合、このような DSN メッセージは、その他の電子メールサーバーやサービスのスパムとなることがあります。</span><span class="sxs-lookup"><span data-stu-id="aa50d-p103">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service. Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="aa50d-123">詳細情報</span><span class="sxs-lookup"><span data-stu-id="aa50d-123">For more information</span></span>

[<span data-ttu-id="aa50d-124">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="aa50d-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="aa50d-125">スパム対策の保護に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="aa50d-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

