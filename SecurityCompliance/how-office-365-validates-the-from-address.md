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
ms.openlocfilehash: 562e08aa54cb6544beccb6f0e8760735f67b834b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531589"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="559f9-103">Office 365 がフィッシング詐欺を防ぐために送信者のアドレスを検証する方法</span><span class="sxs-lookup"><span data-stu-id="559f9-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="559f9-p101">Office 365 と Outlook.com の電子メール アカウントは、ますます多くのフィッシング攻撃を受け取ります。元の値を持つメッセージを送信するのには、フィッシングを使用して 1 つの方法: アドレスは[RFC 5322](https://tools.ietf.org/html/rfc5322)に準拠していません。From: アドレスとも呼ばれます 5322.From のアドレスです。このタイプのフィッシング詐欺を防ぐため、Office 365 と Outlook.com を必要と、RFC 準拠を含めるには、サービスで受信したメッセージから: この資料で説明したように対処します。</span><span class="sxs-lookup"><span data-stu-id="559f9-p101">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks. One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322). The From: address is also called the 5322.From address. To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="559f9-p102">この資料の情報では、一般的な電子メール アドレスの形式の基本を理解する必要があります。詳細については、 [RFC 3696](https://tools.ietf.org/html/rfc3696)だけでなく、 [RFC 5322](https://tools.ietf.org/html/rfc5322) (特にセクション 3.2.3、3.4、3.4.1)、 [RFC 5321](https://tools.ietf.org/html/rfc5321)を参照してください。この資料では、5322.From のアドレスをポリシーの適用についてです。この資料の 5321.MailFrom のアドレスではありません。</span><span class="sxs-lookup"><span data-stu-id="559f9-p102">The information in this article requires you to have a basic understanding of the general format of email addresses. For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696). This article is about policy enforcement for the 5322.From address. This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="559f9-p103">残念ながら、いるデータがインターネット上のいくつか「正当な」電子メールを持たない、メッセージを送信し続けている従来のメール サーバーから不正な形式または: アドレスです。これらのレガシー ・ システムを使用している組織から定期的に電子メールを受信する場合は、これらの組織は最新のセキュリティ標準に準拠するメール サーバーを更新するをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="559f9-p103">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address. If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="559f9-114">マイクロソフトは、2017 年 11 月 9日に、この資料に記載のポリシーの強制をロールアウトを開始します。</span><span class="sxs-lookup"><span data-stu-id="559f9-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="559f9-115">Office 365 での有効な使用を強制する方法: フィッシング攻撃を防ぐためにアドレス</span><span class="sxs-lookup"><span data-stu-id="559f9-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="559f9-p104">使用を強制する方法を変更している office 365: 向上するために受信メッセージのアドレスがフィッシング攻撃から保護します。この資料では。</span><span class="sxs-lookup"><span data-stu-id="559f9-p104">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks. In this article:</span></span>
  
- [<span data-ttu-id="559f9-118">有効なすべてのメッセージがあります: アドレス</span><span class="sxs-lookup"><span data-stu-id="559f9-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="559f9-119">有効なすべてのメッセージがあります: アドレス</span><span class="sxs-lookup"><span data-stu-id="559f9-119">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="559f9-120">元の書式設定: 表示名が含まれていない場合の対処</span><span class="sxs-lookup"><span data-stu-id="559f9-120">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [<span data-ttu-id="559f9-121">元の書式設定: 表示名が含まれている場合の対処</span><span class="sxs-lookup"><span data-stu-id="559f9-121">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [<span data-ttu-id="559f9-122">有効/無効からの他の例: アドレス</span><span class="sxs-lookup"><span data-stu-id="559f9-122">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="559f9-123">From を壊すことがなく、カスタムのドメインへの自動応答を抑制する: ポリシー</span><span class="sxs-lookup"><span data-stu-id="559f9-123">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="559f9-124">Office 365 からオーバーライド: 強制ポリシーに対応</span><span class="sxs-lookup"><span data-stu-id="559f9-124">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="559f9-125">防止し、Office 365 のサイバー犯罪を防ぐには、他の方法</span><span class="sxs-lookup"><span data-stu-id="559f9-125">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="559f9-126">Terry Zink のブログを読む他のユーザーの代理として送信することは、詳細については、この変更によっては影響を受けません」[のこと、電子メールの [送信者] を参照するときですか?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)"です。</span><span class="sxs-lookup"><span data-stu-id="559f9-126">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="559f9-127">有効なすべてのメッセージがあります: アドレス</span><span class="sxs-lookup"><span data-stu-id="559f9-127">All messages must include a valid From: address</span></span>
<span data-ttu-id="559f9-128"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="559f9-128"></span></span>

<span data-ttu-id="559f9-p105">いくつかの自動化されたメッセージは含まないと: 送信時に対応します。以前は、Office 365 または Outlook.com、差出人にメッセージを受信しました: アドレス、サービスの追加から次の既定値: 成果物を作成するためにメッセージのアドレス。</span><span class="sxs-lookup"><span data-stu-id="559f9-p105">Some automated messages don't include a From: address when they are sent. In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="559f9-p106">2017 年 11 月 9日の開始 Office 365 は、ロールアウトの変更新しいルールが適用されますが、データ センター、メール サーバーに位置せず、元のメッセージ: アドレスは、Office 365 または Outlook.com では受け付けられなく。代わりに、Office 365 によって受信されたメッセージをすべて含まれていなければなりませんから、有効な: アドレスです。それ以外の場合、メッセージは、Outlook.com と Office 365 で、削除済みアイテムまたは迷惑メール フォルダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="559f9-p106">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com. Instead, all messages received by Office 365 must already contain a valid From: address. Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="559f9-134">構文の概要: 元の形式が無効です: Office 365 のアドレス</span><span class="sxs-lookup"><span data-stu-id="559f9-134">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="559f9-135"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="559f9-135"></span></span>

<span data-ttu-id="559f9-p107">値の形式: アドレスは、いくつかの Rfc の間で詳細に定義されています。多くのバリエーションに対応し、有効または無効なものと考えることがあります。シンプル、マイクロソフトは、次の形式と定義を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="559f9-p107">The format for the value of the From: address is defined in detail across several RFCs. There are many variations on addressing and what may be considered valid or invalid. To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="559f9-139">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="559f9-139">Where:</span></span>
  
- <span data-ttu-id="559f9-p108">(省略可能) *表示名*は、電子メール アドレスの所有者を記述する語句です。たとえば、送信者のメールボックスの名前よりもわかりやすい名前があります。表示名を使用すると、省略可能です。ただし、表示名を使用する場合は、お勧めことを常に、引用符で囲むようにします。</span><span class="sxs-lookup"><span data-stu-id="559f9-p108">(Optional)  *displayname*  is a phrase that describes the owner of the email address. For example, this might be a more user-friendly name to describe the sender than the name of the mailbox. Using a display name is optional. However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="559f9-144">(必須) *emailaddress*が構成されています。</span><span class="sxs-lookup"><span data-stu-id="559f9-144">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="559f9-145">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="559f9-145">Where:</span></span>
    
  - <span data-ttu-id="559f9-p109">(必須) *ローカル部分*は、アドレスに関連付けられているメールボックスを識別する文字列です。これは、ドメイン内で一意です。多くの場合、メールボックスの所有者のユーザー名または GUID が、ローカル部分の値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="559f9-p109">(Required)  *local-part*  is a string that identifies the mailbox associated with the address. This is unique within the domain. Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="559f9-149">(必須) *ドメイン*は、電子メール アドレスのローカル部分で識別されるメールボックスをホストしているメール サーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="559f9-149">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="559f9-150">元の書式設定: 表示名が含まれていない場合の対処</span><span class="sxs-lookup"><span data-stu-id="559f9-150">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="559f9-151"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="559f9-151"></span></span>

<span data-ttu-id="559f9-p110">A が正しく書式設定: 表示名が含まれていないアドレスには、山括弧の有無には 1 つの電子メール アドレスのみが含まれています。スペースを山かっこを分離しないことをお勧めします。さらに、ないものを含んでいる電子メール アドレスの後。</span><span class="sxs-lookup"><span data-stu-id="559f9-p110">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets. Microsoft recommends that you do not separate the angle brackets with spaces. In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="559f9-155">次の例では有効です。</span><span class="sxs-lookup"><span data-stu-id="559f9-155">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="559f9-156">次の使用例は有効では、山括弧と電子メール アドレスの間にスペースが含まれていますのでお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="559f9-156">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="559f9-157">次の使用例が正しくない電子メール アドレスの後ろのテキストが含まれているため。</span><span class="sxs-lookup"><span data-stu-id="559f9-157">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="559f9-158">元の書式設定: 表示名が含まれている場合の対処</span><span class="sxs-lookup"><span data-stu-id="559f9-158">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="559f9-159"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="559f9-159"></span></span>

<span data-ttu-id="559f9-160">: 表示名の値が含まれているアドレスの場合は、次の規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="559f9-160">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="559f9-p111">送信者のアドレスが表示名を含む表示名にコンマが含まれる場合は、表示名は引用符で囲む必要があります。例えば：</span><span class="sxs-lookup"><span data-stu-id="559f9-p111">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks. For example:</span></span>
    
    <span data-ttu-id="559f9-163">次の例では有効です。</span><span class="sxs-lookup"><span data-stu-id="559f9-163">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="559f9-164">次の使用例が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="559f9-164">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="559f9-165">いない表示名を表示名にコンマが含まれている場合の引用符で囲むは、RFC 5322 無効な場合します。</span><span class="sxs-lookup"><span data-stu-id="559f9-165">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="559f9-166">ベスト プラクティスとしてに関係なく表示名の前後に引用符またはが存在しないかどうかは、表示名にコンマです。</span><span class="sxs-lookup"><span data-stu-id="559f9-166">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="559f9-167">送信者のアドレスには、表示名が含まれている場合は、山かっこ内で電子メール アドレスを囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="559f9-167">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="559f9-168">最善の方法として、表示名と電子メール アドレスの間にスペースを挿入することを Microsoft は強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="559f9-168">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="559f9-169">有効/無効からの他の例: アドレス</span><span class="sxs-lookup"><span data-stu-id="559f9-169">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="559f9-170"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="559f9-170"></span></span>

- <span data-ttu-id="559f9-171">無効です。</span><span class="sxs-lookup"><span data-stu-id="559f9-171">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="559f9-p112">無効です。電子メール アドレスは山かっこで囲まれていません。</span><span class="sxs-lookup"><span data-stu-id="559f9-p112">Invalid. The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="559f9-p113">有効ですがないことをお勧めします。表示名は引用符ではありません。ベスト プラクティスとして、常に表示名を囲む引用符を配置します。</span><span class="sxs-lookup"><span data-stu-id="559f9-p113">Valid, but not recommended. The display name is not in quotes. As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="559f9-p114">無効です。引用符で囲まれた表示名だけでなくすべて囲まれています。</span><span class="sxs-lookup"><span data-stu-id="559f9-p114">Invalid. Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="559f9-p115">無効です。電子メール アドレスを山かっこはありません。</span><span class="sxs-lookup"><span data-stu-id="559f9-p115">Invalid. There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="559f9-p116">無効です。表示名と左かっこの間にスペースはありません。</span><span class="sxs-lookup"><span data-stu-id="559f9-p116">Invalid. There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="559f9-p117">無効です。表示名を右 quotation mark、左の山かっこの間の領域がありません。</span><span class="sxs-lookup"><span data-stu-id="559f9-p117">Invalid. There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="559f9-185">From を壊すことがなく、カスタムのドメインへの自動応答を抑制する: ポリシー</span><span class="sxs-lookup"><span data-stu-id="559f9-185">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="559f9-186"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="559f9-186"></span></span>

<span data-ttu-id="559f9-p118">新しい: ポリシーの適用、不要になった使用できる: \< \>の自動応答を抑制します。代わりに、ドメインには、null の MX レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="559f9-p118">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies. Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="559f9-p119">メール エクスチェン ジャー (MX) レコードは、ドメインのメールを受信するメール サーバーを識別する dns リソース レコードです。応答するサーバーがメッセージを送信するアドレスが公開されていないために、自動応答 (とすべての返信) が自然な抑制されます。</span><span class="sxs-lookup"><span data-stu-id="559f9-p119">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain. Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="559f9-191">設定すると、null の MX レコードをカスタムのドメイン。</span><span class="sxs-lookup"><span data-stu-id="559f9-191">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="559f9-p120">ドメインを選択しているメッセージを送信する () が電子メールを受信します。など、プライマリ ドメインが contoso.com である場合は、noreply.contoso.com を選択する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559f9-p120">Choose a domain from which to send messages that doesn't accept (receive) email. For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="559f9-p121">Null ドメインの MX レコードを設定します。Null の MX レコードは、1 つのドットのなどから成ります。</span><span class="sxs-lookup"><span data-stu-id="559f9-p121">Set up the null MX record for your domain. A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="559f9-196">Null MX を発行する方法の詳細については、 [RFC 7505](https://tools.ietf.org/html/rfc7505)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559f9-196">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="559f9-197">Office 365 からオーバーライド: 強制ポリシーに対応</span><span class="sxs-lookup"><span data-stu-id="559f9-197">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="559f9-198"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="559f9-198"></span></span>

<span data-ttu-id="559f9-199">新しいポリシーを展開の完了後、次の方法のいずれかを使用して Office 365 から受信した、受信メール用には、このポリシーをバイパスすることもだけ。</span><span class="sxs-lookup"><span data-stu-id="559f9-199">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="559f9-200">IP のリストを許可します。</span><span class="sxs-lookup"><span data-stu-id="559f9-200">IP allow lists</span></span>
    
- <span data-ttu-id="559f9-201">オンラインの Exchange のメール フロー ルール</span><span class="sxs-lookup"><span data-stu-id="559f9-201">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="559f9-p122">マイクロソフトはからの強制をオーバーライドすることを強くお勧めします。 ポリシーです。このポリシーをオーバーライドすると、スパムにさらされる、フィッシング詐欺、およびその他のサイバー犯罪の組織のリスクを増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="559f9-p122">Microsoft strongly recommends against overriding the enforcement of the From: policy. Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="559f9-p123">Office 365 に送信する、送信メール用には、このポリシーを無効にすることはできません。また、Outlook.com には、サポートを通じても、いかなる種類のオーバーライドはできません。</span><span class="sxs-lookup"><span data-stu-id="559f9-p123">You cannot override this policy for outbound mail you send in Office 365. In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="559f9-206">防止し、Office 365 のサイバー犯罪を防ぐには、他の方法</span><span class="sxs-lookup"><span data-stu-id="559f9-206">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="559f9-207"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="559f9-207"></span></span>

<span data-ttu-id="559f9-208">フィッシング詐欺などのサイバー犯罪に対して、組織を強化する方法の詳細については、スパム、データ漏洩、およびその他の脅威は、 [Office 365 のセキュリティのベスト プラクティス](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559f9-208">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="559f9-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="559f9-209">Related Topics</span></span>

[<span data-ttu-id="559f9-210">バックスキャター メッセージと EOP</span><span class="sxs-lookup"><span data-stu-id="559f9-210">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

