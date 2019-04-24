---
title: Office 365 の監視および監査アクセス制御
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
- M365-security-compliance
description: '概要: Office 365 で利用できるさまざまな監視および監査アクセス制御の概要について説明します。'
ms.openlocfilehash: 753acd1a0bd0d3b4a834263071d431b63836f399
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262539"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a><span data-ttu-id="932f3-103">Office 365 でのアクセス制御の監視と監査</span><span class="sxs-lookup"><span data-stu-id="932f3-103">Monitoring and Auditing Access Controls in Office 365</span></span>

<span data-ttu-id="932f3-104">Microsoft は、すべての委任、特権のすべての使用、および Office 365 内で発生するすべての操作の広範な監視と監査を行います。</span><span class="sxs-lookup"><span data-stu-id="932f3-104">Microsoft performs extensive monitoring and auditing of all delegation, all use of privileges, and all operations that occur within Office 365.</span></span> <span data-ttu-id="932f3-105">Office 365 のアクセス制御は、最小限の特権の原則に基づいて構築された自動化されたプロセスであり、データアクセス制御と監査を組み込むためのものです。</span><span class="sxs-lookup"><span data-stu-id="932f3-105">Office 365 access control is an automated process built on the principle of least privilege and to incorporate data access controls and audits:</span></span>
- <span data-ttu-id="932f3-106">許可されているすべてのアクセスが一意のユーザーに追跡可能になり、管理者は顧客コンテンツの処理についての責任を負うことができます。</span><span class="sxs-lookup"><span data-stu-id="932f3-106">All permitted access is traceable to a unique user, making administrators accountable for their handling of customer content.</span></span>
- <span data-ttu-id="932f3-107">アクセス制御の要求、承認、および管理操作ログは、セキュリティ insights および悪意のあるイベントを分析するためにキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="932f3-107">Access control requests, approvals, and administrative operations logs are captured for analysis of security insights and malicious events.</span></span>
- <span data-ttu-id="932f3-108">アクセスレベルは、セキュリティグループのメンバーシップに基づいてほぼリアルタイムで確認されており、ビジネスの正当な妥当性を持つユーザーのみがシステムにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="932f3-108">Access levels are reviewed in near real-time based on security group membership to ensure that only users who have authorized business justifications and meet the eligibility requirements have access to the systems.</span></span>
- <span data-ttu-id="932f3-109">Office 365、そのアクセス制御、および Azure Active Directory と物理データセンターを含むサポートサービスは、 [ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001)、 [iso/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC)に準拠するために、独立したサードパーティによって定期的に監査されます。[fedramp](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)およびその他の[規格](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons)。</span><span class="sxs-lookup"><span data-stu-id="932f3-109">Office 365, its access controls, and supporting services, including Azure Active Directory and our physical datacenters, are regularly audited by independent third-parties for compliance with [ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP), and other [standards](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons).</span></span>
- <span data-ttu-id="932f3-110">Office 365 のエンジニアは、昇格したアクセスのベストプラクティスとリスクを確認し、Microsoft のセキュリティおよびプライバシーポリシーに同意して、サービスへの資格を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="932f3-110">Office 365 engineers are required to take yearly security training reviewing elevated access best practices and risks and acknowledge Microsoft's security and privacy policies to continue maintaining their entitlements to the service.</span></span>

<span data-ttu-id="932f3-111">短時間に複数の失敗したログインなど、疑わしい動作が検出されたときに自動通知がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="932f3-111">Automated alerts are triggered when suspicious activity is detected, such as multiple failed logins within a short period.</span></span> <span data-ttu-id="932f3-112">Office 365 セキュリティ対応チームは、機械学習と大規模データ分析を使用して、不規則なアクセスパターンのアクティビティを確認して分析し、異常なおよび不法なアクティビティに積極的に対応します。</span><span class="sxs-lookup"><span data-stu-id="932f3-112">The Office 365 Security Response team uses machine learning and big data analysis to review and analyze activity for irregular access patterns and to proactively respond to anomalous and illicit activities.</span></span> <span data-ttu-id="932f3-113">また、Microsoft は、一連の侵入テスト担当者を採用しており、定期的に赤色のチームと青のチームの練習を行い、サービスのセキュリティとアクセス制御の問題を見つけます。</span><span class="sxs-lookup"><span data-stu-id="932f3-113">Microsoft also employs a dedicated team of penetration testers and engages in periodic red team and blue team exercises to find security and access control issues in the service.</span></span> <span data-ttu-id="932f3-114">お客様は、Office 365 によって提供される監査レポートと管理アクティビティ API を使用して、アクセス制御システムの有効性を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="932f3-114">Customers may also verify the effectiveness of access control systems by using audit reports and the management activity API provided by Office 365.</span></span> 

<span data-ttu-id="932f3-115">詳細については、「office [365 Management Activity API reference](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) and [Auditing and Reporting in office 365](office-365-auditing-and-reporting-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="932f3-115">For more information, see [Office 365 Management Activity API reference](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) and [Auditing and Reporting in Office 365](office-365-auditing-and-reporting-overview.md).</span></span>
