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
description: 登録されていないドメインの電子メールを大量に送信する場合は、メールがブロックされる危険を実行します。詳細については、この記事をお読みください。
ms.openlocfilehash: 8120bd147da2a7aab41ae14c444d2fe57242199e
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276227"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="0dc3a-104">未登録のドメインメール: 知っておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0dc3a-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="0dc3a-p102">Office 365 では、テナントが Exchange Online Protection (EOP) を介して一部のメッセージを中継できます。サポートされている例の1つは、ユーザーが Office 365 メールボックスを持っていて、誰かが電子メールを送信したが、電子メール転送がユーザーの外部メールボックスに戻るように構成されている場合です。これは、学生が個人用の電子メールインターフェイスを利用していても、学校に関連するメールを受信したい教育環境で最も一般的です。もう1つの例として、顧客がハイブリッドシナリオで、EOP からメールを送信するオンプレミスサーバーがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0dc3a-p102">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="0dc3a-109">未登録のドメインに関する問題</span><span class="sxs-lookup"><span data-stu-id="0dc3a-109">Problems with unregistered domains</span></span>

<span data-ttu-id="0dc3a-p103">この問題は、オンプレミスのサーバーが侵害され、EOP の大量のスパムを中継してしまうことにあります。ほとんどの場合、右コネクタはセットアップされていますが、未登録のドメイン (プロビジョニング解除されたドメインとも呼ばれる) からメールを送信しています。Office 365 では、登録されていないドメインからのメールの送信を許可していますが、の送信を計画している各ドメインの管理センターで承認済みドメインを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dc3a-p103">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="0dc3a-p104">いったん侵害されると、テナントは未登録のドメインの送信メールを送信できなくなります。ユーザーは、次の状態を示す配信不能レポート (NDR) を受信します。</span><span class="sxs-lookup"><span data-stu-id="0dc3a-p104">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="0dc3a-p105">550 5.7.750 サービスは利用できません。クライアントが未登録のドメインからの送信をブロックされました</span><span class="sxs-lookup"><span data-stu-id="0dc3a-p105">550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="0dc3a-117">再送信するためにテナントのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="0dc3a-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="0dc3a-118">未登録のドメインからの送信がブロックされた場合は、いくつかの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dc3a-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="0dc3a-p106">Office 365 管理センターですべてのドメインを登録していることを確認してください。詳細については、[こちら](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dc3a-p106">Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="0dc3a-p107">異常なコネクタを探します。悪意のある俳優は、多くの場合、スパムを送信するために Office 365 テナントに新しい受信コネクタを作成します。コネクタの確認の詳細については、[こちら](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dc3a-p107">Look for unusual connectors. Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam. More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="0dc3a-124">オンプレミスのサーバーをロックし、侵害されないようにします。</span><span class="sxs-lookup"><span data-stu-id="0dc3a-124">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="0dc3a-p108">ここでは、特にサードパーティ製のサーバーの場合に、多くの要因が関係しています。いずれにしても、サーバーから発信されたすべてのメールが正当であることを確認できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dc3a-p108">There are many factors involved here, especially if these are third-party servers. Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="0dc3a-p109">完了したら、Microsoft サポートに連絡して、登録されていないドメインから送信されないようにテナントのブロック解除を取得するように依頼する必要があります。 エラーコードを提供することは役に立ちますが、環境がセキュリティで保護されており、スパムが再送信されないことを証明する必要があります。サポートケースを開く方法については、[こちら](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dc3a-p109">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="0dc3a-130">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0dc3a-130">For more information</span></span>

[<span data-ttu-id="0dc3a-131">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="0dc3a-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="0dc3a-132">Office 365 でのメール配信不能レポート</span><span class="sxs-lookup"><span data-stu-id="0dc3a-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="0dc3a-133">メールボックスへの電子メールの転送を構成する</span><span class="sxs-lookup"><span data-stu-id="0dc3a-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="0dc3a-134">Office 365 を使用してメールを送信するように多機能デバイスまたはアプリケーションをセット アップする方法</span><span class="sxs-lookup"><span data-stu-id="0dc3a-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="0dc3a-135">[Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)します。</span><span class="sxs-lookup"><span data-stu-id="0dc3a-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
