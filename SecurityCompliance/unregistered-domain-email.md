---
title: 登録されていないドメインの電子メール
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: 大量のドメインが登録されていない電子メールを送信する場合は、ブロックを取得する電子メールのリスクを実行します。詳細については、この資料を参照してください。
ms.openlocfilehash: f632c5f7ab94a200a364828408b13c0026335869
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769787"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="d5a09-104">登録されていないドメインのメール: に必要なものを知る</span><span class="sxs-lookup"><span data-stu-id="d5a09-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="d5a09-p102">Office 365 は、Exchange オンライン保護 (EOP) では、いくつかのメッセージを中継するテナントのことができます。サポートされている 1 つの例としては、ユーザーが Office 365 メールボックスを持って、電子メールを送信して外部の人がされるようにバックアップを外部メールボックスのユーザーの電子メールの転送が構成されているときになります。これは、受講者が自分の個人的な電子メールのインタ フェースを活用して、、まだ学校に関連する電子メールを取得する必要な教育環境で最も一般的です。別の例がお客様のハイブリッド シナリオでは、EOP から電子メールを送信するサーバーを設置します。</span><span class="sxs-lookup"><span data-stu-id="d5a09-p102">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="d5a09-109">登録されていないドメインの問題</span><span class="sxs-lookup"><span data-stu-id="d5a09-109">Problems with unregistered domains</span></span>

<span data-ttu-id="d5a09-p103">オンプレミスのサーバーが侵害され、大量の EOP をスパムの中継を終了するときに問題があります。ほとんどすべての場合、右側のコネクタに設定されてですが、登録されていないとも呼ばれる準備が解除された、ドメインから送信される電子メール。Office 365 は適度な未登録のドメインからのメールを許可するを送信するように計画する各ドメインの管理センターで、承認済みドメインを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5a09-p103">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="d5a09-p104">危険にさらされた後のテナントされなくなります登録されていないドメインからの送信メールを送信します。ユーザーは配信不能レポート (NDR) を示すが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5a09-p104">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="d5a09-p105">550 5.7.750 サービスを利用できません。クライアントが登録されていないドメインからの送信は禁止</span><span class="sxs-lookup"><span data-stu-id="d5a09-p105">550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="d5a09-117">再送信するためにブロック解除のテナント</span><span class="sxs-lookup"><span data-stu-id="d5a09-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="d5a09-118">登録されていないドメインから送信するためにブロックされる場合に実行する必要があるいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="d5a09-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="d5a09-p106">すべてのドメインを Office 365 の管理センターで登録することを確認します。詳細についてを参照して[ここで](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="d5a09-p106">Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="d5a09-p107">特殊なコネクタを探します。出演者の悪意のある多くの場合迷惑メールを送信するのには、Office 365 のテナントで新しい受信コネクタが作成されます。詳細については、コネクタを確認する方法を参照して[ここで](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="d5a09-p107">Look for unusual connectors. Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam. More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="d5a09-124">オンプレミスのサーバーをロックダウンし、侵害がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5a09-124">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="d5a09-p108">多くの要因関係するここでは、これらは、サード パーティのサーバーの場合は特に。関係なく、する必要があるには、サーバーをそのまますべてのメールが正当であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5a09-p108">There are many factors involved here, especially if these are third-party servers. Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="d5a09-p109">終わったら、マイクロソフト サポートに連絡し、登録されていないドメインから再送信をブロック解除、テナントを取得するよう要求する必要があります。 エラー コードを提供することをお勧め、ですが、お客様の環境がセキュリティで保護されていると、迷惑メールは再送信されないことを証明する必要があります。サポート案件を開く方法の詳細についてを参照して[ここで](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。</span><span class="sxs-lookup"><span data-stu-id="d5a09-p109">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="d5a09-130">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d5a09-130">For more information</span></span>

[<span data-ttu-id="d5a09-131">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="d5a09-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="d5a09-132">Office 365 でのメール配信不能レポート</span><span class="sxs-lookup"><span data-stu-id="d5a09-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="d5a09-133">メールボックスへの電子メールの転送を構成する</span><span class="sxs-lookup"><span data-stu-id="d5a09-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="d5a09-134">Office 365 を使用してメールを送信するように多機能デバイスまたはアプリケーションをセット アップする方法</span><span class="sxs-lookup"><span data-stu-id="d5a09-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="d5a09-135">[管理許可ドメイン Exchange オンライン](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="d5a09-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
