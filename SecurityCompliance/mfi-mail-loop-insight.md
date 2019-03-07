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
description: 管理者は、Office 365 Security & コンプライアンスセンターのメールフローダッシュボードにあるメールループの洞察について知ることができます。
ms.openlocfilehash: babf102e7645de26d4af0a947319856468ccf755
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455239"
---
# <a name="mail-loop-insight"></a><span data-ttu-id="f83c9-103">メールループの分析情報</span><span class="sxs-lookup"><span data-stu-id="f83c9-103">Mail loop insight</span></span>

<span data-ttu-id="f83c9-104">メールループは、システムリソースが浪費され、組織のメールボリュームクォータを使用して、元の送信者に (ndr またはバウンスメッセージとも呼ばれる) 混乱しない配信不能レポートを送信するため、不正です。</span><span class="sxs-lookup"><span data-stu-id="f83c9-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span> <span data-ttu-id="f83c9-105">この洞察は、組織内でメールループが検出されたとき、ループに含まれる電子メールドメイン、およびループ内の前日からのメッセージ数について報告します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-105">This insight reports when a mail loop is found in your organization, the email domains that are involved in the loop, and the number of messages from the previous day that were in the loop.</span></span>

![Office 365 Security & コンプライアンスセンターのメールフローダッシュボードにあるメールループの分析情報](media/c3f707cb-4c89-4e88-989c-81ce1d1d6b99.png)

<span data-ttu-id="f83c9-107">[詳細の**表示**] をクリックすると、フライアウトウィンドウに詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f83c9-107">You can click **View details** to see the details in a flyout pane.</span></span> <span data-ttu-id="f83c9-108">また、最も一般的なループシナリオを特定し、そのループを修正するために推奨されるアクション (使用可能な場合) を提供します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-108">We also identify the most common loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![メールフローダッシュボードの [詳細を表示] ループをクリックした後のフライアウトウィンドウ](media/f7e21300-c62f-41ec-853f-4a2775cd8aa7.png)
