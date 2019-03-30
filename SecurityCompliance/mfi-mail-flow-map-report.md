---
title: メールフローマップレポート
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理者は、Security & コンプライアンスセンターのメールフローのダッシュボードにあるメールフローマップレポートについて理解できます。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bd05ff5cb78adb9dd89dbe3f69c2c3a78d2b1df9
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001140"
---
# <a name="mail-flow-map-report"></a><span data-ttu-id="11687-103">メールフローマップレポート</span><span class="sxs-lookup"><span data-stu-id="11687-103">Mail flow map report</span></span>

> [!NOTE]
> <span data-ttu-id="11687-104">このトピックで説明する機能は、すべての Office 365 組織に展開されていないため、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11687-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="11687-105">このレポートでは、Office 365 組織を通過するメールの流れについての説明が提供されます。</span><span class="sxs-lookup"><span data-stu-id="11687-105">This report gives insights as to how mail flows through your Office 365 organization.</span></span> <span data-ttu-id="11687-106">この情報を使用して、パターンを学習し、異常を特定し、発生した問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="11687-106">You can use this information to learn patterns, identify anomalies, and fix issues as they arise.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードのメールフローマップレポート](media/mail-flow-map-selected.png)

## <a name="mail-flow-map-widget"></a><span data-ttu-id="11687-108">メールフローマップウィジェット</span><span class="sxs-lookup"><span data-stu-id="11687-108">Mail flow map widget</span></span>

<span data-ttu-id="11687-109">既定では、メールフローマップは、前日からの高レベルのメールフローパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="11687-109">By default, the mail flow map shows the high level mail flow pattern from the previous day.</span></span> <span data-ttu-id="11687-110">さまざまな日の左矢印と右矢印を使用できます。</span><span class="sxs-lookup"><span data-stu-id="11687-110">You can use the left and right arrows for different days.</span></span> <span data-ttu-id="11687-111">レポートの各領域の上にマウスカーソルを移動すると、次の図に示すように、Office 365 組織との間のメールの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11687-111">Hovering your mouse cursor over each area in the report will show the volume of mail to and from your Office 365 organization as shown in the following diagram:</span></span>

![メールフローマップウィジェットの左および右の矢印](media/mail-flow-map-widget.png)

## <a name="overview"></a><span data-ttu-id="11687-113">概要</span><span class="sxs-lookup"><span data-stu-id="11687-113">Overview</span></span>

<span data-ttu-id="11687-114">**メールフローマップ**ウィジェットをクリックすると、**メールフローマップ**レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11687-114">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span> <span data-ttu-id="11687-115">詳細なレポートを表示するには、[詳細データの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11687-115">Here you can see more granular level of report, you can click View details table to see detailed data.</span></span> <span data-ttu-id="11687-116">[要求レポート] をクリックして詳細レポートをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="11687-116">You can also download the detailed report by clicking Request report.</span></span>

![メールフローマップレポートの概要ビュー](media/mail-flow-map-overview.png)

## <a name="details"></a><span data-ttu-id="11687-118">詳細</span><span class="sxs-lookup"><span data-stu-id="11687-118">Details</span></span>

<span data-ttu-id="11687-119">既定では、[**データの表示]** は値の**概要**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="11687-119">By default, **Show data for** is set to the value **Overview**.</span></span> <span data-ttu-id="11687-120">ドロップダウンをクリックして [ **detail**] を選択すると、ビューはドメインレベルの詳細に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="11687-120">When you click on the drop down and select **Detail**, the view switches to the domain level detail.</span></span>

![メールフローマップレポートの概要表示での [データの表示] での詳細の選択](media/mail-flow-map-select-detail.png)

<span data-ttu-id="11687-122">次の図に示すように、上位の送信者と受信者のドメインが表示され、残りは**他のユーザー**に配置されます。</span><span class="sxs-lookup"><span data-stu-id="11687-122">The top sender and recipient domains are listed, and the rest will be put in **Others** as shown in the following diagrams:</span></span>

![メールフローマップレポートの詳細表示](media/mail-flow-map-detail.png)

## <a name="related-insights"></a><span data-ttu-id="11687-124">関連する分析情報</span><span class="sxs-lookup"><span data-stu-id="11687-124">Related insights</span></span>

<span data-ttu-id="11687-125">関連する洞察は、使用可能な場合はメールフローマップの下に表示されます (たとえば、送信者のドメインの洞察やメールループの洞察など)。</span><span class="sxs-lookup"><span data-stu-id="11687-125">Related insights are shown beneath the Mail flow map if they're available (for example, the Sender domain insight or the Mail loop insight).</span></span>

## <a name="see-also"></a><span data-ttu-id="11687-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="11687-126">See also</span></span>

<span data-ttu-id="11687-127">メールフローダッシュボードの他のメールフローインサイトの詳細については、「 [Security &/コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11687-127">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>