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
# <a name="yammer-enterprise-access-controls"></a>Yammer Enterprise でのアクセス制御 

Yammer の運用環境への物理的および論理的なアクセスは両方とも、非常に少数のユーザー (インフラストラクチャと運用) に制限されます。 他の Office 365 エンジニアと同様に、Yammer のエンジニアは顧客データへのアクセスをゼロにします。 アクセス許可は、ロックボックスと同様に、承認ベースのジャストインタイムのアクセス制御システムを使用して要求する必要があります。承認者の数には制限があります。 承認者は、要求を確認します (たとえば、要求が正当であるかどうか、ビジネスケース、時間などに基づいて検証されます)。その後、要求を承認または拒否します。 要求が承認された場合、JIT アクセスは定義済みの時間に限定され、その後は自動的に期限が切れます。 

他の Office 365 サービスと同様に、Yammer の運用環境へのすべてのアクセスでは多要素認証が使用されます。 すべてのアクセスおよびコマンド履歴はユーザーに帰属し、Yammer セキュリティチームによって定期的にログおよび確認されます。

yammer の管理と管理の詳細については、「 [yammer 管理者のヘルプ](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)」を参照してください。