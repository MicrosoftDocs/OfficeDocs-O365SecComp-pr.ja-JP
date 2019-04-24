---
title: バックスキャター メッセージと EOP
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: バックスキャター メッセージは、通常、スパムを受信した結果としてメール サーバーから送信される自動バウンス メッセージです。 バックスキャター DNSBL はバックスキャター メッセージを送信する IP アドレスのリストです。 スパム送信者のリストではないため、掲載されたサーバーがバックスキャター DNSBL から削除されることはありません。
ms.openlocfilehash: 62dd86d91e89e4f3c966b2969d0d763595bb5dc3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243898"
---
# <a name="backscatter-messages-and-eop"></a>バックスキャター メッセージと EOP

バックスキャター メッセージは、通常、スパムを受信した結果としてメール サーバーから送信される自動バウンス メッセージです。Exchange Online Protection (EOP) はスパム フィルタリング サービスのため、存在しない受信者やその他の疑わしい宛先への電子メール メッセージがこのサービスによって拒否されます。これが発生すると、EOP が配信不能レポート (NDR) メッセージを生成して、「送信者」に配信します。スパム送信者はメッセージ内で偽造したまたは無効な "差出人" アドレスを使用することが多いため、NDR が送信される送信者アドレスが原因でバックスキャター メッセージになる場合があります。この場合は、EOP ネットワークに関連付けられた送信サーバーがバックスキャター DNS 禁止リスト (DNSBL) に掲載される可能性があります。バックスキャター DNSBL はバックスキャター メッセージを送信する IP アドレスのリストです。スパム送信者のリストではないため、掲載されたサーバーがバックスキャター DNSBL から削除されることはありません。 
  
> [!TIP]
> バックスキャター Web サイト上の説明によれば、すべての受信メールに対する拒否モードの使用はそのサービスの構成または使用として推奨されていません。代わりに、セーフ モードで使用する必要があります。正しいバックスキャター構成の実装方法については、「[Backscatterer.org Web サイト](http://www.backscatterer.org/?target=usage)」を参照してください。 
  
## <a name="related-topics"></a>関連トピック
  
[高度なスパム対策フィルターオプション](advanced-spam-filtering-asf-options.md)
  

