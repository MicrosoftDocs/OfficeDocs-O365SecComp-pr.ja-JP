---
title: Office 365 Advanced Threat Protection との SIEM の統合
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 03/11/2019
ms.collection:
- M365-security-compliance
description: 組織の SIEM サーバーと Office 365 Advanced Threat Protection および関連する脅威イベントを Office 365 アクティビティ管理 API に統合します。
ms.openlocfilehash: da34073669d50cadcc01b5dd885d209a329c645f
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077193"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection との SIEM の統合

組織でセキュリティインシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 Advanced Threat Protection を SIEM サーバーに統合することができます。 SIEM の統合により、SIEM サーバーのレポートにある、Office 365 Advanced Protection によって検出されたマルウェアやフィッシングなどの情報を表示できます。 SIEM 統合をセットアップするには、 [Office 365 アクティビティ管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用します。 

Office 365 Activity Management API は、組織の Office 365 および Azure Active Directory のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得します。 [Office 365 Advanced Threat protection スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)は Advanced threat protection と共に動作するため、組織が Office 365 Advanced Threat protection プラン1または Plan 2 または Office 365 E5 を使用している場合でも、SIEM サーバー統合に同じ API を使用できます。 

SIEM サーバーまたはその他の同様のシステムが監査をポーリングする必要があり**ます。一般的な**ワークロードを検出イベントにアクセスします。 詳細については、「 [Office 365 Management api の概要](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)」を参照してください。 また、 **AuditLogRecordType**の次の値は、OFFICE 365 ATP イベントに関連しています。

### <a name="enum-auditlogrecordtype---type-edmint32"></a>列挙値: AuditLogRecordType - 型: Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|値|メンバ名|説明|
|:-----|:-----|:-----|
|個|ThreatIntelligence|Exchange Online Protection と Office 365 Advanced Threat Protection からのフィッシングとマルウェアのイベント。|
|41|ThreatIntelligenceUrl|ATP の安全なリンクは、Office 365 Advanced Threat Protection からのイベントをブロックする時間とブロックします。|
|47|ThreatIntelligenceAtpContent|SharePoint Online、OneDrive for Business、および Microsoft Teams for Office 365 Advanced Threat Protection のファイルのフィッシングとマルウェアイベント。|

> [!IMPORTANT]
> Office 365 のグローバル管理者であるか、セキュリティ & コンプライアンスセンターに対してセキュリティ管理者の役割が割り当てられている必要があります。これは、SIEM と Office 365 Advanced Threat Protection を統合するための設定です。<br/>Office 365 環境の監査ログを有効にする必要があります。 この問題に関するヘルプを表示するには、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。

## <a name="related-topics"></a>関連項目

[Office 365 の脅威の調査と対応](office-365-ti.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Office 365 セキュリティ&amp; /コンプライアンスセンターのスマートレポートと洞察](reports-and-insights-in-security-and-compliance.md)
  
[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  
