---
title: Office 365 のリソースの制限
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
description: '概要: Office 365 内でさまざまなアプリケーションのリソースに関する情報が制限されています。'
ms.openlocfilehash: a2e7ef42f9bf224363f3b10a5e450d6127f11585
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532814"
---
# <a name="resource-limits"></a>リソースの制限

クォータ (制限) を使用し、調整、リソースの制限が適用されます。Azure Active Directory および個々 の Office 365 サービスは、両方を使用します。制限はサービス固有であるため、新機能を追加すると、時間の経過と共に変更します。さまざまなサービスの現在の制限の詳細については、次のトピックを参照してください。
- [Azure Active Directory サービスの制限と制限](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [Exchange Online の制限](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [Exchange Online Protection の制限](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [SharePoint Online ソフトウェアの境界と制限](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [Skype ビジネスの制限について](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [Yammer REST API およびレートの制限](https://developer.yammer.com/docs/rest-api-rate-limits)
- [ファイル サイズの制限に影響を与える](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

これらの制限だけでなくいくつかの調整メカニズムは、Azure Active Directory と Office 365 の全体で使用されます。サービス内での調整が特に重要に、マイクロソフトのデータ センター内のネットワーク リソースは、広範なサービスを使用するお客様用に最適化されました。調整のメカニズムは次のとおりです。
- Azure Active Directory と Office 365 機能ユーザー ・ レベルの調整、トランザクション、または 1 人のユーザーで実行できる (スクリプトまたはコード) での同時呼び出しの数を制限します。
- 既定のポリシーを調整する PowerShell は、テナントの作成時に、各テナントに割り当てられます。これらの設定は、1 人の管理者が開くことができる同時の PowerShell セッションの最大数などの項目を影響します。
- 各 Exchange オンラインのお客様は、クライアント ・ オペレーションは EWS のチューニングは、既定の Exchange Web サービス (EWS) ポリシーを持っているし、すべての Outlook クライアントに適用する調整します。
