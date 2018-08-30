---
title: Office 365 でのスプーフィング対策保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
description: この資料では、どのように Office 365 を軽減するフィッシング攻撃使用が送信者ドメインがスプーフィングされているドメインは、偽造されたことを説明します。メッセージを分析してこれを達成して、標準的な電子メールの認証方法やその他の送信者評価の手法を使用して、neithe を認証することができるものをブロックします。Office 365 の組織に公開するフィッシング攻撃の数を減らすためにこの変更が実装されています。
ms.openlocfilehash: bbcfbcdf32c87e070f10c9478a7c5978e909f009
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22559222"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Office 365 でのスプーフィング対策保護

この資料では、どのように Office 365 を軽減するフィッシング攻撃使用が送信者ドメインがスプーフィングされているドメインは、偽造されたことを説明します。メッセージを分析し、標準的な電子メールの認証方法やその他の送信者評価の手法を使用して認証できないものをブロックして、これを実現します。お客様に公開するフィッシング攻撃の数を減らすためにこの変更が実装されています。
  
説明なぜこの変更、この変更の顧客をどのように準備することができます、影響を受けるメッセージを表示するのには、メッセージを報告する方法、誤を軽減する方法と、これはマイクロソフトに送信者をどのように準備する必要があります。変更します。
  
マイクロソフトのスプーフィング対策技術は、Office 365 高度な脅威保護 (ATP) と E5 のお客様に最初に展開しました。ただし、互いから学ぶすべてのフィルターのため、分析ツールではないお客様、Outlook.com のユーザーも影響します。
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>フィッシング攻撃の偽装の使用方法

そのユーザーを保護する際に、マイクロソフトはフィッシング詐欺の脅威が最重要視します。スパムやフィッシングをよく使用する方法の 1 つは、なりすまし、送信者を偽造すると、ときに、誰かやどこかに実際のソースとは別に発信するメッセージが表示されます。この手法は、ユーザーの資格情報を取得するように設計されたフィッシング詐欺のキャンペーンでよく使用されます。マイクロソフトのアンチ スプーフ テクノロジーの偽造を調べて具体的には、' から: ヘッダー ' Outlook などの電子メール クライアントに表示されるものであります。マイクロソフトは、精度の高いを From: ヘッダーのスプーフィングは、スプーフィングとしてメッセージを識別します。
  
なりすましメッセージは、実際のユーザーの 2 つの負影響を与えます。
  
### <a name="1-spoofed-messages-deceive-users"></a>1. スプーフィングされたメッセージは、ユーザーをだます
  
最初に、偽装されたメッセージがユーザーをだましてリンクをクリックして、資格情報を提供、マルウェアをダウンロードまたは (後者のでと呼ばれる危険にさらされるビジネス電子メール)、機密性の高いコンテンツを含むメッセージに返信します。たとえば、msoutlook94@service.outlook.com の送信者が偽装のフィッシング詐欺のメッセージは次のように。
  
![Service.outlook.com を偽装するフィッシング詐欺のメッセージ](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
上から service.outlook.com、実際には発生しないが代わりにフィッシャーと同様の外観にすることによって偽装されました。ユーザーを騙して、メッセージ内のリンクをクリックしてましょう。
  
次の使用例は、contoso.com がスプーフィングします。
  
![フィッシング詐欺の危険にさらされるビジネス e メール](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
メッセージは合法的では、スプーフィングを実際には。このフィッシング詐欺は、フィッシング詐欺の一種であるビジネス電子メールのセキュリティ侵害の種類です。
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. ユーザーが偽のものの実際のメッセージを混乱させる
  
2 番目、スプーフィングされたメッセージは、ユーザーがフィッシング詐欺メッセージを知るには、本物のメッセージと偽装している 1 つの違いのための不確実性を作成します。たとえば、以下、マイクロソフトのセキュリティ アカウントの電子メール アドレスからのリセットの実際のパスワードの例です。
  
![マイクロソフトの正規のパスワードのリセット](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
上記のメッセージは、マイクロソフトから来たが、同時に、ユーザーがフィッシング詐欺メッセージを取得することがユーザーをだましてリンクをクリックすると、自分の資格情報を提供し、マルウェアをダウンロード、または機密性の高いコンテンツを含むメッセージに返信します。実際のパスワードのリセットとフェイクの 1 つの違いを見分けるには難しいので、多くのユーザーがこれらのメッセージを無視する、スパムとして報告または不必要にメッセージをマイクロソフトに報告失敗したフィッシング詐欺として。
    
偽装を停止するには、業界をフィルタ リングする電子メールは、 [SPF](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)、 [DKIM](https://technet.microsoft.com/en-us/library/mt695945%28v=exchg.150%29.aspx)、 [DMARC](https://technet.microsoft.com/en-us/library/mt734386%28v=exchg.150%29.aspx)など、電子メール認証プロトコルを開発しました。DMARC は、メッセージの送信者の電子メール クライアントでユーザーに表示される 1 つを調べることをスプーフィングを防ぐことが (上記の例では、これは、service.outlook.com、outlook.com、および accountprotection.microsoft.com) のドメインが SPF や DKIM を渡されるとします。ユーザーに表示されるドメインでは、認証されているし、スプーフィングされていないためです。詳細についてを参照してください"*なぜ電子メールの認証は常に偽装を停止するのには十分理解する"* このドキュメントで後で。 
  
ただし、問題は、電子メール認証レコードはオプションですが、必須ではありません。したがって、強力な認証ポリシーを使用してドメインのように、microsoft.com および skype.com はなりすまし、ドメインのスプーフィングされる対象は、セキュリティ強度の低い認証ポリシー、またはポリシーがないのすべての発行をから保護されます。2018 年 3 月の時点では、Fortune 500 の企業のドメインの 9% だけは、強力な電子メール認証ポリシーを公開します。残りの 91% は、フィッシャー、によってスプーフィングされる可能性があり、別のポリシーを使用してエンドユーザーに配信することがあり、それらを欺く電子メール フィルターを検出した場合を除き、します。
  
![Fortune 500 企業の DMARC のポリシー](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
いる中小企業の規模の企業の割合しない強力な電子メール認証ポリシーを発行する Fortune 500 のサイズが小さく、北米および西ヨーロッパの外部にあるドメインのまだ小さい。
  
これは、企業は、電子メール認証のしくみの認識ではない可能性があります、フィッシングは理解し、それの欠如を活用するための大きな問題です。
  
SPF、DKIM、DMARC をセットアップする方法についてを参照してください"このドキュメントで後で*Office 365 のお客様*です。 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>暗黙の e メールの認証と偽装を停止します。

フィッシング詐欺、スピアー フィッシングとは、このような問題は、強力な電子メール認証ポリシーの制限の導入のため、マイクロソフトは、お客様を保護するための機能への投資を続けます。したがって、*暗黙的な電子メールの認証*に Microsoft が先へ進むドメインが認証されない場合は、マイクロソフトは電子メール認証レコードを発行した場合と同様に扱うこととに合格しない場合にそれに応じて扱うこと。 
  
これを行うためには、Microsoft が送信者評価、送信者と受信者の履歴、行動分析、およびその他の高度なテクニックを含む通常の電子メールの認証に多数の拡張機能をビルドします。電子メールの認証を発行しないドメインから送信されたメッセージは、スプーフィングされているその他の場合信号を正当であることを示すようにマークされます。
  
これにより、ユーザーが持つことができます最後に送信される電子メールはスプーフィングされていないことを確信、送信者は誰もが自分のドメインを偽装して、Office 365 のお客様は、偽装の保護などのより優れた保護を提供できる確信することはできます。
  
マイクロソフトの一般的な告知事項については、 [A 海のフィッシング詐欺第 2 部 - Office 365 のなりすまし対策の強化が行われる](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)を参照してください。
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>スプーフィングとして、メッセージの分類を識別します。

### <a name="composite-authentication"></a>複合認証

SPF、DKIM、DMARC は、単独では役が、メッセージに明示的な認証レコードが存在しない場合に、十分な認証の状態を通信するありません。したがって、マイクロソフトでは、短い形式の複合認証、または compauth が呼び出される単一の値に複数の信号を結合するアルゴリズムを開発しました。スタンプ メッセージのヘッダーに*認証結果*のヘッダーに compauth の値は、Office 365 では、顧客であります。 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**CompAuth の結果**|**説明**|
|:-----|:-----|
|失敗します。|メッセージには、明示的な認証が失敗しました (送信ドメインのレコードに明示的に DNS に公開された) または暗黙の認証 (送信ドメインは、いない、Office 365 は、レコードを発行した場合と同様に結果を補間するため DNS では、レコードを公開しなかった)。|
|渡す|渡される明示的な認証のメッセージ (メッセージは、DMARC、または[最適な推測渡される DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)に渡される) や信頼性の高さに対する暗黙の認証 (送信ドメインは、電子メールの認証レコードを公開しませんが、Office 365 には強力なバックエンドの信号には可能性が高いメッセージを示す正当な)。|
|softpass|メッセージには、低-中程度の信頼度を持つ暗黙の認証が渡されます (ドメインでは、電子メールの認証は公開されませんが、Office 365 を正当なメッセージでは、信号の強度が弱い信号をバックエンドに送信する)。|
|なし|メッセージは認証されませんでした (または、認証でしたが、合いませんでした)、複合認証を送信者評価やその他の要素は適用されませんが、します。|
   
|||
|:-----|:-----|
|**Reason**|**説明**|
|0xx|メッセージには、複合認証が失敗しました。<br/>**000**は、メッセージが拒否、または検疫のアクションを伴う DMARC に失敗しましたを意味します。                   -001 は、メッセージには、暗黙的な電子メールの認証が失敗したを意味します。つまり、送信側のドメインで公開されると、電子メールの認証レコードがなかった場合は、セキュリティ強度の低い障害ポリシー必要がある (SPF ソフトの失敗、または中立的な DMARC のポリシーの p = なし)。<br/>**002**手段が組織に偽装された電子メールを送信するから明示的に禁止されている送信者またはドメインのペアのポリシーは、この設定は管理者が手動で設定します。  <br/>**010**は、メッセージの拒否、または検疫、アクションを伴う DMARC を失敗した送信側のドメイン、組織の承認済みドメインのいずれか (これは、自己自身、または組織内の一部をなりすましが行われる)。  <br/>**011**は、メッセージには、暗黙の電子メールの認証が失敗しました。 送信側のドメイン、組織の承認済みドメインのいずれか (これは、自己自身、または組織内の一部を、なりすましが行われる)。|
|他のすべてのコード (1 xx、2 xx、3 xx、4 xx、5 xx)|アクションが適用されたことはないがメッセージに対する暗黙の認証を渡すか、認証がありませんでした理由は、さまざまな内部コードに対応します。|
   
メッセージのヘッダーを見ると、管理者またはエンド ・ ユーザーでも確認できます送信者がスプーフィングされる可能性がありますを終了したときに Office 365 の到着します。
  
### <a name="differentiating-between-different-types-of-spoofing"></a>なりすましのさまざまな種類の違いを知る

マイクロソフトは、2 種類のメッセージがスプーフィングによって区別します。
  
 **組織内通信のなりすましが行われる**
  
呼ばれる自己自身のなりすまし、これが発生したときからドメイン: アドレスと、同じか、または合わせて、受信者のドメイン (とき、受信者のドメインは、組織の[承認済みドメイン](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)の 1 つです)。または、[差出人のドメイン: アドレスは、同じ組織の一部です。
  
たとえば、次は送信者と受信者の同じドメイン (contoso.com) のです。スペースに挿入する spambot がこのページの収集を防ぐために e メール アドレス)。
  
メールボックス ストアの送信者から。
  
メールボックス ストアの受信者にします。
  
次の送信者と受信者のドメインの組織のドメイン (fabrikam.com) との連携があります。
  
@ Foo.fabrikam.com: 送信者
  
Bar.fabrikam.com @ 受信者にします。
  
次の送信者と受信者のドメインが異なる (microsoft.com および bing.com) が、それらが同じ組織に属して (つまり、両方が組織の承認済みドメインの一部)。
  
Microsoft.com @: 送信者
  
Bing.com @ 受信者にします。
  
組織内通信の偽装に失敗したメッセージには、ヘッダーに次の値が含まれています。
  
X Forefront スパム対策レポート:.CAT:SPM HSPM/PHSH;.SFTY:9.11
  
猫、メッセージのカテゴリで、SPM (スパム) がスタンプされて通常がときどき HSPM (精度の高いスパム) またはフィッシング (フィッシング) によってどのような他のパターンの種類で発生する可能性、メッセージです。
  
SFTY は、メッセージの安全性のレベル、最初の桁の数字 (9) は、メッセージは、フィッシング詐欺、およびドット (11) は、その後の数字の 2 番目のセットは、組織内のなりすまし。
  
2018 (タイムラインが定義されていません) のスタンプがなりすましが行われると、組織内の複合の認証のための特別な理由コードはありません。
  
 **クロス ドメインのスプーフィング**
  
これが発生したときから送信側のドメイン: アドレスは、受信側の組織の外部のドメインです。クロス ドメインのスプーフィングによる複合認証に失敗したメッセージには、ヘッダーに次の値が含まれています。
  
認証の結果:... compauth 失敗の理由を = = 000 と 001
  
X Forefront スパム対策レポート:.CAT:SPOOF;.SFTY:9.22
  
どちらの場合も、次の赤の安全性のヒントは、メッセージ、または受信者のメールボックスの言語にカスタマイズされている同等の関数でスタンプが付けられます。
  
![赤の安全性のヒントは不正の検出](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
見るだけである: またはアドレスと、受信者の電子メールとは何を知ることで組織内通信のクロス ドメインのスプーフィングとを区別することができる電子メールのヘッダーを検査します。
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>方法 Office 365 のお客様が準備新しいスプーフィング対策の保護

### <a name="information-for-administrators"></a>管理者向け情報

Office 365 の組織の管理者は、いくつかの重要な情報に注意する必要がありますがあります。
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>なぜ電子メールの認証は常に偽装を停止するのには十分理解すること

新しいスプーフィング対策保護は、電子メール認証 (SPF、DKIM、DMARC) なりすましとメッセージをマークするに依存しています。一般的な例は、送信側のドメインが SPF レコードを公開しない場合です。SPF レコードが存在しない、またはそれらが正しく設定されていません、マイクロソフトではバックエンド ・ インテリジェンスは、正当なメッセージであることを示す場合を除きをスプーフィングとして送信されたメッセージがマークされます。
  
たとえば、スプーフィング対策を展開する、前にメッセージ可能性がありますきました SPF レコードがない、DKIM のレコードがない、DMARC レコードがないと次のように。 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
スプーフィング対策後、脅威保護の高度なまたは E5 製品を使用している場合、compauth 値がスタンプ (分析ツールではないと E5 で以外のお客様は影響を受けません)。
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

SPF を渡されるドメインに配置からドメインを持つために、複合認証を渡すこれは example.com では、SPF レコードが DKIM レコードではありませんを設定することによってこれを固定である場合: アドレス。 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

渡される DKIM 署名内のドメインが [差出人のドメインに配置するため複合認証を渡すこの DKIM レコードが SPF レコードではなく、設定する場合も、または、: アドレス。 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

ただし、フィッシャーも SPF と DKIM の設定し、自身のドメインでメッセージを署名がから別のドメインを指定します。 アドレスです。SPF と DKIM はどちらも、ドメインからドメインの連携をする必要があります: example.com は、DMARC のレコードを公開しない限り、これとしてマークできません DMARC を使用して、なりすましを行う可能性があるために対処します。 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

電子メール クライアント (Outlook、Outlook、またはその他の電子メール クライアント) からのみで: ドメインが表示されたら、次に、SPF や DKIM、ドメインではなく誤解する可能性、ユーザーにメッセージは、example.com に関しては、付属していたが、maliciousDomain.com から実際に付属していた.
  
![認証されたメッセージから: ドメインが SPF や DKIM を渡されたものと合っていません。](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
そのため、Office 365 が必要ですからドメイン: アドレスが SPF や DKIM 署名内のドメインに配置し、メッセージが正当なことを示すいくつかの他の内部の信号が含まれているしていない場合。それ以外の場合、メッセージは、compauth の失敗になります。 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

認証なしに、ドメインおよびドメイン認証が [差出人のドメインに対しての不一致を設定したが、Office 365 スプーフィング対策保護: 1 つのアドレスは、メッセージの送信者は、ユーザーが表示されと考えています。これは、組織内のドメインと同様に、組織の外部ドメインの両方に当てはまります。
  
したがって、複合認証が失敗し、SPF と DKIM にメッセージが渡された場合でも、偽装であるとマークするメッセージを受け取ることはありませんが SPF と DKIM を渡されるドメインが [差出人のドメインと一致していないため: アドレスです。
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>どのように偽装された電子メールでの変更を理解することが扱われます。

現時点では、Office 365 の内のすべての組織の ATP と ATP 以外の場合にメッセージをスパムし、通常、精度の高いスパム アクションまたは通常の迷惑メールの処理にかかる、DMARC の拒否、または検疫ポリシーを使用してはマークされて、その失敗 (かどうかによってその他の迷惑メール規則最初として識別スパム)。組織内通信のスプーフィング検出では、正規のスパムのアクションを実行します。この動作を有効にする必要はありませんも、それを無効にできます。
  
ただし、クロス ドメインのなりすましメッセージを変更する前に正規のスパム、フィッシング、マルウェアのチェックを通じて、フィルターの他の部分を識別して、疑わしいとしている場合はマークにスパム、フィッシング、マルウェアとそれぞれ。新しいクロス ドメインのなりすまし防止、すべてのメッセージを認証することはできませんが、既定では、操作を行います、フィッシング詐欺対策で定義されている\>ポリシーのスプーフィングを防止します。いずれかが定義されていない場合は、ユーザーの迷惑メール フォルダーに移動されます。場合によっては、さらに不審なメッセージを赤の安全性のヒントをメッセージに追加するがあります。
  
まだ取得としてマークされている迷惑メールが、今も赤の安全性のヒントはスパムとしてマークされていたいくつかのメッセージがあります。、それ以外の場合は、スパムではないが開始としてマークを取得する赤の安全性の先端を使用して迷惑メール (CAT:SPOOF) としてマークされていたメッセージが追加されます。それ以外の場合も、すべてのスパムやフィッシングを検疫に移行されたお客様は今すぐを参照してください [迷惑メール] フォルダーに移動する (この現象は、[スプーフィング対策設定を変更する](#changing-your-anti-spoofing-settings)を参照してください)。
  
(この資料の前半[のなりすましのさまざまな種類の間の Differentiating](#differentiating-between-different-types-of-spoofing)を参照してください) メッセージを偽装することが複数の異なる方法がありますが、2018年 3 月年 Office 365 は、これらのメッセージを処理する方法がないまだ統合します。次の表は、クロス ドメインのなりすまし保護が新しい動作を実行すると、簡単な概要です。 
  
|**スプーフィングの種類**|**カテゴリ**|**追加の安全性のヒントですか。**|**適用対象**|
|:-----|:-----|:-----|:-----|
|DMARC の失敗 (検疫または拒否)  <br/> |HSPM (既定値) は、SPM または PHSH 場合もあります。  <br/> |いいえ (まだ)  <br/> |すべての Office 365 のお客様、Outlook.com  <br/> |
|自己自身  <br/> |SPM  <br/> |はい  <br/> |すべての Office 365 組織では、Outlook.com  <br/> |
|クロス ・ ドメイン  <br/> |なりすまし  <br/> |はい  <br/> |脅威保護の高度な office 365 と E5 のお客様  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a>スプーフィング対策の設定を変更します。

で作成または更新 (クロス ドメイン) のスプーフィング対策の設定には、フィッシング詐欺対策に移動\>脅威の管理下で、スプーフィング対策の設定\>[セキュリティ ポリシー] タブ&amp;コンプライアンス センターです。決して、フィッシング詐欺対策の設定を作成した場合は、1 つを作成する必要があります。
  
![フィッシング対策の新しいポリシーを作成します。](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
既に作成した 1 つ場合に、それを変更することを選択できます。
  
![フィッシング対策 - 既存のポリシーを変更します。](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
作成したポリシーを選択しの説明に従って手順を進める[なりすましインテリジェンスに関する詳細です](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)。
  
![有効にするまたは antispoofing を無効にします。](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![有効にするか、antispoofing の安全性のヒントを無効にします。](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
PowerShell を使用して新しいポリシーを作成します。 
  
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

[セット AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)のマニュアルに従って、PowerShell を使用してフィッシング詐欺対策のポリシー パラメーターを変更する可能性があります。$Name をパラメーターとして指定することがあります。
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

2018 で後で既定のポリシーを作成することを実行するのではなく 1 つ作成されますそれを手動で指定する必要はありませんので、組織内のすべての受信者を対象範囲とする (以下のスクリーン ショットでは、最終的な実装の前に変更される場合)。
  
![フィッシング対策用の既定のポリシー](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
作成したポリシーとは異なりことはできません既定のポリシーを削除、優先順位を変更するかを選択するユーザー、ドメイン、またはグループのスコープを設定するに。
  
![フィッシング対策の既定ポリシーの詳細](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
以降の 2018、PowerShell を使用して、既定の保護を設定します。
  
```
$defaultAntiphishPolicy = Get-AntiphishingPolicy -IsDefault $true
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

のみを無効にしてスプーフィング対策の保護別のメール サーバーまたは Office 365 の前にサーバーがある場合 (詳細についてはアンチのなりすましを無効にする正当なシナリオを参照してください)。 
  
```
$defaultAntiphishPolicy = Get-AntiphishingPolicy -IsDefault $true
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> まず、送信者、ドメインのスプーフィングされた電子メールを送信を許可するを設定、電子メールのパスの最初のホップは、Office 365 では、スプーフィングとしてマークされている多くの正当な電子メールを取得する場合は、必要があります (を参照してください *"管理する正当な送信者 u を送信します。nauthenticated メール」* )。誤検知が多すぎますが発生する場合 (たとえば、正規スプーフィングとしてマークされたメッセージ)、スプーフィング対策の保護を完全に無効にすること勧めしません。代わりに、高度な保護ではなく、Basic を選択することをお勧めします。                   誤検出には、組織は結局のところ、長期的に非常に高いコストを課す、スプーフィングされたメールを公開するよりもを使用することをお勧めします。

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>正当な送信者は認証されていない電子メールを送信するユーザーを管理します。

Office 365 は、認証されていないメールの送信元組織の追跡します。サービスでは、送信者が正当ではないと考えて、 *compauth*の失敗としてマークには。メッセージに適用された、スプーフィング対策ポリシーに依存しますがスプーフィングとして分類されます。 
  
ただし、管理者は、どの送信者は、スプーフィングされたメールを送信するのには Office 365 の意思決定をオーバーライドすることを指定できます。
  
**方法 1 の組織は、ドメインを所有している場合は、電子メールの認証を設定**
  
組織内通信のスプーフィング、および、複数のテナントを所有または相互作用の位置の場合なりすましのクロス ・ ドメインを解決するのにはこのメソッドを使用することができます。クロス ドメインのスプーフィング、Office 365 内での他の顧客に送信して他のプロバイダーでホストされているサード パーティを解決することができます。
  
詳細については、[お客様の Office 365](#customers-of-office-365)を参照してください。 
 
**方法 2 - 認証されていないメールの送信者を許可を構成するのにはインテリジェンスを使用してなりすましを行う可能性**
  
組織に認証されていないメッセージを送信するのに送信者を許可するように[なりすましのインテリジェンス](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)を使用することもできます。 
  
外部ドメインは、偽装されたユーザーが差出人のアドレスのドメイン送信側のインフラストラクチャは、送信元の IP アドレス (/24 に分割されている CIDR 範囲)、または PTR レコードの組織のドメイン (次のスクリーン ショットの送信元 ip アドレスがありますPTR レコードは、outbound.mail.protection.outlook.com、131.107.18.4、outlook.com の送信側のインフラストラクチャとして示されます)。
  
認証されていない電子メールを送信するには、この送信者を許可するには、 **[はい]** に**No**を変更します。
  
![許可された送信者の antispoofing を設定します。](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
特定の送信者、ドメインのスプーフィングを許可するのに PowerShell を使用することもできます。 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Powershell を使用して偽装された送信者を取得します。](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
前のイメージでは、このスクリーン ショットを作成するのには次のように合わせて、ですが、実際にはすべての値が 1 行に表示するに、追加の改行が追加されています。
  
ファイルを編集し、outlook.com と bing.com に対応する行を探して、いいえ] から [はい] に AllowedToSpoof のエントリを変更します。
  
![Powershell を使用して [はい] に設定のスプーフィングを許可します。](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
ファイルを保存し、実行します。 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

Bing.com から認証されていない電子メールを送信するようになりましたことが\*. outlook.com。

**方法 3: 送信者/受信者の組み合わせを許可するエントリを作成します。**
  
すべてのスパムが特定の送信者のフィルターをバイパスすることもできます。詳細については、 [Office 365 の許可リストに送信者を安全に追加する方法](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)を参照してください。
  
このメソッドを使用する場合はスキップ迷惑メールおよびフィッシング フィルターの一部が、マルウェアのフィルター処理します。
  
**方法 4 - 送信者に連絡し、電子メールの認証を設定するように依頼**
  
、スパムやフィッシングの問題が発生したためは、マイクロソフトは、すべての送信者の電子メールの認証の設定を推奨します。送信側ドメインの管理者がわかっている場合は、上書きを追加する必要があるないために、電子メール認証レコードを設定されている要求し、それらにお問い合わせください。詳細についてを参照してください[Office 365 のお客様ではありませんが、ドメインの管理者](#administrators-of-domains-that-are-not-office-365-customers)"後で参照してください。 
  
送信ファイルの取得を認証するドメインに最初に困難な場合がありますが、時間の経過と共により多く電子メール フィルター junking か、自分の電子メールを拒否してより良い配信を確実に適切なレコードを設定するには発生します。
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>メッセージの数がスプーフィングされているとマークされたレポートを表示します。

スプーフィング対策ポリシーを有効にすると、番号がメッセージの数は、フィッシングとマークされたことを回避するのに脅威のインテリジェンスを使用できます。セキュリティに移動するのには、&amp;脅威の管理下にあるコンプライアンス センター (SCC)\>エクスプ ローラーでは、フィッシング、およびグループを送信者のドメインまたは保護の状態でビューを設定します。
  
![フィッシングとしてマークは、メッセージの数を表示します。](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
数としてマークされているフィッシング、スプーフィングとしてマークされているメッセージなどを表示するさまざまなレポートと対話できます。詳細については、 [Office 365 の脅威インテリジェンス入門](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441)を参照してください。
  
まだ、どのメッセージがスプーフィングとフィッシング (一般的なフィッシング詐欺や、ドメインまたはユーザーの偽装) の他の型によってマークされたを分割することはできません。ただし、2018、後ですることがセキュリティであるのか&amp;コンプライアンス センターです。行うと、正規の認証が失敗したため、スプーフィングとしてマークされている可能性のある送信元のドメインを特定するのに出発点としてこのレポートを使用できます。
  
次のスクリーン ショットは、このデータの外観がリリースされたときに変わる可能性がある提案です。
  
![検出タイプでのフィッシング レポートを表示します。](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
分析ツールではないと E5 のお客様は、これらのレポート 2018 脅威保護の状態 (TP) レポートには、[後で使用できるが、少なくとも 24 時間に遅れます。セキュリティに統合されているようにこのページを更新する&amp;コンプライアンス センターです。
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>メッセージの数は、スプーフィングとしてマークされますを予測します。

2018、後で Office 365 で使用すると、スプーフィング対策の実施を無効に設定を更新する 1 回または上で基本認証または高の強制が与えられますさまざまな設定でメッセージを変更する方法を表示する機能です。スプーフィング対策が無効の場合は、することが Basic; をオンにする場合は、スプーフィングとして検出されるメッセージの数を参照してください。または、Basic の場合は、することが高を有効にする場合は、スプーフィングとして検出されますどのように多くのメッセージを参照してください。
  
この機能は、現在開発中です。詳細については定義されている、セキュリティとコンプライアンス ・ センターのスクリーン ショットと PowerShell の例の両方にこのページが更新されます。
  
![Antispoofing を有効にするための「What-if」レポート](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![偽装された送信者を許可する可能性のあるユーザー エクスペリエンス](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a>についてどのように迷惑メール、フィッシング詐欺、および高度なフィッシング詐欺の検出を組み合わせる

Exchange のオンライン ・ カスタマー ・分析ツールと分析ツールではないのは、サービスは、マルウェア、スパム、精度の高いスパム、フィッシング、および一括としてメッセージを識別するときに実行されるアクションを指定できます。ただし、ATP のお客様向けの新しいフィッシング詐欺対策ポリシーとメッセージが複数の検出の種類 (マルウェア、フィッシング、およびユーザーの偽装など) をヒット可能性がありますという事実の導入により、可能性があります混乱を招くとすると、ポリシーが適用されます。 
  
一般に、メッセージに適用されるポリシーは、CAT (カテゴリ) のプロパティに X Forefront スパム対策レポート ヘッダーで識別されます。 
  
|**Priority**|**ポリシー**|**カテゴリ**|**場所、管理しますか。**|**適用対象**|
|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |マルウェア  <br/> |MALW  <br/> |[マルウェアのポリシー](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |すべてのお客様  <br/> |
|2  <br/> |フィッシング  <br/> |PHSH  <br/> |[ホストされるコンテンツ フィルター ポリシー](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |すべてのお客様  <br/> |
|3  <br/> |信頼度の高いスパム  <br/> |HSPM  <br/> |[ホストされるコンテンツ フィルター ポリシー](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |すべてのお客様  <br/> |
|4  <br/> |なりすまし  <br/> |なりすまし  <br/> |[フィッシング詐欺対策ポリシー](https://go.microsoft.com/fwlink/?linkid=864553)[なりすましのインテリジェンス](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) <br/> |ATP のみ  <br/> |
|5  <br/> |スパム  <br/> |SPM  <br/> |[ホストされるコンテンツ フィルター ポリシー](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |すべてのお客様  <br/> |
|6  <br/> |一括  <br/> |一括  <br/> |[ホストされるコンテンツ フィルター ポリシー](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |すべてのお客様  <br/> |
|7   <br/> |ドメインの偽装  <br/> |DIMP  <br/> |[フィッシング詐欺対策ポリシー](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |ATP のみ  <br/> |
|8  <br/> |ユーザーの偽装  <br/> |UIMP  <br/> |[フィッシング詐欺対策ポリシー](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |ATP のみ  <br/> |
   
別のフィッシング詐欺対策ポリシーが複数ある場合は、最高の優先順位で適用されます。たとえば、2 つのポリシーがあるとします。
  
|**ポリシー**|**Priority**|**ユーザー/ドメインの偽装**|**スプーフィング対策**|
|:-----|:-----|:-----|:-----|
|A  <br/> |1  <br/> |On  <br/> |Off  <br/> |
|B  <br/> |2  <br/> |Off  <br/> |オン  <br/> |
   
メッセージは、スプーフィングおよびユーザーの偽装とは、識別しユーザーの同じセットのスコープは、ポリシー A と B のポリシー、し、メッセージは、スプーフィングとして扱われますと以降のアクションは適用されませんスプーフィング対策がになっています。、なりすましは、ユーザーの偽装 (8) よりも高い優先順位 (4) で実行されるとします。
  
フィッシング詐欺の他の種類を作成するには、ポリシーの適用に適用するさまざまなポリシーの設定を調整する必要があります。
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>スプーフィング対策を無効にする正当なシナリオ

スプーフィング対策、フィッシング攻撃からお客様を保護してより、したがってスプーフィング対策の保護を無効にすること強くお勧めします。それを無効にすることは、長期的にリスクの詳細に公開するのですが、いくつか短期的な誤認識を解決する可能性があります。送信者側では、認証を設定するかで、フィッシング詐欺のポリシーを調整することのコストは通常 1 回限りのイベントであるか、最小限、定期的なメンテナンスを必要とします。ただし、データが公開されている、フィッシング攻撃から回復するためのコスト、または資産がされているが非常に高い危険にさらさです。
  
このため、スプーフィング対策誤検出にアンチ スプーフ保護を無効にするよりもを使用することをお勧めします。
  
ただし、正当なシナリオ、スプーフィング対策は無効にする必要があります、およびその他のメール ・ フィルタ リングがある場合に、メッセージのルーティング、および Office 365 の製品は、電子メールのパスの最初のホップではありません。
  
![顧客の MX レコードが Office 365 をポイントしていません。](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
Exchange のオンプレミスのメール サーバー、Ironport などのデバイスをフィルタ リングするメールを他のサーバーがありますか、他のクラウド サービスをホストします。
  
場合は受信者のドメインの MX レコードが Office 365 に、Office 365 は、受信側ドメインの MX レコードを検索し、別のサービスを指す場合は、スプーフィング対策を抑制するため、スプーフィング対策を無効にする必要がありません。かどうか、ドメインには、別のサーバー前面にない場合は、MX レコードを検索するのには、MX のツールボックスのような web サイトを使用できます。次のようなと言えます。
  
![MX レコードは、ドメインを Office 365 をポイントしていないことを示します](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
このドメインは、Office 365 はスプーフィング対策の実施を適用していないため、Office 365 を指していない MX レコードを持っています。
  
ただし場合*は、* 受信者のドメインの MX レコードは、Office 365 の前に別のサービスが存在する場合でも、Office 365 をポイント、しする必要がありますを無効にスプーフィング対策。最も一般的な例は、アドレス書き換えを使用することです。 
  
![書き換えの受信者のルーティングの図](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
ドメイン contoso.com の MX レコードが指す、オンプレミスのサーバーが含まれているために、ドメイン @office365.contoso .net の MX レコードが Office 365 を指すときに\*です。 protection.outlook.com、または\*。 MX レコードに eo.outlook.com。
  
![Office 365 に MX レコードのポイント、したがって可能性があります受信者を書き換える](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
受信者のドメインの MX レコードが、Office 365 をポイントしていないとき、および受信者の書き換えを行ったことを区別することを確認します。これら 2 つのケースを区別する必要があります。
  
受信側のドメインが受信者の書き換えを行われているかどうかがわからない場合があることがわかりますメッセージ ヘッダーを調べることによって。
  
) 最初に、認証結果のヘッダー内の受信者のドメインへのメッセージのヘッダーになります。 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

受信者のドメインが、赤い太字テキストで、このケースの office365.contoso.net であります。これは異なる場合があることで指定した受信者: ヘッダー。
  
に: 例受信者\<受信者のメールボックス ストア\>
  
実際の受信者のドメイン、MX レコードのルックアップを実行します。含まれている場合は\*です。 protection.outlook.com、mail.messaging.microsoft.com、\*です。 eo.outlook.com、または mail.global.frontbridge.com、MX は、Office 365 を指していることを意味します。
  
これらの値を含まない場合、MX は、Office 365 には指していないことを示します。これを確認することができますを使用するツールの 1 つは、MX のツールボックスです。
  
この例では、次の質問を contoso.com ドメインにされてから、受信者のような: ヘッダーには、prem のサーバーに MX レコードのポイント。
  
![Prem のサーバーを指す MX レコード](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
ただし、実際の受信者は、MX レコードは、Office 365 をポイントして、office365.contoso.net です。
  
![受信者の書き換えをする必要があります、Office 365 を指す MX](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
したがって、このメッセージには、受信者の書き換えがおそらく行われています。
  
b) 次に、受信者の書き換えの一般的な用途を区別することを確認します。受信者のドメインを書き換えるしようとしているかどうかは\*です。 onmicrosoft.com、代わりにするように書き直します\*です。 mail.onmicrosoft.com です。
  
別のサーバーの背後にあるルートは、最終的な受信者のドメインを特定し、受信者のドメインの MX レコードは、実際に (と、その DNS レコードの発行) に、Office 365 を指す、スプーフィング対策を無効にするのに進みます。
  
1 つまたは複数のサービスの背後にある場合にのみ、ドメインの最初のホップ ルーティング パスでは、Office 365 の場合、スプーフィング対策を無効にしたくないことを忘れないでください。
  
### <a name="how-to-disable-anti-spoofing"></a>スプーフィング対策を無効にする方法

既にした場合、フィッシング詐欺対策ポリシーの作成、EnableAntispoofEnforcement パラメーターを $false に設定します。 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

無効にするポリシー (またはポリシー) の名前がわからない場合は、それらを表示できます。 
  
```
Get-AntiphishPolicy | fl Name
```

何らかのフィッシング詐欺対策ポリシーをお持ちでない場合は、作成し、無効にすること (場合でも、ポリシーがない、スプーフィング対策がまだ適用されている 2018年の後で、既定のポリシーが作成されますし、無効にすることを 1 つを作成する代わりに).これは複数のステップで実行する必要があります。 
  
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

スプーフィング対策を無効にすると、コマンドレットを使用して利用可能なのみ (第 2 四半期 2018年のことが、セキュリティで利用可能な&amp;コンプライアンス センター)。PowerShell へのアクセスがない場合は、サポート チケットを作成します。
  
Office 365 に送信された場合に間接的なルーティングが行われるようドメインにのみ適用されるこのことを忘れないでください。スプーフィング対策をいくつかの誤認識が発生したため無効にするは我慢より長期的に行うことができます。
  
### <a name="information-for-individual-users"></a>個々 のユーザーの情報

個々 のユーザーは、スプーフィング対策の安全性のヒントとやり取りする方法に制限されます。ただし、これには一般的なシナリオを解決するのにはいくつかの方法があります。
  
### <a name="common-scenario-1---mailbox-forwarding"></a>共通シナリオ 1: メールボックスの転送

場合は別の電子メール サービスを使用して Office 365 または Outlook.com に電子メールを転送して、電子メールはスプーフィングとしてマークすることもし、赤の安全性のヒントが表示されます。Office 365 と Outlook.com は、フォワーダーは、Outlook.com、Office 365、Gmail、または[円弧のプロトコル](https://arc-spec.org)を使用するその他のサービスのいずれかのときに自動的にアドレスを計画します。ただし、その修正プログラムを展開するまでユーザーが接続されているアカウントの機能を転送] オプションを使用するのではなく、直接のメッセージをインポートするのに使用する必要があります。
  
Office 365 に接続されているアカウントを設定するに、Office 365 の web インターフェイスの右上隅に歯車のアイコンを選択します\>メール\>メール\>アカウント\>アカウントに接続します。
  
![Office 365 に接続されているアカウントのオプション](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
Outlook.com では、プロセスは、歯車のアイコンを\>オプション\>メール\>アカウント\>接続されているアカウントです。
  
### <a name="common-scenario-2---discussion-lists"></a>共通シナリオ 2 の説明を一覧表示します。

ディスカッションのリストは既知のスプーフィング対策方法により、転送の問題があるメッセージとその内容を変更からオリジナルを保持する: アドレスです。
  
たとえば、あなたの電子メール アドレスは、ユーザーのメールボックス ストア、し、バードウォッチングに興味のあるディスカッションのリスト birdwatchers @ example.com に参加します。ディスカッションのリストにメッセージを送信するときは、このように送信可能性があります。
  
**から:** John Doe\<ユーザーのメールボックス ストア\> 
  
**に:** ディスカッション リストの birdwatcher の\<@ example.com birdwatchers\> 
  
**件名:** 今週レイニアの上部にあるカシドリの優れた表示 
  
表示を確認すると誰でも今週レイニアからでしょうか。
  
電子メール] ボックスの一覧では、メッセージを受信したとき、メッセージの書式を設定、その内容を変更、参加者の多くの別の電子メールの受信機から構成されるディスカッションのリストのメンバーの残りの部分を再生します。
  
**から:** John Doe\<ユーザーのメールボックス ストア\> 
  
**に:** ディスカッション リストの birdwatcher の\<@ example.com birdwatchers\> 
  
**件名:**[BIRDWATCHERS]今週レイニアの上部にあるカシドリの優れた表示 
  
表示を確認すると誰でも今週レイニアからでしょうか。
  
---
  
Birdwatchers ディスカッションのリストにこのメッセージが送信されました。いつでも購読を解除することができます。
  
上で再生されたメッセージには同じ: アドレス (ユーザーのメールボックス ストア) は、元のメッセージが、件名とメッセージの下部にフッターにタグを追加することによって変更されています。この種類のメッセージの変更は、メーリング リストでは、一般的な誤検出が発生する可能性があります。
  
または他の組織では、メーリング リストの管理者には、スプーフィング対策のチェックに合格するように構成できる場合があります。
  
- DMARC.org の FAQ を確認:[何をすれば、メーリング リストを操作して、DMARC と相互運用したいですか?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)
    
- 」の手順には、このブログの投稿を読む:[エラーを避けるために DMARC と相互運用するメーリング リストの演算子のヒント](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)
    
- 円弧のサポートを参照して、メーリング リストのサーバーに更新プログラムのインストールを検討してください。[https://arc-spec.org](https://arc-spec.org/)
    
場合はメーリング リストの所有権を使用する必要はありません。
  
- (また必要があります電子メールの認証ドメインからの中継は、メーリング リストの設定) の上のオプションのいずれかを実装するのにはメーリング リストの管理者を要求することができます。
    
- メッセージを受信トレイに移動するように電子メール クライアントで、メールボックスのルールを作成できます。設定するのには、組織の管理者に許可する規則、または管理する正当な送信者は認証されていないメールを送信することでオーバーライドとして説明を要求することもできます。
    
- 正当なものとして扱うメーリング リストの上書きを作成するのには Office 365 のサポート チケットを作成することができます。
    
### <a name="other-scenarios"></a>その他のシナリオ

1. 上の一般的なシナリオのどちらもは、自分の状況に適用する場合、false 正バックアップとしてメッセージをマイクロソフトに報告します。詳細についてを参照してください[方法ことができますか迷惑メールまたはスパムでないメッセージをマイクロソフトに報告しますか?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)この資料で後述します。 
    
2. マイクロソフトとサポート チケットとそれを発生させることができます、電子メール管理者にお問い合わせくださいする可能性がありますも。マイクロソフトのエンジニア リング チームは、スプーフィングとしてメッセージが表示された理由を調査します。
    
3. さらに、送信者をすることはない悪意のある偽装されたと確信できる場合は、認証しないメール サーバーからメッセージが送信されていることを示す送信者に返信することがあります。場合があります、その結果、元の送信者が必要な電子メール認証レコードが設定されますが、IT 管理者に連絡します。
  
十分な送信者は、電子メール認証レコードを設定する必要があるドメインの所有者に返信、するとことを受け、そのアクションを取るように。マイクロソフトは、必要なレコードを発行するドメインの所有者でも動作することが、中には、さらに個々 のユーザーは、要求にことができます。
    
4. 必要に応じて、[差出人セーフ リストに送信者を追加します。ただし、こと場合は、フィッシャーは、そのアカウントをスプーフィング、それはメールボックスに配信される、対応します。したがって、多用しないようにこのオプションを使用する必要があります。
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>スプーフィング対策の保護のために送信者をどのように準備する必要があります。

管理者は、現在のメッセージを Microsoft に送信する場合は Office 365 または Outlook.com のいずれかを確認してください、メールが正しく認証されている迷惑メールまたはフィッシングとそうしないとマークすることもできます。 
  
### <a name="customers-of-office-365"></a>Office 365 のお客様

Office 365 をご送信の電子メールを送信するのには Office 365 を使用する場合。
  
- [スプーフィングを防止するために Office 365 の SPF を設定](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)ドメインの
    
- [カスタム ドメインを Office 365 から送信された送信の電子メールを検証するために DKIM を使用して](https://technet.microsoft.com/en-us/library/mt695945%28v=exchg.150%29.aspx)、プライマリ ドメインの
    
- 正当な送信者は、ユーザーを決定するのに、ドメインの[DMARC レコードの設定](https://technet.microsoft.com/en-us/library/mt734386%28v=exchg.150%29.aspx)を 
    
マイクロソフトでは、SPF、DKIM、DMARC のそれぞれの実装の詳細なガイドラインを提供していません。ただし、多くの情報をオンラインで公開があります。サード パーティの企業電子メール認証レコードを設定する組織を支援します。
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>Office 365 のお客様ではないドメインの管理者

ドメイン管理者は、Office 365 の顧客ではない場合。
  
- 必要があります、ドメインの送信元の IP アドレスを発行するのには、SPF を設定しを設定する DKIM (ある場合) メッセージにデジタル署名します。DMARC レコードの設定を考慮することがあります。
    
- 一括送信者に代わってメールを送信した場合は、必要がありますを使用する方法で電子メールを送信するようするようから送信側のドメイン: SPF または DMARC を通過するドメインとアドレス (該当する場合に属する) に揃えて配置します。
    
- オンプレミス メール サーバー、または、サービスとしてのソフトウェアのプロバイダー、または、Microsoft Azure、GoDaddy、ラック、Amazon Web サービスのようなクラウド ・ ホスティング サービスから送信またはと同様に、するようにする場合は、SPF レコードに追加されます。
    
- ISP によってホストされている小規模なドメインの場合は、ISP が提供するの SPF レコードの説明書に従って設定してください。ほとんどの Isp では、命令のこれらの種類を提供し、会社のサポート ページにあります。
    
- 場合でもする前に、電子メールの認証レコードを発行する必要がないと正常に動作しました、まだ Microsoft に送信する電子メールの認証レコードを発行する必要があります。そうするには、フィッシング詐欺との闘いにおいて支援している phished、または送信する組織のいずれかを取得する可能性を軽減します。
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>場合、ドメインと電子メールを送信したがわからないでしょうか。

多くのドメインは、そのすべての送信者は、ユーザーを把握していないため SPF レコードを発行できません。では、ユーザーを認識する必要はありませんがそれらのすべてです。代わりに、必要があります開始するものの特に、企業内のトラフィックのある場所を知っているし、中立的な SPF ポリシーを発行するは、SPF レコードを発行することによってですか? すべて。
  
example.com の TXT」v = spf1 include:spf.example.com? すべて"
  
ニュートラルの SPF ポリシーでは、渡すことが、企業のインフラストラクチャが付属しているすべての電子メールは電子メールの認証に他の電子メールの受信機を意味します。把握できていない送信者から送信される電子メールは、中立的なない SPF レコードを公開しないとほぼ同じであるに再び確立されます。
  
認証されるように、企業内のトラフィックから送信される電子メールをマークする、Office 365 に送信するときは (かどうか Office 365 に暗黙的に認証できることによる) のスプーフィングとして把握できていないソースから送信される電子メールをマークすることもまだです。しかし、これは Office 365 で、スプーフィングとしてマークされているすべての電子メールから改善します。
  
フォールバック ポリシーを使用して SPF レコードを開始取得するとしますか? より多くの送信元のインフラストラクチャは、徐々 にできより厳しいポリシーを公開し、すべて。 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>メーリング リストの所有者である場合ですか。

参照してください[2: ディスカッションの一般的なシナリオの一覧が表示](#common-scenario-2---discussion-lists)されます。 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>場合、インフラストラクチャ ・ プロバイダー、インターネット サービス プロバイダー (ISP)、電子メール サービス プロバイダー (ESP)、クラウドのサービスをホストしているなどとしています。

ドメインの電子メールをホストすると、電子メールを送信または電子メールを送信するホストのインフラストラクチャを提供して、次の操作を行う必要があります。
  
- SPF レコードで発行する詳細なドキュメントを顧客であることを確認します。
    
- 場合でも、お客様は明示的に設定 (既定のドメインを使用して署名) は、送信メールに DKIM 署名を署名を検討してください。偶数倍記号 (+) (1 回とするが、その設定の場合は、お客様のドメインと会社の DKIM 署名を 2 回) DKIM 署名付きの電子メールを作成することができます。
    
お使いのプラットフォームから発信されたメールを認証するが、ことマイクロソフトは迷惑メール、電子メール、認証されていないために、少なくとも場合でも、Microsoft に提は保証されません。Outlook.com で電子メールをフィルターする方法を詳細については、 [Outlook.com のポスト マスターのページ](https://postmaster.live.com/pm/postmaster.aspx)を参照してください。
  
サービス プロバイダーのベスト ・ プラクティスの詳細については、 [M3AAWG モバイル メッセージングのベスト プラクティスのサービス プロバイダー](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)を参照してください。
  
## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="why-is-microsoft-making-this-change"></a>なぜ Microsoft では、この変更しますか。

フィッシング詐欺の影響は、次の攻撃、および Microsoft と考えていますので、電子メール認証 15 年以上にわたって利用されてきたの危険性を引き続き認証されていないメールを許可することは、正当な電子メールが失われるリスクよりも高い。
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>この変更、正当な電子メールをスパムとしてマークしますか。

最初に、スパムとしてマークされているいくつかのメッセージがあります。ただし、時間の経過と共にには、送信者が調整され、スプーフィングされていると間違ったメッセージの量はほとんどの電子メールのパスを取るに足らないものも。
  
マイクロソフト自体最初に採用してこの機能、お客様の残りの部分を展開する前にいくつかの週。最初の中断が発生しました、中に徐々 に低下しています。
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>マイクロソフトは、Office 365 の Outlook.com と非-高度な脅威保護のお客様にこの機能を表示します。

スプーフィング対策の保護では、最初に展開するか、ATP と E5 の顧客とその他のユーザーに、将来的に解放する可能性があります。ただし場合は、レポート作成などに適用されていないいくつかの機能がある可能性があり、ユーザー設定よりも優先します。
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>方法ことができますか迷惑メールまたはスパムでないメッセージをマイクロソフトに報告しますか。

[レポート メッセージに Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を使用することがないかどうか、またはがインストールされている、[送信スパム、スパム以外の場合、および分析のためのマイクロソフトのフィッシング詐欺メッセージ](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)。
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>私はドメイン管理者のすべての送信者は相手を知りません。

[Office 365 のお客様ではありませんが、ドメインの管理者](#administrators-of-domains-that-are-not-office-365-customers)を参照してください。
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>どう自分の組織では、スプーフィング対策の保護を無効にする場合でも、Office 365 は、プライマリ フィルターでしょうか。

行うことこれよりミストのフィッシング詐欺、スパム メッセージを公開するためです。すべてのフィッシング詐欺は、スプーフィングとすべてのスプーフィングが失われます。ただし、リスクはスプーフィング対策を有効にするユーザーよりも大きくなります。
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>スプーフィング対策保護を有効にするわけではすべてのフィッシング詐欺から保護されますか。

残念ながら、いいえなど、その他の手法を使用するのには、フィッシングが適用されますので危険にさらされたアカウント、または無料のサービスのアカウントを設定します。ただし、フィッシング防止対策に優れてこれらに、レイヤーは、Office 365 の保護作業を共同設計するためのフィッシング詐欺の方法は、他の種類を検出し、互いの上に構築します。
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>他の大規模な電子メールの受信機は、認証されていない電子メールをブロックしますか。

ほぼすべての大規模な電子メールの受信機は、従来の SPF、DKIM と DMARC を実装します。いくつかの受信機には、他のチェックには、これらの標準が、一部の移動をブロックするのには Office 365 に認証されていない限りより厳密なメールし、スプーフィングとして扱うことがあります。ただし、業界のほとんどが高まっての電子メールは、この特定の種類についてより厳密な特にフィッシングの問題が発生したためです。
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>必要はありますか、迷惑メールのフィルタ リングの高度なオプションを有効に「SPF ハード失敗」スプーフィング対策を有効にする場合ですか。

残念ですが、SPF ハードが失敗した場合より幅広い条件にだけでなく、スプーフィング対策の機能と見なされるためこのオプションは必要ありません。スプーフィング対策が有効になってがあり、SPF ハード失敗する] オプションが有効になって表示される可能性を誤認識します。スパムやフィッシング、追加の catch は、ほとんどありませんし、代わりにほとんど偽陽性を生成しますが、この機能を無効にすることをお勧めします。
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>送信者書き換えスキーム (SRS) の修正に役立つ電子メールを転送しますか。

SRS は、部分的に転送された電子メールの問題を修正します。SMTP メールからの書き換え、SRS によりを次の宛先に転送されたメッセージ パス SPF です。ただし、スプーフィング対策からに基づいているため: アドレス、メールからまたは DKIM 署名ドメイン (またはその他の信号) との組み合わせではスプーフィングされているとマークされてから転送される電子メールを防ぐために十分な。
  

