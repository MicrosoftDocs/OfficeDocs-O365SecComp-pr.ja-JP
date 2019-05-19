---
title: DKIM 署名付きメッセージの検証をサポートする
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Exchange Online Protection と Exchange Online での DKIM 署名付きメッセージの検証について
ms.openlocfilehash: 0538158d052afb632dc0adbb14a88aa9766e6322
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156449"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>DKIM 署名付きメッセージの検証をサポートする

Exchange Online Protection (EOP) と Exchange Online は、Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) メッセージの受信検証をサポートしています。DKIM は、メッセージが記載されている配信元のドメインから送信され、第三者によって偽造されていないことを検証するための手段です。これにより、電子メール メッセージがその送信を担当する組織に対応付けられます。DKIM 検証は IPv6 通信経由で送信されるすべてのメッセージに自動的に使用されます (IPv6 サポートの詳細については、「[IPv6 経由の匿名受信電子メール メッセージのサポート](support-for-anonymous-inbound-email-messages-over-ipv6.md)」を参照してください)。
  
DKIM は、メッセージ ヘッダー内の DKIM 署名ヘッダーに表示されるデジタル署名付きメッセージを検証します。DKIM 署名検証の結果は RFC 7001 ([メッセージ認証状態を示すためのメッセージ ヘッダー フィールド](https://www.rfc-editor.org/rfc/rfc7001.txt)) に準拠した認証結果ヘッダー内でスタンプされます。メッセージ ヘッダー テキストは次のように表示されます (contoso.com が送信者です)。
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
管理者は、DKIM 検証の結果に対して Exchange[メールフロールール](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)(トランスポートルールとも呼ばれます) を作成し、必要に応じてメッセージをフィルター処理またはルーティングすることができます。 
  

