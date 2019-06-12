---
title: Exchange Online でエラーコード 5.7.7 xx のメール配信の問題を修正する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/11/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Exchange Online でエラーコード 5.7.7 xx の電子メールの問題を解決する方法について説明します (テナントがメールの送信をブロックされた場合)。
ms.openlocfilehash: dbdfdeb351125442018e520d72f953e116d8e1a8
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34865512"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a><span data-ttu-id="8edd8-103">Exchange Online でエラーコード 5.7.7 xx のメール配信の問題を修正する</span><span class="sxs-lookup"><span data-stu-id="8edd8-103">Fix email delivery issues for error code 5.7.7xx in Exchange Online</span></span>

<span data-ttu-id="8edd8-104">このトピックでは、配信不能レポート (NDR、バウンスメッセージ、配信状態通知、または DSN とも呼ばれる) に状態コード 550 5.7.7 xx が表示される場合に実行できる操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="8edd8-104">This topic describes what you can do if you see status code 550 5.7.7xx in a non-delivery report (also known as an NDR, bounce message, delivery status notification, or DSN).</span></span> <span data-ttu-id="8edd8-105">この自動通知は、テナントが1つまたは別の方法で電子メールの送信を制限されている場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8edd8-105">You'll see this automated notification when your tenant is restricted from sending email in one way or another.</span></span> <span data-ttu-id="8edd8-106">これらのエラーコードは通常、705または750として表示されます。</span><span class="sxs-lookup"><span data-stu-id="8edd8-106">These error codes will usually come in as 705 or 750.</span></span>

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a><span data-ttu-id="8edd8-107">5.7.705: テナントがしきい値制限を超過しました: 知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="8edd8-107">5.7.705: Tenant has exceeded threshold restriction: What you need to know</span></span>

<span data-ttu-id="8edd8-108">内部の送信者は、テナントが侵害された場合に、メールを送信しようとするたびにこの NDR を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="8edd8-108">Internal senders could see this NDR whenever you try to send mail if your tenant was compromised.</span></span> <span data-ttu-id="8edd8-109">これは通常、テナントからのトラフィックの大部分が疑わしいと検出され、テナントの送信機能が禁止されている場合に occus します。</span><span class="sxs-lookup"><span data-stu-id="8edd8-109">This usually occus when the majority of traffic from your tenant has been detected as suspicious and has resulted in a ban on sending ability for the tenant.</span></span> <span data-ttu-id="8edd8-110">これは、ユーザーが Office 365 から大量のバルクメールを送信した場合にも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-110">This can also occur if your users send an large amount of bulk mail from Office 365.</span></span> <span data-ttu-id="8edd8-111">サービスの説明に記載されているように、正当なバルク商用電子メール (たとえば、顧客向けのニュースレター) を送信する必要がある Exchange Online のお客様は、これらのサービスに特化したサードパーティのプロバイダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-111">As stated in the service description, Exchange Online customers who need to send legitimate bulk commercial email (for example, customer newsletters) should use third-party providers that specialize in these services.</span></span>

<span data-ttu-id="8edd8-112">テナントとしてユーザーが特定の数の疑わしいメールをサービス経由で送信すると、その問題が解決されるまで、すべてのユーザーがメールを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-112">Once your users collectively, as a tenant, send a certain amount of suspicious mail through the service, all users can be prevented from sending any mail until the problem is fixed.</span></span> <span data-ttu-id="8edd8-113">ユーザーは、次の状態を示す配信不能レポート (NDR) を受信します。</span><span class="sxs-lookup"><span data-stu-id="8edd8-113">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="8edd8-114">550 5.7.705 アクセスが拒否されました、テナントはしきい値を超えています</span><span class="sxs-lookup"><span data-stu-id="8edd8-114">550 5.7.705 Access denied, tenant has exceeded threshold</span></span>

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a><span data-ttu-id="8edd8-115">5.7.750: 登録が解除されるドメインの電子メール制限: 理解しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="8edd8-115">5.7.750: Unregistered Domain Email restriction: What you need to know</span></span>

<span data-ttu-id="8edd8-116">Office 365 では、テナントが Exchange Online Protection (EOP) を介して一部のメッセージを中継できます。</span><span class="sxs-lookup"><span data-stu-id="8edd8-116">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="8edd8-117">サポートされている例の1つは、ユーザーが Office 365 メールボックスを持っていて、誰かが電子メールを送信したが、電子メール転送がユーザーの外部メールボックスに戻るように構成されている場合です。</span><span class="sxs-lookup"><span data-stu-id="8edd8-117">One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox.</span></span> <span data-ttu-id="8edd8-118">これは、学生が個人用の電子メールインターフェイスを利用していても、学校に関連するメールを受信したい教育環境で最も一般的です。</span><span class="sxs-lookup"><span data-stu-id="8edd8-118">This is most common in education environments where students want to leverage their personal email interface but still get emails related to school.</span></span> <span data-ttu-id="8edd8-119">もう1つの例として、顧客がハイブリッドシナリオで、EOP からメールを送信するオンプレミスサーバーがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-119">Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

### <a name="problems-with-unregistered-domains"></a><span data-ttu-id="8edd8-120">未登録のドメインに関する問題</span><span class="sxs-lookup"><span data-stu-id="8edd8-120">Problems with unregistered domains</span></span>

<span data-ttu-id="8edd8-121">この問題は、オンプレミスのサーバーが侵害され、EOP の大量のスパムを中継してしまうことにあります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-121">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP.</span></span> <span data-ttu-id="8edd8-122">ほとんどの場合、右コネクタはセットアップされていますが、未登録のドメイン (プロビジョニング解除されたドメインとも呼ばれる) からメールを送信しています。</span><span class="sxs-lookup"><span data-stu-id="8edd8-122">In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains.</span></span> <span data-ttu-id="8edd8-123">Office 365 では、登録されていないドメインからのメールの送信を許可していますが、の送信を計画している各ドメインの管理センターで承認済みドメインを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-123">Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="8edd8-124">いったん侵害されると、テナントは未登録のドメインの送信メールを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-124">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains.</span></span> <span data-ttu-id="8edd8-125">ユーザーは、次の状態を示す配信不能レポート (NDR) を受信します。</span><span class="sxs-lookup"><span data-stu-id="8edd8-125">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="8edd8-126">550 5.7.750 サービスは利用できません。</span><span class="sxs-lookup"><span data-stu-id="8edd8-126">550 5.7.750 Service unavailable.</span></span> <span data-ttu-id="8edd8-127">クライアントが未登録のドメインからの送信をブロックしました</span><span class="sxs-lookup"><span data-stu-id="8edd8-127">Client blocked from sending from unregistered domains</span></span>

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="8edd8-128">再送信のためにテナントのブロックを解除する方法</span><span class="sxs-lookup"><span data-stu-id="8edd8-128">How to unblocking tenant in order to send again</span></span>

<span data-ttu-id="8edd8-129">テナントが電子メールの送信をブロックされる場合は、次のようないくつかの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-129">There are several things you need to do if your tenant get blocked for sending email:</span></span>

1. <span data-ttu-id="8edd8-130">Microsoft 365 管理センターですべてのドメインを登録していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8edd8-130">Make sure that you register all of your domains in Microsoft 365 admin center.</span></span> <span data-ttu-id="8edd8-131">詳細については、[こちら](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8edd8-131">More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="8edd8-132">異常なコネクタを探します。</span><span class="sxs-lookup"><span data-stu-id="8edd8-132">Look for unusual connectors.</span></span> <span data-ttu-id="8edd8-133">悪意のある俳優は、多くの場合、スパムを送信するために Office 365 テナントに新しい受信コネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="8edd8-133">Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam.</span></span> <span data-ttu-id="8edd8-134">コネクタの確認の詳細については、[こちら](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8edd8-134">More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="8edd8-135">オンプレミスのサーバーをロックし、侵害されないようにします。</span><span class="sxs-lookup"><span data-stu-id="8edd8-135">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="8edd8-136">ここでは、特にサードパーティ製のサーバーの場合に、多くの要因が関係しています。</span><span class="sxs-lookup"><span data-stu-id="8edd8-136">There are many factors involved here, especially if these are third-party servers.</span></span> <span data-ttu-id="8edd8-137">いずれにしても、サーバーから発信されたすべてのメールが正当であることを確認できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-137">Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="8edd8-138">完了したら、Microsoft サポートに連絡して、登録されていないドメインから送信されないようにテナントのブロック解除を取得するように依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-138">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.</span></span>  <span data-ttu-id="8edd8-139">エラーコードを提供することは役に立ちますが、環境がセキュリティで保護されており、スパムが再送信されないことを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8edd8-139">Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again.</span></span> <span data-ttu-id="8edd8-140">サポートケースを開く方法については、[こちら](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8edd8-140">More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="8edd8-141">関連情報</span><span class="sxs-lookup"><span data-stu-id="8edd8-141">For more information</span></span>

[<span data-ttu-id="8edd8-142">Office 365 メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="8edd8-142">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="8edd8-143">Office 365 でのメール配信不能レポート</span><span class="sxs-lookup"><span data-stu-id="8edd8-143">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="8edd8-144">メールボックスへの電子メールの転送を構成する</span><span class="sxs-lookup"><span data-stu-id="8edd8-144">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="8edd8-145">Office 365 を使用してメールを送信するように多機能デバイスまたはアプリケーションをセット アップする方法</span><span class="sxs-lookup"><span data-stu-id="8edd8-145">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="8edd8-146">[Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)します。</span><span class="sxs-lookup"><span data-stu-id="8edd8-146">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
