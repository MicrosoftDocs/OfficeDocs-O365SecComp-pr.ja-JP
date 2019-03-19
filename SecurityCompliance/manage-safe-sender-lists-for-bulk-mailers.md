---
title: バルク メール業者の差出人セーフ リストを管理する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: '差出人セーフ リストを使用する場合は、Exchange Online Protection (EOP) と Outlook で処理が異なることを認識しておく必要があります。サービスでは RFC 5321.MailFrom アドレスと RFC 5322.From アドレスを検査することによって信頼できる差出人とドメインを尊重するのに対して、Outlook では RFC 5322.From アドレスをユーザーの差出人セーフ リストに追加します (注 : サービスは、ブロックする差出人とドメインについては、5321.MailFrom アドレスと 5322.From アドレスの両方を検査します)。'
ms.openlocfilehash: cc0f74fccade2e9b3cb96bbab9ec72936df24bae
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670602"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>バルク メール業者の差出人セーフ リストを管理する

差出人セーフリストを使用する場合は、Exchange Online Protection (EOP) と Outlook が異なる方法で処理することに注意してください。 Office 365 サービスは、rfc 5321.mailfrom アドレスと rfc 5322.from from アドレスを検査することによって、安全な送信者とドメインを尊重しますが、Outlook は rfc 5322.from アドレスをユーザーの [差出人セーフリスト] に追加します。 (注: サービスは、ブロックされた送信者とドメインの5321.mailfrom アドレスと5322.from アドレスの両方を調べます。)
  
RFC 5321.MailFrom アドレスとも呼ばれる SMTP MAIL FROM アドレスは、SPF チェックの実行に使用される電子メール アドレスで、メールが配信できない場合に返送されるメッセージが配信されるパスです。メッセージ ヘッダーの Return-Path に既定で配置されるのはこの電子メール アドレスですが、差出人は異なる Return-Path アドレスを指定することができます。
  
RFC 5322.From アドレスとも呼ばれるメッセージ ヘッダー内の差出人アドレスは、Outlook などのメール クライアントに表示される電子メール アドレスです。
  
大抵の場合、5321.MailFrom アドレスと 5322.From アドレスは同じです。このことは、人間同士のコミュニケーションではよく見られることです。ただし、他のユーザーに代わって電子メールが送信される場合は、これらのアドレスが異なるのが普通です。大部分のバルク メール メッセージでは、ほとんどの場合にそのようになります。
  
たとえば、Blue Yonder Airlines 航空が Margie's Travel に電子メール広告の配信を外注したとします。 受信トレイに入るメッセージの差出人は blueyonder@news.blueyonderairlines.com です。 この例では、MailFrom address は blueyonder.airlines@margiestravel.com、blueyonder@news.blueyonderairlines.com は5321.mailfrom アドレスで、これは Outlook に表示されます。 このサービスは rfc 5322.from アドレスを尊重するため、このメッセージがフィルター処理されないようにするには、rfc 5322.from アドレスを Outlook (ユーザーとして)、または管理者が、スパム対策に示されているようにメールフロールールを設定している場合には、信頼できる差出人として登録します。 [保護](anti-spam-protection.md)] セクション
  

