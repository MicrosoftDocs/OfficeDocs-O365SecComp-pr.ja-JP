---
title: Office 365 でのスプーフィング対策保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/06/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
description: この記事では、偽造された送信者ドメイン (スプーフィングされているドメイン) を使用するフィッシング攻撃に対して Office 365 が軽減される方法について説明します。これは、メッセージを分析し、認証されたメッセージをブロックするために、標準の電子メール認証方法または他の送信者評価手法を使用することで実現します。この変更は、Office 365 の組織に公開されるフィッシング攻撃の数を減らすために実装されています。
ms.openlocfilehash: 041d2ee2cbad1c051c0ca4724d42b189215f0e82
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223876"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Office 365 でのスプーフィング対策保護

この記事では、偽造された送信者ドメイン (スプーフィングされているドメイン) を使用するフィッシング攻撃に対して Office 365 が軽減される方法について説明します。これは、メッセージを分析し、標準の電子メール認証方法またはその他の送信者評価手法を使用して認証できないメッセージをブロックすることによって実現されます。この変更は、お客様がさらされているフィッシング攻撃の数を減らすために実装されています。
  
この記事では、この変更が行われる理由、ユーザーがこの変更をどのように準備できるか、影響を受けるメッセージを表示する方法、メッセージについてのレポート方法、誤検知を軽減する方法、Microsoft がこのように準備する方法についても説明します。変化.
  
Microsoft のスプーフィング対策テクノロジは、最初に office 365 Enterprise E5 サブスクリプションを持っているか、またはサブスクリプションのために office 365 Advanced Threat Protection (ATP) アドオンを購入した組織に展開されていました。2018年10月現在、Exchange Online protection (EOP) を備えた組織に対して保護が拡張されています。また、すべてのフィルターが相互に理解するようになったため、Outlook.com ユーザーも影響を受ける可能性があります。
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>フィッシング攻撃でのスプーフィングの使用方法

ユーザーを保護することにより、Microsoft はフィッシングの脅威に真剣に取り組んでいます。スパム送信者と phishers が一般的に使用する手法の1つはスプーフィングで、送信者が偽造されると、実際のソース以外の人物または他の場所からメッセージが送信されるように表示されます。この手法は、ユーザー資格情報を取得するように設計されたフィッシングキャンペーンでよく使用されます。Microsoft の偽造防止技術では、「From: header」 (Outlook などの電子メールクライアントに表示される) の偽造を具体的に調査しています。Microsoft では、From: ヘッダーがスプーフィングされているという確信がある場合、そのメッセージがスプーフィングとして識別されます。
  
スプーフィングメッセージは、実際のライフユーザーに対して次の2つの悪影響を及ぼします。
  
### <a name="1-spoofed-messages-deceive-users"></a>1. スプーフィングされたメッセージ deceive ユーザー
  
最初に、スプーフィングされたメッセージは、ユーザーがリンクをクリックして、資格情報を表示したり、マルウェアをダウンロードしたり、機密コンテンツ (後者はビジネスメールが危険にさらされる) を含むメッセージに返信したりすることがあります。たとえば、次に示すのは、msoutlook94@service.outlook.com のスプーフィングされた送信者を含むフィッシングメッセージです。
  
![フィッシングメッセージ偽装 service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
上記の操作は実際には service.outlook.com から行われていませんでしたが、その代わりに、フィッシャーによってスプーフィングされたため、そのようになります。ユーザーがメッセージ内のリンクをクリックするように誘導しようとしています。
  
次の例は、スプーフィング contoso.com です。
  
![フィッシングメッセージ-会社のメールが侵害される](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
このメッセージは正規のように見えますが、実際にはなりすましになります。このフィッシングメッセージは、フィッシングのサブカテゴリであるビジネスメール侵害の一種です。
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. ユーザーが偽のメッセージに対して実際のメッセージを混同する
  
2番目に、スプーフィングされたメッセージは、フィッシングメッセージを認識しているが、実際のメッセージとスプーフィングされたメッセージの違いを見分けることができないユーザーに対しては不確実性を作成しますたとえば、次に示すのは、Microsoft セキュリティアカウントの電子メールアドレスからの実際のパスワードのリセットの例です。
  
![Microsoft 正当なパスワードのリセット](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
上記のメッセージは Microsoft から送信されましたが、ユーザーがフィッシングメッセージを取得して、ユーザーがリンクをクリックして、資格情報を入力したり、マルウェアをダウンロードしたり、機密性の高いコンテンツを含むメッセージに返信したりする可能性があります。実際のパスワードのリセットとフェイクの違いを見分けることは難しいため、多くのユーザーはこれらのメッセージを無視するか、スパムとして報告するか、またはメッセージを不必要に Microsoft に報告して、フィッシング詐欺に失敗します。
    
スプーフィングを阻止するため、電子メールフィルター業界は、 [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、 [dkim](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)などの電子メール認証プロトコルを開発してきました。DMARC は、メッセージの送信者を調査できないようにします。ユーザーが電子メールクライアントに表示する (上記の例では、service.outlook.com、outlook.com、および accountprotection.microsoft.com)、SPF または dkim が渡されたドメインを使用しています。つまり、ユーザーに表示されるドメインは認証されているため、スプーフィングされていません。詳細な説明については、このドキュメントの「*電子メール認証がスプーフィングを停止するには常に十分であるとは限りません」* のセクションを参照してください。 
  
ただし、問題は、電子メール認証レコードが省略可能であり、必須ではないことです。そのため、microsoft.com や skype.com のような強力な認証ポリシーを持つドメインはスプーフィングから保護されていますが、弱い認証ポリシーを発行するドメイン、またはポリシーがまったくない場合、スプーフィングされる対象になります。2018年3月の場合、フォーチュン500の企業のうち 9% のドメインのみが、強力な電子メール認証ポリシーを発行します。残りの 91% は、フィッシャーによってスプーフィングされる可能性があり、別のポリシーを使用して電子メールフィルターが検出しない限り、エンドユーザーに配信され、deceive することができます。
  
![フォーチュン500企業の DMARC ポリシー](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
強力な電子メール認証ポリシーを公開する Fortune 500 に含まれていない小規模から中規模の企業の比率は、北米および西ヨーロッパの範囲外のドメインではまだ小さくなっています。
  
これは、企業が電子メール認証のしくみを認識していない場合でも、phishers はその不足を認識して利用するため、大きな問題になります。
  
SPF、dkim、および DMARC の設定の詳細については、このドキュメントの「*Office 365 の顧客*」セクションを参照してください。 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>暗黙的な電子メール認証によるスプーフィングの停止

フィッシングとスピアーフィッシングはこのような問題であり、強力な電子メール認証ポリシーの導入には制限があるため、Microsoft はお客様を保護する機能への投資を継続しています。そのため、microsoft は暗黙的な*電子メール認証*を使用しています。ドメインが認証されていない場合、microsoft はメールの認証レコードを公開した場合と同様に処理し、それに合格しない場合はそれを取り扱います。 
  
これを実現するため、Microsoft では、送信者評価、送信者/受信者履歴、動作分析、その他の高度な手法を含む、通常の電子メール認証にさまざまな拡張機能を構築しています。電子メール認証を公開しないドメインから送信されたメッセージは、正当であることを示す他の通知が含まれていない限り、スプーフィングとしてマークされます。
  
これにより、エンドユーザーは、自分に送信された電子メールがスプーフィングされていないことを確信でき、誰もドメインを偽装していないこと、および Office 365 のお客様が偽装保護などのより優れた保護を提供できるようになります。
  
Microsoft の一般的なアナウンスについては、「[フィッシング Part 2-Office 365 で強化されたスプーフィング対策](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)」を参照してください。
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>メッセージがスプーフィングとして分類されていることを識別する

### <a name="composite-authentication"></a>複合認証

SPF、dkim、DMARC はすべて、自分で使用することができますが、メッセージに明示的な認証レコードがない場合は、十分な認証状態を伝えません。そのため、Microsoft では、複数の信号を複合認証または compauth という1つの値に結合するアルゴリズムを開発しています。Office 365 のお客様は、メッセージヘッダー内の [*認証結果*ヘッダーに compauth 値がスタンプされています。 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**compauth の結果**|**説明**|
|:-----|:-----|
|失敗|メッセージの明示的な認証が失敗しました (dns でドメイン公開レコードを明示的に送信する) か、暗黙の認証を行います (ドメインは dns でレコードを発行していません。そのため、Office 365 は結果を、発行されたレコードのように補間しました)。|
|処理|明示的な認証が渡された (メッセージが渡されたメッセージ、または[最適な推測](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)による DMARC)、または信頼性の高い暗黙的な認証 (送信側ドメインでは電子メール認証レコードは公開されませんが、Office 365 には、DMARC の強力なバックエンドシグナルがあります。メッセージが正当であることを示します。|
|softpass|メッセージが低対中の信頼度で暗黙的な認証を受けた (送信側ドメインでは電子メール認証は公開されませんが、Office 365 にはメッセージが正当であることを示すバックエンド信号がありますが、信号の強度が弱い)。|
|なし|メッセージは認証されていません (または認証されたが、整列されていません)。ただし、送信者評価またはその他の要因により、コンポジット認証は適用されません。|
   
|||
|:-----|:-----|
|**Reason**|**説明**|
|0xx|メッセージの複合認証が失敗しました。<br/>**000**は、拒否または検疫のアクションによってメッセージが失敗したことを意味します。 DMARC。  <br/>**001**は、メッセージが暗黙的な電子メール認証に失敗したことを意味します。これは、送信側ドメインに電子メール認証レコードが公開されていない場合、またはそのようにした場合に、エラーが発生したことを示すエラーポリシー (SPF soft fail またはニュートラル、DMARC policy of p = none) があることを意味します。<br/>**002**は、組織に、スプーフィングされた電子メールの送信を明示的に禁止された送信者/ドメインのペアに対するポリシーがあることを意味します。この設定は、管理者によって手動で設定されます。  <br/>**010**は、メッセージが reject または quarantine の処理によって DMARC に失敗したことを意味し、送信側ドメインは組織の承認済みドメインの1つであることを示します (これは、自己完結型または組織内の一部です)。  <br/>**011**は、メッセージが暗黙的な電子メール認証に失敗したことを意味し、送信側ドメインは、組織の承認済みドメインの1つであることを示します (これは、自己から自己間で、または組織内でのスプーフィングに含まれます)。|
|その他のすべてのコード (1xx、2xx、3xx、4xx、5xx)|メッセージが暗黙的な認証を通過したか、認証が行われなかったが、アクションが適用されなかった理由に関する、さまざまな内部コードに対応します。|
   
メッセージのヘッダーを見ることによって、管理者またはエンドユーザーであっても、送信者がスプーフィングされているという結論で Office 365 を受信する方法を判断できます。
  
### <a name="differentiating-between-different-types-of-spoofing"></a>さまざまな種類のスプーフィングの違い

Microsoft は、2つの異なる種類のスプーフィングメッセージを区別します。
  
 **組織内のスプーフィング**
  
自己自己のスプーフィングとも呼ばれますが、これは、From: アドレス内のドメインが受信者ドメインと同じであるか、またはこのドメインと一致している場合 (受信者のドメインが組織の[承認済みドメイン](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)のいずれかである場合) に発生します。または、From: アドレスのドメインが同じ組織の一部である場合。
  
たとえば、同じドメイン (contoso.com) の送信者と受信者が次のようになります。このページで spambot を実行できないようにするため、メールアドレスにスペースが挿入されます)。
  
From: sender @ contoso.com
  
宛先: 受信者 @ contoso.com
  
次の例では、送信者と受信者のドメインが組織のドメイン (fabrikam.com) と連携しています。
  
From: sender @ foo.fabrikam.com
  
宛先: 受信者 @ bar.fabrikam.com
  
次の送信者と受信者のドメインは異なる (microsoft.com と bing.com)。ただし、それらは同じ組織 (つまり、組織の承認済みドメインの一部) に属しています。
  
From: sender @ microsoft.com
  
宛先: 受信者 @ bing.com
  
組織内のスプーフィングに失敗したメッセージのヘッダーには、次の値が含まれています。
  
スパム対策-レポート:...CAT: SPM/HSPM/PHSH;...SFTY: 9.11
  
CAT はメッセージのカテゴリで、通常は SPM (スパム) としてスタンプされますが、メッセージで発生する他のパターンの種類に応じて、hspm (高精度のスパム) またはフィッシング (フィッシング) の場合があります。
  
SFTY はメッセージの安全性レベルです。最初の桁 (9) はメッセージがフィッシングであることを意味し、ドット (11) の後の数字の2番目のセットは、組織内のスプーフィングであることを意味します。
  
組織内のスプーフィングに対しては、2018 (タイムラインがまだ定義されていない) に対して、複合認証のための具体的な理由コードはありません。
  
 **クロスドメインのスプーフィング**
  
これは、From: アドレスの送信側ドメインが、受信側の組織の外部ドメインである場合に発生します。クロスドメインスプーフィングのために複合認証に失敗するメッセージには、次の値がヘッダーに含まれています。
  
認証-結果:...compauth = fail reason = 000/001
  
スパム対策-レポート:...CAT: スプーフィング;...SFTY: 9.22
  
どちらの場合も、次の赤い安全なヒントがメッセージにスタンプされるか、受信者のメールボックスの言語に合わせてカスタマイズされた同等のものになります。
  
![赤の安全性のヒント-詐欺検知](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
これは、From: アドレスを調べて、受信者の電子メールが何か、または電子メールのヘッダーを調べることによってのみ、組織内およびドメイン間のスプーフィングを区別することができます。
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Office 365 のお客様が新しいスプーフィング対策保護のために自らを準備する方法

### <a name="information-for-administrators"></a>管理者向けの情報

Office 365 の組織の管理者は、いくつかの重要な情報を把握しておく必要があります。
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>電子メール認証がスプーフィングを停止するのに十分ではない理由を理解する

新しいスプーフィング防止保護は、電子メール認証 (SPF、dkim、および DMARC) に依存して、メッセージがスプーフィングとしてマークされないようにします。一般的な例として、送信ドメインが SPF レコードを公開していない場合があります。SPF レコードがない場合、または正しく設定されていない場合、送信されたメッセージは、Microsoft が、メッセージが正当であるというバックエンドインテリジェンスを持っていない限り、スプーフィングとしてマークされます。
  
たとえば、スプーフィング対策が展開されていない場合は、SPF レコードがなく、dkim レコードがなく、DMARC レコードがないというメッセージが次のように表示されている可能性があります。 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
スプーフィング対策の後、Office 365 Enterprise E5、EOP、または ATP がある場合、compauth の値はスタンプされます。
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

example.com が、dkim レコードではなく spf レコードを設定することで修正した場合は、spf が From: アドレス内のドメインと一致しているため、これは複合認証を通過します。 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

または、dkim レコードを設定しても、SPF レコードを設定していない場合は、From: アドレス内のドメインとの間で調整された dkim 署名のドメインであるため、これによっても複合認証が渡されます。 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

ただし、フィッシャーは、SPF と dkim をセットアップして、自分のドメインでメッセージに署名することもできますが、From: アドレスに別のドメインを指定します。SPF も dkim でも、ドメインが From: アドレス内のドメインと一致している必要があるので、example.com が公開されていない DMARC レコードは、DMARC を使用したスプーフィングとしてマークされません。 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

電子メールクライアント (outlook、outlook on the web、またはその他の電子メールクライアント) では、"from: domain" のみが表示されます。これにより、ユーザーが example.com からのメッセージであると誤解を与えることがありますが、実際には maliciousDomain.com から来たものになります。.
  
![認証されたメッセージただし From: ドメインが SPF または dkim に渡されたものと一致しない](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
そのため、Office 365 では、From: アドレスのドメインが SPF または dkim 署名のドメインと一致している必要があり、そうでない場合は、メッセージが正当であることを示す他の内部通知が含まれています。それ以外の場合、メッセージは compauth fail になります。 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

そのため、Office 365 のスプーフィング対策は、認証を行わずにドメインを保護します。認証を設定していないドメインに対しては、ユーザーがメッセージの送信者であると判断した場合と同じであると考えられるドメインに対しては一致しません。これは、組織外のドメインと組織内のドメインの両方に当てはまります。
  
そのため、エラーメッセージが spf と dkim に渡された場合でも、エラーが発生したというメッセージが表示されます。これは、spf と dkim が渡されたドメインが From: アドレス内のドメインと一致していないためです。
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>スプーフィングされたメールの処理方法の変更について

現時点では、Office 365 のすべての組織について、DMARC がポリシーによって拒否または検疫のポリシーによって失敗した場合は、スパムとしてマークされているメッセージ、または通常のスパムアクション (その他のスパムルールは最初にスパムとして識別します)。組織内のスプーフィング検出では、通常のスパムアクションが実行されます。この動作は、有効にする必要はありません。無効にすることもできません。
  
ただし、クロスドメインスプーフィングメッセージの場合は、この変更が定期的なスパム、フィッシング、マルウェアチェックを通過し、フィルターの他の部分が疑わしいと識別された場合は、それらをそれぞれスパム、フィッシング、またはマルウェアとしてマークします。新しいクロスドメインのスプーフィング対策を使用すると、既定では、認証されていないメッセージはフィッシング\>対策対策ポリシーで定義された処理を実行します。定義されていない場合は、[ユーザー] 迷惑メールフォルダーに移動されます。場合によっては、疑わしいメッセージのメッセージにも赤い安全なヒントが追加されることがあります。
  
これにより、スパムとしてマークされたままの状態でスパムとしてマークされていても、安全性のヒントが赤になっているメッセージが発生することがあります。その他の場合は、以前に非スパムとしてマークされたメッセージが、赤い安全なヒントを追加して、スパムとしてマークされるようになります (CAT: スプーフ)。その他の場合でも、すべてのスパムとフィッシングを検疫に移動していたお客様は、それらを迷惑メールフォルダーに移動することになります (この動作は変更できます。変更は、「[スプーフィング対策の設定を変更](#changing-your-anti-spoofing-settings)する」を参照してください)。
  
メッセージが偽装される方法は複数あります (この記事で前述し[た「異なる種類のスプーフィング間](#differentiating-between-different-types-of-spoofing)の相違」を参照してください)。ただし、Office 365 がこれらのメッセージを扱う方法は、2018年3月現在、これらのメッセージは統合されていません。次の表は、クロスドメインスプーフィング対策が新しい動作であることを簡単にまとめたものです。 
  
|**スプーフィングの種類**|**カテゴリ**|**セキュリティヒントが追加されましたか?**|**適用対象**|
|:-----|:-----|:-----|:-----|
|DMARC fail (検疫または拒否)  <br/> |hspm (既定) は、SPM または phsh でもかまいません。  <br/> |いいえ (未完了)  <br/> |すべての Office 365 お客様、Outlook.com  <br/> |
|自己完結型  <br/> |SPM  <br/> |はい  <br/> |すべての Office 365 組織、Outlook.com  <br/> |
|クロスドメイン  <br/> |なりすます  <br/> |はい  <br/> |Office 365 Advanced Threat Protection および E5 お客様  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a>スプーフィング対策の設定を変更する

(クロスドメイン) のスプーフィング対策設定を作成または更新するには、セキュリティ\> \> &amp;コンプライアンスセンターの [脅威の管理ポリシー] タブにある [フィッシング対策] 設定に移動します。フィッシング対策設定を作成していない場合は、次のいずれかを作成する必要があります。
  
![フィッシング対策-新しいポリシーを作成する](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
既に作成してある場合は、それを選択して変更することができます。
  
![フィッシング対策-既存のポリシーを変更する](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
作成したポリシーを選択し、「[スプーフィングインテリジェンスについ](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)て」を参照して、手順を進めます。
  
![スプーフィング防止を有効または無効にする](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![スプーフィング対策の安全性に関するヒントを有効または無効にする](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
PowerShell を使用して新しいポリシーを作成するには、次のようにします。 
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

その後、 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)に記載されているドキュメントに従って、PowerShell を使用してフィッシング対策ポリシーのパラメーターを変更することができます。$name をパラメーターとして指定できます。
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

2018では、既定のポリシーを作成するのではなく、組織内のすべての受信者を対象とするように作成され、手動で指定する必要はありません (以下のスクリーンショットは最終実装の前に変更される可能性があります)。
  
![フィッシング対策の既定のポリシー](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
作成するポリシーとは異なり、既定のポリシーを削除したり、優先度を変更したり、対象とするユーザー、ドメイン、またはグループを選択したりすることはできません。
  
![フィッシング対策の既定のポリシーの詳細](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
PowerShell を使用して既定の保護を設定するには、次のようにします。
  
```
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

Office 365 の前に別のメールサーバーまたはサーバーがある場合にのみ、スプーフィング防止保護を無効にします (詳細については、「スプーフィング対策を無効にする」を参照してください)。 
  
```
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> メールパスの最初のホップが Office 365 で、スプーフィングとしてマークされた正当な電子メールが多すぎる場合は、まずドメインへのスプーフィングされたメールを送信することが許可された送信者を設定する必要があります (「u を送信している*正当な送信者を管理する」を参照してください)。n 認証*された電子メール)。まだ誤検知 (なりすましとしてマークされている正当なメッセージなど) を取得している場合は、スプーフィング対策保護を完全に無効にすることはお勧めしません。代わりに、高レベルの保護ではなく Basic を選択することをお勧めします。                   偽陽性を使用した方が、長期間において大幅にコストがかかることがあるように組織を偽装した電子メールを公開するよりもよいでしょう。

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>認証されていない電子メールを送信している正当な送信者の管理

Office 365 は、組織に対して認証されていない電子メールを送信しているユーザーを追跡します。サービスが送信者が正当でないと判断すると、その送信者は*compauth*エラーとしてマークされます。これは、メッセージに適用されたスプーフィング対策ポリシーによって決まるので、スプーフィングとして分類されます。 
  
ただし、管理者として、スプーフィングされた電子メールを送信することを許可する送信者を指定できます。 Office 365 の決定は無効です。
  
**方法 1-組織がドメインを所有している場合は、電子メール認証を設定します。**
  
この方法は、複数のテナントを所有または操作する場合に、組織内のスプーフィングを解決し、クロスドメインのスプーフィングを解決するために使用できます。また、Office 365 内の他のお客様に送信するクロスドメインのスプーフィングや、他のプロバイダーでホストされているサードパーティも解決できます。
  
詳細については、「 [Office 365 のお客様](#customers-of-office-365)」を参照してください。 
 
**方法 2-スプーフィングインテリジェンスを使用して、認証されていない電子メールの許可された送信者を構成する**
  
[スプーフィングインテリジェンス](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)を使用して、送信者が認証されていないメッセージを組織に送信することを許可することもできます。 
  
外部ドメインの場合、スプーフィングされたユーザーは From アドレスのドメイン、送信元インフラストラクチャは送信元 ip アドレス (最大 24 CIDR 範囲に分割)、または PTR レコードの組織的ドメイン (以下のスクリーンショットでは、送信元 ip がPTR レコードが outbound.mail.protection.outlook.com で、送信元のインフラストラクチャの outlook.com として表示される131.107.18.4 になります。
  
この送信者が認証されてい**ない**電子メールを送信することを許可するには、 **[いいえ] を [はい]** に変更します。
  
![スプーフィング防止が許可された送信者の設定](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
PowerShell を使用して、特定の送信者がドメインを偽装できるようにすることもできます。 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Powershell を使用してスプーフィングされた送信者を取得する](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
前の画像では、このスクリーンショットが適合するように改行が追加されていますが、実際には、すべての値が1行に表示されることになります。
  
ファイルを編集して、outlook.com と bing.com に対応する行を検索し、allowedtospoof エントリを [いいえ] から [はい] に変更します。
  
![Powershell を使用してスプーフ許可を Yes に設定する](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
ファイルを保存し、次のように実行します。 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

これで、bing.com が outlook.com から\*認証されていない電子メールを送信できるようになります。

**方法 3-送信者/受信者のペアの許可エントリを作成する**
  
特定の送信者に対してすべてのスパムフィルタリングをバイパスすることを選択することもできます。詳細については、「 [Office 365 の許可一覧に送信者を安全に追加する方法](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)」を参照してください。
  
このメソッドを使用する場合は、スパムと、フィッシングフィルタリングではなく、一部のスパムをスキップします。
  
**方法 4-送信者に連絡して、電子メール認証を設定するように依頼します。**
  
スパムやフィッシングの問題のため、すべての送信者が電子メール認証を設定することをお勧めします。送信側ドメインの管理者がわかっている場合は、それらのユーザーに連絡して、電子メール認証レコードの設定を要求して、上書きを追加する必要はありません。詳細については、この記事で後述[する「Office 365 の顧客ではないドメインの管理者](#administrators-of-domains-that-are-not-office-365-customers)」を参照してください。 
  
最初に認証のためにドメインを送信することが難しい場合がありますが、時間が経つにつれて、junking を開始したり、電子メールを拒否したりすると、適切なレコードが設定されて配信が向上します。
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>スプーフィングとしてマークされたメッセージの数のレポートを表示する

スプーフィング対策ポリシーを有効にしたら、脅威インテリジェンスを使用して、フィッシングとしてマークされているメッセージの数を示す数値を取得できます。これを行うには、[脅威&amp;管理\>エクスプローラー] の下の [セキュリティ/コンプライアンスセンター (SCC)]、[ビュー] を [フィッシング] に設定し、[送信者ドメインまたは保護の状態でグループ化] の順に移動します。
  
![フィッシングとしてマークされているメッセージの数を表示する](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
さまざまなレポートを操作して、スプーフィングとしてマークされたメッセージなど、フィッシングとしてマークされた回数を確認できます。詳細については、「 [Office 365 の脅威インテリジェンスの概要](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441)」を参照してください。
  
スプーフィングとその他の種類のフィッシング (一般的なフィッシング、ドメインまたはユーザー偽装など) によってマークされたメッセージを分割アウトすることはできません。ただし、2018では、セキュリティ&amp;コンプライアンスセンターを使用してこれを行うことができます。その後、このレポートを使用して、認証に失敗したためにスプーフィングとしてマークされている正当なドメインを特定することができます。
  
次のスクリーンショットは、このデータがどのように表示されるかを提案していますが、リリースされると変わる可能性があります。
  
![検出の種類によるフィッシングレポートの表示](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
非 ATP および E5 のお客様の場合、これらのレポートは、脅威保護の状態 (TPS) レポートの2018で後で利用可能になりますが、少なくとも24時間は遅延します。このページは、セキュリティ&amp;コンプライアンスセンターに統合されると更新されます。
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>スプーフィングとしてマークされるメッセージの数を予測する

2018で後で、Office 365 が設定を更新して、スプーフィング対策の実施を無効にしたり、基本または高強制に設定したりすると、さまざまな設定でメッセージの廃棄がどのように変化するかを確認することができます。つまり、スプーフィング対策がオフになっている場合は、Basic を有効にすると、スプーフィングとして検出されるメッセージの数を確認できます。または、基本の場合は、それより多くのメッセージがスプーフィングとして検出された場合に、それを高にすることができます。
  
この機能は現在開発中です。詳細が定義されると、このページは、セキュリティ/コンプライアンスセンターのスクリーンショットと、PowerShell の例を使用して更新されます。
  
![スプーフィング対策を有効にするための「what-if If」レポート](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![スプーフィングされた送信者を許可するために使用できる UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a>スパム、フィッシング、および高度なフィッシング検出がどのように統合されるかを理解する

Exchange Online を使用する組織では、ATP があるかどうかにかかわらず、サービスがマルウェア、スパム、信頼度の高いスパム、フィッシング、および一括でメッセージを識別するときに実行するアクションを指定できます。atp のお客様のための atp のフィッシング対策ポリシーと、EOP のお客様のためのフィッシング対策ポリシーを使用しており、メッセージが複数の検出タイプ (マルウェア、フィッシング、ユーザー偽装など) をヒットすることがあるという事実については、次のような混乱があります。ポリシーが適用されます。 
  
一般に、メッセージに適用されるポリシーは、CAT (Category) プロパティのスパム対策ヘッダーで識別されます。 
  
|**Priority**|**ポリシー**|**カテゴリ**|**管理されている場所**|**適用対象**|
|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |マルウェア  <br/> |悪意のある w  <br/> |[マルウェアポリシー](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |すべての組織  <br/> |
|2  <br/> |フィッシング  <br/> |phsh  <br/> |[ホスト型コンテンツフィルターポリシー](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |すべての組織  <br/> |
|1/3  <br/> |信頼度の高いスパム  <br/> |hspm  <br/> |[ホスト型コンテンツフィルターポリシー](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |すべての組織  <br/> |
|2/4  <br/> |すまし  <br/> |なりすます  <br/> |[フィッシング対策ポリシー](https://go.microsoft.com/fwlink/?linkid=864553)、[スプーフィングインテリジェンス](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) <br/> |すべての組織  <br/> |
|5  <br/> |スパム  <br/> |SPM  <br/> |[ホスト型コンテンツフィルターポリシー](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |すべての組織  <br/> |
|6  <br/> |大半  <br/> |大半  <br/> |[ホスト型コンテンツフィルターポリシー](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |すべての組織  <br/> |
|7   <br/> |ドメイン偽装  <br/> |dimp  <br/> |[フィッシング対策ポリシー](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |ATP のみを使用している組織  <br/> |
|8   <br/> |ユーザー偽装  <br/> |uimp  <br/> |[フィッシング対策ポリシー](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |ATP のみを使用している組織 <br/> |
   
複数の異なるフィッシング対策ポリシーがある場合は、優先度の高いポリシーが適用されます。たとえば、次の2つのポリシーがあるとします。
  
|**ポリシー**|**Priority**|**ユーザー/ドメインの偽装**|**スプーフィング対策**|
|:-----|:-----|:-----|:-----|
|A  <br/> |1  <br/> |On  <br/> |Off  <br/> |
|B  <br/> |2  <br/> |Off  <br/> |オン  <br/> |
   
メッセージが受信され、スプーフィングとユーザー偽装の両方として識別され、同じユーザーセットがポリシー a およびポリシー B を対象としている場合、メッセージはスプーフィングとして扱われますが、スプーフィング対策がオフになっているため、アクションは適用されません。、なりすましは、ユーザー偽装 (8) よりも高い優先度 (4) で実行されます。
  
他の種類のフィッシングポリシーを適用するには、さまざまなポリシーを適用するユーザーの設定を調整する必要があります。
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>スプーフィング対策を無効にするための正当なシナリオ

スプーフィング対策は、フィッシング攻撃からお客様を保護します。そのため、スプーフィング対策保護を無効にすることをお勧めしません。この設定を無効にすることで、短期的な誤検知を解決できる場合がありますが、長期になると、より多くのリスクにさらされることになります。送信側で認証をセットアップする、またはフィッシングポリシーを調整するためのコストは、通常、1回限りのイベントであるか、定期的なメンテナンスを最小限に抑える必要があります。ただし、データが公開されている、またはアセットが侵害されているフィッシング攻撃から回復するためのコストが大幅に増加します。
  
このため、スプーフィング防止保護を無効にするよりも、スプーフィング対策の誤検知を使用したほうがよい場合があります。
  
しかし、メッセージのルーティングに他のメールフィルター処理製品があり、Office 365 が電子メールのパスの最初のホップではない場合に、スプーフィング対策を無効にする必要があるという正当なシナリオがあります。
  
![お客様の MX レコードが Office 365 を指していない](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
その他のサーバーは、Exchange オンプレミスのメールサーバー、Ironport などのメールフィルターデバイス、または他のクラウドホストサービスである場合があります。
  
受信者のドメインの mx レコードが office 365 を指していない場合、office 365 は受信側のドメインの mx レコードを検索し、別のサービスを指している場合にはスプーフィング対策を抑制するため、スプーフィング対策を無効にする必要はありません。ドメインの前に別のサーバーがあるかどうかわからない場合は、mx ツールバーなどの web サイトを使用して mx レコードを調べることができます。次のような内容になるかもしれません。
  
![MX レコードは、ドメインが Office 365 をポイントしていないことを示します。](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
このドメインには、office 365 をポイントしない MX レコードが含まれているため、office 365 はスプーフィング対策の実施を適用しません。
  
ただし、受信者のドメインの MX レコードが** office 365 を指している場合は、office 365 の前に別のサービスがある場合でも、スプーフィング対策を無効にする必要があります。最も一般的な例として、受信者書き換えを使用する方法があります。 
  
![受信者の書き換え用のルーティングダイアグラム](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
ドメイン protection.outlook.com、または eo.outlook.com に mx レコードが含まれているため、ドメインの mx レコードはオンプレミスのサーバーを指していますが、mx \*レコードには\*が含まれているため、Office 365 を指しています。
  
![MX レコードは Office 365 を指しているため、受信者書き換えの可能性があります。](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
受信者のドメインの MX レコードが Office 365 をポイントしていない場合と、受信者の書き換えに切り替えられた場合は、必ず区別してください。この2つのケースの違いを伝えることが重要です。
  
受信側のドメインで受信者の書き換えが行われているかどうかがわからない場合は、メッセージヘッダーを参照して確認することもできます。
  
) 最初に、認証結果ヘッダー内の受信者ドメインのメッセージのヘッダーを確認します。 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

受信者のドメインは、上記の太字の赤いテキスト (この例では office365.contoso.net) にあります。これは、To: ヘッダーの受信者と異なる場合があります。
  
宛先: 受信者\<受信者 @ contoso.com の例\>
  
実際の受信者ドメインの MX レコード検索を実行します。protection.outlook.com、mail.messaging.microsoft.com \*、 \*eo.outlook.com、または mail.global.frontbridge.com が含まれている場合は、MX が Office 365 をポイントしていることを意味します。
  
この値が含まれていない場合は、MX が Office 365 を指していないことを意味します。これが MX ツールボックスであることを確認するために使用できる1つのツール。
  
この例では、次のようにします。この例では、contoso.com (To: ヘッダーの後に受信者として表示されるドメイン) は、MX レコードがオンプレミスサーバーを指しています。
  
![MX レコードがオンプレミスサーバーを指している](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
ただし、実際の受信者は、office365.contoso.net が Office 365 をポイントしている場合は、次のようになります。
  
![MX は Office 365 を指しており、受信者の書き換えである必要があります。](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
そのため、このメッセージは受信者書き換えになっている可能性があります。
  
b) 2 番目に、受信者の書き換えの一般的なユースケースを区別してください。受信者のドメインを onmicrosoft.com に\*書き直す場合は、代わりに mail.onmicrosoft.com に\*書き換えます。
  
別のサーバーの背後にルーティングされ、受信者ドメインの MX レコードが実際に Office 365 を指している (DNS レコードに公開されている) ことを確認したら、スプーフィング対策を無効にすることができます。
  
ルーティングパスのドメインの最初のホップが Office 365 の場合は、1つ以上のサービスが実行されている場合に限り、スプーフィング対策を無効にしないことを忘れないでください。
  
### <a name="how-to-disable-anti-spoofing"></a>スプーフィング対策を無効にする方法

フィッシング対策ポリシーが既に作成されている場合は、EnableAntispoofEnforcement パラメーターを $false に設定します。 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

無効にするポリシーの名前 (ポリシー) がわからない場合は、次のように表示できます。 
  
```
Get-AntiphishPolicy | fl Name
```

既存のマルウェア対策ポリシーがない場合は、それを作成して無効にすることができます (ポリシーがない場合でも、スプーフィング対策は引き続き適用されます)。2018では、既定のポリシーが作成され、それを作成するのではなく無効にすることができます。.これは、複数の手順で行う必要があります。 
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the antiphishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false 

```

スプーフィング対策を無効にする操作は、コマンドレットを介してのみ使用できます (2018 年&amp;第2四半期後、セキュリティセンターコンプライアンスセンターで利用できます)。PowerShell にアクセスできない場合は、サポートチケットを作成します。
  
これは、Office 365 に送信された場合に、間接的なルーティングが行われるドメインにのみ適用する必要があることに注意してください。誤検知を無効にしないようにしないようにしてください。これにより、長期に対応していることがあります。
  
### <a name="information-for-individual-users"></a>個々のユーザー向けの情報

個々のユーザーは、スプーフィング対策の安全性のヒントを操作する方法に制限があります。ただし、一般的なシナリオを解決するには、いくつかの方法があります。
  
### <a name="common-scenario-1---mailbox-forwarding"></a>一般的なシナリオ #1-メールボックス転送

別の電子メールサービスを使用して、Office 365 または Outlook.com に電子メールを転送すると、電子メールがスプーフィングとしてマークされ、赤い安全なヒントが表示される場合があります。office 365 および Outlook.com は、フォワーダーが Outlook.com、Office 365、Gmail、または[ARC プロトコル](https://arc-spec.org)を使用するその他のサービスのいずれかである場合に、このことを自動的に解決することを計画します。ただし、修正が展開されるまで、ユーザーは、[転送] オプションを使用するのではなく、接続されたアカウント機能を使用してメッセージを直接インポートする必要があります。
  
office 365 \>で接続されたアカウントをセットアップするには、office 365 web インターフェイスのメール\>メール\>アカウント\>が接続されたアカウントの右上隅にある歯車アイコンを選択します。
  
![Office 365-接続されたアカウントのオプション](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
Outlook.com でのプロセスは\> 、[メール\> \>アカウント\>が接続されているアカウント] の歯車アイコンオプションです。
  
### <a name="common-scenario-2---discussion-lists"></a>一般的なシナリオ #2-ディスカッションリスト

ディスカッションリストには、メッセージを転送し、そのコンテンツを変更して元の差出人: アドレスを保持することによって、スプーフィング対策の問題が発生することが知られています。
  
たとえば、電子メールアドレスがユーザー @ contoso.com で、鳥を見ていて、ディスカッションリスト birdwatchers @ example.com に参加したいとします。ディスカッションリストにメッセージを送信する場合は、次のように送信することができます。
  
**From:** John Doe \<user @ contoso.com\> 
  
**宛先:** Birdwatcher のディスカッションリスト\<birdwatchers @ example.com\> 
  
**件名:** この週の Rainier の一番上に青を重ねて表示します。 
  
Rainier で今週の表示をチェックアウトするユーザー
  
電子メールリストがメッセージを受信すると、メッセージの書式を設定し、その内容を変更して、さまざまな電子メール受信者からの参加者で構成されるディスカッションリストにあるメンバーの残りのメンバーに再生します。
  
**From:** John Doe \<user @ contoso.com\> 
  
**宛先:** Birdwatcher のディスカッションリスト\<birdwatchers @ example.com\> 
  
**件名:**[BIRDWATCHERS]この週の Rainier の一番上に青を重ねて表示します。 
  
Rainier で今週の表示をチェックアウトするユーザー
  
---
  
このメッセージは Birdwatchers のディスカッションリストに送信されました。いつでも登録を解除できます。
  
上記の例では、再生されるメッセージの From: address (user @ contoso.com) は同じですが、元のメッセージは件名行にタグを追加することによって変更され、フッターがメッセージの一番下に表示されます。この種のメッセージ変更は、メーリングリストでよく行われ、誤検知につながる可能性があります。
  
組織内のユーザーがメーリングリストの管理者である場合は、それを構成してスプーフィング対策チェックに合格することができます。
  
- DMARC.org の FAQ を確認してください。「[メーリングリストを運用しているので、DMARC と相互運用する必要があるのですが、どうすればいいですか?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)
    
- このブログ投稿の手順を読んでください。[メーリングリストオペレーターが DMARC と相互運用して障害を回避するためのヒント](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)
    
- ARC をサポートするために、メーリングリストサーバーに更新プログラムをインストールすることを検討してください。[https://arc-spec.org](https://arc-spec.org/)
    
メーリングリストの所有権を持っていない場合:
  
- メーリングリストのメンテナに対して、上記のオプションの1つを実装するよう要求することができます (メーリングリストの中継元ドメインに対して電子メール認証を設定する必要もあります)。
    
- メールクライアントでメールボックスルールを作成して、メッセージを受信トレイに移動することができます。「認証されていない電子メールを送信している正当な送信者を管理する」のセクションで説明されているように、組織の管理者に許可ルールの設定または上書きを要求することもできます。
    
- Office 365 を使用してサポートチケットを作成し、宛先リストの上書きを作成して正規のものとして扱うことができます。
    
### <a name="other-scenarios"></a>その他のシナリオ

1. 上記の一般的なシナリオがどちらも状況に当てはまらない場合は、そのメッセージを誤検知として Microsoft に報告します。詳細については、この記事の後半の「[スパムまたは非スパムメッセージを Microsoft に報告する方法](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)」を参照してください。 
    
2. Microsoft とのサポートチケットとして、メール管理者に連絡することもできます。Microsoft のエンジニアリングチームは、メッセージがスプーフィングとしてマークされた理由を調査します。
    
3. さらに、送信者が悪意のある人物であることがわかっている場合は、認証されていないメールサーバーからメッセージを送信していることを通知するメッセージを送信者に返信することもできます。これにより、元の送信者が、必要な電子メール認証レコードを設定する IT 管理者にアクセスすることがあります。
  
メールの認証レコードを設定する必要があることをドメインの所有者に返信するのに十分な数の送信者がいる場合は、それらを spurs してアクションを実行する必要があります。また、Microsoft はドメインの所有者と協力して必要なレコードを発行していますが、個々のユーザーが要求すると、さらに役に立ちます。
    
4. 必要に応じて、送信者を [信頼できる差出人のリスト] に追加します。ただし、フィッシャーがそのアカウントをスプーフすると、そのアカウントがメールボックスに配信されることに注意してください。そのため、このオプションは慎重に使用する必要があります。
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>Microsoft に送信者がスプーフィング対策保護を準備する方法

現在、Microsoft にメッセージを送信している管理者 (Office 365 または Outlook.com のいずれか) の場合は、電子メールが正しく認証されていることを確認する必要があります。そうでない場合は、スパムまたはフィッシングとしてマークされる可能性があります。 
  
### <a name="customers-of-office-365"></a>Office 365 のお客様

office 365 お客様の場合、office 365 を使用して送信電子メールを送信するには、次のようにします。
  
- ドメインの場合、[スプーフィングを防止するために Office 365 で SPF をセットアップ](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)します。
    
- プライマリドメインの場合は、 [dkim を使用して、Office 365 でカスタムドメインから送信される送信電子メールを検証](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)します。
    
- 自分のドメインの[DMARC レコードをセットアップして](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)、正当な送信者であるユーザーを特定することを検討してください。 
    
Microsoft は、SPF、dkim、および DMARC のそれぞれについて、詳細な実装ガイドラインを提供していません。しかし、オンラインで公開されている情報はたくさんあります。また、組織でメールの認証レコードを設定するための専任のサードパーティ企業もあります。
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>Office 365 をご利用のお客様以外のドメインの管理者

ドメイン管理者であり、Office 365 お客様ではない場合:
  
- SPF をセットアップして、ドメインの送信元 IP アドレスを公開し、メッセージにデジタル署名するために dkim (使用可能な場合) を設定する必要があります。DMARC レコードのセットアップを検討することもできます。
    
- 自分の代わりに電子メールを送信しているバルク送信者がある場合、それらのユーザーと共に電子メールを送信して、SPF または DMARC を通過するドメインに対して送信元のアドレス (自分が属している場合) を送信することができます。
    
- オンプレミスのメールサーバーを使用している場合、または Microsoft Azure、GoDaddy、Rackspace、Amazon Web サービスなどのクラウドホストサービスから送信している場合は、SPF レコードに追加されていることを確認する必要があります。
    
- isp によってホストされている小規模のドメインの場合は、isp によって提供される指示に従って SPF レコードを設定する必要があります。ほとんどの isp は、このような種類の指示を提供しており、企業のサポートページにあります。
    
- 電子メール認証レコードを発行する必要がなく、正常に動作していた場合でも、電子メール認証レコードを公開して Microsoft に送信する必要があります。そうすることで、フィッシング対策を行うことができ、自分または組織の phished のどちらかに送信される可能性を減らすことができます。
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>ドメインとしてメールを送信するユーザーがわからない場合はどうすればよいですか?

多くのドメインでは、すべての送信者が誰であるかがわからないため、SPF レコードは公開されません。それでも、すべてのユーザーを知る必要はありません。その代わりに、自分が知っているものに対して SPF レコードを発行し、特に企業のトラフィックが配置され、ニュートラル SPF ポリシーを発行することによって、開始する必要があります。
  
example.com IN TXT "v = spf1 には、次のようにします。
  
中立的な SPF ポリシーは、企業インフラストラクチャから出たすべての電子メールが、他のすべての電子メールレシーバーで電子メール認証を通過することを意味します。知らない送信者から送信された電子メールは、中立的にフォールバックすることになります。これは、SPF レコードの公開とほとんど同じです。
  
office 365 に送信すると、企業のトラフィックからの電子メールは認証済みとしてマークされますが、不明なソースからのメールは、(Office 365 が暗黙的に認証できるかどうかに応じて) スプーフィングとしてマークされることがあります。しかし、これは、Office 365 によってスプーフィングとしてマークされているすべての電子メールについては引き続き改善されています。
  
フォールバックポリシーが設定された SPF レコードの使用を開始すると、より多くの送信元インフラストラクチャを徐々に追加して、より厳しいポリシーを発行することができます。 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>メーリングリストの所有者である場合は、どうすればよいですか?

「[一般的なシナリオ #2 ディスカッションリスト](#common-scenario-2---discussion-lists)」を参照してください。 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>インターネットサービスプロバイダー (ISP)、電子メールサービスプロバイダー (ESP)、クラウドホスティングサービスなどのインフラストラクチャプロバイダーである場合は、どうすればよいですか?

ドメインの電子メールをホストしていて、電子メールを送信できるホスティングインフラストラクチャを提供している場合は、次の操作を実行する必要があります。
  
- お客様が SPF レコードで発行する内容を詳述したドキュメントを所有していることを確認する
    
- お客様が明示的に設定していない場合でも (既定のドメインで署名する)、送信メールで dkim-署名に署名することを検討してください。また、dkim 署名を使用して電子メールを二重署名することもできます (顧客のドメインに設定されている場合は一度に、会社の dkim 署名に対して2回目の署名を使用します)。
    
プラットフォームからの電子メールを認証している場合でも、Deliverability は保証されませんが、少なくとも、認証されていないため、microsoft はメールを迷惑メールではないことを保証します。Outlook.com が電子メールをフィルター処理する方法の詳細については、 [Outlook.com ポストマスターページ](https://postmaster.live.com/pm/postmaster.aspx)を参照してください。
  
サービスプロバイダーのベストプラクティスの詳細については、「 [M3AAWG Mobile Messaging best 習慣 for service providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)」を参照してください。
  
## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="why-is-microsoft-making-this-change"></a>Microsoft がこの変更を行うのはなぜですか?

フィッシング攻撃が影響を受けるため、電子メール認証が15年以上にわたって存在するため、Microsoft は、認証されていない電子メールを引き続き許可するリスクが正当なメールを失うリスクよりも高いと考えています。
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>この変更によって正当な電子メールがスパムとしてマークされるようになりますか。

最初に、スパムとしてマークされているメッセージがいくつかあります。しかし、時間の経過と共に送信者が調整し、mislabeled のメッセージ数は、ほとんどの電子メールパスでは無視できる程度になります。
  
Microsoft は、この機能をお客様の他のユーザーに展開する前に数週間にわたって採用しています。最初に中断が発生しても、徐々に拒否されます。
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>Microsoft は、Office 365 の Outlook.com および Advanced 以外の脅威保護のお客様にこの機能を提供しますか?

Microsoft のスプーフィング対策テクノロジは、最初に office 365 Enterprise E5 サブスクリプションを持っているか、またはサブスクリプションのために office 365 Advanced Threat Protection (ATP) アドオンを購入した組織に展開されていました。2018年10月現在、Exchange Online protection (EOP) を備えた組織に対して保護が拡張されています。将来的には、Outlook.com のためにリリースされる可能性があります。ただし、レポートやカスタムオーバーライドなど、適用されていない機能がある場合があります。
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>スパムまたは非スパムメッセージを Microsoft に報告するにはどうすればよいですか?

[Outlook 用のレポートメッセージアドイン](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を使用するか、またはそれがインストールされていない場合は、[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)することができます。
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>すべての送信者が誰であるかを把握していないドメイン管理者です。

「 [Office 365 のお客様ではないドメインの管理者」を](#administrators-of-domains-that-are-not-office-365-customers)参照してください。
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>Office 365 がプライマリフィルターであっても、自分の組織のスプーフィング対策保護を無効にした場合はどうなりますか。

これは、検出されていないフィッシングおよびスパムメッセージに公開されるため、お勧めしません。すべてのフィッシングがスプーフィングであるとは限りません。また、すべてのスプーフィングが失われるわけではありません。ただし、リスクは、スプーフィング対策を有効にしたお客様よりも高くなります。
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>スプーフィング対策保護を有効にすることは、すべてのフィッシングから保護されることを意味しますか?

phishers は、侵害されたアカウントなどの他の手法を使用するか、無料サービスのアカウントを設定することに適応するため、残念です。ただし、Office 365 の保護レイヤーは相互に連携して相互に機能するように設計されているため、フィッシング対策保護は、これらの他の種類のフィッシング方式を検出するのに非常に優れています。
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>その他の大規模な電子メール受信者は認証されていない電子メールをブロックするか

ほぼすべての大規模メールレシーバーは、従来の SPF、dkim、DMARC を実装しています。一部の受信者には、これらの標準だけではより厳密な他のチェックがありますが、認証されていない電子メールをブロックし、それらをスプーフィングとして扱うことはほとんどありません。しかし、このような特定の種類の電子メールについては、特にフィッシングの問題があるため、業界のほとんどがより厳密になりつつあります。
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>スプーフィング対策を有効にした場合、"SPF Hard Fail" に対して高度なスパムフィルターオプションが有効になっている必要がありますか?

いいえ。ただし、このオプションは、SPF の障害を考慮するだけでなく、非常に幅広い条件セットを考慮しているため、このオプションは不要になりました。スプーフィング対策が有効になっており、SPF Hard Fail オプションが有効になっている場合は、さらに多くの誤検知が表示される可能性があります。この機能を無効にすることをお勧めします。これにより、スパムまたはフィッシングの追加のキャッチはほとんど提供されません。代わりに、ほとんどが誤検知を生成します。
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>送信者書き換えスキーム (SRS) は転送された電子メールの修正に役立ちますか?

SRS は、転送された電子メールの問題を部分的に修正するだけです。SMTP メールをから再書き込みすることで、SRS は転送されたメッセージが次の宛先に SPF を通過することを保証できます。ただし、スプーフィング対策は、from: アドレスと (またはその他の信号の) from または dkim 署名ドメイン (またはその他の信号) のどちらかとの組み合わせに基づいているため、転送された電子メールがスプーフィングとしてマークされないようにするだけで十分ではありません。
  

