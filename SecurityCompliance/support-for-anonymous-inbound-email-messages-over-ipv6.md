---
title: IPv6 経由の匿名受信電子メール メッセージのサポート
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
description: IPv6 のソースからの匿名のメッセージを Exchange のオンライン保護と Exchange のオンラインのサポートを構成する方法について説明します。
ms.openlocfilehash: 0d324ce6e0ff0ff9104ef597176b09a5a319abc7
ms.sourcegitcommit: 75b985b2574f4be70cf352498ea300b3d99dd338
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "26255812"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>IPv6 経由の匿名受信電子メール メッセージのサポート

Exchange オンライン保護 (EOP) および Exchange Online は、トランスポート層セキュリティ (TLS) 経由でメッセージを送信しないユーザーの送信者からの IPv6 通信経由の匿名の受信電子メール メッセージの受信をサポートします。ことができますオプトイン IPv6 経由でマイクロソフトのサポートから Office 365 の管理センターを開くことでこの機能を要求することによってメッセージを受信する[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)、**サポート**をクリックし、**新しいサービス要求**) します。しないに IPv6 の場合、IPv4 経由でメッセージを受信する続行するでしょう。
  
IPv6 経由でメッセージをサービスに送信する送信者は、次の 2 つの要件を満たす必要があります。
  
1. 送信 IPv6 アドレスに有効な PTR レコード (送信 IPv6 アドレスの [DNS 逆引きレコード](https://en.wikipedia.org/wiki/Reverse_DNS_lookup)) を含める必要があります。 
    
2. また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](http://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。
    
これらの要件は、どの構成を使用する場合でも IPv6 にオプトインする前に満たす必要があります。両方の要件が満たされている場合、メッセージはサービスによって提供される通常の電子メール メッセージ フィルタリングを通過します。どちらかの要件が満たされていない場合には、メッセージは次の 450 応答のいずれかで拒否されます。
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
IPv6 経由でメッセージを受信するためにオプトインしていない状態で、送信者がメール サーバーに手動で接続することによって IPv6 経由のメッセージを強制しようとした場合には、メッセージは次のような 550 応答で拒否されます。
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>詳細情報

[DKIM 署名付きメッセージの検証をサポートする](support-for-validation-of-dkim-signed-messages.md)
  

