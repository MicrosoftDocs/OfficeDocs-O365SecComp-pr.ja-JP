---
title: EOP の一般的な FAQ
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: ここでは、Microsoft Exchange Online Protection (EOP) のクラウド ホスト型電子メール フィルター サービスについてよく寄せられる質問を紹介します。その他のよく寄せられる質問 (FAQ) については、以下のリンクを参照してください。
ms.openlocfilehash: e16e1664abd52c1e40aa9c1ac2ea328924708a13
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676827"
---
# <a name="eop-general-faq"></a>EOP の一般的な FAQ

ここでは、Microsoft Exchange Online Protection (EOP) のクラウド ホスト型電子メール フィルター サービスについてよく寄せられる質問を紹介します。その他のよく寄せられる質問 (FAQ) については、以下のリンクを参照してください。
  
- [EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)

- [代理管理に関する FAQ](delegated-administration-faq.md)

- [スパム対策保護に関する FAQ](../anti-spam-protection-faq.md)

- [Exchange Online の差出人セーフ リストと受信拒否リスト](../safe-sender-and-blocked-sender-lists-faq.md)

- [検疫に関する FAQ](../quarantine-faq.md)

- [マルウェア対策保護に関する FAQ](../anti-malware-protection-faq-eop.md)

- [メッセージ追跡の FAQ](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx)

 **Q. EOP とは何ですか?**
  
A. EOP とは、クラウド ホスト型の電子メール フィルター サービスで、ユーザーをスパムやマルウェアから保護し、カスタム ポリシー ルールを適用するために構築されます。
  
 **Q. EOP の無料試用版に新規登録する、または EOPを購入するにはどうすればよいですか?**
  
A. EOP の無料試用版に新規登録する、または EOP を購入するには、「[Exchange Online Protection ホーム ページ](https://products.office.com/exchange/exchange-email-security-spam-protection)」にアクセスしてください。試用版の機能は、有料版のサブスクリプションと同じですが、「[Exchange Online Protection サービスの説明](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview)」サブスクリプション プランで提供されている追加機能も含まれています。
  
 **Q. EOP はどのような価格設定になっていますか?**
  
A. EOP はユーザーごとにライセンスが付与されます。最新の価格情報については、「[Exchange Online Protection ホーム ページ](https://products.office.com/exchange/exchange-email-security-spam-protection)」を参照してください。
  
 **Q. EOP を稼働させるまでにどの程度の時間がかかりますか?**
  
A. 「[EOP サービスを設定する](set-up-your-eop-service.md)」の手順に従って MX レコードを変更すると、メールが EOP を経由するようになり、すぐにフィルター処理が開始されます。MX レコードが DNS 経由で送信されるまで 24 ～ 48 時間かかる場合があります。この処理の途中でも、Exchange 管理センター (EAC) の保護設定を微調整できます。
  
 **Q. EOP を使用するには、 Microsoft Office 365 のすべての機能を使用する必要がありますか?EOP 保護機能以外は不要です。**
  
A. EOP によるオンプレミス メールボックスの保護は、Office 365 のその他の機能を使用しなくても可能です。これをスタンドアロン サブスクリプションといいます。EOP 機能のリストは、「[Exchange Online Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」で確認できます。
  
 **Q. EOP により電子メール フィルタリングにサインアップする際に、Office 365 テナントが必要なのはなぜですか?**
  
A. Office 365 というのは、Office 365 テナントを通じてアクセスできる一連の製品およびサービスの集合体に付けられた名前です。Office 365 テナントは、電子メール フィルタリングのライセンスを追加する開始点と考えてください。
  
 **Q. EOP には、既知の問題や想定される解決策を見つけることのできる通信ポータルがありますか。新機能についてはどうですか。**
  
A. Microsoft 365 管理センターには、この情報がいくつか含まれています。 サービスレベルイベントの影響を受けている場合は、Microsoft 365 管理センターにサインインした後に、通信警告 (通常はベルアイコンが付属) が表示されます。 その項目を参照して、適切に対応することをお勧めします。
  
EOP の新機能については、「[ビジネス向けの Office 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)」を参照してください。 また、 [Microsoft 365 ブログ](https://www.microsoft.com/en-us/microsoft-365/blog/)web サイトに新機能に関するブログ記事を投稿します。
  
 **Q. このサービスは Exchange の旧バージョン (Exchange Server 2010 など) や Exchange 以外の環境で使用できますか?**
  
A. はい、このサービスはサーバーに依存せず、すべての SMTP メール転送エージェントで使用できます。
  
 **Q. このサービスは、どの程度の規模の組織が対象ですか?**
  
A. 組織の規模に関わらずご利用いただけます。EOP ネットワークは、どのような速度で成長する組織であっても十分対応可能です。
  
 **EOP を設定するのに必要なアクセス許可はどのようなものですか?**
  
EOP を構成するには、Office 365 グローバル管理者、または Exchange 会社の管理者 (組織の管理役割グループ) である必要があります。
  
 **Q. 個人データや個人情報が安全に保護されていることを確認できますか?**
  
A. サービス レベル アグリーメント (SLA) などの個人データや個人情報を安全に保護するための手順の詳細については、「[Office 365 セキュリティ センター](https://www.microsoft.com/trust-center)」を参照してください。
  
 **Q. メッセージ サイズの制限などの注意すべき制限がありますか。**
  
EOP での制限の詳細については、「[Exchange Online Protection の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)」を参照してください。
  
 **Q. EOP は PowerShell をサポートしていますか?**
  
A. はい、完全な EOP 機能を PowerShell 経由で利用できます。 詳細については、「 [Exchange Online Protection の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)」を参照してください。
