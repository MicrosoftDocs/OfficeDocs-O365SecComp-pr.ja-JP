---
title: Office 365 がフィッシング詐欺を防ぐために送信者のアドレスを検証する方法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
description: 'フィッシング詐欺を防ぐためには、Office 365 と Outlook.com が必要になりました RFC に準拠するための: アドレスです。'
ms.openlocfilehash: 8425d4ef7635c2beddcd7915daf73736432d4ca9
ms.sourcegitcommit: d89c24258123a3ffde574a391d59afd3aea8470d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2018
ms.locfileid: "23955429"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Office 365 がフィッシング詐欺を防ぐために送信者のアドレスを検証する方法

Office 365 と Outlook.com の電子メール アカウントは、ますます多くのフィッシング攻撃を受け取ります。元の値を持つメッセージを送信するのには、フィッシングを使用して 1 つの方法: アドレスは[RFC 5322](https://tools.ietf.org/html/rfc5322)に準拠していません。From: アドレスとも呼ばれます 5322.From のアドレスです。このタイプのフィッシング詐欺を防ぐため、Office 365 と Outlook.com を必要と、RFC 準拠を含めるには、サービスで受信したメッセージから: この資料で説明したように対処します。
  
> [!NOTE]
> この資料の情報では、一般的な電子メール アドレスの形式の基本を理解する必要があります。詳細については、 [RFC 3696](https://tools.ietf.org/html/rfc3696)だけでなく、 [RFC 5322](https://tools.ietf.org/html/rfc5322) (特にセクション 3.2.3、3.4、3.4.1)、 [RFC 5321](https://tools.ietf.org/html/rfc5321)を参照してください。この資料では、5322.From のアドレスをポリシーの適用についてです。この資料の 5321.MailFrom のアドレスではありません。 
  
残念ながら、いるデータがインターネット上のいくつか「正当な」電子メールを持たない、メッセージを送信し続けている従来のメール サーバーから不正な形式または: アドレスです。これらのレガシー ・ システムを使用している組織から定期的に電子メールを受信する場合は、これらの組織は最新のセキュリティ標準に準拠するメール サーバーを更新するをお勧めします。
  
マイクロソフトは、2017 年 11 月 9日に、この資料に記載のポリシーの強制をロールアウトを開始します。
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Office 365 での有効な使用を強制する方法: フィッシング攻撃を防ぐためにアドレス

使用を強制する方法を変更している office 365: 向上するために受信メッセージのアドレスがフィッシング攻撃から保護します。この資料では。
  
- [有効なすべてのメッセージがあります: アドレス](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [元の書式設定: 表示名が含まれていない場合の対処](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [元の書式設定: 表示名が含まれている場合の対処](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [有効/無効からの他の例: アドレス](how-office-365-validates-the-from-address.md#Examples)
    
- [From を壊すことがなく、カスタムのドメインへの自動応答を抑制する: ポリシー](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [Office 365 からオーバーライド: 強制ポリシーに対応](how-office-365-validates-the-from-address.md#Override)
    
- [防止し、Office 365 のサイバー犯罪を防ぐには、他の方法](how-office-365-validates-the-from-address.md#OtherProtection)
    
Terry Zink のブログを読む他のユーザーの代理として送信することは、詳細については、この変更によっては影響を受けません」[のこと、電子メールの [送信者] を参照するときですか?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)"です。
  
### <a name="all-messages-must-include-a-valid-from-address"></a>有効なすべてのメッセージがあります: アドレス
<a name="MustIncludeFromAddress"> </a>

いくつかの自動化されたメッセージは含まないと: 送信時に対応します。以前は、Office 365 または Outlook.com、差出人にメッセージを受信しました: アドレス、サービスの追加から次の既定値: 成果物を作成するためにメッセージのアドレス。
  
```
From: <>
```

2017 年 11 月 9日の開始 Office 365 は、ロールアウトの変更新しいルールが適用されますが、データ センター、メール サーバーに位置せず、元のメッセージ: アドレスは、Office 365 または Outlook.com では受け付けられなく。代わりに、Office 365 によって受信されたメッセージをすべて含まれていなければなりませんから、有効な: アドレスです。それ以外の場合、メッセージは、Outlook.com と Office 365 で、削除済みアイテムまたは迷惑メール フォルダーに送信されます。 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>構文の概要: 元の形式が無効です: Office 365 のアドレス
<a name="SyntaxOverviewFromAddress"> </a>

値の形式: アドレスは、いくつかの Rfc の間で詳細に定義されています。多くのバリエーションに対応し、有効または無効なものと考えることがあります。シンプル、マイクロソフトは、次の形式と定義を使用することをお勧めします。
  
```
From: "displayname " <emailaddress >
```

詳細は次のとおりです。
  
- (省略可能) *表示名*は、電子メール アドレスの所有者を記述する語句です。たとえば、送信者のメールボックスの名前よりもわかりやすい名前があります。表示名を使用すると、省略可能です。ただし、表示名を使用する場合は、お勧めことを常に、引用符で囲むようにします。 
    
- (必須) *emailaddress*が構成されています。 
    
  ```
  local-part @domain
  ```

    詳細は次のとおりです。
    
  - (必須) *ローカル部分*は、アドレスに関連付けられているメールボックスを識別する文字列です。これは、ドメイン内で一意です。多くの場合、メールボックスの所有者のユーザー名または GUID が、ローカル部分の値として使用されます。 
    
  - (必須) *ドメイン*は、電子メール アドレスのローカル部分で識別されるメールボックスをホストしているメール サーバーの完全修飾ドメイン名 (FQDN)。 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>元の書式設定: 表示名が含まれていない場合の対処
<a name="FormatNoDisplayName"> </a>

A が正しく書式設定: 表示名が含まれていないアドレスには、山括弧の有無には 1 つの電子メール アドレスのみが含まれています。スペースを山かっこを分離しないことをお勧めします。さらに、ないものを含んでいる電子メール アドレスの後。
  
次の例では有効です。
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

次の使用例は有効では、山括弧と電子メール アドレスの間にスペースが含まれていますのでお勧めしません。
  
```
From: < sender@contoso.com >
```

次の使用例が正しくない電子メール アドレスの後ろのテキストが含まれているため。
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>元の書式設定: 表示名が含まれている場合の対処
<a name="FormatDisplayName"> </a>

: 表示名の値が含まれているアドレスの場合は、次の規則を適用します。
  
- 送信者のアドレスが表示名を含む表示名にコンマが含まれる場合は、表示名は引用符で囲む必要があります。例えば：
    
    次の例では有効です。
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    次の使用例が正しくありません。
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    いない表示名を表示名にコンマが含まれている場合の引用符で囲むは、RFC 5322 無効な場合します。
    
    ベスト プラクティスとしてに関係なく表示名の前後に引用符またはが存在しないかどうかは、表示名にコンマです。
    
- 送信者のアドレスには、表示名が含まれている場合は、山かっこ内で電子メール アドレスを囲む必要があります。
    
    最善の方法として、表示名と電子メール アドレスの間にスペースを挿入することを Microsoft は強く推奨します。
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>有効/無効からの他の例: アドレス
<a name="Examples"> </a>

- 無効です。
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- 無効です。電子メール アドレスは山かっこで囲まれていません。
    
  ```
  From: Office 365 sender@contoso.com
  ```

- 有効ですがないことをお勧めします。表示名は引用符ではありません。ベスト プラクティスとして、常に表示名を囲む引用符を配置します。
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- 無効です。引用符で囲まれた表示名だけでなくすべて囲まれています。
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- 無効です。電子メール アドレスを山かっこはありません。
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- 無効です。表示名と左かっこの間にスペースはありません。
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- 無効です。表示名を右 quotation mark、左の山かっこの間の領域がありません。
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>From を壊すことがなく、カスタムのドメインへの自動応答を抑制する: ポリシー
<a name="SuppressAutoReply"> </a>

新しい: ポリシーの適用、不要になった使用できる: \< \>の自動応答を抑制します。代わりに、ドメインには、null の MX レコードを設定する必要があります。
  
メール エクスチェン ジャー (MX) レコードは、ドメインのメールを受信するメール サーバーを識別する dns リソース レコードです。応答するサーバーがメッセージを送信するアドレスが公開されていないために、自動応答 (とすべての返信) が自然な抑制されます。
  
設定すると、null の MX レコードをカスタムのドメイン。
  
- ドメインを選択しているメッセージを送信する () が電子メールを受信します。など、プライマリ ドメインが contoso.com である場合は、noreply.contoso.com を選択する可能性があります。
    
- Null ドメインの MX レコードを設定します。Null の MX レコードは、1 つのドットのなどから成ります。
    
  ```
  noreply.contoso.com IN MX .
  ```

Null MX を発行する方法の詳細については、 [RFC 7505](https://tools.ietf.org/html/rfc7505)を参照してください。
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Office 365 からオーバーライド: 強制ポリシーに対応
<a name="Override"> </a>

新しいポリシーを展開の完了後、次の方法のいずれかを使用して Office 365 から受信した、受信メール用には、このポリシーをバイパスすることもだけ。 
  
- IP のリストを許可します。
    
- オンラインの Exchange のメール フロー ルール
    
マイクロソフトはからの強制をオーバーライドすることを強くお勧めします。 ポリシーです。このポリシーをオーバーライドすると、スパムにさらされる、フィッシング詐欺、およびその他のサイバー犯罪の組織のリスクを増やすことができます。
  
Office 365 に送信する、送信メール用には、このポリシーを無効にすることはできません。また、Outlook.com には、サポートを通じても、いかなる種類のオーバーライドはできません。 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>防止し、Office 365 のサイバー犯罪を防ぐには、他の方法
<a name="OtherProtection"> </a>

フィッシング詐欺などのサイバー犯罪に対して、組織を強化する方法の詳細については、スパム、データ漏洩、およびその他の脅威は、 [Office 365 のセキュリティのベスト プラクティス](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3)を参照してください。
  
## <a name="related-topics"></a>関連項目

[バックスキャター メッセージと EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

