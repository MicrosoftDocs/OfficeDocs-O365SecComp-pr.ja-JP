---
title: EOP のキューイング、保留、返送されるメッセージに関する FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: ここでは、Microsoft Exchange Online Protection (EOP) のフィルター処理中にキューイング、保留、または返送されるメッセージに関してよく寄せられる質問の回答を提供します。
ms.openlocfilehash: 17e5955195c4e38299712fb9161822984b2a643a
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026224"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="3bdc2-103">EOP のキューイング、保留、返送されるメッセージに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="3bdc2-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="3bdc2-104">ここでは、Microsoft Exchange Online Protection (EOP) のフィルター処理中にキューイング、保留、または返送されるメッセージに関してよく寄せられる質問の回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="3bdc2-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>
  
 <span data-ttu-id="3bdc2-105">**Q. なぜメールはキューイングされるのですか?**</span><span class="sxs-lookup"><span data-stu-id="3bdc2-105">**Q. Why is mail queuing?**</span></span>
  
<span data-ttu-id="3bdc2-p101">A. メール配信時に受信者のサーバーに接続できない場合、メッセージはキューイングされるか保留されます。ただし、受信者のネットワークから 500 番台のエラーが返された場合、メッセージは保留されません。</span><span class="sxs-lookup"><span data-stu-id="3bdc2-p101">A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.</span></span>
  
 <span data-ttu-id="3bdc2-109">**Q. メッセージはどのようなときに保留状態になるのですか?**</span><span class="sxs-lookup"><span data-stu-id="3bdc2-109">**Q. How does a message become deferred?**</span></span>
  
<span data-ttu-id="3bdc2-p102">A. 受信者のサーバーに接続できず、受信者のサーバーから接続タイムアウトや接続拒否、400 番台のエラーなどの "一時的なエラー" が返された場合、メッセージは保留されます。500 番台のエラーなどの永続的なエラーが返された場合、メッセージは送信者に戻されます。</span><span class="sxs-lookup"><span data-stu-id="3bdc2-p102">A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>
  
 <span data-ttu-id="3bdc2-113">**Q. メッセージが保留される期間と再試行の間隔はどのくらいですか?**</span><span class="sxs-lookup"><span data-stu-id="3bdc2-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>
  
<span data-ttu-id="3bdc2-p103">A. 保留状態のメッセージはキューに 2 日間保持されます。メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。平均では、5 分ごとにメッセージの送信が再試行されます。</span><span class="sxs-lookup"><span data-stu-id="3bdc2-p103">A. Messages in deferral will remain in our queues for 2 days. Message retry attempts are based on the error we get back from the recipient's mail system. On average, messages are retried every 5 minutes.</span></span>
  
 <span data-ttu-id="3bdc2-118">**Q. メール サーバーが復元された後、キューイングされたメッセージはどのように配信されますか?**</span><span class="sxs-lookup"><span data-stu-id="3bdc2-118">**Q. After your email server is restored, how are queued messages distributed?**</span></span>
  
<span data-ttu-id="3bdc2-p104">A. メール サーバーが復元した後、キューに格納されたすべてのメッセージは、サーバーを利用できなくなったときに受信およびキューに格納された順序で自動的に処理されます。</span><span class="sxs-lookup"><span data-stu-id="3bdc2-p104">A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span> 
  

