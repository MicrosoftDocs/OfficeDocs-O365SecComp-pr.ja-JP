---
title: 低速メール フローのルールのインサイト
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 5/3/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードに表示される低速メールフロールールについて理解できます。
ms.openlocfilehash: 1adbae56bfcf022250b66bac2f3bfd01a7f13234
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158589"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="5c1f7-103">低速メール フローのルールのインサイト</span><span class="sxs-lookup"><span data-stu-id="5c1f7-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="5c1f7-104">非効率的なメールフロールール (トランスポートルールとも呼ばれます) は、組織のメールフロー遅延につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c1f7-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="5c1f7-105">この洞察は、組織のメールフローに影響を与えるメールフロールールを報告します。</span><span class="sxs-lookup"><span data-stu-id="5c1f7-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="5c1f7-106">これらの種類のルールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5c1f7-106">Examples of these types of rules are:</span></span>

- <span data-ttu-id="5c1f7-107">**が**大規模なグループの場合、を使用する条件。</span><span class="sxs-lookup"><span data-stu-id="5c1f7-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="5c1f7-108">複合正規表現 (regex) パターンマッチングを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="5c1f7-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="5c1f7-109">添付ファイルのコンテンツチェックを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="5c1f7-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="5c1f7-110">この洞察は、メールフローの遅延を減らすために、メールフロールールを特定し、微調整するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5c1f7-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードに記載されている低速メールフロールールについての理解](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="5c1f7-112">[詳細の**表示**] をクリックすると、フライアウトウィンドウが表示され、ルールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5c1f7-112">When you click **View details**, a flyout pane appears where you can review the rule.</span></span> <span data-ttu-id="5c1f7-113">また、フライアウトウィンドウで [**サンプルメッセージの表示**] をクリックして、ルールによって影響を受けたメッセージの種類を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="5c1f7-113">In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![メールフローダッシュボードの [低速メールフロールールの詳細を表示する] をクリックした後のフライアウトウィンドウ](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="see-also"></a><span data-ttu-id="5c1f7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c1f7-115">See also</span></span>

<span data-ttu-id="5c1f7-116">メールフローダッシュボードの他のメールフローインサイトの詳細については、「 [Security &/コンプライアンスセンター」の「mail flow insights](mail-flow-insights.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c1f7-116">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>
