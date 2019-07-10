---
title: SIEM server と Microsoft 365 の統合
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: '概要: この記事では、SIEM server と Microsoft 365 の統合の概要について説明します。'
ms.openlocfilehash: 97f1c1d1f1862d140e014b4460ac9f40cb1934bb
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600894"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM server と Microsoft 365 のサービスおよびアプリケーションの統合

## <a name="overview"></a>概要

組織でセキュリティ情報およびイベント管理 (SIEM) サーバーを使用している場合、または SIEM サーバーを近いうちに購入する予定の場合は、Office 365 E5 を含む Microsoft 365 との統合方法について不思議に思うかもしれません。 SIEM サーバーが必要かどうかは、組織のセキュリティ要件など、さまざまな要因によって異なります。 Microsoft 365 はさまざまなセキュリティ機能を提供しています。ただし、組織のコンテンツとアプリケーションがオンプレミスとクラウド (ハイブリッドクラウドの展開の場合など) にある場合は、追加の保護のために SIEM サーバーを追加することを検討してください。 または、組織が特に厳しいセキュリティ要件を満たしている場合は、SIEM サーバーを環境に追加することを検討する必要があります。

## <a name="siem-server-integration-microsoft-365"></a>SIEM server 統合 Microsoft 365

SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからのデータを受信できます。 次の表は、SIEM サーバーの入力と、SIEM サーバーの統合の詳細について説明するいくつかの Microsoft 365 サービスとアプリケーションを示しています。 

| Microsoft 365 サービスまたはアプリケーション | SIEM サーバーの入力 | 詳細については、リソースを参照してください |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md) <br/>または<br/>[Office 365 脅威インテリジェンス](office-365-ti.md) | 監査ログ | [Office 365 Advanced Threat Protection との SIEM の統合](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | ログの統合 | [SIEM と Microsoft Cloud App Security との統合](https://docs.microsoft.com/cloud-app-security/siem) |
| [Microsoft Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | ログの統合 | [SIEM ツールに通知を取得する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Azure セキュリティセンター](https://docs.microsoft.com/azure/security-center/security-center-intro)(脅威の保護と脅威の検出) | アラート | [SIEM への Azure セキュリティデータのエクスポート-パイプライン構成-プレビュー](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[Azure Advanced Threat Analytics](https://docs.microsoft.com/azure/security/azure-threat-detection) | Azure モニター | [発行Azure Monitor を使用して SIEM ツールと統合する](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |ログの統合 |[Microsoft Graph Security API の警告と SIEM の統合](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要がある

SIEM サーバーの統合を構成する前に、監査ログが有効になっていることを確認してください。 

- SharePoint Online、OneDrive for Business、および Azure Active Directory で[は、セキュリティ & コンプライアンスセンターで監査ログが有効になっ](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)ています。

- Exchange Online で[は、Windows PowerShell を使用して監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)します。
 
## <a name="see-also"></a>関連項目

[クラウド導入およびハイブリッド ソリューション](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[クラウド導入のテスト ラボ ガイド (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


