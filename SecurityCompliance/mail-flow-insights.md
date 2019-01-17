---
title: セキュリティ & コンプライアンス センターでのメール フローの把握
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理者は、セキュリティ & コンプライアンス センターでメール フローのダッシュ ボードについて学習できます。
ms.openlocfilehash: 481815430a91413cc96b92c074bd2d62771751ee
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685534"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="f24a3-103">セキュリティ & コンプライアンス センターでのメール フローの把握</span><span class="sxs-lookup"><span data-stu-id="f24a3-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="f24a3-104">管理者は、意見の傾向を発見し、Office 365 の組織内のメール フローに関連する問題を修正するアクションを実行するセキュリティ & コンプライアンス センターでメール フローのダッシュ ボードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f24a3-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="f24a3-105">分析、レポート、およびメール フローのダッシュ ボードで使用可能なウィジェットはです。</span><span class="sxs-lookup"><span data-stu-id="f24a3-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="f24a3-106">送信および受信メール フロー</span><span class="sxs-lookup"><span data-stu-id="f24a3-106">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="f24a3-107">通知のキューおよびキュー</span><span class="sxs-lookup"><span data-stu-id="f24a3-107">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="f24a3-108">レポートのメッセージの自動転送</span><span class="sxs-lookup"><span data-stu-id="f24a3-108">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="f24a3-109">メール ループの把握</span><span class="sxs-lookup"><span data-stu-id="f24a3-109">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="f24a3-110">低速のメール フローのルールの把握</span><span class="sxs-lookup"><span data-stu-id="f24a3-110">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="f24a3-111">メール フローのダッシュ ボードを表示するのには必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f24a3-111">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="f24a3-112">メール フローのダッシュ ボードがあります。</span><span class="sxs-lookup"><span data-stu-id="f24a3-112">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="f24a3-113">**Office 365 のグローバル管理者**ロールのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="f24a3-113">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="f24a3-114">**Office 365 の Exchange 管理者**の役割のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="f24a3-114">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="f24a3-p101">セキュリティ & コンプライアンス センター内の**メール フローの管理者ロール**のメンバーです。このロールは、グローバル管理者または Exchange 管理者の役割のメンバーでないユーザーに明示的に割り当てられます。 場合、</span><span class="sxs-lookup"><span data-stu-id="f24a3-p101">Members of the **Mail flow administrator role** in the Security & Compliance Center. If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="f24a3-117">ユーザーに直接セキュリティ & コンプライアンス センターにログインする必要があります[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="f24a3-117">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="f24a3-118">ユーザーは、メール フローのダッシュ ボードに読み取り専用のアクセス許可をのみがあります。</span><span class="sxs-lookup"><span data-stu-id="f24a3-118">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="f24a3-119">ユーザーは、Office 365 管理ポータルへのアクセスを必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f24a3-119">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="f24a3-120">Office 365 のグローバル管理者ロールの詳細については、 [Office 365 の管理者の役割](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f24a3-120">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

<span data-ttu-id="f24a3-121">セキュリティ & コンプライアンス センターの役割をユーザーに割り当てる方法の詳細については、[セキュリティ & コンプライアンス センターへのユーザー アクセス許可](https://support.office.com/article/2cfce2c8-20c5-47f9-afc4-24b059c1bd76)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f24a3-121">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](https://support.office.com/article/2cfce2c8-20c5-47f9-afc4-24b059c1bd76).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="f24a3-122">メール フローのダッシュ ボードの入手先</span><span class="sxs-lookup"><span data-stu-id="f24a3-122">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="f24a3-123">セキュリティ & コンプライアンス中心に[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="f24a3-123">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="f24a3-124">**メールの流れ**を展開し、**ダッシュ ボード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f24a3-124">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Office 365 のセキュリティ & コンプライアンス センターでメール フローのダッシュ ボード](media/f32f5c0a-ea32-4e47-a477-d070405d4ae8.png)
