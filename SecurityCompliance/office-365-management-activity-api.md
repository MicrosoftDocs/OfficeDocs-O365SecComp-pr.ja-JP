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
ms.collection: Strat_O365_Enterprise
description: Office 365 の管理アクティビティ API について簡単に説明します。
ms.openlocfilehash: 4753be89c008676d5244b5c659c3dd1a545975b2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531645"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="4d59c-103">Office 365 マネージメント アクティビティ API</span><span class="sxs-lookup"><span data-stu-id="4d59c-103">Office 365 Management Activity API</span></span>
<span data-ttu-id="4d59c-p101">マイクロソフトでは、集約されたトランザクションについては、Office 365 テナントを取得する管理者を有効にするレポートのサービスを提供します。[Office 365 の管理アクティビティの API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)は、簡単にデータを取得し、ビジュアル化ツールやアプリケーションに取り込むことで実験を開始するには、認証のため、業界標準の RESTful デザインと OAuth v2 を使用します。API は、データを提供するフィードを Office 365 のユーザー、管理者、運用、およびセキュリティの活動に関する情報が含まれています。データは、規制対応のための保持または調達、オンプレミス インフラストラクチャまたは企業全体にわたる操作、セキュリティ、およびコンプライアンスの監視ソリューションを構築するには、他のソースからログのデータと結合できます。</span><span class="sxs-lookup"><span data-stu-id="4d59c-p101">Microsoft provides reporting services that enable administrators to obtain aggregated transactional information about their Office 365 tenant. The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) uses an industry-standard RESTful design and OAuth v2 for authentication, which makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications. The API provides a data feed that includes information about user, administrator, operations, and security activity in Office 365. The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources to build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="4d59c-p102">Office 365 の管理アクティビティの API は、Office 365 と Azure Active Directory の動作状況のログから、さまざまなユーザー、管理者、システム、ポリシー アクション、およびイベントに関する情報を提供します。API は、すべてのサービス間で共通では、10 個以上のフィールドを持つ一貫した監査スキーマを提供します。これにより、組織は、イベント間を簡単に接続を確立し、データのための新しい方法が有効にします。多数の独立系ソフトウェア ベンダー (Isv) では、マイクロソフトと提携あり、API ベースのソリューションを構築することがあります。いくつかのソリューションは、すべての操作、セキュリティ、およびコンプライアンスに関連する活動の統一されたビューを作成するのには、複数のクラウド プロバイダーとオンプレミス システムからデータを取得する機能を提供するときに Office 365 のデータだけに集中しています。詳細については、 [Office 365 の管理アクティビティの API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d59c-p102">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs. The API provides a consistent audit schema with over 10 fields that are in common across all the services. This allows organizations to make easy connections between events, and it enables new ways to reason over the data. Dozens of Independent Software Vendors (ISVs) have partnered with Microsoft and built solutions based on the API. Some solutions are focused solely on Office 365 data, while others provide the ability to ingest data from multiple cloud providers and on-premises systems to create a unified view of all operations, security, and compliance-related activity. For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
