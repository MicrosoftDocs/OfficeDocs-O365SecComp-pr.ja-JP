---
title: Office 365 において Sender Policy Framework (SPF) を使用して、スプーフィングを防止する方法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/15/2016
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
description: '概要: この記事では、Office 365 において、Sender Policy Framework (SPF) TXT レコードを DNS で使用して、カスタム ドメインから送信されたメッセージを送信先のメール システムが信頼するようにする方法を説明します。これは、Office 365 から送信された送信メールに適用されます。Office 365 から Office 365 内の受信者に送信されたメッセージは、常に SPF チェックに合格します。'
ms.openlocfilehash: aea7f740a67ce282424efc409d25f3f135546ada
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026464"
---
# <a name="how-office-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="04d7c-105">Office 365 において Sender Policy Framework (SPF) を使用して、スプーフィングを防止する方法</span><span class="sxs-lookup"><span data-stu-id="04d7c-105">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

 <span data-ttu-id="04d7c-p102">**概要:** この記事では、Office 365 において、Sender Policy Framework (SPF) TXT レコードを DNS で使用して、カスタム ドメインから送信されたメッセージを送信先のメール システムが信頼するようにする方法を説明します。これは、Office 365 から送信された送信メールに適用されます。Office 365 から Office 365 内の受信者に送信されたメッセージは、常に SPF チェックに合格します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p102">**Summary:** This article describes how Office 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain. This applies to outbound mail sent from Office 365. Messages sent from Office 365 to a recipient within Office 365 will always pass SPF.</span></span> 
  
<span data-ttu-id="04d7c-p103">SPF TXT レコードは、DNS 形式のレコードです。SPF TXT レコードで、メール メッセージの送信元のドメイン名を確認すると、スプーフィングやフィッシングの防止に役立ちます。SPF は、送信者の IP アドレスを、送信側ドメインの所有者とされる名前と照合して、メール メッセージの発信元を確認します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p103">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent. SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="04d7c-p104">SPF レコードの種類は、2014 年にインターネット技術標準化委員会 (IETF) によって廃止されました。代わりに、SPF 情報を公開するには、DNS で TXT レコードを必ず使用してください。この記事の以降の部分では、わかりやすいように SPF TXT レコードという用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p104">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014. Instead, ensure that you use TXT records in DNS to publish your SPF information. The rest of this article uses the term SPF TXT record for clarity.</span></span> 
  
<span data-ttu-id="04d7c-p105">ドメイン管理者は DNS の TXT レコードで SPF 情報を公開します。この SPF 情報は、承認された送信メール サーバーを識別します。送信先メール システムにより、承認された送信メール サーバーからメッセージが発信されたことが確認されます。SPF について既に理解している、または単純な展開を使っていて、Office 365 用に DNS で SPF TXT レコードに含めるものを知りたいだけの場合は、[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) に進んでください。Office 365 で完全にホストされた展開を使っていない場合、または SPF のしくみや Office 365 の SPF についてトラブルシューティングを行う方法について詳しい情報が必要な場合は、このまま読み進めてください。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p105">Domain administrators publish SPF information in TXT records in DNS. The SPF information identifies authorized outbound email servers. Destination email systems verify that messages originate from authorized outbound email servers. If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Office 365, you can go to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). If you do not have a deployment that is fully-hosted in Office 365, or you want more information about how SPF works or how to troubleshoot SPF for Office 365, keep reading.</span></span>
  
> [!NOTE]
> <span data-ttu-id="04d7c-p106">以前は、SharePoint Online も使用している場合、カスタム ドメインに別の SPF TXT レコードを追加する必要がありました。この作業を行う必要はなくなりました。この変更により、SharePoint Online の通知メッセージが [迷惑メール] フォルダーに振り分けられるリスクが軽減されます。直ちに変更を行う必要はありませんが、"参照が多すぎます" というエラーが発生する場合は、[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) に記載されているように SPF TXT レコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p106">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> 
     
## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-office-365"></a><span data-ttu-id="04d7c-123">Office 365 において SPF がスプーフィングとフィッシングを防ぐしくみ</span><span class="sxs-lookup"><span data-stu-id="04d7c-123">How SPF works to prevent spoofing and phishing in Office 365</span></span>
<span data-ttu-id="04d7c-124"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-124"></span></span>

<span data-ttu-id="04d7c-p107">SPF は、送信者がドメインの代理として送信することを許可されているかどうかを判断します。送信者がこの操作を許可されていない場合、つまり、受信側のサーバーで電子メールの SPF チェックが失敗した場合は、そのサーバー上で構成されたスパム ポリシーが、メッセージについて行う処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p107">SPF determines whether or not a sender is permitted to send on behalf of a domain. If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>
  
<span data-ttu-id="04d7c-p108">各 SPF TXT レコードには次の 3 つの部分があります。SPF TXT レコードである宣言、自分のドメインおよび自分のドメインの代理として送信できる外部ドメインからのメール送信を許可されている IP アドレス、強制ルールです。有効な SPF TXT レコードには 3 つすべてが必要です。この記事では、SPF TXT レコードを形成する方法について説明し、Office 365 のサービスを操作するためのベスト プラクティスを提供します。ドメイン レジストラーを操作してレコードを DNS に発行するための手順へのリンクも用意されています。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p108">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule. You need all three in a valid SPF TXT record. This article describes how you form your SPF TXT record and provides best practices for working with the services in Office 365. Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>
  
### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="04d7c-131">SPF の基本: カスタム ドメインからの送信が許可された IP アドレス</span><span class="sxs-lookup"><span data-stu-id="04d7c-131">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="04d7c-132"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-132"></span></span>

<span data-ttu-id="04d7c-133">SPF ルールの基本的な構文を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="04d7c-133">Take a look at the basic syntax for an SPF rule:</span></span>
  
<span data-ttu-id="04d7c-134">v=spf1 \<IP\> \<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="04d7c-134">v=spf1 \<IP\> \<enforcement rule\></span></span>
  
<span data-ttu-id="04d7c-135">たとえば、contoso.com に対して次の SPF ルールが存在するとします。</span><span class="sxs-lookup"><span data-stu-id="04d7c-135">For example, let's say the following SPF rule exists for contoso.com:</span></span>
  
<span data-ttu-id="04d7c-136">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="04d7c-136">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>
  
<span data-ttu-id="04d7c-137">この例では、SPF ルールは、ドメイン contoso.com について、これらの IP アドレスからのメールのみを受け入れるように受信電子メール サーバーに指示します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-137">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>
  
- <span data-ttu-id="04d7c-138">IP アドレス #1</span><span class="sxs-lookup"><span data-stu-id="04d7c-138">IP address #1</span></span>
    
- <span data-ttu-id="04d7c-139">IP アドレス #2</span><span class="sxs-lookup"><span data-stu-id="04d7c-139">IP address #2</span></span>
    
- <span data-ttu-id="04d7c-140">IP アドレス #3</span><span class="sxs-lookup"><span data-stu-id="04d7c-140">IP address #3</span></span>
    
<span data-ttu-id="04d7c-p109">この SPF ルールは受信メール サーバーに、メッセージが contoso.com からのものであるものの、これら 3 つの IP アドレスのいずれからのものでもない場合、受信側サーバーはメッセージに対して強制ルールを適用する必要があることを指示します。通常、強制ルールは次のオプションのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p109">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message. The enforcement rule is usually one of these options:</span></span>
  
- <span data-ttu-id="04d7c-p110">**Hard fail。** メッセージ エンベロープ内に 'hard fail' を含むメッセージをマークし、受信側サーバーでこの種類のメッセージに対して構成されたスパム ポリシーに従います。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p110">**Hard fail.** Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span> 
    
- <span data-ttu-id="04d7c-p111">**Soft fail。** メッセージ エンベロープ内に 'soft fail' を含むメッセージをマークします。通常、電子メール サーバーはこれらのメッセージを配信するように構成されます。ほとんどのエンド ユーザーには、このマークは表示されません。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p111">**Soft fail.** Mark the message with 'soft fail' in the message envelope. Typically, email servers are configured to deliver these messages anyway. Most end users do not see this mark.</span></span> 
    
- <span data-ttu-id="04d7c-p112">**Neutral。** 何もしません。つまり、メッセージ エンベロープをマークしません。通常、これはテスト用に予約されているものであり、ほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p112">**Neutral.** Do nothing, that is, do not mark the message envelope. This is usually reserved for testing purposes and is rarely used.</span></span> 
    
<span data-ttu-id="04d7c-p113">次の例は、さまざまな状況での SPF のしくみを示しています。これらの例では、contoso.com は送信者、woodgrovebank.com は受信者です。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p113">The following examples show how SPF works in different situations. In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>
  
### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="04d7c-154">例 1:送信者から受信者に直接送信されるメッセージの電子メール認証</span><span class="sxs-lookup"><span data-stu-id="04d7c-154">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="04d7c-155"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-155"></span></span>

<span data-ttu-id="04d7c-156">SPF は、送信者から受信者へのパスが直接パスである場合に最適に機能します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-156">SPF works best when the path from sender to receiver is direct, for example:</span></span>
  
![サーバーからサーバーへ直接送信されるときに SPF がメールを認証する方法を示す図。](media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)
  
<span data-ttu-id="04d7c-158">Woodgrovebank.com がメッセージを受け取る際に、IP アドレス # 1 が contoso.com の SPF TXT レコードにある場合は、メッセージは SPF チェックに合格し認証されます。</span><span class="sxs-lookup"><span data-stu-id="04d7c-158">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>
  
### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="04d7c-159">例 2:偽装された送信者のアドレスが SPF チェックに失敗する</span><span class="sxs-lookup"><span data-stu-id="04d7c-159">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="04d7c-160"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-160"></span></span>

<span data-ttu-id="04d7c-161">フィッシャーが contoso.com を偽装する方法を見つけたとします。</span><span class="sxs-lookup"><span data-stu-id="04d7c-161">Suppose a phisher finds a way to spoof contoso.com:</span></span>
  
![偽装しているサーバーから送信されるときに SPF がメールを認証する方法を示す図。](media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)
  
<span data-ttu-id="04d7c-163">IP アドレス #12 は contoso.com の SPF TXT レコードにないため、メッセージは SPF チェックに失敗し、受信者はそのメッセージをスパムとしてマークすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="04d7c-163">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>
  
### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="04d7c-164">例 3:SPF と転送されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="04d7c-164">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="04d7c-165"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-165"></span></span>

<span data-ttu-id="04d7c-p114">SPF の欠点の 1 つは、メールが転送されたときには機能しないことです。たとえば、woodgrovebank.com のユーザーが、outlook.com アカウントにすべての電子メールを送信する転送ルールを設定しているとします。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p114">One drawback of SPF is that it doesn't work when an email has been forwarded. For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>
  
![電子メール メッセージが転送される際に SPF がメールを認証できないことを示す図。](media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)
  
<span data-ttu-id="04d7c-p115">メッセージは当初は、woodgrovebank.com で SPF チェックに合格しますが、IP #25 が contoso.com の SPF TXT レコードにないため、outlook.com では SPF チェックが失敗します。このため、Outlook.com はメッセージをスパムとしてマークする可能性があります。この問題を回避するには、SPF を DKIM や DMARC などの他の電子メールの認証方法と組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p115">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record. Outlook.com might then mark the message as spam. To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>
  
### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="04d7c-172">SPF の基本:自分のドメインに代わってメールを送信できるサード パーティのドメインを含める</span><span class="sxs-lookup"><span data-stu-id="04d7c-172">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="04d7c-173"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-173"></span></span>

<span data-ttu-id="04d7c-p116">IP アドレスに加えて、送信者としてドメインを含めるように SPF TXT レコードを構成することもできます。これらは、"include" ステートメントとして SPF TXT レコードに追加されます。たとえば、contoso.com には、所有する contoso.net と contoso.org からメール サーバーのすべての IP アドレスを含めることもできます。これを行うには、contoso.com は次のような SPF TXT レコードを発行します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p116">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders. These are added to the SPF TXT record as "include" statements. For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns. To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>
  
```
IN TXT "v=spf1 include:contoso.net include:contoso.org -all"
```

<span data-ttu-id="04d7c-p117">受信側サーバーが DNS にこのレコードを確認するときには、SPF TXT レコード上で contoso.net、contoso.org に対して順に DNS 参照も実行します。contoso.net または contoso.org のレコード内に追加の include ステートメントが検出された場合は、それらにも従います。 サービス拒否攻撃を防止するための、1 つの電子メール メッセージに対する DNS 参照の最大数は 10 です。各 include ステートメントは追加の DNS 参照を表します。メッセージが上限 10 を超えると、メッセージは SPF チェックに失敗します。メッセージがこの制限に達すると、受信側サーバーの構成方法に応じて、送信者は、メッセージが生成した "参照数が多すぎます"、または "メッセージの最大ホップ数を超えています" というメッセージを受け取る可能性があります。この問題を回避する方法のヒントについては、「[トラブルシューティング:Office 365 における SPF のベスト プラクティス](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p117">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too. In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10. Each include statement represents an additional DNS lookup. If a message exceeds the 10 limit, the message fails SPF. Once a message reaches this limit, depending on the way the receiving server is configured, the sender may receive a message that states that the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded". For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>
  
## <a name="requirements-for-your-spf-txt-record-and-office-365"></a><span data-ttu-id="04d7c-184">SPF TXT レコードと Office 365 の要件</span><span class="sxs-lookup"><span data-stu-id="04d7c-184">Requirements for your SPF TXT record and Office 365</span></span>
<span data-ttu-id="04d7c-185"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-185"></span></span>

<span data-ttu-id="04d7c-p118">Office 365 をセットアップする際にメールをセットアップすると、既に SPF TXT レコードを作成したことになります。この SPF TXT レコードが、Microsoft メッセージング サーバーを自分のドメインの正当なメールの送信元として識別します。このレコードはおそらく次のようになります。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p118">If you set up mail when you set up Office 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain. This record probably looks like this:</span></span>
  
```
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="04d7c-188">完全にホストされている Office 365 のユーザーである場合 (つまり、送信メールを送信するオンプレミスのメール サーバーを使用していない)、これが Office 365 用に発行する必要のある唯一の SPF TXT レコードになります。</span><span class="sxs-lookup"><span data-stu-id="04d7c-188">If you're a fully-hosted Office 365 customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>
  
<span data-ttu-id="04d7c-189">ハイブリッド展開を構成している (つまり、メールボックスの一部はオンプレミスであり、他は Office 365 でホストされている) 場合や、スタンドアロンの Exchange Online Protection (EOP) を利用しているユーザーである (つまり、組織で EOP を使用してオンプレミスのメールボックスを保護している) 場合には、オンプレミスの各エッジ メール サーバーの送信 IP アドレスを DNS の SPF TXT レコードに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04d7c-189">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Office 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>
  
## <a name="form-your-spf-txt-record-for-office-365"></a><span data-ttu-id="04d7c-190">Office 365 のための SPF TXT レコードの形成</span><span class="sxs-lookup"><span data-stu-id="04d7c-190">Form your SPF TXT record for Office 365</span></span>
<span data-ttu-id="04d7c-191"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-191"></span></span>

<span data-ttu-id="04d7c-p119">この記事に記載されている構文の情報を使って、カスタム ドメイン用の SPF TXT レコードを形成します。ここに記載されていない他の構文オプションもありますが、これらが最もよく使うオプションです。レコードを形成した後は、ドメイン レジストラーでレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p119">Use the syntax information in this article to form the SPF TXT record for your custom domain. Although there are other syntax options that are not mentioned here, these are the most commonly used options. Once you have formed your record, you need to update the record at your domain registrar.</span></span>
  
<span data-ttu-id="04d7c-p120">Office 365 用に含める必要のあるドメインの詳細については、「[SPF に必要な外部 DNS レコード](https://support.office.com/en-us/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US)」を参照してください。ドメイン レジストラーの SPF (TXT) レコードを更新するには、「[詳細な手順](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404)」を参照してください。レジストラーが一覧にない場合、それぞれに個別に連絡して、レコードを更新する方法を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p120">For information about the domains you will need to include for Office 365, see [External DNS records required for SPF](https://support.office.com/en-us/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US). Use the [step-by-step instructions](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404) for updating SPF (TXT) records for your domain registrar. If your registrar is not listed, you will need to contact them separately to learn how to update your record.</span></span> 
  
### <a name="spf-txt-record-syntax-for-office-365"></a><span data-ttu-id="04d7c-198">Office 365 用の SPF TXT レコードの構文</span><span class="sxs-lookup"><span data-stu-id="04d7c-198">SPF TXT record syntax for Office 365</span></span>
<span data-ttu-id="04d7c-199"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-199"></span></span>

<span data-ttu-id="04d7c-200">Office 365 用の標準的な SPF TXT レコードには次の構文があります。</span><span class="sxs-lookup"><span data-stu-id="04d7c-200">A typical SPF TXT record for Office 365 has the following syntax:</span></span>
  
```
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="04d7c-201">たとえば、</span><span class="sxs-lookup"><span data-stu-id="04d7c-201">For example:</span></span>
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="04d7c-202">ここで</span><span class="sxs-lookup"><span data-stu-id="04d7c-202">where:</span></span>
  
- <span data-ttu-id="04d7c-p121">**v=spf1** は必須です。これは、SPF TXT レコードとして TXT レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p121">**v=spf1** is required. This defines the TXT record as an SPF TXT record.</span></span> 
    
- <span data-ttu-id="04d7c-p122">**ip4** は、IP バージョン 4 のアドレスを使用していることを示します。 **ip6** は、IP バージョン 6 のアドレスを使用していることを示します。IPv6 の IP アドレスを使用している場合は、この記事の例の **ip4** を **ip6** に置き換えます。CIDR 表記を使用して IP アドレス範囲を指定することもできます (たとえば、 **ip4:192.168.0.1/26**)。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p122">**ip4** indicates that you are using IP version 4 addresses. **ip6** indicates that you are using IP version 6 addresses. If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article. You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>
    
-  <span data-ttu-id="04d7c-p123">_IP address_ は、SPF TXT レコードに追加する IP アドレスです。通常、これは組織の送信メール サーバーの IP アドレスです。複数の送信メール サーバーを一覧表示できます。詳細については、「 [例: 複数のオンプレミスの送信メール サーバーと Office 365 のための SPF TXT レコード](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p123">_IP address_ is the IP address that you want to add to the SPF TXT record. Usually, this is the IP address of the outbound mail server for your organization. You can list multiple outbound mail servers. For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>
    
-  <span data-ttu-id="04d7c-p124">_domain name_ は、正当な送信者として追加するドメインです。Office 365 用に含める必要のあるドメイン名の一覧については、「 [SPF に必要な外部 DNS レコード](https://support.office.com/en-us/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p124">_domain name_ is the domain you want to add as a legitimate sender. For a list of domain names you should include for Office 365, see [External DNS records required for SPF](https://support.office.com/en-us/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
    
- <span data-ttu-id="04d7c-215">通常、強制ルールは次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="04d7c-215">Enforcement rule is usually one of the following:</span></span>
    
  - <span data-ttu-id="04d7c-216">-all</span><span class="sxs-lookup"><span data-stu-id="04d7c-216">-all</span></span>
    
    <span data-ttu-id="04d7c-p125">hard fail を示します。ドメインに対するすべての承認済みの IP アドレスが既知の場合は、SPF TXT レコードにそれらを一覧表示して、-all (hard fail) 修飾子を使用します。また、SPF のみを使用している場合、つまり、DMARC または DKIM のいずれも使用していない場合は、-all 修飾子を使用する必要もあります。常にこの修飾子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p125">Indicates hard fail. If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier. Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier. We recommend that you use always this qualifier.</span></span>
    
  - <span data-ttu-id="04d7c-221">~all</span><span class="sxs-lookup"><span data-stu-id="04d7c-221">~all</span></span>
    
    <span data-ttu-id="04d7c-p126">soft fail を示します。一覧に IP アドレスのすべてが網羅されているかどうかがわからない場合は、~all (soft fail) 修飾子を使用してください。また、p=quarantine または p=reject と共に DMARC を使用している場合も、~all を使用できます。それ以外の場合は、-all を使用します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p126">Indicates soft fail. If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier. Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all. Otherwise, use -all.</span></span>
    
  - <span data-ttu-id="04d7c-226">?all</span><span class="sxs-lookup"><span data-stu-id="04d7c-226">?all</span></span>
    
    <span data-ttu-id="04d7c-p127">neutral を示します。SPF のテスト時に使用されます。実際の展開でこの修飾子を使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p127">Indicates neutral. This is used when testing SPF. We do not recommend that you use this qualifier in your live deployment.</span></span>
    
### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-office-365"></a><span data-ttu-id="04d7c-230">例: すべてのメールを Office 365 で送信する場合に使用する SPF TXT レコード</span><span class="sxs-lookup"><span data-stu-id="04d7c-230">Example: SPF TXT record to use when all of your mail is sent by Office 365</span></span>
<span data-ttu-id="04d7c-231"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-231"></span></span>

<span data-ttu-id="04d7c-232">すべてのメールを Office 365 で送信する場合は、これを SPF TXT レコードで使用します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-232">If all of your mail is sent by Office 365, use this in your SPF TXT record:</span></span>
  
```
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-office-365"></a><span data-ttu-id="04d7c-233">例: 1 つのオンプレミスの Exchange Server と Office 365 を使用したハイブリッド シナリオの SPF TXT レコード</span><span class="sxs-lookup"><span data-stu-id="04d7c-233">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Office 365</span></span>
<span data-ttu-id="04d7c-234"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-234"></span></span>

<span data-ttu-id="04d7c-235">ハイブリッド環境で、オンプレミスの Exchange Server の IP アドレスが 192.168.0.1 である場合、SPF の強制ルールを hard fail に設定するために、SPF TXT レコードを次のように形成します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-235">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>
  
```
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-office-365"></a><span data-ttu-id="04d7c-236">例: 複数のオンプレミスの送信メール サーバーと Office 365 のための SPF TXT レコード</span><span class="sxs-lookup"><span data-stu-id="04d7c-236">Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365</span></span>
<span data-ttu-id="04d7c-237"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-237"></span></span>

<span data-ttu-id="04d7c-p128">複数の送信メール サーバーがある場合は、各メール サーバーの IP アドレスを、スペースの後に "ip4:" ステートメントを付けて区切り、SPF TXT レコードに追加します。たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p128">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement. For example:</span></span>
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-office-365"></a><span data-ttu-id="04d7c-240">次の手順: Office 365 に SPF をセットアップする</span><span class="sxs-lookup"><span data-stu-id="04d7c-240">Next steps: Set up SPF for Office 365</span></span>
<span data-ttu-id="04d7c-241"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-241"></span></span>

<span data-ttu-id="04d7c-242">SPF TXT レコードを形成した後は、「[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」にある手順に従って SPF TXT レコードをドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-242">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span> 
  
<span data-ttu-id="04d7c-p129">SPF は、スプーフィングを防止するために設計されていますが、SPF で防御できないスプーフィングの手法があります。これらから保護するために、SPF をセットアップすると、Office 365 用に DKIM と DMARC も構成する必要があります。始めるには「[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。次に、「[DMARC を使用して Office 365 でメールを検証する](use-dmarc-to-validate-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p129">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
  
## <a name="troubleshooting-best-practices-for-spf-in-office-365"></a><span data-ttu-id="04d7c-247">トラブルシューティング:Office 365 における SPF のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="04d7c-247">Troubleshooting: Best practices for SPF in Office 365</span></span>
<span data-ttu-id="04d7c-248"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-248"></span></span>

<span data-ttu-id="04d7c-p130">カスタム ドメインに作成できる SPF TXT レコードは 1 つのみです。複数のレコードを作成すると、ラウンド ロビン状況の原因となり、SPF が失敗します。これを避けるために、各サブドメインに対して個別にレコードを作成できます。たとえば、contoso.com に 1 つのレコードを作成し、bulkmail.contoso.com に別のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p130">You can only create one SPF TXT record for your custom domain. Creating multiple records causes a round robin situation and SPF will fail. To avoid this, you can create separate records for each subdomain. For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>
  
<span data-ttu-id="04d7c-p131">電子メール メッセージが配信される前に 10 を超える DNS 参照が行われると、受信側のメール サーバーが  _permerror_ とも呼ばれる永続的なエラーで応答するため、メッセージが SPF チェックに失敗する原因となります。また、受信側のサーバーは、次のようなエラーを含む配信不能レポート (NDR) で応答することもあります。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p131">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check. The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>
  
- <span data-ttu-id="04d7c-255">メッセージのホップ数を超えました。</span><span class="sxs-lookup"><span data-stu-id="04d7c-255">The message exceeded the hop count.</span></span>
    
- <span data-ttu-id="04d7c-256">メッセージに必要な参照数が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="04d7c-256">The message required too many lookups.</span></span>
    
## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-office-365"></a><span data-ttu-id="04d7c-257">Office 365 でサード パーティのドメインを使用する場合の "参照が多すぎます" エラーを回避する</span><span class="sxs-lookup"><span data-stu-id="04d7c-257">Avoiding the "too many lookups" error when you use third-party domains with Office 365</span></span>
<span data-ttu-id="04d7c-258"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-258"></span></span>

<span data-ttu-id="04d7c-p132">サード パーティのドメインの SPF TXT レコードには、受信側のサーバーに多数の DNS 参照を実行するよう指示するものがあります。たとえば、この記事の執筆時には、Salesforce.com のレコードに 5 つの include ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p132">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups. For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>
  
```
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="04d7c-p133">エラーを回避するために、(たとえばバルク メールを送信する) あらゆるユーザーがサブドメインを使用する必要があるというポリシーを、特にこの目的のために実装できます。次にバルク メールを含むサブドメイン用の別の SPF TXT レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p133">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose. You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>
  
 <span data-ttu-id="04d7c-p134">salesforce.com の例などのように、SPF TXT レコードでドメインを使用する必要がある場合がありますが、サードパーティがこの目的のためにユーザーの使用するサブドメインを既に作成している場合もあります。たとえば、exacttarget.com は、SPF TXT レコードに対して使用する必要があるサブドメインを作成しました。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p134">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose. For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span> 
  
```
cust-spf.exacttarget.com
```

<span data-ttu-id="04d7c-265">SPF TXT レコードにサード パーティのドメインを含む場合は、参照の上限値 10 に達することを回避するために、どのドメインまたはサブドメインを使用するかを、サードパーティに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04d7c-265">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>
  
## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="04d7c-266">現在の SPF TXT レコードを表示し、それに必要な参照数を決定する方法</span><span class="sxs-lookup"><span data-stu-id="04d7c-266">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="04d7c-267"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-267"></span></span>

<span data-ttu-id="04d7c-p135">nslookup を使用して、SPF TXT レコードなどの DNS レコードを表示できます。また、ご希望に応じて、無料のオンライン ツールを多数入手し、SPF TXT レコードの内容を表示することもできます。SPF TXT を参照し、一連の include ステートメントとリダイレクトに従って、レコードが必要とする DNS 参照数を判断できます。オンライン ツールには、これらの参照数をカウントして表示するものもあります。この数を継続的に追跡することで、組織から送信されたメッセージが、受信側のサーバーからの permerror と呼ばれる永続的なエラーの要因にならないようにできます。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p135">You can use nslookup to view your DNS records, including your SPF TXT record. Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record. By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires. Some online tools will even count and display these lookups for you. Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="04d7c-273">詳細情報</span><span class="sxs-lookup"><span data-stu-id="04d7c-273">For more information</span></span>
<span data-ttu-id="04d7c-274"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="04d7c-274"></span></span>

<span data-ttu-id="04d7c-p136">SPF TXT レコードの追加についてヘルプが必要ですか?一般的な種々のドメイン レジストラーで SPF (TXT) レコードを更新するには、「[DNS レコードの管理時に Office 365 の DNS レコードを作成する](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404)」を参照してください。[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md) には、Office 365 が SPF チェックに使用する構文とヘッダー フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="04d7c-p136">Need help adding the SPF TXT record? [Step-by-step instructions](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404) for updating SPF (TXT) records at a variety of popular domain registrars is available. [Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for SPF checks.</span></span> 
  

