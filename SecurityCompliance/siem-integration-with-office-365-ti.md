---
title: SIEM と Office 365 の脅威インテリジェンスおよび Advanced threat Protection との統合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.collection:
- M365-security-compliance
description: office 365 の脅威インテリジェンスと Advanced Threat Protection を使用して、組織の SIEM サーバーを office 365 アクティビティ管理 API と統合します。
ms.openlocfilehash: 68d2b4387c1af2363fbb67d0671edeaaa4dc652d
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357438"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a>SIEM と Office 365 の脅威インテリジェンスおよび Advanced threat Protection との統合

組織でセキュリティインシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 の脅威インテリジェンスと Advanced Threat Protection を SIEM サーバーに統合できます。SIEM の統合を使用すると、SIEM server レポートに、Office 365 の高度な保護と脅威のインテリジェンスによって検出されたマルウェアなどの情報を表示できます。SIEM 統合をセットアップするには、 [Office 365 アクティビティ管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用します。 

office 365 Activity Management API は、組織の office 365 および Azure Active Directory のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得します。[Office 365 advanced threat protection および脅威インテリジェンススキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)は、脅威インテリジェンスや advanced threat protection で機能するため、組織が高度な脅威保護を備えているが脅威インテリジェンスを持たない (またはその逆) 場合は、SIEM サーバーの統合にも同じ API を使用します。 

SIEM サーバーまたはその他の同様のシステムが監査をポーリングする必要があり**ます。一般的な**ワークロードを検出イベントにアクセスします。詳細については、「 [Office 365 Management api の概要](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)」を参照してください。 

> [!IMPORTANT]
> office 365 のグローバル管理者であるか、セキュリティ & コンプライアンスセンターに対してセキュリティ管理者の役割が割り当てられている必要があります。これは、SIEM と office 365 Advanced Threat Protection を統合するための設定です。<br/>Office 365 環境の監査ログを有効にする必要があります。この問題に関するヘルプを表示するには、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。

## <a name="related-topics"></a>関連項目

[Office 365 脅威インテリジェンス](office-365-ti.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Office 365 セキュリティ&amp; /コンプライアンスセンターのスマートレポートと洞察](reports-and-insights-in-security-and-compliance.md)
  
[Office 365 セキュリティ&amp; /コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)
  

