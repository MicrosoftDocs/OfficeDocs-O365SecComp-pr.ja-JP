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
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="c9098-103">Office 365 がフィッシングを防ぐために差出人アドレスを検証する方法</span><span class="sxs-lookup"><span data-stu-id="c9098-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="c9098-104">Office 365 と Outlook.com 電子メールアカウントには、次第に大量のフィッシング攻撃があります。</span><span class="sxs-lookup"><span data-stu-id="c9098-104">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="c9098-105">phishers を使用する方法の1つは、 [RFC 5322](https://tools.ietf.org/html/rfc5322)に準拠していない From: アドレスの値を持つメッセージを送信することです。</span><span class="sxs-lookup"><span data-stu-id="c9098-105">One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="c9098-106">from: アドレスは、5322.from アドレスとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c9098-106">The From: address is also called the 5322.From address.</span></span> <span data-ttu-id="c9098-107">この種のフィッシングを防止するために、Office 365 と Outlook.com は、この記事で説明されているように、RFC 準拠の差出人: アドレスを含むようにサービスによって受信されるメッセージを要求します。</span><span class="sxs-lookup"><span data-stu-id="c9098-107">To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9098-108">この記事に記載されている情報では、電子メールアドレスの一般的な形式を基本的に理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9098-108">The information in this article requires you to have a basic understanding of the general format of email addresses.</span></span> <span data-ttu-id="c9098-109">詳細については、rfc [5322](https://tools.ietf.org/html/rfc5322) (特にセクション3.2.3、3.4、および 3.4.1)、rfc [5321](https://tools.ietf.org/html/rfc5321)、および[rfc 3696](https://tools.ietf.org/html/rfc3696)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9098-109">For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696).</span></span> <span data-ttu-id="c9098-110">この記事では、5322.from アドレスのポリシーの適用について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9098-110">This article is about policy enforcement for the 5322.From address.</span></span> <span data-ttu-id="c9098-111">この記事では、5321.mailfrom の MailFrom アドレスについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="c9098-111">This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="c9098-112">残念ながら、インターネット上に従来の電子メールサーバーがいくつか存在していても、引き続き "正当な" 電子メールメッセージを送信しています。アドレスが不明であるか、無効である。</span><span class="sxs-lookup"><span data-stu-id="c9098-112">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address.</span></span> <span data-ttu-id="c9098-113">これらの従来のシステムを使用する組織から定期的に電子メールを受信する場合は、最新のセキュリティ標準に準拠するようにメールサーバーを更新するように組織を促します。</span><span class="sxs-lookup"><span data-stu-id="c9098-113">If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="c9098-114">Microsoft は、2017年11月9日にこの記事に記載されているポリシーの適用を開始します。</span><span class="sxs-lookup"><span data-stu-id="c9098-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="c9098-115">Office 365 がフィッシング攻撃を防止するために有効な From: アドレスの使用を強制する方法</span><span class="sxs-lookup"><span data-stu-id="c9098-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="c9098-116">Office 365 は、フィッシング攻撃からの保護を強化するために、受信したメッセージ内の From: アドレスの使用を強制する方法に変更を加えています。</span><span class="sxs-lookup"><span data-stu-id="c9098-116">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks.</span></span> <span data-ttu-id="c9098-117">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="c9098-117">In this article:</span></span>
  
- [<span data-ttu-id="c9098-118">すべてのメッセージに有効な差出人: アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9098-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="c9098-119">表示名を含めない場合の From: アドレスの形式</span><span class="sxs-lookup"><span data-stu-id="c9098-119">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [<span data-ttu-id="c9098-120">表示名が含まれている場合の From: アドレスの形式</span><span class="sxs-lookup"><span data-stu-id="c9098-120">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [<span data-ttu-id="c9098-121">有効で無効な From: アドレスの追加例</span><span class="sxs-lookup"><span data-stu-id="c9098-121">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="c9098-122">カスタムドメインに対する自動返信を抑制して、From: ポリシーを破損させます。</span><span class="sxs-lookup"><span data-stu-id="c9098-122">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="c9098-123">Office 365 From: address 強制ポリシーの上書き</span><span class="sxs-lookup"><span data-stu-id="c9098-123">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="c9098-124">Office 365 で cybercrimes を防止し、保護するためのその他の方法</span><span class="sxs-lookup"><span data-stu-id="c9098-124">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="c9098-125">他のユーザーの代理としての送信は、この変更の影響を受けません。詳細については、「「[メールの送信者」を参照して](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)ください」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9098-125">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="c9098-126">すべてのメッセージに有効な差出人: アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9098-126">All messages must include a valid From: address</span></span>
<span data-ttu-id="c9098-127"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="c9098-127"></span></span>

<span data-ttu-id="c9098-128">一部の自動メッセージには、送信時に From: アドレスは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c9098-128">Some automated messages don't include a From: address when they are sent.</span></span> <span data-ttu-id="c9098-129">以前は、Office 365 または Outlook.com が From: アドレスなしでメッセージを受信すると、サービスは次の既定の from: address をメッセージに追加して、そのメッセージを配信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c9098-129">In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="c9098-130">2017年11月9日以降、office 365 はデータセンターとメールサーバーへの変更をロールアウトします。これにより、From: アドレスのないメッセージは office 365 または Outlook.com によって受け入れられなくなり、新しいルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9098-130">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com.</span></span> <span data-ttu-id="c9098-131">その代わりに、Office 365 で受信したすべてのメッセージには、有効な差出人: アドレスが既に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9098-131">Instead, all messages received by Office 365 must already contain a valid From: address.</span></span> <span data-ttu-id="c9098-132">それ以外の場合は、Outlook.com と Office 365 の迷惑メールフォルダーまたは削除済みアイテムフォルダーにメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="c9098-132">Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="c9098-133">構文の概要: Office 365 の From: アドレスの有効な形式</span><span class="sxs-lookup"><span data-stu-id="c9098-133">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="c9098-134"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="c9098-134"></span></span>

<span data-ttu-id="c9098-135">From: アドレスの値の形式は、いくつかの rfc で詳細に定義されています。</span><span class="sxs-lookup"><span data-stu-id="c9098-135">The format for the value of the From: address is defined in detail across several RFCs.</span></span> <span data-ttu-id="c9098-136">アドレス指定には、さまざまなバリエーションがあり、有効または無効と見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="c9098-136">There are many variations on addressing and what may be considered valid or invalid.</span></span> <span data-ttu-id="c9098-137">簡単にするために、Microsoft は次の形式と定義を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9098-137">To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="c9098-138">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c9098-138">Where:</span></span>
  
- <span data-ttu-id="c9098-139">オプション *displayname*は、電子メールアドレスの所有者を説明する語句です。</span><span class="sxs-lookup"><span data-stu-id="c9098-139">(Optional)  *displayname*  is a phrase that describes the owner of the email address.</span></span> <span data-ttu-id="c9098-140">たとえば、これは、メールボックスの名前よりも、送信者を示すユーザーフレンドリな名前になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c9098-140">For example, this might be a more user-friendly name to describe the sender than the name of the mailbox.</span></span> <span data-ttu-id="c9098-141">表示名の使用はオプションです。</span><span class="sxs-lookup"><span data-stu-id="c9098-141">Using a display name is optional.</span></span> <span data-ttu-id="c9098-142">ただし、表示名の使用を選択する場合は、表示されているとおり常に引用符で囲むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9098-142">However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="c9098-143">要する *emailaddress*は次のもので構成されます。</span><span class="sxs-lookup"><span data-stu-id="c9098-143">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="c9098-144">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c9098-144">Where:</span></span>
    
  - <span data-ttu-id="c9098-145">要する *local part*は、アドレスに関連付けられているメールボックスを識別する文字列です。</span><span class="sxs-lookup"><span data-stu-id="c9098-145">(Required)  *local-part*  is a string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="c9098-146">これは、ドメイン内で一意です。</span><span class="sxs-lookup"><span data-stu-id="c9098-146">This is unique within the domain.</span></span> <span data-ttu-id="c9098-147">多くの場合、メールボックス所有者のユーザー名または GUID は、ローカル部分の値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9098-147">Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="c9098-148">要する *domain*は、電子メールアドレスのローカル部分で識別されるメールボックスをホストするメールサーバーの完全修飾ドメイン名 (FQDN) です。</span><span class="sxs-lookup"><span data-stu-id="c9098-148">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="c9098-149">表示名を含めない場合の From: アドレスの形式</span><span class="sxs-lookup"><span data-stu-id="c9098-149">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="c9098-150"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="c9098-150"></span></span>

<span data-ttu-id="c9098-151">表示名が含まれていない電子メールアドレスが1つだけ含まれている場合は、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="c9098-151">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets.</span></span> <span data-ttu-id="c9098-152">Microsoft では、山かっこをスペースで区切らないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9098-152">Microsoft recommends that you do not separate the angle brackets with spaces.</span></span> <span data-ttu-id="c9098-153">また、電子メールアドレスの後に何も含めないでください。</span><span class="sxs-lookup"><span data-stu-id="c9098-153">In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="c9098-154">次の例は有効です。</span><span class="sxs-lookup"><span data-stu-id="c9098-154">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="c9098-155">次の例は有効ですが、角かっこと電子メールアドレスの間にスペースが含まれているため、推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="c9098-155">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="c9098-156">次の例は、電子メールアドレスの後にテキストが含まれているため、無効です。</span><span class="sxs-lookup"><span data-stu-id="c9098-156">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="c9098-157">表示名が含まれている場合の From: アドレスの形式</span><span class="sxs-lookup"><span data-stu-id="c9098-157">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="c9098-158"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="c9098-158"></span></span>

<span data-ttu-id="c9098-159">From: 表示名の値を含むアドレスでは、次のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9098-159">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="c9098-160">送信者のアドレスに表示名が含まれており、表示名にコンマが含まれている場合は、表示名を引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9098-160">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks.</span></span> <span data-ttu-id="c9098-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c9098-161">For example:</span></span>
    
    <span data-ttu-id="c9098-162">次の例は有効です。</span><span class="sxs-lookup"><span data-stu-id="c9098-162">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="c9098-163">次の例は無効です。</span><span class="sxs-lookup"><span data-stu-id="c9098-163">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="c9098-164">表示名にコンマが含まれている場合は、RFC 5322 に従って、表示名が引用符で囲まれていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="c9098-164">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="c9098-165">表示名の中にコンマが含まれているかどうかに関係なく、ベストプラクティスとして、表示名を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c9098-165">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="c9098-166">送信者のアドレスに表示名が含まれている場合は、その電子メールアドレスを山かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9098-166">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="c9098-167">ベストプラクティスとして、表示名と電子メールアドレスの間にスペースを挿入することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9098-167">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="c9098-168">有効で無効な From: アドレスの追加例</span><span class="sxs-lookup"><span data-stu-id="c9098-168">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="c9098-169"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c9098-169"></span></span>

- <span data-ttu-id="c9098-170">有効な</span><span class="sxs-lookup"><span data-stu-id="c9098-170">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="c9098-171">無効</span><span class="sxs-lookup"><span data-stu-id="c9098-171">Invalid.</span></span> <span data-ttu-id="c9098-172">電子メールアドレスは、山かっこで囲まれていません。</span><span class="sxs-lookup"><span data-stu-id="c9098-172">The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="c9098-173">有効ですが、推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="c9098-173">Valid, but not recommended.</span></span> <span data-ttu-id="c9098-174">表示名が引用符で囲まれていません。</span><span class="sxs-lookup"><span data-stu-id="c9098-174">The display name is not in quotes.</span></span> <span data-ttu-id="c9098-175">ベストプラクティスとして、表示名を常に引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c9098-175">As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="c9098-176">無効</span><span class="sxs-lookup"><span data-stu-id="c9098-176">Invalid.</span></span> <span data-ttu-id="c9098-177">表示名だけでなく、すべてが引用符で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="c9098-177">Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="c9098-178">無効</span><span class="sxs-lookup"><span data-stu-id="c9098-178">Invalid.</span></span> <span data-ttu-id="c9098-179">電子メールアドレスは、山かっこで囲まれていません。</span><span class="sxs-lookup"><span data-stu-id="c9098-179">There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="c9098-180">無効</span><span class="sxs-lookup"><span data-stu-id="c9098-180">Invalid.</span></span> <span data-ttu-id="c9098-181">表示名と左山かっこの間にスペースはありません。</span><span class="sxs-lookup"><span data-stu-id="c9098-181">There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="c9098-182">無効</span><span class="sxs-lookup"><span data-stu-id="c9098-182">Invalid.</span></span> <span data-ttu-id="c9098-183">[表示名] と [左山かっこ] の前後には、二重引用符の間にスペースを入れることはできません。</span><span class="sxs-lookup"><span data-stu-id="c9098-183">There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="c9098-184">カスタムドメインに対する自動返信を抑制して、From: ポリシーを破損させます。</span><span class="sxs-lookup"><span data-stu-id="c9098-184">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="c9098-185"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="c9098-185"></span></span>

<span data-ttu-id="c9098-186">新しい from: policy 執行を使用すると、次\< \>のものを使用できなくなります。自動応答を抑制します。</span><span class="sxs-lookup"><span data-stu-id="c9098-186">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies.</span></span> <span data-ttu-id="c9098-187">代わりに、カスタムドメインの null MX レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9098-187">Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="c9098-188">メールエクスチェンジャー (MX) レコードは、ドメインのメールを受信するメールサーバーを識別する、DNS 内のリソースレコードです。</span><span class="sxs-lookup"><span data-stu-id="c9098-188">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain.</span></span> <span data-ttu-id="c9098-189">応答サーバーがメッセージを送信できる公開アドレスがないため、自動応答 (およびすべての返信) は自然に抑制されます。</span><span class="sxs-lookup"><span data-stu-id="c9098-189">Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="c9098-190">カスタムドメイン用の null MX レコードを設定する場合:</span><span class="sxs-lookup"><span data-stu-id="c9098-190">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="c9098-191">電子メールを受信しないメッセージの送信元のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9098-191">Choose a domain from which to send messages that doesn't accept (receive) email.</span></span> <span data-ttu-id="c9098-192">たとえば、プライマリドメインが contoso.com の場合は、noreply.contoso.com を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="c9098-192">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="c9098-193">ドメインの null MX レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9098-193">Set up the null MX record for your domain.</span></span> <span data-ttu-id="c9098-194">null MX レコードは、次の例のように1つのドットで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c9098-194">A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="c9098-195">null MX の公開の詳細については、「 [RFC 7505](https://tools.ietf.org/html/rfc7505)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9098-195">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="c9098-196">Office 365 From: address 強制ポリシーの上書き</span><span class="sxs-lookup"><span data-stu-id="c9098-196">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="c9098-197"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="c9098-197"></span></span>

<span data-ttu-id="c9098-198">新しいポリシーのロールアウトが完了したら、次のいずれかの方法を使用して、Office 365 から受信する受信メールに対してのみこのポリシーをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="c9098-198">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="c9098-199">IP 許可一覧</span><span class="sxs-lookup"><span data-stu-id="c9098-199">IP allow lists</span></span>
    
- <span data-ttu-id="c9098-200">Exchange Online のメールフロールール</span><span class="sxs-lookup"><span data-stu-id="c9098-200">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="c9098-201">Microsoft は、From: ポリシーの強制を上書きすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9098-201">Microsoft strongly recommends against overriding the enforcement of the From: policy.</span></span> <span data-ttu-id="c9098-202">このポリシーを無効にすると、スパム、フィッシング、その他の cybercrimes にさらされるリスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="c9098-202">Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="c9098-203">Office 365 で送信する送信メールに対してこのポリシーを上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c9098-203">You cannot override this policy for outbound mail you send in Office 365.</span></span> <span data-ttu-id="c9098-204">さらに、Outlook.com では、サポートによっても、あらゆる種類の上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="c9098-204">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="c9098-205">Office 365 で cybercrimes を防止し、保護するためのその他の方法</span><span class="sxs-lookup"><span data-stu-id="c9098-205">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="c9098-206"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="c9098-206"></span></span>

<span data-ttu-id="c9098-207">フィッシング、スパム、データ侵害、その他の脅威などの cybercrimes に対して組織を強化する方法の詳細については、「 [Office 365 のセキュリティのベストプラクティス](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9098-207">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c9098-208">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c9098-208">Related Topics</span></span>

[<span data-ttu-id="c9098-209">バックスキャター メッセージと EOP</span><span class="sxs-lookup"><span data-stu-id="c9098-209">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

