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
# <a name="office-365-management-activity-api"></a>Office 365 マネージメント アクティビティ API
Microsoft では、管理者が Office 365 テナントに関する集約されたトランザクション情報を取得できるようにするレポートサービスを提供しています。 [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)は、業界標準の RESTful 設計および OAuth v2 を使用して認証を行います。これにより、データを取得して取り込むをビジュアル化ツールやアプリケーションに簡単に取り込むことができます。 API は、Office 365 のユーザー、管理者、操作、およびセキュリティアクティビティに関する情報を含むデータフィードを提供します。 このデータは、規制目的のため、またはオンプレミスのインフラストラクチャやその他のソースから調達されたログデータと組み合わせて、企業全体にわたる運用、セキュリティ、およびコンプライアンスの監視ソリューションを構築するために保持できます。

Office 365 管理アクティビティ API は、Office 365 と Azure Active Directory のアクティビティ ログからの、ユーザー、管理者、システム、およびポリシー アクションとポリシー イベントについての情報を提供します。 この API は、すべてのサービスで共通の10以上のフィールドを持つ一貫性のある監査スキーマを提供します。 これにより、組織はイベント間の簡単な接続を確立できるようになり、データに対して新しい方法を使用できるようになります。 多数の独立系ソフトウェアベンダー (isv) が、この API に基づいて Microsoft およびビルドされたソリューションと提携しています。 一部のソリューションは、Office 365 データにのみ焦点を置いていますが、複数のクラウドプロバイダーやオンプレミスシステムからのデータを取り込み、運用、セキュリティ、コンプライアンス関連のすべてのアクティビティを統合したビューを作成する機能を提供するものもあります。 詳細については、「 [Office 365 Management Activity API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)」を参照してください。
