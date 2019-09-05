---
title: Office 365 でのサービス拒否攻撃に対する防御
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
description: サービス拒否 (DoS) 攻撃の概要。
ms.openlocfilehash: 94f87a11f396cb8ef09fd6d670d73ba8d1e88eda
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761663"
---
# <a name="defend-against-denial-of-service-attacks-in-office-365"></a>Office 365 でのサービス拒否攻撃に対する防御

## <a name="introduction"></a>はじめに

Microsoft は、100を超えるデータセンターのグローバルクラウドインフラストラクチャでホストされている200を超えるクラウドサービスのための信頼できるインフラストラクチャを提供しています。 これらには以下が含まれます。

- Microsoft Azure
- Microsoft Bing
- Microsoft Dynamics 365
- Microsoft Office 365
- Microsoft OneDrive
- Skype
- Xbox Live

大規模なインターネットプレゼンスがあり、クラウドサービスを提供する多くの主要なインターネットプロパティを持つグローバル組織の場合、Microsoft はハッカーやその他の悪意のある個人にとって大きな共通の標的となります。 クライアントと Microsoft クラウドとの間のネットワーク通信層は、悪意のある攻撃の最大目標の1つです。 実際、Microsoft は何らかの形式のネットワークベースの cyberattack で継続的かつ永続的に実行されています。 これを使用すると、Microsoft は多層防御セキュリティ原則を使用して、クラウドサービスとネットワークを保護します。 このような攻撃から防御する信頼性の高い永続的なリスク軽減システムがない場合は、Microsoft のクラウドサービスがオフラインになり、お客様が利用できなくなります。

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>サービス拒否攻撃の定義と現象

ネットワークサービスを攻撃する方法の1つは、サービスホストに対して多数の要求を作成して、ネットワークとサーバーが正規ユーザーからのサービスを拒否できるようにすることです。 これは、サービス拒否 (DoS) 攻撃と呼ばれます。 複数のアクター、エンドポイント、またはベクトルによって攻撃が実行されると、その攻撃は分散型サービス拒否 (DDoS) 攻撃と呼ばれます。 手段、motives、およびターゲットは異なりますが、DoS および DDoS 攻撃は、インターネットサイトまたはサービスが、一時的または無限に機能しないようにするための取り組みとなります。

[米国のコンピュータエマージェンシーレディネスチーム](https://www.us-cert.gov/)(米国-CERT) は、次のものを含む DoS 攻撃の兆候を定義します。

- ネットワークのパフォーマンスが異常に遅くなる (ファイルを開くとき、またはインターネットサイトにアクセスするとき)
- Web サイトの利用不可
- Web サイトへのアクセス不可
- 受信したスパムが飛躍的に増加する
- ワイヤレスまたは有線のインターネット接続の切断
- Web またはインターネットサービスへのアクセスが長期間失われる

## <a name="related-topics"></a>関連項目

- [サービス拒否攻撃に対する防御の主要な原則](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Microsoft のサービス拒否防御戦略](office-365-microsoft-dos-defense-strategy.md)
- [サービス拒否攻撃に対する Microsoft クラウドサービスの防御](office-365-defending-cloud-services-against-dos-attacks.md)
