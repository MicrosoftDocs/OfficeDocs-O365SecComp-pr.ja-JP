---
title: トップドメインのメール フローの状態洞察　
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある上位のドメインメールフローの状態について理解できます。
ms.openlocfilehash: c339769c65b2b1cec3d187873e71e5f1e283ccc7
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158649"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="c6ff9-103">トップドメインのメール フローの状態洞察　</span><span class="sxs-lookup"><span data-stu-id="c6ff9-103">Top domain mail flow status insight</span></span>

<span data-ttu-id="c6ff9-104">**上位ドメインのメールフローの状態**に関する情報は、メールフローの観点から、組織のドメインの現在の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="c6ff9-104">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="c6ff9-105">この洞察は、***メールフローに影響を与える***(たとえば、外部電子メールを受信できない) 問題が発生しているドメインを特定してトラブルシューティングするのに役立ちます。特に、ドメインの有効期限、または間違った MX レコードがあるドメイン。</span><span class="sxs-lookup"><span data-stu-id="c6ff9-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインフローの状態の洞察](media/domain-mail-flow-status-selected.png)

<span data-ttu-id="c6ff9-107">[**詳細**] をクリックすると、各ドメインの状態の詳細が表示されるポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6ff9-107">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="c6ff9-108">ドメインに緑のチェックマークが表示されている場合は、現在の MX レコード (メールフローインサイトダッシュボードを参照した場合) がレコードに設定されている値と一致し、ドメインが過去2時間以内に電子メールを受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ff9-108">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="c6ff9-109">ドメインの赤色の x は、MX レコードが変更されており、過去6時間以内にドメインがメールを受信していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ff9-109">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="c6ff9-110">これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c6ff9-110">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="c6ff9-111">ドメインレジストラーまたは DNS ホスティングサービスを使用して、ドメインの有効期限が切れていないか、またはドメインの MX レコードが正しくないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c6ff9-111">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![トップドメインフローの状態に関する詳細ポップアップ](media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a><span data-ttu-id="c6ff9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6ff9-113">See also</span></span>

<span data-ttu-id="c6ff9-114">メールフローダッシュボードの他のメールフローインサイトの詳細については、「 [Security &/コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6ff9-114">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
