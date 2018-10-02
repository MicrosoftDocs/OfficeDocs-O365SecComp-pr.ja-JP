---
title: Exchange Online Protection の IP アドレス
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: eb14f38b-7b55-4a47-84a0-4a56a59e4111
description: メールの送受信、または Exchange Online Protection ポータルと管理サービスには、次の Microsoft データ センター IP アドレスが Microsoft Exchange Online Protection (EOP) によって使用されます。EOP からのメッセージを送受信するため、または管理サービスを使用するために、ネットワークでこれらの IP アドレスからの接続が許可されていることを確認してください。
ms.openlocfilehash: 5742c19f98f8515670150f69c421c19ffecc7668
ms.sourcegitcommit: b6473cd6ba3f9ac79dc6a2040fc148020dfbe464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "25358366"
---
# <a name="exchange-online-protection-ip-addresses"></a>Exchange Online Protection の IP アドレス

メールの送受信、または Exchange Online Protection ポータルと管理サービスには、次の Microsoft データ センター IP アドレスが Microsoft Exchange Online Protection (EOP) によって使用されます。EOP からのメッセージを送受信するため、または管理サービスを使用するために、ネットワークでこれらの IP アドレスからの接続が許可されていることを確認してください。
 
> [!NOTE]
> マイクロソフトでは、IP アドレスと FQDN エントリをこのページでの REST ベースの web サービスを開発しました。この新しいサービスを構成し、ファイアウォールやプロキシ サーバーなどのネットワーク境界デバイスを更新できます。エンドポイント、リスト、または特定の変更の現在のバージョンの一覧をダウンロードすることができます。このサービスは、XML ドキュメント、RSS フィード、および IP アドレスと FQDN エントリをこのページに置き換えられます。この新しいサービスを試して、 [Web サービス](https://support.office.com/article/managing-office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#webservice)に移動します。 
 
## <a name="eop-ip-address-ranges"></a>EOP IP アドレスの範囲

||||
|:-----|:-----|:-----|
|**IPv4 アドレスの範囲** <br/> |**IPv6 アドレスの範囲** <br/> |
| 23.103.132.0/22 | 2a01:111:f400:7 c 00::/54 |
| 23.103.136.0/21 | 2a01:111:f400:fc00::/54 |
| 23.103.144.0/20 | 2a01:111:f403::/48 |
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
> ここで提供されている IP アドレスの範囲は、お客様のコネクタを使用して中継ののみ使用されます。IP アドレスのリストへの変更はことはまれですと事前に通知されます。ビジネス パートナー、スマート ホスト、またはサービスの公開済み IP アドレスの範囲をオンプレミス環境のルートに送信するメッセージを構成すること必要がありますそれぞれの宛先にルーティングするための正しいコネクターにことを確認します。コネクタの詳細については、[使用するコネクタの決定](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)を参照してください。 ここでは IP アドレスが時間の経過とともに変更できます。IP のすべてのレコードに追加されているアドレスを変更、または、過去 1 年で廃止、 [EOP の IP アドレスの変更通知](change-notification-for-eop-ip-addresses.md)を参照してください。 
 
Microsoft Office 365 が使用する IP アドレスについて詳しくは、「[Office 365 の URL および IP アドレス範囲](https://go.microsoft.com/fwlink/p/?LinkId=324165)」を参照してください。

