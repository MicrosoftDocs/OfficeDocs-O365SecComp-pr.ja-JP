---
title: EOP の一般的な FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: ここでは、Microsoft Exchange Online Protection (EOP) のクラウド ホスト型電子メール フィルター サービスについてよく寄せられる質問を紹介します。その他のよく寄せられる質問 (FAQ) については、以下のリンクを参照してください。
ms.openlocfilehash: 9a8ac96678e33623803e95998780b4544dec5a78
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027384"
---
# <a name="eop-general-faq"></a>EOP の一般的な FAQ

ここでは、Microsoft Exchange Online Protection (EOP) のクラウド ホスト型電子メール フィルター サービスについてよく寄せられる質問を紹介します。その他のよく寄せられる質問 (FAQ) については、以下のリンクを参照してください。
  
- [EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)
    
- [代理管理の FAQ](delegated-administration-faq.md)
    
- [スパム対策の保護に関する FAQ](../anti-spam-protection-faq.md)
    
- [Exchange Online の差出人セーフ リストと受信拒否リスト](../safe-sender-and-blocked-sender-lists-faq.md)
    
- [検疫に関する FAQ](../quarantine-faq.md)
    
- [マルウェア対策保護に関する FAQ](../anti-malware-protection-faq-eop.md)
    
- [Message Trace FAQ](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx)
    
- [FOPE から EOP への移行の FAQ](http://technet.microsoft.com/library/e0e76b89-b0d3-4c0a-bfc8-137b579e983b.aspx)
    
 **Q. EOP とは何ですか?**
  
A. EOP とは、クラウド ホスト型の電子メール フィルター サービスで、ユーザーをスパムやマルウェアから保護し、カスタム ポリシー ルールを適用するために構築されます。
  
 **Q. EOP の無料試用版に新規登録する、または EOPを購入するにはどうすればよいですか?**
  
A. EOP の無料試用版に新規登録する、または EOP を購入するには、「[Exchange Online Protection ホーム ページ](https://go.microsoft.com/fwlink/p/?LinkId=279912)」にアクセスしてください。試用版の機能は、有料版のサブスクリプションと同じですが、「[Exchange Online Protection サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)」サブスクリプション プランで提供されている追加機能も含まれています。 
  
 **Q. EOP はどのような価格設定になっていますか?**
  
A. EOP はユーザーごとにライセンスが付与されます。最新の価格情報については、「[Exchange Online Protection ホーム ページ](https://go.microsoft.com/fwlink/p/?LinkId=279912)」を参照してください。
  
 **Q. EOP を稼働させるまでにどの程度の時間がかかりますか?**
  
A. 「[EOP サービスを設定する](set-up-your-eop-service.md)」の手順に従って MX レコードを変更すると、メールが EOP を経由するようになり、すぐにフィルター処理が開始されます。MX レコードが DNS 経由で送信されるまで 24 ～ 48 時間かかる場合があります。この処理の途中でも、Exchange 管理センター (EAC) の保護設定を微調整できます。
  
 **Q. EOP を使用するには、 Microsoft Office 365 のすべての機能を使用する必要がありますか?EOP 保護機能以外は不要です。**
  
A. EOP によるオンプレミス メールボックスの保護は、Office 365 のその他の機能を使用しなくても可能です。これをスタンドアロン サブスクリプションといいます。EOP 機能のリストは、「[Exchange Online Protection サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)」で確認できます。
  
 **Q. EOP により電子メール フィルタリングにサインアップする際に、Office 365 テナントが必要なのはなぜですか?**
  
A. Office 365 というのは、Office 365 テナントを通じてアクセスできる一連の製品およびサービスの集合体に付けられた名前です。Office 365 テナントは、電子メール フィルタリングのライセンスを追加する開始点と考えてください。
  
 **Q. EOP には、既知の問題や想定される解決策を見つけることのできる通信ポータルがありますか。新機能についてはどうですか。**
  
A. Office 365 の管理者センターにこの情報の一部があります。サービス レベル イベントの影響を受けている場合は、Office 365 の管理者センターにサインインした後に通信アラートが (通常はベルのアイコンと共に) 表示されます。その項目を参照して、適切に対応することをお勧めします。
  
EOP の新機能については、「[ビジネス向けの Office 365 ロードマップ](https://office.microsoft.com/en-us/products/office-365-roadmap-FX104343353.aspx)」を参照してください。新機能を調べるためのお勧めの情報源です。[Office ブログ](https://go.microsoft.com/fwlink/p/?LinkId=392724) Web サイトにも新機能に関するブログ記事が投稿されています。 
  
 **Q. このサービスは Exchange の旧バージョン (Exchange Server 2010 など) や Exchange 以外の環境で使用できますか?**
  
A. はい、このサービスはサーバーに依存せず、すべての SMTP メール転送エージェントで使用できます。
  
 **Q. このサービスは、どの程度の規模の組織が対象ですか?**
  
A. 組織の規模に関わらずご利用いただけます。EOP ネットワークは、どのような速度で成長する組織であっても十分対応可能です。
  
 **EOP を設定するのに必要なアクセス許可はどのようなものですか?**
  
EOP を構成するには、Office 365 グローバル管理者、または Exchange 会社の管理者 (組織の管理役割グループ) である必要があります。
  
 **Q. 個人データや個人情報が安全に保護されていることを確認できますか?**
  
A. サービス レベル アグリーメント (SLA) などの個人データや個人情報を安全に保護するための手順の詳細については、「[Office 365 セキュリティ センター](https://go.microsoft.com/fwlink/p/?LinkId=285405)」を参照してください。
  
 **Q. メッセージ サイズの制限などの注意すべき制限がありますか。**
  
EOP での制限の詳細については、「[Exchange Online Protection の制限](https://go.microsoft.com/fwlink/p/?LinkId=402617)」を参照してください。 
  
 **Q. EOP はリモート Windows PowerShell をサポートしていますか?**
  
A. はい、リモート Windows PowerShell を使用してすべての EOP 機能が利用できます。詳細については、「[Exchange Online Protection の PowerShell](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx)」を参照してください。
  

