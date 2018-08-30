---
title: Office 365 Yammer エンタープライズ ・ アクセスを制御します。
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: 概要 Yammer エンタープライズ ・ アクセス ・ コントロールに関する運用環境にします。'
ms.openlocfilehash: 3f51e63c16022353e743b57d8e977f2ea2e6a835
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532670"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="e72c2-103">Yammer Enterprise でのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="e72c2-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="e72c2-p101">Yammer の本番環境への物理および論理アクセスは、非常に少数のユーザー (インフラストラクチャと運用) に制限されます。同様に他の Office 365 のエンジニア、Yammer エンジニア アクセス ゼロ位置顧客データ。ロック ボックスは、のようなジャスト ・ イン ・ タイムの承認に基づくアクセス制御システムを使用してアクセスを要求する必要があり、承認者の数に制限があります。承認者が要求を確認 (例: を確認するかどうか、要求は、正当な必要性、ビジネス ・ ケース、時間などに基づく)、承認するか、要求を拒否します。要求が承認されると、その後、自動的に有効期限が切れる、定義され、限られた時間の JIT のアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="e72c2-p101">Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations). As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data. Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers. Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request. If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires.</span></span> 

<span data-ttu-id="e72c2-p102">同様に、他の Office 365 サービスは、Yammer の運用環境に対するすべてのアクセスは、多元的な認証を利用しています。すべてアクセスし、コマンドの履歴は、ユーザーに属すると記録され、Yammer のセキュリティ チームが定期的に確認します。</span><span class="sxs-lookup"><span data-stu-id="e72c2-p102">As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication. All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="e72c2-111">Yammer の管理と管理に関する詳細については、 [Yammer 管理のヘルプ](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e72c2-111">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>