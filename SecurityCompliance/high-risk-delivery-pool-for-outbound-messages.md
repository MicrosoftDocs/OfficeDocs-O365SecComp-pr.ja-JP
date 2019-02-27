---
title: 送信メッセージにおける危険度の高い配信プール
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/24/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 顧客の電子メール システムがマルウェアまたは悪意のあるスパム攻撃によって侵害を受け、ホストされているフィルター サービスでスパムを送信していると、Office 365 データ センター サーバーの IP アドレスがサードパーティのブロック リストに表示されることがあります。
ms.openlocfilehash: 604fdf2df11b6dff493444fe9dbcc6f95ced6a7d
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275547"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>送信メッセージにおける危険度の高い配信プール

顧客の電子メール システムがマルウェアまたは悪意のあるスパム攻撃によって侵害を受け、ホストされているフィルター サービスでスパムを送信していると、Office 365 データ センター サーバーの IP アドレスがサードパーティのブロック リストに表示されることがあります。ホストされているフィルター サービスは使用しなくても、このブロック リストを使用する宛先サーバーは、そのリストに追加された、ホストされているフィルター IP アドレスから送信されたすべての電子メールを拒否します。これを避けるために、スパムしきい値を超えるすべての送信メッセージが、危険度の高い配信プールで配信されます。この補助的な送信電子メール プールは、低品質になることがあるメッセージの送信にのみ使用されます。これは、送信 IP アドレスがブロックされる可能性が高いメッセージを残りのネットワークが送信しないように保護します。
  
専用のより危険度の高い配信プールを使用すると、高品質であることがわかっているメッセージのみを通常の送信プールが送信するようになります。この補助的な IP プールを使用することにより、通常の送信 IP プールが禁止リストに追加される可能性が低くなります。より危険度の高い配信プールが禁止リストに含まれる危険性は残りますが、これは仕様です。
  
送信側ドメインにアドレス レコード (A レコード、そのドメインの IP アドレスを提供する) がないメッセージ、および送信側ドメインに MX レコード (DNS に含まれる特定のドメインに対するメールを受信するサーバーへメールを送信するために役立つ) がないメッセージは、スパムの傾向に関係なく、常に危険度の高い配信プールでルーティングされます。
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>カスタマイズ可能な配信状態通知 (DSN) メッセージについて

送信用の危険度の高い配信プールは、すべての「返送された」か「失敗した」かの (DSN) メッセージの配信を管理します。
  
DSN メッセージの急増の原因は、次のとおりです。
  
- サービスを使用しているいずれかの顧客に影響を与えるスプーフィング キャンペーン
    
- ディレクトリ獲得攻撃
    
- スパム攻撃
    
- 承認されていない SMTP サーバー
    
これらのすべての問題により、サービスが処理する DSN メッセージの数が急増する結果となることがあります。多くの場合、このような DSN メッセージは、その他の電子メールサーバーやサービスのスパムとなることがあります。
  
## <a name="for-more-information"></a>詳細情報

[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)
  
[スパム対策保護に関する FAQ](anti-spam-protection-faq.md)
  

