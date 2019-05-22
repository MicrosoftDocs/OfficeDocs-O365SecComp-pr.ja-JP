---
title: 未確認の送信者
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。
ms.openlocfilehash: 92458a93a4da3e449061e4d2a4ba312d635c42cc
ms.sourcegitcommit: 7f00f765e8fa674ce1c8c66f5b89b6bea45e13ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2019
ms.locfileid: "34341625"
---
# <a name="unverified-sender"></a><span data-ttu-id="67b11-103">未確認の送信者</span><span class="sxs-lookup"><span data-stu-id="67b11-103">Unverified Sender</span></span>

<span data-ttu-id="67b11-104">フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="67b11-104">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67b11-105">メッセージがフィッシング詐欺としてマークされている場合、Outlook.com および web 上の Outlook では、ページの上部に警告が表示されますが、メッセージ内のすべてのリンクを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="67b11-105">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="67b11-106">受信トレイ内の疑わしいメッセージを特定するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="67b11-106">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="67b11-107">Web 上の Outlook.com および Outlook on the メッセージの送信者が識別できない場合、または送信者アドレスに表示されているものとは異なる場合のインジケーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="67b11-107">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="67b11-108">未確認の送信者の処理を受信するメッセージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="67b11-108">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="67b11-109">Office 365 をご利用のお客様の場合は、セキュリティ & コンプライアンスセンターを使用してこの機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="67b11-109">If you are an Office 365 customer you can manage this feature through the Security & Compliance Center.</span></span> 

- <span data-ttu-id="67b11-110">Office 365 Security & コンプライアンスセンターでは、テナント管理者は、フィッシングポリシーの下にあるスプーフィング対策保護を使用して、この機能をオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="67b11-110">In the Office 365 Security & Compliance Center, tenant admins can turn the feature on, or off, through the Anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="67b11-111">また、' Get-antiphishpolicy ' コマンドレットを使用して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="67b11-111">Additionally, it can be managed through the ‘Set-AntiPhishPolicy’ cmdlet.</span></span> <span data-ttu-id="67b11-112">詳細については、「Office 365 のフィッシング対策保護」および「Get-antiphishpolicy」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b11-112">For more details, see Anti-phishing protection in Office 365 and Set-AntiPhishPolicy.</span></span>

    ![グラフィックインターフェイスで認証されていない送信者を編集する。](media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="67b11-114">管理者が誤検知を識別し、送信者が未確認の送信者の処理を受信しないようにする場合は、次のいずれかの操作を実行して、スプーフィングインテリジェンススプーフィング許可リストに送信者を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="67b11-114">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment they can take one of the following actions to add the sender to the Spoof Intelligence spoof allow list:</span></span>
        
    - <span data-ttu-id="67b11-115">スプーフィングインテリジェンスの洞察を通じてドメインペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="67b11-115">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="67b11-116">詳細については、「チュートリアル: スプーフィングインテリジェンスの洞察」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b11-116">For more details, see Walkthrough: spoof intelligence insight</span></span>
                
    - <span data-ttu-id="67b11-117">Get-phishfilterpolicy コマンドレットを使用して、ドメインペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="67b11-117">Add the domain pair through the PhishFilterPolicy cmdlet.</span></span> <span data-ttu-id="67b11-118">詳細については、「Get-phishfilterpolicy」および「Office のスプーフィング対策保護」を参照してください365</span><span class="sxs-lookup"><span data-stu-id="67b11-118">For more details, see Set-PhishFilterPolicy and Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="67b11-119">また、電子メールトランスポートルール (Etr)、安全なドメインリスト (スパム対策ポリシー)、安全な送信者リスト、またはユーザーがこのユーザーを自分のドメイン内の "安全な送信者" として設定している場合にも、未検証の送信者の処理は適用されません。ボックス.</span><span class="sxs-lookup"><span data-stu-id="67b11-119">Additionally, we do not apply the unverified sender treatment if it was delivered to the inbox via an admin allow list, including Email Transport Rules (ETRs), Safe Domain List (Anti-Spam Policy), Safe Sender List or a user has set this user as a “Safe Sender” in their inbox.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="67b11-120">送信者の画像に '? ' が表示される</span><span class="sxs-lookup"><span data-stu-id="67b11-120">You see a '?' in the sender image</span></span>

<span data-ttu-id="67b11-121">Outlook.com と web 上の Outlook が電子メール認証手法を使用して送信者の身元を確認できない場合は、送信者の写真に '? ' が表示されます。</span><span class="sxs-lookup"><span data-stu-id="67b11-121">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span> 

![メッセージが検証に合格しませんでした](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="67b11-123">認証に失敗したすべてのメッセージが悪意のあるものであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="67b11-123">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="67b11-124">ただし、送信者を認識しない場合は、認証されないメッセージの操作について注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67b11-124">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="67b11-125">または、通常は送信者の画像に '? ' が含まれていない送信者を認識したが、突然表示を開始した場合は、送信者がスプーフィングされているという署名になることがあります。</span><span class="sxs-lookup"><span data-stu-id="67b11-125">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="67b11-126">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="67b11-126">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="67b11-127">Outlook.com と web 上の Outlook で、'? ' および ' via ' プロパティを追加するために使用する条件とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="67b11-127">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="67b11-128">送信者イメージの '? ' の場合: Outlook.com では、メッセージが SPF または DKIM 認証のいずれかを通過する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67b11-128">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="67b11-129">詳細については、「 [Set UP SPF In office 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 」を参照して、スプーフィングを防止し、 [Dkim を使用して office 365 のカスタムドメインから送信される送信電子メールを検証](use-dkim-to-validate-outbound-email.md)します。</span><span class="sxs-lookup"><span data-stu-id="67b11-129">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="67b11-130">Via タグの場合: From アドレスのドメインが DKIM シグネチャまたは SMTP メールのドメインと異なる場合、Outlook.com は、この2つのフィールドのいずれかにドメインを表示します (DKIM シグネチャを優先します)。</span><span class="sxs-lookup"><span data-stu-id="67b11-130">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the-"></a><span data-ttu-id="67b11-131">'? ' を削除する方法</span><span class="sxs-lookup"><span data-stu-id="67b11-131">How do I remove the '?'</span></span>

<span data-ttu-id="67b11-132">送信者の画像の '? ' の場合は、送信者として、SPF または DKIM のいずれかを使用してメッセージを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67b11-132">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="67b11-133">Via タグ: 送信者としての場合は、DKIM 署名のドメインまたは SMTP メールが、From アドレスのドメインと同じかサブドメインのものであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67b11-133">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="67b11-134">Outlook.com と web 上の Outlook は、認証を通過しないすべてのメッセージに対してこのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="67b11-134">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="67b11-135">必ずしもそうではありません。</span><span class="sxs-lookup"><span data-stu-id="67b11-135">Not necessarily.</span></span> <span data-ttu-id="67b11-136">Outlook.com および web 上の Outlook は、メッセージ内に送信者を認証するためのその他のプロパティがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="67b11-136">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="67b11-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="67b11-137">Related topics</span></span>

[<span data-ttu-id="67b11-138">Outlook.com メールアカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="67b11-138">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="67b11-139">Outlook.com での迷惑行為、フィッシング、またはスプーフィングに対処する</span><span class="sxs-lookup"><span data-stu-id="67b11-139">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="67b11-140">Outlook on the web で迷惑メールおよびスパムをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="67b11-140">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
