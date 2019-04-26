---
title: Outlook.com および web 上の Outlook で不審なメッセージを特定する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。
ms.openlocfilehash: edba30bb2ac0f9dc6ebc12db957a518de0c1b543
ms.sourcegitcommit: 9907bebc5f225032f681c4952de0b0be2df278ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33345912"
---
# <a name="identify-suspicious-messages-in-outlookcom-and-outlook-on-the-web"></a><span data-ttu-id="fdf64-103">Outlook.com および web 上の Outlook で不審なメッセージを特定する</span><span class="sxs-lookup"><span data-stu-id="fdf64-103">Identify suspicious messages in Outlook.com and Outlook on the web</span></span>

<span data-ttu-id="fdf64-104">フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="fdf64-104">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fdf64-105">メッセージがフィッシング詐欺としてマークされている場合、Outlook.com および web 上の Outlook では、ページの上部に警告が表示されますが、メッセージ内のすべてのリンクを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="fdf64-105">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="fdf64-106">受信トレイ内の疑わしいメッセージを特定するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="fdf64-106">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="fdf64-107">web 上の Outlook.com および Outlook on the メッセージの送信者が識別できない場合、または送信者アドレスに表示されているものとは異なる場合のインジケーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="fdf64-107">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="fdf64-108">送信者の画像に '? ' が表示される</span><span class="sxs-lookup"><span data-stu-id="fdf64-108">You see a '?' in the sender image</span></span>

<span data-ttu-id="fdf64-109">Outlook.com と web 上の Outlook が電子メール認証手法を使用して送信者の身元を確認できない場合は、送信者の写真に '? ' が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdf64-109">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span>

![メッセージが検証に合格しませんでした](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="fdf64-111">認証に失敗したすべてのメッセージが悪意のあるものであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="fdf64-111">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="fdf64-112">ただし、送信者を認識しない場合は、認証されないメッセージの操作について注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdf64-112">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="fdf64-113">または、通常は送信者の画像に '? ' が含まれていない送信者を認識したが、突然表示を開始した場合は、送信者がスプーフィングされているという署名になることがあります。</span><span class="sxs-lookup"><span data-stu-id="fdf64-113">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a><span data-ttu-id="fdf64-114">送信者のアドレスが差出人アドレスに表示されているものと異なる</span><span class="sxs-lookup"><span data-stu-id="fdf64-114">The sender's address is different than what appears in the From address</span></span>

<span data-ttu-id="fdf64-115">多くの場合、メッセージに表示される電子メールアドレスは、差出人アドレスに表示されているものとは異なります。</span><span class="sxs-lookup"><span data-stu-id="fdf64-115">Frequently, the email address you see in a message is different than what you see in the From address.</span></span> <span data-ttu-id="fdf64-116">場合によっては、送信者が実際のユーザーではない人物であることを phishers してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fdf64-116">Sometimes phishers try to trick you into thinking that the sender is someone other than who they really are.</span></span>

<span data-ttu-id="fdf64-117">Outlook.com と、web 上の Outlook で、送信者の実際のアドレスと差出人のアドレスのアドレスが異なることを検出すると、[経由] タグを使用して実際の送信者が表示されます。これには下線が付きます。</span><span class="sxs-lookup"><span data-stu-id="fdf64-117">When Outlook.com and Outlook on the web detect a difference between the sender's actual address and the address on the From address, they show the actual sender using the via tag, which will be underlined.</span></span>

![未確認の送信者代替テキスト](media/unverified-sender-feature1.png)

<span data-ttu-id="fdf64-119">この例では、送信側`suspicious.com`ドメインは認証されますが`unknown@contoso.com` 、送信者は差出人アドレスに入力します。</span><span class="sxs-lookup"><span data-stu-id="fdf64-119">In this example, the sending domain `suspicious.com` is authenticated, but the sender put `unknown@contoso.com` in the From address.</span></span>

<span data-ttu-id="fdf64-120">via タグを持つすべてのメッセージが疑わしいとは限りません。</span><span class="sxs-lookup"><span data-stu-id="fdf64-120">Not every message with a via tag is suspicious.</span></span> <span data-ttu-id="fdf64-121">ただし、via タグが付いているメッセージを認識しない場合は、それとの対話に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdf64-121">However, if you don't recognize a message with a via tag, you should be cautious about interacting with it.</span></span>

<span data-ttu-id="fdf64-122">Outlook.com と新しい Outlook on the web では、メッセージを開く必要なしに、メッセージ一覧の送信者の名前またはアドレスの上にカーソルを置くと、その電子メールアドレスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fdf64-122">In Outlook.com and the new Outlook on the web, you can hover your cursor over a sender's name or address in the message list to see their email address, without needing to open the message.</span></span>

![OneDrive の使用を開始する](media/get-started-with-onedrive-message.png)

<span data-ttu-id="fdf64-124">新しい Outlook on the web を使用しているかどうかを確認するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="fdf64-124">How do you know if you're using the new Outlook on the web?</span></span> <span data-ttu-id="fdf64-125">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdf64-125">See the following examples:</span></span>

![Outlook vs Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="fdf64-127">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="fdf64-127">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="fdf64-128">Outlook.com と web 上の Outlook で、'? ' および ' via ' プロパティを追加するために使用する条件とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="fdf64-128">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="fdf64-129">送信者イメージの '? ' の場合: Outlook.com では、メッセージが SPF または dkim 認証のいずれかを通過する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdf64-129">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="fdf64-130">詳細については、「 [Set up SPF in office 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 」を参照して、スプーフィングを防止し、 [dkim を使用して office 365 のカスタムドメインから送信される送信電子メールを検証](use-dkim-to-validate-outbound-email.md)します。</span><span class="sxs-lookup"><span data-stu-id="fdf64-130">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="fdf64-131">via タグの場合: from アドレスのドメインが dkim シグネチャまたは SMTP メールのドメインと異なる場合、Outlook.com は、この2つのフィールドのいずれかにドメインを表示します (dkim シグネチャを優先します)。</span><span class="sxs-lookup"><span data-stu-id="fdf64-131">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a><span data-ttu-id="fdf64-132">これらのプロパティを IP で使用できる、Exchange トランスポートルールの許可、または安全な送信者に上書きすることはできますか。</span><span class="sxs-lookup"><span data-stu-id="fdf64-132">Can I override these properties with IP Allows, Exchange Transport Rule Allows, or safe senders?</span></span>

<span data-ttu-id="fdf64-133">これらのプロパティを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fdf64-133">You can't override these properties.</span></span>

### <a name="how-do-i-remove-these-properties"></a><span data-ttu-id="fdf64-134">これらのプロパティを削除するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="fdf64-134">How do I remove these properties?</span></span>

<span data-ttu-id="fdf64-135">送信者の画像の '? ' の場合は、送信者として、SPF または dkim のいずれかを使用してメッセージを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdf64-135">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="fdf64-136">via タグ: 送信者としての場合は、dkim 署名のドメインまたは SMTP メールが、from アドレスのドメインと同じかサブドメインのものであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdf64-136">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="fdf64-137">Outlook.com と web 上の Outlook は、認証を通過しないすべてのメッセージに対してこのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdf64-137">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="fdf64-138">必ずしもそうではありません。</span><span class="sxs-lookup"><span data-stu-id="fdf64-138">Not necessarily.</span></span> <span data-ttu-id="fdf64-139">Outlook.com および web 上の Outlook は、メッセージ内に送信者を認証するためのその他のプロパティがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="fdf64-139">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fdf64-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fdf64-140">Related topics</span></span>

[<span data-ttu-id="fdf64-141">Outlook.com メールアカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="fdf64-141">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="fdf64-142">Outlook.com での迷惑行為、フィッシング、またはスプーフィングに対処する</span><span class="sxs-lookup"><span data-stu-id="fdf64-142">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="fdf64-143">Outlook on the web で迷惑メールおよびスパムをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="fdf64-143">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
