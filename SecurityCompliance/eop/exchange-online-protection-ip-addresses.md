---
title: Exchange Online Protection の IP アドレス
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: eb14f38b-7b55-4a47-84a0-4a56a59e4111
description: メールの送受信、または Exchange Online Protection ポータルと管理サービスには、次の Microsoft データ センター IP アドレスが Microsoft Exchange Online Protection (EOP) によって使用されます。EOP からのメッセージを送受信するため、または管理サービスを使用するために、ネットワークでこれらの IP アドレスからの接続が許可されていることを確認してください。
ms.openlocfilehash: 6c7d8c78a012be3928317eac1e9b6fcdeab64a24
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222826"
---
# <a name="exchange-online-protection-ip-addresses"></a>Exchange Online Protection の IP アドレス

メールの送受信、または Exchange Online Protection ポータルと管理サービスには、次の Microsoft データ センター IP アドレスが Microsoft Exchange Online Protection (EOP) によって使用されます。EOP からのメッセージを送受信するため、または管理サービスを使用するために、ネットワークでこれらの IP アドレスからの接続が許可されていることを確認してください。
 
> [!NOTE]
> Microsoft は、このページの IP アドレスと FQDN エントリ用の REST ベースの web サービスを開発しました。この新しいサービスは、ファイアウォールやプロキシサーバーなどのネットワーク境界デバイスの構成と更新に役立てることができます。エンドポイントのリスト、リストの現在のバージョン、または特定の変更をダウンロードすることができます。このサービスは、このページの XML ドキュメント、RSS フィード、および IP アドレスと FQDN エントリを置き換えます。この新しいサービスを試すには、「 [Office 365 の IP アドレスと URL Web サービス](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)」にアクセスしてください。 
 
## <a name="eop-ip-address-ranges"></a>EOP IP アドレスの範囲

||||
|:-----|:-----|:-----|
|**IPv4 アドレス範囲** <br/> |**IPv6 アドレスの範囲** <br/> |
| 23.103.132.0/22 | 2a01: 111: f400: 7c00::/54 |
| 23.103.136.0/21 | 2a01: 111: f400: fc00::/54 |
| 23.103.144.0/20 | 2a01: 111: f403::/48 |
| 23.103.198.0/23 |  |
| 23.103.200.0/22 |  |
| 40.92.0.0/14 |  |
| 40.107.0.0/17 |  |
| 52.100.0.0/14 |  |
| 52.238.78.88/32 |  |
| 65.55.88.0/24 |  |
| 65.55.169.0/24 |  |
| 94.245.120.64/26 |  |
| 104.47.0.0/17 |  |
| 157.55.234.0/24 |  |
| 157.56.110.0/23 |  |
| 157.56.112.0/24 |  |
| 207.46.100.0/24 |  |
| 207.46.163.0/24 |  |
| 213.199.154.0/24 |  |
| 213.199.180.128/26 |  |
| 216.32.180.0/23 |  |
||||
 
> [!IMPORTANT]
> ここで提供されている IP アドレスの範囲は、顧客コネクタ経由の中継にのみ使用されます。IP アドレスの一覧に対する変更はめったにありません。事前に伝達されています。ビジネスパートナー、スマートホスト、またはオンプレミス環境に送信されるメッセージが、サービスの公開された IP アドレスの範囲を経由してルーティングされるようにするには、各宛先にルーティングするための正しいコネクタを構成する必要があります。コネクタの詳細については、「[使用するコネクタを決定する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)」を参照してください。このトピックの IP アドレスは、時間の経過とともに変化する可能性があります。  
 
Microsoft Office 365 が使用する IP アドレスについて詳しくは、「[Office 365 の URL および IP アドレス範囲](https://go.microsoft.com/fwlink/p/?LinkId=324165)」を参照してください。

