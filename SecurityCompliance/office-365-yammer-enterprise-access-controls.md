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
# <a name="yammer-enterprise-access-controls"></a>Yammer Enterprise でのアクセス制御 

Yammer の本番環境への物理および論理アクセスは、非常に少数のユーザー (インフラストラクチャと運用) に制限されます。同様に他の Office 365 のエンジニア、Yammer エンジニア アクセス ゼロ位置顧客データ。ロック ボックスは、のようなジャスト ・ イン ・ タイムの承認に基づくアクセス制御システムを使用してアクセスを要求する必要があり、承認者の数に制限があります。承認者が要求を確認 (例: を確認するかどうか、要求は、正当な必要性、ビジネス ・ ケース、時間などに基づく)、承認するか、要求を拒否します。要求が承認されると、その後、自動的に有効期限が切れる、定義され、限られた時間の JIT のアクセスが許可されます。 

同様に、他の Office 365 サービスは、Yammer の運用環境に対するすべてのアクセスは、多元的な認証を利用しています。すべてアクセスし、コマンドの履歴は、ユーザーに属すると記録され、Yammer のセキュリティ チームが定期的に確認します。

Yammer の管理と管理に関する詳細については、 [Yammer 管理のヘルプ](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)を参照してください。