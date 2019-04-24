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
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>Office 365 でのアクセス制御の監視と監査

Microsoft は、すべての委任、特権のすべての使用、および Office 365 内で発生するすべての操作の広範な監視と監査を行います。 Office 365 のアクセス制御は、最小限の特権の原則に基づいて構築された自動化されたプロセスであり、データアクセス制御と監査を組み込むためのものです。
- 許可されているすべてのアクセスが一意のユーザーに追跡可能になり、管理者は顧客コンテンツの処理についての責任を負うことができます。
- アクセス制御の要求、承認、および管理操作ログは、セキュリティ insights および悪意のあるイベントを分析するためにキャプチャされます。
- アクセスレベルは、セキュリティグループのメンバーシップに基づいてほぼリアルタイムで確認されており、ビジネスの正当な妥当性を持つユーザーのみがシステムにアクセスできるようにします。
- Office 365、そのアクセス制御、および Azure Active Directory と物理データセンターを含むサポートサービスは、 [ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001)、 [iso/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC)に準拠するために、独立したサードパーティによって定期的に監査されます。[fedramp](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)およびその他の[規格](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons)。
- Office 365 のエンジニアは、昇格したアクセスのベストプラクティスとリスクを確認し、Microsoft のセキュリティおよびプライバシーポリシーに同意して、サービスへの資格を維持する必要があります。

短時間に複数の失敗したログインなど、疑わしい動作が検出されたときに自動通知がトリガーされます。 Office 365 セキュリティ対応チームは、機械学習と大規模データ分析を使用して、不規則なアクセスパターンのアクティビティを確認して分析し、異常なおよび不法なアクティビティに積極的に対応します。 また、Microsoft は、一連の侵入テスト担当者を採用しており、定期的に赤色のチームと青のチームの練習を行い、サービスのセキュリティとアクセス制御の問題を見つけます。 お客様は、Office 365 によって提供される監査レポートと管理アクティビティ API を使用して、アクセス制御システムの有効性を確認することもできます。 

詳細については、「office [365 Management Activity API reference](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) and [Auditing and Reporting in office 365](office-365-auditing-and-reporting-overview.md)」を参照してください。
