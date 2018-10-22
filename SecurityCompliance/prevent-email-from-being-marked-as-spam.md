---
title: Office 365 でメールが迷惑メールとしてマークされるのを防ぐ方法
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 34823bbc-a3e3-4949-ba42-97c73997eeed
description: Office 365 で、メールが迷惑メールにならないようにし、迷惑メールとしてマークされるのを防ぐ方法について説明します。
ms.openlocfilehash: f7ba560b4eb30abcda4c97617ead883659558bd8
ms.sourcegitcommit: 6d72cdb882b93edf6dfddb5ff2e6d8a16e2fa0bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2018
ms.locfileid: "25596720"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>Office 365 でメールが迷惑メールとしてマークされるのを防ぐ方法

 **Office 365 でメールが迷惑メールとしてマークされていますか? 以下のようにしてください。**
  
Exchange Online Protection (EOP) は、迷惑メールをフィルターで除外して、ユーザーが見たくないコンテンツが受信トレイに入らないようにします。ただし、時には、ユーザーが本当に見たいものが EOP によってフィルターで除外されてしまうことがあります。
  
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>メッセージが迷惑メールとしてマークされた理由を判断する

Office 365 での迷惑メールに関する多くの問題は、[メールのメッセージ ヘッダーを調べ](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)、そうなった理由を判断することによって解決できます。文字列 SFV:NSPM を含む X-Forefront-Antispam-Report というメッセージ ヘッダーがある場合、Exchange Online Protection (EOP) はメッセージをスキャンしてそれを迷惑メールと見なしたことを意味します。この場合は、[メッセージ報告アドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)してフィルターが改善されるようにすることを強くお勧めします。この値がヘッダーにない場合は、メールが迷惑メール スキャンをパススルーしなかったか、構成の問題があったためにメッセージが迷惑メールとして誤って分類されたことが考えられます。[迷惑メール対策メッセージ ヘッダーに関する詳しい説明](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)をご覧ください。
  
ヘッダーで、次の見出しと値を探します。
  
### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:BLK** 送信元アドレスが受信者の受信拒否リストにあるためにメッセージが迷惑メールとしてマークされたことを示します。 
    
- **SFV:SKS** コンテンツ フィルターの前にメッセージが迷惑メールとしてマークされたことを示します。この場合は、メッセージを迷惑メールとしてマークするトランスポート ルールが関係している可能性があります。メッセージ トレースを実行して、Spam Confidence Level (SCL) が高く設定されていそうなトランスポート ルールがトリガーされたかどうかを調べてください。 
    
- **SFV:SKB** メッセージは迷惑メール フィルター ポリシーの拒否リストと一致したために迷惑メールとしてマークされたことを示します。 
    
- **SFV:BULK** x-microsoft-antispam ヘッダーにある Bulk Complaint Level (BCL) 値が、コンテンツ フィルターに設定されているバルクしきい値を超えていることを示します。バルク メールとは、ユーザーはサインアップした可能性があるとしても望ましくないと思われるメールのことです。メッセージ ヘッダーで、X-Microsoft-Antispam ヘッダーの中の BCL (Bulk Confidence Level) プロパティを見つけます。迷惑メール フィルターに設定されたしきい値よりも BCL 値の方が小さければ、これらのタイプのバルク メッセージを迷惑メールとしてマークするようにしきい値を調整することが必要になる場合があります。[バルク メールの処理](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/)に関する許容度とユーザー設定はユーザーによって異なります。ユーザー設定ごとに異なるポリシーやルールを作成できます。
    
- **CAT:SPOOF** または **CAT:PHISH** メッセージはなりすましと思われることを示します。つまり、メッセージ ソースは検証できないため、疑わしい可能性があるということです。有効であるなら、送信元は SPF と DKIM が適切に構成されていることを確認する必要があります。詳細については、Authentication-Results ヘッダーを確認してください。すべての送信元に適切なメール認証方法を使用させるのは難しいかもしれませんが、こうした確認を省略することは極めて危険であり、侵害の一番の原因です。 
    
### <a name="x-customspam"></a>x-customspam

- このヘッダーがあるということは、迷惑メール フィルターでいずれかの[高度な迷惑メール オプションが有効になっている](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx)ためにメッセージが迷惑メールとしてマークされたことを示しています。これらの機能を必要としない限り、既定の設定を使用することをお勧めします。 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a>大量の迷惑メールの他の原因の解決方法

Exchange Online Protection (EOP) が効率的に機能するためには、いくつかのタスクを管理者が実行する必要があります。Office 365 テナントの管理者でなく、大量の迷惑メールを受け取っているユーザーは、これらのタスクを管理者と一緒に行うこともできます。そうしない場合は、ユーザーのセクションにスキップしてください。
  
### <a name="for-admins"></a>管理者向け

- **DNS レコードを Office 365 に向ける** EOP によって保護されるためには、すべてのドメインのメール エクスチェンジャー (MX) DNS レコードが Office 365 (Office 365 のみ) に向いていなければなりません。MX が Office 365 に向いていなければ、EOP はユーザーのための迷惑メール フィルター処理を行いません。別のサービスまたはアプライアンスを使用してドメインのための迷惑メール フィルター処理を行う場合は、EOP の迷惑メール保護を無効にすることを検討する必要があります。これを行うには、SCL 値を -1 に設定するトランスポート ルールを作成します。EOP を使用することを後で決定する場合は、このトランスポート ルールを必ず削除してください。 
    
- **Outlook の SmartScreen フィルターを無効にする** ユーザーが Outlook デスクトップ クライアントを使用している場合、ユーザーは中断されている SmartScreen フィルター機能を無効にする必要があります。有効にしておくと、誤検知の原因になることがあります。これは、更新されたデスクトップ Outlook クライアントを実行している場合は必須ではありません。 
    
- **ユーザーのメッセージ報告アドインをオンにする** [ユーザーのメッセージ報告アドインを有効にする](enable-the-report-message-add-in.md)ことを強くお勧めします。管理者は、ユーザーが送信しているフィードバックを調べ、あらゆるパターンを使用して、問題の原因と思われる設定を調整することもできます。
    
- **すぐに送信元を許可する** すぐに送信元を許可する必要がある場合は、**特定の送信元の IP アドレスのみ許可する**ことを強くお勧めします。あるいは、送信元を許可したうえで、送信元が SPF や DKIM のような認証検査に合格したことを確認する (送信元ドメインと成功した Authentication-Results ヘッダーの**両方**を求めるトランスポート ルールを作成する) こともできます。 
    
### <a name="for-users"></a>ユーザー向け

- **Microsoft に迷惑メールを報告する** [メッセージ報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) を使用して、Microsoft に迷惑メール メッセージを報告します。また、junk@office365.microsoft.com にメッセージを送信し、1 つ以上のメッセージをレポートに添付することができます。
    
    **重要** メッセージを添付ファイルとして転送しなければ、[ヘッダーがないために Office 365 の迷惑メール フィルターの改善ができなくなります](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/)。 
    
- **許可リストに送信元を追加する (ただし慎重に使用する)** 最後の手段として、[ブロックまたは許可 (迷惑メール設定)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) を行えます。その場合は、対象となるフィッシング試行が受信トレイに入れられるようになる可能性があることに注意する必要があります。
    

