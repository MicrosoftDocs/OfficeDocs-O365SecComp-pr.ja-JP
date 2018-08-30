---
title: Office 365 のサービス拒否の攻撃に対する防御
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
description: サービス拒否 (DoS) 攻撃の概要について説明します。
ms.openlocfilehash: b5a51ae332b32142d9ab993a29763b2160c3ce97
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531542"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a>Office 365 のサービス拒否の攻撃に対する防御

## <a name="introduction"></a>概要
マイクロソフトでは、200 以上のクラウド サービスについて、Microsoft Azure、マイクロソフトの Bing、Microsoft Office 365、Microsoft Dynamics 365、マイクロソフトの OneDrive、Skype、および Xbox Live を含む、グローバル クラウドでホストされている信頼できるインフラストラクチャを提供してください。100 以上のデータ センターのインフラストラクチャです。

重要なインターネット プレゼンスとクラウド サービスを提供する多くの著名なインターネット プロパティをグローバルな組織としては、マイクロソフトは、ハッカーや悪意のある他のユーザーの大規模な一般的なターゲットをします。ネットワーク クライアントとマイクロソフトのクラウド--間の通信レイヤーは、悪意のある攻撃の最大のターゲットのいずれかです。実際には、長年にわたって Microsoft が行われて継続的に永続的にネットワーク ・ ベースの cyberattack のいくつかのフォームの下にあります。、ほぼ常にマイクロソフトのインターネットのプロパティの少なくとも 1 つが発生している攻撃のいくつかのフォームです。信頼性と永続的なリスクの軽減、システムでこれらの攻撃を防ぐことができますマイクロソフトのクラウド サービスがなければ、オフラインにしてお客様に利用できません。

マイクロソフトでは、そのクラウド サービスとネットワークを保護するのに多層防御のセキュリティの原則を使用します。 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>定義と、サービス拒否の攻撃の症状
ネットワーク サービスを攻撃する方法の 1 つでは、サービスのホストに対するネットワークと正当なユーザーにサービスを拒否するようにサーバーが過負荷に多くの要求を作成します。これはサービス拒否 (DoS) 攻撃と呼ばれます。攻撃が実行すると、複数のアクター、エンドポイント、またはベクトルでは分散型サービス拒否 (DDoS) 攻撃と呼ばれます。手段、動機、およびターゲットが異なる場合、正しく機能しているからか、まったく、一時的または永続的にサービスやインターネット サイトを防ぐために個人または個人の努力の一般に DoS と DDoS 攻撃で構成されます。

(U. s. 証明書)、[米国のコンピューター緊急対応チーム](https://www.us-cert.gov/)には、DoS 攻撃の兆候が定義されています。
- ネットワークのパフォーマンスの低下を通常 (とファイルを開く、またはインターネット サイトにアクセスする)
- Web サイトが使用できません。
- Web サイトにアクセスすることができません。
- 受信したスパムの激増
- ワイヤレスやワイヤード (有線) のインターネット接続の切断
- Web または任意のインターネット サービスへのアクセスの長期的な損失

## <a name="related-topics"></a>関連項目
- [サービス拒否攻撃に対する防御の主要な原則](office-365-core-principles-of-defense-against-dos-attacks.md)
- [マイクロソフトのサービス拒否攻撃の防御戦略](office-365-microsoft-dos-defense-strategy.md)
- [マイクロソフトのクラウド サービスをサービス拒否の攻撃を防御](office-365-defending-cloud-services-against-dos-attacks.md)
