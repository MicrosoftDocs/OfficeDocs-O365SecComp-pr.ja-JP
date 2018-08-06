---
title: IPv6 経由の匿名受信電子メール メッセージのサポート
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/4/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
description: Exchange オンライン保護 (EOP) および Exchange Online は、トランスポート層セキュリティ (TLS) 経由でメッセージを送信しないユーザーの送信者からの IPv6 通信経由の匿名の受信電子メール メッセージの受信をサポートします。ことができますオプトイン UNRESOLVED_TOKEN_VAL(exMCSS) から Office 365 の管理センターを開くことでこの機能を要求することによって、IPv6 経由でメッセージを受信するhttps://portal.office.com/adminportal/home、サポートをクリックし、新しいサービス要求) します。しないに IPv6 の場合、IPv4 経由でメッセージを受信する続行するでしょう。
ms.openlocfilehash: a07e79732e9027d5848b787101be11066b5f0cb5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026294"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="3d815-105">IPv6 経由の匿名受信電子メール メッセージのサポート</span><span class="sxs-lookup"><span data-stu-id="3d815-105">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="3d815-p102">Exchange Online Protection (EOP) および Exchange Online は、トランスポート層セキュリティ (TLS) 経由でメッセージを送信しない送信者からの IPv6 通信経由の匿名受信電子メール メッセージの受信をサポートしています。UNRESOLVED_TOKEN_VAL(exMCSS) にこの機能を要求する ([https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) の Office 365 管理センター を開き、 **[サポート]** をクリックし、 **[新しいサービス リクエスト]** をクリックする) ことによって、IPv6 経由でメッセージを受信するためにオプトインすることができます。IPv6 にオプトインしない場合は、引き続き、IPv4 経由でメッセージを受信することになります。</span><span class="sxs-lookup"><span data-stu-id="3d815-p102">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS). You can opt-in to receive messages over IPv6 by requesting this functionality from UNRESOLVED_TOKEN_VAL(exMCSS) by opening the Office 365 admin center at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home), clicking **Support**, and then clicking **New service request**). If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="3d815-109">IPv6 経由でメッセージをサービスに送信する送信者は、次の 2 つの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d815-109">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="3d815-110">送信 IPv6 アドレスに有効な PTR レコード (送信 IPv6 アドレスの [DNS 逆引きレコード](https://en.wikipedia.org/wiki/Reverse_DNS_lookup)) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d815-110">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="3d815-111">また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](http://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d815-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="3d815-p103">これらの要件は、どの構成を使用する場合でも IPv6 にオプトインする前に満たす必要があります。両方の要件が満たされている場合、メッセージはサービスによって提供される通常の電子メール メッセージ フィルタリングを通過します。どちらかの要件が満たされていない場合には、メッセージは次の 450 応答のいずれかで拒否されます。</span><span class="sxs-lookup"><span data-stu-id="3d815-p103">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6. If both requirements are met, the message will go through normal email message filtering provided by the service. If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="3d815-115">IPv6 経由でメッセージを受信するためにオプトインしていない状態で、送信者がメール サーバーに手動で接続することによって IPv6 経由のメッセージを強制しようとした場合には、メッセージは次のような 550 応答で拒否されます。</span><span class="sxs-lookup"><span data-stu-id="3d815-115">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="3d815-116">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3d815-116">For more information</span></span>

[<span data-ttu-id="3d815-117">DKIM 署名付きメッセージの検証をサポートする</span><span class="sxs-lookup"><span data-stu-id="3d815-117">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  

