---
title: Office 365 Yammer エンタープライズアクセスコントロール
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '概要: 運用環境での Yammer エンタープライズアクセス制御についての簡単な概要。'
ms.openlocfilehash: 76b62e7ea026a52d822e5a213461e930b1d595e3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217887"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="fec84-103">Yammer Enterprise でのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="fec84-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="fec84-p101">Yammer の運用環境への物理的および論理的なアクセスは両方とも、非常に少数のユーザー (インフラストラクチャと運用) に制限されます。他の Office 365 エンジニアと同様に、Yammer のエンジニアは顧客データへのアクセスをゼロにします。アクセス許可は、ロックボックスと同様に、承認ベースのジャストインタイムのアクセス制御システムを使用して要求する必要があります。承認者の数には制限があります。承認者は、要求を確認します (たとえば、要求が正当であるかどうか、ビジネスケース、時間などに基づいて検証されます)。その後、要求を承認または拒否します。要求が承認された場合、JIT アクセスは定義済みの時間に限定され、その後は自動的に期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="fec84-p101">Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations). As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data. Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers. Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request. If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires.</span></span> 

<span data-ttu-id="fec84-p102">他の Office 365 サービスと同様に、Yammer の運用環境へのすべてのアクセスでは多要素認証が使用されます。すべてのアクセスおよびコマンド履歴はユーザーに帰属し、Yammer セキュリティチームによって定期的にログおよび確認されます。</span><span class="sxs-lookup"><span data-stu-id="fec84-p102">As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication. All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="fec84-111">yammer の管理と管理の詳細については、「 [yammer 管理者のヘルプ](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fec84-111">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>