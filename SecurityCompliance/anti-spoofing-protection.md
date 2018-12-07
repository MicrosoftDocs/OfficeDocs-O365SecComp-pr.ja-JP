---
title: Office 365 でのスプーフィング対策保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/06/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
description: この資料では、どのように Office 365 を軽減するフィッシング攻撃使用が送信者ドメインがスプーフィングされているドメインは、偽造されたことを説明します。メッセージを分析してこれを達成して、標準的な電子メールの認証方法やその他の送信者評価の手法を使用して、neithe を認証することができるものをブロックします。Office 365 の組織に公開するフィッシング攻撃の数を減らすためにこの変更が実装されています。
ms.openlocfilehash: 95f4995b6447870700bc483f205ca3ff831045f5
ms.sourcegitcommit: 8c5a88433cff23c59b436260808cf3d91b06fdef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2018
ms.locfileid: "27194718"
---
# <a name="anti-spoofing-protection-in-office-365"></a><span data-ttu-id="bbd0f-105">Office 365 でのスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="bbd0f-105">Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="bbd0f-p102">この資料では、どのように Office 365 を軽減するフィッシング攻撃使用が送信者ドメインがスプーフィングされているドメインは、偽造されたことを説明します。メッセージを分析し、標準的な電子メールの認証方法やその他の送信者評価の手法を使用して認証できないものをブロックして、これを実現します。お客様に公開するフィッシング攻撃の数を減らすためにこの変更が実装されています。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p102">This article describes how Office 365 mitigates against phishing attacks that uses forged sender domains, that is, domains that are spoofed. It accomplishes this by analyzing the messages and blocking the ones that cannot be authenticated using standard email authentication methods, nor other sender reputation techniques. This change is being implemented to reduce the number of phishing attacks customers are exposed to.</span></span>
  
<span data-ttu-id="bbd0f-109">説明なぜこの変更、この変更の顧客をどのように準備することができます、影響を受けるメッセージを表示するのには、メッセージを報告する方法、誤を軽減する方法と、これはマイクロソフトに送信者をどのように準備する必要があります。変更します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-109">This article also describes why this change is being made, how customers can prepare for this change, how to view messages that will be affected, how to report on messages, how to mitigate false positives, as well as how senders to Microsoft should prepare for this change.</span></span>
  
<span data-ttu-id="bbd0f-p103">マイクロソフトのスプーフィング対策テクノロジは、Office 365 エンタープライズ E5 サブスクリプションまたはサブスクリプションの Office 365 高度な脅威保護 (ATP) のアドオンを購入する必要があるが、組織に最初に配置されました。10 月、2018 年にも Exchange オンライン保護 (EOP) が存在する組織に保護が拡張します。さらに、互いから学ぶすべての当社のフィルターにより、Outlook.com のユーザーもがあります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p103">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription. As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well. Additionally, because of the way all of our filters learn from each other, Outlook.com users may also be affected.</span></span>
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="bbd0f-113">フィッシング攻撃の偽装の使用方法</span><span class="sxs-lookup"><span data-stu-id="bbd0f-113">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="bbd0f-p104">そのユーザーを保護する際に、マイクロソフトはフィッシング詐欺の脅威が最重要視します。スパムやフィッシングをよく使用する方法の 1 つは、なりすまし、送信者を偽造すると、ときに、誰かやどこかに実際のソースとは別に発信するメッセージが表示されます。この手法は、ユーザーの資格情報を取得するように設計されたフィッシング詐欺のキャンペーンでよく使用されます。マイクロソフトのアンチ スプーフ テクノロジーの偽造を調べて具体的には、' から: ヘッダー ' Outlook などの電子メール クライアントに表示されるものであります。マイクロソフトは、精度の高いを From: ヘッダーのスプーフィングは、スプーフィングとしてメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p104">When it comes to protecting its users, Microsoft takes the threat of phishing seriously. One of the techniques that spammers and phishers commonly use is spoofing, which is when the sender is forged, and a message appears to originate from someone or somewhere other than the actual source. This technique is often used in phishing campaigns designed to obtain user credentials. Microsoft's Anti-spoof technology specifically examines forgery of the 'From: header' which is the one that shows up in an email client like Outlook. When Microsoft has high confidence that the From: header is spoofed, it identifies the message as a spoof.</span></span>
  
<span data-ttu-id="bbd0f-119">なりすましメッセージは、実際のユーザーの 2 つの負影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-119">Spoofing messages have two negative implications for real life users:</span></span>
  
### <a name="1-spoofed-messages-deceive-users"></a><span data-ttu-id="bbd0f-120">1. スプーフィングされたメッセージは、ユーザーをだます</span><span class="sxs-lookup"><span data-stu-id="bbd0f-120">1. Spoofed messages deceive users</span></span>
  
<span data-ttu-id="bbd0f-p105">最初に、偽装されたメッセージがユーザーをだましてリンクをクリックして、資格情報を提供、マルウェアをダウンロードまたは (後者のでと呼ばれる危険にさらされるビジネス電子メール)、機密性の高いコンテンツを含むメッセージに返信します。たとえば、msoutlook94@service.outlook.com の送信者が偽装のフィッシング詐欺のメッセージは次のように。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p105">First, a spoofed message may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (the latter of which is known as Business Email Compromise). For example, the following is a phishing message with a spoofed sender of msoutlook94@service.outlook.com:</span></span>
  
![Service.outlook.com を偽装するフィッシング詐欺のメッセージ](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
<span data-ttu-id="bbd0f-p106">上から service.outlook.com、実際には発生しないが代わりにフィッシャーと同様の外観にすることによって偽装されました。ユーザーを騙して、メッセージ内のリンクをクリックしてましょう。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p106">The above did not actually come from service.outlook.com, but instead was spoofed by the phisher to make it look like it did. It is attempting to trick a user into clicking the link within the message.</span></span>
  
<span data-ttu-id="bbd0f-126">次の使用例は、contoso.com がスプーフィングします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-126">The next example is spoofing contoso.com:</span></span>
  
![フィッシング詐欺の危険にさらされるビジネス e メール](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
<span data-ttu-id="bbd0f-p107">メッセージは合法的では、スプーフィングを実際には。このフィッシング詐欺は、フィッシング詐欺の一種であるビジネス電子メールのセキュリティ侵害の種類です。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p107">The message looks legitimate, but in fact is a spoof. This phishing message is a type of Business Email Compromise which is a subcategory of phishing.</span></span>
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a><span data-ttu-id="bbd0f-130">2. ユーザーが偽のものの実際のメッセージを混乱させる</span><span class="sxs-lookup"><span data-stu-id="bbd0f-130">2. Users confuse real messages for fake ones</span></span>
  
<span data-ttu-id="bbd0f-p108">2 番目、スプーフィングされたメッセージは、ユーザーがフィッシング詐欺メッセージを知るには、本物のメッセージと偽装している 1 つの違いのための不確実性を作成します。たとえば、以下、マイクロソフトのセキュリティ アカウントの電子メール アドレスからのリセットの実際のパスワードの例です。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p108">Second, spoofed messages create uncertainty for users who know about phishing messages but cannot tell the difference between a real message and spoofed one. For example, the following is an example of an actual password reset from the Microsoft Security account email address:</span></span>
  
![マイクロソフトの正規のパスワードのリセット](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
<span data-ttu-id="bbd0f-p109">上記のメッセージは、マイクロソフトから来たが、同時に、ユーザーがフィッシング詐欺メッセージを取得することがユーザーをだましてリンクをクリックすると、自分の資格情報を提供し、マルウェアをダウンロード、または機密性の高いコンテンツを含むメッセージに返信します。実際のパスワードのリセットとフェイクの 1 つの違いを見分けるには難しいので、多くのユーザーがこれらのメッセージを無視する、スパムとして報告または不必要にメッセージをマイクロソフトに報告失敗したフィッシング詐欺として。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p109">The above message did come from Microsoft, but at the same time, users are used to getting phishing messages that may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content. Because it is difficult to tell the difference between a real password reset and a fake one, many users ignore these messages, report them as spam, or unnecessarily report the messages back to Microsoft as missed phishing scams.</span></span>
    
<span data-ttu-id="bbd0f-p110">偽装を停止するには、業界をフィルタ リングする電子メールは、 [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)など、電子メール認証プロトコルを開発しました。DMARC は、メッセージの送信者の電子メール クライアントでユーザーに表示される 1 つを調べることをスプーフィングを防ぐことが (上記の例では、これは、service.outlook.com、outlook.com、および accountprotection.microsoft.com) のドメインが SPF や DKIM を渡されるとします。ユーザーに表示されるドメインでは、認証されているし、スプーフィングされていないためです。詳細についてを参照してください"*なぜ電子メールの認証は常に偽装を停止するのには十分理解する"* このドキュメントで後で。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p110">To stop spoofing, the email filtering industry has developed email authentication protocols such as [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), and [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email). DMARC prevents spoofing examining a message's sender - the one that the user sees in their email client (in the examples above, this is service.outlook.com, outlook.com, and accountprotection.microsoft.com) - with the domain that passed SPF or DKIM. That is, the domain that the user sees has been authenticated and is therefore not spoofed. For a more complete discussion, see the section "*Understanding why email authentication is not always enough to stop spoofing"*  later on in this document.</span></span> 
  
<span data-ttu-id="bbd0f-p111">ただし、問題は、電子メール認証レコードはオプションですが、必須ではありません。したがって、強力な認証ポリシーを使用してドメインのように、microsoft.com および skype.com はなりすまし、ドメインのスプーフィングされる対象は、セキュリティ強度の低い認証ポリシー、またはポリシーがないのすべての発行をから保護されます。2018 年 3 月の時点では、Fortune 500 の企業のドメインの 9% だけは、強力な電子メール認証ポリシーを公開します。残りの 91% は、フィッシャー、によってスプーフィングされる可能性があり、別のポリシーを使用してエンドユーザーに配信することがあり、それらを欺く電子メール フィルターを検出した場合を除き、します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p111">However, the problem is that email authentication records are optional, not required. Therefore, while domains with strong authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker authentication policies, or no policy at all, are targets for being spoofed.As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies. The remaining 91% may be spoofed by a phisher, and unless the email filter detects it using another policy, may be delivered to an end user and deceive them:</span></span>
  
![Fortune 500 企業の DMARC のポリシー](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
<span data-ttu-id="bbd0f-144">いる中小企業の規模の企業の割合しない強力な電子メール認証ポリシーを発行する Fortune 500 のサイズが小さく、北米および西ヨーロッパの外部にあるドメインのまだ小さい。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-144">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for domains that are outside of North America and western Europe.</span></span>
  
<span data-ttu-id="bbd0f-145">これは、企業は、電子メール認証のしくみの認識ではない可能性があります、フィッシングは理解し、それの欠如を活用するための大きな問題です。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-145">This is a big problem because while enterprises may not be aware of how email authentication works, phishers do understand and take advantage of the lack of it.</span></span>
  
<span data-ttu-id="bbd0f-146">SPF、DKIM、DMARC をセットアップする方法についてを参照してください"このドキュメントで後で*Office 365 のお客様*です。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-146">For information on setting up SPF, DKIM, and DMARC, see the section "*Customers of Office 365"*  later on in this document.</span></span> 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a><span data-ttu-id="bbd0f-147">暗黙の e メールの認証と偽装を停止します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-147">Stopping spoofing with implicit email authentication</span></span>

<span data-ttu-id="bbd0f-p112">フィッシング詐欺、スピアー フィッシングとは、このような問題は、強力な電子メール認証ポリシーの制限の導入のため、マイクロソフトは、お客様を保護するための機能への投資を続けます。したがって、*暗黙的な電子メールの認証*に Microsoft が先へ進むドメインが認証されない場合は、マイクロソフトは電子メール認証レコードを発行した場合と同様に扱うこととに合格しない場合にそれに応じて扱うこと。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p112">Because phishing and spear phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft continues to invest in capabilities to protect its customers. Therefore, Microsoft is moving ahead with  *implicit email authentication* - if a domain doesn't authenticate, Microsoft will treat it as if it had published email authentication records and treat it accordingly if it doesn't pass.</span></span> 
  
<span data-ttu-id="bbd0f-p113">これを行うためには、Microsoft が送信者評価、送信者と受信者の履歴、行動分析、およびその他の高度なテクニックを含む通常の電子メールの認証に多数の拡張機能をビルドします。電子メールの認証を発行しないドメインから送信されたメッセージは、スプーフィングされているその他の場合信号を正当であることを示すようにマークされます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p113">To accomplish this, Microsoft has built numerous extensions to regular email authentication including sender reputation, sender/recipient history, behavioral analysis, and other advanced techniques. A message sent from a domain that doesn't publish email authentication will be marked as spoof unless it contains other signals to indicate that it is legitimate.</span></span>
  
<span data-ttu-id="bbd0f-152">これにより、ユーザーが持つことができます最後に送信される電子メールはスプーフィングされていないことを確信、送信者は誰もが自分のドメインを偽装して、Office 365 のお客様は、偽装の保護などのより優れた保護を提供できる確信することはできます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-152">By doing this, end users can have confidence that an email sent to them has not been spoofed, senders can be confident that nobody is impersonating their domain, and customers of Office 365 can offer even better protection such as Impersonation protection.</span></span>
  
<span data-ttu-id="bbd0f-153">マイクロソフトの一般的な告知事項については、 [A 海のフィッシング詐欺第 2 部 - Office 365 のなりすまし対策の強化が行われる](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-153">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a><span data-ttu-id="bbd0f-154">スプーフィングとして、メッセージの分類を識別します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-154">Identifying that a message is classified as spoofed</span></span>

### <a name="composite-authentication"></a><span data-ttu-id="bbd0f-155">複合認証</span><span class="sxs-lookup"><span data-stu-id="bbd0f-155">Composite authentication</span></span>

<span data-ttu-id="bbd0f-p114">SPF、DKIM、DMARC は、単独では役が、メッセージに明示的な認証レコードが存在しない場合に、十分な認証の状態を通信するありません。したがって、マイクロソフトでは、短い形式の複合認証、または compauth が呼び出される単一の値に複数の信号を結合するアルゴリズムを開発しました。スタンプ メッセージのヘッダーに*認証結果*のヘッダーに compauth の値は、Office 365 では、顧客であります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p114">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records. Therefore, Microsoft has developed an algorithm that combines multiple signals into a single value called Composite Authentication, or compauth for short. Customers in Office 365 have compauth values stamped into the *Authentication-Results* header in the message headers.</span></span> 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|<span data-ttu-id="bbd0f-159">**CompAuth の結果**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-159">**CompAuth result**</span></span>|<span data-ttu-id="bbd0f-160">**説明**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bbd0f-161">失敗します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-161">fail</span></span>|<span data-ttu-id="bbd0f-162">メッセージには、明示的な認証が失敗しました (送信ドメインのレコードに明示的に DNS に公開された) または暗黙の認証 (送信ドメインは、いない、Office 365 は、レコードを発行した場合と同様に結果を補間するため DNS では、レコードを公開しなかった)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-162">Message failed explicit authentication (sending domain published records explicitly in DNS) or implicit authentication (sending domain did not publish records in DNS, so Office 365 interpolated the result as if it had published records).</span></span>|
|<span data-ttu-id="bbd0f-163">渡す</span><span class="sxs-lookup"><span data-stu-id="bbd0f-163">pass</span></span>|<span data-ttu-id="bbd0f-164">渡される明示的な認証のメッセージ (メッセージは、DMARC、または[最適な推測渡される DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)に渡される) や信頼性の高さに対する暗黙の認証 (送信ドメインは、電子メールの認証レコードを公開しませんが、Office 365 には強力なバックエンドの信号には可能性が高いメッセージを示す正当な)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-164">Message passed explicit authentication (message passed DMARC, or [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) or implicit authentication with high confidence (sending domain does not publish email authentication records, but Office 365 has strong backend signals to indicate the message is likely legitimate).</span></span>|
|<span data-ttu-id="bbd0f-165">softpass</span><span class="sxs-lookup"><span data-stu-id="bbd0f-165">softpass</span></span>|<span data-ttu-id="bbd0f-166">メッセージには、低-中程度の信頼度を持つ暗黙の認証が渡されます (ドメインでは、電子メールの認証は公開されませんが、Office 365 を正当なメッセージでは、信号の強度が弱い信号をバックエンドに送信する)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-166">Message passed implicit authentication with low-to-medium confidence (sending domain does not publish email authentication, but Office 365 has backend signals to indicate the message is legitimate but the strength of the signal is weaker).</span></span>|
|<span data-ttu-id="bbd0f-167">なし</span><span class="sxs-lookup"><span data-stu-id="bbd0f-167">none</span></span>|<span data-ttu-id="bbd0f-168">メッセージは認証されませんでした (または、認証でしたが、合いませんでした)、複合認証を送信者評価やその他の要素は適用されませんが、します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-168">Message did not authenticate (or it did authenticate but did not align), but composite authentication not applied due to sender reputation or other factors.</span></span>|
   
|||
|:-----|:-----|
|<span data-ttu-id="bbd0f-169">**Reason**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-169">**Reason**</span></span>|<span data-ttu-id="bbd0f-170">**説明**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-170">**Description**</span></span>|
|<span data-ttu-id="bbd0f-171">0xx</span><span class="sxs-lookup"><span data-stu-id="bbd0f-171">0xx</span></span>|<span data-ttu-id="bbd0f-172">メッセージには、複合認証が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-172">Message failed composite authentication.</span></span><br/><span data-ttu-id="bbd0f-p115">**000**は、メッセージが拒否、または検疫のアクションを伴う DMARC に失敗しましたを意味します。                   -001 は、メッセージには、暗黙的な電子メールの認証が失敗したを意味します。つまり、送信側のドメインで公開されると、電子メールの認証レコードがなかった場合は、セキュリティ強度の低い障害ポリシー必要がある (SPF ソフトの失敗、または中立的な DMARC のポリシーの p = なし)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p115">**000** means the message failed DMARC with an action of reject or quarantine.                    - 001 means the message failed implicit email authentication. This means that the sending domain did not have email authentication records published, or if they did, they had a weaker failure policy (SPF soft fail or neutral, DMARC policy of p=none).  </span></span><br/><span data-ttu-id="bbd0f-176">**002**手段が組織に偽装された電子メールを送信するから明示的に禁止されている送信者またはドメインのペアのポリシーは、この設定は管理者が手動で設定します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-176">**002** means the organization has a policy for the sender/domain pair that is explicitly prohibited from sending spoofed email, this setting is manually set by an administrator.</span></span>  <br/><span data-ttu-id="bbd0f-177">**010**は、メッセージの拒否、または検疫、アクションを伴う DMARC を失敗した送信側のドメイン、組織の承認済みドメインのいずれか (これは、自己自身、または組織内の一部をなりすましが行われる)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-177">**010** means the message failed DMARC with an action of reject or quarantine, and the sending domain is one of your organization's accepted-domains (this is part of self-to-self, or intra-org, spoofing).</span></span>  <br/><span data-ttu-id="bbd0f-178">**011**は、メッセージには、暗黙の電子メールの認証が失敗しました。 送信側のドメイン、組織の承認済みドメインのいずれか (これは、自己自身、または組織内の一部を、なりすましが行われる)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-178">**011** means the message failed implicit email authentication, and the sending domain is one of your organization's accepted domains (this is part of self-to-self, or intra-org, spoofing).</span></span>|
|<span data-ttu-id="bbd0f-179">他のすべてのコード (1 xx、2 xx、3 xx、4 xx、5 xx)</span><span class="sxs-lookup"><span data-stu-id="bbd0f-179">All other codes (1xx, 2xx, 3xx, 4xx, 5xx)</span></span>|<span data-ttu-id="bbd0f-180">アクションが適用されたことはないがメッセージに対する暗黙の認証を渡すか、認証がありませんでした理由は、さまざまな内部コードに対応します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-180">Corresponds to various internal codes for why a message passed implicit authentication, or had no authentication but no action was applied.</span></span>|
   
<span data-ttu-id="bbd0f-181">メッセージのヘッダーを見ると、管理者またはエンド ・ ユーザーでも確認できます送信者がスプーフィングされる可能性がありますを終了したときに Office 365 の到着します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-181">By looking at the headers of a message, an administrator or even an end user can determine how Office 365 arrives at the conclusion that the sender may be spoofed.</span></span>
  
### <a name="differentiating-between-different-types-of-spoofing"></a><span data-ttu-id="bbd0f-182">なりすましのさまざまな種類の違いを知る</span><span class="sxs-lookup"><span data-stu-id="bbd0f-182">Differentiating between different types of spoofing</span></span>

<span data-ttu-id="bbd0f-183">マイクロソフトは、2 種類のメッセージがスプーフィングによって区別します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-183">Microsoft differentiates between two different types of spoofing messages:</span></span>
  
 <span data-ttu-id="bbd0f-184">**組織内通信のなりすましが行われる**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-184">**Intra-org spoofing**</span></span>
  
<span data-ttu-id="bbd0f-185">呼ばれる自己自身のなりすまし、これが発生したときからドメイン: アドレスと、同じか、または合わせて、受信者のドメイン (とき、受信者のドメインは、組織の[承認済みドメイン](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)の 1 つです)。または、[差出人のドメイン: アドレスは、同じ組織の一部です。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-185">Also known as self-to-self spoofing, this occurs when the domain in the From: address is the same as, or aligns with, the recipient domain (when recipient domain is one of your organization's [Accepted Domains](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)); or, when the domain in the From: address is part of the same organization.</span></span>
  
<span data-ttu-id="bbd0f-p116">たとえば、次は送信者と受信者の同じドメイン (contoso.com) のです。スペースに挿入する spambot がこのページの収集を防ぐために e メール アドレス)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p116">For example, the following has sender and recipient from the same domain (contoso.com). Spaces are inserted into the email address to prevent spambot harvesting on this page):</span></span>
  
<span data-ttu-id="bbd0f-188">メールボックス ストアの送信者から。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-188">From: sender @ contoso.com</span></span>
  
<span data-ttu-id="bbd0f-189">メールボックス ストアの受信者にします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-189">To: recipient @ contoso.com</span></span>
  
<span data-ttu-id="bbd0f-190">次の送信者と受信者のドメインの組織のドメイン (fabrikam.com) との連携があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-190">The following has the sender and recipient domains aligning with the organizational domain (fabrikam.com):</span></span>
  
<span data-ttu-id="bbd0f-191">@ Foo.fabrikam.com: 送信者</span><span class="sxs-lookup"><span data-stu-id="bbd0f-191">From: sender @ foo.fabrikam.com</span></span>
  
<span data-ttu-id="bbd0f-192">Bar.fabrikam.com @ 受信者にします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-192">To: recipient @ bar.fabrikam.com</span></span>
  
<span data-ttu-id="bbd0f-193">次の送信者と受信者のドメインが異なる (microsoft.com および bing.com) が、それらが同じ組織に属して (つまり、両方が組織の承認済みドメインの一部)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-193">The following sender and recipient domains are different (microsoft.com and bing.com), but they belong to the same organization (that is, both are part of the organization's Accepted Domains):</span></span>
  
<span data-ttu-id="bbd0f-194">Microsoft.com @: 送信者</span><span class="sxs-lookup"><span data-stu-id="bbd0f-194">From: sender @ microsoft.com</span></span>
  
<span data-ttu-id="bbd0f-195">Bing.com @ 受信者にします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-195">To: recipient @ bing.com</span></span>
  
<span data-ttu-id="bbd0f-196">組織内通信の偽装に失敗したメッセージには、ヘッダーに次の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-196">Messages that fail intra-org spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="bbd0f-197">X Forefront スパム対策レポート:.CAT:SPM HSPM/PHSH;.SFTY:9.11</span><span class="sxs-lookup"><span data-stu-id="bbd0f-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span></span>
  
<span data-ttu-id="bbd0f-198">猫、メッセージのカテゴリで、SPM (スパム) がスタンプされて通常がときどき HSPM (精度の高いスパム) またはフィッシング (フィッシング) によってどのような他のパターンの種類で発生する可能性、メッセージです。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-198">The CAT is the category of the message, and it is normally stamped as SPM (spam), but occasionally may be HSPM (high confidence spam) or PHISH (phishing) depending upon what other types of patterns occur in the message.</span></span>
  
<span data-ttu-id="bbd0f-199">SFTY は、メッセージの安全性のレベル、最初の桁の数字 (9) は、メッセージは、フィッシング詐欺、およびドット (11) は、その後の数字の 2 番目のセットは、組織内のなりすまし。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-199">The SFTY is the safety level of the message, the first digit (9) means the message is phishing, and second set of digits after the dot (11) means it is intra-org spoofing.</span></span>
  
<span data-ttu-id="bbd0f-200">2018 (タイムラインが定義されていません) のスタンプがなりすましが行われると、組織内の複合の認証のための特別な理由コードはありません。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-200">There is no specific reason code for Composite Authentication for intra-org spoofing, that will be stamped later in 2018 (timeline not yet defined).</span></span>
  
 <span data-ttu-id="bbd0f-201">**クロス ドメインのスプーフィング**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-201">**Cross-domain spoofing**</span></span>
  
<span data-ttu-id="bbd0f-p117">これが発生したときから送信側のドメイン: アドレスは、受信側の組織の外部のドメインです。クロス ドメインのスプーフィングによる複合認証に失敗したメッセージには、ヘッダーに次の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p117">This occurs when the sending domain in the From: address is an external domain to the receiving organization. Messages that fail Composite Authentication due to cross-domain spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="bbd0f-p118">認証の結果:... compauth 失敗の理由を = = 000 と 001</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p118">Authentication-Results: … compauth=fail reason=000/001</span></span>
  
<span data-ttu-id="bbd0f-206">X Forefront スパム対策レポート:.CAT:SPOOF;.SFTY:9.22</span><span class="sxs-lookup"><span data-stu-id="bbd0f-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span></span>
  
<span data-ttu-id="bbd0f-207">どちらの場合も、次の赤の安全性のヒントは、メッセージ、または受信者のメールボックスの言語にカスタマイズされている同等の関数でスタンプが付けられます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-207">In both cases, the following red safety tip is stamped in the message, or an equivalent that is customized to the recipient mailbox's language:</span></span>
  
![赤の安全性のヒントは不正の検出](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
<span data-ttu-id="bbd0f-209">見るだけである: またはアドレスと、受信者の電子メールとは何を知ることで組織内通信のクロス ドメインのスプーフィングとを区別することができる電子メールのヘッダーを検査します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-209">It's only by looking at the From: address and knowing what your recipient email is, or by inspecting the email headers, that you can differentiate between intra-org and cross-domain spoofing.</span></span>
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a><span data-ttu-id="bbd0f-210">方法 Office 365 のお客様が準備新しいスプーフィング対策の保護</span><span class="sxs-lookup"><span data-stu-id="bbd0f-210">How customers of Office 365 can prepare themselves for the new anti-spoofing protection</span></span>

### <a name="information-for-administrators"></a><span data-ttu-id="bbd0f-211">管理者向け情報</span><span class="sxs-lookup"><span data-stu-id="bbd0f-211">Information for administrators</span></span>

<span data-ttu-id="bbd0f-212">Office 365 の組織の管理者は、いくつかの重要な情報に注意する必要がありますがあります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-212">As an administrator of an organization in Office 365, there are several key pieces of information you should be aware of.</span></span>
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="bbd0f-213">なぜ電子メールの認証は常に偽装を停止するのには十分理解すること</span><span class="sxs-lookup"><span data-stu-id="bbd0f-213">Understanding why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="bbd0f-p119">新しいスプーフィング対策保護は、電子メール認証 (SPF、DKIM、DMARC) なりすましとメッセージをマークするに依存しています。一般的な例は、送信側のドメインが SPF レコードを公開しない場合です。SPF レコードが存在しない、またはそれらが正しく設定されていません、マイクロソフトではバックエンド ・ インテリジェンスは、正当なメッセージであることを示す場合を除きをスプーフィングとして送信されたメッセージがマークされます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p119">The new anti-spoofing protection relies on email authentication (SPF, DKIM, and DMARC) to not mark a message as spoofing. A common example is when a sending domain has never published SPF records. If there are no SPF records or they are incorrectly set up, a sent message will be marked as spoofed unless Microsoft has back-end intelligence that says the message is legitimate.</span></span>
  
<span data-ttu-id="bbd0f-217">たとえば、スプーフィング対策を展開する、前にメッセージ可能性がありますきました SPF レコードがない、DKIM のレコードがない、DMARC レコードがないと次のように。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-217">For example, prior to anti-spoofing being deployed, a message may have looked like the following with no SPF record, no DKIM record, and no DMARC record:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
<span data-ttu-id="bbd0f-218">スプーフィング対策後があれば Office 365 エンタープライズ E5、EOP、ATP、compauth 値がスタンプします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-218">After anti-spoofing, if you have Office 365 Enterprise E5, EOP, or ATP, the compauth value is stamped:</span></span>
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

<span data-ttu-id="bbd0f-219">SPF を渡されるドメインに配置からドメインを持つために、複合認証を渡すこれは example.com では、SPF レコードが DKIM レコードではありませんを設定することによってこれを固定である場合: アドレス。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-219">If example.com fixed this by setting up an SPF record but not a DKIM record, this would pass composite authentication because the domain that passed SPF aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="bbd0f-220">渡される DKIM 署名内のドメインが [差出人のドメインに配置するため複合認証を渡すこの DKIM レコードが SPF レコードではなく、設定する場合も、または、: アドレス。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-220">Or, if they set up a DKIM record but not an SPF record, this would also pass composite authentication because the domain in the DKIM-Signature that passed aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="bbd0f-p120">ただし、フィッシャーも SPF と DKIM の設定し、自身のドメインでメッセージを署名がから別のドメインを指定します。 アドレスです。SPF と DKIM はどちらも、ドメインからドメインの連携をする必要があります: example.com は、DMARC のレコードを公開しない限り、これとしてマークできません DMARC を使用して、なりすましを行う可能性があるために対処します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p120">However, a phisher may also set up SPF and DKIM and sign the message with their own domain, but specify a different domain in the From: address. Neither SPF nor DKIM requires the domain to align with the domain in the From: address, so unless example.com published DMARC records, this would not be marked as a spoof using DMARC:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="bbd0f-223">電子メール クライアント (Outlook、Outlook、またはその他の電子メール クライアント) からのみで: ドメインが表示されたら、次に、SPF や DKIM、ドメインではなく誤解する可能性、ユーザーにメッセージは、example.com に関しては、付属していたが、maliciousDomain.com から実際に付属していた.</span><span class="sxs-lookup"><span data-stu-id="bbd0f-223">In the email client (Outlook, Outlook on the web, or any other email client), only the From: domain is displayed, not the domain in the SPF or DKIM, and that can mislead the user into thinking the message came from example.com, but actually came from maliciousDomain.com.</span></span>
  
![認証されたメッセージから: ドメインが SPF や DKIM を渡されたものと合っていません。](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
<span data-ttu-id="bbd0f-p121">そのため、Office 365 が必要ですからドメイン: アドレスが SPF や DKIM 署名内のドメインに配置し、メッセージが正当なことを示すいくつかの他の内部の信号が含まれているしていない場合。それ以外の場合、メッセージは、compauth の失敗になります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p121">For that reason, Office 365 requires that the domain in the From: address aligns with the domain in the SPF or DKIM signature, and if it doesn't, contains some other internal signals that indicates that the message is legitimate. Otherwise, the message would be a compauth fail.</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

<span data-ttu-id="bbd0f-p122">認証なしに、ドメインおよびドメイン認証が [差出人のドメインに対しての不一致を設定したが、Office 365 スプーフィング対策保護: 1 つのアドレスは、メッセージの送信者は、ユーザーが表示されと考えています。これは、組織内のドメインと同様に、組織の外部ドメインの両方に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p122">Thus, Office 365 anti-spoofing protects against domains with no authentication, and against domains who set up authentication but mismatch against the domain in the From: address as that is the one that the user sees and believes is the sender of the message. This is true both of domains external to your organization, as well as domains within your organization.</span></span>
  
<span data-ttu-id="bbd0f-229">したがって、複合認証が失敗し、SPF と DKIM にメッセージが渡された場合でも、偽装であるとマークするメッセージを受け取ることはありませんが SPF と DKIM を渡されるドメインが [差出人のドメインと一致していないため: アドレスです。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-229">Therefore, if you ever receive a message that failed composite authentication and is marked as spoofed, even though the message passed SPF and DKIM, it's because the domain that passed SPF and DKIM are not aligned with the domain in the From: address.</span></span>
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a><span data-ttu-id="bbd0f-230">どのように偽装された電子メールでの変更を理解することが扱われます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-230">Understanding changes in how spoofed emails are treated</span></span>

<span data-ttu-id="bbd0f-p123">現時点では、Office 365 の内のすべての組織の ATP と ATP 以外の場合にメッセージをスパムし、通常、精度の高いスパム アクションまたは通常の迷惑メールの処理にかかる、DMARC の拒否、または検疫ポリシーを使用してはマークされて、その失敗 (かどうかによってその他の迷惑メール規則最初として識別スパム)。組織内通信のスプーフィング検出では、正規のスパムのアクションを実行します。この動作を有効にする必要はありませんも、それを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p123">Currently, for all organizations in Office 365 - ATP and non-ATP - messages that fail DMARC with a policy of reject or quarantine are marked as spam and usually take the high confidence spam action, or sometimes the regular spam action (depending on whether other spam rules first identify it as spam). Intra-org spoof detections take the regular spam action. This behavior does not need to be enabled, nor can it be disabled.</span></span>
  
<span data-ttu-id="bbd0f-p124">ただし、クロス ドメインのなりすましメッセージを変更する前に正規のスパム、フィッシング、マルウェアのチェックを通じて、フィルターの他の部分を識別して、疑わしいとしている場合はマークにスパム、フィッシング、マルウェアとそれぞれ。新しいクロス ドメインのなりすまし防止、すべてのメッセージを認証することはできませんが、既定では、操作を行います、フィッシング詐欺対策で定義されている\>ポリシーのスプーフィングを防止します。いずれかが定義されていない場合は、ユーザーの迷惑メール フォルダーに移動されます。場合によっては、さらに不審なメッセージを赤の安全性のヒントをメッセージに追加するがあります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p124">However, for cross-domain spoofing messages, before this change they would go through regular spam, phish, and malware checks and if other parts of the filter identified them as suspicious, would mark them as spam, phish, or malware respectively. With the new cross-domain spoofing protection, any message that can't be authenticated will, by default, take the action defined in the Anti-phishing \> Anti-spoofing policy. If one is not defined, it will be moved to a users Junk Email folder. In some cases, more suspicious messages will also have the red safety tip added to the message.</span></span>
  
<span data-ttu-id="bbd0f-p125">まだ取得としてマークされている迷惑メールが、今も赤の安全性のヒントはスパムとしてマークされていたいくつかのメッセージがあります。、それ以外の場合は、スパムではないが開始としてマークを取得する赤の安全性の先端を使用して迷惑メール (CAT:SPOOF) としてマークされていたメッセージが追加されます。それ以外の場合も、すべてのスパムやフィッシングを検疫に移行されたお客様は今すぐを参照してください [迷惑メール] フォルダーに移動する (この現象は、[スプーフィング対策設定を変更する](#changing-your-anti-spoofing-settings)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p125">This may result in some messages that were previously marked as spam still getting marked as spam but will now also have a red safety tip; in other cases, messages that were previously marked as non-spam will start getting marked as spam (CAT:SPOOF) with a red safety tip added. In still other cases, customers that were moving all spam and phish to the quarantine would now see them going to the Junk Mail Folder (this behavior can be changed, see [Changing your anti-spoofing settings](#changing-your-anti-spoofing-settings)).</span></span>
  
<span data-ttu-id="bbd0f-p126">(この資料の前半[のなりすましのさまざまな種類の間の Differentiating](#differentiating-between-different-types-of-spoofing)を参照してください) メッセージを偽装することが複数の異なる方法がありますが、2018年 3 月年 Office 365 は、これらのメッセージを処理する方法がないまだ統合します。次の表は、クロス ドメインのなりすまし保護が新しい動作を実行すると、簡単な概要です。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p126">There are multiple different ways a message can be spoofed (see  [Differentiating between different types of spoofing](#differentiating-between-different-types-of-spoofing) earlier in this article) but as of March 2018 the way Office 365 treats these messages is not yet unified. The following table is a quick summary, with Cross-domain spoofing protection being new behavior:</span></span> 
  
|<span data-ttu-id="bbd0f-242">**スプーフィングの種類**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-242">**Type of spoof**</span></span>|<span data-ttu-id="bbd0f-243">**分類**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-243">**Category**</span></span>|<span data-ttu-id="bbd0f-244">**追加の安全性のヒントですか。**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-244">**Safety tip added?**</span></span>|<span data-ttu-id="bbd0f-245">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-245">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bbd0f-246">DMARC の失敗 (検疫または拒否)</span><span class="sxs-lookup"><span data-stu-id="bbd0f-246">DMARC fail (quarantine or reject)</span></span>  <br/> |<span data-ttu-id="bbd0f-247">HSPM (既定値) は、SPM または PHSH 場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-247">HSPM (default), may also be SPM or PHSH</span></span>  <br/> |<span data-ttu-id="bbd0f-248">いいえ (まだ)</span><span class="sxs-lookup"><span data-stu-id="bbd0f-248">No (not yet)</span></span>  <br/> |<span data-ttu-id="bbd0f-249">すべての Office 365 のお客様、Outlook.com</span><span class="sxs-lookup"><span data-stu-id="bbd0f-249">All Office 365 customers, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="bbd0f-250">自己自身</span><span class="sxs-lookup"><span data-stu-id="bbd0f-250">Self-to-self</span></span>  <br/> |<span data-ttu-id="bbd0f-251">SPM</span><span class="sxs-lookup"><span data-stu-id="bbd0f-251">SPM</span></span>  <br/> |<span data-ttu-id="bbd0f-252">はい</span><span class="sxs-lookup"><span data-stu-id="bbd0f-252">Yes</span></span>  <br/> |<span data-ttu-id="bbd0f-253">すべての Office 365 組織では、Outlook.com</span><span class="sxs-lookup"><span data-stu-id="bbd0f-253">All Office 365 organizations, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="bbd0f-254">クロス ・ ドメイン</span><span class="sxs-lookup"><span data-stu-id="bbd0f-254">Cross-domain</span></span>  <br/> |<span data-ttu-id="bbd0f-255">なりすまし</span><span class="sxs-lookup"><span data-stu-id="bbd0f-255">SPOOF</span></span>  <br/> |<span data-ttu-id="bbd0f-256">はい</span><span class="sxs-lookup"><span data-stu-id="bbd0f-256">Yes</span></span>  <br/> |<span data-ttu-id="bbd0f-257">脅威保護の高度な office 365 と E5 のお客様</span><span class="sxs-lookup"><span data-stu-id="bbd0f-257">Office 365 Advanced Threat Protection and E5 customers</span></span>  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a><span data-ttu-id="bbd0f-258">スプーフィング対策の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-258">Changing your anti-spoofing settings</span></span>

<span data-ttu-id="bbd0f-p127">で作成または更新 (クロス ドメイン) のスプーフィング対策の設定には、フィッシング詐欺対策に移動\>脅威の管理下で、スプーフィング対策の設定\>[セキュリティ ポリシー] タブ&amp;コンプライアンス センターです。決して、フィッシング詐欺対策の設定を作成した場合は、1 つを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p127">To create or update your (cross-domain) anti-spoofing settings, navigate to the Anti-phishing \> Anti-spoofing settings under the Threat Management \> Policy tab in the Security &amp; Compliance Center. If you have never created any anti-phishing settings, you will need to create one:</span></span>
  
![フィッシング対策の新しいポリシーを作成します。](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
<span data-ttu-id="bbd0f-262">既に作成した 1 つ場合に、それを変更することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-262">If you've already created one, you can select it to modify it:</span></span>
  
![フィッシング対策 - 既存のポリシーを変更します。](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
<span data-ttu-id="bbd0f-264">作成したポリシーを選択しの説明に従って手順を進める[なりすましインテリジェンスに関する詳細です](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-264">Select the policy you just created and proceed through the steps as described on [Learn More about Spoof Intelligence.](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span></span>
  
![有効にするまたは antispoofing を無効にします。](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![有効にするか、antispoofing の安全性のヒントを無効にします。](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
<span data-ttu-id="bbd0f-267">PowerShell を使用して新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-267">To create a new policy via PowerShell:</span></span> 
  
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

<span data-ttu-id="bbd0f-p128">[セット AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)のマニュアルに従って、PowerShell を使用してフィッシング詐欺対策のポリシー パラメーターを変更する可能性があります。$Name をパラメーターとして指定することがあります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p128">You may then modify the anti-phishing policy parameters using PowerShell, following the documentation at [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps). You may specify the $name as a parameter:</span></span>
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

<span data-ttu-id="bbd0f-270">2018 で後で既定のポリシーを作成することを実行するのではなく 1 つ作成されますそれを手動で指定する必要はありませんので、組織内のすべての受信者を対象範囲とする (以下のスクリーン ショットでは、最終的な実装の前に変更される場合)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-270">Later in 2018, rather than you having to create a default policy, one will be created for you that is scoped to all the recipients in your organization so you don't have to specify it manually (the screenshots below are subject to change before the final implementation).</span></span>
  
![フィッシング対策用の既定のポリシー](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
<span data-ttu-id="bbd0f-272">作成したポリシーとは異なりことはできません既定のポリシーを削除、優先順位を変更するかを選択するユーザー、ドメイン、またはグループのスコープを設定するに。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-272">Unlike a policy that you create, you cannot delete the default policy, modify its priority, or choose which users, domains, or groups to scope it to.</span></span>
  
![フィッシング対策の既定ポリシーの詳細](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
<span data-ttu-id="bbd0f-274">PowerShell を使用して、既定の保護レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-274">To set up your default protection via PowerShell:</span></span>
  
```
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

<span data-ttu-id="bbd0f-275">のみを無効にしてスプーフィング対策の保護別のメール サーバーまたは Office 365 の前にサーバーがある場合 (詳細についてはアンチのなりすましを無効にする正当なシナリオを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-275">You should only disable anti-spoofing protection if you have another mail server or servers in front of Office 365 (see Legitimate scenarios to disable anti-spoofing for more details).</span></span> 
  
```
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> <span data-ttu-id="bbd0f-p129">まず、送信者、ドメインのスプーフィングされた電子メールを送信を許可するを設定、電子メールのパスの最初のホップは、Office 365 では、スプーフィングとしてマークされている多くの正当な電子メールを取得する場合は、必要があります (を参照してください *"管理する正当な送信者 u を送信します。nauthenticated メール」* )。誤検知が多すぎますが発生する場合 (たとえば、正規スプーフィングとしてマークされたメッセージ)、スプーフィング対策の保護を完全に無効にすること勧めしません。代わりに、高度な保護ではなく、Basic を選択することをお勧めします。                   誤検出には、組織は結局のところ、長期的に非常に高いコストを課す、スプーフィングされたメールを公開するよりもを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p129">If the first hop in your email path is Office 365, and you are getting too many legitimate emails marked as spoof, you should first set up your senders that are allowed to send spoofed email to your domain (see the section  *"Managing legitimate senders who are sending unauthenticated email"*  ). If you are still getting too many false positives (e.g., legitimate messages marked as spoof), we do NOT recommend disabling anti-spoofing protection altogether. Instead, we recommend choosing Basic instead of High protection.                    It is better to work through false positives than to expose your organization to spoofed email which could end up imposing significantly higher costs in the long term.</span></span>

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="bbd0f-280">正当な送信者は認証されていない電子メールを送信するユーザーを管理します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-280">Managing legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="bbd0f-p130">Office 365 は、認証されていないメールの送信元組織の追跡します。サービスでは、送信者が正当ではないと考えて、 *compauth*の失敗としてマークには。メッセージに適用された、スプーフィング対策ポリシーに依存しますがスプーフィングとして分類されます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p130">Office 365 keeps track of who is sending unauthenticated email to your organization. If the service thinks the sender is not legitimate, it will mark it as a *compauth* failure. This will be classified as SPOOF although it depends on your anti-spoofing policy that was applied to the message.</span></span> 
  
<span data-ttu-id="bbd0f-284">ただし、管理者は、どの送信者は、スプーフィングされたメールを送信するのには Office 365 の意思決定をオーバーライドすることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-284">However, as an administrator, you can specify which senders are permitted to send spoofed email, overriding Office 365's decision.</span></span>
  
<span data-ttu-id="bbd0f-285">**方法 1 の組織は、ドメインを所有している場合は、電子メールの認証を設定**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-285">**Method 1 - If your organization owns the domain, set up email authentication**</span></span>
  
<span data-ttu-id="bbd0f-p131">組織内通信のスプーフィング、および、複数のテナントを所有または相互作用の位置の場合なりすましのクロス ・ ドメインを解決するのにはこのメソッドを使用することができます。クロス ドメインのスプーフィング、Office 365 内での他の顧客に送信して他のプロバイダーでホストされているサード パーティを解決することができます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p131">This method can be used to resolve intra-org spoofing, and cross-domain spoofing in cases where you own or interact with multiple tenants. It also helps resolve cross-domain spoofing where you send to other customers within Office 365, and also third parties that are hosted in other providers.</span></span>
  
<span data-ttu-id="bbd0f-288">詳細については、[お客様の Office 365](#customers-of-office-365)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-288">For more details, see [Customers of Office 365](#customers-of-office-365).</span></span> 
 
<span data-ttu-id="bbd0f-289">**方法 2 - 認証されていないメールの送信者を許可を構成するのにはインテリジェンスを使用してなりすましを行う可能性**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-289">**Method 2 - Use Spoof intelligence to configure permitted senders of unauthenticated email**</span></span>
  
<span data-ttu-id="bbd0f-290">組織に認証されていないメッセージを送信するのに送信者を許可するように[なりすましのインテリジェンス](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-290">You can also use [Spoof Intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) to permit senders to transmit unauthenticated messages to your organization.</span></span> 
  
<span data-ttu-id="bbd0f-291">外部ドメインは、偽装されたユーザーが差出人のアドレスのドメイン送信側のインフラストラクチャは、送信元の IP アドレス (/24 に分割されている CIDR 範囲)、または PTR レコードの組織のドメイン (次のスクリーン ショットの送信元 ip アドレスがありますPTR レコードは、outbound.mail.protection.outlook.com、131.107.18.4、outlook.com の送信側のインフラストラクチャとして示されます)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-291">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the sending IP address (divided up into /24 CIDR ranges), or the organizational domain of the PTR record (in the screenshot below, the sending IP might be 131.107.18.4 whose PTR record is outbound.mail.protection.outlook.com, and this would show up as outlook.com for the sending infrastructure).</span></span>
  
<span data-ttu-id="bbd0f-292">認証されていない電子メールを送信するには、この送信者を許可するには、 **[はい]** に**No**を変更します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-292">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>
  
![許可された送信者の antispoofing を設定します。](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
<span data-ttu-id="bbd0f-294">特定の送信者、ドメインのスプーフィングを許可するのに PowerShell を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-294">You can also use PowerShell to allow specific sender to spoof your domain:</span></span> 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Powershell を使用して偽装された送信者を取得します。](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
<span data-ttu-id="bbd0f-296">前のイメージでは、このスクリーン ショットを作成するのには次のように合わせて、ですが、実際にはすべての値が 1 行に表示するに、追加の改行が追加されています。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-296">In the previous image, additional line breaks have been added to make this screenshot fit, but in actuality all the values would appear on a single line.</span></span>
  
<span data-ttu-id="bbd0f-297">ファイルを編集し、outlook.com と bing.com に対応する行を探して、いいえ] から [はい] に AllowedToSpoof のエントリを変更します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-297">Edit the file and look for the line that corresponds to outlook.com and bing.com, and change the AllowedToSpoof Entry from No to Yes:</span></span>
  
![Powershell を使用して [はい] に設定のスプーフィングを許可します。](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
<span data-ttu-id="bbd0f-299">ファイルを保存し、実行します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-299">Save the file, and then run:</span></span> 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

<span data-ttu-id="bbd0f-300">Bing.com から認証されていない電子メールを送信するようになりましたことが\*. outlook.com。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-300">This will now allow bing.com to send unauthenticated email from \*.outlook.com.</span></span>

<span data-ttu-id="bbd0f-301">**方法 3: 送信者/受信者の組み合わせを許可するエントリを作成します。**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-301">**Method 3 - Create an allow entry for the sender/recipient pair**</span></span>
  
<span data-ttu-id="bbd0f-p132">すべてのスパムが特定の送信者のフィルターをバイパスすることもできます。詳細については、 [Office 365 の許可リストに送信者を安全に追加する方法](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p132">You can also choose to bypass all spam filtering for a particular sender. For more details, see [How to securely add a sender to an allow list in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).</span></span>
  
<span data-ttu-id="bbd0f-304">このメソッドを使用する場合はスキップ迷惑メールおよびフィッシング フィルターの一部が、マルウェアのフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-304">If you use this method, it will skip spam and some of the phish filtering, but not malware filtering.</span></span>
  
<span data-ttu-id="bbd0f-305">**方法 4 - 送信者に連絡し、電子メールの認証を設定するように依頼**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-305">**Method 4 - Contact the sender and ask them to set up email authentication**</span></span>
  
<span data-ttu-id="bbd0f-p133">、スパムやフィッシングの問題が発生したためは、マイクロソフトは、すべての送信者の電子メールの認証の設定を推奨します。送信側ドメインの管理者がわかっている場合は、上書きを追加する必要があるないために、電子メール認証レコードを設定されている要求し、それらにお問い合わせください。詳細についてを参照してください[Office 365 のお客様ではありませんが、ドメインの管理者](#administrators-of-domains-that-are-not-office-365-customers)"後で参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p133">Because of the problem of spam and phishing, Microsoft recommends all senders set up email authentication. If you know an administrator of the sending domain, contact them and request that they set up email authentication records so you do not have to add any overrides. For more information, see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers)" later in this article.</span></span> 
  
<span data-ttu-id="bbd0f-309">送信ファイルの取得を認証するドメインに最初に困難な場合がありますが、時間の経過と共により多く電子メール フィルター junking か、自分の電子メールを拒否してより良い配信を確実に適切なレコードを設定するには発生します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-309">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span>
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="bbd0f-310">メッセージの数がスプーフィングされているとマークされたレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-310">Viewing reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="bbd0f-p134">スプーフィング対策ポリシーを有効にすると、番号がメッセージの数は、フィッシングとマークされたことを回避するのに脅威のインテリジェンスを使用できます。セキュリティに移動するのには、&amp;脅威の管理下にあるコンプライアンス センター (SCC)\>エクスプ ローラーでは、フィッシング、およびグループを送信者のドメインまたは保護の状態でビューを設定します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p134">Once your anti-spoofing policy is enabled, you can use Threat Intelligence to get numbers around how many messages are marked as phish. To do this, go into the Security &amp; Compliance Center (SCC) under Threat Management \> Explorer, set the View to Phish, and group by Sender Domain or Protection Status:</span></span>
  
![フィッシングとしてマークは、メッセージの数を表示します。](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
<span data-ttu-id="bbd0f-p135">数としてマークされているフィッシング、スプーフィングとしてマークされているメッセージなどを表示するさまざまなレポートと対話できます。詳細については、 [Office 365 の脅威インテリジェンス入門](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p135">You can interact with the various reports to see how many were marked as phishing, including messages marked as SPOOF. To learn more, see [Get started with Office 365 Threat Intelligence](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441).</span></span>
  
<span data-ttu-id="bbd0f-p136">まだ、どのメッセージがスプーフィングとフィッシング (一般的なフィッシング詐欺や、ドメインまたはユーザーの偽装) の他の型によってマークされたを分割することはできません。ただし、2018、後ですることがセキュリティであるのか&amp;コンプライアンス センターです。行うと、正規の認証が失敗したため、スプーフィングとしてマークされている可能性のある送信元のドメインを特定するのに出発点としてこのレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p136">You cannot yet split out which messages were marked due to spoofing vs. other types of phishing (general phishing, domain or user impersonation, and so on). However, later in 2018, you will be able to do this through the Security &amp; Compliance Center. Once you do, you can use this report as a starting place to identify sending domains that may be legitimate that are being marked as spoof due to failing authentication.</span></span>
  
<span data-ttu-id="bbd0f-319">次のスクリーン ショットは、このデータの外観がリリースされたときに変わる可能性がある提案です。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-319">The following screenshot is a proposal for how this data will look, but may change when released:</span></span>
  
![検出タイプでのフィッシング レポートを表示します。](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
<span data-ttu-id="bbd0f-p137">分析ツールではないと E5 のお客様は、これらのレポート 2018 脅威保護の状態 (TP) レポートには、[後で使用できるが、少なくとも 24 時間に遅れます。セキュリティに統合されているようにこのページを更新する&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p137">For non-ATP and E5 customers, these reports will be available later in 2018 under the Threat Protection Status (TPS) reports, but will be delayed by at least 24 hours. This page will be updated as they are integrated into the Security &amp; Compliance Center.</span></span>
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a><span data-ttu-id="bbd0f-323">メッセージの数は、スプーフィングとしてマークされますを予測します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-323">Predicting how many messages will be marked as spoof</span></span>

<span data-ttu-id="bbd0f-p138">2018、後で Office 365 で使用すると、スプーフィング対策の実施を無効に設定を更新する 1 回または上で基本認証または高の強制が与えられますさまざまな設定でメッセージを変更する方法を表示する機能です。スプーフィング対策が無効の場合は、することが Basic; をオンにする場合は、スプーフィングとして検出されるメッセージの数を参照してください。または、Basic の場合は、することが高を有効にする場合は、スプーフィングとして検出されますどのように多くのメッセージを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p138">Later in 2018, once Office 365 updates its settings to let you turn the anti-spoofing enforcement Off, or on with Basic or High enforcement, you will be given the ability to see how message disposition will change at the various settings. That is, if anti-spoofing is Off, you will be able to see how many messages will be detected as Spoof if you turn to Basic; or, if it's Basic, you will be able to see how many more messages will be detected as Spoof if you turn it to High.</span></span>
  
<span data-ttu-id="bbd0f-p139">この機能は、現在開発中です。詳細については定義されている、セキュリティとコンプライアンス ・ センターのスクリーン ショットと PowerShell の例の両方にこのページが更新されます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p139">This feature is currently under development. As more details are defined, this page will be updated both with screenshots of the Security and Compliance Center, and with PowerShell examples.</span></span>
  
![Antispoofing を有効にするための「What-if」レポート](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![偽装された送信者を許可する可能性のあるユーザー エクスペリエンス](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a><span data-ttu-id="bbd0f-330">についてどのように迷惑メール、フィッシング詐欺、および高度なフィッシング詐欺の検出を組み合わせる</span><span class="sxs-lookup"><span data-stu-id="bbd0f-330">Understanding how spam, phishing, and advanced phishing detections are combined</span></span>

<span data-ttu-id="bbd0f-p140">ATP の有無にかかわらず、Exchange Online を使用する組織は、このサービスでは、マルウェア、スパム、精度の高いスパム、フィッシング、および一括としてメッセージを確認するときに実行する操作を指定できます。ATP お客様は、ATP のフィッシング対策ポリシーと EOP のお客様にとって、フィッシング詐欺対策ポリシーとメッセージが複数の検出の種類 (たとえば、マルウェア、フィッシング詐欺、およびユーザーの偽装) をヒット可能性がありますという事実、ある可能性がありますか、混乱を招くポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p140">Organizations that use Exchange Online, with or without ATP, can specify which actions to take when the service identifies messages as malware, spam, high confidence spam, phishing, and bulk. With the ATP Anti-phishing policies for ATP customers, and the Anti-phishing policies for EOP customers, and the fact that a message may hit multiple detection types (for example, malware, phishing, and user-impersonation), there may be some confusion as to which policy applies.</span></span> 
  
<span data-ttu-id="bbd0f-333">一般に、メッセージに適用されるポリシーは、CAT (カテゴリ) のプロパティに X Forefront スパム対策レポート ヘッダーで識別されます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-333">In general, the policy applied to a message is identified in the X-Forefront-Antispam-Report header in the CAT (Category) property.</span></span> 
  
|<span data-ttu-id="bbd0f-334">**Priority**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-334">**Priority**</span></span>|<span data-ttu-id="bbd0f-335">**ポリシー**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-335">**Policy**</span></span>|<span data-ttu-id="bbd0f-336">**分類**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-336">**Category**</span></span>|<span data-ttu-id="bbd0f-337">**場所、管理しますか。**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-337">**Where managed?**</span></span>|<span data-ttu-id="bbd0f-338">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-338">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bbd0f-339">1 </span><span class="sxs-lookup"><span data-stu-id="bbd0f-339">1</span></span>  <br/> |<span data-ttu-id="bbd0f-340">マルウェア</span><span class="sxs-lookup"><span data-stu-id="bbd0f-340">Malware</span></span>  <br/> |<span data-ttu-id="bbd0f-341">MALW</span><span class="sxs-lookup"><span data-stu-id="bbd0f-341">MALW</span></span>  <br/> |[<span data-ttu-id="bbd0f-342">マルウェアのポリシー</span><span class="sxs-lookup"><span data-stu-id="bbd0f-342">Malware policy</span></span>](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="bbd0f-343">すべての組織</span><span class="sxs-lookup"><span data-stu-id="bbd0f-343">All organizations</span></span>  <br/> |
|<span data-ttu-id="bbd0f-344">2 </span><span class="sxs-lookup"><span data-stu-id="bbd0f-344">2</span></span>  <br/> |<span data-ttu-id="bbd0f-345">フィッシング</span><span class="sxs-lookup"><span data-stu-id="bbd0f-345">Phishing</span></span>  <br/> |<span data-ttu-id="bbd0f-346">PHSH</span><span class="sxs-lookup"><span data-stu-id="bbd0f-346">PHSH</span></span>  <br/> |[<span data-ttu-id="bbd0f-347">ホストされるコンテンツ フィルター ポリシー</span><span class="sxs-lookup"><span data-stu-id="bbd0f-347">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="bbd0f-348">すべての組織</span><span class="sxs-lookup"><span data-stu-id="bbd0f-348">All organizations</span></span>  <br/> |
|<span data-ttu-id="bbd0f-349">3 </span><span class="sxs-lookup"><span data-stu-id="bbd0f-349">3</span></span>  <br/> |<span data-ttu-id="bbd0f-350">信頼度の高いスパム</span><span class="sxs-lookup"><span data-stu-id="bbd0f-350">High confidence spam</span></span>  <br/> |<span data-ttu-id="bbd0f-351">HSPM</span><span class="sxs-lookup"><span data-stu-id="bbd0f-351">HSPM</span></span>  <br/> |[<span data-ttu-id="bbd0f-352">ホストされるコンテンツ フィルター ポリシー</span><span class="sxs-lookup"><span data-stu-id="bbd0f-352">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="bbd0f-353">すべての組織</span><span class="sxs-lookup"><span data-stu-id="bbd0f-353">All organizations</span></span>  <br/> |
|<span data-ttu-id="bbd0f-354">4 </span><span class="sxs-lookup"><span data-stu-id="bbd0f-354">4</span></span>  <br/> |<span data-ttu-id="bbd0f-355">なりすまし</span><span class="sxs-lookup"><span data-stu-id="bbd0f-355">Spoofing</span></span>  <br/> |<span data-ttu-id="bbd0f-356">なりすまし</span><span class="sxs-lookup"><span data-stu-id="bbd0f-356">SPOOF</span></span>  <br/> |<span data-ttu-id="bbd0f-357">[フィッシング詐欺対策ポリシー](https://go.microsoft.com/fwlink/?linkid=864553)[なりすましのインテリジェンス](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span><span class="sxs-lookup"><span data-stu-id="bbd0f-357">[Anti-phishing policy](https://go.microsoft.com/fwlink/?linkid=864553),          [Spoof intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span></span> <br/> |<span data-ttu-id="bbd0f-358">すべての組織</span><span class="sxs-lookup"><span data-stu-id="bbd0f-358">All organizations</span></span>  <br/> |
|<span data-ttu-id="bbd0f-359">5 </span><span class="sxs-lookup"><span data-stu-id="bbd0f-359">5</span></span>  <br/> |<span data-ttu-id="bbd0f-360">スパム</span><span class="sxs-lookup"><span data-stu-id="bbd0f-360">Spam</span></span>  <br/> |<span data-ttu-id="bbd0f-361">SPM</span><span class="sxs-lookup"><span data-stu-id="bbd0f-361">SPM</span></span>  <br/> |[<span data-ttu-id="bbd0f-362">ホストされるコンテンツ フィルター ポリシー</span><span class="sxs-lookup"><span data-stu-id="bbd0f-362">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="bbd0f-363">すべての組織</span><span class="sxs-lookup"><span data-stu-id="bbd0f-363">All organizations</span></span>  <br/> |
|<span data-ttu-id="bbd0f-364">6 </span><span class="sxs-lookup"><span data-stu-id="bbd0f-364">6</span></span>  <br/> |<span data-ttu-id="bbd0f-365">一括</span><span class="sxs-lookup"><span data-stu-id="bbd0f-365">Bulk</span></span>  <br/> |<span data-ttu-id="bbd0f-366">一括</span><span class="sxs-lookup"><span data-stu-id="bbd0f-366">BULK</span></span>  <br/> |[<span data-ttu-id="bbd0f-367">ホストされるコンテンツ フィルター ポリシー</span><span class="sxs-lookup"><span data-stu-id="bbd0f-367">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="bbd0f-368">すべての組織</span><span class="sxs-lookup"><span data-stu-id="bbd0f-368">All organizations</span></span>  <br/> |
|<span data-ttu-id="bbd0f-369">7 </span><span class="sxs-lookup"><span data-stu-id="bbd0f-369">7</span></span>  <br/> |<span data-ttu-id="bbd0f-370">ドメインの偽装</span><span class="sxs-lookup"><span data-stu-id="bbd0f-370">Domain Impersonation</span></span>  <br/> |<span data-ttu-id="bbd0f-371">DIMP</span><span class="sxs-lookup"><span data-stu-id="bbd0f-371">DIMP</span></span>  <br/> |[<span data-ttu-id="bbd0f-372">フィッシング詐欺対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="bbd0f-372">Anti-phishing policy</span></span>](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |<span data-ttu-id="bbd0f-373">ATP の組織のみ</span><span class="sxs-lookup"><span data-stu-id="bbd0f-373">Organizations with ATP only</span></span>  <br/> |
|<span data-ttu-id="bbd0f-374">8 </span><span class="sxs-lookup"><span data-stu-id="bbd0f-374">8</span></span>  <br/> |<span data-ttu-id="bbd0f-375">ユーザーの偽装</span><span class="sxs-lookup"><span data-stu-id="bbd0f-375">User Impersonation</span></span>  <br/> |<span data-ttu-id="bbd0f-376">UIMP</span><span class="sxs-lookup"><span data-stu-id="bbd0f-376">UIMP</span></span>  <br/> |[<span data-ttu-id="bbd0f-377">フィッシング詐欺対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="bbd0f-377">Anti-phishing policy</span></span>](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |<span data-ttu-id="bbd0f-378">ATP の組織のみ</span><span class="sxs-lookup"><span data-stu-id="bbd0f-378">Organizations with ATP only</span></span> <br/> |
   
<span data-ttu-id="bbd0f-p141">別のフィッシング詐欺対策ポリシーが複数ある場合は、最高の優先順位で適用されます。たとえば、2 つのポリシーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p141">If you have multiple different Anti-phishing policies, the one at the highest priority will apply. For example, suppose you have two policies:</span></span>
  
|<span data-ttu-id="bbd0f-381">**ポリシー**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-381">**Policy**</span></span>|<span data-ttu-id="bbd0f-382">**Priority**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-382">**Priority**</span></span>|<span data-ttu-id="bbd0f-383">**ユーザー/ドメインの偽装**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-383">**User/Domain Impersonation**</span></span>|<span data-ttu-id="bbd0f-384">**スプーフィング対策**</span><span class="sxs-lookup"><span data-stu-id="bbd0f-384">**Anti-spoofing**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bbd0f-385">A</span><span class="sxs-lookup"><span data-stu-id="bbd0f-385">A</span></span>  <br/> |<span data-ttu-id="bbd0f-386">1 </span><span class="sxs-lookup"><span data-stu-id="bbd0f-386">1</span></span>  <br/> |<span data-ttu-id="bbd0f-387">On</span><span class="sxs-lookup"><span data-stu-id="bbd0f-387">On</span></span>  <br/> |<span data-ttu-id="bbd0f-388">Off</span><span class="sxs-lookup"><span data-stu-id="bbd0f-388">Off</span></span>  <br/> |
|<span data-ttu-id="bbd0f-389">B</span><span class="sxs-lookup"><span data-stu-id="bbd0f-389">B</span></span>  <br/> |<span data-ttu-id="bbd0f-390">2 </span><span class="sxs-lookup"><span data-stu-id="bbd0f-390">2</span></span>  <br/> |<span data-ttu-id="bbd0f-391">Off</span><span class="sxs-lookup"><span data-stu-id="bbd0f-391">Off</span></span>  <br/> |<span data-ttu-id="bbd0f-392">オン</span><span class="sxs-lookup"><span data-stu-id="bbd0f-392">On</span></span>  <br/> |
   
<span data-ttu-id="bbd0f-393">メッセージは、スプーフィングおよびユーザーの偽装とは、識別しユーザーの同じセットのスコープは、ポリシー A と B のポリシー、し、メッセージは、スプーフィングとして扱われますと以降のアクションは適用されませんスプーフィング対策がになっています。、なりすましは、ユーザーの偽装 (8) よりも高い優先順位 (4) で実行されるとします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-393">If a message comes in and is identified as both spoofing and user impersonation, and the same set of users is scoped to Policy A and Policy B, then the message is treated as a spoof but no action is applied since Anti-spoofing is turned off, and SPOOF runs at a higher priority (4) than User Impersonation (8).</span></span>
  
<span data-ttu-id="bbd0f-394">フィッシング詐欺の他の種類を作成するには、ポリシーの適用に適用するさまざまなポリシーの設定を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-394">To make other types of phishing policy apply, you will need to adjust the settings of who the various policies are applied to.</span></span>
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a><span data-ttu-id="bbd0f-395">スプーフィング対策を無効にする正当なシナリオ</span><span class="sxs-lookup"><span data-stu-id="bbd0f-395">Legitimate scenarios to disable anti-spoofing</span></span>

<span data-ttu-id="bbd0f-p142">スプーフィング対策、フィッシング攻撃からお客様を保護してより、したがってスプーフィング対策の保護を無効にすること強くお勧めします。それを無効にすることは、長期的にリスクの詳細に公開するのですが、いくつか短期的な誤認識を解決する可能性があります。送信者側では、認証を設定するかで、フィッシング詐欺のポリシーを調整することのコストは通常 1 回限りのイベントであるか、最小限、定期的なメンテナンスを必要とします。ただし、データが公開されている、フィッシング攻撃から回復するためのコスト、または資産がされているが非常に高い危険にさらさです。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p142">Anti-spoofing better protects customers from phishing attacks, and therefore disabling anti-spoofing protection is strongly discouraged. By disabling it, you may resolve some short-term false positives, but long term you will be exposed to more risk. The cost for setting up authentication on the sender side, or making adjustments in the phishing policies, are usually one-time events or require only minimal, periodic maintenance. However, the cost to recover from a phishing attack where data has been exposed, or assets have been compromised is much higher.</span></span>
  
<span data-ttu-id="bbd0f-400">このため、スプーフィング対策誤検出にアンチ スプーフ保護を無効にするよりもを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-400">For this reason, it is better to work through anti-spoofing false positives than to disable anti-spoof protection.</span></span>
  
<span data-ttu-id="bbd0f-401">ただし、正当なシナリオ、スプーフィング対策は無効にする必要があります、およびその他のメール ・ フィルタ リングがある場合に、メッセージのルーティング、および Office 365 の製品は、電子メールのパスの最初のホップではありません。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-401">However, there is a legitimate scenario where anti-spoofing should be disabled, and that is when there are additional mail-filtering products in the message routing, and Office 365 is not the first hop in the email path:</span></span>
  
![顧客の MX レコードが Office 365 をポイントしていません。](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
<span data-ttu-id="bbd0f-403">Exchange のオンプレミスのメール サーバー、Ironport などのデバイスをフィルタ リングするメールを他のサーバーがありますか、他のクラウド サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-403">The other server may be an Exchange on-premise mail server, a mail filtering device such as Ironport, or another cloud hosted service.</span></span>
  
<span data-ttu-id="bbd0f-p143">場合は受信者のドメインの MX レコードが Office 365 に、Office 365 は、受信側ドメインの MX レコードを検索し、別のサービスを指す場合は、スプーフィング対策を抑制するため、スプーフィング対策を無効にする必要がありません。かどうか、ドメインには、別のサーバー前面にない場合は、MX レコードを検索するのには、MX のツールボックスのような web サイトを使用できます。次のようなと言えます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p143">If the MX record of the recipient domain does not point to Office 365, then there is no need to disable anti-spoofing because Office 365 looks up your receiving domain's MX record and suppresses anti-spoofing if it points to another service. If you don't know if your domain has another server in front, you can use a website like MX Toolbox to look up the MX record. It might say something like the following:</span></span>
  
![MX レコードは、ドメインを Office 365 をポイントしていないことを示します](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
<span data-ttu-id="bbd0f-408">このドメインは、Office 365 はスプーフィング対策の実施を適用していないため、Office 365 を指していない MX レコードを持っています。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-408">This domain has an MX record that does not point to Office 365, so Office 365 would not apply anti-spoofing enforcement.</span></span>
  
<span data-ttu-id="bbd0f-p144">ただし場合*は、* 受信者のドメインの MX レコードは、Office 365 の前に別のサービスが存在する場合でも、Office 365 をポイント、しする必要がありますを無効にスプーフィング対策。最も一般的な例は、アドレス書き換えを使用することです。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p144">However, if the MX record of the recipient domain  *does*  point to Office 365, even though there is another service in front of Office 365, then you should disable anti-spoofing. The most common example is through the use of a recipient rewrite:</span></span> 
  
![書き換えの受信者のルーティングの図](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
<span data-ttu-id="bbd0f-412">ドメイン contoso.com の MX レコードが指す、オンプレミスのサーバーが含まれているために、ドメイン @office365.contoso .net の MX レコードが Office 365 を指すときに\*です。 protection.outlook.com、または\*。 MX レコードに eo.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-412">The domain contoso.com's MX record points to the on-premise server, while the domain @office365.contoso.net's MX record points to Office 365 because it contains \*.protection.outlook.com, or \*.eo.outlook.com in the MX record:</span></span>
  
![Office 365 に MX レコードのポイント、したがって可能性があります受信者を書き換える](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
<span data-ttu-id="bbd0f-p145">受信者のドメインの MX レコードが、Office 365 をポイントしていないとき、および受信者の書き換えを行ったことを区別することを確認します。これら 2 つのケースを区別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p145">Be sure to differentiate when a recipient domain's MX record does not point to Office 365, and when it has undergone a recipient rewrite. It is important to tell the difference between these two cases.</span></span>
  
<span data-ttu-id="bbd0f-416">受信側のドメインが受信者の書き換えを行われているかどうかがわからない場合があることがわかりますメッセージ ヘッダーを調べることによって。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-416">If you are unsure whether or not your receiving domain has undergone a recipient-rewrite, sometimes you can tell by looking at the message headers.</span></span>
  
<span data-ttu-id="bbd0f-417">) 最初に、認証結果のヘッダー内の受信者のドメインへのメッセージのヘッダーになります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-417">a) First, look at the headers in the message for the recipient domain in the Authentication-Results header:</span></span> 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

<span data-ttu-id="bbd0f-p146">受信者のドメインが、赤い太字テキストで、このケースの office365.contoso.net であります。これは異なる場合があることで指定した受信者: ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p146">The recipient domain is found in the bold red text above, in this case office365.contoso.net. This may be different that the recipient in the To: header:</span></span>
  
<span data-ttu-id="bbd0f-420">に: 例受信者\<受信者のメールボックス ストア\></span><span class="sxs-lookup"><span data-stu-id="bbd0f-420">To: Example Recipient \<recipient @ contoso.com\></span></span>
  
<span data-ttu-id="bbd0f-p147">実際の受信者のドメイン、MX レコードのルックアップを実行します。含まれている場合は\*です。 protection.outlook.com、mail.messaging.microsoft.com、\*です。 eo.outlook.com、または mail.global.frontbridge.com、MX は、Office 365 を指していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p147">Perform an MX-record lookup of the actual recipient domain. If it contains \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com, or mail.global.frontbridge.com, that means that the MX points to Office 365.</span></span>
  
<span data-ttu-id="bbd0f-p148">これらの値を含まない場合、MX は、Office 365 には指していないことを示します。これを確認することができますを使用するツールの 1 つは、MX のツールボックスです。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p148">If it does not contain those values, then it means that the MX does not point to Office 365. One tool you can use to verify this is MX Toolbox.</span></span>
  
<span data-ttu-id="bbd0f-425">この例では、次の質問を contoso.com ドメインにされてから、受信者のような: ヘッダーには、prem のサーバーに MX レコードのポイント。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-425">For this particular example, the following says that contoso.com, the domain that looks like the recipient since it was the To: header, has MX record points to an on-prem server:</span></span>
  
![Prem のサーバーを指す MX レコード](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
<span data-ttu-id="bbd0f-427">ただし、実際の受信者は、MX レコードは、Office 365 をポイントして、office365.contoso.net です。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-427">However, the actual recipient is office365.contoso.net whose MX record does point to Office 365:</span></span>
  
![受信者の書き換えをする必要があります、Office 365 を指す MX](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
<span data-ttu-id="bbd0f-429">したがって、このメッセージには、受信者の書き換えがおそらく行われています。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-429">Therefore, this message has likely undergone a recipient-rewrite.</span></span>
  
<span data-ttu-id="bbd0f-p149">b) 次に、受信者の書き換えの一般的な用途を区別することを確認します。受信者のドメインを書き換えるしようとしているかどうかは\*です。 onmicrosoft.com、代わりにするように書き直します\*です。 mail.onmicrosoft.com です。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p149">b) Second, be sure to distinguish between common use cases of recipient rewrites. If you are going to rewrite the recipient domain to \*.onmicrosoft.com, instead rewrite it to \*.mail.onmicrosoft.com.</span></span>
  
<span data-ttu-id="bbd0f-432">別のサーバーの背後にあるルートは、最終的な受信者のドメインを特定し、受信者のドメインの MX レコードは、実際に (と、その DNS レコードの発行) に、Office 365 を指す、スプーフィング対策を無効にするのに進みます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-432">Once you have identified the final recipient domain that is routed behind another server and the recipient domain's MX record actually points to Office 365 (as published in its DNS records), you may proceed to disable anti-spoofing.</span></span>
  
<span data-ttu-id="bbd0f-433">1 つまたは複数のサービスの背後にある場合にのみ、ドメインの最初のホップ ルーティング パスでは、Office 365 の場合、スプーフィング対策を無効にしたくないことを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-433">Remember, you don't want to disable anti-spoofing if the domain's first hop in the routing path is Office 365, only when it's behind one or more services.</span></span>
  
### <a name="how-to-disable-anti-spoofing"></a><span data-ttu-id="bbd0f-434">スプーフィング対策を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="bbd0f-434">How to disable anti-spoofing</span></span>

<span data-ttu-id="bbd0f-435">既にした場合、フィッシング詐欺対策ポリシーの作成、EnableAntispoofEnforcement パラメーターを $false に設定します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-435">If you already have an Anti-phishing policy created, set the EnableAntispoofEnforcement parameter to $false:</span></span> 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

<span data-ttu-id="bbd0f-436">無効にするポリシー (またはポリシー) の名前がわからない場合は、それらを表示できます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-436">If you don't know the name of the policy (or policies) to disable, you can display them:</span></span> 
  
```
Get-AntiphishPolicy | fl Name
```

<span data-ttu-id="bbd0f-p150">何らかのフィッシング詐欺対策ポリシーをお持ちでない場合は、作成し、無効にすること (場合でも、ポリシーがない、スプーフィング対策がまだ適用されている 2018年の後で、既定のポリシーが作成されますし、無効にすることを 1 つを作成する代わりに).これは複数のステップで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p150">If you don't have any existing anti-phishing policies, you can create one and then disable it (even if you don't have a policy, anti-spoofing is still applied; later on in 2018, a default policy will be created for you and you can then disable that instead of creating one). You will have to do this in multiple steps:</span></span> 
  
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

<span data-ttu-id="bbd0f-p151">スプーフィング対策を無効にすると、コマンドレットを使用して利用可能なのみ (第 2 四半期 2018年のことが、セキュリティで利用可能な&amp;コンプライアンス センター)。PowerShell へのアクセスがない場合は、サポート チケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p151">Disabling anti-spoofing is only available via cmdlet (later in Q2 2018 it will be available in the Security &amp; Compliance Center). If you do not have access to PowerShell, create a support ticket.</span></span>
  
<span data-ttu-id="bbd0f-p152">Office 365 に送信された場合に間接的なルーティングが行われるようドメインにのみ適用されるこのことを忘れないでください。スプーフィング対策をいくつかの誤認識が発生したため無効にするは我慢より長期的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p152">Remember, this should only be applied to domains that undergo indirect routing when sent to Office 365. Resist the temptation to disable anti-spoofing because of some false positives, it will be better in the long run to work through them.</span></span>
  
### <a name="information-for-individual-users"></a><span data-ttu-id="bbd0f-443">個々 のユーザーの情報</span><span class="sxs-lookup"><span data-stu-id="bbd0f-443">Information for individual users</span></span>

<span data-ttu-id="bbd0f-p153">個々 のユーザーは、スプーフィング対策の安全性のヒントとやり取りする方法に制限されます。ただし、これには一般的なシナリオを解決するのにはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p153">Individual users are limited in how they can interact with the anti-spoofing safety tip. However, there are several things you can do to resolve common scenarios.</span></span>
  
### <a name="common-scenario-1---mailbox-forwarding"></a><span data-ttu-id="bbd0f-446">共通シナリオ 1: メールボックスの転送</span><span class="sxs-lookup"><span data-stu-id="bbd0f-446">Common scenario #1 - Mailbox forwarding</span></span>

<span data-ttu-id="bbd0f-p154">場合は別の電子メール サービスを使用して Office 365 または Outlook.com に電子メールを転送して、電子メールはスプーフィングとしてマークすることもし、赤の安全性のヒントが表示されます。Office 365 と Outlook.com は、フォワーダーは、Outlook.com、Office 365、Gmail、または[円弧のプロトコル](https://arc-spec.org)を使用するその他のサービスのいずれかのときに自動的にアドレスを計画します。ただし、その修正プログラムを展開するまでユーザーが接続されているアカウントの機能を転送] オプションを使用するのではなく、直接のメッセージをインポートするのに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p154">If you use another email service and forward your email to Office 365 or Outlook.com, your email may be marked as spoofing and receive a red safety tip. Office 365 and Outlook.com plan to address this automatically when the forwarder is one of Outlook.com, Office 365, Gmail, or any other service that uses the [ARC protocol](https://arc-spec.org). However, until that fix is deployed, users should use the Connected Accounts feature to import their messages directly, rather than using the forwarding option.</span></span>
  
<span data-ttu-id="bbd0f-450">Office 365 に接続されているアカウントを設定するに、Office 365 の web インターフェイスの右上隅に歯車のアイコンを選択します\>メール\>メール\>アカウント\>アカウントに接続します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-450">To set up connected accounts in Office 365, select the Gear icon in the top right corner of the Office 365 web interface \> Mail \> Mail \> Accounts \> Connected accounts.</span></span>
  
![Office 365 に接続されているアカウントのオプション](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
<span data-ttu-id="bbd0f-452">Outlook.com では、プロセスは、歯車のアイコンを\>オプション\>メール\>アカウント\>接続されているアカウントです。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-452">In Outlook.com, the process is the Gear icon \> Options \> Mail \> Accounts \> Connected accounts.</span></span>
  
### <a name="common-scenario-2---discussion-lists"></a><span data-ttu-id="bbd0f-453">共通シナリオ 2 の説明を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-453">Common scenario #2 - Discussion lists</span></span>

<span data-ttu-id="bbd0f-454">ディスカッションのリストは既知のスプーフィング対策方法により、転送の問題があるメッセージとその内容を変更からオリジナルを保持する: アドレスです。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-454">Discussion lists are known to have problems with anti-spoofing due to the way they forward the message and modify its contents yet retain the original From: address.</span></span>
  
<span data-ttu-id="bbd0f-p155">たとえば、あなたの電子メール アドレスは、ユーザーのメールボックス ストア、し、バードウォッチングに興味のあるディスカッションのリスト birdwatchers @ example.com に参加します。ディスカッションのリストにメッセージを送信するときは、このように送信可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p155">For example, suppose your email address is user @ contoso.com, and you are interested in Bird Watching and join the discussion list birdwatchers @ example.com. When you send a message to the discussion list, you might send it this way:</span></span>
  
<span data-ttu-id="bbd0f-457">**から:** John Doe\<ユーザーのメールボックス ストア\></span><span class="sxs-lookup"><span data-stu-id="bbd0f-457">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="bbd0f-458">**に:** ディスカッション リストの birdwatcher の\<@ example.com birdwatchers\></span><span class="sxs-lookup"><span data-stu-id="bbd0f-458">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="bbd0f-p156">**件名:** 今週レイニアの上部にあるカシドリの優れた表示</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p156">**Subject:** Great viewing of blue jays at the top of Mt. Rainier this week</span></span> 
  
<span data-ttu-id="bbd0f-p157">表示を確認すると誰でも今週レイニアからでしょうか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p157">Anyone want to check out the viewing this week from Mt. Rainier?</span></span>
  
<span data-ttu-id="bbd0f-463">電子メール] ボックスの一覧では、メッセージを受信したとき、メッセージの書式を設定、その内容を変更、参加者の多くの別の電子メールの受信機から構成されるディスカッションのリストのメンバーの残りの部分を再生します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-463">When the email list receives the message, they format the message, modify its contents, and replay it to the rest of the members on the discussion list which is made up of participants from many different email receivers.</span></span>
  
<span data-ttu-id="bbd0f-464">**から:** John Doe\<ユーザーのメールボックス ストア\></span><span class="sxs-lookup"><span data-stu-id="bbd0f-464">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="bbd0f-465">**に:** ディスカッション リストの birdwatcher の\<@ example.com birdwatchers\></span><span class="sxs-lookup"><span data-stu-id="bbd0f-465">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="bbd0f-p158">**件名:**[BIRDWATCHERS]今週レイニアの上部にあるカシドリの優れた表示</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p158">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt. Rainier this week</span></span> 
  
<span data-ttu-id="bbd0f-p159">表示を確認すると誰でも今週レイニアからでしょうか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p159">Anyone want to check out the viewing this week from Mt. Rainier?</span></span>
  
---
  
<span data-ttu-id="bbd0f-p160">Birdwatchers ディスカッションのリストにこのメッセージが送信されました。いつでも購読を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p160">This message was sent to the Birdwatchers Discussion List. You can unsubscribe at any time.</span></span>
  
<span data-ttu-id="bbd0f-p161">上で再生されたメッセージには同じ: アドレス (ユーザーのメールボックス ストア) は、元のメッセージが、件名とメッセージの下部にフッターにタグを追加することによって変更されています。この種類のメッセージの変更は、メーリング リストでは、一般的な誤検出が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p161">In the above, the replayed message has the same From: address (user @ contoso.com) but the original message has been modified by adding a tag to the Subject line, and a footer to the bottom of the message. This type of message modification is common in mailing lists, and may result in false positives.</span></span>
  
<span data-ttu-id="bbd0f-474">または他の組織では、メーリング リストの管理者には、スプーフィング対策のチェックに合格するように構成できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-474">If you or someone in your organization is an administrator of the mailing list, you may be able to configure it to pass anti-spoofing checks.</span></span>
  
- <span data-ttu-id="bbd0f-475">DMARC.org の FAQ を確認:[何をすれば、メーリング リストを操作して、DMARC と相互運用したいですか?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span><span class="sxs-lookup"><span data-stu-id="bbd0f-475">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span></span>
    
- <span data-ttu-id="bbd0f-476">」の手順には、このブログの投稿を読む:[エラーを避けるために DMARC と相互運用するメーリング リストの演算子のヒント](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span><span class="sxs-lookup"><span data-stu-id="bbd0f-476">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span></span>
    
- <span data-ttu-id="bbd0f-477">円弧のサポートを参照して、メーリング リストのサーバーに更新プログラムのインストールを検討してください。[https://arc-spec.org](https://arc-spec.org/)</span><span class="sxs-lookup"><span data-stu-id="bbd0f-477">Consider installing updates on your mailing list server to support ARC, see [https://arc-spec.org](https://arc-spec.org/)</span></span>
    
<span data-ttu-id="bbd0f-478">場合はメーリング リストの所有権を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-478">If you do not have ownership of the mailing list:</span></span>
  
- <span data-ttu-id="bbd0f-479">(また必要があります電子メールの認証ドメインからの中継は、メーリング リストの設定) の上のオプションのいずれかを実装するのにはメーリング リストの管理者を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-479">You can request the maintainer of the mailing list to implement one of the options above (they should also have email authentication set up for the domain the mailing list is relaying from)</span></span>
    
- <span data-ttu-id="bbd0f-p162">メッセージを受信トレイに移動するように電子メール クライアントで、メールボックスのルールを作成できます。設定するのには、組織の管理者に許可する規則、または管理する正当な送信者は認証されていないメールを送信することでオーバーライドとして説明を要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p162">You can create mailbox rules in your email client to move messages to the Inbox. You can also request your organization's administrators to set up allow rules, or overrides as discussed in the section Managing legitimate senders who are sending unauthenticated email</span></span>
    
- <span data-ttu-id="bbd0f-482">正当なものとして扱うメーリング リストの上書きを作成するのには Office 365 のサポート チケットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-482">You can create a support ticket with Office 365 to create an override for the mailing list to treat it as legitimate</span></span>
    
### <a name="other-scenarios"></a><span data-ttu-id="bbd0f-483">その他のシナリオ</span><span class="sxs-lookup"><span data-stu-id="bbd0f-483">Other scenarios</span></span>

1. <span data-ttu-id="bbd0f-p163">上の一般的なシナリオのどちらもは、自分の状況に適用する場合、false 正バックアップとしてメッセージをマイクロソフトに報告します。詳細についてを参照してください[方法ことができますか迷惑メールまたはスパムでないメッセージをマイクロソフトに報告しますか?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)この資料で後述します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p163">If neither of the above common scenarios applies to your situation, report the message as a false positive back to Microsoft. For more information, see the section [How can I report spam or non-spam messages back to Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) later in this article.</span></span> 
    
2. <span data-ttu-id="bbd0f-p164">マイクロソフトとサポート チケットとそれを発生させることができます、電子メール管理者にお問い合わせくださいする可能性がありますも。マイクロソフトのエンジニア リング チームは、スプーフィングとしてメッセージが表示された理由を調査します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p164">You may also contact your email administrator who can raise it as a support ticket with Microsoft. The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>
    
3. <span data-ttu-id="bbd0f-p165">さらに、送信者をすることはない悪意のある偽装されたと確信できる場合は、認証しないメール サーバーからメッセージが送信されていることを示す送信者に返信することがあります。場合があります、その結果、元の送信者が必要な電子メール認証レコードが設定されますが、IT 管理者に連絡します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p165">Additionally, if you know who the sender is and are confident they are not being maliciously spoofed, you may reply back to the sender indicating that they are sending messages from a mail server that does not authenticate. This sometimes results in the original sender contacting their IT administrator who will set up the required email authentication records.</span></span>
  
<span data-ttu-id="bbd0f-p166">十分な送信者は、電子メール認証レコードを設定する必要があるドメインの所有者に返信、するとことを受け、そのアクションを取るように。マイクロソフトは、必要なレコードを発行するドメインの所有者でも動作することが、中には、さらに個々 のユーザーは、要求にことができます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p166">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action. While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>
    
4. <span data-ttu-id="bbd0f-p167">必要に応じて、[差出人セーフ リストに送信者を追加します。ただし、こと場合は、フィッシャーは、そのアカウントをスプーフィング、それはメールボックスに配信される、対応します。したがって、多用しないようにこのオプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p167">Optionally, add the sender to your Safe Senders list. However, be aware that if a phisher spoofs that account, it will be delivered to your mailbox. Therefore, this option should be used sparingly.</span></span>
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a><span data-ttu-id="bbd0f-495">スプーフィング対策の保護のために送信者をどのように準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-495">How senders to Microsoft should prepare for anti-spoofing protection</span></span>

<span data-ttu-id="bbd0f-496">管理者は、現在のメッセージを Microsoft に送信する場合は Office 365 または Outlook.com のいずれかを確認してください、メールが正しく認証されている迷惑メールまたはフィッシングとそうしないとマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-496">If you are an administrator who currently sends messages to Microsoft, either Office 365 or Outlook.com, you should ensure that your email is properly authenticated otherwise it may be marked as spam or phish.</span></span> 
  
### <a name="customers-of-office-365"></a><span data-ttu-id="bbd0f-497">Office 365 のお客様</span><span class="sxs-lookup"><span data-stu-id="bbd0f-497">Customers of Office 365</span></span>

<span data-ttu-id="bbd0f-498">Office 365 をご送信の電子メールを送信するのには Office 365 を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-498">If you are an Office 365 customer and you use Office 365 to send outbound email:</span></span>
  
- <span data-ttu-id="bbd0f-499">[スプーフィングを防止するために Office 365 の SPF を設定](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)ドメインの</span><span class="sxs-lookup"><span data-stu-id="bbd0f-499">For your domains, [Set up SPF in Office 365 to help prevent spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)</span></span>
    
- <span data-ttu-id="bbd0f-500">[カスタム ドメインを Office 365 から送信された送信の電子メールを検証するために DKIM を使用して](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、プライマリ ドメインの</span><span class="sxs-lookup"><span data-stu-id="bbd0f-500">For your primary domains, [Use DKIM to validate outbound email sent from your custom domain in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)</span></span>
    
- <span data-ttu-id="bbd0f-501">正当な送信者は、ユーザーを決定するのに、ドメインの[DMARC レコードの設定](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)を</span><span class="sxs-lookup"><span data-stu-id="bbd0f-501">[Consider setting up DMARC records](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) for your domain to determine who are your legitimate senders</span></span> 
    
<span data-ttu-id="bbd0f-p168">マイクロソフトでは、SPF、DKIM、DMARC のそれぞれの実装の詳細なガイドラインを提供していません。ただし、多くの情報をオンラインで公開があります。サード パーティの企業電子メール認証レコードを設定する組織を支援します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p168">Microsoft does not provide detailed implementation guidelines for each of SPF, DKIM, and DMARC. However, there is a lot of information published online. There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a><span data-ttu-id="bbd0f-505">Office 365 のお客様ではないドメインの管理者</span><span class="sxs-lookup"><span data-stu-id="bbd0f-505">Administrators of domains that are not Office 365 customers</span></span>

<span data-ttu-id="bbd0f-506">ドメイン管理者は、Office 365 の顧客ではない場合。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-506">If you are a domain administrator but are not an Office 365 customer:</span></span>
  
- <span data-ttu-id="bbd0f-p169">必要があります、ドメインの送信元の IP アドレスを発行するのには、SPF を設定しを設定する DKIM (ある場合) メッセージにデジタル署名します。DMARC レコードの設定を考慮することがあります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p169">You should set up SPF to publish your domain's sending IP addresses, and also set up DKIM (if available) to digitally sign messages. You may also consider setting up DMARC records.</span></span>
    
- <span data-ttu-id="bbd0f-509">一括送信者に代わってメールを送信した場合は、必要がありますを使用する方法で電子メールを送信するようするようから送信側のドメイン: SPF または DMARC を通過するドメインとアドレス (該当する場合に属する) に揃えて配置します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-509">If you have bulk senders who are transmitting email on your behalf, you should work with them to send email in a way such that the sending domain in the From: address (if it belongs to you) aligns with the domain that passes SPF or DMARC.</span></span>
    
- <span data-ttu-id="bbd0f-510">オンプレミス メール サーバー、または、サービスとしてのソフトウェアのプロバイダー、または、Microsoft Azure、GoDaddy、ラック、Amazon Web サービスのようなクラウド ・ ホスティング サービスから送信またはと同様に、するようにする場合は、SPF レコードに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-510">If you have on-premise mail servers, or send from a Software-as-a-service provider, or from a cloud-hosting service like Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, or similar, you should ensure that they are added to your SPF record.</span></span>
    
- <span data-ttu-id="bbd0f-p170">ISP によってホストされている小規模なドメインの場合は、ISP が提供するの SPF レコードの説明書に従って設定してください。ほとんどの Isp では、命令のこれらの種類を提供し、会社のサポート ページにあります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p170">If you are a small domain that is hosted by an ISP, you should set up your SPF record according to the instructions that is provided to you by your ISP. Most ISPs provide these types of instructions and can be found on the company's support pages.</span></span>
    
- <span data-ttu-id="bbd0f-p171">場合でもする前に、電子メールの認証レコードを発行する必要がないと正常に動作しました、まだ Microsoft に送信する電子メールの認証レコードを発行する必要があります。そうするには、フィッシング詐欺との闘いにおいて支援している phished、または送信する組織のいずれかを取得する可能性を軽減します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p171">Even if you have not had to publish email authentication records before, and it worked fine, you must still publish email authentication records to send to Microsoft. By doing so, you are helping in the fight against phishing, and reducing the possibility that either you, or organizations you send to, will get phished.</span></span>
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a><span data-ttu-id="bbd0f-515">場合、ドメインと電子メールを送信したがわからないでしょうか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-515">What if you don't know who sends email as your domain?</span></span>

<span data-ttu-id="bbd0f-p172">多くのドメインは、そのすべての送信者は、ユーザーを把握していないため SPF レコードを発行できません。では、ユーザーを認識する必要はありませんがそれらのすべてです。代わりに、必要があります開始するものの特に、企業内のトラフィックのある場所を知っているし、中立的な SPF ポリシーを発行するは、SPF レコードを発行することによってですか? すべて。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p172">Many domains do not publish SPF records because they do not know who all their senders are. That's okay, you do not need to know who all of them are. Instead, you should get started by publishing an SPF record for the ones you do know of, especially where your corporate traffic is located, and publish a neutral SPF policy, ?all:</span></span>
  
<span data-ttu-id="bbd0f-519">example.com の TXT」v = spf1 include:spf.example.com? すべて"</span><span class="sxs-lookup"><span data-stu-id="bbd0f-519">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span></span>
  
<span data-ttu-id="bbd0f-p173">ニュートラルの SPF ポリシーでは、渡すことが、企業のインフラストラクチャが付属しているすべての電子メールは電子メールの認証に他の電子メールの受信機を意味します。把握できていない送信者から送信される電子メールは、中立的なない SPF レコードを公開しないとほぼ同じであるに再び確立されます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p173">The neutral SPF policy means that any email that comes out of your corporate infrastructure will pass email authentication at all other email receivers. Email that comes from senders you don't know about will fall back to neutral, which is almost the same as publishing no SPF record at all.</span></span>
  
<span data-ttu-id="bbd0f-p174">認証されるように、企業内のトラフィックから送信される電子メールをマークする、Office 365 に送信するときは (かどうか Office 365 に暗黙的に認証できることによる) のスプーフィングとして把握できていないソースから送信される電子メールをマークすることもまだです。しかし、これは Office 365 で、スプーフィングとしてマークされているすべての電子メールから改善します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p174">When sending to Office 365, email that comes from your corporate traffic will be marked as authenticated, but the email that comes from sources you don't know about may still be marked as spoof (depending upon whether or not Office 365 can implicitly authenticate it). However, this is still an improvement from all email being marked as spoof by Office 365.</span></span>
  
<span data-ttu-id="bbd0f-524">フォールバック ポリシーを使用して SPF レコードを開始取得するとしますか? より多くの送信元のインフラストラクチャは、徐々 にできより厳しいポリシーを公開し、すべて。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-524">Once you've gotten started with an SPF record with a fallback policy of ?all, you can gradually include more and more sending infrastructure and then publish a stricter policy.</span></span> 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a><span data-ttu-id="bbd0f-525">メーリング リストの所有者である場合ですか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-525">What if you are the owner of a mailing list?</span></span>

<span data-ttu-id="bbd0f-526">参照してください[2: ディスカッションの一般的なシナリオの一覧が表示](#common-scenario-2---discussion-lists)されます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-526">See the section [Common scenario #2 - Discussion lists](#common-scenario-2---discussion-lists).</span></span> 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a><span data-ttu-id="bbd0f-527">場合、インフラストラクチャ ・ プロバイダー、インターネット サービス プロバイダー (ISP)、電子メール サービス プロバイダー (ESP)、クラウドのサービスをホストしているなどとしています。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-527">What if you are an infrastructure provider such as an Internet Service Provider (ISP), Email Service Provider (ESP), or cloud hosting service?</span></span>

<span data-ttu-id="bbd0f-528">ドメインの電子メールをホストすると、電子メールを送信または電子メールを送信するホストのインフラストラクチャを提供して、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-528">If you host a domain's email, and it sends email, or provide hosting infrastructure that can send email, you should do the following:</span></span>
  
- <span data-ttu-id="bbd0f-529">SPF レコードで発行する詳細なドキュメントを顧客であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-529">Ensure your customers have documentation detailing what to publish in their SPF records</span></span>
    
- <span data-ttu-id="bbd0f-p175">場合でも、お客様は明示的に設定 (既定のドメインを使用して署名) は、送信メールに DKIM 署名を署名を検討してください。偶数倍記号 (+) (1 回とするが、その設定の場合は、お客様のドメインと会社の DKIM 署名を 2 回) DKIM 署名付きの電子メールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p175">Consider signing DKIM-signatures on outbound email even if the customer doesn't explicitly set it up (sign with a default domain). You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>
    
<span data-ttu-id="bbd0f-p176">お使いのプラットフォームから発信されたメールを認証するが、ことマイクロソフトは迷惑メール、電子メール、認証されていないために、少なくとも場合でも、Microsoft に提は保証されません。Outlook.com で電子メールをフィルターする方法を詳細については、 [Outlook.com のポスト マスターのページ](https://postmaster.live.com/pm/postmaster.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p176">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it is not authenticated. For more details around how Outlook.com filters email, see the [Outlook.com Postmaster page](https://postmaster.live.com/pm/postmaster.aspx).</span></span>
  
<span data-ttu-id="bbd0f-534">サービス プロバイダーのベスト ・ プラクティスの詳細については、 [M3AAWG モバイル メッセージングのベスト プラクティスのサービス プロバイダー](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-534">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
  
## <a name="frequently-asked-questions"></a><span data-ttu-id="bbd0f-535">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="bbd0f-535">Frequently Asked Questions</span></span>

### <a name="why-is-microsoft-making-this-change"></a><span data-ttu-id="bbd0f-536">なぜ Microsoft では、この変更しますか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-536">Why is Microsoft making this change?</span></span>

<span data-ttu-id="bbd0f-537">フィッシング詐欺の影響は、次の攻撃、および Microsoft と考えていますので、電子メール認証 15 年以上にわたって利用されてきたの危険性を引き続き認証されていないメールを許可することは、正当な電子メールが失われるリスクよりも高い。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-537">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continue to allow unauthenticated email is higher than the risk of losing legitimate email.</span></span>
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="bbd0f-538">この変更、正当な電子メールをスパムとしてマークしますか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-538">Will this change cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="bbd0f-p177">最初に、スパムとしてマークされているいくつかのメッセージがあります。ただし、時間の経過と共にには、送信者が調整され、スプーフィングされていると間違ったメッセージの量はほとんどの電子メールのパスを取るに足らないものも。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p177">At first, there will be some messages that are marked as spam. However, over time, senders will adjust and then the amount of messages mislabeled as spoofed will be negligible for most email paths.</span></span>
  
<span data-ttu-id="bbd0f-p178">マイクロソフト自体最初に採用してこの機能、お客様の残りの部分を展開する前にいくつかの週。最初の中断が発生しました、中に徐々 に低下しています。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p178">Microsoft itself first adopted this feature several weeks before deploying it to the rest of its customers. While there was disruption at first, it gradually declined.</span></span>
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a><span data-ttu-id="bbd0f-543">マイクロソフトは、Office 365 の Outlook.com と非-高度な脅威保護のお客様にこの機能を表示します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-543">Will Microsoft bring this feature to Outlook.com and non-Advanced Threat Protection customers of Office 365?</span></span>

<span data-ttu-id="bbd0f-p179">マイクロソフトのスプーフィング対策テクノロジは、Office 365 エンタープライズ E5 サブスクリプションまたはサブスクリプションの Office 365 高度な脅威保護 (ATP) のアドオンを購入する必要があるが、組織に最初に配置されました。10 月、2018 年にも Exchange オンライン保護 (EOP) が存在する組織に保護が拡張します。今後、Outlook.com の解放ことがあります。場合は、レポート作成などに適用されていないいくつかの機能がある可能性があり、ユーザー設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p179">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription. As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well. In the future, we may release it for Outlook.com. However, if we do, there may be some capabilities that are not applied such as reporting and custom overrides.</span></span>
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="bbd0f-548">方法ことができますか迷惑メールまたはスパムでないメッセージをマイクロソフトに報告しますか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-548">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="bbd0f-549">[レポート メッセージに Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を使用することがないかどうか、またはがインストールされている、[送信スパム、スパム以外の場合、および分析のためのマイクロソフトのフィッシング詐欺メッセージ](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-549">You can either use the [Report Message Add-in for Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), or if it isn't installed, [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx).</span></span>
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a><span data-ttu-id="bbd0f-550">私はドメイン管理者のすべての送信者は相手を知りません。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-550">I'm a domain administrator who doesn't know who all my senders are!</span></span>

<span data-ttu-id="bbd0f-551">[Office 365 のお客様ではありませんが、ドメインの管理者](#administrators-of-domains-that-are-not-office-365-customers)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-551">Please see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers).</span></span>
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a><span data-ttu-id="bbd0f-552">どう自分の組織では、スプーフィング対策の保護を無効にする場合でも、Office 365 は、プライマリ フィルターでしょうか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-552">What happens if I disable anti-spoofing protection for my organization, even though Office 365 is my primary filter?</span></span>

<span data-ttu-id="bbd0f-p180">行うことこれよりミストのフィッシング詐欺、スパム メッセージを公開するためです。すべてのフィッシング詐欺は、スプーフィングとすべてのスプーフィングが失われます。ただし、リスクはスプーフィング対策を有効にするユーザーよりも大きくなります。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p180">We do not recommend this because you will be exposed to more missed phishing and spam messages. Not all phishing is spoofing, and not all spoofs will be missed. However, your risk will be higher than a customer who enables anti-spoofing.</span></span>
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="bbd0f-556">スプーフィング対策保護を有効にするわけではすべてのフィッシング詐欺から保護されますか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-556">Does enabling anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="bbd0f-p181">残念ながら、いいえなど、その他の手法を使用するのには、フィッシングが適用されますので危険にさらされたアカウント、または無料のサービスのアカウントを設定します。ただし、フィッシング防止対策に優れてこれらに、レイヤーは、Office 365 の保護作業を共同設計するためのフィッシング詐欺の方法は、他の種類を検出し、互いの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p181">Unfortunately, no, because phishers will adapt to use other techniques such as compromised accounts, or setting up accounts of free services. However, anti-phishing protection works much better to detect these other types of phishing methods because Office 365's protection layers are designed work together and build on top of each other.</span></span>
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a><span data-ttu-id="bbd0f-559">他の大規模な電子メールの受信機は、認証されていない電子メールをブロックしますか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-559">Do other large email receivers block unauthenticated email?</span></span>

<span data-ttu-id="bbd0f-p182">ほぼすべての大規模な電子メールの受信機は、従来の SPF、DKIM と DMARC を実装します。いくつかの受信機には、他のチェックには、これらの標準が、一部の移動をブロックするのには Office 365 に認証されていない限りより厳密なメールし、スプーフィングとして扱うことがあります。ただし、業界のほとんどが高まっての電子メールは、この特定の種類についてより厳密な特にフィッシングの問題が発生したためです。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p182">Nearly all large email receivers implement traditional SPF, DKIM, and DMARC. Some receivers have other checks that are more strict than just those standards, but few go as far as Office 365 to block unauthenticated email and treat them as a spoof. However, most of the industry is becoming more and more strict about this particular type of email, particularly because of the problem of phishing.</span></span>
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a><span data-ttu-id="bbd0f-563">必要はありますか、迷惑メールのフィルタ リングの高度なオプションを有効に「SPF ハード失敗」スプーフィング対策を有効にする場合ですか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-563">Do I still need the Advanced Spam Filtering option enabled for "SPF Hard Fail" if I enable anti-spoofing?</span></span>

<span data-ttu-id="bbd0f-p183">残念ですが、SPF ハードが失敗した場合より幅広い条件にだけでなく、スプーフィング対策の機能と見なされるためこのオプションは必要ありません。スプーフィング対策が有効になってがあり、SPF ハード失敗する] オプションが有効になって表示される可能性を誤認識します。スパムやフィッシング、追加の catch は、ほとんどありませんし、代わりにほとんど偽陽性を生成しますが、この機能を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p183">No, this option is no longer required because the anti-spoofing feature not only considers SPF hard fails, but a much wider set of criteria. If you have anti-spoofing enabled and the SPF Hard Fail option enabled, you will probably get more false positives. We recommend disabling this feature as it would provide almost no additional catch for spam or phish, and instead generate mostly false positives.</span></span>
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a><span data-ttu-id="bbd0f-567">送信者書き換えスキーム (SRS) の修正に役立つ電子メールを転送しますか。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-567">Does Sender Rewriting Scheme (SRS) help fix forwarded email?</span></span>

<span data-ttu-id="bbd0f-p184">SRS は、部分的に転送された電子メールの問題を修正します。SMTP メールからの書き換え、SRS によりを次の宛先に転送されたメッセージ パス SPF です。ただし、スプーフィング対策からに基づいているため: アドレス、メールからまたは DKIM 署名ドメイン (またはその他の信号) との組み合わせではスプーフィングされているとマークされてから転送される電子メールを防ぐために十分な。</span><span class="sxs-lookup"><span data-stu-id="bbd0f-p184">SRS only partially fixes the problem of forwarded email. By rewriting the SMTP MAIL FROM, SRS can ensure that the forwarded message passes SPF at the next destination. However, because anti-spoofing is based upon the From: address in combination with either the MAIL FROM or DKIM-signing domain (or other signals), it is not enough to prevent forwarded email from being marked as spoofed.</span></span>
  

