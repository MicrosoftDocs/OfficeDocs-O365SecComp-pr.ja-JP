---
title: 低速のメール フローのルールの把握
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 5/3/2018
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: 管理者は、Office 365 のセキュリティ & コンプライアンス センターでメール フローのダッシュ ボードに低速のメール フロー ルールの把握について学習できます。
ms.openlocfilehash: 930ea7c57d896c75c6af1333f2bf202b56270199
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685533"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="91288-103">低速のメール フローのルールの把握</span><span class="sxs-lookup"><span data-stu-id="91288-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="91288-p101">非効率的なメール フロー ルール (トランスポート ルールでとも呼ばれます) は、組織のメール フローの遅延が発生する可能性があります。この情報は、メール フロー ルール、組織のメール フローに影響を与えることを報告します。これらの規則の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="91288-p101">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization. This insight reports mail flow rules that have an impact on your organization's mail flow. Examples of these types of rules are:</span></span>

- <span data-ttu-id="91288-107">大規模なグループ**のメンバー**を使用する条件です。</span><span class="sxs-lookup"><span data-stu-id="91288-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="91288-108">複雑な正規表現 (regex) パターンの一致を使用する条件です。</span><span class="sxs-lookup"><span data-stu-id="91288-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="91288-109">添付ファイルのコンテンツのチェック機能を使用する条件です。</span><span class="sxs-lookup"><span data-stu-id="91288-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="91288-110">識別し、メール フローの遅延を減らすためのメール フロー ルールを微調整するには、情報を得ることが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="91288-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![低速のメール フロー ルールを Office 365 のセキュリティ & コンプライアンス センターでメール フローのダッシュ ボードでの把握](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="91288-p102">**ビューの詳細]** をクリックすると、フライアウト ウィンドウでは、ルールを確認することができますが表示されます。フライアウトのウィンドウで、ルールの影響を受けるメッセージの種類を表示する**サンプル メッセージを表示する**をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="91288-p102">When you click **View details**, a flyout pane appears where you can review the rule. In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![メール フローのダッシュ ボードでの低速のメール フロー ルール情報の詳細の表示をクリックするとフライアウト ウィンドウ](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)
