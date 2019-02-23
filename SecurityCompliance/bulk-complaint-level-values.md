---
title: バルク苦情レベルの値
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: バルクメール広告は、送信中の pa tterns、コンテンツ作成、およびリスト取得の方法によって異なります。適切なバルクメールを使用して、必要なコンテンツを含むメッセージをサブスクライバーに送信することができます。これらのメッセージは、受信者からの苦情をほとんど発生しません。その他のバルクメール広告は、スパムによく似た迷惑メールを送信し、受信者に多数の苦情を生成します。これらの種類のバルクメール広告を区別するために、バルクメール業者からのメッセージにバルク苦情レベル (BCL) 格付けが割り当てられます。BCL の評価範囲は、バルクメーラーが苦情を生成する頻度に応じて、1から9の範囲で指定します。bcl 9 の評価を受けている送信者は、受信者からの苦情を多く発生させる可能性がありますが、bcl 3 の評価は多くの苦情を生み出していることはほとんどありません。Microsoft では、内部ソースとサードパーティソースの両方を使用して、バルクメールを識別し、適切な BCL を決定します。この評価は、すべてのメッセージのスパム対策ヘッダーで公開されます。このメッセージヘッダーの詳細については、「スパム対策メッセージヘッダー」を参照してください。
ms.openlocfilehash: 9947c0f36681126748e8617d67116c6932209760
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222926"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="82f9a-112">バルク苦情レベルの値</span><span class="sxs-lookup"><span data-stu-id="82f9a-112">Bulk Complaint Level values</span></span>

<span data-ttu-id="82f9a-p102">バルク メール業者によって、送信パターン、コンテンツ作成、およびリスト取得方法が異なります。中には、関連コンテンツを含む、必要なメッセージをサブスクライバーに送信する優良なバルク メール業者もいます。このようなメッセージが受信者の苦情につながることはあまりありません。他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。これらのバルク メール業者の種類を区別するために、バルク メール業者からのメッセージにバルク苦情レベル (BCL) 格付けが割り当てられます。バルク メール業者のレベルに応じた 1 ～ 9 の BCL 格付け範囲が苦情を生み出す程度を表します。BCL が 9 の送信者は受信者からの苦情が多い可能性があるのに対して、BCL が 3 の送信者は受信者からの苦情が少ない可能性があります。Microsoft では、内部ソースとサード パーティ ソースの両方を使用して、バルク メールを識別し、適切な BCL を決定します。この格付けは、すべてのメッセージの **X-Microsoft-Antispam** ヘッダーで公開されます。このメッセージ ヘッダーの詳細については、「 [スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82f9a-p102">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices. Some are good bulk mailers that send wanted messages with relevant content to their subscribers. These messages generate few complaints from recipients. Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients. To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating. BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints. A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints. Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL. This rating is exposed in the **X-Microsoft-Antispam** header of every message. For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
<span data-ttu-id="82f9a-123">BCL 値を使用して組織に必要なバルク フィルタリング レベルを設定するには、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="82f9a-123">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="82f9a-p103">より多くの BCL 値が追加されており、将来的にここに含まれます。次の表に、現在使用されている BCL 値とその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="82f9a-p103">More BCL values are being added and will be included here in the future. The following table lists and describes the BCL values that are currently in use.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="82f9a-126">**BCL 値**</span><span class="sxs-lookup"><span data-stu-id="82f9a-126">**BCL Value**</span></span> <br/> |<span data-ttu-id="82f9a-127">**説明**</span><span class="sxs-lookup"><span data-stu-id="82f9a-127">**Description**</span></span> <br/> |
|<span data-ttu-id="82f9a-128">.0</span><span class="sxs-lookup"><span data-stu-id="82f9a-128">0</span></span>  <br/> |<span data-ttu-id="82f9a-129">バルク送信者からのメッセージではありません。</span><span class="sxs-lookup"><span data-stu-id="82f9a-129">The message isn't from a bulk sender.</span></span>  <br/> |
|<span data-ttu-id="82f9a-130">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="82f9a-130">1, 2, 3</span></span>  <br/> |<span data-ttu-id="82f9a-131">苦情がほとんどないバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="82f9a-131">The message is from a bulk sender that generates few complaints.</span></span>  <br/> |
|<span data-ttu-id="82f9a-132">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="82f9a-132">4, 5, 6, 7</span></span>  <br/> |<span data-ttu-id="82f9a-133">苦情の件数がさまざまなバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="82f9a-133">The message is from a bulk sender that generates a mixed number of complaints.</span></span>  <br/> |
|<span data-ttu-id="82f9a-134">8, 9</span><span class="sxs-lookup"><span data-stu-id="82f9a-134">8, 9</span></span>  <br/> |<span data-ttu-id="82f9a-135">苦情の件数が最も多いバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="82f9a-135">The message is from a bulk sender that generates a high number of complaints</span></span>  <br/> |
   

