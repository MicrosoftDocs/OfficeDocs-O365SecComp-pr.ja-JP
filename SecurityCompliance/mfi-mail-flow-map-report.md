---
title: メール フローのマップ レポート
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローのダッシュボードにあるメールフローマップレポートの詳細を確認できます。
ms.openlocfilehash: 04ffbdc339a084f3ae2bf9947469966f1a868d02
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35601024"
---
# <a name="mail-flow-map-report"></a><span data-ttu-id="1f0f9-103">メール フローのマップ レポート</span><span class="sxs-lookup"><span data-stu-id="1f0f9-103">Mail flow map report</span></span>

<span data-ttu-id="1f0f9-104">このレポートでは、Office 365 組織を通過するメールの流れについての説明が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-104">This report gives insights as to how mail flows through your Office 365 organization.</span></span> <span data-ttu-id="1f0f9-105">この情報を使用して、パターンを学習し、異常を特定し、発生した問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-105">You can use this information to learn patterns, identify anomalies, and fix issues as they arise.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードのメールフローマップレポート](media/mail-flow-map-selected.png)

## <a name="mail-flow-map-widget"></a><span data-ttu-id="1f0f9-107">メールフローマップウィジェット</span><span class="sxs-lookup"><span data-stu-id="1f0f9-107">Mail flow map widget</span></span>

<span data-ttu-id="1f0f9-108">既定では、メールフローマップは、前日からの高レベルのメールフローパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-108">By default, the mail flow map shows the high level mail flow pattern from the previous day.</span></span> <span data-ttu-id="1f0f9-109">さまざまな日の左矢印と右矢印を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-109">You can use the left and right arrows for different days.</span></span> <span data-ttu-id="1f0f9-110">レポートの各領域の上にマウスカーソルを移動すると、次の図に示すように、Office 365 組織との間のメールの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-110">Hovering your mouse cursor over each area in the report will show the volume of mail to and from your Office 365 organization as shown in the following diagram:</span></span>

![メールフローマップウィジェットの左および右の矢印](media/mail-flow-map-widget.png)

## <a name="overview"></a><span data-ttu-id="1f0f9-112">概要</span><span class="sxs-lookup"><span data-stu-id="1f0f9-112">Overview</span></span>

<span data-ttu-id="1f0f9-113">**メールフローマップ**ウィジェットをクリックすると、**メールフローマップ**レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-113">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span> <span data-ttu-id="1f0f9-114">詳細なレポートを表示するには、[詳細データの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-114">Here you can see more granular level of report, you can click View details table to see detailed data.</span></span> <span data-ttu-id="1f0f9-115">[要求レポート] をクリックして詳細レポートをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-115">You can also download the detailed report by clicking Request report.</span></span>

![メールフローマップレポートの概要ビュー](media/mail-flow-map-overview.png)

## <a name="details"></a><span data-ttu-id="1f0f9-117">詳細</span><span class="sxs-lookup"><span data-stu-id="1f0f9-117">Details</span></span>

<span data-ttu-id="1f0f9-118">既定では、[**データの表示]** は値の**概要**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-118">By default, **Show data for** is set to the value **Overview**.</span></span> <span data-ttu-id="1f0f9-119">ドロップダウンをクリックして [ **detail**] を選択すると、ビューはドメインレベルの詳細に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-119">When you click on the drop down and select **Detail**, the view switches to the domain level detail.</span></span>

![メールフローマップレポートの概要表示での [データの表示] での詳細の選択](media/mail-flow-map-select-detail.png)

<span data-ttu-id="1f0f9-121">次の図に示すように、上位の送信者と受信者のドメインが表示され、残りは**他のユーザー**に配置されます。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-121">The top sender and recipient domains are listed, and the rest will be put in **Others** as shown in the following diagrams:</span></span>

![メールフローマップレポートの詳細表示](media/mail-flow-map-detail.png)

## <a name="related-insights"></a><span data-ttu-id="1f0f9-123">関連する分析情報</span><span class="sxs-lookup"><span data-stu-id="1f0f9-123">Related insights</span></span>

<span data-ttu-id="1f0f9-124">関連する洞察は、使用可能な場合はメールフローマップの下に表示されます (たとえば、送信者のドメインの洞察やメールループの洞察など)。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-124">Related insights are shown beneath the Mail flow map if they're available (for example, the Sender domain insight or the Mail loop insight).</span></span>

## <a name="see-also"></a><span data-ttu-id="1f0f9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f0f9-125">See also</span></span>

<span data-ttu-id="1f0f9-126">メールフローダッシュボードのその他のメールフローインサイトの詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f0f9-126">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>