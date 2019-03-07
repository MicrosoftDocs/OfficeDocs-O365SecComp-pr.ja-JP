---
title: 低速メール フローのルールの分析情報
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 5/3/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: 管理者は、Office 365 Security & コンプライアンスセンターのメールフローダッシュボードに記載されている低速メールフロールールについて理解できます。
ms.openlocfilehash: 8188ee0da15ac337499866783ca4f2d893062d5b
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454879"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="d239f-103">低速メール フローのルールの分析情報</span><span class="sxs-lookup"><span data-stu-id="d239f-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="d239f-104">非効率的なメールフロールール (トランスポートルールとも呼ばれます) は、組織のメールフロー遅延につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d239f-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="d239f-105">この洞察は、組織のメールフローに影響を与えるメールフロールールを報告します。</span><span class="sxs-lookup"><span data-stu-id="d239f-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="d239f-106">これらの種類のルールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d239f-106">Examples of these types of rules are:</span></span>

- <span data-ttu-id="d239f-107">**が**大規模なグループの場合、を使用する条件。</span><span class="sxs-lookup"><span data-stu-id="d239f-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="d239f-108">複合正規表現 (regex) パターンマッチングを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="d239f-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="d239f-109">添付ファイルのコンテンツチェックを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="d239f-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="d239f-110">この洞察は、メールフローの遅延を減らすために、メールフロールールを特定し、微調整するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d239f-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Office 365 Security & コンプライアンスセンターのメールフローダッシュボードに記載されている低速のメールフロールールの洞察](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="d239f-112">[詳細の**表示**] をクリックすると、フライアウトウィンドウが表示され、ルールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d239f-112">When you click **View details**, a flyout pane appears where you can review the rule.</span></span> <span data-ttu-id="d239f-113">また、フライアウトウィンドウで [**サンプルメッセージの表示**] をクリックして、ルールによって影響を受けたメッセージの種類を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="d239f-113">In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![メールフローダッシュボードの [低速メールフロールールの詳細を表示する] をクリックした後のフライアウトウィンドウ](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)
