---
title: バックスキャター メッセージと EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: backscatter メッセージは、通常、スパムの受信の結果としてメールサーバーによって送信される自動バウンスメッセージです。バックスキャター dnsbl は、バック散布メッセージを送信する IP アドレスのリストです。スパム送信者のリストではないため、バックスキャター dnsbl からサーバーを削除しようとしていません。
ms.openlocfilehash: 075200ff85762056290690f40d6047ea25a1dbde
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222776"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="cb16c-105">バックスキャター メッセージと EOP</span><span class="sxs-lookup"><span data-stu-id="cb16c-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="cb16c-p102">バックスキャター メッセージは、通常、スパムを受信した結果としてメール サーバーから送信される自動バウンス メッセージです。Exchange Online Protection (EOP) はスパム フィルタリング サービスのため、存在しない受信者やその他の疑わしい宛先への電子メール メッセージがこのサービスによって拒否されます。これが発生すると、EOP が配信不能レポート (NDR) メッセージを生成して、「送信者」に配信します。スパム送信者はメッセージ内で偽造したまたは無効な "差出人" アドレスを使用することが多いため、NDR が送信される送信者アドレスが原因でバックスキャター メッセージになる場合があります。この場合は、EOP ネットワークに関連付けられた送信サーバーがバックスキャター DNS 禁止リスト (DNSBL) に掲載される可能性があります。バックスキャター DNSBL はバックスキャター メッセージを送信する IP アドレスのリストです。スパム送信者のリストではないため、掲載されたサーバーがバックスキャター DNSBL から削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cb16c-p102">Backscatter messages are the automated bounce messages that are sent by mail servers, typically as a result of incoming spam. Because Exchange Online Protection (EOP) is a spam filtering service, email messages sent to nonexistent recipients and to other suspicious destinations are rejected by our service. When this happens, EOP generates a non-delivery report (NDR) message and delivers it back to the "sender." Because spammers frequently use a forged or invalid "From" address in their messages, the sender address to which the NDR is sent may result in a backscatter message. When this happens, outgoing servers that are associated with the EOP network may be listed on the Backscatterer DNS Block List (DNSBL). The Backscatterer DNSBL is a list of IP addresses that send backscatter messages. It isn't a spammer list, and we don't try to remove our servers from the Backscatterer DNSBL.</span></span> 
  
> [!TIP]
> <span data-ttu-id="cb16c-p103">バックスキャター Web サイト上の説明によれば、すべての受信メールに対する拒否モードの使用はそのサービスの構成または使用として推奨されていません。代わりに、セーフ モードで使用する必要があります。正しいバックスキャター構成の実装方法については、「[Backscatterer.org Web サイト](http://www.backscatterer.org/?target=usage)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb16c-p103">According to the instructions on the Backscatterer website, the use of reject mode for all incoming mail isn't a recommended configuration or use of that service. It should be used in safe mode instead. For more information about implementing the correct backscatter configuration, visit the [Backscatterer.org website](http://www.backscatterer.org/?target=usage).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="cb16c-116">詳細情報</span><span class="sxs-lookup"><span data-stu-id="cb16c-116">For more information</span></span>

[<span data-ttu-id="cb16c-117">Backscatterer.org IP 一覧</span><span class="sxs-lookup"><span data-stu-id="cb16c-117">The Backscatterer.org IP list</span></span>](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
<span data-ttu-id="cb16c-118">「 [Advanced spam filtering options](advanced-spam-filtering-asf-options.md) 」の「NDR backscatter」エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb16c-118">See the "NDR backscatter" entry in [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md)</span></span>
  

