---
title: SIEM Microsoft 365 とサーバーの統合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- SIEM
description: '概要: は、SIEM Microsoft 365 とサーバーの統合の概要を取得するには、この記事を読みます。'
ms.openlocfilehash: bd512ca6d75928712e3444581a78610a0869123d
ms.sourcegitcommit: 63ed467fc3e1ab1ab9ee122df97c64737169834e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842685"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM Microsoft 365 のサービスおよびアプリケーションとサーバの統合

## <a name="overview"></a>概要

組織が、セキュリティ情報およびイベント管理 (SIEM) サーバーを使用する場合、または SIEM サーバーをすぐに取得することを計画している場合は、する依存関係をすることをどのように統合 Office 365 の企業を含む、Microsoft の 365 です。SIEM サーバーする必要があるかどうかは、組織のセキュリティ要件など、多くの要因によって異なります。Microsoft 365 には、さまざまなセキュリティ機能が用意されています。ただし、組織の設置型とクラウド (ハイブリッド クラウドの展開の場合) のようにコンテンツやアプリケーションが、余分な保護のための SIEM サーバーを追加を検討可能性があります。または、特別、厳格なセキュリティ要件を満たす必要がありますがある場合、は、SIEM サーバーを環境内に追加を検討する可能性があります。

## <a name="siem-server-integration-microsoft-365"></a>SIEM サーバー統合 Microsoft 365

SIEM サーバーは、さまざまな Microsoft 365 サービスとアプリケーションからデータを受信できます。次の表に、いくつかの Microsoft 365 サービスと SIEM サーバーの入力と SIEM サーバ統合の詳細についての参照先のアプリケーションを示します。 

| Microsoft 365 サービスまたはアプリケーション | SIEM サーバーの入力 | リソースの詳細 |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md) <br/>   または   <br/>[Office 365 脅威インテリジェンス](office-365-ti.md) | 監査ログ | [Office 365 の脅威インテリジェンスと脅威の高度な保護と SIEM の統合](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | ログの統合 | [マイクロソフト クラウド アプリケーションのセキュリティと SIEM の統合](https://docs.microsoft.com/cloud-app-security/siem) |
| [Office 365 Cloud App Security](office-365-cas-overview.md) | ログの統合 | [SIEM サーバーと Office 365 Cloud App Security を統合する](integrate-your-siem-server-with-office-365-cas.md) |
| [Windows Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | ログの統合 | [SIEM ツールに警告をプルします。](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| [Azure のセキュリティ センター](https://docs.microsoft.com/azure/security-center/security-center-intro)(脅威保護し、脅威の検出) | 警告 | [SIEM のパイプラインの構成 - プレビューに azure のセキュリティ データをエクスポートします。](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [Azure Active Directory Id の保護](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | 監査ログ | [Azure Active Directory の監査ログを統合します。](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [Azure の高度な脅威の分析](https://docs.microsoft.com/azure/security/azure-threat-detection) | ログの統合 | [ATA SIEM のログの参照](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要があります。

SIEM サーバー統合を構成する前に監査ログを有効にすることを確認します。 

- SharePoint、オンライン ビジネス、および、Azure Active Directory の[セキュリティとコンプライアンス ・ センターの監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)するための OneDrive です。

- Exchange オンラインで[Windows PowerShell で監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)します。
 
## <a name="see-also"></a>関連項目

[クラウド導入およびハイブリッド ソリューション](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[クラウド導入のテスト ラボ ガイド (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


