---
title: DMARC を使用して Office 365 でメールを検証する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.custom: TN2DMC
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Office 365 組織から送信されたメッセージを検証するための、ドメインベースのメッセージ認証、レポート、および準拠 (DMARC) を構成する方法について説明します。
ms.openlocfilehash: d224acaf6b1d53cdf9ababca87c5880a5499c613
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341578"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a><span data-ttu-id="29a6b-103">DMARC を使用して Office 365 でメールを検証する</span><span class="sxs-lookup"><span data-stu-id="29a6b-103">Use DMARC to validate email in Office 365</span></span>

<span data-ttu-id="29a6b-p101">メール送信者を認証し、宛先の電子メールシステムがから送信されたメッセージを信頼していることを確認するために、ドメインベースのメッセージの認証、報告、および準拠 ([DMARC](https://dmarc.org)) は、送信者ポリシーフレームワーク (SPF) および domainkeys で識別されるメール (dkim) と連携して動作します。自分のドメイン。DMARC を SPF と dkim で実装すると、スプーフィングやフィッシング電子メールに対する保護が強化されます。DMARC はメールシステムの受信をサポートしており、SPF または dkim チェックに失敗したドメインから送信されたメッセージの処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p101">Domain-based Message Authentication, Reporting, and Conformance ([DMARC](https://dmarc.org)) works with Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM) to authenticate mail senders and ensure that destination email systems trust messages sent from your domain. Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email. DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span>
  
## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a><span data-ttu-id="29a6b-107">SPF と DMARC が連携して Office 365 の電子メールを保護するしくみ</span><span class="sxs-lookup"><span data-stu-id="29a6b-107">How do SPF and DMARC work together to protect email in Office 365?</span></span>
<span data-ttu-id="29a6b-108"><a name="SPFandDMARC"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-108"></span></span>

 <span data-ttu-id="29a6b-p102">電子メール メッセージには、発信者、送信者、またはアドレスが含まれていることがあります。これらのアドレスは、さまざまな目的に使用できます。たとえば、次のアドレスについて考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p102">An email message may contain multiple originator, or sender, addresses. These addresses are used for different purposes. For example, consider these addresses:</span></span> 
  
- <span data-ttu-id="29a6b-p103">**"Mail From" アドレス**: 送信者を識別し、配信不能通知など、メッセージの配信に関する問題が発生した場合に、いつ返信を送信するかを指定します。これは、電子メールメッセージの封筒部分に表示され、通常は電子メールアプリケーションによって表示されません。これは、MailFrom アドレスまたは逆パスアドレスと呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p103">**"Mail From" address**: Identifies the sender and specifies where to send return notices if any problems occur with the delivery of the message, such as non-delivery notices. This appears in the envelope portion of an email message and is not usually displayed by your email application. This is sometimes called the 5321.MailFrom address or the reverse-path address.</span></span>
    
- <span data-ttu-id="29a6b-p104">**"from" アドレス**: メールアプリケーションによって差出人アドレスとして表示されるアドレス。このアドレスは、電子メールの作成者を識別します。これは、メッセージの作成を担当するユーザーまたはシステムのメールボックスです。これは、5322.from アドレスと呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p104">**"From" address**: The address displayed as the From address by your mail application. This address identifies the author of the email. That is, the mailbox of the person or system responsible for writing the message. This is sometimes called the 5322.From address.</span></span>
    
<span data-ttu-id="29a6b-p105">SPF は、DNS TXT レコードを使用して、特定のドメインに対する認証済みの送信側 IP アドレスのリストを提示します。通常、SPF チェックは 5321.MailFrom アドレスに対してのみ実行されます。つまり、単独で SPF を使用すると、5322.From アドレスは認証されないことになります。これは、SPF チェックにパスしていても、5322.From 送信者アドレスがスプーフィングされたメッセージをユーザーが受信するというシナリオの余地を残すことになります。たとえば、次のような SMTP トランスクリプトを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p105">SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:</span></span>
  
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

<span data-ttu-id="29a6b-124">このトランスクリプトでは、送信者のアドレスは次にようになります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-124">In this transcript, the sender addresses are as follows:</span></span>
  
- <span data-ttu-id="29a6b-125">Mail From アドレス (5321.MailFrom): phish@phishing.contoso.com</span><span class="sxs-lookup"><span data-stu-id="29a6b-125">Mail from address (5321.MailFrom): phish@phishing.contoso.com</span></span>
    
- <span data-ttu-id="29a6b-126">From アドレス (5322.From): security@woodgrovebank.com</span><span class="sxs-lookup"><span data-stu-id="29a6b-126">From address (5322.From): security@woodgrovebank.com</span></span>
    
<span data-ttu-id="29a6b-p106">SPF を構成した場合、受信側サーバーは Mail From アドレス phish@phishing.contoso.com に対してチェックを実行します。メッセージがドメイン phishing.contoso.com の有効なソースから送信された場合は、SPF チェックをパスします。電子メール クライアントには差出人アドレスのみが表示されるため、ユーザーには、このメッセージが security@woodgrovebank.com から送信されたように見えます。SPF だけでは、woodgrovebank.com の有効性は認証されません。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p106">If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.</span></span>
  
<span data-ttu-id="29a6b-p107">DMARC を使用すると、From アドレスに対するチェックを受信側サーバーも実行するようになります。前述の例では、woodgrovebank.com の所定の場所に DMARC TXT レコードが存在していれば、From アドレスに対するチェックは失敗します。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p107">When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.</span></span>
  
## <a name="what-is-a-dmarc-txt-record"></a><span data-ttu-id="29a6b-133">DMARC TXT レコードとは</span><span class="sxs-lookup"><span data-stu-id="29a6b-133">What is a DMARC TXT record?</span></span>
<span data-ttu-id="29a6b-134"><a name="WhatisDMARC"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-134"></span></span>

<span data-ttu-id="29a6b-p108">SPF の DNS レコードと同様に、DMARC のレコードは、スプーフィングとフィッシングの防止に役立つ DNS テキスト (TXT) レコードです。DMARC TXT レコードは DNS で発行します。DMARC TXT レコードは、メール作成者の IP アドレスを、送信側ドメインの所有者とされる名前と照合して、メール メッセージの発信元を確認します。 この DMARC TXT レコードにより、承認済みの送信メール サーバーを識別します。送信先メール システムでは、メッセージが承認済みの送信メール サーバーから発信されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p108">Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.</span></span>
  
<span data-ttu-id="29a6b-140">Microsoft の DMARC TXT レコードは、次のような内容になります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-140">Microsoft's DMARC TXT record looks something like this:</span></span>
  
```
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 
```

<span data-ttu-id="29a6b-p109">Microsoft は、DMARC レポートをサード パーティの [Agari](https://agari.com) に送信します。 Agari では、DMARC レポートを収集して分析します。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p109">Microsoft sends its DMARC reports to [Agari](https://agari.com), a 3rd party. Agari collects and analyzes DMARC reports.</span></span>
  
## <a name="implement-dmarc-for-inbound-mail"></a><span data-ttu-id="29a6b-143">受信メール用に DMARC を実装する</span><span class="sxs-lookup"><span data-stu-id="29a6b-143">Implement DMARC for inbound mail</span></span>
<span data-ttu-id="29a6b-144"><a name="implementDMARCinbound"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-144"></span></span>

<span data-ttu-id="29a6b-p110">Office 365 で受信するメールの DMARC を設定するために必要な手順はありません。すべて、Microsoft が手配します。DMARC チェックをパスしないメールに対する処理について知る必要がある場合は、「[Office 365 が DMARC に失敗した受信メールを処理する方法](use-dmarc-to-validate-email.md#inbounddmarcfail)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p110">You don't have to do a thing to set up DMARC for mail that you receive in Office 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Office 365 handles inbound email that fails DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).</span></span>
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a><span data-ttu-id="29a6b-148">Office 365 からの送信メール用に DMARC を実装する</span><span class="sxs-lookup"><span data-stu-id="29a6b-148">Implement DMARC for outbound mail from Office 365</span></span>
<span data-ttu-id="29a6b-149"><a name="implementDMARCoutbound"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-149"></span></span>

<span data-ttu-id="29a6b-p111">Office 365 を使用しているもののカスタム ドメインを使用していない場合 (つまり、onmicrosoft.com を使用する場合)、組織で DMARC を構成または実装するために、他に行わなければならないことは何もありません。SPF のセットアップはすでに完了しており、Office 365 により自動的に送信メールに DKIM 署名が生成されます。この署名の詳細については「[DKIM と Office 365 の既定の動作](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p111">If you use Office 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Office 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
 <span data-ttu-id="29a6b-p112">カスタム ドメインを所有している場合や、Office 365 に加えてオンプレミスの Exchange サーバーも使用している場合は、送信メール用に手動で DMARC を実装する必要があります。カスタム ドメイン用に DMARC を実装する手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p112">If you have a custom domain or you are using on-premises Exchange servers in addition to Office 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:</span></span> 
  
- [<span data-ttu-id="29a6b-155">手順 1:ドメインに対する有効なメールのソースを特定する</span><span class="sxs-lookup"><span data-stu-id="29a6b-155">Step 1: Identify valid sources of mail for your domain</span></span>](use-dmarc-to-validate-email.md#IdentifyValidSources)
    
- [<span data-ttu-id="29a6b-156">手順 2:Office 365 でドメイン用に SPF をセットアップする</span><span class="sxs-lookup"><span data-stu-id="29a6b-156">Step 2: Set up SPF for your domain in Office 365</span></span>](use-dmarc-to-validate-email.md#ConfigSPF)
    
- [<span data-ttu-id="29a6b-157">手順 3:Office 365 でカスタム ドメイン用に DKIM をセットアップする</span><span class="sxs-lookup"><span data-stu-id="29a6b-157">Step 3: Set up DKIM for your custom domain in Office 365</span></span>](use-dmarc-to-validate-email.md#ConfigDKIM)
    
- [<span data-ttu-id="29a6b-158">手順 4:Office 365 でドメイン用の DMARC TXT レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="29a6b-158">Step 4: Form the DMARC TXT record for your domain in Office 365</span></span>](use-dmarc-to-validate-email.md#CreateDMARCRecord)
    
### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a><span data-ttu-id="29a6b-159">手順 1:ドメインに対する有効なメールのソースを特定する</span><span class="sxs-lookup"><span data-stu-id="29a6b-159">Step 1: Identify valid sources of mail for your domain</span></span>
<span data-ttu-id="29a6b-160"><a name="IdentifyValidSources"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-160"></span></span>

<span data-ttu-id="29a6b-p113">既に SPF のセットアップが済んでいる場合は、この演習を完了していることになります。ただし、DMARC には追加の考慮事項があります。ドメインに対するメールのソースを特定するときには、2 つの問いに答える必要があります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p113">If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:</span></span>
  
- <span data-ttu-id="29a6b-164">どの IP アドレスにドメインからメッセージを送信するか。</span><span class="sxs-lookup"><span data-stu-id="29a6b-164">What IP addresses send messages from my domain?</span></span>
    
- <span data-ttu-id="29a6b-165">自分の代わりにサード パーティから送信されるメールについて、5321.MailFrom ドメインと 5322.From ドメインが一致しているか。</span><span class="sxs-lookup"><span data-stu-id="29a6b-165">For mail sent from third parties on my behalf, will the 5321.MailFrom and 5322.From domains match?</span></span>
    
### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a><span data-ttu-id="29a6b-166">手順 2:Office 365 でドメイン用に SPF をセットアップする</span><span class="sxs-lookup"><span data-stu-id="29a6b-166">Step 2: Set up SPF for your domain in Office 365</span></span>
<span data-ttu-id="29a6b-167"><a name="ConfigSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-167"></span></span>

<span data-ttu-id="29a6b-168">すべての有効な送信者の一覧が用意できると、「[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」の手順を実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-168">Now that you have a list of all your valid senders you can follow the steps to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>
  
<span data-ttu-id="29a6b-169">たとえば、contoso.com が Exchange Online からメールを送信するとします。このとき、オンプレミスの Exchange サーバーの IP アドレスが 192.168.0.1、Web アプリケーションの IP アドレスが 192.168.100.100 だと仮定すると、SPF TXT テキストレコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-169">For example, assuming contoso.com sends mail from Exchange Online, an on-premises Exchange server whose IP address is 192.168.0.1, and a web application whose IP address is 192.168.100.100, the SPF TXT record would look like this:</span></span>
  
```
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

<span data-ttu-id="29a6b-170">ベスト プラクティスとして、SPF TXT レコードでは、サード パーティの送信者についても考慮に入れておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-170">As a best practice, ensure that your SPF TXT record takes into account third-party senders.</span></span>
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a><span data-ttu-id="29a6b-171">手順 3:Office 365 でカスタム ドメイン用に DKIM をセットアップする</span><span class="sxs-lookup"><span data-stu-id="29a6b-171">Step 3: Set up DKIM for your custom domain in Office 365</span></span>
<span data-ttu-id="29a6b-172"><a name="ConfigDKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-172"></span></span>

<span data-ttu-id="29a6b-p114">SPF のセットアップ後には、DKIM をセットアップする必要があります。DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加できます。DKIM をセットアップする代わりに、ドメインに対して Office 365 で既定の DKIM 構成の使用を許可すると、DMARC が失敗することがあります。これは、既定の DKIM 構成が、5322.From アドレスとしてカスタム ドメインではなく初期設定の onmicrosoft.com ドメインを使用するためです。これにより、ドメインから送信されたすべてのメールの 5321.MailFrom アドレスと 5322.From アドレスとの間に不一致が生じることになります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p114">Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Office 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.</span></span>
  
<span data-ttu-id="29a6b-p115">メールを代理で送信するサード パーティの送信者が存在しているときに、そのサード パーティが送信するメールの 5321.MailFrom アドレスと 5322.From アドレスが一致していないと、そのメールに対する DMARC は失敗します。これを回避するには、そのサード パーティの送信者について、具体的にドメインの DKIM をセットアップする必要があります。これにより、このサード パーティのサービスからのメールを Office 365 で認証できるようになります。 ただし、そのようにすると、サード パーティが送信したメールを本人が送信したメールであるかのように検証することを他者 (Yahoo、Gmail、Comcast など) にも許可するようになります。これには、顧客がどこにメールボックスを配置していてもドメインとの信頼を構築できるようになるという利点があります。それと同時に、メッセージはドメインの認証チェックをパスしているため、Office 365 は偽装を理由にメッセージをスパムとしてマークしなくなります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p115">If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Office 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Office 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.</span></span>
  
<span data-ttu-id="29a6b-183">サード パーティの送信者がドメインを偽装できるように DKIM をセットアップする方法を含め、ドメインの DKIM をセットアップする手順については、「[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29a6b-183">For instructions on setting up DKIM for your domain, including how to set up DKIM for third-party senders so they can spoof your domain, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a><span data-ttu-id="29a6b-184">手順 4:Office 365 でドメイン用の DMARC TXT レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="29a6b-184">Step 4: Form the DMARC TXT record for your domain in Office 365</span></span>
<span data-ttu-id="29a6b-185"><a name="CreateDMARCRecord"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-185"></span></span>

<span data-ttu-id="29a6b-p116">ここでは、Office 365 で最もよく使用される構文オプションを示します。ただし、ここに記載されていない別の構文のオプションもあります。ドメイン用の DMARC TXT レコードは、次に示す形式で作成します。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p116">Although there are other syntax options that are not mentioned here, these are the most commonly used options for Office 365. Form the DMARC TXT record for your domain in the format:</span></span>
  
```
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; pct=100; p=policy"
```

<span data-ttu-id="29a6b-188">各部分の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29a6b-188">where:</span></span>
  
- <span data-ttu-id="29a6b-p117">*domain*は、保護するドメインです。既定では、このレコードは、ドメインとすべてのサブドメインからのメールを保護します。たとえば、dmarc.contoso.com を指定\_すると、dmarc は、ドメインおよび housewares.contoso.com や plumbing.contoso.com などのすべてのサブドメインからのメールを保護します。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p117">*domain* is the domain you want to protect. By default, the record protects mail from the domain and all subdomains. For example, if you specify \_dmarc.contoso.com, then DMARC protects mail from the domain and all subdomains, such as housewares.contoso.com or plumbing.contoso.com.</span></span> 
    
- <span data-ttu-id="29a6b-p118">*TTL*は常に1時間に相当する必要があります。TTL に使用される単位は、ドメインのレジストラーに応じて時間 (1 時間)、分 (60 分)、または秒 (3600 秒) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p118">*TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.</span></span> 
    
- <span data-ttu-id="29a6b-194">*pct = 100*は、このルールが電子メールの 100% で使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="29a6b-194">*pct=100* indicates that this rule should be used for 100% of email.</span></span>
    
- <span data-ttu-id="29a6b-p119">\*\* DMARC が失敗した場合に受信側サーバーが従う必要のあるポリシーを指定します。ポリシーは、なし、検疫、または拒否に設定できます。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p119">*policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.</span></span> 
    
<span data-ttu-id="29a6b-197">どのオプションを使用するかについては、「[Office 365 で DMARC を実装する際のベスト プラクティス](use-dmarc-to-validate-email.md#DMARCbestpractices)」の概念をよく理解してください。</span><span class="sxs-lookup"><span data-stu-id="29a6b-197">For information about which options to use, become familiar with the concepts in [Best practices for implementing DMARC in Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).</span></span>
  
<span data-ttu-id="29a6b-198">例:</span><span class="sxs-lookup"><span data-stu-id="29a6b-198">Examples:</span></span>
  
- <span data-ttu-id="29a6b-199">ポリシーをなし (none) に設定する</span><span class="sxs-lookup"><span data-stu-id="29a6b-199">Policy set to none</span></span>
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- <span data-ttu-id="29a6b-200">ポリシーを検疫 (quarantine) に設定する</span><span class="sxs-lookup"><span data-stu-id="29a6b-200">Policy set to quarantine</span></span>
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- <span data-ttu-id="29a6b-201">ポリシーを拒否 (reject) に設定する</span><span class="sxs-lookup"><span data-stu-id="29a6b-201">Policy set to reject</span></span>
  
    ```
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

<span data-ttu-id="29a6b-p120">レコードの作成後には、ドメイン レジストラーでレコードを更新する必要があります。DMARC TXT レコードを Office 365 の DNS レコードに追加する手順の詳細については、「[DNS レコードを管理するときに Office 365 の DNS レコードを作成する](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p120">Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Office 365, see [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span></span>
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a><span data-ttu-id="29a6b-204">Office 365 で DMARC を実装する際のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="29a6b-204">Best practices for implementing DMARC in Office 365</span></span>
<span data-ttu-id="29a6b-205"><a name="DMARCbestpractices"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-205"></span></span>

<span data-ttu-id="29a6b-p121">DMARC は、メール フローの他の部分に影響を与えないように段階的に実装できます。ここに示す手順に従ったロール アウト計画を作成して実施してください。ここに示す各手順は、まずサブドメインに実行します。その後で、その他の各サブドメインに対して実行し、最後に組織のトップレベル ドメインに実行してから、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p121">You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.</span></span>
  
1. <span data-ttu-id="29a6b-209">DMARC の実装による影響を監視する</span><span class="sxs-lookup"><span data-stu-id="29a6b-209">Monitor the impact of implementing DMARC</span></span>
    
    <span data-ttu-id="29a6b-p122">まず、サブドメインまたはドメインに単純な監視モード レコードを使用することから始めます。このレコードでは、そのドメインを使用して確認するメッセージについての統計を送信するように DMARC レシーバーに要求します。監視モード レコードとは、ポリシーをなし (p=none) に設定したDMARC TXT レコードのことです。多くの企業は、p=none の DMARC TXT レコードを発行しています。それより制限の厳しいポリシーを発行することで、どれだけのメールが失われるかについて、明確にはわからないためです。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p122">Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.</span></span> 
    
    <span data-ttu-id="29a6b-p123">これは、メッセージング インフラストラクチャに SPF や DKIM を実装する前でも実行できます。ただし、SPF と DKIM を実装して併用するまでは、DMARC を使用した効果的なメールの検疫や拒否はできません。SPF と DKIM を導入すると、DMARC によって生成されるレポートには、それらのチェックをパスしたメッセージとパスしなかったメッセージの発信元と数が示されます。それらのチェックの適用対象になる (または適用対象にならない) 正当なトラフィックの量を簡単に確認できます。また、あらゆる問題のトラブルシューティングも簡単になります。さらに、どれだけの偽装メッセージが送信されているかや、偽装メッセージの送信元についても、次第にわかるようになります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p123">You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.</span></span>
    
2. <span data-ttu-id="29a6b-218">DMARC に失敗したメールの検疫を外部のメール システムに要求する</span><span class="sxs-lookup"><span data-stu-id="29a6b-218">Request that external mail systems quarantine mail that fails DMARC</span></span>
    
    <span data-ttu-id="29a6b-p124">すべて、または大部分の正当なトラフィックが SPF と DKIM で保護されるという確信が持てるようになり、DMARC の実装による影響を理解したら、検疫ポリシーを実装してください。検疫ポリシーとは、ポリシーを検疫 (p=quarantine) に設定した DMARC TXT レコードのことです。このようにすることで、DMARC レシーバーに対して、DMARC に失敗したドメインからのメッセージを顧客の受信トレイではなく、ローカルのスパム フォルダーと同等のフォルダーに入れるように指示します。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p124">When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.</span></span>
    
3. <span data-ttu-id="29a6b-222">DMARC に失敗したメッセージを受け取らないように外部システムに要求する</span><span class="sxs-lookup"><span data-stu-id="29a6b-222">Request that external mail systems not accept messages that fail DMARC</span></span>
    
    <span data-ttu-id="29a6b-p125">最後の手順は、拒否ポリシーの実装です。拒否ポリシーとは、ポリシーを拒否 (p=reject) に設定した DMARC TXT レコードのことです。これにより、DMARC レシーバーに対して、DMARC チェックに失敗したメッセージを受け取らないように指示します。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p125">The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.</span></span> 
    
## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a><span data-ttu-id="29a6b-226">Office 365 が DMARC に失敗した送信メールを処理する方法</span><span class="sxs-lookup"><span data-stu-id="29a6b-226">How Office 365 handles outbound email that fails DMARC</span></span>
<span data-ttu-id="29a6b-227"><a name="outbounddmarcfail"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-227"></span></span>

<span data-ttu-id="29a6b-p126">メッセージが Office 365 から送信され、DMARC に失敗し、ポリシーが p = quarantine または p = reject に設定されている場合、メッセージは[送信メッセージの高リスク配信プール](high-risk-delivery-pool-for-outbound-messages.md)を経由してルーティングされます。送信メールの上書きはありません。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p126">If a message is outbound from Office 365 and fails DMARC, and you have set the policy to p=quarantine or p=reject, the message is routed through the [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md). There is no override for outbound email.</span></span>
  
<span data-ttu-id="29a6b-p127">DMARC 拒否ポリシー (p=reject) を発行すると、どの顧客も Office 365 ではドメインを偽装できなくなります。メッセージは、サービスを通じたメッセージ送信の中継時に、ドメインの SPF または DKIM をパスできないためです。 ただし、DMARC 拒否ポリシーを発行していても、すべてのメールが Office 365 で認証されている場合、前述の説明どおりに受信メールの一部はスパムとしてのマークが付けられます。それ以外のメールは、SPF を発行していない場合に、サービスを通じて送信を中継するようにしていると拒否されます。 これは、DMARC TXT レコードの作成時に、ドメインの代理としてメールを送信するサーバーの一部の IP アドレスとアプリを含め忘れている場合などに発生します。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p127">If you publish a DMARC reject policy (p=reject), no other customer in Office 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Office 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.</span></span>
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a><span data-ttu-id="29a6b-233">Office 365 が DMARC に失敗した受信メールを処理する方法</span><span class="sxs-lookup"><span data-stu-id="29a6b-233">How Office 365 handles inbound email that fails DMARC</span></span>
<span data-ttu-id="29a6b-234"><a name="inbounddmarcfail"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-234"></span></span>

<span data-ttu-id="29a6b-p128">送信側サーバーの DMARC ポリシーが p=reject の場合、EOP はメッセージを拒否するのではなく、スパムとしてのマークを付けます。つまり、受信メールの場合、Office 365 は p=reject と p=quarantine を同様に扱うということです。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p128">If the DMARC policy of the sending server is p=reject, EOP marks the message as spam instead of rejecting it. In other words, for inbound email, Office 365 treats p=reject and p=quarantine the same way.</span></span>
  
<span data-ttu-id="29a6b-p129">このように Office 365 が構成されている理由は、一部の正当なメールが DMARC に失敗することがあるためです。たとえば、メッセージがメーリング リストに送信されてから、リストのすべての参加者にメッセージが中継される場合、DMARC に失敗することがあります。こうしたメッセージを Office 365 が拒否すると、受信者が正当なメールを失うことになり、そのメールを取得する手段がなくなります。 その代わりに、このようなメッセージは DMARC に失敗するようにしておき、スパムのマークを付けて拒否しないようにします。必要であれば、ユーザーは自分の受信トレイから、次の方法でメッセージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p129">Office 365 is configured like this because some legitimate email may fail DMARC. For example, a message might fail DMARC if it is sent to a mailing list that then relays the message to all list participants. If Office 365 rejected these messages, people could lose legitimate email and have no way to retrieve it. Instead, these messages will still fail DMARC but they will be marked as spam and not rejected. If desired, users can still get these messages in their inbox through these methods:</span></span>
  
- <span data-ttu-id="29a6b-242">ユーザーが、自分のメール クライアントを使用して、個別に安全な送信者を追加する</span><span class="sxs-lookup"><span data-stu-id="29a6b-242">Users add safe senders individually by using their email client</span></span>
    
- <span data-ttu-id="29a6b-243">管理者は、特定の送信者に対してメッセージを許可するすべてのユーザーに対して Exchange メールフロールール (トランスポートルールとも呼ばれます) を作成します。</span><span class="sxs-lookup"><span data-stu-id="29a6b-243">Administrators create an Exchange mail flow rule (also known as a transport rule) for all users that allows messages for those particular senders.</span></span> 
    
## <a name="troubleshooting-your-dmarc-implementation"></a><span data-ttu-id="29a6b-244">DMARC 実装のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="29a6b-244">Troubleshooting your DMARC implementation</span></span>
<span data-ttu-id="29a6b-245"><a name="dmarctroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-245"></span></span>

<span data-ttu-id="29a6b-246">ドメインの MX レコードを構成したときに、最初のエントリを EOP 以外にすると、DMARC の失敗はドメインに強制されなくなります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-246">If you have configured your domain's MX records where EOP is not the first entry, DMARC failures will not be enforced for your domain.</span></span> 
  
<span data-ttu-id="29a6b-p130">Office 365 のお客様でも、ドメインのプライマリ MX レコードが EOP を指していないと、DMARC による利点は得られなくなります。たとえば、MX レコードがオンプレミスのメール サーバーを指していて、コネクタを使用することで EOP にメールをルーティングしていると、DMARC は機能しなくなります。このシナリオでは、受信側ドメインは認証済みドメインのいずれかになりますが、EOP はプライマリ MX ではありません。たとえば、contoso.com がそれ自体の MX をポイントしていて、セカンダリ MX レコードとして EOP を使用しているとすると、contoso.com の MX レコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p130">If you're an Office 365 customer, and your domain's primary MX record does not point to EOP, you will not get the benefits of DMARC. For example, DMARC won't work if you point the MX record to your on-premises mail server and then route email to EOP by using a connector. In this scenario, the receiving domain is one of your Accepted-Domains but EOP is not the primary MX. For example, suppose contoso.com points its MX at itself and uses EOP as a secondary MX record, contoso.com's MX record looks like the following:</span></span>
  
```
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

<span data-ttu-id="29a6b-p131">すべて、またはほとんどの電子メールは、プライマリ MX であるため、最初に mail.contoso.com にルーティングされ、その後、EOP にルーティングされます。場合によっては、MX レコードとして EOP を一覧表示し、単にメールをルーティングするためにコネクタを接続するだけでもかまいません。EOP は、DMARC 検証を実行するための最初のエントリである必要はありません。すべてのオンプレミス/O365 サーバーが DMARC チェックを行うことができないため、検証を確実にするだけです。 DMARC は、DMARC TXT レコードを設定するときに、顧客のドメインに対して適用する資格がありますが、実際に実行するのは受信側のサーバーである必要があります。 受信側のサーバーとして EOP を設定した場合、EOP は DMARC 強制を行います。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p131">All, or most, email will first be routed to mail.contoso.com since it's the primary MX, and then mail will get routed to EOP. In some cases, you might not even list EOP as an MX record at all and simply hook up connectors to route your email. EOP does not have to be the first entry for DMARC validation to be done. It just ensures the validation, as we cannot be certain that all on-premise/non-O365 servers will do DMARC checks.  DMARC is eligible to be enforced for a customer’s domain (not server) when you set up the DMARC TXT record, but it is up to the receiving server to actually do the enforcement.  If you set up EOP as the receiving server, then EOP does the DMARC enforcement.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="29a6b-257">詳細情報</span><span class="sxs-lookup"><span data-stu-id="29a6b-257">For more information</span></span>
<span data-ttu-id="29a6b-258"><a name="sectionSection8"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-258"></span></span>

<span data-ttu-id="29a6b-p132">DMARC の詳細情報が必要ですか。以下のリソースが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="29a6b-p132">Want more information about DMARC? These resources can help.</span></span>
  
- <span data-ttu-id="29a6b-261">[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md) には、Office 365 が DMARC チェックに使用する構文とヘッダー フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="29a6b-261">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DMARC checks.</span></span> 
    
- <span data-ttu-id="29a6b-262">M[3](https://www.m3aawg.org/activities/training/dmarc-training-series)AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group) の「<sup>DMARC TRAINING SERIES</sup>」</span><span class="sxs-lookup"><span data-stu-id="29a6b-262">Take the [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) from M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).</span></span>
    
- <span data-ttu-id="29a6b-263">[dmarcian](https://space.dmarcian.com/deployment/) のチェックリストを使用する。</span><span class="sxs-lookup"><span data-stu-id="29a6b-263">Use the checklist at [dmarcian](https://space.dmarcian.com/deployment/).</span></span>
    
- <span data-ttu-id="29a6b-264">[DMARC.org](https://dmarc.org) のソースに直接アクセスする。</span><span class="sxs-lookup"><span data-stu-id="29a6b-264">Go directly to the source at [DMARC.org](https://dmarc.org).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="29a6b-265">See also</span><span class="sxs-lookup"><span data-stu-id="29a6b-265">See also</span></span>
<span data-ttu-id="29a6b-266"><a name="sectionSection8"> </a></span><span class="sxs-lookup"><span data-stu-id="29a6b-266"></span></span>

[<span data-ttu-id="29a6b-267">Office 365 で Sender Policy Framework (SPF) を使用してスプーフィングを防止する方法</span><span class="sxs-lookup"><span data-stu-id="29a6b-267">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[<span data-ttu-id="29a6b-268">スプーフィングを防止するために Office 365 で SPF を設定する</span><span class="sxs-lookup"><span data-stu-id="29a6b-268">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[<span data-ttu-id="29a6b-269">DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する</span><span class="sxs-lookup"><span data-stu-id="29a6b-269">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md)

