---
title: Office 365 に送信される迷惑メールへの対処
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
ms.collection:
- M365-security-compliance
description: Microsoft のメールの安全性ロードマップには、他に例を見ない製品間のアプローチが含まれます。Exchange Online Protection (EOP) のスパム対策とフィッシング対策のフィルタリング テクノロジは、Microsoft のメール プラットフォーム全体に適用され、最新のスパム対策とフィッシング策のツール、およびネットワーク全体にわたる技術革新をユーザーに提供しています。 EOP の目標は、包括的で使用可能なメール サービスを提供し、迷惑メール、詐欺目的のメールの脅威 (フィッシング)、マルウェアを検出し、それらからユーザーを保護することです。
ms.openlocfilehash: 0a73d428e952c0c0cb340d91a52768a42ae204a1
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599393"
---
# <a name="fighting-junk-email-sent-to-office-365"></a><span data-ttu-id="04d37-105">Office 365 に送信される迷惑メールへの対処</span><span class="sxs-lookup"><span data-stu-id="04d37-105">Fighting junk email sent to Office 365</span></span>

<span data-ttu-id="04d37-p102">Microsoft のメールの安全性ロードマップには、他に例を見ない製品間のアプローチが含まれます。Exchange Online Protection (EOP) のスパム対策とフィッシング対策のフィルタリング テクノロジは、Microsoft のメール プラットフォーム全体に適用され、最新のスパム対策とフィッシング策のツール、およびネットワーク全体にわたる技術革新をユーザーに提供しています。 EOP の目標は、包括的で使用可能なメール サービスを提供し、迷惑メール、詐欺目的のメールの脅威 (フィッシング)、マルウェアを検出し、それらからユーザーを保護することです。</span><span class="sxs-lookup"><span data-stu-id="04d37-p102">Microsoft's email safety roadmap involves an unmatched cross-product approach. Exchange Online Protection (EOP) anti-spam and anti-phishing filtering technology is being applied across Microsoft's email platforms to provide users with the latest anti-spam and anti-phishing tools and innovations throughout the network. The goal for EOP is to offer a comprehensive and usable email service that helps detect and protect users from junk email, fraudulent email threats (phishing), and malware.</span></span>
  
## <a name="the-challenge"></a><span data-ttu-id="04d37-109">課題</span><span class="sxs-lookup"><span data-stu-id="04d37-109">The challenge</span></span>

<span data-ttu-id="04d37-p103">メールは、コンシューマーだけでなく、マーケティング担当者、サポート スタッフ、販売組織、あらゆる規模の企業にとっても、重要なコミュニケーション ツールとなっています。メールの使用が増えるにつれ、メールの不正使用も増えました。監視されていない迷惑メールによって、受信トレイとネットワークに余分な負荷が掛かり、ユーザー満足度に影響を及ぼし、正当なメール通信の効果が阻害されます。これが Microsoft がスパム対策テクノロジへの投資を継続する理由です。簡単に言えば、迷惑メールを格納して、フィルター処理することから始めます。 </span><span class="sxs-lookup"><span data-stu-id="04d37-p103">Email has become an important communication tool not only for consumers but also for marketers, support staff, sales organizations, and businesses of all sizes. As email use has grown, so has email abuse. Unmonitored junk email can clog inboxes and networks, impact user satisfaction, and hamper the effectiveness of legitimate email communications. That's why Microsoft continues to invest in anti-spam technologies. Simply put, it starts by containing and filtering junk email.</span></span> 
  
## <a name="our-efforts"></a><span data-ttu-id="04d37-115">取り組み</span><span class="sxs-lookup"><span data-stu-id="04d37-115">Our efforts</span></span>

<span data-ttu-id="04d37-116">EOP には、ユーザーのメールの使用に対して迷惑メールが与える悪影響を最小限に抑えるための手順が数多く用意されています。</span><span class="sxs-lookup"><span data-stu-id="04d37-116">EOP offers a number of steps to minimize the negative impact junk email has on our users' email experience.</span></span>
  
### <a name="exchange-online-protection-technology"></a><span data-ttu-id="04d37-117">Exchange Online Protection のテクノロジ</span><span class="sxs-lookup"><span data-stu-id="04d37-117">Exchange Online Protection technology</span></span>

<span data-ttu-id="04d37-p104">迷惑メールを減らすため、EOP には独自の EOP フィルタリング テクノロジを使った迷惑メールからの保護が含まれています。このテクノロジはメールを検査して、迷惑メールを識別し、正当なメールと区別します。EOP のコンテンツ フィルターは、既知のスパムとフィッシングの脅威、コンシューマー プラットフォームである Outlook.com からのユーザー フィードバックから学習します。これらの種類のデータは、EOP テクノロジが正当なメールと迷惑メールを認識するためのトレーニングになり、送信者評価へのキーになる情報源でもあります。迷惑メール分類プログラムの EOP ユーザーからの継続的なフィードバックにより、EOP テクノロジは今後もトレーニングを続け、改善を図っていきます。</span><span class="sxs-lookup"><span data-stu-id="04d37-p104">To help reduce junk email, EOP includes junk email protection using proprietary EOP filtering technologies which screen email to identify and separate junk email from legitimate email. The EOP content filter learns from known spam and phishing threats and user feedback from our consumer platform, Outlook.com. These types of data help train EOP technologies to recognize legitimate email and junk email and are key inputs into sender reputation. Ongoing feedback from EOP users in the junk email classification program helps ensure that the EOP technologies are continually trained and improved.</span></span>
  
#### <a name="how-does-eop-work"></a><span data-ttu-id="04d37-122">EOP のしくみ</span><span class="sxs-lookup"><span data-stu-id="04d37-122">How does EOP work?</span></span>

<span data-ttu-id="04d37-p105">外部ユーザーが EOP ユーザーにメール メッセージを送信すると、EOP フィルタリング テクノロジは、メッセージの内容を評価し、メッセージが迷惑メールかどうかの確率に基づいてメッセージにレベルを割り当てます。このレベルは、Spam Confidence Level (SCL) と呼ばれるメッセージ プロパティとして、メッセージに直接格納されます。SCL レベルは、EOP 内の他のスパム対策保護層に送信されるときのまま、メッセージと共に維持されます。</span><span class="sxs-lookup"><span data-stu-id="04d37-p105">When an external user sends an email message to an EOP user, EOP filtering technologies evaluate the content of the message and assigns a rating to the message based on the probability that the message is junk email. This rating is stored as a message property called a Spam Confidence Level (SCL) within the message itself. The SCL rating stays with the message as it is sent to other anti-spam protection layers within EOP.</span></span> 
  
<span data-ttu-id="04d37-p106">EOP 内のルールは、さまざまな SCL レベルのメール メッセージを処理するように設定されています。メッセージが特定のしきい値を超える SCL レベルである場合は、スパムと見なされます。システム管理者が設定したスパムの配信オプションに応じて、メッセージは検疫されるか、ユーザーの迷惑メール フォルダーに配信されます。</span><span class="sxs-lookup"><span data-stu-id="04d37-p106">Rules inside EOP are set to handle email messages with various SCL ratings. If a message has an SCL rating higher than a certain threshold, it is considered spam. The message will be quarantined or delivered to the user's junk mail folder depending on how the system administrator configures the spam delivery option.</span></span>
  
#### <a name="eop-filters"></a><span data-ttu-id="04d37-129">EOP フィルター</span><span class="sxs-lookup"><span data-stu-id="04d37-129">EOP filters</span></span>

<span data-ttu-id="04d37-p107">スパム対策のフィルタリング テクノロジに加え、EOP では、システム管理者がフィルター レベルを設定して、ユーザー アカウントへのメールの配信をさらにカスタマイズすることもできます。管理者は、送信者やドメイン名を、信頼できる差出人のリストとドメイン リストに簡単に追加でき、メッセージの内容にかかわらず、その送信者やドメインからのメールを迷惑メールとして処理されないようにできます。詳しくは、「[Exchange Online の差出人セーフ リストと受信拒否リスト](safe-sender-and-blocked-sender-lists-faq.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04d37-p107">In addition to the anti-spam filtering technologies, EOP also gives the system administrator the ability to set filter levels to further customize the delivery of email to their user accounts. Administrators can easily add a sender or domain name to the Safe Senders and Domains List so that the email from that sender or domain is never treated as junk regardless of the content of the message. For information, see [Safe sender and blocked sender lists in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md).</span></span>
  
### <a name="phishing-protection"></a><span data-ttu-id="04d37-133">フィッシング対策</span><span class="sxs-lookup"><span data-stu-id="04d37-133">Phishing protection</span></span>

<span data-ttu-id="04d37-p108">フィッシングとは、個人情報の盗難であり、インターネット上で最も急速に成長している脅威の 1 つです。多くの場合、個人情報や財務情報を要求されたり、そのような情報を要求する Web サイトへのリンクが含まれていたりすると、フィッシング メッセージを識別できます。EOP では、独自の EOP フィルタリング テクノロジの一部として、フィッシング対策を提供しています。EOP フィルタリング テクノロジは、メールを分析して、不正なリンクや偽装されたドメインを検出し、これらの種類のオンライン詐欺からユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="04d37-p108">Phishing (pronounced "fishing") is a form of identity theft and one of the fastest growing threats on the Internet. You can often identify a phishing message when it requests personal or financial information or includes a link to a website that requests such information. EOP offers phishing protection as part of the proprietary EOP filtering technologies. EOP filtering technologies analyze email to help detect fraudulent links or spoofed domains to help protect users from these types of online scams.</span></span>
  
#### <a name="how-does-phishing-protection-work"></a><span data-ttu-id="04d37-138">フィッシング対策のしくみ</span><span class="sxs-lookup"><span data-stu-id="04d37-138">How does phishing protection work?</span></span>

<span data-ttu-id="04d37-p109">多くの場合、フィッシング メールはリンクを含んで送信されます。このリンクをクリックすると、ユーザーは一見有効に見える不正な Web サイト (金融機関やオンライン サービスなど) にリダイレクトされます。このフィッシング サイトでユーザーは通常、ユーザー名、パスワード、社会保障番号などの個人情報を入力するよう求められます。フィッシング サイトに入力した情報から、フィッシャーはユーザー情報を盗むことができます。よく知られている信頼されているブランド名やロゴを使うことで、フィッシャーは正当であるように見せることができます。EOP で利用できるフィッシング フィルター テクノロジは、メール内にある潜在的なフィッシングの特徴を調べます。検出されると、メールは迷惑メール フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="04d37-p109">Often a phishing email will be sent containing a link, once clicked the link redirects users to a fraudulent web site that appears valid (like your financial institution or online service). This phishing site usually prompts users to enter personal information like user names, passwords, and social security numbers. Any information you enter on the phishing site helps the phisher steal your identity. By using well-known trusted brand names and logos, phishers are able to appear legitimate. Phishing filter technology offered in EOP checks for potential phishing characteristics in email. If found, the email is moved to the Junk folder.</span></span>
  
<span data-ttu-id="04d37-145">Microsoft では、フィッシング対策テクノロジについて次の 2 つに重点を置いています。1 つ目はフィッシング メール メッセージがユーザーに配信されないようにすること、2 つ目は偽装されたメールや Web サイトにユーザーが騙される可能性を排除することです。</span><span class="sxs-lookup"><span data-stu-id="04d37-145">Microsoft is focusing its anti-phishing technology efforts on two fronts: first by helping to prevent phishing email messages from reaching our users and second by helping to eliminate the possibility of users being deceived by spoofed emails and web sites.</span></span> 
  
> [!TIP]
> <span data-ttu-id="04d37-146">Internet Explorer バージョン 7 以上では、ユーザーが既知のフィッシング サイトや潜在的なフィッシング サイトにアクセスした場合に、ユーザーをブロックするか、ユーザーに警告して、ユーザーが騙されて個人情報を提供しないようにします。[最新バージョンの Internet Explorer を使っていることを確認してください](https://www.microsoft.com/windows/ie/default.mspx)。</span><span class="sxs-lookup"><span data-stu-id="04d37-146">Internet Explorer version 7 and above will block or warn users when they visit known or potential phishing sites so that they aren't tricked into providing personal information.[Make sure that you have the latest version of Internet Explorer](https://www.microsoft.com/windows/ie/default.mspx).</span></span> 
  
#### <a name="authentication"></a><span data-ttu-id="04d37-147">認証</span><span class="sxs-lookup"><span data-stu-id="04d37-147">Authentication</span></span>

<span data-ttu-id="04d37-p110">ドメイン スプーフィングとは、正当なメール アドレスを模倣して、不正なメールを正当に見せかける方法です。スプーフィングは、個人の機密情報を漏洩するようユーザーを誘導するために、悪意のある個人や組織がフィッシング詐欺で使います。このような情報が公開されると、身元詐称やその他の不正行為につながります。</span><span class="sxs-lookup"><span data-stu-id="04d37-p110">Domain spoofing is a way of imitating a legitimate email address to make fraudulent email look legitimate. Spoofing is used by malicious individuals or organizations in phishing scams to lure people into divulging sensitive personal information. Disclosure of such information can lead to identify theft and other types of fraud.</span></span>
  
<span data-ttu-id="04d37-p111">EOP では、Sender Protection Framework (SPF)、DomainKeys Identified Mail (DKIM)、Domain-based Message Authentication, Reporting, and Conformance (DMARC)、その他の暗黙的な認証を使って、送信元であると主張するドメインからメッセージが送信されたことを確認します。迷惑メールやフィッシング詐欺から受信者を保護するため、すべての送信者が SPF と DKIM を使うことをお勧めします。送信者には、承認されていない送信者から送信されたメールを拒否するか検疫するために DMARC の発行を検討することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04d37-p111">EOP uses Sender Protection Framework (SPF), DomainKeys Identified Mail (DKIM), and Domain-based Message Authentication, Reporting, and Conformance (DMARC), and other implicit authentications to verify that messages came from the domain they claim to come from. We recommend that all senders use SPF and DKIM to protect their recipients from junk email and phishing scams. We recommend senders consider publishing a DMARC to reject or quarantine mail sent from unauthorized senders.</span></span>
  
- <span data-ttu-id="04d37-154">SPF について詳しくは、「[RFC 7208](https://tools.ietf.org/html/rfc7208)」と「[Sender Policy Framework](http://www.openspf.org/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04d37-154">To learn more about SPF, see [RFC 7208](https://tools.ietf.org/html/rfc7208) and [Sender Policy Framework](http://www.openspf.org/).</span></span>
    
- <span data-ttu-id="04d37-155">DKIM について詳しくは、「[RFC 6376](https://tools.ietf.org/html/rfc6376)」と「[DKIM.org](http://dkim.org/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04d37-155">To learn more about DKIM, see [RFC 6376](https://tools.ietf.org/html/rfc6376) and [DKIM.org](http://dkim.org/).</span></span>
    
- <span data-ttu-id="04d37-156">DMARC について詳しくは、「[DMARC.org](https://dmarc.org/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04d37-156">To learn more about DMARC, see [DMARC.org](https://dmarc.org/).</span></span>
    
### <a name="legislation"></a><span data-ttu-id="04d37-157">法律制定</span><span class="sxs-lookup"><span data-stu-id="04d37-157">Legislation</span></span>

<span data-ttu-id="04d37-p112">Microsoft では、新しいテクノロジと自主規制の開発には効果的な政府の政策と法的枠組みによるサポートが必要であると考えています。迷惑メールが世界中にまん延するにつれ、商用メールを規制する動きが多くの立法機関で活発化してきました。多くの国や地域では現在、迷惑メール防止法が施行されています。米国では、迷惑メールに対応した連邦法と州法が制定されており、この補完的なアプローチによって迷惑メールを減少させ、正規の電子商取引を促進しています。CAN-SPAM 法では、詐欺メールや偽装メールを阻止するためのさまざまなツールが提供されています。</span><span class="sxs-lookup"><span data-stu-id="04d37-p112">At Microsoft, we believe that the development of new technologies and self-regulation requires the support of effective government policy and legal frameworks. The worldwide spam proliferation has spurred numerous legislative bodies to regulate commercial email. Many countries/regions now have spam-fighting laws in place. The United States has both federal and state laws governing spam, and this complementary approach is helping to curtail spam while enabling legitimate e-commerce to prosper. The CAN-SPAM Act expands the tools available for curbing fraudulent and deceptive email messages.</span></span>
  

