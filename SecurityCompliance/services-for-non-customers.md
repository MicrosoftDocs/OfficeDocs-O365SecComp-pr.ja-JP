---
title: Office 365 にメールを送信するユーザー以外に対するサービス
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/2/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 電子メールをユーザーが安心して使用できるようにするため、Microsoft は各種ポリシーやテクノロジを用いて、ユーザーを保護しています。
ms.openlocfilehash: 2f5b8f07576ec01852d47c3e4ec1c787885667b2
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598743"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a>Office 365 にメールを送信するユーザー以外に対するサービス
  
電子メールの不正使用、迷惑メール、詐欺メール (フィッシング詐欺) は、引き続き電子メール エコシステム全体にとって負担となっています。電子メールをユーザーが安心して使用できるようにするため、Microsoft は各種ポリシーやテクノロジを用いて、ユーザーを保護しています。ただし、正当な電子メールが不利を被らないようにするべきであることも理解しています。そのため、送信者が送信評価をプロアクティブに管理して、Office 365 ユーザーに電子メールを配信する機能の向上を支援する一連のサービスを確立してきました。
  
Office 365 ユーザーではなくても組織に利点があります。その概要を以下に示します。
  
## <a name="sender-solutions"></a>送信者のソリューション
<a name="sectionSection0"> </a>

|**サービス**|**利点**|
|:-----|:-----|
|このオンライン ヘルプ コンテンツ  <br/> | 提供内容：  <br/>  EOP ユーザーへの通信の配信に関する質問の起点  <br/>  Microsoft のポリシーと要件が記載された簡単なオンライン ガイドが含まれる  <br/>  Microsoft によって導入されている迷惑メール フィルターと認証テクノロジの概要  <br/> |
|[Microsoft サポート](services-for-non-customers.md#AboutSupport) <br/> |配信の問題に対するセルフヘルプと充実したサポートを提供します。  <br/> |
|[Office 365 スパム対策用 IP リストから除外ポータル](services-for-non-customers.md#DelistPortal) <br/> |IP リストからの除外要求を送信するためのツール。この要求を送信する前に、送信者は、疑わしい IP から不正なメールや悪意のあるメールが送信されないことを確認する責任があります。  <br/> |
|[Exchange Online からの迷惑メールの不正使用とスパムの報告](services-for-non-customers.md#ReportOurJunk) <br/> |スパムや他の望ましくないメールが Exchange Online から送信されたり、インターネットや電子メール システムが混乱したりしないようにします。  <br/> |
   
## <a name="microsoft-support"></a>Microsoft サポート
<a name="AboutSupport"> </a>

Microsoft は、Office 365 受信トレイに電子メールを送信するユーザーのためにいくつかのサポート オプションを提供しています。次のことをお勧めします。
  
- 受信するあらゆる配信不能レポートの指示に従ってください。
    
- 「[Office 365 に送信されるメールのトラブルシューティング](troubleshooting-mail-sent-to-office-365.md)」で、ユーザー以外が経験する一般的な問題について確認します。
    
- [Office 365 のリストから除外ポータル](https://sender.office.com)を使用して、ご使用の IP を、ブロックされる送信者リストから除外する要求を送信します。 
    
- [Microsoft コミュニティ フォーラム](https://community.office365.com/en-us/f/)をご覧ください。
    
- 電子メールを送信しようとしている Office 365 ユーザーに別の方法で連絡と取り、Microsoft サポートに連絡して自分の代わりにサポート チケットをオープンするよう依頼します。場合によっては、Microsoft サポートは法的な理由から、ブロックされている IP 領域を所有している送信者と直接やり取りする必要が生じます。ただし通常は、ユーザー以外はサポート チケットをオープンできません。
    
     Office 365 の Microsoft 製品サポートについて詳しくは、「 [サポート](https://technet.microsoft.com/library/office-365-support.aspx)」をご覧ください。
    
## <a name="office-365-anti-spam-ip-delist-portal"></a>Office 365 スパム対策用 IP リストから除外ポータル
<a name="DelistPortal"> </a>

これは、自分自身を Office 365 でブロックされている送信者リストから除外するために使用できるセルフサービス ポータルです。このポータルは、Office 365 に電子メール アドレスがある受信者に電子メールを送信するとエラー・メッセージを受け取るものの、エラーではないと思われる場合に使用します。詳細については、「[リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)」を参照してください。
  
## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Exchange Online からの迷惑メールの不正使用とスパムの報告
<a name="ReportOurJunk"> </a>

ある場合、当社の使用条件およびポリシーに違反した迷惑メールをサード パーティーが送信するのに Office 365 が使用されることがあります。 Office 365 から迷惑メールを受信する場合、そうしたメッセージに関して [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) に報告できます。 RFC 5322 や ARF 形式でメッセージ ヘッダー全体を含め、問題のあるメッセージを添付してください。 Outlook on the web ユーザーは、組み込みツールを使用して迷惑メールを報告できます。 詳細については、「 [Outlook on the web で迷惑メールとフィッシング詐欺を報告する](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)」を参照してください。
  

