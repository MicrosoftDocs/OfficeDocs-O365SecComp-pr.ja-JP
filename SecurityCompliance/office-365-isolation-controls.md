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
# <a name="office-365-isolation-controls"></a><span data-ttu-id="748f5-103">Office 365 での分離コントロール</span><span class="sxs-lookup"><span data-stu-id="748f5-103">Office 365 Isolation Controls</span></span> 

<span data-ttu-id="748f5-p101">マイクロソフトは、Office 365 のマルチ テナント型アーキテクチャには、ローカルおよび国際的な規格に加え、エンタープライズ レベルのセキュリティ、機密性、プライバシー、整合性、および可用性の[標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)がサポートされていることを確認するのには継続的に動作します。スケールおよびマイクロソフトが提供するサービスの範囲を指定するには、困難であり、多大な人的介入が必要な場合は、Office 365 を管理するための経済的ながあります。複数グローバルに分散したデータ センター、高度に自動化された方法で、非常にいくつかのデータ センターの運用が、人間のタッチを必要として、演算が少ない場合でもお客様のコンテンツへのアクセスを必要とする office 365 サービスが提供されます。当社のスタッフは、これらのサービスとデータ センターの自動化ツールを使用してをサポートし、高度なリモート アクセスをセキュリティで保護します。いくつかの方法の詳細については、大規模なサービスは、Office 365 を参照してください[IT 担当者向けの Office 365 を見て、シーンの背後](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202)で運営されています。</span><span class="sxs-lookup"><span data-stu-id="748f5-p101">Microsoft continuously works to ensure that the multi-tenant architecture of Office 365 supports enterprise-level security, confidentiality, privacy, integrity, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons), as well as local and international standards. Given the scale and the scope of services provided by Microsoft, it would be difficult and non-economical to manage Office 365 if significant human interaction were required. Office 365 services are provided through multiple globally-distributed datacenters, in a highly-automated fashion, where extremely few datacenter operations require a human touch, and even fewer operations require access to customer content. Our staff supports these services and datacenters using automated tools and highly secure remote access. For some of the details about how large-scale services are operated in Office 365, see [a behind the scenes look at Office 365 for IT Pros](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).</span></span>

<span data-ttu-id="748f5-p102">Office 365 は、重要なビジネス機能を提供し、全体の Office 365 環境に寄与する複数のサービスで構成されます。これらのサービスは、自己完結型と、相互に統合するために設計されています。Office 365 は、[サービス指向アーキテクチャ](https://msdn.microsoft.com/library/aa480021.aspx)の設計との相互運用可能なサービスが適切に定義されたビジネス機能、および[の運用上のセキュリティを提供する形でのソフトウェア開発として定義されているの原則で設計されています。保証](http://www.microsoft.com/download/details.aspx?id=40872)、さまざまなマイクロソフトでは、マイクロソフトの[セキュリティ開発ライフ サイクル](https://www.microsoft.com/sdl/default.aspx)、[マイクロソフト セキュリティ レスポンス センター](https://technet.microsoft.com/library/dn440717.aspx)、さらに深いなどに固有の機能で、サポート技術情報が組み込まれたフレームワークが得られるcybersecurity 脅威の情勢の認識です。</span><span class="sxs-lookup"><span data-stu-id="748f5-p102">Office 365 is composed of multiple services that provide important business functionality and contribute to the entire Office 365 experience. Each of these services is designed to be self-contained and to integrate with one another. Office 365 is designed with the principles of a [Service-Oriented Architecture](https://msdn.microsoft.com/library/aa480021.aspx), which is defined as designing and developing software in the form of interoperable services providing well-defined business functionality, and [Operational Security Assurance](http://www.microsoft.com/download/details.aspx?id=40872), a framework that incorporates the knowledge gained through a variety of capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="748f5-p103">Office 365 サービスは、互いに相互運用が、それらを設計および実装するように、配置して互いに独立して、自律的なサービスとして運用することができます。マイクロソフトでは、職務と権限のない、または意図しない変更のための機会を減らすために Office 365 の担当領域や組織の資産の悪用を分離します。Office 365 チームは、包括的な役割に基づくアクセス制御メカニズムの一部としての役割が定義されているが。</span><span class="sxs-lookup"><span data-stu-id="748f5-p103">Office 365 services interoperate with each other, but they are designed and implemented so that they can be deployed and operated as autonomous services, independent of each other. Microsoft segregates duties and areas of responsibility for Office 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets. Office 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="748f5-115">お客様のコンテンツの分離</span><span class="sxs-lookup"><span data-stu-id="748f5-115">Customer Content Isolation</span></span>
<span data-ttu-id="748f5-p104">テナントに属するすべてのお客様のコンテンツは、他のテナントと Office 365 の管理で使用する操作とシステムのデータから分離します。保護の複数のフォームは、任意の Office 365 サービスまたはアプリケーション、または、テナントや Office 365 のシステム自体の情報への不正アクセスを得るの危険にさらされるリスクを最小限に抑えるため、Office 365 で実装されています。Microsoft Office 365 のテナントのデータの論理的分離を実装する方法については、 [Office 365 のテナントの分離](office-365-tenant-isolation-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="748f5-p104">All customer content belonging to a tenant is isolated from other tenants and from the operations and systems data used in the management of Office 365. Multiple forms of protection have been implemented throughout Office 365 to minimize the risk of compromise of any Office 365 service or application, or any gaining of unauthorized access to the information of tenants or the Office 365 system itself. For information about how Microsoft implements logical isolation of tenant data within Office 365, see [Tenant Isolation in Office 365](office-365-tenant-isolation-overview.md).</span></span>
