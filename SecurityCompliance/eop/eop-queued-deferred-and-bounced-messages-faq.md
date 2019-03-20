---
title: EOP のキューイング、保留、返送されるメッセージに関する FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: ここでは、Microsoft Exchange Online Protection (EOP) のフィルター処理中にキューイング、保留、または返送されるメッセージに関してよく寄せられる質問の回答を提供します。
ms.openlocfilehash: e8fdb07d11a1f540e94b82730eb848a97f51523a
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693206"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="4a836-103">EOP のキューイング、保留、返送されるメッセージに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="4a836-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="4a836-104">ここでは、Microsoft Exchange Online Protection (EOP) のフィルター処理中にキューイング、保留、または返送されるメッセージに関してよく寄せられる質問の回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="4a836-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>
  
 <span data-ttu-id="4a836-105">**Q. なぜメールはキューイングされるのですか?**</span><span class="sxs-lookup"><span data-stu-id="4a836-105">**Q. Why is mail queuing?**</span></span>
  
<span data-ttu-id="4a836-p101">A. メール配信時に受信者のサーバーに接続できない場合、メッセージはキューイングされるか保留されます。ただし、受信者のネットワークから 500 番台のエラーが返された場合、メッセージは保留されません。</span><span class="sxs-lookup"><span data-stu-id="4a836-p101">A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.</span></span>
  
 <span data-ttu-id="4a836-109">**Q. メッセージはどのようなときに保留状態になるのですか?**</span><span class="sxs-lookup"><span data-stu-id="4a836-109">**Q. How does a message become deferred?**</span></span>
  
<span data-ttu-id="4a836-p102">A. 受信者のサーバーに接続できず、受信者のサーバーから接続タイムアウトや接続拒否、400 番台のエラーなどの "一時的なエラー" が返された場合、メッセージは保留されます。500 番台のエラーなどの永続的なエラーが返された場合、メッセージは送信者に戻されます。</span><span class="sxs-lookup"><span data-stu-id="4a836-p102">A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>
  
 <span data-ttu-id="4a836-113">**Q. メッセージが保留される期間と再試行の間隔はどのくらいですか?**</span><span class="sxs-lookup"><span data-stu-id="4a836-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>
  
<span data-ttu-id="4a836-114">A.</span><span class="sxs-lookup"><span data-stu-id="4a836-114">A.</span></span> <span data-ttu-id="4a836-115">保留状態のメッセージはキューに 2 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="4a836-115">Messages in deferral will remain in our queues for 2 days.</span></span> <span data-ttu-id="4a836-116">メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="4a836-116">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="4a836-117">最初のいくつかの deferrals は15分以内で、以降の再試行 (次の半周期以上) では、複数回の再試行の間隔が最大60分に増加します。</span><span class="sxs-lookup"><span data-stu-id="4a836-117">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="4a836-118">間隔の期間の展開は動的であり、キューのサイズや内部メッセージの優先度などの複数の変数を考慮します。</span><span class="sxs-lookup"><span data-stu-id="4a836-118">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="4a836-119">基本的には、15分 (またはそれ以下) から開始します。その後、次の数時間で最大60分に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="4a836-119">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>
  
 <span data-ttu-id="4a836-120">**Q. メール サーバーが復元された後、キューイングされたメッセージはどのように配信されますか?**</span><span class="sxs-lookup"><span data-stu-id="4a836-120">**Q. After your email server is restored, how are queued messages distributed?**</span></span>
  
<span data-ttu-id="4a836-p104">A. メール サーバーが復元した後、キューに格納されたすべてのメッセージは、サーバーを利用できなくなったときに受信およびキューに格納された順序で自動的に処理されます。</span><span class="sxs-lookup"><span data-stu-id="4a836-p104">A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span> 
  

