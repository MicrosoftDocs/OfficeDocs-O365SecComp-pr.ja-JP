---
title: Office 365 の監視および監査のアクセス制御
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
description: '概要: さまざまな監視および監査のアクセス コントロールの Office 365 内で利用可能な概要です。'
ms.openlocfilehash: 7ef25d62ce3c4fa320dd0b164183c6f67be7d76d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532669"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>監視し、Office 365 にアクセス制御の監査

マイクロソフトでは、広範な監視およびすべての委任、特権のすべての使用、および Office 365 内で発生するすべての操作の監査を実行します。Office 365 日のアクセス制御は自動化されたプロセスとデータ アクセスの制御と監査を組み込むことを最低限の特権の原則に基づいて構築されました。
- 許可されているすべてのアクセスは、管理者がお客様のコンテンツの処理に責任を持つ、一意のユーザーにトレースできます。
- セキュリティの見識や悪意のあるイベントの分析には、アクセス制御の要求、承認、および管理操作のログがキャプチャされます。
- 業務の妥当性を承認し、適格性の要件を満たしているユーザーのみがシステムにアクセスをできるようにするのにはリアルタイムのセキュリティ グループのメンバーシップの近くでのアクセス レベルを確認します。
- Office 365、アクセス ・ コントロール、およびサポート サービス、Azure Active Directory などの物理的なデータ センターが[ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001) [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC)に準拠するための独立したサード パーティによって定期的に監査します。[FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)、およびその他の[規格](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons)です。
- Office 365 のエンジニアは、年間のセキュリティ トレーニングを昇格したアクセスのベスト ・ プラクティスとリスクを確認して、マイクロソフトのセキュリティと引き続きサービスには、その権限を維持するためにプライバシー ポリシーを確認する必要があります。

自動化されたアラートは、短い期間内の複数の失敗したログインなど、不審な動作が検出されたときにトリガーされます。Office 365 のセキュリティ対応チームを確認し、不規則なアクセス ・ パターンの利用状況を分析して、異常や不正なアクティビティにプロアクティブに対応する機械学習と大きなデータの分析に使用します。マイクロソフトでは、侵入テスト担当者の専門チームを採用していますを実施しており定期的な赤チームと青チームのセキュリティし、サービスの管理の問題にアクセスするための演習。お客様は、監査レポートおよび管理アクティビティ Office 365 によって提供される API を使用してアクセス制御システムの有効性を確認することがありますもできます。 

詳細については、 [Office 365 の管理アクティビティの API リファレンス](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx)」および「[監査と Office 365 レポート](office-365-auditing-and-reporting-overview.md)を参照してください。
