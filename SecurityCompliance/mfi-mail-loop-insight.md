---
title: メールループの分析情報
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
description: 管理者は、Security & コンプライアンスセンターのメールフローダッシュボードにあるメールループについて理解できます。
ms.openlocfilehash: 7229f8ebfc9ca1a46d91acc210199a3a6002c01e
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000320"
---
# <a name="mail-loop-insight"></a><span data-ttu-id="c307f-103">メールループの分析情報</span><span class="sxs-lookup"><span data-stu-id="c307f-103">Mail loop insight</span></span>

<span data-ttu-id="c307f-104">メールループは、システムリソースが浪費され、組織のメールボリュームクォータを使用して、元の送信者に (ndr またはバウンスメッセージとも呼ばれる) 混乱しない配信不能レポートを送信するため、不正です。</span><span class="sxs-lookup"><span data-stu-id="c307f-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span> <span data-ttu-id="c307f-105">この洞察は、組織内でメールループが検出されたとき、ループに含まれる電子メールドメイン、およびループ内の前日からのメッセージ数について報告します。</span><span class="sxs-lookup"><span data-stu-id="c307f-105">This insight reports when a mail loop is found in your organization, the email domains that are involved in the loop, and the number of messages from the previous day that were in the loop.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードにあるメールループの洞察](media/c3f707cb-4c89-4e88-989c-81ce1d1d6b99.png)

<span data-ttu-id="c307f-107">[詳細の**表示**] をクリックすると、フライアウトウィンドウに詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c307f-107">You can click **View details** to see the details in a flyout pane.</span></span> <span data-ttu-id="c307f-108">また、最も一般的なループシナリオを特定し、そのループを修正するために推奨されるアクション (使用可能な場合) を提供します。</span><span class="sxs-lookup"><span data-stu-id="c307f-108">We also identify the most common loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![メールフローダッシュボードの [詳細を表示] ループをクリックした後のフライアウトウィンドウ](media/f7e21300-c62f-41ec-853f-4a2775cd8aa7.png)

## <a name="see-also"></a><span data-ttu-id="c307f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c307f-110">See also</span></span>

<span data-ttu-id="c307f-111">メールフローダッシュボードの他のメールフローインサイトの詳細については、「 [Security &/コンプライアンスセンター」の「mail flow insights](mail-flow-insights.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c307f-111">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>
