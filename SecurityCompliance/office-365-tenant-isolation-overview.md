---
title: Office 365 のテナントの分離
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
description: マイクロソフトが Office 365 のテナントの分離を強制する方法の概要です。
ms.openlocfilehash: fcf66ee65c2a4cfdf73ae0eac77f54bd555d059d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532212"
---
# <a name="tenant-isolation-in-office-365"></a>Office 365 のテナントの分離

クラウド コンピューティングの多くのお客様の間で共有、共通のインフラストラクチャの概念を同時には、規模の経済をリードする主な利点の 1 つです。この概念には、*マルチ テナント機能*をが呼び出されます。マイクロソフトは、クラウド サービスのマルチ テナント型アーキテクチャがエンタープライズ レベルのセキュリティ、機密性、プライバシー、整合性、および可用性の標準をサポートしていることを確認するのには継続的に動作します。

マイクロソフトのクラウド サービスは、多大な投資と[信頼できるコンピューティング](https://www.microsoft.com/en-us/twc/default.aspx)の[セキュリティ開発ライフ サイクル](http://www.microsoft.com/security/sdl/default.aspx)から蓄積した経験に基づいて、すべてのテナントがすべてに悪意のある可能性があることを前提に設計されました。、他のテナントとは、セキュリティや、他のテナントのサービスに影響を与えたり、他のテナントのコンテンツにアクセスするから 1 つのテナントのアクションを禁止するセキュリティ対策を実装しています。

マルチ テナント環境でのテナントの分離を維持するための 2 つの主な目標は次のとおりです。
1.  テナントの間で、お客様のコンテンツへの漏洩や不正アクセスを防止します。そして
2.  悪影響を別のテナントのサービスから 1 つのテナントの操作を防止します。

保護の複数のフォームは、妥協することの Office 365 サービスまたはアプリケーション、またはその他のテナントを含め、Office 365 システム自体の情報への無許可アクセスを獲得から顧客を防ぐために Office 365 で実装されています。
- Office 365 サービスの各テナント内の顧客のコンテンツの論理的分離は、Azure Active Directory 承認およびロールベースのアクセス制御を実現します。
- SharePoint Online には、ストレージ ・ レベルでのデータの分離のメカニズムが用意されています。
- マイクロソフトでは、お客様のコンテンツの完全性と機密性を保護するために厳密な物理的なセキュリティ、経歴審査、および複数層の暗号化戦略を使用します。すべての Office 365 のデータ センター生体測定式アクセスを持つコントロールを物理的にアクセスするのにはパーム プリントを最も必要とします。さらに、すべての米国ベースの Microsoft の従業員は、人材採用プロセスの一部として標準的なバック グラウンド チェックが正常に完了する必要があります。Office 365 の管理者のアクセスに使用されるコントロールの詳細については、 [Office 365 の管理者アクセスの制御](office-365-administrative-access-controls-overview.md)を参照してください。
- Office 365 は、残りの部分で、BitLocker は、ファイルごとの暗号化を含む、移動中のお客様のコンテンツを暗号化するサービス側の技術を使用してトランスポート層セキュリティ (TLS) とインターネット プロトコル セキュリティ (IPsec)。特定の詳細については、Office 365 での暗号化では、 [Office 365 のデータの暗号化テクノロジ](office-365-encryption-in-the-microsoft-cloud-overview.md)を参照してください。

同時に、上記の保護は、保護の脅威および軽減だけでは物理的な分離によって提供されるのと同じを提供する論理的分離の堅牢なコントロールを提供します。

## <a name="related-links"></a>関連リンク
- [Azure Active Directory での分離とアクセス制御](office-365-isolation-in-azure-active-directory.md)
- [Office Graph と Delve でのテナントの分離](office-365-isolation-in-graph-and-delve.md)
- [Office 365 の検索でのテナントの分離](office-365-isolation-in-office-365-search.md)
- [Office 365 でのテナントの分離のビデオ](office-365-isolation-in-office-365-video.md)
- [リソースの制限](office-365-resource-limits.md)
- [テナント境界の監視とテスト](office-365-monitoring-and-testing.md)
- [Office 365 での分離とアクセス制御](office-365-isolation-in-office-365.md)