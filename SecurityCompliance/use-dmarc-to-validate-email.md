---
title: DMARC を使用して Office 365 でメールを検証する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.custom: TN2DMC
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
description: 'Domain-based Message Authentication, Reporting, and Conformance (DMARC) は、Sender Policy Framework (SPF) および DomainKeys Identified Mail (DKIM) と併用することで、メールの送信者を認証できるようになり、送信先の電子メール システムはドメインから送信されたメッセージを信頼するようになります。 '
ms.openlocfilehash: 199ab67d17152fc0c4ed6b9f87cde66beaf913d5
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003226"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a>DMARC を使用して Office 365 でメールを検証する

Domain-based のメッセージの認証、レポート、および準拠[DMARC)](https://dmarc.org)メールの送信者を認証し、送信先の電子メール システムから送信されたメッセージを信頼することを確認するには、送信者ポリシー フレームワーク (SPF) および DomainKeys 確認メール (DKIM) と連携ドメインです。SPF と DKIM DMARC を実装することは、スプーフィング、フィッシング詐欺メールを確実に保護を提供します。DMARC できますが、メッセージの処理方法を決定する受信側のメール システムは、失敗の SPF や DKIM をチェックする自分のドメインから送信されます。 
  
## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a>SPF と DMARC が連携して Office 365 の電子メールを保護するしくみ
<a name="SPFandDMARC"> </a>

 電子メール メッセージには、発信者、送信者、またはアドレスが含まれていることがあります。これらのアドレスは、さまざまな目的に使用できます。たとえば、次のアドレスについて考えてみましょう。 
  
- **"Mail From" アドレス:** 送信者を識別し、メッセージの配信に問題が発生した場合に、配信不能通知などの通知の返送先を指定します。これは電子メール メッセージのエンベロープ部分に表示されます。通常、ユーザーの電子メール アプリケーションには表示されません。これは、 5321.MailFrom アドレスまたはリバース パス アドレスとも呼ばれます。
    
- **"From" アドレス** From アドレスとして、ユーザーの電子メール アプリケーションに表示されるアドレス。このアドレスは電子メールの作成者を識別します。つまり、メッセージを書いた個人またはシステムのメールボックスになります。これは、 5322.From アドレスとも呼ばれます。
    
SPF は、DNS TXT レコードを使用して、特定のドメインに対する認証済みの送信側 IP アドレスのリストを提示します。通常、SPF チェックは 5321.MailFrom アドレスに対してのみ実行されます。つまり、単独で SPF を使用すると、5322.From アドレスは認証されないことになります。これは、SPF チェックにパスしていても、5322.From 送信者アドレスがスプーフィングされたメッセージをユーザーが受信するというシナリオの余地を残すことになります。たとえば、次のような SMTP トランスクリプトを考えてみます。
  
```
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S: 
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S: 
S: http://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .

```

このトランスクリプトでは、送信者のアドレスは次にようになります。
  
- Mail From アドレス (5321.MailFrom): phish@phishing.contoso.com
    
- From アドレス (5322.From): security@woodgrovebank.com
    
SPF を構成した場合、受信側サーバーは Mail From アドレス phish@phishing.contoso.com に対してチェックを実行します。メッセージがドメイン phishing.contoso.com の有効なソースから送信された場合は、SPF チェックをパスします。電子メール クライアントには差出人アドレスのみが表示されるため、ユーザーには、このメッセージが security@woodgrovebank.com から送信されたように見えます。SPF だけでは、woodgrovebank.com の有効性は認証されません。
  
DMARC を使用すると、From アドレスに対するチェックを受信側サーバーも実行するようになります。前述の例では、woodgrovebank.com の所定の場所に DMARC TXT レコードが存在していれば、From アドレスに対するチェックは失敗します。
  
## <a name="what-is-a-dmarc-txt-record"></a>DMARC TXT レコードとは
<a name="WhatisDMARC"> </a>

SPF の DNS レコードと同様に、DMARC のレコードは、スプーフィングとフィッシングの防止に役立つ DNS テキスト (TXT) レコードです。DMARC TXT レコードは DNS で発行します。DMARC TXT レコードは、メール作成者の IP アドレスを、送信側ドメインの所有者とされる名前と照合して、メール メッセージの発信元を確認します。 この DMARC TXT レコードにより、承認済みの送信メール サーバーを識別します。送信先メール システムでは、メッセージが承認済みの送信メール サーバーから発信されたことを確認できます。
  
Microsoft の DMARC TXT レコードは、次のような内容になります。
  
```
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 

```

Microsoft は、DMARC レポートをサード パーティの [Agari](https://agari.com) に送信します。 Agari では、DMARC レポートを収集して分析します。
  
## <a name="implement-dmarc-for-inbound-mail"></a>受信メール用に DMARC を実装する
<a name="implementDMARCinbound"> </a>

Office 365 で受信するメールの DMARC を設定するために必要な手順はありません。すべて、Microsoft が手配します。DMARC チェックをパスしないメールに対する処理について知る必要がある場合は、「[Office 365 が DMARC に失敗した受信メールを処理する方法](use-dmarc-to-validate-email.md#inbounddmarcfail)」を参照してください。
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a>Office 365 からの送信メール用に DMARC を実装する
<a name="implementDMARCoutbound"> </a>

Office 365 を使用しているもののカスタム ドメインを使用していない場合 (つまり、onmicrosoft.com を使用する場合)、組織で DMARC を構成または実装するために、他に行わなければならないことは何もありません。SPF のセットアップはすでに完了しており、Office 365 により自動的に送信メールに DKIM 署名が生成されます。この署名の詳細については「[DKIM と Office 365 の既定の動作](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)」をご覧ください。
  
 カスタム ドメインを所有している場合や、Office 365 に加えてオンプレミスの Exchange サーバーも使用している場合は、送信メール用に手動で DMARC を実装する必要があります。カスタム ドメイン用に DMARC を実装する手順は次のとおりです。 
  
- [手順 1:ドメインに対する有効なメールのソースを特定する](use-dmarc-to-validate-email.md#IdentifyValidSources)
    
- [手順 2:Office 365 でドメイン用に SPF をセットアップする](use-dmarc-to-validate-email.md#ConfigSPF)
    
- [手順 3:Office 365 でカスタム ドメイン用に DKIM をセットアップする](use-dmarc-to-validate-email.md#ConfigDKIM)
    
- [手順 4:Office 365 でドメイン用の DMARC TXT レコードを作成する](use-dmarc-to-validate-email.md#CreateDMARCRecord)
    
### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>手順 1:ドメインに対する有効なメールのソースを特定する
<a name="IdentifyValidSources"> </a>

既に SPF のセットアップが済んでいる場合は、この演習を完了していることになります。ただし、DMARC には追加の考慮事項があります。ドメインに対するメールのソースを特定するときには、2 つの問いに答える必要があります。
  
- どの IP アドレスにドメインからメッセージを送信するか。
    
- 自分の代わりにサード パーティから送信されるメールについて、5321.MailFrom ドメインと 5322.From ドメインが一致しているか。
    
### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a>手順 2:Office 365 でドメイン用に SPF をセットアップする
<a name="ConfigSPF"> </a>

すべての有効な送信者の一覧が用意できると、「[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」の手順を実行できるようになります。
  
たとえば、contoso.com が Exchange Online からメールを送信するとします。このとき、オンプレミスの Exchange サーバーの IP アドレスが 192.168.0.1、Web アプリケーションの IP アドレスが 192.168.100.100 だと仮定すると、SPF TXT テキストレコードは次のようになります。
  
```
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

ベスト プラクティスとして、SPF TXT レコードでは、サード パーティの送信者についても考慮に入れておく必要があります。
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a>手順 3:Office 365 でカスタム ドメイン用に DKIM をセットアップする
<a name="ConfigDKIM"> </a>

SPF のセットアップ後には、DKIM をセットアップする必要があります。DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加できます。DKIM をセットアップする代わりに、ドメインに対して Office 365 で既定の DKIM 構成の使用を許可すると、DMARC が失敗することがあります。これは、既定の DKIM 構成が、5322.From アドレスとしてカスタム ドメインではなく初期設定の onmicrosoft.com ドメインを使用するためです。これにより、ドメインから送信されたすべてのメールの 5321.MailFrom アドレスと 5322.From アドレスとの間に不一致が生じることになります。
  
メールを代理で送信するサード パーティの送信者が存在しているときに、そのサード パーティが送信するメールの 5321.MailFrom アドレスと 5322.From アドレスが一致していないと、そのメールに対する DMARC は失敗します。これを回避するには、そのサード パーティの送信者について、具体的にドメインの DKIM をセットアップする必要があります。これにより、このサード パーティのサービスからのメールを Office 365 で認証できるようになります。 ただし、そのようにすると、サード パーティが送信したメールを本人が送信したメールであるかのように検証することを他者 (Yahoo、Gmail、Comcast など) にも許可するようになります。これには、顧客がどこにメールボックスを配置していてもドメインとの信頼を構築できるようになるという利点があります。それと同時に、メッセージはドメインの認証チェックをパスしているため、Office 365 は偽装を理由にメッセージをスパムとしてマークしなくなります。
  
サード パーティの送信者がドメインを偽装できるように DKIM をセットアップする方法を含め、ドメインの DKIM をセットアップする手順については、「[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a>手順 4:Office 365 でドメイン用の DMARC TXT レコードを作成する
<a name="CreateDMARCRecord"> </a>

ここでは、Office 365 で最もよく使用される構文オプションを示します。ただし、ここに記載されていない別の構文のオプションもあります。ドメイン用の DMARC TXT レコードは、次に示す形式で作成します。
  
```
_dmarc.domainTTL IN TXT "v=DMARC1; pct=100; p=policy
```

各部分の意味は次のとおりです。
  
-  *domain*  は、保護対象にするドメインです。既定では、このレコードは、ドメインとすべてのサブドメインからのメールを保護します。たとえば、_dmarc.contoso.com を指定すると、DMARC は、このドメインとすべてのサブドメイン (housewares.contoso.com や plumbing.contoso.com など) からのメールを保護します。 
    
-  *TTL*  は、常に 1 時間に相当する必要があります。TTL に使用される単位は、ドメインのレジストラーに応じて hours (1 時間)、minutes (60 分)、または seconds (3,600 秒) のいずれかになります。 
    
- pct=100 は、このルールがメールの 100% に使用される必要があることを示します。
    
-  *policy*  では、DMARC に失敗した場合に受信側サーバーが従う必要のあるポリシーを指定します。ポリシーは、なし (none)、検疫 (quarantine)、または拒否 (reject) に設定できます。 
    
どのオプションを使用するかについては、「[Office 365 で DMARC を実装する際のベスト プラクティス](use-dmarc-to-validate-email.md#DMARCbestpractices)」の概念をよく理解してください。
  
例:
  
ポリシーをなし (none) に設定する
  
```
_dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
```

ポリシーを検疫 (quarantine) に設定する
  
```
_dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
```

ポリシーを拒否 (reject) に設定する
  
```
_dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
```

レコードの作成後には、ドメイン レジストラーでレコードを更新する必要があります。DMARC TXT レコードを Office 365 の DNS レコードに追加する手順の詳細については、「[DNS レコードを管理するときに Office 365 の DNS レコードを作成する](https://support.office.com/article/Create-DNS-records-for-Office-365-when-you-manage-your-DNS-records-b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)」を参照してください。
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a>Office 365 で DMARC を実装する際のベスト プラクティス
<a name="DMARCbestpractices"> </a>

DMARC は、メール フローの他の部分に影響を与えないように段階的に実装できます。ここに示す手順に従ったロール アウト計画を作成して実施してください。ここに示す各手順は、まずサブドメインに実行します。その後で、その他の各サブドメインに対して実行し、最後に組織のトップレベル ドメインに実行してから、次の手順に進みます。
  
1. DMARC の実装による影響を監視する
    
    まず、サブドメインまたはドメインに単純な監視モード レコードを使用することから始めます。このレコードでは、そのドメインを使用して確認するメッセージについての統計を送信するように DMARC レシーバーに要求します。監視モード レコードとは、ポリシーをなし (p=none) に設定したDMARC TXT レコードのことです。多くの企業は、p=none の DMARC TXT レコードを発行しています。それより制限の厳しいポリシーを発行することで、どれだけのメールが失われるかについて、明確にはわからないためです。 
    
    これは、メッセージング インフラストラクチャに SPF や DKIM を実装する前でも実行できます。ただし、SPF と DKIM を実装して併用するまでは、DMARC を使用した効果的なメールの検疫や拒否はできません。SPF と DKIM を導入すると、DMARC によって生成されるレポートには、それらのチェックをパスしたメッセージとパスしなかったメッセージの発信元と数が示されます。それらのチェックの適用対象になる (または適用対象にならない) 正当なトラフィックの量を簡単に確認できます。また、あらゆる問題のトラブルシューティングも簡単になります。さらに、どれだけの偽装メッセージが送信されているかや、偽装メッセージの送信元についても、次第にわかるようになります。
    
2. DMARC に失敗したメールの検疫を外部のメール システムに要求する
    
    すべて、または大部分の正当なトラフィックが SPF と DKIM で保護されるという確信が持てるようになり、DMARC の実装による影響を理解したら、検疫ポリシーを実装してください。検疫ポリシーとは、ポリシーを検疫 (p=quarantine) に設定した DMARC TXT レコードのことです。このようにすることで、DMARC レシーバーに対して、DMARC に失敗したドメインからのメッセージを顧客の受信トレイではなく、ローカルのスパム フォルダーと同等のフォルダーに入れるように指示します。
    
3. DMARC に失敗したメッセージを受け取らないように外部システムに要求する
    
    最後の手順は、拒否ポリシーの実装です。拒否ポリシーとは、ポリシーを拒否 (p=reject) に設定した DMARC TXT レコードのことです。これにより、DMARC レシーバーに対して、DMARC チェックに失敗したメッセージを受け取らないように指示します。 
    
## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a>Office 365 が DMARC に失敗した送信メールを処理する方法
<a name="outbounddmarcfail"> </a>

検疫または p を p にポリシーを設定してメッセージが Office 365 から送信され、DMARC が失敗した場合 = = 元に戻す、[送信メッセージの高リスク配信プール](high-risk-delivery-pool-for-outbound-messages.md)を通じてメッセージをルーティングします。送信電子メールのオーバーライドがありません。
  
DMARC 拒否ポリシー (p=reject) を発行すると、どの顧客も Office 365 ではドメインを偽装できなくなります。メッセージは、サービスを通じたメッセージ送信の中継時に、ドメインの SPF または DKIM をパスできないためです。 ただし、DMARC 拒否ポリシーを発行していても、すべてのメールが Office 365 で認証されている場合、前述の説明どおりに受信メールの一部はスパムとしてのマークが付けられます。それ以外のメールは、SPF を発行していない場合に、サービスを通じて送信を中継するようにしていると拒否されます。 これは、DMARC TXT レコードの作成時に、ドメインの代理としてメールを送信するサーバーの一部の IP アドレスとアプリを含め忘れている場合などに発生します。
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a>Office 365 が DMARC に失敗した受信メールを処理する方法
<a name="inbounddmarcfail"> </a>

送信側サーバーの DMARC ポリシーが p=reject の場合、EOP はメッセージを拒否するのではなく、スパムとしてのマークを付けます。つまり、受信メールの場合、Office 365 は p=reject と p=quarantine を同様に扱うということです。
  
このように Office 365 が構成されている理由は、一部の正当なメールが DMARC に失敗することがあるためです。たとえば、メッセージがメーリング リストに送信されてから、リストのすべての参加者にメッセージが中継される場合、DMARC に失敗することがあります。こうしたメッセージを Office 365 が拒否すると、受信者が正当なメールを失うことになり、そのメールを取得する手段がなくなります。 その代わりに、このようなメッセージは DMARC に失敗するようにしておき、スパムのマークを付けて拒否しないようにします。必要であれば、ユーザーは自分の受信トレイから、次の方法でメッセージを取得できます。
  
- ユーザーが、自分のメール クライアントを使用して、個別に安全な送信者を追加する
    
- 管理者が、該当する送信者のメッセージを許可するすべてのユーザーに向けて Exchange トランスポート ルール (ETR) を作成する 
    
## <a name="troubleshooting-your-dmarc-implementation"></a>DMARC 実装のトラブルシューティング
<a name="dmarctroubleshoot"> </a>

ドメインの MX レコードを構成したときに、最初のエントリを EOP 以外にすると、DMARC の失敗はドメインに強制されなくなります。 
  
Office 365 のお客様でも、ドメインのプライマリ MX レコードが EOP を指していないと、DMARC による利点は得られなくなります。たとえば、MX レコードがオンプレミスのメール サーバーを指していて、コネクタを使用することで EOP にメールをルーティングしていると、DMARC は機能しなくなります。このシナリオでは、受信側ドメインは認証済みドメインのいずれかになりますが、EOP はプライマリ MX ではありません。たとえば、contoso.com がそれ自体の MX をポイントしていて、セカンダリ MX レコードとして EOP を使用しているとすると、contoso.com の MX レコードは次のようになります。
  
```
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com

```

すべてまたはほとんどの場合、電子メールは、[プライマリ MX では、EOP にメールが送られますしに最初 mail.contoso.com にルーティングされます。いくつかの場合であっても EOP に MX レコードに一覧表示し、単にあなたの電子メールをルーティングするコネクタをフック可能性があります。EOP は DMARC 検証を実行するための最初のエントリではありません。確認できませんでの設置型と非-O365 のすべてのサーバーが DMARC のチェックを行うことにだけ、検証を保証します。 DMARC はお客様のドメイン (サーバーではなく) に適用する条件を満たすとき、DMARC の TXT レコードを設定するが、実際に強制を行うには、受信側のサーバーにします。 EOP と受信側のサーバーをセットアップする場合は、EOP は DMARC 実施とします。

  
## <a name="for-more-information"></a>詳細情報
<a name="sectionSection8"> </a>

DMARC の詳細情報が必要ですか。以下のリソースが役に立ちます。
  
- [スパム対策メッセージ ヘッダー](anti-spam-message-headers.md) には、Office 365 が DMARC チェックに使用する構文とヘッダー フィールドが含まれています。 
    
- M[3](https://www.m3aawg.org/activities/training/dmarc-training-series)AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group) の「<sup>DMARC TRAINING SERIES</sup>」
    
- [dmarcian](https://space.dmarcian.com/deployment/) のチェックリストを使用する。
    
- [DMARC.org](https://dmarc.org) のソースに直接アクセスする。
    
## <a name="see-also"></a>See also
<a name="sectionSection8"> </a>

[Office 365 において Sender Policy Framework (SPF) を使用して、スプーフィングを防止する方法](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[スプーフィングを防止するために Office 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)

