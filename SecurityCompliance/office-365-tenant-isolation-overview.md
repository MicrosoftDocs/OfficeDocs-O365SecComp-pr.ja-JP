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
# <a name="tenant-isolation-in-office-365"></a><span data-ttu-id="e0e02-103">Office 365 のテナントの分離</span><span class="sxs-lookup"><span data-stu-id="e0e02-103">Tenant Isolation in Office 365</span></span>

<span data-ttu-id="e0e02-p101">クラウド コンピューティングの多くのお客様の間で共有、共通のインフラストラクチャの概念を同時には、規模の経済をリードする主な利点の 1 つです。この概念には、*マルチ テナント機能*をが呼び出されます。マイクロソフトは、クラウド サービスのマルチ テナント型アーキテクチャがエンタープライズ レベルのセキュリティ、機密性、プライバシー、整合性、および可用性の標準をサポートしていることを確認するのには継続的に動作します。</span><span class="sxs-lookup"><span data-stu-id="e0e02-p101">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale. This concept is called *multi-tenancy*. Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="e0e02-107">マイクロソフトのクラウド サービスは、多大な投資と[信頼できるコンピューティング](https://www.microsoft.com/en-us/twc/default.aspx)の[セキュリティ開発ライフ サイクル](http://www.microsoft.com/security/sdl/default.aspx)から蓄積した経験に基づいて、すべてのテナントがすべてに悪意のある可能性があることを前提に設計されました。、他のテナントとは、セキュリティや、他のテナントのサービスに影響を与えたり、他のテナントのコンテンツにアクセスするから 1 つのテナントのアクションを禁止するセキュリティ対策を実装しています。</span><span class="sxs-lookup"><span data-stu-id="e0e02-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/en-us/twc/default.aspx) and the [Security Development Lifecycle](http://www.microsoft.com/security/sdl/default.aspx), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="e0e02-108">マルチ テナント環境でのテナントの分離を維持するための 2 つの主な目標は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0e02-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>
1.  <span data-ttu-id="e0e02-109">テナントの間で、お客様のコンテンツへの漏洩や不正アクセスを防止します。そして</span><span class="sxs-lookup"><span data-stu-id="e0e02-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.  <span data-ttu-id="e0e02-110">悪影響を別のテナントのサービスから 1 つのテナントの操作を防止します。</span><span class="sxs-lookup"><span data-stu-id="e0e02-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="e0e02-111">保護の複数のフォームは、妥協することの Office 365 サービスまたはアプリケーション、またはその他のテナントを含め、Office 365 システム自体の情報への無許可アクセスを獲得から顧客を防ぐために Office 365 で実装されています。</span><span class="sxs-lookup"><span data-stu-id="e0e02-111">Multiple forms of protection have been implemented throughout Office 365 to prevent customers from compromising Office 365 services or applications or gaining unauthorized access to the information of other tenants or the Office 365 system itself, including:</span></span>
- <span data-ttu-id="e0e02-112">Office 365 サービスの各テナント内の顧客のコンテンツの論理的分離は、Azure Active Directory 承認およびロールベースのアクセス制御を実現します。</span><span class="sxs-lookup"><span data-stu-id="e0e02-112">Logical isolation of customer content within each tenant for Office 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="e0e02-113">SharePoint Online には、ストレージ ・ レベルでのデータの分離のメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e0e02-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="e0e02-p102">マイクロソフトでは、お客様のコンテンツの完全性と機密性を保護するために厳密な物理的なセキュリティ、経歴審査、および複数層の暗号化戦略を使用します。すべての Office 365 のデータ センター生体測定式アクセスを持つコントロールを物理的にアクセスするのにはパーム プリントを最も必要とします。さらに、すべての米国ベースの Microsoft の従業員は、人材採用プロセスの一部として標準的なバック グラウンド チェックが正常に完了する必要があります。Office 365 の管理者のアクセスに使用されるコントロールの詳細については、 [Office 365 の管理者アクセスの制御](office-365-administrative-access-controls-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0e02-p102">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content. All Office 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access. In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process. For more information on the controls used for administrative access in Office 365, see [Office 365 Administrative Access Controls](office-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="e0e02-p103">Office 365 は、残りの部分で、BitLocker は、ファイルごとの暗号化を含む、移動中のお客様のコンテンツを暗号化するサービス側の技術を使用してトランスポート層セキュリティ (TLS) とインターネット プロトコル セキュリティ (IPsec)。特定の詳細については、Office 365 での暗号化では、 [Office 365 のデータの暗号化テクノロジ](office-365-encryption-in-the-microsoft-cloud-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0e02-p103">Office 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec). For specific details about encryption in Office 365, see [Data Encryption Technologies in Office 365](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="e0e02-120">同時に、上記の保護は、保護の脅威および軽減だけでは物理的な分離によって提供されるのと同じを提供する論理的分離の堅牢なコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="e0e02-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="e0e02-121">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e0e02-121">Related Links</span></span>
- [<span data-ttu-id="e0e02-122">Azure Active Directory での分離とアクセス制御</span><span class="sxs-lookup"><span data-stu-id="e0e02-122">Isolation and Access Control in Azure Active Directory</span></span>](office-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="e0e02-123">Office Graph と Delve でのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="e0e02-123">Tenant Isolation in the Office Graph and Delve</span></span>](office-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="e0e02-124">Office 365 の検索でのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="e0e02-124">Tenant Isolation in Office 365 Search</span></span>](office-365-isolation-in-office-365-search.md)
- [<span data-ttu-id="e0e02-125">Office 365 でのテナントの分離のビデオ</span><span class="sxs-lookup"><span data-stu-id="e0e02-125">Tenant Isolation in Office 365 Video</span></span>](office-365-isolation-in-office-365-video.md)
- [<span data-ttu-id="e0e02-126">リソースの制限</span><span class="sxs-lookup"><span data-stu-id="e0e02-126">Resource Limits</span></span>](office-365-resource-limits.md)
- [<span data-ttu-id="e0e02-127">テナント境界の監視とテスト</span><span class="sxs-lookup"><span data-stu-id="e0e02-127">Monitoring and Testing Tenant Boundaries</span></span>](office-365-monitoring-and-testing.md)
- [<span data-ttu-id="e0e02-128">Office 365 での分離とアクセス制御</span><span class="sxs-lookup"><span data-stu-id="e0e02-128">Isolation and Access Control in Office 365</span></span>](office-365-isolation-in-office-365.md)