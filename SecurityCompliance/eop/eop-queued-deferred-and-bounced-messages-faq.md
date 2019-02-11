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
ms.openlocfilehash: 4b2c902adacd6e72e587aadaceecd22dd0084d85
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686427"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP のキューイング、保留、返送されるメッセージに関する FAQ

ここでは、Microsoft Exchange Online Protection (EOP) のフィルター処理中にキューイング、保留、または返送されるメッセージに関してよく寄せられる質問の回答を提供します。
  
 **Q. なぜメールはキューイングされるのですか?**
  
A. メール配信時に受信者のサーバーに接続できない場合、メッセージはキューイングされるか保留されます。ただし、受信者のネットワークから 500 番台のエラーが返された場合、メッセージは保留されません。
  
 **Q. メッセージはどのようなときに保留状態になるのですか?**
  
A. 受信者のサーバーに接続できず、受信者のサーバーから接続タイムアウトや接続拒否、400 番台のエラーなどの "一時的なエラー" が返された場合、メッセージは保留されます。500 番台のエラーなどの永続的なエラーが返された場合、メッセージは送信者に戻されます。
  
 **Q. メッセージが保留される期間と再試行の間隔はどのくらいですか?**
  
A. メッセージ遅延を 2 日間、キューに残ります。メッセージの再試行回数は、受信者のメール システムから返されます、エラーに基づいています。最初のいくつかの繰延は、15 分を 60 分の最大値を何度か再試行間隔を大きく (次の半ダースかそこら) 経由でのそれ以降の再試行で、小さいか。間隔の期間の拡張は、動的で、キューのサイズを内部のメッセージの優先順位などの複数の変数を考慮に入れる。Basic では、15 分は (または小さい) を開始するを展開するから次のいくつかの時間を 60 分の最大にします。
  
 **Q. メール サーバーが復元された後、キューイングされたメッセージはどのように配信されますか?**
  
A. メール サーバーが復元した後、キューに格納されたすべてのメッセージは、サーバーを利用できなくなったときに受信およびキューに格納された順序で自動的に処理されます。 
  

