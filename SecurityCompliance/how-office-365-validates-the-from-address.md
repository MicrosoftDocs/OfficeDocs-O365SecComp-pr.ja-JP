---
title: Office 365 がフィッシングを防ぐために差出人アドレスを検証する方法
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 'フィッシングを防止するために、Office 365 と Outlook.com では、From: アドレスの RFC 準拠が必要になりました。'
ms.openlocfilehash: e540e56a7a40d13a92719865fccefefa61de47c2
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253935"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Office 365 がフィッシングを防ぐために差出人アドレスを検証する方法

Office 365 と Outlook.com 電子メールアカウントには、次第に大量のフィッシング攻撃があります。 phishers を使用する方法の1つは、 [RFC 5322](https://tools.ietf.org/html/rfc5322)に準拠していない From: アドレスの値を持つメッセージを送信することです。 from: アドレスは、5322.from アドレスとも呼ばれます。 この種のフィッシングを防止するために、Office 365 と Outlook.com は、この記事で説明されているように、RFC 準拠の差出人: アドレスを含むようにサービスによって受信されるメッセージを要求します。
  
> [!NOTE]
> この記事に記載されている情報では、電子メールアドレスの一般的な形式を基本的に理解しておく必要があります。 詳細については、rfc [5322](https://tools.ietf.org/html/rfc5322) (特にセクション3.2.3、3.4、および 3.4.1)、rfc [5321](https://tools.ietf.org/html/rfc5321)、および[rfc 3696](https://tools.ietf.org/html/rfc3696)を参照してください。 この記事では、5322.from アドレスのポリシーの適用について説明します。 この記事では、5321.mailfrom の MailFrom アドレスについては説明しません。 
  
残念ながら、インターネット上に従来の電子メールサーバーがいくつか存在していても、引き続き "正当な" 電子メールメッセージを送信しています。アドレスが不明であるか、無効である。 これらの従来のシステムを使用する組織から定期的に電子メールを受信する場合は、最新のセキュリティ標準に準拠するようにメールサーバーを更新するように組織を促します。
  
Microsoft は、2017年11月9日にこの記事に記載されているポリシーの適用を開始します。
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Office 365 がフィッシング攻撃を防止するために有効な From: アドレスの使用を強制する方法

Office 365 は、フィッシング攻撃からの保護を強化するために、受信したメッセージ内の From: アドレスの使用を強制する方法に変更を加えています。 この記事の内容
  
- [すべてのメッセージに有効な差出人: アドレスを含める必要があります。](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [表示名を含めない場合の From: アドレスの形式](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [表示名が含まれている場合の From: アドレスの形式](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [有効で無効な From: アドレスの追加例](how-office-365-validates-the-from-address.md#Examples)
    
- [カスタムドメインに対する自動返信を抑制して、From: ポリシーを破損させます。](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [Office 365 From: address 強制ポリシーの上書き](how-office-365-validates-the-from-address.md#Override)
    
- [Office 365 で cybercrimes を防止し、保護するためのその他の方法](how-office-365-validates-the-from-address.md#OtherProtection)
    
他のユーザーの代理としての送信は、この変更の影響を受けません。詳細については、「「[メールの送信者」を参照して](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)ください」を参照してください。
  
### <a name="all-messages-must-include-a-valid-from-address"></a>すべてのメッセージに有効な差出人: アドレスを含める必要があります。
<a name="MustIncludeFromAddress"> </a>

一部の自動メッセージには、送信時に From: アドレスは含まれません。 以前は、Office 365 または Outlook.com が From: アドレスなしでメッセージを受信すると、サービスは次の既定の from: address をメッセージに追加して、そのメッセージを配信できるようにします。
  
```
From: <>
```

2017年11月9日以降、office 365 はデータセンターとメールサーバーへの変更をロールアウトします。これにより、From: アドレスのないメッセージは office 365 または Outlook.com によって受け入れられなくなり、新しいルールが適用されます。 その代わりに、Office 365 で受信したすべてのメッセージには、有効な差出人: アドレスが既に含まれている必要があります。 それ以外の場合は、Outlook.com と Office 365 の迷惑メールフォルダーまたは削除済みアイテムフォルダーにメッセージが送信されます。 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>構文の概要: Office 365 の From: アドレスの有効な形式
<a name="SyntaxOverviewFromAddress"> </a>

From: アドレスの値の形式は、いくつかの rfc で詳細に定義されています。 アドレス指定には、さまざまなバリエーションがあり、有効または無効と見なすことができます。 簡単にするために、Microsoft は次の形式と定義を使用することをお勧めします。
  
```
From: "displayname " <emailaddress >
```

詳細は次のとおりです。
  
- オプション *displayname*は、電子メールアドレスの所有者を説明する語句です。 たとえば、これは、メールボックスの名前よりも、送信者を示すユーザーフレンドリな名前になることがあります。 表示名の使用はオプションです。 ただし、表示名の使用を選択する場合は、表示されているとおり常に引用符で囲むことをお勧めします。 
    
- 要する *emailaddress*は次のもので構成されます。 
    
  ```
  local-part @domain
  ```

    詳細は次のとおりです。
    
  - 要する *local part*は、アドレスに関連付けられているメールボックスを識別する文字列です。 これは、ドメイン内で一意です。 多くの場合、メールボックス所有者のユーザー名または GUID は、ローカル部分の値として使用されます。 
    
  - 要する *domain*は、電子メールアドレスのローカル部分で識別されるメールボックスをホストするメールサーバーの完全修飾ドメイン名 (FQDN) です。 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>表示名を含めない場合の From: アドレスの形式
<a name="FormatNoDisplayName"> </a>

表示名が含まれていない電子メールアドレスが1つだけ含まれている場合は、次のように設定します。 Microsoft では、山かっこをスペースで区切らないことをお勧めします。 また、電子メールアドレスの後に何も含めないでください。
  
次の例は有効です。
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

次の例は有効ですが、角かっこと電子メールアドレスの間にスペースが含まれているため、推奨されていません。
  
```
From: < sender@contoso.com >
```

次の例は、電子メールアドレスの後にテキストが含まれているため、無効です。
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>表示名が含まれている場合の From: アドレスの形式
<a name="FormatDisplayName"> </a>

From: 表示名の値を含むアドレスでは、次のルールが適用されます。
  
- 送信者のアドレスに表示名が含まれており、表示名にコンマが含まれている場合は、表示名を引用符で囲む必要があります。 次に例を示します。
    
    次の例は有効です。
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    次の例は無効です。
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    表示名にコンマが含まれている場合は、RFC 5322 に従って、表示名が引用符で囲まれていないことを示します。
    
    表示名の中にコンマが含まれているかどうかに関係なく、ベストプラクティスとして、表示名を引用符で囲みます。
    
- 送信者のアドレスに表示名が含まれている場合は、その電子メールアドレスを山かっこで囲む必要があります。
    
    ベストプラクティスとして、表示名と電子メールアドレスの間にスペースを挿入することを強くお勧めします。
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>有効で無効な From: アドレスの追加例
<a name="Examples"> </a>

- 有効な
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- 無効 電子メールアドレスは、山かっこで囲まれていません。
    
  ```
  From: Office 365 sender@contoso.com
  ```

- 有効ですが、推奨されていません。 表示名が引用符で囲まれていません。 ベストプラクティスとして、表示名を常に引用符で囲みます。
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- 無効 表示名だけでなく、すべてが引用符で囲まれています。
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- 無効 電子メールアドレスは、山かっこで囲まれていません。
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- 無効 表示名と左山かっこの間にスペースはありません。
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- 無効 [表示名] と [左山かっこ] の前後には、二重引用符の間にスペースを入れることはできません。
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>カスタムドメインに対する自動返信を抑制して、From: ポリシーを破損させます。
<a name="SuppressAutoReply"> </a>

新しい from: policy 執行を使用すると、次\< \>のものを使用できなくなります。自動応答を抑制します。 代わりに、カスタムドメインの null MX レコードを設定する必要があります。
  
メールエクスチェンジャー (MX) レコードは、ドメインのメールを受信するメールサーバーを識別する、DNS 内のリソースレコードです。 応答サーバーがメッセージを送信できる公開アドレスがないため、自動応答 (およびすべての返信) は自然に抑制されます。
  
カスタムドメイン用の null MX レコードを設定する場合:
  
- 電子メールを受信しないメッセージの送信元のドメインを選択します。 たとえば、プライマリドメインが contoso.com の場合は、noreply.contoso.com を選択することができます。
    
- ドメインの null MX レコードを設定します。 null MX レコードは、次の例のように1つのドットで構成されます。
    
  ```
  noreply.contoso.com IN MX .
  ```

null MX の公開の詳細については、「 [RFC 7505](https://tools.ietf.org/html/rfc7505)」を参照してください。
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Office 365 From: address 強制ポリシーの上書き
<a name="Override"> </a>

新しいポリシーのロールアウトが完了したら、次のいずれかの方法を使用して、Office 365 から受信する受信メールに対してのみこのポリシーをバイパスできます。 
  
- IP 許可一覧
    
- Exchange Online のメールフロールール
    
Microsoft は、From: ポリシーの強制を上書きすることを強くお勧めします。 このポリシーを無効にすると、スパム、フィッシング、その他の cybercrimes にさらされるリスクが高まります。
  
Office 365 で送信する送信メールに対してこのポリシーを上書きすることはできません。 さらに、Outlook.com では、サポートによっても、あらゆる種類の上書きを許可しません。 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>Office 365 で cybercrimes を防止し、保護するためのその他の方法
<a name="OtherProtection"> </a>

フィッシング、スパム、データ侵害、その他の脅威などの cybercrimes に対して組織を強化する方法の詳細については、「 [Office 365 のセキュリティのベストプラクティス](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3)」を参照してください。
  
## <a name="related-topics"></a>関連トピック

[バックスキャター メッセージと EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

