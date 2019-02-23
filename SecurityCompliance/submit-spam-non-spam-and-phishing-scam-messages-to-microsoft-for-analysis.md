---
title: スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
description: 'ユーザーは、誤検出および誤検知のスパムメッセージを分析のために Microsoft に送信することができます。 '
ms.openlocfilehash: 584331411c836e25f2818cfb8ed9f1596910cc53
ms.sourcegitcommit: 06d6e63225f912d0f3c6bb836c61eb11c1dbe97a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "30206530"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a>スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する

組織内のユーザーが迷惑メール (スパム) またはフィッシング詐欺メッセージを受信トレイで受信する場合や、迷惑メールとしてマークされているために正当な電子メールメッセージを受信しない場合は、ストレスが発生する可能性があります。より正確になるように、スパムフィルターを常に微調整しています。この処理は、誤検出および誤検知のスパムメッセージを分析のために Microsoft に送信することによって、ユーザーが支援します。"誤負" は、スパムとして識別されていないものの、スパムメッセージであることを示します。"偽陽性" は、誤ってスパムとして識別された正当な電子メールメッセージです。 
  
> [!NOTE]
> 大量の送信が送信されるため、分析のすべての要求に応答できない場合があります。 
  
## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a>スパム フィルターを通過した迷惑メールまたはフィッシング詐欺メッセージを送信する
<a name="sectionSection0"> </a>

スパムフィルターを通過して、迷惑メールまたはフィッシング詐欺メールとして分類されるメッセージを受信した場合は、必要に応じて microsoft スパム分析チームと microsoft のフィッシング分析チームに "偽否定的" メッセージを送信できます。アナリストはメッセージを確認し、分類基準を満たす場合は、サービス全体のフィルターに追加します。 
  
組織全体に適用されるスパム設定については、「 [Office 365 スパムフィルターで迷惑メールをブロックする」を](https://go.microsoft.com/fwlink/p/?LinkId=534225)参照して、誤拒否の問題を防止してください。この記事には、誤検知を防止するためのヒントが記載されています。
  
迷惑メール メッセージを送信するには、次のようにします。
  
- outlook および web 上の outlook では、Microsoft outlook 用のレポートメッセージアドインを使用します。このツールをインストールして使用する方法については、「[レポートメッセージアドインを有効](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)にする」を参照してください。 
        
- 次の手順で説明するように、電子メールを使用して、迷惑メールまたはフィッシング詐欺として分類されるメッセージを Microsoft に送信することもできます。
    
### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a>メールを使用して Microsoft に迷惑メール (スパム) またはフィッシング詐欺メッセージを送信する
<a name="Useemailtosubmitjunkspamorphishingscammessages"> </a>

Microsoft に迷惑メールまたはフィッシング詐欺メッセージを送信するには:
  
1. 空の電子メールメッセージを作成します。
    
2. 次のように、メッセージをレビューする Microsoft チームにメッセージを送信します。 
    
  - 迷惑メールメッセージの場合: junk@office365.microsoft.com
    
  - フィッシング詐欺メッセージの場合: phish@office365.microsoft.com
    
3. 迷惑メールまたはフィッシング詐欺メッセージをコピーして、新しいメッセージに添付ファイルとして貼り付けます。 
    
    > [!NOTE]
    > 新しいメッセージに複数のメッセージを添付することができます。すべてのメッセージが同じ種類 (フィッシング詐欺メッセージまたは迷惑メールメッセージ) であることを確認します。> 新しいメッセージの本文は空のままにします。 
  
4. [ **送信**] をクリックします。
    
## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a>通過が許可されるはずだったのに迷惑メールとタグ付けされたメッセージを提出する
<a name="sectionSection1"> </a>

メッセージが誤って迷惑メールとして識別された場合は、「偽陽性」メッセージを Microsoft スパム分析チームに送信できます。アナリストは、メッセージの評価と分析を行います。分析結果によっては、サービス全体のスパムコンテンツフィルタールールを調整して、メッセージを経由することができます。
  
管理者は、組織全体に適用されるその他のスパム設定情報を確認できます。[メッセージがスパムとしてマークされないようにする方法に](https://go.microsoft.com/fwlink/p/?LinkId=534224)ついて説明します。この情報は、管理者レベルの制御があり、誤検知を防ぐ必要がある場合に役立ちます。
  
スパムではないメッセージを送信するには、次のようにします。
  
- コンテンツフィルターを構成するときに **[迷惑メールフォルダーにメッセージを移動**する] アクションを使用する (これが既定の操作である) 場合、ユーザーは、outlook または web 上の outlook (旧称: outlook web App) の迷惑メールフォルダーに誤検知メッセージを解放することができます。. 
    
  - Outlook ユーザーは、**迷惑メール**ではない右クリックメニューオプションを使用して誤検知メッセージを解放できます。ただし、この記事の手順に示されているように、電子メールでメッセージを Microsoft に送信する必要があります。 
    
  - Outlook on the web ユーザーは、偽陽性のメッセージを解放して、**迷惑メールではないとしてマーク**を付けて、分析のために Microsoft に送信することができます。これを行う方法の詳細については、「 [Outlook on the web で迷惑メールとフィッシング詐欺を報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)する」を参照してください。
    
- コンテンツフィルターを構成するときに、 **[迷惑メールフォルダーにメッセージを移動**する] アクションの代わりに [メッセージの**検疫**] アクションを使用すると、次のようになります。 
    
  - 管理者は、スパム検疫済みメッセージを解放し、それらを誤検知として Exchange 管理センターから報告できます。詳細については、「[管理者として検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-an-administrator.md)」を参照してください。
    
  - ユーザーは、次のチャネルを使用して、自分のスパム検疫済みメッセージを解放し、誤検知として報告することができます。 
    
  - Exchange 管理センター (EAC) ユーザー インターフェイス。詳細については、「[Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)」を参照してください。
    
  - エンドユーザー スパム通知メッセージ (管理者が有効にしている場合)。 
    
- 電子メールを使用して、スパムとして分類されていないメッセージを Microsoft に送信することもできます。その場合は、以下の手順を必ず実行してください。
    
### <a name="use-email-to-submit-false-positive-messages"></a>電子メールで誤検知メッセージを提出する

「[メールを使用して迷惑 (スパム) またはフィッシング詐欺メッセージを Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md#Useemailtosubmitjunkspamorphishingscammessages)」に記載されているものと同じ手順を使用します。ただし、メッセージを not_junk@office365.microsoft.com に送信します。
  
## <a name="spam-evaluation-and-rules-deployment"></a>スパム評価とルールの展開
<a name="sectionSection2"> </a>

スパム分析チームは、送信したメッセージを調査し、今後の迷惑メールを防ぐためにスパムフィルターを調整します。そのため、Office 365 スパムフィルターは常に見直されています。送信されたすべてのアイテムは、ネットワーク全体のレベルで評価されます。False 肯定提出は、スパムフィルターを通過できるようになる可能性があるルールの調整を調査および評価します。そのため、サービスに誤検知と、偽の否定 (迷惑メールではない) について通知することは、自分やグローバルネットワークを使用するすべてのお客様にとって有益です。スパムチームは、送信された各メッセージ内の次のようなインジケーターをチェックします。
  
- 送信元アドレス
    
- 送信 IP アドレス
    
- キーワード
    
- 語句
    
- 送信頻度
    
- その他の傾向やパターン
    
この情報を確認した後、スパムチームは、サービスのスパムフィルタリングレイヤーに変更を加える可能性があります。スパムチームの詳細については、次の英語のみのビデオをご覧ください。
  
[Microsoft Exchange スパムチームビデオ](https://youtu.be/-TpX_-GMC7o?hd=1)
  
スパム評価は、スパムの発信元の言語や文字セットに関係なく適用される継続的なプロセスです。スパム メッセージはあいまいであったり、件名やメッセージ本文のテキストがないことがあるため、スパム チームは、その他のメッセージの特性を使用してフィルター処理を行います。つまり、スパム チームが特定のメッセージをスパムとして設定し、そのルール ベースに必要な変更を行った場合、メッセージの特徴がフィルターを回避できるほど大きく変わらない限り、メッセージはブロックされます。新しいスパム ルールは継続的にデプロイされます。個々の提出についてルールがデプロイされる時期は、提出の量と質によって異なります。新しいスパム ルールはすべてのユーザーに対してグローバルに設定されるため、個々のスパムの提出が必ずしも新しいスパム ルールになるとは限りません。
   
## <a name="for-more-information"></a>関連情報
<a name="sectionSection4"> </a>

[スパム対策とマルウェア対策の保護](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx)
  
[メッセージがスパムとしてマークされないようにする方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

