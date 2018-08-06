---
title: EOP のキューイング、保留、返送されるメッセージに関する FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: ここでは、Microsoft Exchange Online Protection (EOP) のフィルター処理中にキューイング、保留、または返送されるメッセージに関してよく寄せられる質問の回答を提供します。
ms.openlocfilehash: 17e5955195c4e38299712fb9161822984b2a643a
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026224"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP のキューイング、保留、返送されるメッセージに関する FAQ

ここでは、Microsoft Exchange Online Protection (EOP) のフィルター処理中にキューイング、保留、または返送されるメッセージに関してよく寄せられる質問の回答を提供します。
  
 **Q. なぜメールはキューイングされるのですか?**
  
A. メール配信時に受信者のサーバーに接続できない場合、メッセージはキューイングされるか保留されます。ただし、受信者のネットワークから 500 番台のエラーが返された場合、メッセージは保留されません。
  
 **Q. メッセージはどのようなときに保留状態になるのですか?**
  
A. 受信者のサーバーに接続できず、受信者のサーバーから接続タイムアウトや接続拒否、400 番台のエラーなどの "一時的なエラー" が返された場合、メッセージは保留されます。500 番台のエラーなどの永続的なエラーが返された場合、メッセージは送信者に戻されます。
  
 **Q. メッセージが保留される期間と再試行の間隔はどのくらいですか?**
  
A. 保留状態のメッセージはキューに 2 日間保持されます。メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。平均では、5 分ごとにメッセージの送信が再試行されます。
  
 **Q. メール サーバーが復元された後、キューイングされたメッセージはどのように配信されますか?**
  
A. メール サーバーが復元した後、キューに格納されたすべてのメッセージは、サーバーを利用できなくなったときに受信およびキューに格納された順序で自動的に処理されます。 
  

