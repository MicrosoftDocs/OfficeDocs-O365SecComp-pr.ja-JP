---
title: Office 365 Yammer エンタープライズアクセスコントロール
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '概要: 運用環境での Yammer エンタープライズアクセス制御についての簡単な概要。'
ms.openlocfilehash: 61598235a010aaa1c578c449cb054073212a41f9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262349"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="614ee-103">Yammer Enterprise でのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="614ee-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="614ee-104">Yammer の運用環境への物理的および論理的なアクセスは両方とも、非常に少数のユーザー (インフラストラクチャと運用) に制限されます。</span><span class="sxs-lookup"><span data-stu-id="614ee-104">Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations).</span></span> <span data-ttu-id="614ee-105">他の Office 365 エンジニアと同様に、Yammer のエンジニアは顧客データへのアクセスをゼロにします。</span><span class="sxs-lookup"><span data-stu-id="614ee-105">As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data.</span></span> <span data-ttu-id="614ee-106">アクセス許可は、ロックボックスと同様に、承認ベースのジャストインタイムのアクセス制御システムを使用して要求する必要があります。承認者の数には制限があります。</span><span class="sxs-lookup"><span data-stu-id="614ee-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers.</span></span> <span data-ttu-id="614ee-107">承認者は、要求を確認します (たとえば、要求が正当であるかどうか、ビジネスケース、時間などに基づいて検証されます)。その後、要求を承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="614ee-107">Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="614ee-108">要求が承認された場合、JIT アクセスは定義済みの時間に限定され、その後は自動的に期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="614ee-108">If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires.</span></span> 

<span data-ttu-id="614ee-109">他の Office 365 サービスと同様に、Yammer の運用環境へのすべてのアクセスでは多要素認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="614ee-109">As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication.</span></span> <span data-ttu-id="614ee-110">すべてのアクセスおよびコマンド履歴はユーザーに帰属し、Yammer セキュリティチームによって定期的にログおよび確認されます。</span><span class="sxs-lookup"><span data-stu-id="614ee-110">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="614ee-111">yammer の管理と管理の詳細については、「 [yammer 管理者のヘルプ](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614ee-111">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>