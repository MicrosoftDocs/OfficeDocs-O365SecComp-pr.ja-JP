---
title: Office 365 でのサービス拒否攻撃に対する防御
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: サービス拒否 (DoS) 攻撃の概要。
ms.openlocfilehash: 246704bff18c07d9b76281ae3c7071cd0d747630
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220507"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a>Office 365 でのサービス拒否攻撃に対する防御

## <a name="introduction"></a>はじめに
microsoft は、microsoft Azure、microsoft Bing、microsoft Office 365、microsoft Dynamics 365、microsoft OneDrive、Skype、Xbox Live などの200を超えるクラウドサービスのための信頼できるインフラストラクチャを提供しています。グローバルクラウドでホストされています。100を超えるデータセンターのインフラストラクチャ。

大規模なインターネットプレゼンスがあり、クラウドサービスを提供する多くの主要なインターネットプロパティを持つグローバル組織の場合、Microsoft はハッカーやその他の悪意のある個人にとって大きな共通の標的となります。ネットワーク--クライアントと Microsoft Cloud 間の通信レイヤーは、悪意のある攻撃の最大目標の1つです。実際、多くの場合、Microsoft は何らかの形式のネットワークベースの cyberattack を使用して継続的かつ永続的に実行されています。ほぼすべての時間で、Microsoft のインターネットプロパティの少なくとも1つは何らかの形で攻撃を受けています。このような攻撃から防御できる信頼性と永続的なリスク軽減システムがない場合、Microsoft のクラウドサービスはオフラインになり、お客様は利用できなくなります。

Microsoft では、多層防御セキュリティ原則を使用して、クラウドサービスとネットワークを保護しています。 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>サービス拒否攻撃の定義と現象
ネットワークサービスを攻撃する方法の1つは、サービスのホストに対して多数の要求を作成し、ネットワークやサーバーが正当なユーザーにサービスを拒否することです。これは、サービス拒否 (DoS) 攻撃と呼ばれます。複数のアクター、エンドポイント、またはベクトルによって攻撃が実行されると、その攻撃は分散型サービス拒否 (DDoS) 攻撃と呼ばれます。この方法は、motives とターゲットが異なることがありますが、DoS および DDoS 攻撃は一般に、インターネットサイトまたはサービスが、一時的または無限に機能しないようにするための個人または個人の努力から構成されます。

[米国のコンピュータエマージェンシーレディネスチーム](https://www.us-cert.gov/)(米国-CERT) は、次のものを含む DoS 攻撃の兆候を定義します。
- ネットワークのパフォーマンスが異常に遅くなる (ファイルを開くとき、またはインターネットサイトにアクセスするとき)
- Web サイトの利用不可
- Web サイトへのアクセス不可
- 受信したスパムが飛躍的に増加する
- ワイヤレスまたは有線のインターネット接続の切断
- Web またはインターネットサービスへのアクセスが長期間失われる

## <a name="related-topics"></a>関連トピック
- [サービス拒否攻撃に対する防御の主要な原則](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Microsoft のサービス拒否防御戦略](office-365-microsoft-dos-defense-strategy.md)
- [サービス拒否攻撃に対する Microsoft クラウドサービスの防御](office-365-defending-cloud-services-against-dos-attacks.md)
