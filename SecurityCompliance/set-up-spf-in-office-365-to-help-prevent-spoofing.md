---
title: スプーフィングを防止するために Office 365 で SPF を設定する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 2/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
description: '概要: この記事では、Office 365 で Sender Policy Framework (SPF) をカスタム ドメインと併用できるように、ドメイン ネーム サービス (DNS) レコードを更新する方法について説明します。 SPF を使うと、カスタム ドメインから送信される送信電子メールを検証できます。'
ms.openlocfilehash: 039a09e7dac307ead156eac47699edbd2350b304
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692836"
---
# <a name="set-up-spf-in-office-365-to-help-prevent-spoofing"></a>スプーフィングを防止するために Office 365 で SPF を設定する

 **概要:** この記事では、Office 365 で Sender Policy Framework (SPF) をカスタム ドメインと併用できるように、ドメイン ネーム サービス (DNS) レコードを更新する方法について説明します。SPF を使うと、カスタム ドメインから送信される送信電子メールを検証できます。 
  
カスタム ドメインを使用するには、Office 365 では、Sender Policy Framework (SPF) TXT レコードを DNS レコードに追加してスプーフィングを防止する必要があります。SPF は、ユーザーに代わってメールを送信できるメール サーバーを識別します。基本的には、SPF を DKIM、DMARC、その他の Office 365 でサポートされているテクノロジと併用することによって、スプーフィングとフィッシング詐欺を防止できます。SPF は TXT レコードとして追加され、DNS はこのレコードを使って、カスタム ドメインの代わりにメールを送信できるメール サーバーを識別します。受信側のメール システムは、この SPF TXT レコードを参照して、カスタム ドメインからのメッセージが、承認されたメッセージング サーバーからのものであるかどうかを判別します。
  
たとえば、カスタム ドメイン contoso.com が Office 365 を使用しているとします。ユーザーのドメインの正当なメール サーバーとして Office 365 メッセージング サーバーを一覧表示する SPF TXT レコードを追加します。受信メッセージング サーバーが joe@contoso.com からのメッセージを取得すると、サーバーによって contoso.com の SPF TXT レコードが検索され、適切なメッセージであるかどうかが検出されます。受信サーバーで、SPF レコードに一覧表示されている Office 365 メッセージング サーバー以外のサーバーからメッセージを取得していることが検出された場合、受信メール サーバーはそのメッセージを迷惑メールとして拒否できます。
  
また、カスタム ドメインに SPF TXT レコードが含まれていないと、一部の受信サーバーはメッセージを完全に拒否することがあります。これは、受信サーバーが、承認されたメッセージング サーバーからのメッセージであることを検証できないためです。
  
既に Office 365 のメールを設定している場合、SPF TXT レコードとして Microsoft のメッセージング サーバーが DNS に含まれています。ただし、場合によっては DNS で SPF TXT レコードを更新する必要があります。たとえば、次のような場合です。
  
- 以前は、SharePoint Online を使用している場合、カスタム ドメインに別の SPF TXT レコードを追加する必要がありました。この作業を行う必要はなくなりました。この変更により、SharePoint Online の通知メッセージが [迷惑メール] フォルダーに振り分けられるリスクが軽減されます。参照の制限数である 10 に達し、"参照制限を超えました"、"ホップが多すぎます" などのメッセージを示すエラーが表示される場合は、SPF TXT レコードを更新します。
    
- Office 365 とオンプレミスの Exchange を使用したハイブリッド環境の場合。
    
- DKIM と DMARC をセットアップする場合 (推奨)。
    
## <a name="updating-your-spf-txt-record-for-office-365"></a>Office 365 の SPF TXT レコードを更新する

DNS で TXT レコードを更新する前に、情報を収集し、レコード形式を判別する必要があります。これによって、DNS エラーの発生を防止できます。サポートされている SPF 構文の高度な例や詳細については、「[Office 365 において SPF がスプーフィングとフィッシングを防ぐしくみ](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)」をご覧ください。
  
次の情報を収集します。
  
- カスタム ドメインの現在の SPF TXT レコード。手順に関しては、「[Office 365 の DNS レコードの作成に必要な情報を収集する](https://support.office.microsoft.com/en-us/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67)」をご覧ください。
    
- すべてのオンプレミス メッセージ サーバーの IP アドレス。たとえば、 **192.168.0.1** などです。
    
- SPF TXT レコードに含める必要があるサードパーティ製のすべてのドメインに使用するドメイン名。一部のバルク メール プロバイダーは、顧客用のサブドメインを設定しています。たとえば、会社 MailChimp に **servers.mcsv.net** を設定するなどです。
    
- SPF TXT レコードで使う強制ルールを決定します。**-all** をお勧めします。その他の構文オプションについて詳しくは、「[Office 365 用の SPF TXT レコードの構文](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)」をご覧ください。
    
### <a name="to-add-or-update-your-spf-txt-record"></a>SPF TXT レコードを追加または更新するには

1. まだ行っていなければ、次の表の構文を使って、SPF TXT レコードを形成します。
    
||**使用対象**|**Office 365 ユーザーとの共通性**|**追加対象**|
|:-----|:-----|:-----|:-----|
|1-d  <br/> |いずれかの電子メール システム (必須)  <br/> |共通。この値で始まるすべての SPF レコード  <br/> |v=spf1  <br/> |
|pbm-2  <br/> |Exchange Online  <br/> |共通  <br/> |include:spf.protection.outlook.com  <br/> |
|1/3  <br/> |Exchange Online 専用のみ  <br/> |共通ではない  <br/> |ip4: 23.103.224.0/19 ip4: 206.191.224.0/19 ip4: 40.103.0.0/16 に含まれています。  <br/> |
|2/4  <br/> |Office 365 Germany、Microsoft Cloud Germany のみ  <br/> |共通ではない  <br/> |添付の内容は以下のとおりです。  <br/> |
|5  <br/> |サード パーティ製の電子メール システム  <br/> |共通ではない  <br/> |include:\<domain name\>  <br/> domain name は、サード パーティ製の電子メール システムのドメイン名です。  <br/> |
|シックス  <br/> |オンプレミスの電子メール システム。たとえば、Exchange Online Protection と別のメール システム  <br/> |共通ではない  <br/> | 各追加メール システムで次のいずれかを使用します。  <br/>  ip4:\<  _IP address_\>  <br/>  ip6:\<  _IP address_\>  <br/>  include:\<  _domain name_\>  <br/>  \<  _IP address_\> の値は他のメール システムの IP アドレスで、\< _domain name_\> はユーザーのドメインのためにメールを送信する他のメール システムのドメイン名です。  <br/> |
|7  <br/> |いずれかの電子メール システム (必須)  <br/> |共通。この値で終わるすべての SPF レコード  <br/> |\< _enforcement rule_\>  <br/> 可能な値はいくつかあります。 **-all** を使用することをお勧めします。  <br/> |
   
1.1 Office 365 で完全にホストされている場合、つまり、オンプレミスのメールサーバーを使用していない場合、SPF TXT レコードには行1、2、および7が含まれるため、次のようになります。
    
  ```
   v=spf1 include:spf.protection.outlook.com -all
  ```

1.2 これは、最も一般的な Office 365 SPF TXT レコードです。 このレコードは、Office 365 データセンターが米国内にあるか、ヨーロッパ (ドイツ) にあるか、または別の場所にあるかに関係なく、すべてのユーザーに対して機能します。
    
1.3 ただし、Microsoft Cloud ドイツの一部である Office 365 ドイツを購入した場合は、2行目ではなく、行4の include ステートメントを使用する必要があります。 たとえば、Office 365 Germany で完全にホストされている場合、つまり、オンプレミスのメール サーバーを使っていない場合は、SPF TXT レコードには、次のように 1 行目、4 行目、7 行目が含まれます。
    
  ```
   v=spf1 include:spf.protection.outlook.de -all
  ```

1.4 office 365 に既に展開されており、カスタムドメイン用の SPF TXT レコードをセットアップしていて、office 365 ドイツに移行する場合は、spf txt レコードを更新する必要があります。 これを行うには**** 、次のように変更します。たとえば、「spf」を**含め**ます。
    
2. SPF TXT レコードを形成した後は、DNS でレコードを更新する必要があります。 1つのドメインに対して使用できる SPF TXT レコードは1つだけです。 SPF TXT レコードが存在する場合は、新しいレコードを追加するのではなく、既存のレコードを更新する必要があります。 [ [Office 365 の dns レコードの作成](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide)] に移動し、dns ホストのリンクをクリックします。 
    
3. SPF TXT レコードをテストします。
    
## <a name="more-information-about-spf"></a>SPF の詳細情報

サポートされている SPF 構文、スプーフィング、トラブルシューティング、Office 365 が SPF をサポートする方法の高度な例や詳細については、「[Office 365 において SPF がスプーフィングとフィッシングを防ぐしくみ](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)」をご覧ください。
  
## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>次の手順：Office 365 の SPF のセットアップ後

SPF TXT レコードで問題が発生している場合「[トラブルシューティング:Office 365 における SPF のベスト プラクティス](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)」をお読みください。
  
 SPF はスプーフィングを防止するために設計されていますが、SPF で防御できないスプーフィングの手法があります。これらから保護するために、SPF をセットアップすると、Office 365 用に DKIM と DMARC も構成する必要があります。始めるには「[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」をご覧ください。次は、「[DMARC を使用して Office 365 でメールを検証する](use-dmarc-to-validate-email.md)」を参照してください。
  

