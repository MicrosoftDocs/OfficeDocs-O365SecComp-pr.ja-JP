---
title: Office 365 での分離コントロール
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
description: '概要: Office 365 の分離のコントロールの説明。'
ms.openlocfilehash: 3a5c06d0675a4503d9f5e5edd58535688fb9180a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532809"
---
# <a name="office-365-isolation-controls"></a>Office 365 での分離コントロール 

マイクロソフトは、Office 365 のマルチ テナント型アーキテクチャには、ローカルおよび国際的な規格に加え、エンタープライズ レベルのセキュリティ、機密性、プライバシー、整合性、および可用性の[標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)がサポートされていることを確認するのには継続的に動作します。スケールおよびマイクロソフトが提供するサービスの範囲を指定するには、困難であり、多大な人的介入が必要な場合は、Office 365 を管理するための経済的ながあります。複数グローバルに分散したデータ センター、高度に自動化された方法で、非常にいくつかのデータ センターの運用が、人間のタッチを必要として、演算が少ない場合でもお客様のコンテンツへのアクセスを必要とする office 365 サービスが提供されます。当社のスタッフは、これらのサービスとデータ センターの自動化ツールを使用してをサポートし、高度なリモート アクセスをセキュリティで保護します。いくつかの方法の詳細については、大規模なサービスは、Office 365 を参照してください[IT 担当者向けの Office 365 を見て、シーンの背後](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202)で運営されています。

Office 365 は、重要なビジネス機能を提供し、全体の Office 365 環境に寄与する複数のサービスで構成されます。これらのサービスは、自己完結型と、相互に統合するために設計されています。Office 365 は、[サービス指向アーキテクチャ](https://msdn.microsoft.com/library/aa480021.aspx)の設計との相互運用可能なサービスが適切に定義されたビジネス機能、および[の運用上のセキュリティを提供する形でのソフトウェア開発として定義されているの原則で設計されています。保証](http://www.microsoft.com/download/details.aspx?id=40872)、さまざまなマイクロソフトでは、マイクロソフトの[セキュリティ開発ライフ サイクル](https://www.microsoft.com/sdl/default.aspx)、[マイクロソフト セキュリティ レスポンス センター](https://technet.microsoft.com/library/dn440717.aspx)、さらに深いなどに固有の機能で、サポート技術情報が組み込まれたフレームワークが得られるcybersecurity 脅威の情勢の認識です。

Office 365 サービスは、互いに相互運用が、それらを設計および実装するように、配置して互いに独立して、自律的なサービスとして運用することができます。マイクロソフトでは、職務と権限のない、または意図しない変更のための機会を減らすために Office 365 の担当領域や組織の資産の悪用を分離します。Office 365 チームは、包括的な役割に基づくアクセス制御メカニズムの一部としての役割が定義されているが。

## <a name="customer-content-isolation"></a>お客様のコンテンツの分離
テナントに属するすべてのお客様のコンテンツは、他のテナントと Office 365 の管理で使用する操作とシステムのデータから分離します。保護の複数のフォームは、任意の Office 365 サービスまたはアプリケーション、または、テナントや Office 365 のシステム自体の情報への不正アクセスを得るの危険にさらされるリスクを最小限に抑えるため、Office 365 で実装されています。Microsoft Office 365 のテナントのデータの論理的分離を実装する方法については、 [Office 365 のテナントの分離](office-365-tenant-isolation-overview.md)を参照してください。
