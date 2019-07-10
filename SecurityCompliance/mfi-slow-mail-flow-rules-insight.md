---
title: 低速メール フローのルールのインサイト
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 5/3/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードに記載されている低速メールフロールールについて理解できます。
ms.openlocfilehash: 4477b388df321ee774ec7916a695cbfc69fc8e87
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598073"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="53a16-103">低速メール フローのルールのインサイト</span><span class="sxs-lookup"><span data-stu-id="53a16-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="53a16-104">非効率的なメールフロールール (トランスポートルールとも呼ばれます) は、組織のメールフロー遅延につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53a16-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="53a16-105">この洞察は、組織のメールフローに影響を与えるメールフロールールを報告します。</span><span class="sxs-lookup"><span data-stu-id="53a16-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="53a16-106">これらの種類のルールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="53a16-106">Examples of these types of rules are:</span></span>

- <span data-ttu-id="53a16-107">**が**大規模なグループの場合、を使用する条件。</span><span class="sxs-lookup"><span data-stu-id="53a16-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="53a16-108">複合正規表現 (regex) パターンマッチングを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="53a16-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="53a16-109">添付ファイルのコンテンツチェックを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="53a16-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="53a16-110">この洞察は、メールフローの遅延を減らすために、メールフロールールを特定し、微調整するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="53a16-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードに記載されている低速メールフロールールについての考察](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="53a16-112">[詳細の**表示**] をクリックすると、フライアウトウィンドウが表示され、ルールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="53a16-112">When you click **View details**, a flyout pane appears where you can review the rule.</span></span> <span data-ttu-id="53a16-113">また、フライアウトウィンドウで [**サンプルメッセージの表示**] をクリックして、ルールによって影響を受けたメッセージの種類を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="53a16-113">In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![メールフローダッシュボードの [低速メールフロールールの詳細を表示する] をクリックした後のフライアウトウィンドウ](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="see-also"></a><span data-ttu-id="53a16-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="53a16-115">See also</span></span>

<span data-ttu-id="53a16-116">メールフローダッシュボードのその他のメールフローインサイトの詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a16-116">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>
