---
title: IPv6 経由の匿名受信電子メール メッセージのサポート
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: exchange online Protection および exchange online の IPv6 ソースからの匿名メッセージのサポートを構成する方法について説明します。
ms.openlocfilehash: 229ee045d03b3fa4ccb7b4d5e59e1b2b7df6a7d7
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276357"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="0840a-103">IPv6 経由の匿名受信電子メール メッセージのサポート</span><span class="sxs-lookup"><span data-stu-id="0840a-103">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="0840a-104">Exchange Online Protection (EOP) および Exchange Online は、トランスポート層セキュリティ (TLS) 経由でメッセージを送信しない送信者からの IPv6 通信経由の匿名受信電子メール メッセージの受信をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0840a-104">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS).</span></span> <span data-ttu-id="0840a-105">この機能を Microsoft サポートから要求することにより[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)、IPv6 経由でメッセージを受信することができます。そのためには、Office 365 管理センターを開き、[**サポート**] をクリックしてから、[**新しいサービスリクエスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0840a-105">You can opt-in to receive messages over IPv6 by requesting this functionality from Microsoft Support by opening the Office 365 admin center at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home), clicking **Support**, and then clicking **New service request**).</span></span> <span data-ttu-id="0840a-106">IPv6 にオプトインしない場合は、引き続き、IPv4 経由でメッセージを受信することになります。</span><span class="sxs-lookup"><span data-stu-id="0840a-106">If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="0840a-107">IPv6 経由でメッセージをサービスに送信する送信者は、次の 2 つの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="0840a-107">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="0840a-108">送信 IPv6 アドレスに有効な PTR レコード (送信 IPv6 アドレスの [DNS 逆引きレコード](https://en.wikipedia.org/wiki/Reverse_DNS_lookup)) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0840a-108">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="0840a-109">また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](http://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0840a-109">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="0840a-p102">これらの要件は、どの構成を使用する場合でも IPv6 にオプトインする前に満たす必要があります。両方の要件が満たされている場合、メッセージはサービスによって提供される通常の電子メール メッセージ フィルタリングを通過します。どちらかの要件が満たされていない場合には、メッセージは次の 450 応答のいずれかで拒否されます。</span><span class="sxs-lookup"><span data-stu-id="0840a-p102">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6. If both requirements are met, the message will go through normal email message filtering provided by the service. If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="0840a-113">IPv6 経由でメッセージを受信するためにオプトインしていない状態で、送信者がメール サーバーに手動で接続することによって IPv6 経由のメッセージを強制しようとした場合には、メッセージは次のような 550 応答で拒否されます。</span><span class="sxs-lookup"><span data-stu-id="0840a-113">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="0840a-114">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0840a-114">For more information</span></span>

[<span data-ttu-id="0840a-115">DKIM 署名付きメッセージの検証をサポートする</span><span class="sxs-lookup"><span data-stu-id="0840a-115">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  

