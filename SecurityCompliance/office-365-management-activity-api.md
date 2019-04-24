---
title: Office 365 マネージメント アクティビティ API
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
- M365-analytics
description: Office 365 Management Activity API についての簡単な概要。
ms.openlocfilehash: 3405eaac000111fb5d5f054edcbe6816aa9af9e7
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262559"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="bac41-103">Office 365 マネージメント アクティビティ API</span><span class="sxs-lookup"><span data-stu-id="bac41-103">Office 365 Management Activity API</span></span>
<span data-ttu-id="bac41-104">Microsoft では、管理者が Office 365 テナントに関する集約されたトランザクション情報を取得できるようにするレポートサービスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="bac41-104">Microsoft provides reporting services that enable administrators to obtain aggregated transactional information about their Office 365 tenant.</span></span> <span data-ttu-id="bac41-105">[Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)は、業界標準の RESTful 設計および OAuth v2 を使用して認証を行います。これにより、データを取得して取り込むをビジュアル化ツールやアプリケーションに簡単に取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="bac41-105">The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) uses an industry-standard RESTful design and OAuth v2 for authentication, which makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications.</span></span> <span data-ttu-id="bac41-106">API は、Office 365 のユーザー、管理者、操作、およびセキュリティアクティビティに関する情報を含むデータフィードを提供します。</span><span class="sxs-lookup"><span data-stu-id="bac41-106">The API provides a data feed that includes information about user, administrator, operations, and security activity in Office 365.</span></span> <span data-ttu-id="bac41-107">このデータは、規制目的のため、またはオンプレミスのインフラストラクチャやその他のソースから調達されたログデータと組み合わせて、企業全体にわたる運用、セキュリティ、およびコンプライアンスの監視ソリューションを構築するために保持できます。</span><span class="sxs-lookup"><span data-stu-id="bac41-107">The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources to build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="bac41-108">Office 365 管理アクティビティ API は、Office 365 と Azure Active Directory のアクティビティ ログからの、ユーザー、管理者、システム、およびポリシー アクションとポリシー イベントについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bac41-108">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="bac41-109">この API は、すべてのサービスで共通の10以上のフィールドを持つ一貫性のある監査スキーマを提供します。</span><span class="sxs-lookup"><span data-stu-id="bac41-109">The API provides a consistent audit schema with over 10 fields that are in common across all the services.</span></span> <span data-ttu-id="bac41-110">これにより、組織はイベント間の簡単な接続を確立できるようになり、データに対して新しい方法を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bac41-110">This allows organizations to make easy connections between events, and it enables new ways to reason over the data.</span></span> <span data-ttu-id="bac41-111">多数の独立系ソフトウェアベンダー (isv) が、この API に基づいて Microsoft およびビルドされたソリューションと提携しています。</span><span class="sxs-lookup"><span data-stu-id="bac41-111">Dozens of Independent Software Vendors (ISVs) have partnered with Microsoft and built solutions based on the API.</span></span> <span data-ttu-id="bac41-112">一部のソリューションは、Office 365 データにのみ焦点を置いていますが、複数のクラウドプロバイダーやオンプレミスシステムからのデータを取り込み、運用、セキュリティ、コンプライアンス関連のすべてのアクティビティを統合したビューを作成する機能を提供するものもあります。</span><span class="sxs-lookup"><span data-stu-id="bac41-112">Some solutions are focused solely on Office 365 data, while others provide the ability to ingest data from multiple cloud providers and on-premises systems to create a unified view of all operations, security, and compliance-related activity.</span></span> <span data-ttu-id="bac41-113">詳細については、「 [Office 365 Management Activity API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac41-113">For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
