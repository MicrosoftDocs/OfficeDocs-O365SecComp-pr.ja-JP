---
title: ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/20/2018
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
ms.openlocfilehash: 87b7083fe1345a15ea582f12a5b0d417bbe6b568
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002603"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="f0786-103">ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する</span><span class="sxs-lookup"><span data-stu-id="f0786-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="f0786-104">スパムとして分類されている Office 365 からメール メッセージをユーザーが送り続ける場合、メッセージを送信しないようブロックされます。 </span><span class="sxs-lookup"><span data-stu-id="f0786-104">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages.</span></span> 
  
<span data-ttu-id="f0786-105">
送信者がメール メッセージを送信しないようブロックされると、配信不能レポート (NDR つまりメールはメッセージの送信に失敗した) を受信します。このレポートは、ブロックを解除するために取る必要がある手順に関する特定の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f0786-105">When a sender is blocked from sending emails messages, they receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>
  
<span data-ttu-id="f0786-p101">サービスが特定の web サイト、ドメイン、個々 のユーザーがブロックされ、だけでなく、IP アドレスをブロックすることもできます。場合によっては、ドメインまたは web サイト追加できますブロック リストに迷惑メール メッセージに表示されているからといって。として Office 365 の管理者、ユーザー、web サイト、ドメイン、およびサード パーティのブロック リストから削除する IP アドレスを取得しようことができます。このトピックの下部にあるテーブルのリンクを使用して、各サード パーティに連絡し、指示に従って操作します。場合は、Office 365 アカウントに他のユーザーが Office 365 の外部メッセージを送信できません、自分のアカウント可能性がありますが、最終的に外部の受信拒否リストに。Office 365 の外部のユーザーは、自分を[delisting のセルフ サービス ポータル](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx)を使用して受信拒否リストから削除を試行できます。</span><span class="sxs-lookup"><span data-stu-id="f0786-p101">Not only can individual users be blocked by the service, but specific websites, domains, and IP addresses can also be blocked. In some cases, domains or websites can be added to a block list just because they appear in a spam message. As the Office 365 admin, you can try to get users, websites, domains, and IP addresses removed from third-party block lists. Use the links in the table at the bottom of this topic to contact each third party, and then follow the instructions. If someone outside Office 365 cannot send messages to your Office 365 account, their account may have ended up on the external blocked senders list. Users outside Office 365 can try to remove themselves from the blocked senders list by using the [self-service delisting portal](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="f0786-p102">スパムとして分類されているメールを送信しないよう Office 365 ユーザーがブロックされたときに、通知を受け取るよう送信スパム設定を構成できます。ユーザーのメールボックスの問題が解決されると、その送信者のブロックを解除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f0786-p102">You can configure outbound spam settings so that you get anotification when an Office 365 user is blocked from sending email that's classified as spam. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="f0786-114">ブロックされている Office 365 メール アカウントのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="f0786-114">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="f0786-p103">Exchange 管理センター (EAC) では、このタスクを完了するとします。EAC の詳細については、 [Exchange 管理センターでは、Exchange オンライン保護](exchange-admin-center-in-exchange-online-protection-eop.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0786-p103">You complete this task in the Exchange admin center (EAC). Check out [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) for details about the EAC.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f0786-117">Exchange Online の EAC 以外では、アクション センターは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f0786-117">You won't see the action center unless you're in the EAC for Exchange Online.</span></span> 
  
1. <span data-ttu-id="f0786-118">EAC で**の保護**に移動\>**アクション センター**です。</span><span class="sxs-lookup"><span data-stu-id="f0786-118">In the EAC, navigate to **protection** \> **action center**.</span></span>
    
    ![Exchange 管理センターのアクション センターに移動します。](media/9bbf0844-7b34-4a86-a2b7-8c7e9c8519a3.png)
  
2. <span data-ttu-id="f0786-120">**[検索]** アイコンを選択し、ブロックされているユーザーの SMTP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f0786-120">Select the **Search** icon, and then enter the SMTP address of the blocked user.</span></span> 
    
    ![アクション センターでブロックされているユーザーを検索する](media/f931b5a0-7115-4d95-9f6f-b403436031ba.png)
  
3. <span data-ttu-id="f0786-122">説明ウィンドウの **[アカウントのブロック解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0786-122">Click **Unblock Account** in the description pane.</span></span> 
    
    ![アクション センターでユーザーのブロックを解除する](media/c5d5b1b9-8416-45aa-9631-881e94d1d056.png)
  
4. <span data-ttu-id="f0786-124">**[はい]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="f0786-124">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="f0786-p104">テナント管理者がアカウントのブロックを解除できる回数には制限があります。ユーザーに関して制限を超えると、エラー メッセージが表示されます。ユーザーのブロックを解除するには、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f0786-p104">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. Contact Support to unblock the user.</span></span> 
  
## <a name="third-party-block-lists"></a><span data-ttu-id="f0786-127">サード パーティのブロック リスト</span><span class="sxs-lookup"><span data-stu-id="f0786-127">Third-party block lists</span></span>

|<span data-ttu-id="f0786-128">**リスト名**</span><span class="sxs-lookup"><span data-stu-id="f0786-128">**List Name**</span></span>|<span data-ttu-id="f0786-129">**リスト削除ポータル**</span><span class="sxs-lookup"><span data-stu-id="f0786-129">**Delisting Portal**</span></span>|<span data-ttu-id="f0786-130">**詳細情報**</span><span class="sxs-lookup"><span data-stu-id="f0786-130">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f0786-131">URIBL</span><span class="sxs-lookup"><span data-stu-id="f0786-131">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="f0786-132">URIBL web サイト</span><span class="sxs-lookup"><span data-stu-id="f0786-132">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="f0786-133">SURBL</span><span class="sxs-lookup"><span data-stu-id="f0786-133">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="f0786-134">SURBL URI の評判のデータの概要</span><span class="sxs-lookup"><span data-stu-id="f0786-134">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="f0786-135">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="f0786-135">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="f0786-136">DNSBL フィルタ リングを理解します。</span><span class="sxs-lookup"><span data-stu-id="f0786-136">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="f0786-137">invaluement</span><span class="sxs-lookup"><span data-stu-id="f0786-137">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="f0786-138">invaluement スパム対策リスト</span><span class="sxs-lookup"><span data-stu-id="f0786-138">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="f0786-139">Phishtank</span><span class="sxs-lookup"><span data-stu-id="f0786-139">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="f0786-140">PhishTank のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="f0786-140">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> <span data-ttu-id="f0786-141">また、Exchange のオンライン保護は、スパムのフィルタ リングのサード パーティのブロック リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0786-141">Exchange Online Protection also uses third-party block lists for spam filtering.</span></span> 
   
## <a name="for-more-information"></a><span data-ttu-id="f0786-142">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f0786-142">For more information</span></span>

[<span data-ttu-id="f0786-143">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="f0786-143">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="f0786-144">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="f0786-144">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="f0786-145">リストから除外のポータルを使って Office 365 の受信拒否リストから自分自身を削除する</span><span class="sxs-lookup"><span data-stu-id="f0786-145">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

