---
title: 迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 'ユーザーがスパムとして分類されている Office 365 からメッセージを送り続ける場合、メッセージを送信しないよう制限されます。 '
ms.openlocfilehash: 56f1a34fe4b47a722ff1dace73dd001f0c4812a2
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854721"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="8659d-103">迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="8659d-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="8659d-104">ユーザーが、Office 365 からスパムとして分類される 電子メールを送信し続ける場合、電子メールの送信は制限されますが、それでも受信はできます。</span><span class="sxs-lookup"><span data-stu-id="8659d-104">If a user continuously sends emails that are classified as spam from Office 365, they will be restricted from sending email, but will still be able to receive it.</span></span> <span data-ttu-id="8659d-105">ユーザーはサービスに不適切な送信者として記録され、次のような配信不能レポート（NDR）を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8659d-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

> <span data-ttu-id="8659d-106">「有効な送信者として認識されなかったため、メッセージを配信できませんでした。」</span><span class="sxs-lookup"><span data-stu-id="8659d-106">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="8659d-107">この最も一般的な理由は、メールアドレスがスパムを送信している疑いがあり、メールを送信することを許可されていないことです。</span><span class="sxs-lookup"><span data-stu-id="8659d-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="8659d-108">詳細については、メールアドレスの管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="8659d-108">Contact  your email admin for assistance.</span></span> <span data-ttu-id="8659d-109">リモートサーバーが 「550 5.1.8 アクセスが拒否されました。アウトバウンド送信者が正しくありません」を返す</span><span class="sxs-lookup"><span data-stu-id="8659d-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8659d-110">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="8659d-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="8659d-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="8659d-111"></span></span>

<span data-ttu-id="8659d-112">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="8659d-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="8659d-113">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8659d-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="8659d-114">必要なアクセス許可については、「[Exchange Online の機能アクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」の「スパム対策」のエントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8659d-114">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the Anti-spam entry in the [Feature permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="8659d-115">以下の手順はリモート PowerShell 経由でも実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8659d-115">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="8659d-116">Get-BlockedSenderAddress コマンドレットを使用して制限付きユーザーのリストを取得し、Remove-BlockedSenderAddress を使用して制限を削除します。</span><span class="sxs-lookup"><span data-stu-id="8659d-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="8659d-117">Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8659d-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="8659d-118">ブロックされた Office 365 メールアカウントの制限を削除する</span><span class="sxs-lookup"><span data-stu-id="8659d-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="8659d-119">このタスクは、セキュリティ/コンプライアンス センター（SCC）で実行します。</span><span class="sxs-lookup"><span data-stu-id="8659d-119">You complete this task in the Security & Compliance Center (SCC).</span></span> <span data-ttu-id="8659d-120">SCC の詳細については、[セキュリティ/コンプライアンス センターにアクセス](go-to-the-securitycompliance-center.md)してください。</span><span class="sxs-lookup"><span data-stu-id="8659d-120">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="8659d-121">これらの機能を実行するには、**組織管理**または**セキュリティ管理者**の役割グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8659d-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="8659d-122">SCC 役割グループの詳細については、[「セキュリティ/コンプライアンスセンターの権限」を参照](permissions-in-the-security-and-compliance-center.md)してください。</span><span class="sxs-lookup"><span data-stu-id="8659d-122">[Go to Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="8659d-123">Office 365　の包括的な管理者権限を持つ職場または学校のアカウントを使用して、Office 365 セキュリティ/コンプライアンスセンターにサインインし、左側のリストで **[脅威の管理]** を展開し、**[レビュー]** を選択して、**[制限付きユーザー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="8659d-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8659d-124">セキュリティ&amp;コンプライアンス センターの**制限付きユーザー**ページ（旧称アクションセンター）に直接アクセスするには、次のURLを使用します：> [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="8659d-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="8659d-125">このページには、メールの送信がブロックされているユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8659d-125">This page will contain the list of users that have been blocked from sending email.</span></span>  <span data-ttu-id="8659d-126">制限を削除するユーザーを見つけて、**[ブロック解除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8659d-126">Find the user you wish to remove restrictions from, and select **Unblock**.</span></span>

3. <span data-ttu-id="8659d-127">送信が制限されているアカウントの詳細がポップアップで表示されます。</span><span class="sxs-lookup"><span data-stu-id="8659d-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="8659d-128">アカウントが実際に侵害された場合に備えて、適切な対策を講じるため、推奨事項を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8659d-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="8659d-129">操作が完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8659d-129">Click **Next** when it's done.</span></span>

4. <span data-ttu-id="8659d-130">次の画面には、今後の侵害を防ぐための推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8659d-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="8659d-131">\*多要素認証 (MFA) を有効にし、</span><span class="sxs-lookup"><span data-stu-id="8659d-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="8659d-132">操作が完了したら、**[ユーザーのブロックを解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8659d-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="8659d-133">**[はい]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="8659d-133">Click **Yes** to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8659d-134">制限が解除されるまで 30 分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8659d-134">It may take 30 minutes or more before restrictions are removed.</span></span> 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="8659d-135">この事態の際に管理者にアラートが送信されるようにする</span><span class="sxs-lookup"><span data-stu-id="8659d-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="8659d-136">「メールの送信を制限されたユーザー」アラートは、Office 365 のセキュリティ/コンプライアンスのアラート ポリシーページでポリシーとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="8659d-136">A "User restricted from sending email" alert is available as a policy under the Office 365 Security & Compliance Alert policies page.</span></span> <span data-ttu-id="8659d-137">これは以前は送信用のスパムポリシーでしたが、現在は Office 365 アラート プラットフォームに実装されています。</span><span class="sxs-lookup"><span data-stu-id="8659d-137">This was formerly the outbound spam policy but is now native to the Office 365 alerting platform.</span></span> <span data-ttu-id="8659d-138">アラートの詳細については、「[セキュリティ/コンプライアンス センターでのアラート ポリシー](alert-policies.md)」を参照してください。 </span><span class="sxs-lookup"><span data-stu-id="8659d-138">Go to [Alert policies in the Security & Compliance Center](alert-policies.md) for more information on alerts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8659d-139">アラートを機能させるには、監査ログ検索をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8659d-139">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="8659d-140">詳細については、「[Office 365 の監査ログの検索を有効または無効にする](turn-audit-log-search-on-or-off.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8659d-140">See how to [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md) for more information.</span></span>

<span data-ttu-id="8659d-141">このアラートのポリシーは既定のものであり、すべての Office 365 テナントに付属しているため、設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8659d-141">The policy for this alert is a default one and comes with every Office 365 tenant and does not need to be set up.</span></span> <span data-ttu-id="8659d-142">これは重大度の高いアラートと見なされ、ユーザーがメールの送信を制限されている場合にアラートが発生するたび、設定された TenantAdmins グループにメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="8659d-142">It is considered a High severity alert and will email the configured TenantAdmins group when the alert is fired whenever a user has been restricted from sending mail.</span></span> <span data-ttu-id="8659d-143">管理者は、[SCC ポータル] > [アラート] > [アラート ポリシー] > [メールの送信が制限されているユーザー]　の下にあるアラートに移動して、このアラートが発生したときに通知されるグループを更新できます。</span><span class="sxs-lookup"><span data-stu-id="8659d-143">Admins can update the group notified when this alert happens by going to the alert under the SCC portal > Alerts > Alert policies > Users restricted from sending email.</span></span>

<span data-ttu-id="8659d-144">アラートは次のように編集できます。</span><span class="sxs-lookup"><span data-stu-id="8659d-144">You will be able to Edit the alert to:</span></span>
- <span data-ttu-id="8659d-145">メール通知をオン/オフにする</span><span class="sxs-lookup"><span data-stu-id="8659d-145">Turn email notifications On/Off</span></span>
- <span data-ttu-id="8659d-146">必要な受信者にメールを送信する</span><span class="sxs-lookup"><span data-stu-id="8659d-146">Email the required recipients</span></span>
- <span data-ttu-id="8659d-147">1 日に受信する通知を制限する</span><span class="sxs-lookup"><span data-stu-id="8659d-147">Limit the notifications you get per day</span></span>

## <a name="checking-for-and-removing-restrictions-using-powershell"></a><span data-ttu-id="8659d-148">PowerShell を使用して制限を確認および削除する</span><span class="sxs-lookup"><span data-stu-id="8659d-148">Checking for and removing restrictions using PowerShell</span></span>
<span data-ttu-id="8659d-149">制限付きユーザー向けの PowerShell コマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8659d-149">The PowerShell commands for Restricted Users are:</span></span>
- <span data-ttu-id="8659d-150">`Get-BlockedSenderAddress`：メールの送信が制限されているユーザーのリストを取得する</span><span class="sxs-lookup"><span data-stu-id="8659d-150">`Get-BlockedSenderAddress`: Run to retreive the list of users that are restricted from sending email</span></span>
- <span data-ttu-id="8659d-151">`Remove-BlockedSenderAddress`：ユーザーの制限を削除する</span><span class="sxs-lookup"><span data-stu-id="8659d-151">`Remove-BlockedSenderAddress`: Run to remove user(s) from being restricted</span></span>

## <a name="for-more-information"></a><span data-ttu-id="8659d-152">関連情報</span><span class="sxs-lookup"><span data-stu-id="8659d-152">For more information</span></span>

[<span data-ttu-id="8659d-153">侵害された電子メール アカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="8659d-153">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

<span data-ttu-id="8659d-154">
  [メールアラートの送信が制限されているユーザーを把握する](https://docs.microsoft.com/ja-JP/office365/securitycompliance/alert-policies)</span><span class="sxs-lookup"><span data-stu-id="8659d-154">[Understanding the User restricted from sending email alert](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)</span></span>

[<span data-ttu-id="8659d-155">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="8659d-155">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="8659d-156">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8659d-156">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

<span data-ttu-id="8659d-157">
  [セキュリティ/コンプライアンス センターのアラート ポリシー](https://docs.microsoft.com/ja-JP/office365/securitycompliance/alert-policies)</span><span class="sxs-lookup"><span data-stu-id="8659d-157">[Alert policies in the Office 365 Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)</span></span>
