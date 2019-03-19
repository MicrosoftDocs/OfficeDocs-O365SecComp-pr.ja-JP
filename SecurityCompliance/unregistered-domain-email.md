---
title: 未登録のドメインメール
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 登録されていないドメインの電子メールを大量に送信する場合は、メールがブロックされる危険を実行します。 詳細については、この記事をお読みください。
ms.openlocfilehash: 21c403c8072902565f63048782b06c531cdbceb0
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670542"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="d6658-104">未登録のドメインメール: 知っておくべき情報</span><span class="sxs-lookup"><span data-stu-id="d6658-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="d6658-105">Office 365 では、テナントが Exchange Online Protection (EOP) を介して一部のメッセージを中継できます。</span><span class="sxs-lookup"><span data-stu-id="d6658-105">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d6658-106">サポートされている例の1つは、ユーザーが Office 365 メールボックスを持っていて、誰かが電子メールを送信したが、電子メール転送がユーザーの外部メールボックスに戻るように構成されている場合です。</span><span class="sxs-lookup"><span data-stu-id="d6658-106">One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox.</span></span> <span data-ttu-id="d6658-107">これは、学生が個人用の電子メールインターフェイスを利用していても、学校に関連するメールを受信したい教育環境で最も一般的です。</span><span class="sxs-lookup"><span data-stu-id="d6658-107">This is most common in education environments where students want to leverage their personal email interface but still get emails related to school.</span></span> <span data-ttu-id="d6658-108">もう1つの例として、顧客がハイブリッドシナリオで、EOP からメールを送信するオンプレミスサーバーがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6658-108">Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="d6658-109">未登録のドメインに関する問題</span><span class="sxs-lookup"><span data-stu-id="d6658-109">Problems with unregistered domains</span></span>

<span data-ttu-id="d6658-110">この問題は、オンプレミスのサーバーが侵害され、EOP の大量のスパムを中継してしまうことにあります。</span><span class="sxs-lookup"><span data-stu-id="d6658-110">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP.</span></span> <span data-ttu-id="d6658-111">ほとんどの場合、右コネクタはセットアップされていますが、未登録のドメイン (プロビジョニング解除されたドメインとも呼ばれる) からメールを送信しています。</span><span class="sxs-lookup"><span data-stu-id="d6658-111">In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains.</span></span> <span data-ttu-id="d6658-112">Office 365 では、登録されていないドメインからのメールの送信を許可していますが、の送信を計画している各ドメインの管理センターで承認済みドメインを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6658-112">Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="d6658-113">いったん侵害されると、テナントは未登録のドメインの送信メールを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d6658-113">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains.</span></span> <span data-ttu-id="d6658-114">ユーザーは、次の状態を示す配信不能レポート (NDR) を受信します。</span><span class="sxs-lookup"><span data-stu-id="d6658-114">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="d6658-115">550 5.7.750 サービスは利用できません。</span><span class="sxs-lookup"><span data-stu-id="d6658-115">550 5.7.750 Service unavailable.</span></span> <span data-ttu-id="d6658-116">クライアントが未登録のドメインからの送信をブロックされました</span><span class="sxs-lookup"><span data-stu-id="d6658-116">Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="d6658-117">再送信するためにテナントのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="d6658-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="d6658-118">未登録のドメインからの送信がブロックされた場合は、いくつかの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6658-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="d6658-119">Microsoft 365 管理センターですべてのドメインを登録していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d6658-119">Make sure that you register all of your domains in Microsoft 365 admin center.</span></span> <span data-ttu-id="d6658-120">詳細については、[こちら](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6658-120">More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="d6658-121">異常なコネクタを探します。</span><span class="sxs-lookup"><span data-stu-id="d6658-121">Look for unusual connectors.</span></span> <span data-ttu-id="d6658-122">悪意のある俳優は、多くの場合、スパムを送信するために Office 365 テナントに新しい受信コネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="d6658-122">Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam.</span></span> <span data-ttu-id="d6658-123">コネクタの確認の詳細については、[こちら](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6658-123">More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="d6658-124">オンプレミスのサーバーをロックし、侵害されないようにします。</span><span class="sxs-lookup"><span data-stu-id="d6658-124">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="d6658-125">ここでは、特にサードパーティ製のサーバーの場合に、多くの要因が関係しています。</span><span class="sxs-lookup"><span data-stu-id="d6658-125">There are many factors involved here, especially if these are third-party servers.</span></span> <span data-ttu-id="d6658-126">いずれにしても、サーバーから発信されたすべてのメールが正当であることを確認できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6658-126">Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="d6658-127">完了したら、Microsoft サポートに連絡して、登録されていないドメインから送信されないようにテナントのブロック解除を取得するように依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6658-127">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.</span></span>  <span data-ttu-id="d6658-128">エラーコードを提供することは役に立ちますが、環境がセキュリティで保護されており、スパムが再送信されないことを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6658-128">Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again.</span></span> <span data-ttu-id="d6658-129">サポートケースを開く方法については、[こちら](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6658-129">More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="d6658-130">関連情報</span><span class="sxs-lookup"><span data-stu-id="d6658-130">For more information</span></span>

[<span data-ttu-id="d6658-131">Office 365 メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="d6658-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="d6658-132">Office 365 でのメール配信不能レポート</span><span class="sxs-lookup"><span data-stu-id="d6658-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="d6658-133">メールボックスへの電子メールの転送を構成する</span><span class="sxs-lookup"><span data-stu-id="d6658-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="d6658-134">Office 365 を使用してメールを送信するように多機能デバイスまたはアプリケーションをセット アップする方法</span><span class="sxs-lookup"><span data-stu-id="d6658-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="d6658-135">[Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)します。</span><span class="sxs-lookup"><span data-stu-id="d6658-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
