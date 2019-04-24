---
title: バルク苦情レベルの値
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: バルク メール業者によって、送信パターン、コンテンツ作成、およびリスト取得方法が異なります。 中には、関連コンテンツを含む、必要なメッセージをサブスクライバーに送信する優良なバルク メール業者もいます。 このようなメッセージが受信者の苦情につながることはあまりありません。 他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。 これらのバルク メール業者の種類を区別するために、バルク メール業者からのメッセージにバルク苦情レベル (BCL) 格付けが割り当てられます。 バルク メール業者のレベルに応じた 1 ～ 9 の BCL 格付け範囲が苦情を生み出す程度を表します。 BCL が 9 の送信者は受信者からの苦情が多い可能性があるのに対して、BCL が 3 の送信者は受信者からの苦情が少ない可能性があります。 Microsoft では、内部ソースとサード パーティ ソースの両方を使用して、バルク メールを識別し、適切な BCL を決定します。 この格付けは、すべてのメッセージの X-Microsoft-Antispam ヘッダーで公開されます。 このメッセージ ヘッダーの詳細については、「 スパム対策メッセージ ヘッダー」を参照してください。
ms.openlocfilehash: e6d639098adc8c29b09b186ff72e38c5f5ac4e81
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243818"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="a2522-112">バルク苦情レベルの値</span><span class="sxs-lookup"><span data-stu-id="a2522-112">Bulk Complaint Level values</span></span>

<span data-ttu-id="a2522-p102">バルク メール業者によって、送信パターン、コンテンツ作成、およびリスト取得方法が異なります。中には、関連コンテンツを含む、必要なメッセージをサブスクライバーに送信する優良なバルク メール業者もいます。このようなメッセージが受信者の苦情につながることはあまりありません。他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。これらのバルク メール業者の種類を区別するために、バルク メール業者からのメッセージにバルク苦情レベル (BCL) 格付けが割り当てられます。バルク メール業者のレベルに応じた 1 ～ 9 の BCL 格付け範囲が苦情を生み出す程度を表します。BCL が 9 の送信者は受信者からの苦情が多い可能性があるのに対して、BCL が 3 の送信者は受信者からの苦情が少ない可能性があります。Microsoft では、内部ソースとサード パーティ ソースの両方を使用して、バルク メールを識別し、適切な BCL を決定します。この格付けは、すべてのメッセージの **X-Microsoft-Antispam** ヘッダーで公開されます。このメッセージ ヘッダーの詳細については、「 [スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2522-p102">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices. Some are good bulk mailers that send wanted messages with relevant content to their subscribers. These messages generate few complaints from recipients. Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients. To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating. BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints. A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints. Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL. This rating is exposed in the **X-Microsoft-Antispam** header of every message. For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
<span data-ttu-id="a2522-123">BCL 値を使用して組織に必要なバルク フィルタリング レベルを設定するには、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="a2522-123">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="a2522-p103">より多くの BCL 値が追加されており、将来的にここに含まれます。次の表に、現在使用されている BCL 値とその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="a2522-p103">More BCL values are being added and will be included here in the future. The following table lists and describes the BCL values that are currently in use.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a2522-126">**BCL 値**</span><span class="sxs-lookup"><span data-stu-id="a2522-126">**BCL Value**</span></span> <br/> |<span data-ttu-id="a2522-127">**説明**</span><span class="sxs-lookup"><span data-stu-id="a2522-127">**Description**</span></span> <br/> |
|<span data-ttu-id="a2522-128">.0</span><span class="sxs-lookup"><span data-stu-id="a2522-128">0</span></span>  <br/> |<span data-ttu-id="a2522-129">バルク送信者からのメッセージではありません。</span><span class="sxs-lookup"><span data-stu-id="a2522-129">The message isn't from a bulk sender.</span></span>  <br/> |
|<span data-ttu-id="a2522-130">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="a2522-130">1, 2, 3</span></span>  <br/> |<span data-ttu-id="a2522-131">苦情がほとんどないバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="a2522-131">The message is from a bulk sender that generates few complaints.</span></span>  <br/> |
|<span data-ttu-id="a2522-132">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="a2522-132">4, 5, 6, 7</span></span>  <br/> |<span data-ttu-id="a2522-133">苦情の件数がさまざまなバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="a2522-133">The message is from a bulk sender that generates a mixed number of complaints.</span></span>  <br/> |
|<span data-ttu-id="a2522-134">8, 9</span><span class="sxs-lookup"><span data-stu-id="a2522-134">8, 9</span></span>  <br/> |<span data-ttu-id="a2522-135">苦情の件数が最も多いバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="a2522-135">The message is from a bulk sender that generates a high number of complaints</span></span>  <br/> |
   

