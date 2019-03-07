---
title: セキュリティ & コンプライアンスセンターのメールフローインサイト
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードについて学習できます。
ms.openlocfilehash: 1e18bcb381a6b557d3141c0c17b8433cfcd00049
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455149"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="69a8b-103">セキュリティ & コンプライアンスセンターのメールフローインサイト</span><span class="sxs-lookup"><span data-stu-id="69a8b-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="69a8b-104">管理者は、Security & コンプライアンスセンターのメールフローダッシュボードを使用して、Office 365 組織のメールフローに関連する問題を解決するための傾向、洞察、アクションの実行を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="69a8b-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="69a8b-105">メールフローダッシュボードで使用できる洞察、レポート、およびウィジェットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="69a8b-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="69a8b-106">送信と受信のメール フロー</span><span class="sxs-lookup"><span data-stu-id="69a8b-106">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="69a8b-107">キューのアラートとキュー</span><span class="sxs-lookup"><span data-stu-id="69a8b-107">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="69a8b-108">自動転送済みメッセージレポート</span><span class="sxs-lookup"><span data-stu-id="69a8b-108">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="69a8b-109">メールループの分析情報</span><span class="sxs-lookup"><span data-stu-id="69a8b-109">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="69a8b-110">低速メール フローのルールの分析情報</span><span class="sxs-lookup"><span data-stu-id="69a8b-110">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="69a8b-111">メールフローダッシュボードを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="69a8b-111">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="69a8b-112">メールフローダッシュボードは次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="69a8b-112">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="69a8b-113">**Office 365 グローバル管理者**ロールのメンバー。</span><span class="sxs-lookup"><span data-stu-id="69a8b-113">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="69a8b-114">**Office 365 Exchange 管理者**ロールのメンバー。</span><span class="sxs-lookup"><span data-stu-id="69a8b-114">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="69a8b-115">Security & コンプライアンスセンターの**メールフロー管理者ロール**のメンバー。</span><span class="sxs-lookup"><span data-stu-id="69a8b-115">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="69a8b-116">この役割が、グローバル管理者または Exchange 管理者の役割のメンバーではないユーザーに明示的に割り当てられている場合:</span><span class="sxs-lookup"><span data-stu-id="69a8b-116">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="69a8b-117">ユーザーは、Security & コンプライアンスセンターに直接ログインする必要が[https://protection.office.com](https://protection.office.com)あります。</span><span class="sxs-lookup"><span data-stu-id="69a8b-117">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="69a8b-118">ユーザーには、メールフローダッシュボードに対する読み取り専用アクセス許可のみが付与されます。</span><span class="sxs-lookup"><span data-stu-id="69a8b-118">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="69a8b-119">ユーザーは Office 365 管理ポータルにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="69a8b-119">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="69a8b-120">office 365 のグローバル管理者の役割の詳細については、「 [office 365 管理者の役割につい](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a8b-120">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

<span data-ttu-id="69a8b-121">セキュリティ & コンプライアンスセンターの役割をユーザーに割り当てる方法については、「[ユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する](https://support.office.com/article/2cfce2c8-20c5-47f9-afc4-24b059c1bd76)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a8b-121">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](https://support.office.com/article/2cfce2c8-20c5-47f9-afc4-24b059c1bd76).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="69a8b-122">メールフローダッシュボードの検索先</span><span class="sxs-lookup"><span data-stu-id="69a8b-122">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="69a8b-123">セキュリティ & コンプライアンスセンターに移動し[https://protection.office.com](https://protection.office.com)ます。</span><span class="sxs-lookup"><span data-stu-id="69a8b-123">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="69a8b-124">[**メールフロー** ] を展開し、[**ダッシュボード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69a8b-124">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Office 365 Security & コンプライアンスセンターのメールフローダッシュボード](media/f32f5c0a-ea32-4e47-a477-d070405d4ae8.png)
