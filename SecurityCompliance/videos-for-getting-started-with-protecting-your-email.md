---
title: 電子メール保護の入門ビデオ
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: laurawi
ms.date: 2/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: この入門ドキュメントは、Exchange Online Protection (EOP) といくつかの重要な用語を理解するのに役立ちます。 これは、exchange Online のクラウドホスト型メールボックスを保護している、または exchange Server 2016 などの社内メールボックスを保護している EOP スタンドアロンのお客様に対して適用されます。
ms.openlocfilehash: f9c966fd2e4ca4788b6400aba337019c49f56b84
ms.sourcegitcommit: 9403f8f038a9940f1b6299fc7d5c560bb7fbcc41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2019
ms.locfileid: "30310007"
---
## <a name="what-is-exchange-online-protection-eop"></a><span data-ttu-id="8b6f4-104">Exchange Online Protection (EOP) とは</span><span class="sxs-lookup"><span data-stu-id="8b6f4-104">What is Exchange Online Protection (EOP)</span></span>

<span data-ttu-id="8b6f4-105">Exchange Online Protection (EOP) は、クラウドベースの電子メールフィルター処理サービスであり、スパムやマルウェアから組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-105">Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="8b6f4-106">Office 365 にメールボックスがある場合、それらはサービスの一部であるため、EOP によって自動的に保護されます。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-106">If you have mailboxes in Office 365, they are automatically protected by EOP since it is part of the service.</span></span> <span data-ttu-id="8b6f4-107">これには、Office 365 とオンプレミスの両方にメールボックスがあり、ハイブリッドシナリオとしてよく知られている組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-107">This includes organizations that have mailboxes in both Office 365 and on-premise, which is commonly known as a hybrid scenario.</span></span> <span data-ttu-id="8b6f4-108">EOP スタンドアロンは、クラウドにメールボックスを持っていないが、社内メールボックスを保護する必要があるお客様も利用できます。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-108">EOP standalone is also available for customers who do not have mailboxes in the cloud but want to protect their on-premise mailboxes.</span></span> 

<span data-ttu-id="8b6f4-109">EOP は迷惑メールのフィルターを試行し、ユーザーが表示したくないコンテンツを受信トレイがクリアしないようにします。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-109">EOP attempts to filter out junk, keeping your Inbox clear of content that users don't want to see.</span></span> <span data-ttu-id="8b6f4-110">通常、迷惑メールは [迷惑メール] フォルダーに配信されます。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-110">Normally, junk mail is delivered to the Junk Email folder.</span></span> <span data-ttu-id="8b6f4-111">迷惑メールフォルダーが自分で必要なことを確認するための簡単な方法であることを確認するために、フィルター処理で必要なことを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-111">Some users like to check to make sure the filtering is doing what they want so the Junk Email folder is an easy way for users to check on their own.</span></span>  

> [!TIP]
> <span data-ttu-id="8b6f4-112">迷惑メールやその他の不正な電子メールが迷惑メールフォルダーに自動的に送られる場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-112">It is a good thing when junk or otherwise bad email goes into the Junk Email folder automatically.</span></span> <span data-ttu-id="8b6f4-113">サービスは、既定またはカスタムの管理者設定の状態に基づいて必要な処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-113">The service will do what is necessary based on what the default or the custom admin settings state.</span></span> <span data-ttu-id="8b6f4-114">言い換えると、ユーザーは迷惑メールフォルダーに多数のスパムメールを表示することを心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-114">In other words, users should not worry about seeing a lot of spam mail in the Junk Email folder.</span></span> <span data-ttu-id="8b6f4-115">管理者がすべての迷惑メールを視界から除外することを希望している場合は、検疫を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-115">If admins prefer to move all junk out of sight, then the Quarantine should be configured.</span></span> <span data-ttu-id="8b6f4-116">詳細については、「 [Office で電子メールメッセージを検疫する 365](quarantine-email-messages.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-116">For more details, see the [Quarantine email messages in Office 365](quarantine-email-messages.md) article.</span></span>

## <a name="important-terms"></a><span data-ttu-id="8b6f4-117">重要な用語</span><span class="sxs-lookup"><span data-stu-id="8b6f4-117">Important terms</span></span>

<span data-ttu-id="8b6f4-118">**受信:** Office 365 に入ってくるメッセージ</span><span class="sxs-lookup"><span data-stu-id="8b6f4-118">**Inbound:** Messages that are coming into Office 365.</span></span>

<span data-ttu-id="8b6f4-119">**送信:** Office 365 から出てくるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-119">**Outbound:** Messages that are going out of Office 365.</span></span>

<span data-ttu-id="8b6f4-120">**内部:** 組織内のユーザーから組織内のユーザーに送信されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-120">**Internal:** Messages that are from someone inside the organization to someone inside the organization.</span></span> <span data-ttu-id="8b6f4-121">これには、ハイブリッドシナリオと1つのメールボックスがオンプレミスにあり、他のメールボックスがクラウド内に存在する可能性があるユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-121">This includes customers who are in hybrid scenarios and one mailbox could be on-premise and the other mailbox is in the cloud.</span></span>

<span data-ttu-id="8b6f4-122">**False 負 (FN):** スパムやその他の迷惑メールが、受信トレイに正しく送信されません。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-122">**False Negative (FN):** Spam and other junk that incorrectly gets sent into the inbox.</span></span>

<span data-ttu-id="8b6f4-123">**False 陽性 (FP):** 誤ってスパムとしてマークされ、迷惑メールフォルダーまたは検疫に入れられる正当なメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-123">**False Positive (FP):** Legitimate messages that incorrectly get marked as spam and put into the Junk Email folder or Quarantine.</span></span>

<span data-ttu-id="8b6f4-124">**スパム (迷惑メールとも呼ばれます):** これには、商業広告、チェーンレター、政治的メールなどの形式があります。これは、ユーザーが電子メールを送信しようとしたり、不正なコミットを試行したりしているスパムからのサインアップを行わないメールです。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-124">**Spam, also known as unsolicited e-mail:** This comes in the form of commercial advertising, chain letters, political mailings, etc. This is email that users do not sign up for and from spammers who are trying to solicit products or attempting to commit fraud.</span></span>

<span data-ttu-id="8b6f4-125">**フィッシング:** フィッシングとは、個人情報の盗難や不正行為を防止するために、個人情報を提供することを目的とする特別な種類のスパムです。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-125">**Phish:** Phishing is a special type of spam that is intended to trick you into giving up personal information for the purpose of committing identity theft or fraud.</span></span> <span data-ttu-id="8b6f4-126">通常、この種類のメッセージには、悪意のあるリンクや添付ファイルが含まれますが、常には含まれません。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-126">This type of message usually contains a malicious link or attachment, but not always.</span></span>

<span data-ttu-id="8b6f4-127">**スプーフィング:** スプーフィングとは、スパム送信者が from ヘッダーを偽造して、メッセージが実際のソース以外の人物または別の場所から発信されたように見えるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-127">**Spoof:** Spoofing is when spammers forge the FROM header so that messages appear to have originated from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="8b6f4-128">これはスパムでもかまいませんが、フィッシングユーザーに最もよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-128">This can be spam but most commonly used to phish users.</span></span>

<span data-ttu-id="8b6f4-129">**偽装:** この種類のスパムは、送信者アドレスを偽造する方法でもありますが、実際のソースのようになるように名前またはドメインの一部を変更することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-129">**Impersonation:** This type of spam is also a way to forge the sender address, but it is done by modifying part of the name or domain so that it looks like the real source.</span></span> <span data-ttu-id="8b6f4-130">たとえば、請求書の "l" が実際には11で、Microsoft の "o" が0という数字に置き換えられていると、Bi11@micr0s0ft.com のようになります。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-130">For example, Bi11@micr0s0ft.com, where the "l" in Bill was actually the number eleven and the "o" in Microsoft was replaced with the number zero.</span></span>

<span data-ttu-id="8b6f4-131">**Bulk:** 通常、バルクメールはユーザーによって要請されますが、企業が他の企業に情報を販売する際に間接的に発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-131">**Bulk:** Bulk mail is usually solicited by users, although sometimes indirectly when companies sell information to other companies.</span></span> <span data-ttu-id="8b6f4-132">通常、ユーザーは大量のメール (newletters) に意図的にサインアップしていますが、後で忘れることはなく、スパムであると考えられます。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-132">It is common that users intentionally sign up for bulk mail (i.e. newletters) but forget later on and think it is spam.</span></span> <span data-ttu-id="8b6f4-133">バルクメールが送信されると、ユーザーがサインアップするよりも多くの場合、大量メールがスパムになる。</span><span class="sxs-lookup"><span data-stu-id="8b6f4-133">Bulk mail becomes spam when bulk mailers send more than users sign up and complaint levels get too high.</span></span>
