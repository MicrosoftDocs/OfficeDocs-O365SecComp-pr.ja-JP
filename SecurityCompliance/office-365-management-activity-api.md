---
title: Office 365 マネージメント アクティビティ API
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
- M365-analytics
description: Office 365 Management Activity API についての簡単な概要。
ms.openlocfilehash: ca5517d3049830cd7be912b2e2e47a34a866aca0
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090560"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="bb2d6-103">Office 365 マネージメント アクティビティ API</span><span class="sxs-lookup"><span data-stu-id="bb2d6-103">Office 365 Management Activity API</span></span>
<span data-ttu-id="bb2d6-p101">Microsoft では、管理者が Office 365 テナントに関する集約されたトランザクション情報を取得できるようにするレポートサービスを提供しています。[Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)は、業界標準の RESTful 設計および OAuth v2 を使用して認証を行います。これにより、データを取得して取り込むをビジュアル化ツールやアプリケーションに簡単に取り込むことができます。API は、Office 365 のユーザー、管理者、操作、およびセキュリティアクティビティに関する情報を含むデータフィードを提供します。このデータは、規制目的のため、またはオンプレミスのインフラストラクチャやその他のソースから調達されたログデータと組み合わせて、企業全体にわたる運用、セキュリティ、およびコンプライアンスの監視ソリューションを構築するために保持できます。</span><span class="sxs-lookup"><span data-stu-id="bb2d6-p101">Microsoft provides reporting services that enable administrators to obtain aggregated transactional information about their Office 365 tenant. The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) uses an industry-standard RESTful design and OAuth v2 for authentication, which makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications. The API provides a data feed that includes information about user, administrator, operations, and security activity in Office 365. The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources to build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="bb2d6-p102">office 365 Management Activity API は、office 365 および Azure Active Directory のアクティビティログから、さまざまなユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を提供します。この API は、すべてのサービスで共通の10以上のフィールドを持つ一貫性のある監査スキーマを提供します。これにより、組織はイベント間の簡単な接続を確立できるようになり、データに対して新しい方法を使用できるようになります。多数の独立系ソフトウェアベンダー (isv) が、この API に基づいて Microsoft およびビルドされたソリューションと提携しています。一部のソリューションは、Office 365 データにのみ焦点を置いていますが、複数のクラウドプロバイダーやオンプレミスシステムからのデータを取り込み、運用、セキュリティ、コンプライアンス関連のすべてのアクティビティを統合したビューを作成する機能を提供するものもあります。詳細については、「 [Office 365 Management Activity API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb2d6-p102">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs. The API provides a consistent audit schema with over 10 fields that are in common across all the services. This allows organizations to make easy connections between events, and it enables new ways to reason over the data. Dozens of Independent Software Vendors (ISVs) have partnered with Microsoft and built solutions based on the API. Some solutions are focused solely on Office 365 data, while others provide the ability to ingest data from multiple cloud providers and on-premises systems to create a unified view of all operations, security, and compliance-related activity. For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
