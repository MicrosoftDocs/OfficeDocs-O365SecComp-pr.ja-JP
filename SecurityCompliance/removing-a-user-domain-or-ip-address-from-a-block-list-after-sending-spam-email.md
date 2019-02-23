---
title: ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/01/2018
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
ms.openlocfilehash: 3ffd8b65d6994699093237e9f9a0a3aaa802f5e2
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223086"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="51c79-103">ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する</span><span class="sxs-lookup"><span data-stu-id="51c79-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="51c79-p101">ユーザーが、スパムとして分類された Office 365 から電子メールメッセージを継続的に送信した場合、それ以上メッセージを送信することはブロックされます。ユーザーは、無効な送信者としてサービスに一覧表示され、次の状態を示す配信不能レポート (NDR) を受信します。</span><span class="sxs-lookup"><span data-stu-id="51c79-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="51c79-p102">有効な送信者として認識されなかったため、メッセージを配信できませんでした。最も一般的な理由は、メールアドレスがスパムを送信している可能性があり、組織外のメッセージを送信することが許可されなくなったためです。詳細については、メール管理者に問い合わせてください。 リモートサーバーが ' 550 5.1.8 アクセスが拒否されましたが、正しくない送信送信者 ' が返されました</span><span class="sxs-lookup"><span data-stu-id="51c79-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="51c79-110">また、テナント管理者は、ユーザーがその他の送信メッセージの送信を制限していることを示す警告を受信します。</span><span class="sxs-lookup"><span data-stu-id="51c79-110">The tenant admins will also receive an alert stating that the user has been restricted from sending any more outbound messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51c79-111">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="51c79-111">What do you need to know before you begin?</span></span>
<span data-ttu-id="51c79-112"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="51c79-112"></span></span>

<span data-ttu-id="51c79-113">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="51c79-113">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="51c79-p103">この手順を実行する前に、アクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「スパム対策エントリ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51c79-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="51c79-p104">次の手順は、リモート PowerShell を使用して実行することもできます。制限を解除するには、BlockedSenderAddress コマンドレットを使用して、制限されたユーザーの一覧を取得し、BlockedSenderAddress を削除します。Windows PowerShell を使用して exchange online に接続する方法については、「 [exchange online powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51c79-p104">The following procedure can also be performed via remote PowerShell. Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="51c79-119">ブロックされた Office 365 メールアカウントの制限を削除する</span><span class="sxs-lookup"><span data-stu-id="51c79-119">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="51c79-p105">このタスクは、「Office 365 Security & コンプライアンスセンター (SCC) で完了します。SCC の詳細について[は、「Office 365 Security & コンプライアンスセンター」を参照](go-to-the-securitycompliance-center.md)してください。これらの機能を実行するには、**組織の管理**または**セキュリティ管理者**の役割グループに所属している必要があります。SCC の役割グループの詳細について[は、「Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可」を参照](permissions-in-the-security-and-compliance-center.md)してください。</span><span class="sxs-lookup"><span data-stu-id="51c79-p105">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC. You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions. [Go to Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="51c79-124">office 365 のグローバル管理者特権を持つ職場または学校のアカウントを使用して、office 365 セキュリティ/コンプライアンスセンターにサインインし、左側の一覧で [**脅威の管理**] を展開し、[**レビュー**] を選択して、[制限あり] を選択します。 **ユーザー**。</span><span class="sxs-lookup"><span data-stu-id="51c79-124">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="51c79-125">セキュリティ&amp; /コンプライアンスセンターの [制限された**ユーザー** ] ページ (以前のアクションセンター) に直接移動するには、次の URL を使用します。 >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="51c79-125">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="51c79-p106">このページには、組織外へのメールの送信をブロックされているユーザーの一覧が表示されます。 制限を解除するユーザーを見つけ、[**ブロックの解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51c79-p106">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="51c79-128">**[はい]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="51c79-128">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="51c79-p107">テナント管理者がアカウントのブロックを解除できる回数には制限があります。ユーザーの制限を超えている場合は、エラーメッセージが表示されます。その後、サポートに連絡して、ユーザーのブロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c79-p107">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span><br/><br/> <span data-ttu-id="51c79-131">ユーザーがブロック解除されるまで最大で1時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="51c79-131">It may take up to 1 hour before the user is unblocked.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="51c79-132">サード パーティのブロック リスト</span><span class="sxs-lookup"><span data-stu-id="51c79-132">Third-party block lists</span></span>

<span data-ttu-id="51c79-p108">Exchange Online Protection では、スパムフィルター処理における意思決定に役立てるために、サードパーティのブロックリストも使用します。ユーザー、web サイト、ドメイン、および IP アドレスを、スパムメッセージに表示するためだけにブロックリストに追加できます。Office 365 管理者は、サードパーティのリストプロバイダーが所有している場合は、それらのオブジェクトを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c79-p108">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you.</span></span>

> [!NOTE]
> <span data-ttu-id="51c79-p109">office 365 の外部のユーザーが office 365 アカウントにメッセージを送信できない場合は、そのアカウントが外部の受信拒否リストに含まれている可能性があります。Office 365 の外部のユーザーは、[セルフサービス](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)の区切りポータルを使用して自分自身を削除しようとすることができます。</span><span class="sxs-lookup"><span data-stu-id="51c79-p109">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="51c79-138">関連情報</span><span class="sxs-lookup"><span data-stu-id="51c79-138">For more information</span></span>

[<span data-ttu-id="51c79-139">侵害された電子メールアカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="51c79-139">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="51c79-140">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="51c79-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="51c79-141">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="51c79-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="51c79-142">Office 365 Security & コンプライアンスセンターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="51c79-142">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

  

