---
title: バルク メール業者の差出人セーフ リストを管理する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
description: '差出人セーフ リストを使用する場合は、Exchange Online Protection (EOP) と Outlook で処理が異なることを認識しておく必要があります。サービスでは RFC 5321.MailFrom アドレスと RFC 5322.From アドレスを検査することによって信頼できる差出人とドメインを尊重するのに対して、Outlook では RFC 5322.From アドレスをユーザーの差出人セーフ リストに追加します (注 : サービスは、ブロックする差出人とドメインについては、5321.MailFrom アドレスと 5322.From アドレスの両方を検査します)。'
ms.openlocfilehash: e5d6f8440281d527e7ea1846416b785beda25f1c
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026544"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>バルク メール業者の差出人セーフ リストを管理する

差出人セーフ リストを使用する場合は、Exchange Online Protection (EOP) と Outlook で処理が異なることを認識しておく必要があります。サービスでは RFC 5321.MailFrom アドレスと RFC 5322.From アドレスを検査することによって信頼できる差出人とドメインを尊重するのに対して、Outlook では RFC 5322.From アドレスをユーザーの差出人セーフ リストに追加します (注 : サービスは、ブロックする差出人とドメインについては、5321.MailFrom アドレスと 5322.From アドレスの両方を検査します)。
  
RFC 5321.MailFrom アドレスとも呼ばれる SMTP MAIL FROM アドレスは、SPF チェックの実行に使用される電子メール アドレスで、メールが配信できない場合に返送されるメッセージが配信されるパスです。メッセージ ヘッダーの Return-Path に既定で配置されるのはこの電子メール アドレスですが、差出人は異なる Return-Path アドレスを指定することができます。
  
RFC 5322.From アドレスとも呼ばれるメッセージ ヘッダー内の差出人アドレスは、Outlook などのメール クライアントに表示される電子メール アドレスです。
  
大抵の場合、5321.MailFrom アドレスと 5322.From アドレスは同じです。このことは、人間同士のコミュニケーションではよく見られることです。ただし、他のユーザーに代わって電子メールが送信される場合は、これらのアドレスが異なるのが普通です。大部分のバルク メール メッセージでは、ほとんどの場合にそのようになります。
  
たとえば、Blue Yonder Airlines 航空が Margie's Travel に電子メール広告の配信を外注したとします。受信トレイに入るメッセージの差出人は blueyonder@news.blueyonderairlines.com です。この場合、5321.MailFrom アドレスは blueyonder.airlines@margiestravel.com であり、blueyonder@news.blueyonderairlines.com は Outlook で表示される 5322.From アドレスです。サービスでは RFC 5322.From アドレスが尊重されるため、このメッセージがフィルターで除外されないようにするには、単に RFC 5322.From アドレスを Outlook の信頼できる差出人として追加するだけで済みます。
  

