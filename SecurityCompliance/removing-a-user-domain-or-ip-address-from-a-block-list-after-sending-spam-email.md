---
title: ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: 'スパムとして分類されている Office 365 からメール メッセージをユーザーが送り続ける場合、メッセージを送信しないようブロックされます。 '
ms.openlocfilehash: 6665c405c62f75b77e7898419ebcfbc1c8c20f4c
ms.sourcegitcommit: 7b85c22fc85ec19e4b44a07e91bfa9ade768185a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998611"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="660a9-103">ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する</span><span class="sxs-lookup"><span data-stu-id="660a9-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="660a9-p101">ユーザーは、継続的に迷惑メールとして分類されている Office 365 の電子メール メッセージを送信する場合は、そのメッセージの送信がブロックされます。ユーザーが不正な送信の送信元としてサービスに表示され、配信不能レポート (NDR) を示すが表示されます。</span><span class="sxs-lookup"><span data-stu-id="660a9-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="660a9-p102">有効な送信者として認識していなかったために、メッセージを配信できませんでした。このエラーの最も一般的な理由は、あなたの電子メール アドレスがスパムを送信する可能性がある場合、そのことができなく、組織外へメッセージを送信するには。について、メール管理者に問い合わせてください。 550 5.1.8 アクセス拒否、送信者送信リモート サーバーから返されました</span><span class="sxs-lookup"><span data-stu-id="660a9-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="660a9-p103">送信スパム ポリシー設定を構成するには、電子メールを送信することから、Office 365 ユーザーがブロックされたときに通知を取得するためです。ユーザーのメールボックスで問題が解決された後は、その送信者のブロックを削除できます。</span><span class="sxs-lookup"><span data-stu-id="660a9-p103">You can configure your outbound spam policy settings so that you get a notification when an Office 365 user is blocked from sending email. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="660a9-112">ブロックされている Office 365 メール アカウントのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="660a9-112">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="660a9-p104">Office 365 のセキュリティとコンプライアンス センター (SCC) では、このタスクを完了するとします。SCC の詳細については、 [Office 365 のセキュリティとコンプライアンスの中心に移動](go-to-the-securitycompliance-center.md)をします。</span><span class="sxs-lookup"><span data-stu-id="660a9-p104">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="660a9-115">職場または学校を Office 365 のセキュリティやコンプライアンス センターにサインインし、**脅威の管理**を展開し、左側のボックスの一覧で、**レビュー**をクリックし選択**制限付きの Office 365 グローバル管理者特権を持つアカウントを使用してください。ユーザー**。</span><span class="sxs-lookup"><span data-stu-id="660a9-115">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="660a9-116">セキュリティで**制限されたユーザー**のページに直接移動するのには&amp;コンプライアンス センターでは、この URL を使用します >。[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="660a9-116">To go directly to the **Restricted Users** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="660a9-p105">このページから別の組織にメールを送信するブロックされているユーザーの一覧が含まれます。 上の制限を削除し、たいをクリックし、**ブロックを解除する**にユーザーを検索するには。</span><span class="sxs-lookup"><span data-stu-id="660a9-p105">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="660a9-119">**[はい]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="660a9-119">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="660a9-p106">テナント管理者がアカウントのブロックを解除できる回数に制限があります。ユーザーの制限を超えた場合は、エラー メッセージが表示されます。ユーザーのブロックを解除するためのサポートに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="660a9-p106">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="660a9-122">サード パーティのブロック リスト</span><span class="sxs-lookup"><span data-stu-id="660a9-122">Third-party block lists</span></span>

<span data-ttu-id="660a9-p107">また、Exchange のオンライン保護は、スパム フィルターで決定を下すためにサード パーティのブロック リストを使用します。ブロックのスパム メッセージに表示されるリストには、ユーザー、web サイト、ドメイン、および IP アドレスを追加できます。、Office 365 管理者としては、これらのオブジェクトに属している場合は、サード ・ パーティ製リスト プロバイダーからの削除を取得するください。内のリンクを使用して、各サード パーティに連絡し、指示に従って操作するテーブルの下。</span><span class="sxs-lookup"><span data-stu-id="660a9-p107">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you. Use the links in the below table to contact each third party and then follow their instructions.</span></span>

|<span data-ttu-id="660a9-127">**リスト名**</span><span class="sxs-lookup"><span data-stu-id="660a9-127">**List Name**</span></span>|<span data-ttu-id="660a9-128">**リスト削除ポータル**</span><span class="sxs-lookup"><span data-stu-id="660a9-128">**Delisting Portal**</span></span>|<span data-ttu-id="660a9-129">**詳細情報**</span><span class="sxs-lookup"><span data-stu-id="660a9-129">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="660a9-130">URIBL</span><span class="sxs-lookup"><span data-stu-id="660a9-130">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="660a9-131">URIBL web サイト</span><span class="sxs-lookup"><span data-stu-id="660a9-131">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="660a9-132">SURBL</span><span class="sxs-lookup"><span data-stu-id="660a9-132">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="660a9-133">SURBL URI の評判のデータの概要</span><span class="sxs-lookup"><span data-stu-id="660a9-133">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="660a9-134">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="660a9-134">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="660a9-135">DNSBL フィルタ リングを理解します。</span><span class="sxs-lookup"><span data-stu-id="660a9-135">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="660a9-136">invaluement</span><span class="sxs-lookup"><span data-stu-id="660a9-136">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="660a9-137">invaluement スパム対策リスト</span><span class="sxs-lookup"><span data-stu-id="660a9-137">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="660a9-138">Phishtank</span><span class="sxs-lookup"><span data-stu-id="660a9-138">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="660a9-139">PhishTank のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="660a9-139">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |

> [!NOTE]
> <span data-ttu-id="660a9-p108">Office 365 アカウントに他のユーザーが Office 365 の外部メッセージを送信できません、ブロックされた外部の送信者の一覧に自分のアカウント可能性があります。Office 365 の外部のユーザーは、自分を[delisting のセルフ サービス ポータル](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)を使用して削除を試行できます。</span><span class="sxs-lookup"><span data-stu-id="660a9-p108">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="660a9-142">詳細情報</span><span class="sxs-lookup"><span data-stu-id="660a9-142">For more information</span></span>

[<span data-ttu-id="660a9-143">感染した電子メール アカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="660a9-143">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="660a9-144">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="660a9-144">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="660a9-145">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="660a9-145">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

  

  

