---
title: Office 365 でのスプーフィング対策保護
ms.author: tracyp
author: MSFTtracyp
manager: laurawi
ms.date: 3/6/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: この記事では、Office 365 で、偽造された送信者ドメイン (スプーフィングされたドメイン) を使用するフィッシング攻撃を軽減する方法について説明します。 これは、メッセージを分析して、標準の電子メール認証の方法や、その他の送信者評価の手法を使用して認証できないメッセージをブロックすることで実現します。 今回の変更は、Office 365 の組織が対象になるフィッシング攻撃の数を減らすために実装されました。
ms.openlocfilehash: 00cf4d6ba0fe7bc9bc081466d7b23a8a9b75631e
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2019
ms.locfileid: "30936797"
---
# <a name="anti-spoofing-protection-in-office-365"></a><span data-ttu-id="82616-105">Office 365 でのスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="82616-105">Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="82616-106">この記事では、Office 365 で、偽造された送信者ドメイン (スプーフィングされたドメイン) を使用するフィッシング攻撃を軽減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="82616-106">This article describes how Office 365 mitigates against phishing attacks that use forged sender domains, that is, domains that are spoofed.</span></span> <span data-ttu-id="82616-107">これは、メッセージを分析して、標準の電子メール認証方法や、その他の送信者評価の手法を使用して認証できないメッセージをブロックすることで実現します。</span><span class="sxs-lookup"><span data-stu-id="82616-107">It accomplishes this by analyzing the messages and blocking the ones that cannot be authenticated using standard email authentication methods, nor other sender reputation techniques.</span></span> <span data-ttu-id="82616-108">今回の変更は、Office 365 の組織が対象になるフィッシング攻撃の数を減らすために実装されました。</span><span class="sxs-lookup"><span data-stu-id="82616-108">This change was implemented to reduce the number of phishing attacks to which organizations in Office 365 are exposed.</span></span>
  
<span data-ttu-id="82616-109">この記事では、今回の変更が実施された理由、今回の変更に対応するように準備する方法、影響を受けるメッセージの表示方法、メッセージに関するレポートの作成方法、誤検出を減らす方法、および Microsoft への送信者が今回の変更にどのように備えるべきかについても説明します。</span><span class="sxs-lookup"><span data-stu-id="82616-109">This article also describes why this change is being made, how customers can prepare for this change, how to view messages that will be affected, how to report on messages, how to mitigate false positives, as well as how senders to Microsoft should prepare for this change.</span></span>
  
<span data-ttu-id="82616-110">Microsoft のスプーフィング対策テクノロジは、最初に Office 365 Enterprise E5 サブスクリプションを所有する組織、またはサブスクリプションに対応する Office 365 Advanced Threat Protection (ATP) アドオンを購入した組織に導入されました。</span><span class="sxs-lookup"><span data-stu-id="82616-110">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span> <span data-ttu-id="82616-111">2018 年 10 月の時点では、Exchange Online Protection (EOP) を保有する組織にも保護の範囲を広げました。</span><span class="sxs-lookup"><span data-stu-id="82616-111">As of October, 2018 we extended the protection to organizations that have Exchange Online Protection (EOP) as well.</span></span> <span data-ttu-id="82616-112">また、すべてのフィルターが相互に学習する方法のため、Outlook.com のユーザーも影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82616-112">Additionally, because of the way all of our filters learn from each other, Outlook.com users may also be affected.</span></span>
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="82616-113">フィッシング攻撃でスプーフィングが使用される方法</span><span class="sxs-lookup"><span data-stu-id="82616-113">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="82616-114">ユーザーの保護について、Microsoft はフィッシングの脅威を重大視しています。</span><span class="sxs-lookup"><span data-stu-id="82616-114">When it comes to protecting its users, Microsoft takes the threat of phishing seriously.</span></span> <span data-ttu-id="82616-115">迷惑メールの送信者やフィッシャー (フィッシング詐欺師) がよく使用する手法の 1 つにスプーフィング (なりすまし) があります。スプーフィングによって、送信者が偽装されると、メッセージは実際の発信元とは異なる送信者または送信元から送られてきたように見えます。</span><span class="sxs-lookup"><span data-stu-id="82616-115">One of the techniques that spammers and phishers commonly use is spoofing, which is when the sender is forged, and a message appears to originate from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="82616-116">この手法は、多くの場合、ユーザーの認証情報を詐取しようとするフィッシング活動で使用されます。</span><span class="sxs-lookup"><span data-stu-id="82616-116">This technique is often used in phishing campaigns designed to obtain user credentials.</span></span> <span data-ttu-id="82616-117">Microsoft のスプーフィング対策テクノロジでは、具体的には「From: ヘッダー」の偽装を調べます。Outlook などの電子メール クライアントには、このヘッダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82616-117">Microsoft's Anti-spoof technology specifically examines forgery of the 'From: header' which is the one that shows up in an email client like Outlook.</span></span> <span data-ttu-id="82616-118">Microsoft は高確率で From: ヘッダーがスプーフィングされていると確信すると、そのメッセージをスプーフィングとして識別します。</span><span class="sxs-lookup"><span data-stu-id="82616-118">When Microsoft has high confidence that the From: header is spoofed, it identifies the message as a spoof.</span></span>
  
<span data-ttu-id="82616-119">スプーフィング メッセージは、実際のユーザーに 2 つの悪影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="82616-119">Spoofing messages have two negative implications for real life users:</span></span>
  
### <a name="1-spoofed-messages-deceive-users"></a><span data-ttu-id="82616-120">1. ユーザーがスプーフィングされたメッセージにだまされる</span><span class="sxs-lookup"><span data-stu-id="82616-120">1. Spoofed messages deceive users</span></span>
  
<span data-ttu-id="82616-121">1 つ目は、スプーフィングされたメッセージがユーザーにリンクをクリックするように誘導し、認証情報を提出させたり、マルウェアをダウンロードさせたり、機密コンテンツを含めてメッセージに返信させたりします (最後のものは「ビジネス メール詐欺」と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="82616-121">First, a spoofed message may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (the latter of which is known as Business Email Compromise).</span></span> <span data-ttu-id="82616-122">たとえば、次のフィッシング メッセージにある msoutlook94@service.outlook.com は、なりすましの送信者です。</span><span class="sxs-lookup"><span data-stu-id="82616-122">For example, the following is a phishing message with a spoofed sender of msoutlook94@service.outlook.com:</span></span>
  
![service.outlook.com を偽装しているフィッシング メッセージ](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
<span data-ttu-id="82616-124">上記のものは実際には service.outlook.com から発信されたものではありませんが、そう見えるようにフィッシャーがスプーフィングしています。</span><span class="sxs-lookup"><span data-stu-id="82616-124">The above did not actually come from service.outlook.com, but instead was spoofed by the phisher to make it look like it did.</span></span> <span data-ttu-id="82616-125">ここでは、ユーザーをだまして、メッセージ内のリンクをクリックさせようとしています。</span><span class="sxs-lookup"><span data-stu-id="82616-125">It is attempting to trick a user into clicking the link within the message.</span></span>
  
<span data-ttu-id="82616-126">次の例では、contoso.com のスプーフィングです。</span><span class="sxs-lookup"><span data-stu-id="82616-126">The next example is spoofing contoso.com:</span></span>
  
![フィッシング メッセージ: ビジネス メール詐欺](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
<span data-ttu-id="82616-128">このメッセージは正当なものに見えますが、実際にはなりすましです。</span><span class="sxs-lookup"><span data-stu-id="82616-128">The message looks legitimate, but in fact is a spoof.</span></span> <span data-ttu-id="82616-129">このフィッシング メッセージは、フィッシングのサブカテゴリであるビジネス メール詐欺の一種です。</span><span class="sxs-lookup"><span data-stu-id="82616-129">This phishing message is a type of Business Email Compromise which is a subcategory of phishing.</span></span>

### <a name="2-users-confuse-real-messages-for-fake-ones"></a><span data-ttu-id="82616-130">2. ユーザーが本物と偽物のメッセージを混同する</span><span class="sxs-lookup"><span data-stu-id="82616-130">2. Users confuse real messages for fake ones</span></span>
  
<span data-ttu-id="82616-131">2 つ目に、スプーフィングされたメッセージために、フィッシング メッセージについての知識があっても、本物とスプーフィングされたメッセージの見分けがつかないユーザーが疑いを持つようになってしまいます。</span><span class="sxs-lookup"><span data-stu-id="82616-131">Second, spoofed messages create uncertainty for users who know about phishing messages but cannot tell the difference between a real message and spoofed one.</span></span> <span data-ttu-id="82616-132">たとえば、次のものは Microsoft Security アカウントの電子メール アドレスから送信された本物のパスワード リセットのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="82616-132">For example, the following is an example of an actual password reset from the Microsoft Security account email address:</span></span>
  
![Microsoft の正当なパスワード リセット](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
<span data-ttu-id="82616-134">上記のメッセージは Microsoft から発信されたものですが、その一方で、ユーザーは今までにフィッシング メッセージを何度も受け取っています。そのメッセージは、リンクをクリックするように誘導して、認証情報を提出させたり、マルウェアをダウンロードさせたり、機密コンテンツを含めてメッセージに返信させたりしようとします。</span><span class="sxs-lookup"><span data-stu-id="82616-134">The above message did come from Microsoft, but at the same time, users are used to getting phishing messages that may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content.</span></span> <span data-ttu-id="82616-135">本物と偽物のパスワード リセットを見分けることが難しいため、多くのユーザーは、こうしたメッセージを無視したり、スパムとして報告したり、間違ったフィッシング詐欺として Microsoft に不要な報告を返したりします。</span><span class="sxs-lookup"><span data-stu-id="82616-135">Because it is difficult to tell the difference between a real password reset and a fake one, many users ignore these messages, report them as spam, or unnecessarily report the messages back to Microsoft as missed phishing scams.</span></span>

<span data-ttu-id="82616-136">スプーフィングを阻止するために、電子メールのフィルター処理分野の業界は、電子メール認証のプロトコル ([SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、[DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、[DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) など) を開発しました。</span><span class="sxs-lookup"><span data-stu-id="82616-136">To stop spoofing, the email filtering industry has developed email authentication protocols such as [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), and [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email).</span></span> <span data-ttu-id="82616-137">DMARC は、ユーザーのメール クライアントに表示されるメッセージの送信者 (前述の例では、service.outlook.com、outlook.com、および accountprotection.microsoft.com) を SPF または DKIM をパスしたドメインで検査することでスプーフィングを防止します。</span><span class="sxs-lookup"><span data-stu-id="82616-137">DMARC prevents spoofing examining a message's sender - the one that the user sees in their email client (in the examples above, this is service.outlook.com, outlook.com, and accountprotection.microsoft.com) - with the domain that passed SPF or DKIM.</span></span> <span data-ttu-id="82616-138">つまり、ユーザーに表示されるドメインは認証されているため、スプーフィングされていないことになります。</span><span class="sxs-lookup"><span data-stu-id="82616-138">That is, the domain that the user sees has been authenticated and is therefore not spoofed.</span></span> <span data-ttu-id="82616-139">詳細な説明については、この記事で後述するセクション「*電子メール認証がスプーフィングの阻止には不十分なことがある理由*」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-139">For a more complete discussion, see the section "*Understanding why email authentication is not always enough to stop spoofing"*  later on in this article.</span></span>
  
<span data-ttu-id="82616-140">ただし、電子メール認証レコードはオプションであり、必須ではないという問題があります。</span><span class="sxs-lookup"><span data-stu-id="82616-140">However, the problem is that email authentication records are optional, not required.</span></span> <span data-ttu-id="82616-141">そのため、microsoft.com や skype.com などの強力な認証ポリシーを公開しているドメインはスプーフィングから保護されますが、公開している認証ポリシーが弱いドメインや認証ポリシーがまったく存在しないドメインはスプーフィングの対象になります。2018 年 3 月の時点で、Fortune 500 の企業のうち強力な電子メール認証ポリシーを公開しているドメインは 9% のみです。</span><span class="sxs-lookup"><span data-stu-id="82616-141">Therefore, while domains with strong authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker authentication policies, or no policy at all, are targets for being spoofed.As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="82616-142">残りの 91% はフィッシャーによってスプーフィングされる可能性があり、その他のポリシーを使用する電子メール フィルターで検出されないと、エンド ユーザーとデバイスに配信されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="82616-142">The remaining 91% may be spoofed by a phisher, and unless the email filter detects it using another policy, may be delivered to an end user and deceive them:</span></span>
  
![Fortune 500 企業の DMARC ポリシー](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
<span data-ttu-id="82616-144">Fortune 500 に含まれない中小規模の企業で強力な電子メール認証ポリシーを公開している割合はさらに少なくなり、北米と西ヨーロッパ以外のドメインでは、それよりも少ない割合になります。</span><span class="sxs-lookup"><span data-stu-id="82616-144">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for domains that are outside of North America and western Europe.</span></span>
  
<span data-ttu-id="82616-145">これは重大な問題です。企業は電子メール認証のしくみを認識していないことがありますが、フィッシャーはそのしくみを理解して利用するためです。</span><span class="sxs-lookup"><span data-stu-id="82616-145">This is a big problem because while enterprises may not be aware of how email authentication works, phishers do understand and take advantage of the lack of it.</span></span>
  
<span data-ttu-id="82616-146">SPF、DKIM、および DMARC のセットアップの詳細については、この記事で後述する「*Office 365 のユーザー*」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-146">For information on setting up SPF, DKIM, and DMARC, see the section "*Customers of Office 365"*  later on in this document.</span></span> 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a><span data-ttu-id="82616-147">暗黙的な電子メール認証によるスプーフィングの防止</span><span class="sxs-lookup"><span data-stu-id="82616-147">Stopping spoofing with implicit email authentication</span></span>

<span data-ttu-id="82616-148">フィッシングやスピア フィッシングは大きな問題であり、強力な電子メール認証ポリシーの導入は限られているため、Microsoft はユーザーを保護するための機能に投資を続けています。</span><span class="sxs-lookup"><span data-stu-id="82616-148">Because phishing and spear phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft continues to invest in capabilities to protect its customers.</span></span> <span data-ttu-id="82616-149">そのため、Microsoft は*暗黙的な電子メール認証*を進めています。これは、ドメインが認証されていない場合、Microsoft は電子メール認証レコードが公開されているもとして、パスしない場合はそれに応じて処理します。</span><span class="sxs-lookup"><span data-stu-id="82616-149">Therefore, Microsoft is moving ahead with  *implicit email authentication* - if a domain doesn't authenticate, Microsoft will treat it as if it had published email authentication records and treat it accordingly if it doesn't pass.</span></span> 
  
<span data-ttu-id="82616-150">これを実現するために、Microsoft は通常の電子メール認証に対する多数の拡張機能 (送信者評価、送受信者履歴、行動分析などの高度な手法) を構築しました。</span><span class="sxs-lookup"><span data-stu-id="82616-150">To accomplish this, Microsoft has built numerous extensions to regular email authentication including sender reputation, sender/recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="82616-151">電子メール認証を公開しないドメインから送信されたメッセージは、そのメッセージが正当であることを示す別のシグナルが含まれていないときには、スプーフィングのマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="82616-151">A message sent from a domain that doesn't publish email authentication will be marked as spoof unless it contains other signals to indicate that it is legitimate.</span></span>
  
<span data-ttu-id="82616-152">これにより、エンド ユーザーは送信されてきた電子メールがスプーフィングされていないことを確信できるようになり、送信者は自分のドメインが偽装される心配がなくなり、Office 365 のユーザーはさらに優れた偽装保護などの保護を提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="82616-152">By doing this, end users can have confidence that an email sent to them has not been spoofed, senders can be confident that nobody is impersonating their domain, and customers of Office 365 can offer even better protection such as Impersonation protection.</span></span>
  
<span data-ttu-id="82616-153">Microsoft の一般発表については、「[大量のフィッシング詐欺: 第 2 部 - 強化された Office 365 のスプーフィング対策](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-153">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a><span data-ttu-id="82616-154">スプーフィングとして分類されたメッセージの識別</span><span class="sxs-lookup"><span data-stu-id="82616-154">Identifying that a message is classified as spoofed</span></span>

### <a name="composite-authentication"></a><span data-ttu-id="82616-155">複合認証</span><span class="sxs-lookup"><span data-stu-id="82616-155">Composite authentication</span></span>

<span data-ttu-id="82616-156">SPF、DKIM、および DMARC は、いずれも単独で役立つものですが、メッセージに明示的な認証レコードが存在していないときには、認証の状態を十分に伝達しません。</span><span class="sxs-lookup"><span data-stu-id="82616-156">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="82616-157">そのため、Microsoft は、複数のシグナルを 1 つの値に結合する複合認証 (略称: compauth) というアルゴリズムを開発しました。</span><span class="sxs-lookup"><span data-stu-id="82616-157">Therefore, Microsoft has developed an algorithm that combines multiple signals into a single value called Composite Authentication, or compauth for short.</span></span> <span data-ttu-id="82616-158">Office 365 のユーザーは、メッセージのヘッダーに含まれる *Authentication-Results* ヘッダーに compauth の値がスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="82616-158">Customers in Office 365 have compauth values stamped into the *Authentication-Results* header in the message headers.</span></span> 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|<span data-ttu-id="82616-159">**CompAuth の結果**</span><span class="sxs-lookup"><span data-stu-id="82616-159">**CompAuth result**</span></span>|<span data-ttu-id="82616-160">**説明**</span><span class="sxs-lookup"><span data-stu-id="82616-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="82616-161">fail</span><span class="sxs-lookup"><span data-stu-id="82616-161">FAIL</span></span>|<span data-ttu-id="82616-162">メッセージは明示的な認証に失敗したか (送信側ドメインが DNS で明示的にレコードを公開している場合)、暗黙的な認証に失敗した (送信側ドメインが DNS でレコードを公開していないため、そのドメインでレコードが公開されたものとして Office 365 によって結果が挿入された場合)。</span><span class="sxs-lookup"><span data-stu-id="82616-162">Message failed explicit authentication (sending domain published records explicitly in DNS) or implicit authentication (sending domain did not publish records in DNS, so Office 365 interpolated the result as if it had published records).</span></span>|
|<span data-ttu-id="82616-163">pass</span><span class="sxs-lookup"><span data-stu-id="82616-163">Single pass</span></span>|<span data-ttu-id="82616-164">メッセージは明示的な認証をパスした (メッセージは DMARC をパスしたか、[最適な推測で DMARC をパスした](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365))、または暗黙的な認証を高確度でパスした (送信側ドメインが電子メール認証レコードを公開していないが、Office 365 にはメッセージが正当である可能性が高いことを示す強力なバックエンドのシグナルがある)。</span><span class="sxs-lookup"><span data-stu-id="82616-164">Message passed explicit authentication (message passed DMARC, or [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) or implicit authentication with high confidence (sending domain does not publish email authentication records, but Office 365 has strong backend signals to indicate the message is likely legitimate).</span></span>|
|<span data-ttu-id="82616-165">softpass</span><span class="sxs-lookup"><span data-stu-id="82616-165">softpass</span></span>|<span data-ttu-id="82616-166">メッセージは暗黙的な認証を信頼度「低」から「中」でパスした (送信側ドメインが電子メール認証を公開していないが、Office 365 にはメッセージが正当であることを示すバックエンドのシグナルがある。ただし、そのシグナルの強度は弱い)。</span><span class="sxs-lookup"><span data-stu-id="82616-166">Message passed implicit authentication with low-to-medium confidence (sending domain does not publish email authentication, but Office 365 has backend signals to indicate the message is legitimate but the strength of the signal is weaker).</span></span>|
|<span data-ttu-id="82616-167">none</span><span class="sxs-lookup"><span data-stu-id="82616-167">none</span></span>|<span data-ttu-id="82616-168">メッセージは認証されていない (または、認証されたが一致しなかった)。ただし、送信者評価などの要因によって複合認証は適用されていない。</span><span class="sxs-lookup"><span data-stu-id="82616-168">Message did not authenticate (or it did authenticate but did not align), but composite authentication not applied due to sender reputation or other factors.</span></span>|
   
|||
|:-----|:-----|
|<span data-ttu-id="82616-169">**理由**</span><span class="sxs-lookup"><span data-stu-id="82616-169">**Reason**</span></span>|<span data-ttu-id="82616-170">**説明**</span><span class="sxs-lookup"><span data-stu-id="82616-170">**Description**</span></span>|
|<span data-ttu-id="82616-171">0xx</span><span class="sxs-lookup"><span data-stu-id="82616-171">0xx</span></span>|<span data-ttu-id="82616-172">メッセージは複合認証に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="82616-172">Message failed composite authentication.</span></span><br/><span data-ttu-id="82616-173">**000** は、メッセージが拒否または検疫のアクションによって DMARC に失敗したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="82616-173">**000** means the message failed DMARC with an action of reject or quarantine.</span></span>  <br/><span data-ttu-id="82616-174">**001** は、メッセージが暗黙的な電子メール認証に失敗したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="82616-174">**001** means the message failed implicit email authentication.</span></span> <span data-ttu-id="82616-175">これは、送信側ドメインが電子メール認証レコードを公開していないか、公開していた場合でも弱い失敗ポリシー (SPF soft fail または neutral、p=none の DMARC ポリシー) があったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="82616-175">This means that the sending domain did not have email authentication records published, or if they did, they had a weaker failure policy (SPF soft fail or neutral, DMARC policy of p=none).</span></span>  <br/><span data-ttu-id="82616-176">**002** は、組織に、スプーフィングされたメールの送信を明示的に禁止する送信者/ドメインのペアのポリシーがあることを意味します。この設定は、管理者が手動で設定します。</span><span class="sxs-lookup"><span data-stu-id="82616-176">**002** means the organization has a policy for the sender/domain pair that is explicitly prohibited from sending spoofed email, this setting is manually set by an administrator.</span></span>  <br/><span data-ttu-id="82616-177">**010** は、メッセージが拒否または検疫のアクションによって DMARC に失敗して、送信側ドメインが組織の承認済みドメインに含まれていることを意味します (これは、自己完結型 (つまり組織内の) スプーフィングの一部です)。</span><span class="sxs-lookup"><span data-stu-id="82616-177">**010** means the message failed DMARC with an action of reject or quarantine, and the sending domain is one of your organization's accepted-domains (this is part of self-to-self, or intra-org, spoofing).</span></span>  <br/><span data-ttu-id="82616-178">**011** は、暗黙的な電子メール認証に失敗したが、送信側ドメインが組織の承認済みドメインのいずれかであることを意味します (これは、自己完結型 (つまり組織内の) スプーフィングの一部です)。</span><span class="sxs-lookup"><span data-stu-id="82616-178">**011** means the message failed implicit email authentication, and the sending domain is one of your organization's accepted domains (this is part of self-to-self, or intra-org, spoofing).</span></span>|
|<span data-ttu-id="82616-179">その他のすべてのコード (1xx、2xx、3xx、4xx、5xx)</span><span class="sxs-lookup"><span data-stu-id="82616-179">All other codes (1xx, 2xx, 3xx, 4xx, 5xx)</span></span>|<span data-ttu-id="82616-180">メッセージが暗黙の認証にパスした理由や、認証なしでもアクションが適用されなかった理由に関する、さまざまな内部コードに対応します。</span><span class="sxs-lookup"><span data-stu-id="82616-180">Corresponds to various internal codes for why a message passed implicit authentication, or had no authentication but no action was applied.</span></span>|
   
<span data-ttu-id="82616-181">管理者は (エンド ユーザーも) メッセージのヘッダーを調べることで、送信者がスプーフィングされている可能性があるという結論を Office 365 が導き出した過程を確認できます。</span><span class="sxs-lookup"><span data-stu-id="82616-181">By looking at the headers of a message, an administrator or even an end user can determine how Office 365 arrives at the conclusion that the sender may be spoofed.</span></span>
  
### <a name="differentiating-between-different-types-of-spoofing"></a><span data-ttu-id="82616-182">各種のスプーフィングの区別</span><span class="sxs-lookup"><span data-stu-id="82616-182">Differentiating between different types of spoofing</span></span>

<span data-ttu-id="82616-183">Microsoft では、2 種類のスプーフィング メッセージを区別しています。</span><span class="sxs-lookup"><span data-stu-id="82616-183">Microsoft differentiates between two different types of spoofing messages:</span></span>
  
 <span data-ttu-id="82616-184">**組織内スプーフィング**</span><span class="sxs-lookup"><span data-stu-id="82616-184">**Intra-org spoofing**</span></span>
  
<span data-ttu-id="82616-185">自己完結型スプーフィングとも呼ばれます。これは、From: アドレスのドメインが受信者のドメインと同じまたは一致する (受信者のドメインが組織の[承認済みドメイン](https://technet.microsoft.com/ja-JP/library/jj945194%28v=exchg.150%29.aspx)のいずれかに含まれる) 場合、または From: アドレスのドメインが同じ組織の一部である場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="82616-185">Also known as self-to-self spoofing, this occurs when the domain in the From: address is the same as, or aligns with, the recipient domain (when recipient domain is one of your organization's [Accepted Domains](https://technet.microsoft.com/ja-JP/library/jj945194%28v=exchg.150%29.aspx)); or, when the domain in the From: address is part of the same organization.</span></span>
  
<span data-ttu-id="82616-186">たとえば、次に示す送信者と受信者のドメインは同じドメイン (contoso.com) です。</span><span class="sxs-lookup"><span data-stu-id="82616-186">For example, the following has sender and recipient from the same domain (contoso.com).</span></span> <span data-ttu-id="82616-187">このページでのスパムボットの収集活動を阻止するために、電子メール アドレスにはスペースが挿入されています。</span><span class="sxs-lookup"><span data-stu-id="82616-187">Spaces are inserted into the email address to prevent spambot harvesting on this page):</span></span>
  
<span data-ttu-id="82616-188">From: sender @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="82616-188">From: sender @ contoso.com</span></span>
  
<span data-ttu-id="82616-189">To: recipient @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="82616-189">To: recipient @ contoso.com</span></span>
  
<span data-ttu-id="82616-190">次に示す送信者と受信者のドメインは組織のドメイン (fabrikam.com) が一致しています。</span><span class="sxs-lookup"><span data-stu-id="82616-190">The following has the sender and recipient domains aligning with the organizational domain (fabrikam.com):</span></span>
  
<span data-ttu-id="82616-191">From: sender @ foo.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="82616-191">From: sender @ foo.fabrikam.com</span></span>
  
<span data-ttu-id="82616-192">To: recipient @ bar.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="82616-192">To: recipient @ bar.fabrikam.com</span></span>
  
<span data-ttu-id="82616-193">次に示す送信者と受信者のドメイン (microsoft.com と bing.com) は異なっていますが、どちらも同じ組織に属しています (つまり、どちらも組織の承認済みドメインの一部です)。</span><span class="sxs-lookup"><span data-stu-id="82616-193">The following sender and recipient domains are different (microsoft.com and bing.com), but they belong to the same organization (that is, both are part of the organization's Accepted Domains):</span></span>
  
<span data-ttu-id="82616-194">From: sender @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="82616-194">From: sender @ microsoft.com</span></span>
  
<span data-ttu-id="82616-195">To: recipient @ bing.com</span><span class="sxs-lookup"><span data-stu-id="82616-195">To: recipient @ bing.com</span></span>
  
<span data-ttu-id="82616-196">組織内スプーフィングに失敗したメッセージのヘッダーには、次の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82616-196">Messages that fail intra-org spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="82616-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span><span class="sxs-lookup"><span data-stu-id="82616-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span></span>
  
<span data-ttu-id="82616-198">CAT はメッセージのカテゴリであり、通常は SPM (スパム) のスタンプが設定されています。ただし、メッセージ内にある別の種類のパターンによって HSPM (高確度スパム) や PHISH (フィッシング) などになっていることもあります。</span><span class="sxs-lookup"><span data-stu-id="82616-198">The CAT is the category of the message, and it is normally stamped as SPM (spam), but occasionally may be HSPM (high confidence spam) or PHISH (phishing) depending upon what other types of patterns occur in the message.</span></span>
  
<span data-ttu-id="82616-199">SFTY はメッセージの安全性レベルです。最初の数字 (9) はメッセージがフィッシングであることを意味します。ドットの後にある 2 番目の数字のセット (11) は組織内スプーフィングであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="82616-199">The SFTY is the safety level of the message, the first digit (9) means the message is phishing, and second set of digits after the dot (11) means it is intra-org spoofing.</span></span>
  
<span data-ttu-id="82616-200">2018 年後半の時点では、組織内スプーフィングについてスタンプされる複合認証の特定の理由コードはありません (タイムラインは未定義です)。</span><span class="sxs-lookup"><span data-stu-id="82616-200">There is no specific reason code for Composite Authentication for intra-org spoofing, that will be stamped later in 2018 (timeline not yet defined).</span></span>
  
 <span data-ttu-id="82616-201">**クロスドメイン スプーフィング**</span><span class="sxs-lookup"><span data-stu-id="82616-201">**Cross-domain spoofing**</span></span>
  
<span data-ttu-id="82616-202">これは、From: アドレスの送信側ドメインが受信側組織の外部ドメインになる場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="82616-202">This occurs when the sending domain in the From: address is an external domain to the receiving organization.</span></span> <span data-ttu-id="82616-203">クロスドメイン スプーフィングのために複合認証に失敗したメッセージのヘッダーには、次の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82616-203">Messages that fail Composite Authentication due to cross-domain spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="82616-204">Authentication-Results: …</span><span class="sxs-lookup"><span data-stu-id="82616-204">Authentication-Results: …</span></span> <span data-ttu-id="82616-205">compauth=fail reason=000/001</span><span class="sxs-lookup"><span data-stu-id="82616-205">compauth=fail reason=000/001</span></span>
  
<span data-ttu-id="82616-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span><span class="sxs-lookup"><span data-stu-id="82616-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span></span>
  
<span data-ttu-id="82616-207">どちらの場合も、メッセージには次に示す赤色の安全のヒントがスタンプされます (同じ内容のヒントが受信者のメールボックスの言語に応じてカスタマイズされていることもあります)。</span><span class="sxs-lookup"><span data-stu-id="82616-207">In both cases, the following red safety tip is stamped in the message, or an equivalent that is customized to the recipient mailbox's language:</span></span>
  
![赤色の安全のヒント: 不正検出](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
<span data-ttu-id="82616-209">From: アドレスを調べて受信者の電子メールの内容を知るか、電子メールのヘッダーを調べることでのみ、組織内スプーフィングとクロスドメイン スプーフィングを区別できます。</span><span class="sxs-lookup"><span data-stu-id="82616-209">It's only by looking at the From: address and knowing what your recipient email is, or by inspecting the email headers, that you can differentiate between intra-org and cross-domain spoofing.</span></span>
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a><span data-ttu-id="82616-210">Office 365 のユーザーが自分で新しいスプーフィング対策保護の準備を整える方法</span><span class="sxs-lookup"><span data-stu-id="82616-210">How customers of Office 365 can prepare themselves for the new anti-spoofing protection</span></span>

### <a name="information-for-administrators"></a><span data-ttu-id="82616-211">管理者向けの情報</span><span class="sxs-lookup"><span data-stu-id="82616-211">Information for administrators</span></span>

<span data-ttu-id="82616-212">Office 365 の組織の管理者には、いくつかの注意が必要になる重要な情報があります。</span><span class="sxs-lookup"><span data-stu-id="82616-212">As an administrator of an organization in Office 365, there are several key pieces of information you should be aware of.</span></span>
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="82616-213">電子メール認証がスプーフィングの阻止には不十分なことがある理由</span><span class="sxs-lookup"><span data-stu-id="82616-213">Understanding why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="82616-214">新しいスプーフィング対策保護は、電子メール認証 (SPF、DKIM、および DMARC) に依存してメッセージにスプーフィングのマークを付けます。</span><span class="sxs-lookup"><span data-stu-id="82616-214">The new anti-spoofing protection relies on email authentication (SPF, DKIM, and DMARC) to not mark a message as spoofing.</span></span> <span data-ttu-id="82616-215">一般的な例として、これまでに送信側ドメインが SPF レコードを公開したことがない場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="82616-215">A common example is when a sending domain has never published SPF records.</span></span> <span data-ttu-id="82616-216">SPF レコードが存在しない場合やレコードが不適切に設定されている場合は、Microsoft のバックエンド インテリジェンスによってメッセージが正当であると宣言されていないと、送信メッセージにスプーフィングのマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="82616-216">If there are no SPF records or they are incorrectly set up, a sent message will be marked as spoofed unless Microsoft has back-end intelligence that says the message is legitimate.</span></span>
  
<span data-ttu-id="82616-217">たとえば、スプーフィング対策が展開されるまで、SPF、DKIM、および DMARC のどのレコードもないメッセージは次のようなものになります。</span><span class="sxs-lookup"><span data-stu-id="82616-217">For example, prior to anti-spoofing being deployed, a message may have looked like the following with no SPF record, no DKIM record, and no DMARC record:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
<span data-ttu-id="82616-218">スプーフィング対策後、Office 365 Enterprise E5、EOP、または ATP を使用している場合は、compauth 値がスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="82616-218">After anti-spoofing, if you have Office 365 Enterprise E5, EOP, or ATP, the compauth value is stamped:</span></span>
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

<span data-ttu-id="82616-219">これを修正するために example.com が SPF レコードを設定した場合は、DKIM レコードを設定していない場合でも、SPF にパスしたドメインと From: アドレスのドメインが一致するため、複合認証にパスするようになります。</span><span class="sxs-lookup"><span data-stu-id="82616-219">If example.com fixed this by setting up an SPF record but not a DKIM record, this would pass composite authentication because the domain that passed SPF aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="82616-220">また、DKIM レコードを設定して SPF レコードを設定していない場合でも、From: アドレスのドメインとパスした DKIM-Signature のドメインが一致するため同様に複合認証にパスします。</span><span class="sxs-lookup"><span data-stu-id="82616-220">Or, if they set up a DKIM record but not an SPF record, this would also pass composite authentication because the domain in the DKIM-Signature that passed aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="82616-221">ただし、フィッシャーも SPF と DKIM を設定して自分のドメインでメッセージに署名しておいて、From: アドレスに異なるドメインを指定する可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="82616-221">However, a phisher may also set up SPF and DKIM and sign the message with their own domain, but specify a different domain in the From: address.</span></span> <span data-ttu-id="82616-222">SPF と DKIM のどちらも From: アドレスのドメインと一致する必要はないため、example.com が DMARC レコードを公開していないときには、DMARC を使用してスプーフィングのマークが付けられることはありません。</span><span class="sxs-lookup"><span data-stu-id="82616-222">Neither SPF nor DKIM requires the domain to align with the domain in the From: address, so unless example.com published DMARC records, this would not be marked as a spoof using DMARC:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="82616-223">電子メール クライアント (Outlook や Outlook on the web などのあらゆる電子メール クライアント) には、From: ドメインのみが表示され、SPF や DKIM のドメインは表示されません。そのため、ユーザーは実際には maliciousDomain.com から送信されたメッセージを example.com から送信されたものだと誤解してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82616-223">In the email client (Outlook, Outlook on the web, or any other email client), only the From: domain is displayed, not the domain in the SPF or DKIM, and that can mislead the user into thinking the message came from example.com, but actually came from maliciousDomain.com.</span></span>
  
![パスした SPF または DKIM と From: ドメインが一致しないにもかかわらず認証されたメッセージ](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
<span data-ttu-id="82616-225">こうした理由から、Office 365 では From: アドレスのドメインが SPF または DKIM 署名のドメインと一致することを必要とします。また、一致しない場合は、メッセージが正当であることを示す何らかの内部シグナルが含まれていることを必要とします。</span><span class="sxs-lookup"><span data-stu-id="82616-225">For that reason, Office 365 requires that the domain in the From: address aligns with the domain in the SPF or DKIM signature, and if it doesn't, contains some other internal signals that indicates that the message is legitimate.</span></span> <span data-ttu-id="82616-226">それ以外の場合、メッセージは compauth に失敗します。</span><span class="sxs-lookup"><span data-stu-id="82616-226">Otherwise, the message would be a compauth fail.</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

<span data-ttu-id="82616-227">このようにして、Office 365 のスプーフィング対策では、認証されていないドメイン、および認証が設定されていてもユーザーが確認してメッセージの送信者だと信じる From: アドレスのドメインと一致しないドメインからの保護を実施します。</span><span class="sxs-lookup"><span data-stu-id="82616-227">Thus, Office 365 anti-spoofing protects against domains with no authentication, and against domains who set up authentication but mismatch against the domain in the From: address as that is the one that the user sees and believes is the sender of the message.</span></span> <span data-ttu-id="82616-228">これは、組織外のドメインと組織内のドメインの両方に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="82616-228">This is true both of domains external to your organization, as well as domains within your organization.</span></span>
  
<span data-ttu-id="82616-229">そのため、SPF と DKIM をパスしていても複合認証に失敗してスプーフィングのマークが付けられたメッセージを受信した場合は、From: アドレスのドメインが SPF および DKIM をパスしたドメインと一致していないことになります。</span><span class="sxs-lookup"><span data-stu-id="82616-229">Therefore, if you ever receive a message that failed composite authentication and is marked as spoofed, even though the message passed SPF and DKIM, it's because the domain that passed SPF and DKIM are not aligned with the domain in the From: address.</span></span>
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a><span data-ttu-id="82616-230">スプーフィングされた電子メールの処理方法の変更について</span><span class="sxs-lookup"><span data-stu-id="82616-230">Understanding changes in how spoofed emails are treated</span></span>

<span data-ttu-id="82616-231">現時点では、Office 365 のすべての組織 (ATP および ATP 以外) について、拒否または検疫のポリシーで DMARC に失敗したメッセージにはスパムのマークが付けられ、そのほとんどは高確度スパムの処理が実行されますが、通常のスパム処理が実行されることもあります (別のスパム ルールが先にメッセージをスパムとして識別したかどうかに応じて異なります)。</span><span class="sxs-lookup"><span data-stu-id="82616-231">Currently, for all organizations in Office 365 - ATP and non-ATP - messages that fail DMARC with a policy of reject or quarantine are marked as spam and usually take the high confidence spam action, or sometimes the regular spam action (depending on whether other spam rules first identify it as spam).</span></span> <span data-ttu-id="82616-232">組織内スプーフィングの検出では、通常のスパム処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="82616-232">Intra-org spoof detections take the regular spam action.</span></span> <span data-ttu-id="82616-233">この動作は、有効にする必要はありません。また、無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="82616-233">This behavior does not need to be enabled, nor can it be disabled.</span></span>
  
<span data-ttu-id="82616-234">ただし、クロスドメイン スプーフィングのメッセージについては、今回の変更が実施されるまでは、通常のスパム、フィッシング、およびマルウェアのチェックが実行され、フィルターの別の部分でメッセージが疑わしいものと識別された場合に、それぞれスパム、フィッシング、またはマルウェアのマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="82616-234">However, for cross-domain spoofing messages, before this change they would go through regular spam, phish, and malware checks and if other parts of the filter identified them as suspicious, would mark them as spam, phish, or malware respectively.</span></span> <span data-ttu-id="82616-235">新しいクロスドメイン スプーフィング対策では、認証できないメッセージには、[フィッシング対策] \> [スプーフィング対策ポリシー] で定義されたアクションが既定で実行されます。</span><span class="sxs-lookup"><span data-stu-id="82616-235">With the new cross-domain spoofing protection, any message that can't be authenticated will, by default, take the action defined in the Anti-phishing \> Anti-spoofing policy.</span></span> <span data-ttu-id="82616-236">これが定義されていない場合は、ユーザーの [迷惑メール] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="82616-236">If one is not defined, it will be moved to a users Junk Email folder.</span></span> <span data-ttu-id="82616-237">場合によっては、より疑わしいメッセージには、赤色の安全のヒントもメッセージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="82616-237">In some cases, more suspicious messages will also have the red safety tip added to the message.</span></span>
  
<span data-ttu-id="82616-238">その結果として、これまでにスパムのマークが付けられていた一部のメッセージには、引き続きスパムのマークが付けられますが、赤色の安全のヒントも付けられるようになります。また、以前は非スパムのマークが付けられていたメッセージに、赤色の安全性のヒントが追加された状態でスパムのマーク (CAT:SPOOF) が付けられることもあります。</span><span class="sxs-lookup"><span data-stu-id="82616-238">This may result in some messages that were previously marked as spam still getting marked as spam but will now also have a red safety tip; in other cases, messages that were previously marked as non-spam will start getting marked as spam (CAT:SPOOF) with a red safety tip added.</span></span> <span data-ttu-id="82616-239">さらに別のケースでは、すべてのスパムとフィッシングを検疫に移動していたユーザーは、それらが [迷惑メール] フォルダーに移動されるようになったことがわかります (この動作は変更できます。「[スプーフィング対策の設定の変更](#changing-your-anti-spoofing-settings)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="82616-239">In still other cases, customers that were moving all spam and phish to the quarantine would now see them going to the Junk Mail Folder (this behavior can be changed, see [Changing your anti-spoofing settings](#changing-your-anti-spoofing-settings)).</span></span>
  
<span data-ttu-id="82616-240">メッセージがスプーフィングされる方法は複数ありますが (この記事で前述した「[各種のスプーフィングの区別](#differentiating-between-different-types-of-spoofing)」を参照)、2018 年 3 月の時点では、そうしたメッセージを Office 365 で処理する方法は統合されていません。</span><span class="sxs-lookup"><span data-stu-id="82616-240">There are multiple different ways a message can be spoofed (see  [Differentiating between different types of spoofing](#differentiating-between-different-types-of-spoofing) earlier in this article) but as of March 2018 the way Office 365 treats these messages is not yet unified.</span></span> <span data-ttu-id="82616-241">次の表は、動作が新しくなったクロスドメイン スプーフィング対策の簡単な概要です。</span><span class="sxs-lookup"><span data-stu-id="82616-241">The following table is a quick summary, with Cross-domain spoofing protection being new behavior:</span></span> 
  
|<span data-ttu-id="82616-242">**スプーフィングの種類**</span><span class="sxs-lookup"><span data-stu-id="82616-242">**Type of spoof**</span></span>|<span data-ttu-id="82616-243">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="82616-243">**Category**</span></span>|<span data-ttu-id="82616-244">**安全のヒントの追加**</span><span class="sxs-lookup"><span data-stu-id="82616-244">**Safety tip added?**</span></span>|<span data-ttu-id="82616-245">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="82616-245">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="82616-246">DMARC の失敗 (検疫または拒否)</span><span class="sxs-lookup"><span data-stu-id="82616-246">DMARC fail (quarantine or reject)</span></span>  <br/> |<span data-ttu-id="82616-247">HSPM (既定)、SPM または PHSH の可能性もあり</span><span class="sxs-lookup"><span data-stu-id="82616-247">HSPM (default), may also be SPM or PHSH</span></span>  <br/> |<span data-ttu-id="82616-248">なし (現時点)</span><span class="sxs-lookup"><span data-stu-id="82616-248">No (not yet)</span></span>  <br/> |<span data-ttu-id="82616-249">すべての Office 365 ユーザー、Outlook.com</span><span class="sxs-lookup"><span data-stu-id="82616-249">All Office 365 customers, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="82616-250">自己完結型</span><span class="sxs-lookup"><span data-stu-id="82616-250">Self-to-self</span></span>  <br/> |<span data-ttu-id="82616-251">SPM</span><span class="sxs-lookup"><span data-stu-id="82616-251">SPM</span></span>  <br/> |<span data-ttu-id="82616-252">あり</span><span class="sxs-lookup"><span data-stu-id="82616-252">Yes</span></span>  <br/> |<span data-ttu-id="82616-253">すべての Office 365 組織、Outlook.com</span><span class="sxs-lookup"><span data-stu-id="82616-253">All Office 365 organizations, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="82616-254">クロスドメイン</span><span class="sxs-lookup"><span data-stu-id="82616-254">Cross-domain access</span></span>  <br/> |<span data-ttu-id="82616-255">SPOOF</span><span class="sxs-lookup"><span data-stu-id="82616-255">SPOOF</span></span>  <br/> |<span data-ttu-id="82616-256">あり</span><span class="sxs-lookup"><span data-stu-id="82616-256">Yes</span></span>  <br/> |<span data-ttu-id="82616-257">Office 365 Advanced Threat Protection および E5 ユーザー</span><span class="sxs-lookup"><span data-stu-id="82616-257">Office 365 Advanced Threat Protection and E5 customers</span></span>  <br/> |

### <a name="changing-your-anti-spoofing-settings"></a><span data-ttu-id="82616-258">スプーフィング対策の設定の変更</span><span class="sxs-lookup"><span data-stu-id="82616-258">Changing your anti-spoofing settings</span></span>

<span data-ttu-id="82616-259">スプーフィング対策 (クロスドメイン) の設定を作成または更新するには、セキュリティ/コンプライアンス センターの [脅威の管理] \> [ポリシー] タブにある [フィッシング対策] \> [スプーフィング対策の設定] に移動します。</span><span class="sxs-lookup"><span data-stu-id="82616-259">To create or update your (cross-domain) anti-spoofing settings, navigate to the Anti-phishing \> Anti-spoofing settings under the Threat Management \> Policy tab in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="82616-260">これまでにフィッシング対策の設定を作成したことがない場合は、その設定を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82616-260">If you have never created any anti-phishing settings, you will need to create one:</span></span>
  
![フィッシング対策: 新しいポリシーの作成](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
<span data-ttu-id="82616-262">既に作成したものがある場合は、それを選択して変更できます。</span><span class="sxs-lookup"><span data-stu-id="82616-262">If you've already created one, you can select it to modify it:</span></span>
  
![フィッシング対策: 既存のポリシーの変更](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
<span data-ttu-id="82616-264">ここで作成したポリシーを選択して、「[スプーフィング インテリジェンスの詳細情報](learn-about-spoof-intelligence.md)」の手順を進めます。</span><span class="sxs-lookup"><span data-stu-id="82616-264">Select the policy you just created and proceed through the steps as described in [Learn more about spoof intelligence](learn-about-spoof-intelligence.md).</span></span>
  
![スプーフィング対策の有効化または無効化](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![スプーフィング対策の安全のヒントの有効化または無効化](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
<span data-ttu-id="82616-267">PowerShell を使用して新しいポリシーを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="82616-267">To create a new authentication provider by using Windows PowerShell</span></span> 
  
```powershell
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

<span data-ttu-id="82616-268">その後で、PowerShell を使用してフィッシング対策ポリシーのパラメーターを変更することもできます。[Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-268">You may then modify the anti-phishing policy parameters using PowerShell, following the documentation at [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps).</span></span> <span data-ttu-id="82616-269">パラメーターとして、$name を指定できます。</span><span class="sxs-lookup"><span data-stu-id="82616-269">You may specify the $name as a parameter:</span></span>
  
```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

<span data-ttu-id="82616-270">2018 年の後半の時点では、既定のポリシーを作成する必要はなくなりました。組織内のすべての受信者を対象とする既定のポリシーが自動的に作成されるため、手動で指定する必要はありません (上記のスクリーンショットは、最終的な実装前に変更されることがあります)。</span><span class="sxs-lookup"><span data-stu-id="82616-270">Later in 2018, rather than you having to create a default policy, one will be created for you that is scoped to all the recipients in your organization so you don't have to specify it manually (the screenshots below are subject to change before the final implementation).</span></span>
  
![フィッシング対策の既定のポリシー](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
<span data-ttu-id="82616-272">ユーザーが作成したポリシーとは異なり、既定のポリシーは削除することも、優先度を変更することも、対象とするユーザー、ドメイン、またはグループを選択することもできません。</span><span class="sxs-lookup"><span data-stu-id="82616-272">Unlike a policy that you create, you cannot delete the default policy, modify its priority, or choose which users, domains, or groups to scope it to.</span></span>
  
![フィッシング対策の既定のポリシーの詳細](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
<span data-ttu-id="82616-274">PowerShell を使用して既定の保護を設定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="82616-274">To set up your default protection by using PowerShell:</span></span>
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

<span data-ttu-id="82616-275">スプーフィング対策保護は、Office 365 の前面に別のメール サーバーがある場合にのみ無効にします (詳細については、「スプーフィング対策の無効化が正当なシナリオ」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="82616-275">You should only disable anti-spoofing protection if you have another mail server or servers in front of Office 365 (see Legitimate scenarios to disable anti-spoofing for more details).</span></span>
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> <span data-ttu-id="82616-276">メール パスの最初のホップが Office 365 であり、スプーフィングのマークが付けられた正当な電子メールが多すぎる場合は、まず、スプーフィングされた電子メールの自分のドメインへの送信を許可する送信者を設定します (「*認証されていない電子メールを送信する正当な送信者の管理*」を参照)。</span><span class="sxs-lookup"><span data-stu-id="82616-276">If the first hop in your email path is Office 365, and you are getting too many legitimate emails marked as spoof, you should first set up your senders that are allowed to send spoofed email to your domain (see the section  *"Managing legitimate senders who are sending unauthenticated email"*  ).</span></span> <span data-ttu-id="82616-277">それでも誤検知 (正当なメッセージにスプーフィングのマークが付けられる) が多すぎる場合でも、スプーフィング対策保護を完全に無効化することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="82616-277">If you are still getting too many false positives (that is, legitimate messages marked as spoof), we do NOT recommend disabling anti-spoofing protection altogether.</span></span> <span data-ttu-id="82616-278">その代りに、「高」ではなく「基本」の保護を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82616-278">Instead, we recommend choosing Basic instead of High protection.</span></span> <span data-ttu-id="82616-279">スプーフィングされた電子メールを放置すると長期的には組織に相当に高いコストがかかる可能性があるため、誤検知に対処するほうが良いでしょう。</span><span class="sxs-lookup"><span data-stu-id="82616-279">It is better to work through false positives than to expose your organization to spoofed email which could end up imposing significantly higher costs in the long term.</span></span>

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="82616-280">認証されていない電子メールを送信する正当な送信者の管理</span><span class="sxs-lookup"><span data-stu-id="82616-280">Managing legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="82616-281">Office 365 は、認証されていない電子メールを組織に送信している送信者を追跡しています。</span><span class="sxs-lookup"><span data-stu-id="82616-281">Office 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="82616-282">その送信者がサービスによって正当ではないと判断されると、*compauth* 失敗のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="82616-282">If the service thinks the sender is not legitimate, it will mark it as a *compauth* failure.</span></span> <span data-ttu-id="82616-283">これは、SPOOF として分類されますが、そのメッセージに適用されたスプーフィング対策ポリシーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="82616-283">This will be classified as SPOOF although it depends on your anti-spoofing policy that was applied to the message.</span></span>
  
<span data-ttu-id="82616-284">ただし、管理者は、Office 365 の決定をオーバーライドして、スプーフィングされた電子メールの送信を許可する送信者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="82616-284">However, as an administrator, you can specify which senders are permitted to send spoofed email, overriding Office 365's decision.</span></span>
  
<span data-ttu-id="82616-285">**方法 1: 組織がドメインを所有している場合は、電子メール認証を設定する**</span><span class="sxs-lookup"><span data-stu-id="82616-285">**Method 1 - If your organization owns the domain, set up email authentication**</span></span>
  
<span data-ttu-id="82616-286">この方法は、組織内スプーフィングの解決に使用できます。また、複数のテナントを所有している場合や複数のテナントとやり取りする場合のクロスドメイン スプーフィングの解決にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="82616-286">This method can be used to resolve intra-org spoofing, and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="82616-287">さらに、Office 365 内の別のユーザーや、別のプロバイダーでホストされているサード パーティに送信する場合のクロスドメイン スプーフィングを解決する際にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82616-287">It also helps resolve cross-domain spoofing where you send to other customers within Office 365, and also third parties that are hosted in other providers.</span></span>
  
<span data-ttu-id="82616-288">詳細については、「[Office 365 のユーザー](#customers-of-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-288">For more details, see [Overview of deploying languages in Office 365 ProPlus](#customers-of-office-365).</span></span>

<span data-ttu-id="82616-289">**方法 2: スプーフィング インテリジェンスを使用して、認証されていない電子メールが許可された送信者を構成する**</span><span class="sxs-lookup"><span data-stu-id="82616-289">**Method 2 - Use Spoof intelligence to configure permitted senders of unauthenticated email**</span></span>
  
<span data-ttu-id="82616-290">認証されていないメッセージを組織に送信する送信者を許可するために、[スプーフィング インテリジェンス](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="82616-290">You can also use [Spoof Intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) to permit senders to transmit unauthenticated messages to your organization.</span></span> 
  
<span data-ttu-id="82616-291">外部ドメインの場合、スプーフィングされたユーザーは From アドレスのドメインになり、送信側インフラストラクチャは送信側 IP アドレス (/24 CIDR 範囲で分割)、または PTR レコードの組織のドメインになります (次のスクリーンショットでは、送信側 IP は 131.107.18.4 で、その PTR レコードは outbound.mail.protection.outlook.com であり、送信側インフラストラクチャについては outlook.com と表示されます)。</span><span class="sxs-lookup"><span data-stu-id="82616-291">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the sending IP address (divided up into /24 CIDR ranges), or the organizational domain of the PTR record (in the screenshot below, the sending IP might be 131.107.18.4 whose PTR record is outbound.mail.protection.outlook.com, and this would show up as outlook.com for the sending infrastructure).</span></span>
  
<span data-ttu-id="82616-292">この送信者に認証されていない電子メールの送信を許可するには、**[いいえ]** を **[はい]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="82616-292">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>
  
![スプーフィング対策の許可された送信者の設定](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
<span data-ttu-id="82616-294">PowerShell を使用して、特定の送信者にドメインのスプーフィングを許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="82616-294">You can also use PowerShell to allow specific sender to spoof your domain:</span></span>
  
```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Powershell から取得したスプーフィングされた送信者](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
<span data-ttu-id="82616-296">上の画像では、このスクリーンショットに収まるようにするための改行が追加されています。</span><span class="sxs-lookup"><span data-stu-id="82616-296">In the previous image, additional line breaks have been added to make this screenshot fit.</span></span> <span data-ttu-id="82616-297">通常は、すべての値が 1 行で表示されます。</span><span class="sxs-lookup"><span data-stu-id="82616-297">Normally, all the values would appear on a single line.</span></span>
  
<span data-ttu-id="82616-298">ファイルを編集し、outlook.com と bing.com に対応する行を見つけて、AllowedToSpoof エントリを No から Yes に変更します。</span><span class="sxs-lookup"><span data-stu-id="82616-298">Edit the file and look for the line that corresponds to outlook.com and bing.com, and change the AllowedToSpoof entry from No to Yes:</span></span>
  
![Powershell でスプーフィングの許可を Yes に設定する](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
<span data-ttu-id="82616-300">ファイルを保存して、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="82616-300">Save the file and then close it.</span></span>
  
```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

<span data-ttu-id="82616-301">これにより、bing.com は認証されていない電子メールを \*.outlook.com から送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="82616-301">This will now allow bing.com to send unauthenticated email from \*.outlook.com.</span></span>

<span data-ttu-id="82616-302">**方法 3: 送信者/受信者ペアの許可エントリを作成する**</span><span class="sxs-lookup"><span data-stu-id="82616-302">**Method 3 - Create an allow entry for the sender/recipient pair**</span></span>
  
<span data-ttu-id="82616-303">特定の送信者に対するすべてのスパム フィルター処理をバイパスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="82616-303">You can also choose to bypass all spam filtering for a particular sender.</span></span> <span data-ttu-id="82616-304">詳細については、「[Office 365 の許可リストに安全に送信者を追加する方法](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-304">For more details, see [How to securely add a sender to an allow list in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).</span></span>
  
<span data-ttu-id="82616-305">この方法を使用すると、スパム フィルター処理と一部のフィッシング フィルター処理がスキップされます。ただし、マルウェア フィルター処理はスキップされません。</span><span class="sxs-lookup"><span data-stu-id="82616-305">If you use this method, it will skip spam and some of the phish filtering, but not malware filtering.</span></span>
  
<span data-ttu-id="82616-306">**方法 4: 送信者に問い合わせて、電子メール認証を設定するように依頼する**</span><span class="sxs-lookup"><span data-stu-id="82616-306">**Method 4 - Contact the sender and ask them to set up email authentication**</span></span>
  
<span data-ttu-id="82616-307">スパムとフィッシングの問題があるため、Microsoft は、すべての送信者が電子メール認証を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82616-307">Because of the problem of spam and phishing, Microsoft recommends all senders set up email authentication.</span></span> <span data-ttu-id="82616-308">送信側ドメインの管理者がわかっている場合は、その管理者に問い合わせて、電子メール認証レコードを設定するように要求し、一切のオーバーライドが不要になるようにします。</span><span class="sxs-lookup"><span data-stu-id="82616-308">If you know an administrator of the sending domain, contact them and request that they set up email authentication records so you do not have to add any overrides.</span></span> <span data-ttu-id="82616-309">詳細については、この記事で後述する「[Office 365 ユーザーではないドメインの管理者](#administrators-of-domains-that-are-not-office-365-customers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-309">For more information, see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers)" later in this article.</span></span> 
  
<span data-ttu-id="82616-310">送信側ドメインで認証することは最初は難しい場合もありますが、そのドメインからの電子メールを迷惑メールとして処理したり拒否したりする電子メール フィルターが時間の経過と共に増え続け、適切に配信されるようにするために適切なレコードを設定することになります。</span><span class="sxs-lookup"><span data-stu-id="82616-310">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span>
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="82616-311">スプーフィングのマークが付けられたメッセージの数量に関するレポートの表示</span><span class="sxs-lookup"><span data-stu-id="82616-311">Viewing reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="82616-312">スプーフィング対策ポリシーを有効にすると、脅威の調査と対応の機能を使用して、フィッシングのマークが付けられたメッセージの量に関する数値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="82616-312">Once your anti-spoofing policy is enabled, you can use threat investigation and response capabilities to get numbers around how many messages are marked as phish.</span></span> <span data-ttu-id="82616-313">このためには、セキュリティ/コンプライアンス センター (SCC) の [脅威の管理] \> [エクスプローラー] に移動して、[表示] を [フィッシング] に設定し、[送信者のドメイン] または [保護の状態] でグループ化します。</span><span class="sxs-lookup"><span data-stu-id="82616-313">To do this, go into the Security &amp; Compliance Center (SCC) under Threat Management \> Explorer, set the View to Phish, and group by Sender Domain or Protection Status:</span></span>
  
![フィッシングのマークが付けられたメッセージ数の表示](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
<span data-ttu-id="82616-315">各種のレポートを操作して、SPOOF のマークが付けられたメッセージも含めて、フィッシングのマークが付けられた数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="82616-315">You can interact with the various reports to see how many were marked as phishing, including messages marked as SPOOF.</span></span> <span data-ttu-id="82616-316">詳細については、「[Office 365 の脅威の調査と対応についての作業を開始する](get-started-with-ti.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-316">To learn more, see [Get started with Office 365 Threat investigation and response](get-started-with-ti.md).</span></span>
  
<span data-ttu-id="82616-317">現在のところ、どのメッセージにスプーフィングのマークが付けられたかを分類することはできません。その他の種類のフィッシングは分類できます (全般的なフィッシング、ドメインまたはユーザーの偽装など)。</span><span class="sxs-lookup"><span data-stu-id="82616-317">You can't yet split out which messages were marked due to spoofing as opposed to other types of phishing (general phishing, domain or user impersonation, and so on).</span></span> <span data-ttu-id="82616-318">将来、これはセキュリティ/コンプライアンス センターから実行できるようになる予定です。</span><span class="sxs-lookup"><span data-stu-id="82616-318">However, later, you will be able to do this through the Security &amp; Compliance Center.</span></span> <span data-ttu-id="82616-319">そのときには、このレポートを起点として使用して、認証に失敗したためにスプーフィングのマークが付けられている正当な送信側ドメインを特定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="82616-319">Once you do, you can use this report as a starting place to identify sending domains that may be legitimate that are being marked as spoof due to failing authentication.</span></span>
  
<span data-ttu-id="82616-320">次のスクリーンショットは、このデータの表示形式を提案するためのものですが、リリース時には変更されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82616-320">The following screenshot is a proposal for how this data will look, but may change when released:</span></span>
  
![検出の種類別に表示されたフィッシング レポート](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
<span data-ttu-id="82616-322">ATP なしのユーザーと E5 ユーザーの場合、こうしたレポートは、将来、脅威に対する保護の状態 (TPS) レポートで利用できるようになりますが、少なくとも 24 時間の遅れがあると見込まれます。</span><span class="sxs-lookup"><span data-stu-id="82616-322">For non-ATP and E5 customers, these reports will be available later under the Threat Protection Status (TPS) reports, but will be delayed by at least 24 hours.</span></span> <span data-ttu-id="82616-323">このページは、それらの機能をセキュリティ/コンプライアンス センターに統合したときに更新される予定です。</span><span class="sxs-lookup"><span data-stu-id="82616-323">This page will be updated as they are integrated into the Security &amp; Compliance Center.</span></span>
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a><span data-ttu-id="82616-324">スプーフィングのマークが付けられるメッセージの数量の予測</span><span class="sxs-lookup"><span data-stu-id="82616-324">Predicting how many messages will be marked as spoof</span></span>

<span data-ttu-id="82616-325">Office 365 の設定が更新されて、スプーフィング対策の適用をオフにしたり、「基本」または「高」の適用でオンにしたりできるようになると、さまざまな設定でメッセージの処理がどのように変化するかを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="82616-325">Once Office 365 updates its settings to let you turn the anti-spoofing enforcement Off, or on with Basic or High enforcement, you will be given the ability to see how message disposition will change at the various settings.</span></span> <span data-ttu-id="82616-326">つまり、スプーフィング対策がオフのときに、「基本」にするとスプーフィングとして検出されるメッセージの数を確認できるようになり、「基本」になっているときに、「高」にするとスプーフィングとして検出されるメッセージ数の増加量を確認できるようになるということです。</span><span class="sxs-lookup"><span data-stu-id="82616-326">That is, if anti-spoofing is Off, you will be able to see how many messages will be detected as Spoof if you turn to Basic; or, if it's Basic, you will be able to see how many more messages will be detected as Spoof if you turn it to High.</span></span>
  
<span data-ttu-id="82616-327">この機能は、現在開発中です。</span><span class="sxs-lookup"><span data-stu-id="82616-327">This feature is currently under development.</span></span> <span data-ttu-id="82616-328">詳細が明らかになり次第、このページはセキュリティ/コンプライアンス センターのスクリーンショットと、PowerShell の例の両方で更新される予定です。</span><span class="sxs-lookup"><span data-stu-id="82616-328">As more details are defined, this page will be updated both with screenshots of the Security and Compliance Center, and with PowerShell examples.</span></span>
  
![スプーフィング対策を有効にした場合の「What-If」レポート](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![スプーフィングされた送信者を許可する際の予定される UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a><span data-ttu-id="82616-331">スパム検出、フィッシング検出、および高度なフィッシング検出の結合方法について</span><span class="sxs-lookup"><span data-stu-id="82616-331">Understanding how spam, phishing, and advanced phishing detections are combined</span></span>

<span data-ttu-id="82616-332">Exchange Online を使用している組織は、ATP の有無にかかわらず、サービスによってメッセージがマルウェア、スパム、高確度スパム、フィッシング、およびバルクとして識別されたときに実行するアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="82616-332">Organizations that use Exchange Online, with or without ATP, can specify which actions to take when the service identifies messages as malware, spam, high confidence spam, phishing, and bulk.</span></span> <span data-ttu-id="82616-333">ATP ユーザー向けの ATP フィッシング対策ポリシーと、EOP ユーザー向けのフィッシング対策ポリシーがあり、メッセージは複数の検出の種類 (たとえば、マルウェア、フィッシング、およびユーザー偽装) に該当するという事実があるため、どのポリシーが適用されるかについて、ある程度の混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82616-333">With the ATP Anti-phishing policies for ATP customers, and the Anti-phishing policies for EOP customers, and the fact that a message may hit multiple detection types (for example, malware, phishing, and user-impersonation), there may be some confusion as to which policy applies.</span></span>
  
<span data-ttu-id="82616-334">一般に、メッセージに適用されたポリシーは、X-Forefront-Antispam-Report ヘッダーの CAT (カテゴリ) で特定できます。</span><span class="sxs-lookup"><span data-stu-id="82616-334">In general, the policy applied to a message is identified in the X-Forefront-Antispam-Report header in the CAT (Category) property.</span></span>
  
|<span data-ttu-id="82616-335">**優先度**</span><span class="sxs-lookup"><span data-stu-id="82616-335">**Priority**</span></span>|<span data-ttu-id="82616-336">**ポリシー**</span><span class="sxs-lookup"><span data-stu-id="82616-336">**Policy**</span></span>|<span data-ttu-id="82616-337">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="82616-337">**Category**</span></span>|<span data-ttu-id="82616-338">**管理の場所**</span><span class="sxs-lookup"><span data-stu-id="82616-338">**Where managed?**</span></span>|<span data-ttu-id="82616-339">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="82616-339">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="82616-340">1</span><span class="sxs-lookup"><span data-stu-id="82616-340">-1</span></span>  <br/> |<span data-ttu-id="82616-341">マルウェア</span><span class="sxs-lookup"><span data-stu-id="82616-341">Malware detections</span></span>  <br/> |<span data-ttu-id="82616-342">MALW</span><span class="sxs-lookup"><span data-stu-id="82616-342">MALW</span></span>  <br/> |[<span data-ttu-id="82616-343">マルウェア ポリシー</span><span class="sxs-lookup"><span data-stu-id="82616-343">Malware Filter policy attributes</span></span>](configure-anti-malware-policies.md) <br/> |<span data-ttu-id="82616-344">すべての組織</span><span class="sxs-lookup"><span data-stu-id="82616-344">All organizations</span></span>  <br/> |
|<span data-ttu-id="82616-345">2</span><span class="sxs-lookup"><span data-stu-id="82616-345">-2</span></span>  <br/> |<span data-ttu-id="82616-346">フィッシング</span><span class="sxs-lookup"><span data-stu-id="82616-346">Phishing</span></span>  <br/> |<span data-ttu-id="82616-347">PHSH</span><span class="sxs-lookup"><span data-stu-id="82616-347">PHSH</span></span>  <br/> |[<span data-ttu-id="82616-348">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="82616-348">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="82616-349">すべての組織</span><span class="sxs-lookup"><span data-stu-id="82616-349">All organizations</span></span>  <br/> |
|<span data-ttu-id="82616-350">3</span><span class="sxs-lookup"><span data-stu-id="82616-350">-3</span></span>  <br/> |<span data-ttu-id="82616-351">高確度スパム</span><span class="sxs-lookup"><span data-stu-id="82616-351">High confidence spam</span></span>  <br/> |<span data-ttu-id="82616-352">HSPM</span><span class="sxs-lookup"><span data-stu-id="82616-352">HSPM</span></span>  <br/> |[<span data-ttu-id="82616-353">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="82616-353">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="82616-354">すべての組織</span><span class="sxs-lookup"><span data-stu-id="82616-354">All organizations</span></span>  <br/> |
|<span data-ttu-id="82616-355">4</span><span class="sxs-lookup"><span data-stu-id="82616-355">4.</span></span>  <br/> |<span data-ttu-id="82616-356">スプーフィング</span><span class="sxs-lookup"><span data-stu-id="82616-356">Spoofing</span></span>  <br/> |<span data-ttu-id="82616-357">SPOOF</span><span class="sxs-lookup"><span data-stu-id="82616-357">SPOOF</span></span>  <br/> |<span data-ttu-id="82616-358">[スプーフィング対策ポリシー](https://go.microsoft.com/fwlink/?linkid=864553)、[スプーフィング インテリジェンス](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="82616-358">[Anti-phishing policy](https://go.microsoft.com/fwlink/?linkid=864553), [Spoof intelligence](learn-about-spoof-intelligence.md)</span></span> <br/> |<span data-ttu-id="82616-359">すべての組織</span><span class="sxs-lookup"><span data-stu-id="82616-359">All organizations</span></span>  <br/> |
|<span data-ttu-id="82616-360">5</span><span class="sxs-lookup"><span data-stu-id="82616-360">5.</span></span>  <br/> |<span data-ttu-id="82616-361">スパム</span><span class="sxs-lookup"><span data-stu-id="82616-361">Spam</span></span>  <br/> |<span data-ttu-id="82616-362">SPM</span><span class="sxs-lookup"><span data-stu-id="82616-362">SPM</span></span>  <br/> |[<span data-ttu-id="82616-363">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="82616-363">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="82616-364">すべての組織</span><span class="sxs-lookup"><span data-stu-id="82616-364">All organizations</span></span>  <br/> |
|<span data-ttu-id="82616-365">6</span><span class="sxs-lookup"><span data-stu-id="82616-365">6.</span></span>  <br/> |<span data-ttu-id="82616-366">バルク</span><span class="sxs-lookup"><span data-stu-id="82616-366">Bulk operations</span></span>  <br/> |<span data-ttu-id="82616-367">BULK</span><span class="sxs-lookup"><span data-stu-id="82616-367">BULK</span></span>  <br/> |[<span data-ttu-id="82616-368">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="82616-368">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="82616-369">すべての組織</span><span class="sxs-lookup"><span data-stu-id="82616-369">All organizations</span></span>  <br/> |
|<span data-ttu-id="82616-370">7</span><span class="sxs-lookup"><span data-stu-id="82616-370">7.</span></span>  <br/> |<span data-ttu-id="82616-371">ドメイン偽装</span><span class="sxs-lookup"><span data-stu-id="82616-371">Domain Impersonation</span></span>  <br/> |<span data-ttu-id="82616-372">DIMP</span><span class="sxs-lookup"><span data-stu-id="82616-372">DIMP</span></span>  <br/> |[<span data-ttu-id="82616-373">Office 365 の ATP フィッシング対策とフィッシング対策ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="82616-373">Set up anti-phishing and ATP anti-phishing policies</span></span>](set-up-anti-phishing-policies.md) <br/> |<span data-ttu-id="82616-374">ATP ありの組織のみ</span><span class="sxs-lookup"><span data-stu-id="82616-374">Organizations with ATP only</span></span>  <br/> |
|<span data-ttu-id="82616-375">8</span><span class="sxs-lookup"><span data-stu-id="82616-375">8.</span></span>  <br/> |<span data-ttu-id="82616-376">ユーザー偽装</span><span class="sxs-lookup"><span data-stu-id="82616-376">User impersonation</span></span>  <br/> |<span data-ttu-id="82616-377">UIMP</span><span class="sxs-lookup"><span data-stu-id="82616-377">UIMP</span></span>  <br/> |[<span data-ttu-id="82616-378">Office 365 の ATP フィッシング対策とフィッシング対策ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="82616-378">Set up anti-phishing and ATP anti-phishing policies</span></span>](set-up-anti-phishing-policies.md) <br/> |<span data-ttu-id="82616-379">ATP ありの組織のみ</span><span class="sxs-lookup"><span data-stu-id="82616-379">Organizations with ATP only</span></span> <br/> |

<span data-ttu-id="82616-380">複数の異なるフィッシング対策ポリシーがある場合は、優先度が最も高いものが適用されます。</span><span class="sxs-lookup"><span data-stu-id="82616-380">If you have multiple different Anti-phishing policies, the one at the highest priority will apply.</span></span> <span data-ttu-id="82616-381">たとえば、次の 2 つのポリシーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="82616-381">For example, suppose you have two policies:</span></span>

|<span data-ttu-id="82616-382">**ポリシー**</span><span class="sxs-lookup"><span data-stu-id="82616-382">**Policy**</span></span>|<span data-ttu-id="82616-383">**優先度**</span><span class="sxs-lookup"><span data-stu-id="82616-383">**Priority**</span></span>|<span data-ttu-id="82616-384">**ユーザー/ドメイン偽装**</span><span class="sxs-lookup"><span data-stu-id="82616-384">**User/Domain Impersonation**</span></span>|<span data-ttu-id="82616-385">**スプーフィング対策**</span><span class="sxs-lookup"><span data-stu-id="82616-385">**Anti-spoofing**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="82616-386">A</span><span class="sxs-lookup"><span data-stu-id="82616-386">A</span></span>  <br/> |<span data-ttu-id="82616-387">1</span><span class="sxs-lookup"><span data-stu-id="82616-387">-1</span></span>  <br/> |<span data-ttu-id="82616-388">オン</span><span class="sxs-lookup"><span data-stu-id="82616-388">On</span></span>  <br/> |<span data-ttu-id="82616-389">オフ</span><span class="sxs-lookup"><span data-stu-id="82616-389">Off</span></span>  <br/> |
|<span data-ttu-id="82616-390">B</span><span class="sxs-lookup"><span data-stu-id="82616-390">B</span></span>  <br/> |<span data-ttu-id="82616-391">2</span><span class="sxs-lookup"><span data-stu-id="82616-391">-2</span></span>  <br/> |<span data-ttu-id="82616-392">オフ</span><span class="sxs-lookup"><span data-stu-id="82616-392">Off</span></span>  <br/> |<span data-ttu-id="82616-393">オン</span><span class="sxs-lookup"><span data-stu-id="82616-393">On</span></span>  <br/> |

<span data-ttu-id="82616-394">着信したメッセージがスプーフィングとユーザー偽装の両方として識別され、ポリシー A とポリシー B の適用範囲が同じユーザーのグループに設定されている場合、そのメッセージはスプーフィングとして扱われますが、スプーフィング対策はオフにされていて、SPOOF の優先度 (4) はユーザー偽装の優先度 (8) よりも高いため、どのアクションも適用されません。</span><span class="sxs-lookup"><span data-stu-id="82616-394">If a message comes in and is identified as both spoofing and user impersonation, and the same set of users is scoped to Policy A and Policy B, then the message is treated as a spoof but no action is applied since Anti-spoofing is turned off, and SPOOF runs at a higher priority (4) than User Impersonation (8).</span></span>
  
<span data-ttu-id="82616-395">別の種類のフィッシング ポリシーが適用されるようにするには、各種ポリシーの適用対象になるユーザーの設定を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82616-395">To make other types of phishing policy apply, you will need to adjust the settings of who the various policies are applied to.</span></span>
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a><span data-ttu-id="82616-396">スプーフィング対策の無効化が正当なシナリオ</span><span class="sxs-lookup"><span data-stu-id="82616-396">Legitimate scenarios to disable anti-spoofing</span></span>

<span data-ttu-id="82616-397">スプーフィング対策はフィッシング攻撃からのユーザーの保護を向上するためのものです。そのため、スプーフィング対策保護を無効にすることはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="82616-397">Anti-spoofing better protects customers from phishing attacks, and therefore disabling anti-spoofing protection is strongly discouraged.</span></span> <span data-ttu-id="82616-398">無効にすることで、ある程度の誤検知を短期的に解決することはできますが、長期的には、より大きなリスクにさらされることになります。</span><span class="sxs-lookup"><span data-stu-id="82616-398">By disabling it, you may resolve some short-term false positives, but long term you will be exposed to more risk.</span></span> <span data-ttu-id="82616-399">送信者側で認証を設定するコストや、フィッシング ポリシーの調整のためのコストは、通常、1 回限りのイベントであり、要求されるメンテナンスは最小限の定期的なもののみです。</span><span class="sxs-lookup"><span data-stu-id="82616-399">The cost for setting up authentication on the sender side, or making adjustments in the phishing policies, are usually one-time events or require only minimal, periodic maintenance.</span></span> <span data-ttu-id="82616-400">その一方、フィッシング攻撃によってデータが公開されてしまったり、資産が侵害されてしまうと、その回復にかかるコストは非常に高くなります。</span><span class="sxs-lookup"><span data-stu-id="82616-400">However, the cost to recover from a phishing attack where data has been exposed, or assets have been compromised is much higher.</span></span>
  
<span data-ttu-id="82616-401">このため、スプーフィング対策保護を無効にするよりも、スプーフィング対策の誤検知に対処するほうが好結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="82616-401">For this reason, it is better to work through anti-spoofing false positives than to disable anti-spoof protection.</span></span>
  
<span data-ttu-id="82616-402">ただし、スプーフィング対策の無効化が必要になる正当なシナリオもあります。そのシナリオとは、メッセージ ルーティングに別のメールのフィルター処理製品があり、メール パスの最初のホップが Office 365 ではない場合です。</span><span class="sxs-lookup"><span data-stu-id="82616-402">However, there is a legitimate scenario where anti-spoofing should be disabled, and that is when there are additional mail-filtering products in the message routing, and Office 365 is not the first hop in the email path:</span></span>
  
![ユーザーの MX レコードは Office 365 を指していません](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
<span data-ttu-id="82616-404">その他のサーバーは、オンプレミスの Exchange メール サーバー、Ironport などのメール フィルター処理デバイス、または別のクラウドでホストされているサービスです。</span><span class="sxs-lookup"><span data-stu-id="82616-404">The other server may be an Exchange on-premises mail server, a mail filtering device such as Ironport, or another cloud hosted service.</span></span>
  
<span data-ttu-id="82616-405">受信者ドメインの MX レコードが Office 365 を指していない場合は、スプーフィング対策を無効にする必要はありません。Office 365 は受信側ドメインの MX レコードを検索して、そのレコードが別のサービスを指しているときには、スプーフィング対策を抑止します。</span><span class="sxs-lookup"><span data-stu-id="82616-405">If the MX record of the recipient domain does not point to Office 365, then there is no need to disable anti-spoofing because Office 365 looks up your receiving domain's MX record and suppresses anti-spoofing if it points to another service.</span></span> <span data-ttu-id="82616-406">ドメインの前面に別のサーバーがあるかどうかがわからない場合は、MX Toolbox などの Web サイトを使用すると MX レコードを参照できます。</span><span class="sxs-lookup"><span data-stu-id="82616-406">If you don't know if your domain has another server in front, you can use a website like MX Toolbox to look up the MX record.</span></span> <span data-ttu-id="82616-407">これにより、次のような表示が得られます。</span><span class="sxs-lookup"><span data-stu-id="82616-407">It might say something like the following:</span></span>
  
![MX レコードはドメインが Office 365 を指していないことを示しています](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
<span data-ttu-id="82616-409">このドメインの MX レコードは Office 365 を指していないため、Office 365 はスプーフィング対策の実施を適用しません。</span><span class="sxs-lookup"><span data-stu-id="82616-409">This domain has an MX record that does not point to Office 365, so Office 365 would not apply anti-spoofing enforcement.</span></span>
  
<span data-ttu-id="82616-410">ただし、受信者のドメインが Office 365 を指して*いる*場合は、Office 365 の前面に別のサービスが存在していても、スプーフィング対策を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82616-410">However, if the MX record of the recipient domain  *does*  point to Office 365, even though there is another service in front of Office 365, then you should disable anti-spoofing.</span></span> <span data-ttu-id="82616-411">最も一般的な例は、受信者の書き換えによるものです。</span><span class="sxs-lookup"><span data-stu-id="82616-411">The most common example is through the use of a recipient rewrite:</span></span> 
  
![受信者の書き換えのルーティング図](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
<span data-ttu-id="82616-413">ドメイン contoso.com の MX レコードはオンプレミスのサーバーを指していますが、ドメイン @office365.contoso.net の MX レコードは Office 365 を指しています。これは、MX レコードに \*.protection.outlook.com、または \*.eo.outlook.com が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="82616-413">The domain contoso.com's MX record points to the on-premises server, while the domain @office365.contoso.net's MX record points to Office 365 because it contains \*.protection.outlook.com, or \*.eo.outlook.com in the MX record:</span></span>
  
![MX レコードは Office 365 を指しているため、受信者が書き換えられている可能性があります](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
<span data-ttu-id="82616-415">受信者のドメインの MX レコードが Office 365 指していない場合と、受信者の書き換えが実施された場合を区別するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="82616-415">Be sure to differentiate when a recipient domain's MX record does not point to Office 365, and when it has undergone a recipient rewrite.</span></span> <span data-ttu-id="82616-416">この 2 つのケースを見分けることが重要です。</span><span class="sxs-lookup"><span data-stu-id="82616-416">It is important to tell the difference between these two cases.</span></span>
  
<span data-ttu-id="82616-417">受信側ドメインの受信者が書き換えられたかどうか不明な場合は、メッセージのヘッダーを調べることで判断できます。</span><span class="sxs-lookup"><span data-stu-id="82616-417">If you are unsure whether or not your receiving domain has undergone a recipient-rewrite, sometimes you can tell by looking at the message headers.</span></span>
  
<span data-ttu-id="82616-418">a) まず、メッセージのヘッダーで、Authentication-Results ヘッダーにある受信者ドメインを調べます。</span><span class="sxs-lookup"><span data-stu-id="82616-418">a) First, look at the headers in the message for the recipient domain in the Authentication-Results header:</span></span>
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

<span data-ttu-id="82616-419">受信者のドメインは、上記の赤色で示された太字のテキストでわかります (この例では、office365.contoso.net)。</span><span class="sxs-lookup"><span data-stu-id="82616-419">The recipient domain is found in the bold red text above, in this case office365.contoso.net.</span></span> <span data-ttu-id="82616-420">これは、To: ヘッダーの受信者と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="82616-420">This may be different that the recipient in the To: header:</span></span>
  
<span data-ttu-id="82616-421">To: Example Recipient \<recipient @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="82616-421">To: Example Recipient \<recipient @ contoso.com\></span></span>
  
<span data-ttu-id="82616-422">実際の受信者のドメインの MX レコード検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="82616-422">Perform an MX-record lookup of the actual recipient domain.</span></span> <span data-ttu-id="82616-423">MX に \*.protection.outlook.com、mail.messaging.microsoft.com、\*.eo.outlook.com、または mail.global.frontbridge.com が含まれている場合、その MX は Office 365 を指していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="82616-423">If it contains \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com, or mail.global.frontbridge.com, that means that the MX points to Office 365.</span></span>
  
<span data-ttu-id="82616-424">これらの値が含まれていない場合、その MX は Office 365 を指していないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="82616-424">If it does not contain those values, then it means that the MX does not point to Office 365.</span></span> <span data-ttu-id="82616-425">これを確認するには、MX Toolbox などを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82616-425">One tool you can use to verify this is MX Toolbox.</span></span>
  
<span data-ttu-id="82616-426">この例では、contoso.com (To: ヘッダーにあるため受信者のように見えるドメイン) の MX レコードは、次に示すようにオンプレミスのサーバーを指しています。</span><span class="sxs-lookup"><span data-stu-id="82616-426">For this particular example, the following says that contoso.com, the domain that looks like the recipient since it was the To: header, has MX record points to an on-prem server:</span></span>
  
![オンプレミスのサーバーを指している MX レコード](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
<span data-ttu-id="82616-428">ただし、実際の受信者は office365.contoso.net であり、その MX レコードは Office 365 を指しています。</span><span class="sxs-lookup"><span data-stu-id="82616-428">However, the actual recipient is office365.contoso.net whose MX record does point to Office 365:</span></span>
  
![MX は Office 365 を指しています (受信者が書き換えられている可能性が高い)](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
<span data-ttu-id="82616-430">そのため、このメッセージは受信者が書き換えられている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82616-430">Therefore, this message has likely undergone a recipient-rewrite.</span></span>
  
<span data-ttu-id="82616-431">b) その次に、受信者の書き換えの一般的なユースケースを区別するようにします。</span><span class="sxs-lookup"><span data-stu-id="82616-431">b) Second, be sure to distinguish between common use cases of recipient rewrites.</span></span> <span data-ttu-id="82616-432">受信者のドメインを \*.onmicrosoft.com に書き換えようとしている場合は、そのドメインを \*.mail.onmicrosoft.com に書き換えます。</span><span class="sxs-lookup"><span data-stu-id="82616-432">If you are going to rewrite the recipient domain to \*.onmicrosoft.com, instead rewrite it to \*.mail.onmicrosoft.com.</span></span>
  
<span data-ttu-id="82616-433">別のサーバーの背後にルーティングされる最終的な受信者のドメインを特定し、その受信者のドメインの MX レコードが実際には Office 365 を指していることを特定したら、スプーフィング対策を無効にする作業を進めることができます。</span><span class="sxs-lookup"><span data-stu-id="82616-433">Once you have identified the final recipient domain that is routed behind another server and the recipient domain's MX record actually points to Office 365 (as published in its DNS records), you may proceed to disable anti-spoofing.</span></span>
  
<span data-ttu-id="82616-434">繰り返しになりますが、ルーティング パスでドメインの最初のホップが Office 365 の場合はスプーフィング対策を無効にしないでください (その前に 1 つ以上のサービスがある場合にのみ実行してください)。</span><span class="sxs-lookup"><span data-stu-id="82616-434">Remember, you don't want to disable anti-spoofing if the domain's first hop in the routing path is Office 365, only when it's behind one or more services.</span></span>
  
### <a name="how-to-disable-anti-spoofing"></a><span data-ttu-id="82616-435">スプーフィング対策を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="82616-435">How to disable anti-spoofing</span></span>

<span data-ttu-id="82616-436">フィッシング対策ポリシーが作成済みの場合は、EnableAntispoofEnforcement パラメーターを $false に設定します。</span><span class="sxs-lookup"><span data-stu-id="82616-436">If you already have an Anti-phishing policy created, set the EnableAntispoofEnforcement parameter to $false:</span></span>
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

<span data-ttu-id="82616-437">無効にするポリシーの名前がわからない場合は、次のようにして表示できます。</span><span class="sxs-lookup"><span data-stu-id="82616-437">If you don't know the name of the policy (or policies) to disable, you can display them:</span></span>
  
```
Get-AntiphishPolicy | fl Name
```

<span data-ttu-id="82616-438">既存のフィッシング対策ポリシーがない場合は、そのポリシーを作成してから無効にしてください (ポリシーがない場合でも、スプーフィング対策は適用されています。2018 年後半の時点で、既定のポリシーが自動で作成されるようになったため、既定のポリシーを作成することなく無効にできます)。</span><span class="sxs-lookup"><span data-stu-id="82616-438">If you don't have any existing anti-phishing policies, you can create one and then disable it (even if you don't have a policy, anti-spoofing is still applied; later on in 2018, a default policy will be created for you and you can then disable that instead of creating one).</span></span> <span data-ttu-id="82616-439">これは、複数の手順で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82616-439">You will have to do this in multiple steps:</span></span>
  
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
# Finally, scope the anti-phishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false

```

<span data-ttu-id="82616-440">スプーフィング対策は、コマンドレットでのみ無効化できます (将来は、セキュリティ/コンプライアンス センターでも可能になります)。</span><span class="sxs-lookup"><span data-stu-id="82616-440">Disabling anti-spoofing is only available via cmdlet (later it will be available in the Security &amp; Compliance Center).</span></span> <span data-ttu-id="82616-441">PowerShell にアクセスできない場合は、サポート チケットを作成してください。</span><span class="sxs-lookup"><span data-stu-id="82616-441">If you do not have access to PowerShell, create a support ticket.</span></span>
  
<span data-ttu-id="82616-442">繰り返しになりますが、この操作は、Office 365 への送信時に間接的にルーティングされるドメインにのみ適用してください。</span><span class="sxs-lookup"><span data-stu-id="82616-442">Remember, this should only be applied to domains that undergo indirect routing when sent to Office 365.</span></span> <span data-ttu-id="82616-443">ある程度の誤検出を理由にスプーフィング対策を無効にする誘惑には負けないようにしてください。長期的には、誤検出に対処するほうが好結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="82616-443">Resist the temptation to disable anti-spoofing because of some false positives, it will be better in the long run to work through them.</span></span>
  
### <a name="information-for-individual-users"></a><span data-ttu-id="82616-444">個々のユーザーに関する情報</span><span class="sxs-lookup"><span data-stu-id="82616-444">Information for individual users</span></span>

<span data-ttu-id="82616-445">個々のユーザーは、スプーフィング対策の安全のヒントに対する操作内容が制限されています。</span><span class="sxs-lookup"><span data-stu-id="82616-445">Individual users are limited in how they can interact with the anti-spoofing safety tip.</span></span> <span data-ttu-id="82616-446">ただし、一般的なシナリオを解決するために、いくつかのことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="82616-446">However, there are several things you can do to resolve common scenarios.</span></span>
  
### <a name="common-scenario-1---mailbox-forwarding"></a><span data-ttu-id="82616-447">一般的なシナリオ #1: メールボックスの転送</span><span class="sxs-lookup"><span data-stu-id="82616-447">Common scenario #1 - Mailbox forwarding</span></span>

<span data-ttu-id="82616-448">別の電子メール サービスを使用しているときに、Office 365 や Outlook.com に電子メールを転送すると、その電子メールにはスプーフィングのマークが付けられ、赤色の安全のヒントが示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="82616-448">If you use another email service and forward your email to Office 365 or Outlook.com, your email may be marked as spoofing and receive a red safety tip.</span></span> <span data-ttu-id="82616-449">Office 365 および Outlook.com では、フォワーダーが Outlook.com、Office 365、Gmail などの [ARC プロトコル](https://arc-spec.org)を使用するサービスの場合は、自動的にこの問題に対応する予定です。</span><span class="sxs-lookup"><span data-stu-id="82616-449">Office 365 and Outlook.com plan to address this automatically when the forwarder is one of Outlook.com, Office 365, Gmail, or any other service that uses the [ARC protocol](https://arc-spec.org).</span></span> <span data-ttu-id="82616-450">ただし、そのための修正プログラムが展開されるまでは、転送オプションを使用するのではなく、接続先アカウント機能を使用して、メッセージを直接インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82616-450">However, until that fix is deployed, users should use the Connected Accounts feature to import their messages directly, rather than using the forwarding option.</span></span>
  
<span data-ttu-id="82616-451">Office 365 の接続先アカウントを設定するには、Office 365 Web インターフェイスの右上にある歯車アイコン \> [メール] \> [メール] \> [アカウント] \> [接続されているアカウント] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="82616-451">To set up connected accounts in Office 365, select the Gear icon in the top right corner of the Office 365 web interface \> Mail \> Mail \> Accounts \> Connected accounts.</span></span>
  
![Office 365: [接続されているアカウント] オプション](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
<span data-ttu-id="82616-453">Outlook.com の場合は、歯車アイコン \> [オプション] \> [メール] \> [アカウント] \> [接続されているアカウント] の順に進みます。</span><span class="sxs-lookup"><span data-stu-id="82616-453">In Outlook.com, the process is the Gear icon \> Options \> Mail \> Accounts \> Connected accounts.</span></span>
  
### <a name="common-scenario-2---discussion-lists"></a><span data-ttu-id="82616-454">一般的なシナリオ #2: ディスカッション リスト</span><span class="sxs-lookup"><span data-stu-id="82616-454">Common scenario #2 - Discussion lists</span></span>

<span data-ttu-id="82616-455">ディスカッション リストには、スプーフィング対策に関する既知の問題があります。このリストは、メッセージを転送して、その内容を変更するにもかかわらず元の From: アドレスが保持されるという方法に問題の原因があります。</span><span class="sxs-lookup"><span data-stu-id="82616-455">Discussion lists are known to have problems with anti-spoofing due to the way they forward the message and modify its contents yet retain the original From: address.</span></span>
  
<span data-ttu-id="82616-456">たとえば、自分の電子メール アドレスが user @ contoso.com で、バード ウォッチングに興味があり、ディスカッション リスト birdwatchers @ example.com に参加するとします。</span><span class="sxs-lookup"><span data-stu-id="82616-456">For example, suppose your email address is user @ contoso.com, and you are interested in Bird Watching and join the discussion list birdwatchers @ example.com.</span></span> <span data-ttu-id="82616-457">このディスカッション リストにメッセージを送信するときには、次の方法で送信することになります。</span><span class="sxs-lookup"><span data-stu-id="82616-457">When you send a message to the discussion list, you might send it this way:</span></span>
  
<span data-ttu-id="82616-458">**From:** John Doe \<user @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="82616-458">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="82616-459">**宛先:** Birdwatcher のディスカッション リスト \<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="82616-459">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="82616-460">**件名:** 今週、レーニア山からアオカケス</span><span class="sxs-lookup"><span data-stu-id="82616-460">**Subject:** Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="82616-461">を見ることができます</span><span class="sxs-lookup"><span data-stu-id="82616-461">Rainier this week</span></span> 
  
<span data-ttu-id="82616-462">今週、レーニア山からの風景を</span><span class="sxs-lookup"><span data-stu-id="82616-462">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="82616-463">眺めてみませんか?</span><span class="sxs-lookup"><span data-stu-id="82616-463">Rainier?</span></span>
  
<span data-ttu-id="82616-464">電子メール リストはメッセージを受信すると、そのメッセージの書式を設定し、内容を変更して、ディスカッション リストの残りのメンバーに向けてメッセージをリプレイします。このメンバーは、多様な電子メール レシーバーから構成されています。</span><span class="sxs-lookup"><span data-stu-id="82616-464">When the email list receives the message, they format the message, modify its contents, and replay it to the rest of the members on the discussion list which is made up of participants from many different email receivers.</span></span>
  
<span data-ttu-id="82616-465">**From:** John Doe \<user @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="82616-465">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="82616-466">**宛先:** Birdwatcher のディスカッション リスト \<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="82616-466">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="82616-467">**件名:** [BIRDWATCHERS] 今週、レーニア山からアオカケス</span><span class="sxs-lookup"><span data-stu-id="82616-467">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="82616-468">を見ることができます</span><span class="sxs-lookup"><span data-stu-id="82616-468">Rainier this week</span></span> 
  
<span data-ttu-id="82616-469">今週、レーニア山からの風景を</span><span class="sxs-lookup"><span data-stu-id="82616-469">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="82616-470">眺めてみませんか?</span><span class="sxs-lookup"><span data-stu-id="82616-470">Rainier?</span></span>
  
---
  
<span data-ttu-id="82616-471">このメッセージは、Birdwatchers ディスカッション リストに送信されました。</span><span class="sxs-lookup"><span data-stu-id="82616-471">This message was sent to the Birdwatchers Discussion List.</span></span> <span data-ttu-id="82616-472">いつでも購読を解除できます。</span><span class="sxs-lookup"><span data-stu-id="82616-472">You can unsubscribe to the newsletter at any time.</span></span>
  
<span data-ttu-id="82616-473">上記のリプレイされたメッセージには、同じ From: アドレス (user @ contoso.com) がありますが、元のメッセージは件名にタグを追加して、メッセージの下側にフッターを追加することで変更されています。</span><span class="sxs-lookup"><span data-stu-id="82616-473">In the above, the replayed message has the same From: address (user @ contoso.com) but the original message has been modified by adding a tag to the Subject line, and a footer to the bottom of the message.</span></span> <span data-ttu-id="82616-474">この種のメッセージの変更は、メーリング リストでは一般的なものですが、誤検出の原因になることがあります。</span><span class="sxs-lookup"><span data-stu-id="82616-474">This type of message modification is common in mailing lists, and may result in false positives.</span></span>
  
<span data-ttu-id="82616-475">組織内のいずれかのユーザーがメーリング リストの管理者になっている場合は、そのメーリング リストがスプーフィング対策をパスするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="82616-475">If you or someone in your organization is an administrator of the mailing list, you may be able to configure it to pass anti-spoofing checks.</span></span>
  
- <span data-ttu-id="82616-476">DMARC.org で次のよくある質問を確認してください: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span><span class="sxs-lookup"><span data-stu-id="82616-476">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span></span>

- <span data-ttu-id="82616-477">次のブログ記事の手順を参照してください: [DMARC との相互運用で失敗を回避するためのメーリング リスト運営者向けのヒント](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span><span class="sxs-lookup"><span data-stu-id="82616-477">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span></span>

- <span data-ttu-id="82616-478">メーリング リスト サーバーに ARC をサポートする更新プログラムをインストールすることを検討してください ([https://arc-spec.org](https://arc-spec.org/) を参照)</span><span class="sxs-lookup"><span data-stu-id="82616-478">Consider installing updates on your mailing list server to support ARC, see [https://arc-spec.org](https://arc-spec.org/)</span></span>

<span data-ttu-id="82616-479">メーリング リストの所有者でない場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="82616-479">If you do not have ownership of the mailing list:</span></span>
  
- <span data-ttu-id="82616-480">メーリング リストの管理者に、上記のいずれかのオプションを実装するように要求してください (この管理者は、メーリング リストを中継するドメインにも電子メール認証を設定する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="82616-480">You can request the maintainer of the mailing list to implement one of the options above (they should also have email authentication set up for the domain the mailing list is relaying from)</span></span>

- <span data-ttu-id="82616-481">電子メール クライアントで、メッセージを受信トレイに移動するメールボックス ルールを作成してください。</span><span class="sxs-lookup"><span data-stu-id="82616-481">You can create mailbox rules in your email client to move messages to the Inbox.</span></span> <span data-ttu-id="82616-482">また、組織の管理者に許可ルールを設定するように要求するか、「認証されていない電子メールを送信する正当な送信者の管理」のセクションで説明するようにオーバーライドするように要求してください。</span><span class="sxs-lookup"><span data-stu-id="82616-482">You can also request your organization's administrators to set up allow rules, or overrides as discussed in the section Managing legitimate senders who are sending unauthenticated email</span></span>

- <span data-ttu-id="82616-483">Office 365 でサポート チケットを作成して、メーリング リストを正当なものとして扱うためのオーバーライドを作成してください。</span><span class="sxs-lookup"><span data-stu-id="82616-483">You can create a support ticket with Office 365 to create an override for the mailing list to treat it as legitimate</span></span>

### <a name="other-scenarios"></a><span data-ttu-id="82616-484">その他のシナリオ</span><span class="sxs-lookup"><span data-stu-id="82616-484">Other scenarios</span></span>

1. <span data-ttu-id="82616-485">上記の一般的なシナリオのいずれにも当てはまらない場合は、そのメッセージを誤検出として Microsoft に報告してください。</span><span class="sxs-lookup"><span data-stu-id="82616-485">If neither of the above common scenarios applies to your situation, report the message as a false positive back to Microsoft.</span></span> <span data-ttu-id="82616-486">詳細については、この記事で後述する「[スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-486">For more information, see the section [How can I report spam or non-spam messages back to Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) later in this article.</span></span> 

2. <span data-ttu-id="82616-487">また、サポート チケットとして Microsoft にこの件を提出できる電子メール管理者に問い合わせることもできます。</span><span class="sxs-lookup"><span data-stu-id="82616-487">You may also contact your email administrator who can raise it as a support ticket with Microsoft.</span></span> <span data-ttu-id="82616-488">Microsoft のエンジニアリング チームは、メッセージにスプーフィングのマークが付けられた理由を調査します。</span><span class="sxs-lookup"><span data-stu-id="82616-488">The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>

3. <span data-ttu-id="82616-489">さらに、送信者がわかっていて、悪意のあるスプーフィングでないと確信している場合は、送信者に、認証されていないメール サーバーからメッセージを送信していることを返信で知らせてください。</span><span class="sxs-lookup"><span data-stu-id="82616-489">Additionally, if you know who the sender is and are confident they are not being maliciously spoofed, you may reply back to the sender indicating that they are sending messages from a mail server that does not authenticate.</span></span> <span data-ttu-id="82616-490">これにより、元の送信者は要求された電子メール認証レコードを設定する IT 管理者に問い合わせることもあります。</span><span class="sxs-lookup"><span data-stu-id="82616-490">This sometimes results in the original sender contacting their IT administrator who will set up the required email authentication records.</span></span>
  
<span data-ttu-id="82616-491">ドメインの所有者に対して相当数の送信者が電子メール認証レコードの設定が必要なことを返信することで、ドメインの所有者の行動を促します。</span><span class="sxs-lookup"><span data-stu-id="82616-491">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action.</span></span> <span data-ttu-id="82616-492">Microsoft は必要なレコードを公開するためにドメインの所有者と協力しますが、個々のユーザーの要求が大きな支援になります。</span><span class="sxs-lookup"><span data-stu-id="82616-492">While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>

4. <span data-ttu-id="82616-493">必要に応じて、送信者を [差出人セーフ リスト] に追加します。</span><span class="sxs-lookup"><span data-stu-id="82616-493">Optionally, add the sender to your Safe Senders list.</span></span> <span data-ttu-id="82616-494">ただし、そのアカウントをフィッシャーがスプーフィングすると、それが自分のメールボックスに配信される点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="82616-494">However, be aware that if a phisher spoofs that account, it will be delivered to your mailbox.</span></span> <span data-ttu-id="82616-495">そのため、このオプションは慎重に使用してください。</span><span class="sxs-lookup"><span data-stu-id="82616-495">Therefore, this option should be used sparingly.</span></span>

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a><span data-ttu-id="82616-496">スプーフィング対策保護に対して Microsoft への送信者が必要になる準備</span><span class="sxs-lookup"><span data-stu-id="82616-496">How senders to Microsoft should prepare for anti-spoofing protection</span></span>

<span data-ttu-id="82616-497">現在、Microsoft (Office 365 または Outlook.com) にメッセージを送信する管理者は、電子メールが適切に認証されていることを確認する必要があります。そうしていないと、そのメールにはスパムまたはフィッシングのマークが付けられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82616-497">If you are an administrator who currently sends messages to Microsoft, either Office 365 or Outlook.com, you should ensure that your email is properly authenticated otherwise it may be marked as spam or phish.</span></span>
  
### <a name="customers-of-office-365"></a><span data-ttu-id="82616-498">Office 365 のユーザー</span><span class="sxs-lookup"><span data-stu-id="82616-498">Customers of Office 365</span></span>

<span data-ttu-id="82616-499">Office 365 のユーザーが Office 365 を使用して送信メールを送信する場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="82616-499">If you are an Office 365 customer and you use Office 365 to send outbound email:</span></span>
  
- <span data-ttu-id="82616-500">ドメインについては、[スプーフィングを防止するために Office 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="82616-500">[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</span></span>

- <span data-ttu-id="82616-501">プライマリ ドメインについては、[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="82616-501">[Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md)</span></span>

- <span data-ttu-id="82616-502">正当な送信者を判断するために、ドメインに [DMARC レコードを設定することを検討する](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="82616-502">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine who are your legitimate senders</span></span>

<span data-ttu-id="82616-503">Microsoft は、SPF、DKIM、および DMARC のそれぞれに関する詳細な実装ガイドラインを提供しません。</span><span class="sxs-lookup"><span data-stu-id="82616-503">Microsoft does not provide detailed implementation guidelines for each of SPF, DKIM, and DMARC.</span></span> <span data-ttu-id="82616-504">ただし、オンラインで公開されている大量の情報があります。</span><span class="sxs-lookup"><span data-stu-id="82616-504">However, there is a lot of information published online.</span></span> <span data-ttu-id="82616-505">また、組織が電子メール認証レコードを設定する際の支援を専門としているサード パーティ企業もあります。</span><span class="sxs-lookup"><span data-stu-id="82616-505">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a><span data-ttu-id="82616-506">Office 365 のユーザーではないドメインの管理者</span><span class="sxs-lookup"><span data-stu-id="82616-506">Administrators of domains that are not Office 365 customers</span></span>

<span data-ttu-id="82616-507">Office 365 のユーザーではないドメインの管理者は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="82616-507">If you are a domain administrator but are not an Office 365 customer:</span></span>
  
- <span data-ttu-id="82616-508">SPF を設定してドメインの送信側 IP アドレスを公開する必要があります。また、DKIM (使用可能な場合) を設定してメッセージにデジタル署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82616-508">You should set up SPF to publish your domain's sending IP addresses, and also set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="82616-509">さらに、DMARC レコードを設定することも検討してください。</span><span class="sxs-lookup"><span data-stu-id="82616-509">You may also consider setting up DMARC records.</span></span>

- <span data-ttu-id="82616-510">自分の代りに電子メールを転送するバルク送信者がいる場合は、その送信者と協力して、From: アドレスの送信側ドメインが SPF または DMARC をパスするドメインと一致するような方法で電子メールを送信する必要があります (送信側ドメインを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="82616-510">If you have bulk senders who are transmitting email on your behalf, you should work with them to send email in a way such that the sending domain in the From: address (if it belongs to you) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="82616-511">オンプレミスのメール サーバーがある場合、またはサービスとしてのソフトウェア プロバイダーや、クラウド ホスティング サービス (Microsoft Azure、GoDaddy、Rackspace、アマゾン ウェブ サービスなど) からメールを送信する場合は、それらを SPF レコードに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82616-511">If you have on-premises mail servers, or send from a Software-as-a-service provider, or from a cloud-hosting service like Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, or similar, you should ensure that they are added to your SPF record.</span></span>

- <span data-ttu-id="82616-512">ISP でホストされている小規模ドメインの場合は、その ISP が用意した手順に従って SPF レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82616-512">If you are a small domain that is hosted by an ISP, you should set up your SPF record according to the instructions that is provided to you by your ISP.</span></span> <span data-ttu-id="82616-513">ほとんどの ISP は、この種の手順を用意していて、その会社のサポート ページに掲載しています。</span><span class="sxs-lookup"><span data-stu-id="82616-513">Most ISPs provide these types of instructions and can be found on the company's support pages.</span></span>

- <span data-ttu-id="82616-514">これまでは電子メール認証レコードを公開する必要がなく、問題なく機能していたとしても、Microsoft に電子メールを送信するには電子メール認証レコードの公開が必要になります。</span><span class="sxs-lookup"><span data-stu-id="82616-514">Even if you have not had to publish email authentication records before, and it worked fine, you must still publish email authentication records to send to Microsoft.</span></span> <span data-ttu-id="82616-515">そうすることが、フィッシング詐欺の撲滅に協力することになり、自分やメール送信先の組織がフィッシング詐欺の被害を受ける可能性を減らすことになります。</span><span class="sxs-lookup"><span data-stu-id="82616-515">By doing so, you are helping in the fight against phishing, and reducing the possibility that either you, or organizations you send to, will get phished.</span></span>

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a><span data-ttu-id="82616-516">自分のドメインとして電子メールを送信した送信者がわからない場合</span><span class="sxs-lookup"><span data-stu-id="82616-516">What if you don't know who sends email as your domain?</span></span>

<span data-ttu-id="82616-517">多くのドメインは、すべての送信者を把握しているわけではないため、SPF レコードを公開していません。</span><span class="sxs-lookup"><span data-stu-id="82616-517">Many domains do not publish SPF records because they do not know who all their senders are.</span></span> <span data-ttu-id="82616-518">そのことは問題になりません。すべての送信者がわかっている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="82616-518">That's okay, you do not need to know who all of them are.</span></span> <span data-ttu-id="82616-519">その代りに、自分が知っているもの、特に会社のトラフィックがある場所の SPF レコードを公開することから始めて、次のニュートラル SPF ポリシー (?all) を公開します。</span><span class="sxs-lookup"><span data-stu-id="82616-519">Instead, you should get started by publishing an SPF record for the ones you do know of, especially where your corporate traffic is located, and publish a neutral SPF policy, ?all:</span></span>
  
<span data-ttu-id="82616-520">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span><span class="sxs-lookup"><span data-stu-id="82616-520">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span></span>
  
<span data-ttu-id="82616-521">ニュートラル ポリシーとは、会社のインフラストラクチャから送信されるすべての電子メールが、その他すべての電子メール レシーバーの場所で電子メール認証にパスするという意味です。</span><span class="sxs-lookup"><span data-stu-id="82616-521">The neutral SPF policy means that any email that comes out of your corporate infrastructure will pass email authentication at all other email receivers.</span></span> <span data-ttu-id="82616-522">不明な送信者から送られた電子メールは、ニュートラルにフォールバックします。これは、SPF レコードをまったく公開していないこととほとんど同じです。</span><span class="sxs-lookup"><span data-stu-id="82616-522">Email that comes from senders you don't know about will fall back to neutral, which is almost the same as publishing no SPF record at all.</span></span>
  
<span data-ttu-id="82616-523">Office 365 への送信時、会社のトラフィックから送信された電子メールには認証済みのマークが付けられますが、不明な送信元から送信された電子メールには引き続きスプーフィングのマークが付けられることがあります (Office 365 によって暗黙的に認証できるかどうかによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="82616-523">When sending to Office 365, email that comes from your corporate traffic will be marked as authenticated, but the email that comes from sources you don't know about may still be marked as spoof (depending upon whether or not Office 365 can implicitly authenticate it).</span></span> <span data-ttu-id="82616-524">ただし、これは Office 365 によってすべての電子メールにスプーフィングのマークが付けられることからの改善に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="82616-524">However, this is still an improvement from all email being marked as spoof by Office 365.</span></span>
  
<span data-ttu-id="82616-525">フォールバック ポリシーが ?all の SPF レコードを出発点として、段階的に送信側インフラストラクチャを増強して、より厳密なポリシーを公開してください。</span><span class="sxs-lookup"><span data-stu-id="82616-525">Once you've gotten started with an SPF record with a fallback policy of ?all, you can gradually include more and more sending infrastructure and then publish a stricter policy.</span></span> 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a><span data-ttu-id="82616-526">メーリング リストの所有者の場合</span><span class="sxs-lookup"><span data-stu-id="82616-526">What if you are the owner of a mailing list?</span></span>

<span data-ttu-id="82616-527">セクション「[一般的なシナリオ #2: ディスカッション リスト](#common-scenario-2---discussion-lists)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-527">See the section [Common scenario #2 - Discussion lists](#common-scenario-2---discussion-lists).</span></span>
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a><span data-ttu-id="82616-528">インターネット サービス プロバイダー (ISP)、電子メール サービス プロバイダー (ESP)、クラウド ホスティング サービスなどのインフラストラクチャ プロバイダーの場合</span><span class="sxs-lookup"><span data-stu-id="82616-528">What if you are an infrastructure provider such as an Internet Service Provider (ISP), Email Service Provider (ESP), or cloud hosting service?</span></span>

<span data-ttu-id="82616-529">ドメインの電子メールをホストしていて、そのドメインで電子メールを送信する場合、または電子メールを送信できるホスティング インフラストラクチャを提供している場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="82616-529">If you host a domain's email, and it sends email, or provide hosting infrastructure that can send email, you should do the following:</span></span>
  
- <span data-ttu-id="82616-530">顧客に SPF レコードで公開する内容の詳細についてのドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="82616-530">Ensure your customers have documentation detailing what to publish in their SPF records</span></span>

- <span data-ttu-id="82616-531">顧客が明示的に設定していない場合でも、送信電子メールの DKIM 署名に署名することを検討します (既定のドメインで署名)。</span><span class="sxs-lookup"><span data-stu-id="82616-531">Consider signing DKIM-signatures on outbound email even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="82616-532">DKIM 署名では電子メールに二重署名することもできます (顧客のドメインで設定されている場合に 1 つ目の署名、会社の DKIM 署名で 2 つ目の署名)。</span><span class="sxs-lookup"><span data-stu-id="82616-532">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="82616-533">プラットフォームから送信された電子メールを認証していても Microsoft への配信が可能であることが保証されるわけではありませんが、少なくとも、認証されていないという理由で Microsoft がそのメールを迷惑メールとして処理することはなくなります。</span><span class="sxs-lookup"><span data-stu-id="82616-533">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it is not authenticated.</span></span> <span data-ttu-id="82616-534">Outlook.com での電子メールのフィルター処理に関する詳細については、[Outlook.com Postmaster ページ](https://postmaster.live.com/pm/postmaster.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-534">For more details around how Outlook.com filters email, see the [Outlook.com Postmaster page](https://postmaster.live.com/pm/postmaster.aspx).</span></span>
  
<span data-ttu-id="82616-535">サービス プロバイダーのベスト プラクティスの詳細については、「[M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-535">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
  
## <a name="frequently-asked-questions"></a><span data-ttu-id="82616-536">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="82616-536">Frequently Asked Questions</span></span>

### <a name="why-is-microsoft-making-this-change"></a><span data-ttu-id="82616-537">Microsoft が今回の変更を行う理由</span><span class="sxs-lookup"><span data-stu-id="82616-537">Why is Microsoft making this change?</span></span>

<span data-ttu-id="82616-538">フィッシング攻撃の影響により、15 年以上前から電子メール認証が実施されているため、Microsoft は認証されていない電子メールを許可し続けるリスクのほうが、正当な電子メールを失うリスクよりも高いと判断しています。</span><span class="sxs-lookup"><span data-stu-id="82616-538">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continue to allow unauthenticated email is higher than the risk of losing legitimate email.</span></span>
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="82616-539">今回の変更により正当なメールにスパムのマークが付けられることがありますか</span><span class="sxs-lookup"><span data-stu-id="82616-539">Will this change cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="82616-540">当初は、一部のメッセージにスパムのマークが付けられるようになります。</span><span class="sxs-lookup"><span data-stu-id="82616-540">At first, there will be some messages that are marked as spam.</span></span> <span data-ttu-id="82616-541">ただし、時間の経過と共に、送信者が適応するようになり、ほとんどのメール パスでスプーフィングとして間違ったラベルが付けられるメッセージの量は無視できる程度になります。</span><span class="sxs-lookup"><span data-stu-id="82616-541">However, over time, senders will adjust and then the amount of messages mislabeled as spoofed will be negligible for most email paths.</span></span>
  
<span data-ttu-id="82616-542">Microsoft は、この機能をお客様に展開する数週間前に率先して導入しました。</span><span class="sxs-lookup"><span data-stu-id="82616-542">Microsoft itself first adopted this feature several weeks before deploying it to the rest of its customers.</span></span> <span data-ttu-id="82616-543">最初のうちは混乱もありましたが、それも次第に収まりました。</span><span class="sxs-lookup"><span data-stu-id="82616-543">While there was disruption at first, it gradually declined.</span></span>
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a><span data-ttu-id="82616-544">Microsoft は、この機能を Outlook.com と Advanced Threat Protection のない Office 365 ユーザーに導入しますか</span><span class="sxs-lookup"><span data-stu-id="82616-544">Will Microsoft bring this feature to Outlook.com and non-Advanced Threat Protection customers of Office 365?</span></span>

<span data-ttu-id="82616-545">Microsoft のスプーフィング対策テクノロジは、最初に Office 365 Enterprise E5 サブスクリプションを所有する組織、またはサブスクリプションに対応する Office 365 Advanced Threat Protection (ATP) アドオンを購入した組織に導入されました。</span><span class="sxs-lookup"><span data-stu-id="82616-545">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span> <span data-ttu-id="82616-546">2018 年 10 月の時点では、Exchange Online Protection (EOP) の所有組織にも保護の範囲を広げました。</span><span class="sxs-lookup"><span data-stu-id="82616-546">As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well.</span></span> <span data-ttu-id="82616-547">今後は、Outlook.com にもリリースする予定です。</span><span class="sxs-lookup"><span data-stu-id="82616-547">In the future, we may release it for Outlook.com.</span></span> <span data-ttu-id="82616-548">ただし、その場合は、レポートやカスタム オーバーライドなどの一部の機能が適用されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82616-548">However, if we do, there may be some capabilities that are not applied such as reporting and custom overrides.</span></span>
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="82616-549">スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか</span><span class="sxs-lookup"><span data-stu-id="82616-549">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="82616-550">[Outlook 用の迷惑メール報告アドイン](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を使用できます。このアドインをインストールしていない場合は、[スパム、非スパム、およびフィッシング詐欺メッセージを分析のために Microsoft に送信する](https://technet.microsoft.com/ja-JP/library/jj200769%28v=exchg.150%29.aspx)こともできます。</span><span class="sxs-lookup"><span data-stu-id="82616-550">You can either use the [Report Message Add-in for Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), or if it isn't installed, [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://technet.microsoft.com/ja-JP/library/jj200769%28v=exchg.150%29.aspx).</span></span>
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a><span data-ttu-id="82616-551">ドメイン管理者ですが、把握できていない送信者がいます</span><span class="sxs-lookup"><span data-stu-id="82616-551">I'm a domain administrator who doesn't know who all my senders are!</span></span>

<span data-ttu-id="82616-552">「[Office 365 のユーザーではないドメインの管理者](#administrators-of-domains-that-are-not-office-365-customers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82616-552">Please see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers).</span></span>
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a><span data-ttu-id="82616-553">Office 365 がプライマリ フィルターだとしても、自分の組織のスプーフィング対策保護を無効にすると問題が発生しますか</span><span class="sxs-lookup"><span data-stu-id="82616-553">What happens if I disable anti-spoofing protection for my organization, even though Office 365 is my primary filter?</span></span>

<span data-ttu-id="82616-554">これについては、お勧めできません。より多くの見逃されたフィッシング メッセージやスパム メッセージにさらされるようになります。</span><span class="sxs-lookup"><span data-stu-id="82616-554">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="82616-555">すべてのフィッシングがスプーフィングであるわけでなく、すべてのスプーフィングが見逃されるわけでもありません。</span><span class="sxs-lookup"><span data-stu-id="82616-555">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="82616-556">ただし、スプーフィング対策を有効にしているお客様よりもリスクは高くなります。</span><span class="sxs-lookup"><span data-stu-id="82616-556">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="82616-557">スプーフィング対策保護を有効にすることで、すべてのフィッシングから保護されるようになりますか</span><span class="sxs-lookup"><span data-stu-id="82616-557">Does enabling anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="82616-558">残念ながら、そうはなりません。フィッシャーは侵害されたアカウントやフリー サービスのアカウントを設定するなど、別の手法を採用するようになるためです。</span><span class="sxs-lookup"><span data-stu-id="82616-558">Unfortunately, no, because phishers will adapt to use other techniques such as compromised accounts, or setting up accounts of free services.</span></span> <span data-ttu-id="82616-559">ただし、Office 365 の各保護層は連携するように設計されていて、相互をベースとして構築されているため、フィッシング対策保護は、そのような別の種類のフィッシング方法の検出にも優れています。</span><span class="sxs-lookup"><span data-stu-id="82616-559">However, anti-phishing protection works much better to detect these other types of phishing methods because Office 365's protection layers are designed work together and build on top of each other.</span></span>
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a><span data-ttu-id="82616-560">他の大規模な電子メール レシーバーが認証されていない電子メールをブロックすることはありますか</span><span class="sxs-lookup"><span data-stu-id="82616-560">Do other large email receivers block unauthenticated email?</span></span>

<span data-ttu-id="82616-561">ほとんどすべての大規模電子メール レシーバーが、従来型の SPF、DKIM、および DMARC を実装してます。</span><span class="sxs-lookup"><span data-stu-id="82616-561">Nearly all large email receivers implement traditional SPF, DKIM, and DMARC.</span></span> <span data-ttu-id="82616-562">一部のレシーバーは、そうした標準のものよりも厳密な別のチェックを実施していますが、認証されていない電子メールをブロックしてスプーフィングとして扱う Office 365 に匹敵するものはわずかしかありません。</span><span class="sxs-lookup"><span data-stu-id="82616-562">Some receivers have other checks that are more strict than just those standards, but few go as far as Office 365 to block unauthenticated email and treat them as a spoof.</span></span> <span data-ttu-id="82616-563">ただし、この業界のほとんどが、特にフィッシング詐欺の問題を理由に、この種の電子メールに対する厳しさを増しています。</span><span class="sxs-lookup"><span data-stu-id="82616-563">However, most of the industry is becoming more and more strict about this particular type of email, particularly because of the problem of phishing.</span></span>
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a><span data-ttu-id="82616-564">スプーフィング対策を有効にしていても、"SPF Hard Fail" に対して高度な迷惑メール フィルターのオプションを有効にする必要がありますか</span><span class="sxs-lookup"><span data-stu-id="82616-564">Do I still need the Advanced Spam Filtering option enabled for "SPF Hard Fail" if I enable anti-spoofing?</span></span>

<span data-ttu-id="82616-565">いいえ。このオプションは不要になりました。スプーフィング対策機能では、SPF hard fail だけでなく、それよりも広範な条件のセットが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="82616-565">No, this option is no longer required because the anti-spoofing feature not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="82616-566">スプーフィング対策を有効にしているときに、SPF Hard Fail オプションも有効にすると、誤検出が多くなく可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82616-566">If you have anti-spoofing enabled and the SPF Hard Fail option enabled, you will probably get more false positives.</span></span> <span data-ttu-id="82616-567">この機能は無効にすることをお勧めします。この機能によって、追加で捕捉されるスパムやフィッシングはほとんどなく、多くの場合に誤検出が発生します。</span><span class="sxs-lookup"><span data-stu-id="82616-567">We recommend disabling this feature as it would provide almost no additional catch for spam or phish, and instead generate mostly false positives.</span></span>
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a><span data-ttu-id="82616-568">センダー リライティング スキーム (SRS) は転送された電子メールの問題修正に役立ちますか</span><span class="sxs-lookup"><span data-stu-id="82616-568">Does Sender Rewriting Scheme (SRS) help fix forwarded email?</span></span>

<span data-ttu-id="82616-569">SRS は転送された電子メールの問題を部分的にしか解決しません。</span><span class="sxs-lookup"><span data-stu-id="82616-569">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="82616-570">SMTP MAIL FROM を書き換えることで、SRS では転送されたメッセージが次の宛先で確実に SPF をパスするようになります。</span><span class="sxs-lookup"><span data-stu-id="82616-570">By rewriting the SMTP MAIL FROM, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="82616-571">ただし、スプーフィング対策は MAIL FROM または DKIM 署名のドメイン (またはその他のシグナル) と組み合わせた From: アドレスに基づいているため、転送された電子メールにスプーフィングのマークが付けられることを回避するには不十分です。</span><span class="sxs-lookup"><span data-stu-id="82616-571">However, because anti-spoofing is based upon the From: address in combination with either the MAIL FROM or DKIM-signing domain (or other signals), it is not enough to prevent forwarded email from being marked as spoofed.</span></span>