---
title: DKIM 署名付きメッセージの検証をサポートする
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: exchange online Protection と exchange online での dkim 署名付きメッセージの検証について
ms.openlocfilehash: 126586235d17fc123ed266d6c4ce5004df5df25a
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275907"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>DKIM 署名付きメッセージの検証をサポートする

Exchange Online Protection (EOP) と Exchange Online は、Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) メッセージの受信検証をサポートしています。DKIM は、メッセージが記載されている配信元のドメインから送信され、第三者によって偽造されていないことを検証するための手段です。これにより、電子メール メッセージがその送信を担当する組織に対応付けられます。DKIM 検証は IPv6 通信経由で送信されるすべてのメッセージに自動的に使用されます (IPv6 サポートの詳細については、「[IPv6 経由の匿名受信電子メール メッセージのサポート](support-for-anonymous-inbound-email-messages-over-ipv6.md)」を参照してください)。
  
DKIM は、メッセージ ヘッダー内の DKIM 署名ヘッダーに表示されるデジタル署名付きメッセージを検証します。DKIM 署名検証の結果は RFC 7001 ([メッセージ認証状態を示すためのメッセージ ヘッダー フィールド](https://www.rfc-editor.org/rfc/rfc7001.txt)) に準拠した認証結果ヘッダー内でスタンプされます。メッセージ ヘッダー テキストは次のように表示されます (contoso.com が送信者です)。
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
管理者は、dkim 検証の結果に対して Exchange[メールフロールール](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)(トランスポートルールとも呼ばれます) を作成し、必要に応じてメッセージをフィルター処理またはルーティングすることができます。 
  

