---
title: エンド ユーザーのスパム通知を使ってスパム検疫済みメッセージを解放して報告する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: '検疫済みメールに関するエンドユーザーのスパム通知メッセージを管理者から取得したユーザーは、これらのメッセージに対してこれらの操作を行うことができます。 '
ms.openlocfilehash: f9a8cdf21dfae631b311651aa2259af2f76d73b8
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30691976"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a>エンド ユーザーのスパム通知を使ってスパム検疫済みメッセージを解放して報告する

[![TechNet から support.office.com に移動するコンテンツについてのイメージ内のテキスト](media/ab7c897a-4798-4f31-8c84-f17a8409b133.png)](https://go.microsoft.com/fwlink/p/?LinkID=624152)
  
管理者がエンドユーザーのスパム通知を有効にした場合、ユーザーは、自分のメールボックス宛てに送信されたメッセージのうち、スパムと特定されて検疫されたメッセージがリストされている通知メッセージを受信します。このメッセージには、列挙されたスパム検疫済みメッセージの数と、リスト内の最後のメッセージの日付と時刻 (世界協定時刻 (UTC)) が含まれています。このリストで、各メッセージに関する以下の情報を確認できます。 
  
- **送信者** 検疫されたメッセージの送信者名と電子メール アドレス。 
    
- **件名** 検疫されたメッセージの件名テキスト。 
    
- **日付** メッセージが検疫された日付と時刻 (UTC)。 
    
- **サイズ** 検疫されたメッセージのキロバイト (KB) 単位のサイズ。 
    
各メッセージに対して次の操作を行うことができます。
  
- **受信トレイに移動** このリンクをクリックすると、メッセージがそれを表示可能な受信トレイに送信されます。 
    
- **迷惑メールではないと報告** このリンクをクリックすると、メッセージのコピーが分析のために Microsoft に送信されます。スパム チームはメッセージの評価と分析を行い、分析結果に応じてスパム対策フィルター ルールを調整し、そのメッセージの通過を許可します。 
    
> [!NOTE]
>  メールフロールール (とも呼ばれます) が一致したために検疫されたメッセージは、エンドユーザースパム検疫済みメッセージには含まれません。 スパム検疫済みメッセージのみが列挙されます。 >  メッセージを移動して、それを誤検知 (迷惑メールではない) として報告できるのは一度だけです。 
  

