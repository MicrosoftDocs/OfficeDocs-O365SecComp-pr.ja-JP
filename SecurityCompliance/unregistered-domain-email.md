---
title: 登録されていないドメインの電子メール
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: 大量のドメインが登録されていない電子メールを送信する場合は、ブロックを取得する電子メールのリスクを実行します。詳細については、この資料を参照してください。
ms.openlocfilehash: f2b60f492197bf0dadb702a1c3f184c2d7e56bf1
ms.sourcegitcommit: 7b85c22fc85ec19e4b44a07e91bfa9ade768185a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998601"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="8573e-104">登録されていないドメインのメール: に必要なものを知る</span><span class="sxs-lookup"><span data-stu-id="8573e-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="8573e-p102">Office 365 は、Exchange オンライン保護 (EOP) では、いくつかのメッセージを中継するテナントのことができます。サポートされている 1 つの例としては、ユーザーが Office 365 メールボックスを持って、電子メールを送信して外部の人がされるようにバックアップを外部メールボックスのユーザーの電子メールの転送が構成されているときになります。これは、受講者が自分の個人的な電子メールのインタ フェースを活用して、、まだ学校に関連する電子メールを取得する必要な教育環境で最も一般的です。別の例お客様ハイブリッド シナリオでは、EOP から電子メールを送信する、オンプレミスのサーバーがある場合です。</span><span class="sxs-lookup"><span data-stu-id="8573e-p102">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premise servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="8573e-109">登録されていないドメインの問題</span><span class="sxs-lookup"><span data-stu-id="8573e-109">Problems with unregistered domains</span></span>

<span data-ttu-id="8573e-p103">オンプレミスのサーバーが侵害され、大量の EOP をスパムの中継を終了するときに問題があります。ほとんどすべての場合、右側のコネクタに設定されてですが、登録されていないとも呼ばれる準備が解除された、ドメインから送信される電子メール。Office 365 は適度な未登録のドメインからのメールを許可するを送信するように計画する各ドメインの管理センターで、承認済みドメインを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8573e-p103">The problem is when on-premise servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="8573e-p104">危険にさらされた後のテナントされなくなります登録されていないドメインからの送信メールを送信します。ユーザーは配信不能レポート (NDR) を示すが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8573e-p104">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="8573e-p105">550 5.7.750 サービスを利用できません。クライアントが登録されていないドメインからの送信は禁止</span><span class="sxs-lookup"><span data-stu-id="8573e-p105">550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="8573e-117">再送信するためにブロック解除のテナント</span><span class="sxs-lookup"><span data-stu-id="8573e-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="8573e-118">登録されていないドメインから送信するためにブロックされる場合に実行する必要があるいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="8573e-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="8573e-p106">すべてのドメインを Office 365 の管理センターで登録することを確認します。詳細についてを参照して[ここで](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="8573e-p106">Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="8573e-p107">オンプレミスのサーバーをロックダウンし、侵害がないことを確認します。多くの要因関係するここでは、これらは、サード パーティのサーバーがそのサーバーをそのまますべてのメールが正当なことを確認できるようにする必要が場合に特に。</span><span class="sxs-lookup"><span data-stu-id="8573e-p107">Lock down your on-premise servers and ensure that they are not compromised. There are many factors involved here, especially if these are third-party servers, but you will need to be able to make sure all mail leaving that server is legitimate.</span></span>

<span data-ttu-id="8573e-p108">終わったら、マイクロソフト サポートに連絡し、登録されていないドメインから再送信をブロック解除、テナントを取得するよう要求する必要があります。 エラー コードを提供することをお勧め、ですが、お客様の環境がセキュリティで保護されていると、迷惑メールは再送信されないことを証明する必要があります。詳細についてを参照して[ここで](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。</span><span class="sxs-lookup"><span data-stu-id="8573e-p108">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="8573e-126">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8573e-126">For more information</span></span>

[<span data-ttu-id="8573e-127">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="8573e-127">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="8573e-128">Office 365 の電子メールの配信不能レポート</span><span class="sxs-lookup"><span data-stu-id="8573e-128">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="8573e-129">メールボックスへの電子メールの転送を構成する</span><span class="sxs-lookup"><span data-stu-id="8573e-129">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="8573e-130">Office 365 を使用してメールを送信するように多機能デバイスまたはアプリケーションをセット アップする方法</span><span class="sxs-lookup"><span data-stu-id="8573e-130">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="8573e-131">[管理許可ドメイン Exchange オンライン](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="8573e-131">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
