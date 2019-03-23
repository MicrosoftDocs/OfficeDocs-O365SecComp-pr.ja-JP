---
title: トップドメインメールフローのステータスの洞察
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理者は、Office 365 Security & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインのメールフローの状態に関する洞察を得ることができます。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 04aa986982465a4c66fbf99f517fb34622d65e19
ms.sourcegitcommit: fec1010e405f14e792d650aee0312b78fced3343
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "30722959"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="e09fc-103">トップドメインメールフローのステータスの洞察</span><span class="sxs-lookup"><span data-stu-id="e09fc-103">Top domain mail flow status insight</span></span>

> [!NOTE]
> <span data-ttu-id="e09fc-104">このトピックで説明する機能は、すべての Office 365 組織に展開されていないため、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e09fc-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="e09fc-105">**上位ドメインのメールフローの状態**に関する情報は、メールフローの観点から、組織のドメインの現在の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="e09fc-105">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="e09fc-106">この洞察は、***メールフローに影響を与える***(たとえば、外部電子メールを受信できない) 問題が発生しているドメインを特定してトラブルシューティングするのに役立ちます。特に、ドメインの有効期限、または間違った MX レコードがあるドメイン。</span><span class="sxs-lookup"><span data-stu-id="e09fc-106">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Office 365 Security & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインフローの状態の洞察](media/domain-mail-flow-status-selected.png)

<span data-ttu-id="e09fc-108">[**詳細**] をクリックすると、各ドメインの状態の詳細が表示されるポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e09fc-108">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="e09fc-109">ドメインに緑のチェックマークが表示されている場合は、現在の MX レコード (メールフローインサイトダッシュボードを参照した場合) がレコードに設定されている値と一致し、ドメインが過去2時間以内に電子メールを受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="e09fc-109">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="e09fc-110">ドメインの赤色の x は、MX レコードが変更されており、過去6時間以内にドメインがメールを受信していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e09fc-110">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="e09fc-111">これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e09fc-111">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="e09fc-112">ドメインレジストラーまたは DNS ホスティングサービスを使用して、ドメインの有効期限が切れていないか、またはドメインの MX レコードが正しくないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e09fc-112">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![トップドメインフローの状態に関する詳細ポップアップ](media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a><span data-ttu-id="e09fc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e09fc-114">See also</span></span>

<span data-ttu-id="e09fc-115">メールフローダッシュボードの他のメールフローインサイトの詳細については、「 [Security &/コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e09fc-115">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>