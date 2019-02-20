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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '概要: Office 365 内の分離コントロールについて説明します。'
ms.openlocfilehash: ad39f300445485e46699b509f845ac363d3041fa
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090969"
---
# <a name="office-365-isolation-controls"></a><span data-ttu-id="64139-103">Office 365 での分離コントロール</span><span class="sxs-lookup"><span data-stu-id="64139-103">Office 365 Isolation Controls</span></span> 

<span data-ttu-id="64139-p101">Microsoft は、Office 365 のマルチテナントアーキテクチャが、エンタープライズレベルのセキュリティ、機密性、プライバシー、整合性、および可用性の[標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)と、ローカルおよび国際標準をサポートしていることを継続的にご確認ください。Microsoft によって提供されるサービスの規模と範囲を考えると、大量の人的介入が必要になった場合に Office 365 を管理するのは困難で、経済的ではありません。Office 365 サービスは、グローバルに分散した複数のデータセンターを介して提供されますが、非常に多くのデータセンター操作が必要になるだけで、ユーザーのコンテンツにアクセスする必要のある操作も少なくなります。マイクロソフトのスタッフは、自動化ツールおよび高度なセキュリティで保護されたリモートアクセスを使用してこれらのサービスとデータセンターをサポートします。大規模サービスが office 365 でどのように動作するかに関する詳細については、「 [office 365 for IT 担当者向けの背景](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64139-p101">Microsoft continuously works to ensure that the multi-tenant architecture of Office 365 supports enterprise-level security, confidentiality, privacy, integrity, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons), as well as local and international standards. Given the scale and the scope of services provided by Microsoft, it would be difficult and non-economical to manage Office 365 if significant human interaction were required. Office 365 services are provided through multiple globally-distributed datacenters, in a highly-automated fashion, where extremely few datacenter operations require a human touch, and even fewer operations require access to customer content. Our staff supports these services and datacenters using automated tools and highly secure remote access. For some of the details about how large-scale services are operated in Office 365, see [a behind the scenes look at Office 365 for IT Pros](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).</span></span>

<span data-ttu-id="64139-p102">office 365 は、重要なビジネス機能を提供し、office 365 環境全体に貢献する複数のサービスで構成されています。これらの各サービスは、自己完結型であり、相互に統合するように設計されています。Office 365 は、[サービス指向アーキテクチャ](https://msdn.microsoft.com/library/aa480021.aspx)の原則を使用して設計されています。これは、適切に定義されたビジネス機能を提供し、[運用上のセキュリティを提供する相互運用可能なサービスとしてのソフトウェアの設計と開発と定義されています。保証](http://www.microsoft.com/download/details.aspx?id=40872)として、microsoft の[セキュリティ開発ライフサイクル](https://www.microsoft.com/sdl/default.aspx)、 [microsoft セキュリティレスポンスセンター](https://technet.microsoft.com/library/dn440717.aspx)、ディープを含む、microsoft 固有のさまざまな機能によって得られた知識を組み込むフレームワーク。cybersecurity 脅威の状況を認識します。</span><span class="sxs-lookup"><span data-stu-id="64139-p102">Office 365 is composed of multiple services that provide important business functionality and contribute to the entire Office 365 experience. Each of these services is designed to be self-contained and to integrate with one another. Office 365 is designed with the principles of a [Service-Oriented Architecture](https://msdn.microsoft.com/library/aa480021.aspx), which is defined as designing and developing software in the form of interoperable services providing well-defined business functionality, and [Operational Security Assurance](http://www.microsoft.com/download/details.aspx?id=40872), a framework that incorporates the knowledge gained through a variety of capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="64139-p103">Office 365 サービスは相互に相互運用されますが、相互に依存しない独立したサービスとして展開および運用できるように設計および実装されています。Microsoft segregates の職務および Office 365 の責任範囲によって、組織の資産の改ざんまたは誤用の可能性を低減します。Office 365 teams は、役割ベースの総合的なアクセス制御メカニズムの一部として役割を定義しています。</span><span class="sxs-lookup"><span data-stu-id="64139-p103">Office 365 services interoperate with each other, but they are designed and implemented so that they can be deployed and operated as autonomous services, independent of each other. Microsoft segregates duties and areas of responsibility for Office 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets. Office 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="64139-115">顧客コンテンツの分離</span><span class="sxs-lookup"><span data-stu-id="64139-115">Customer Content Isolation</span></span>
<span data-ttu-id="64139-p104">テナントに属するすべてのお客様のコンテンツは、他のテナント、および Office 365 の管理で使用されている運用およびシステムのデータから分離されています。office 365 には複数の形式の保護が実装されており、office 365 のサービスまたはアプリケーションが侵害されるリスクを最小限に抑えたり、テナントまたは office 365 システム自体の情報に対する権限のないアクセス権を取得したりします。Microsoft が office 365 内のテナントデータの論理的分離を実装する方法については、「 [office 365 のテナント分離](office-365-tenant-isolation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64139-p104">All customer content belonging to a tenant is isolated from other tenants and from the operations and systems data used in the management of Office 365. Multiple forms of protection have been implemented throughout Office 365 to minimize the risk of compromise of any Office 365 service or application, or any gaining of unauthorized access to the information of tenants or the Office 365 system itself. For information about how Microsoft implements logical isolation of tenant data within Office 365, see [Tenant Isolation in Office 365](office-365-tenant-isolation-overview.md).</span></span>
