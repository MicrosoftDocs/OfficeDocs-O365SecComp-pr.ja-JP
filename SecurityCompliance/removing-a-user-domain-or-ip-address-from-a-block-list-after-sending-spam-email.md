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
ms.openlocfilehash: 3f3130bec3cde4cdc1343a0140a9013deacfc519
ms.sourcegitcommit: d85fc77cba3a17d5ddf215e2f506f61b499e0cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "23839111"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="9ab1f-103">ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する</span><span class="sxs-lookup"><span data-stu-id="9ab1f-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="9ab1f-104">スパムとして分類されている Office 365 からメール メッセージをユーザーが送り続ける場合、メッセージを送信しないようブロックされます。 </span><span class="sxs-lookup"><span data-stu-id="9ab1f-104">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages.</span></span> 
  
<span data-ttu-id="9ab1f-105">
送信者がメール メッセージを送信しないようブロックされると、配信不能レポート (NDR つまりメールはメッセージの送信に失敗した) を受信します。このレポートは、ブロックを解除するために取る必要がある手順に関する特定の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9ab1f-105">When a sender is blocked from sending emails messages, they receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>
  
<span data-ttu-id="9ab1f-p101">サービスが特定の web サイト、ドメイン、個々 のユーザーがブロックされ、だけでなく、IP アドレスをブロックすることもできます。場合によっては、ドメインまたは web サイト追加できますブロック リストに迷惑メール メッセージに表示されているからといって。として Office 365 の管理者、ユーザー、web サイト、ドメイン、およびサード パーティのブロック リストから削除する IP アドレスを取得しようことができます。このトピックの下部にあるテーブルのリンクを使用して、各サード パーティに連絡し、指示に従って操作します。場合は、Office 365 アカウントに他のユーザーが Office 365 の外部メッセージを送信できません、自分のアカウント可能性がありますが、最終的に外部の受信拒否リストに。Office 365 の外部のユーザーは、自分を[delisting のセルフ サービス ポータル](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx)を使用して受信拒否リストから削除を試行できます。</span><span class="sxs-lookup"><span data-stu-id="9ab1f-p101">Not only can individual users be blocked by the service, but specific websites, domains, and IP addresses can also be blocked. In some cases, domains or websites can be added to a block list just because they appear in a spam message. As the Office 365 admin, you can try to get users, websites, domains, and IP addresses removed from third-party block lists. Use the links in the table at the bottom of this topic to contact each third party, and then follow the instructions. If someone outside Office 365 cannot send messages to your Office 365 account, their account may have ended up on the external blocked senders list. Users outside Office 365 can try to remove themselves from the blocked senders list by using the [self-service delisting portal](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="9ab1f-p102">スパムとして分類されているメールを送信しないよう Office 365 ユーザーがブロックされたときに、通知を受け取るよう送信スパム設定を構成できます。ユーザーのメールボックスの問題が解決されると、その送信者のブロックを解除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9ab1f-p102">You can configure outbound spam settings so that you get anotification when an Office 365 user is blocked from sending email that's classified as spam. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="9ab1f-114">ブロックされている Office 365 メール アカウントのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="9ab1f-114">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="9ab1f-p103">Office 365 のセキュリティとコンプライアンス センター (SCC) では、このタスクを完了するとします。SCC の詳細については、 [Office 365 のセキュリティとコンプライアンスの中心に移動](go-to-the-securitycompliance-center.md)をします。</span><span class="sxs-lookup"><span data-stu-id="9ab1f-p103">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="9ab1f-117">職場または学校を Office 365 のセキュリティやコンプライアンス センターにサインインし、**脅威の管理**を展開し、左側のボックスの一覧で、**レビュー**をクリックし選択**制限付きの Office 365 グローバル管理者特権を持つアカウントを使用してください。ユーザー**。</span><span class="sxs-lookup"><span data-stu-id="9ab1f-117">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="9ab1f-118">セキュリティで**制限されたユーザー**のページに直接移動するのには&amp;コンプライアンス センターでは、この URL を使用します >。[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="9ab1f-118">To go directly to the **Restricted Users** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="9ab1f-p104">このページから別の組織にメールを送信するブロックされているユーザーの一覧が含まれます。 制限を解除し、たい] をクリックし、**ブロックを解除する**ので、ユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="9ab1f-p104">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user(s) you wish to remove restrictions and then click on **Unblock**.</span></span>

3. <span data-ttu-id="9ab1f-121">**[はい]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="9ab1f-121">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="9ab1f-p105">テナント管理者がアカウントのブロックを解除できる回数に制限があります。ユーザーの制限を超えた場合は、エラー メッセージが表示されます。ユーザーのブロックを解除するためのサポートに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ab1f-p105">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span> 
  
## <a name="third-party-block-lists"></a><span data-ttu-id="9ab1f-124">サード パーティのブロック リスト</span><span class="sxs-lookup"><span data-stu-id="9ab1f-124">Third-party block lists</span></span>

|<span data-ttu-id="9ab1f-125">**リスト名**</span><span class="sxs-lookup"><span data-stu-id="9ab1f-125">**List Name**</span></span>|<span data-ttu-id="9ab1f-126">**リスト削除ポータル**</span><span class="sxs-lookup"><span data-stu-id="9ab1f-126">**Delisting Portal**</span></span>|<span data-ttu-id="9ab1f-127">**詳細情報**</span><span class="sxs-lookup"><span data-stu-id="9ab1f-127">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9ab1f-128">URIBL</span><span class="sxs-lookup"><span data-stu-id="9ab1f-128">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="9ab1f-129">URIBL web サイト</span><span class="sxs-lookup"><span data-stu-id="9ab1f-129">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="9ab1f-130">SURBL</span><span class="sxs-lookup"><span data-stu-id="9ab1f-130">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="9ab1f-131">SURBL URI の評判のデータの概要</span><span class="sxs-lookup"><span data-stu-id="9ab1f-131">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="9ab1f-132">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="9ab1f-132">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="9ab1f-133">DNSBL フィルタ リングを理解します。</span><span class="sxs-lookup"><span data-stu-id="9ab1f-133">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="9ab1f-134">invaluement</span><span class="sxs-lookup"><span data-stu-id="9ab1f-134">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="9ab1f-135">invaluement スパム対策リスト</span><span class="sxs-lookup"><span data-stu-id="9ab1f-135">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="9ab1f-136">Phishtank</span><span class="sxs-lookup"><span data-stu-id="9ab1f-136">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="9ab1f-137">PhishTank のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="9ab1f-137">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> <span data-ttu-id="9ab1f-138">また、Exchange のオンライン保護は、スパムのフィルタ リングのサード パーティのブロック リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ab1f-138">Exchange Online Protection also uses third-party block lists for spam filtering.</span></span> 
   
## <a name="for-more-information"></a><span data-ttu-id="9ab1f-139">詳細情報</span><span class="sxs-lookup"><span data-stu-id="9ab1f-139">For more information</span></span>

[<span data-ttu-id="9ab1f-140">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="9ab1f-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="9ab1f-141">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="9ab1f-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="9ab1f-142">リストから除外のポータルを使って Office 365 の受信拒否リストから自分自身を削除する</span><span class="sxs-lookup"><span data-stu-id="9ab1f-142">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

