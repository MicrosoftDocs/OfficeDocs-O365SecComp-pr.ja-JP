---
title: DKIM 署名付きメッセージの検証をサポートする
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
description: Exchange Online Protection (EOP) と Exchange Online は、Domain Keys Identified Mail (DKIM) メッセージの受信検証をサポートしています。DKIM は、メッセージが記載されている配信元のドメインから送信され、第三者によって偽造されていないことを検証するための手段です。これにより、電子メール メッセージがその送信を担当する組織に対応付けられます。DKIM 検証は IPv6 通信経由で送信されるすべてのメッセージに自動的に使用されます (IPv6 サポートの詳細については、「IPv6 経由の匿名受信電子メール メッセージのサポート」を参照してください)。
ms.openlocfilehash: d2fab69847732bb7ed54f943d2c7845e06084936
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002268"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>DKIM 署名付きメッセージの検証をサポートする

Exchange Online Protection (EOP) と Exchange Online は、Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) メッセージの受信検証をサポートしています。DKIM は、メッセージが記載されている配信元のドメインから送信され、第三者によって偽造されていないことを検証するための手段です。これにより、電子メール メッセージがその送信を担当する組織に対応付けられます。DKIM 検証は IPv6 通信経由で送信されるすべてのメッセージに自動的に使用されます (IPv6 サポートの詳細については、「[IPv6 経由の匿名受信電子メール メッセージのサポート](support-for-anonymous-inbound-email-messages-over-ipv6.md)」を参照してください)。
  
DKIM は、メッセージ ヘッダー内の DKIM 署名ヘッダーに表示されるデジタル署名付きメッセージを検証します。DKIM 署名検証の結果は RFC 7001 ([メッセージ認証状態を示すためのメッセージ ヘッダー フィールド](https://www.rfc-editor.org/rfc/rfc7001.txt)) に準拠した認証結果ヘッダー内でスタンプされます。メッセージ ヘッダー テキストは次のように表示されます (contoso.com が送信者です)。
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
管理者は、DKIM 検証の結果に基づいて Exchange [Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) を作成し、必要に応じてメッセージをフィルター処理またはルーティングできます。 
  

