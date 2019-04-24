---
title: SIEM server と Microsoft 365 の統合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: '概要: この記事では、SIEM server と Microsoft 365 の統合の概要について説明します。'
ms.openlocfilehash: 905f6fc9b6fd62748e25c27d6e5cdbedacc0f806
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260665"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM server と Microsoft 365 のサービスおよびアプリケーションの統合

## <a name="overview"></a>概要

組織でセキュリティ情報およびイベント管理 (SIEM) サーバーを使用している場合、または SIEM サーバーを近いうちに購入する予定の場合は、Office 365 Enterprise を含む Microsoft 365 との統合方法を疑問に思うかもしれません。 SIEM サーバーが必要かどうかは、組織のセキュリティ要件など、さまざまな要因によって異なります。 Microsoft 365 はさまざまなセキュリティ機能を提供しています。ただし、組織のコンテンツとアプリケーションがオンプレミスとクラウド (ハイブリッドクラウドの展開の場合など) にある場合は、追加の保護のために SIEM サーバーを追加することを検討してください。 または、組織が特に厳しいセキュリティ要件を満たしている場合は、SIEM サーバーを環境に追加することを検討する必要があります。

## <a name="siem-server-integration-microsoft-365"></a>SIEM server 統合 Microsoft 365

SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからのデータを受信できます。 次の表は、SIEM サーバーの入力と、SIEM サーバーの統合の詳細について説明するいくつかの Microsoft 365 サービスとアプリケーションを示しています。 

| Microsoft 365 サービスまたはアプリケーション | SIEM サーバーの入力 | 詳細については、リソースを参照してください |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md) <br/>   or   <br/>[Office 365 脅威インテリジェンス](office-365-ti.md) | 監査ログ | [Office 365 Advanced Threat Protection との SIEM の統合](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | ログの統合 | [SIEM と Microsoft Cloud App Security との統合](https://docs.microsoft.com/cloud-app-security/siem) |
| [Office 365 Cloud App Security](office-365-cas-overview.md) | ログの統合 | [SIEM サーバーと Office 365 Cloud App Security を統合する](integrate-your-siem-server-with-office-365-cas.md) |
| [Windows Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | ログの統合 | [SIEM ツールに通知を取得する](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| [Azure セキュリティセンター](https://docs.microsoft.com/azure/security-center/security-center-intro)(脅威の保護と脅威の検出) | アラート | [SIEM への Azure セキュリティデータのエクスポート-パイプライン構成-プレビュー](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | 監査ログ | [Azure Active Directory 監査ログを統合する](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [Azure Advanced Threat Analytics](https://docs.microsoft.com/azure/security/azure-threat-detection) | ログの統合 | [ATA SIEM ログリファレンス](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要がある

SIEM サーバーの統合を構成する前に、監査ログが有効になっていることを確認してください。 

- SharePoint Online、OneDrive for business、および Azure Active Directory で[は、セキュリティ & コンプライアンスセンターで監査ログが有効になっ](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)ています。

- Exchange Online で[は、Windows PowerShell を使用して監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)します。
 
## <a name="see-also"></a>関連項目

[クラウド導入およびハイブリッド ソリューション](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[クラウド導入のテスト ラボ ガイド (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


