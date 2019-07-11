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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: ユーザーが、スパムとして分類された Office 365 から電子メールを継続的に送信した場合、それ以上メッセージを送信することはできません。
ms.openlocfilehash: 40d63bb452392041401fd1af6d0d6d4af67e5d2b
ms.sourcegitcommit: 986f40a00ab454093b21e724d58594b8b8b4a9ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "35613655"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="51a0a-103">迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="51a0a-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="51a0a-104">ユーザーが Office 365 からスパムとして分類された電子メールを継続的に送信すると、メールの送信が制限されますが、受信は可能になります。</span><span class="sxs-lookup"><span data-stu-id="51a0a-104">If a user continuously sends emails that are classified as spam from Office 365, they will be restricted from sending email, but will still be able to receive it.</span></span> <span data-ttu-id="51a0a-105">ユーザーは、無効な送信者としてサービスに一覧表示され、次の状態を示す配信不能レポート (NDR) を受信します。</span><span class="sxs-lookup"><span data-stu-id="51a0a-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

> <span data-ttu-id="51a0a-106">"有効な送信者として認識されなかったため、メッセージを配信できませんでした。</span><span class="sxs-lookup"><span data-stu-id="51a0a-106">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="51a0a-107">最も一般的な理由は、電子メールアドレスがスパム送信の疑いがあり、電子メールの送信が許可されていないためです。</span><span class="sxs-lookup"><span data-stu-id="51a0a-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="51a0a-108">詳細については、メール管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="51a0a-108">Contact  your email admin for assistance.</span></span> <span data-ttu-id="51a0a-109">リモートサーバーが ' 550 5.1.8 アクセス拒否、正しくない送信送信者を返しました。 "</span><span class="sxs-lookup"><span data-stu-id="51a0a-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51a0a-110">事前に必要な知識</span><span class="sxs-lookup"><span data-stu-id="51a0a-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="51a0a-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="51a0a-111"></span></span>

<span data-ttu-id="51a0a-112">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="51a0a-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="51a0a-113">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="51a0a-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="51a0a-114">必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「スパム対策エントリ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51a0a-114">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="51a0a-115">以下の手順はリモート PowerShell 経由でも実行することができます。Get-HostedOutboundSpamFilterPolicy コマンドレットを使用して設定を確認し、 Set-HostedOutboundSpamFilterPolicy を使用して送信スパム ポリシー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="51a0a-115">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="51a0a-116">制限を解除するには、BlockedSenderAddress コマンドレットを使用して、制限されたユーザーの一覧を取得し、BlockedSenderAddress を削除します。</span><span class="sxs-lookup"><span data-stu-id="51a0a-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="51a0a-117">Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51a0a-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="51a0a-118">ブロックされた Office 365 メールアカウントの制限を削除する</span><span class="sxs-lookup"><span data-stu-id="51a0a-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="51a0a-119">セキュリティ & コンプライアンスセンター (SCC) でこのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="51a0a-119">You complete this task in the Security & Compliance Center (SCC).</span></span> <span data-ttu-id="51a0a-120">SCC の詳細について[は、「Security & コンプライアンスセンター」を参照](go-to-the-securitycompliance-center.md)してください。</span><span class="sxs-lookup"><span data-stu-id="51a0a-120">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="51a0a-121">これらの機能を実行するには、**組織の管理**または**セキュリティ管理者**の役割グループに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="51a0a-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="51a0a-122">SCC 役割グループの詳細について[は、「セキュリティ & コンプライアンスセンター」の「アクセス許可」を参照](permissions-in-the-security-and-compliance-center.md)してください。</span><span class="sxs-lookup"><span data-stu-id="51a0a-122">[Go to Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="51a0a-123">Office 365 のグローバル管理者特権を持つ職場または学校のアカウントを使用して、Office 365 セキュリティ/コンプライアンスセンターにサインインし、左側の一覧で [**脅威の管理**] を展開し、[**レビュー**] を選択して、[制限あり] を選択します。 **ユーザー**。</span><span class="sxs-lookup"><span data-stu-id="51a0a-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="51a0a-124">セキュリティ&amp; /コンプライアンスセンターの [制限された**ユーザー** ] ページ (以前のアクションセンター) に直接移動するには、次の URL を使用します。 >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="51a0a-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="51a0a-125">このページには、電子メールの送信をブロックされているユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51a0a-125">This page will contain the list of users that have been blocked from sending email.</span></span>  <span data-ttu-id="51a0a-126">制限を削除するユーザーを検索し、[**ブロック解除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="51a0a-126">Find the user you wish to remove restrictions from, and select **Unblock**.</span></span>

3. <span data-ttu-id="51a0a-127">フライアウトは、送信が制限されているアカウントの詳細に進みます。</span><span class="sxs-lookup"><span data-stu-id="51a0a-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="51a0a-128">アカウントが実際に侵害された場合に備えて、適切な操作を実行していることを確認するために、推奨事項を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51a0a-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="51a0a-129">完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51a0a-129">Click **Next** when done.</span></span>

4. <span data-ttu-id="51a0a-130">次の画面には、今後の侵害を防止するための推奨事項があります。</span><span class="sxs-lookup"><span data-stu-id="51a0a-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="51a0a-131">多要素認証 (MFA) を有効にし、パスワードを変更することは、優れた防衛策となります。</span><span class="sxs-lookup"><span data-stu-id="51a0a-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="51a0a-132">完了したら、[**ユーザーのブロック解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51a0a-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="51a0a-133">**[はい]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="51a0a-133">Click **Yes** to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="51a0a-134">制限が削除されるまでに30分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="51a0a-134">It may take 30 minutes or more before restrictions are removed.</span></span> 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="51a0a-135">この問題が発生した場合に管理者に警告を出す</span><span class="sxs-lookup"><span data-stu-id="51a0a-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="51a0a-136">[ユーザーによる電子メール送信からの制限] 通知は、Office 365 セキュリティ & コンプライアンスのアラートポリシーのページの下にあるポリシーとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="51a0a-136">A "User restricted from sending email" alert is available as a policy under the Office 365 Security & Compliance Alert policies page.</span></span> <span data-ttu-id="51a0a-137">これは以前の送信スパムポリシーでしたが、Office 365 通知プラットフォームにネイティブになっています。</span><span class="sxs-lookup"><span data-stu-id="51a0a-137">This was formerly the outbound spam policy but is now native to the Office 365 alerting platform.</span></span> <span data-ttu-id="51a0a-138">警告の詳細について[は、「セキュリティ & コンプライアンスセンター」のアラートポリシー](alert-policies.md)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="51a0a-138">Go to [Alert policies in the Security & Compliance Center](alert-policies.md) for more information on alerts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51a0a-139">警告が機能するには、監査ログの検索を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51a0a-139">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="51a0a-140">詳細については、「 [Office 365 監査ログの検索をオンまたはオフ](turn-audit-log-search-on-or-off.md)にする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51a0a-140">See how to [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md) for more information.</span></span>

<span data-ttu-id="51a0a-141">この通知のポリシーは既定のものであり、すべての Office 365 テナントに付属しており、設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="51a0a-141">The policy for this alert is a default one and comes with every Office 365 tenant and does not need to be set up.</span></span> <span data-ttu-id="51a0a-142">ユーザーがメールの送信を制限されている場合に常に警告が発生すると、これは重要度の高いアラートとして扱われ、構成された TenantAdmins グループが電子メールで送信されます。</span><span class="sxs-lookup"><span data-stu-id="51a0a-142">It is considered a High severity alert and will email the configured TenantAdmins group when the alert is fired whenever a user has been restricted from sending mail.</span></span> <span data-ttu-id="51a0a-143">管理者は、SCC ポータルの下にあるアラートにアクセスすることで、この警告が発生したときに通知されるグループを更新することができます。ユーザーがメールの送信を制限されて > ユーザーに通知 > アラートポリシー > ます。</span><span class="sxs-lookup"><span data-stu-id="51a0a-143">Admins can update the group notified when this alert happens by going to the alert under the SCC portal > Alerts > Alert policies > Users restricted from sending email.</span></span>

<span data-ttu-id="51a0a-144">通知を編集して、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="51a0a-144">You will be able to Edit the alert to:</span></span>
- <span data-ttu-id="51a0a-145">メール通知をオン/オフにする</span><span class="sxs-lookup"><span data-stu-id="51a0a-145">Turn email notifications On/Off</span></span>
- <span data-ttu-id="51a0a-146">必要な受信者を電子メールで送信する</span><span class="sxs-lookup"><span data-stu-id="51a0a-146">Email the required recipients</span></span>
- <span data-ttu-id="51a0a-147">1日に受信する通知を制限する</span><span class="sxs-lookup"><span data-stu-id="51a0a-147">Limit the notifications you get per day</span></span>

## <a name="checking-for-and-removing-restrictions-using-powershell"></a><span data-ttu-id="51a0a-148">PowerShell を使用した制限の確認と削除</span><span class="sxs-lookup"><span data-stu-id="51a0a-148">Checking for and removing restrictions using PowerShell</span></span>
<span data-ttu-id="51a0a-149">制限されたユーザーのための PowerShell コマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51a0a-149">The PowerShell commands for Restricted Users are:</span></span>
- <span data-ttu-id="51a0a-150">`Get-BlockedSenderAddress`: を実行して、電子メールの送信を制限するユーザーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="51a0a-150">`Get-BlockedSenderAddress`: Run to retreive the list of users that are restricted from sending email</span></span>
- <span data-ttu-id="51a0a-151">`Remove-BlockedSenderAddress`: を実行して、制限されていないユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="51a0a-151">`Remove-BlockedSenderAddress`: Run to remove user(s) from being restricted</span></span>

## <a name="for-more-information"></a><span data-ttu-id="51a0a-152">関連情報</span><span class="sxs-lookup"><span data-stu-id="51a0a-152">For more information</span></span>

[<span data-ttu-id="51a0a-153">侵害された電子メールアカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="51a0a-153">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="51a0a-154">ユーザーがメール通知の送信を制限していることを理解する</span><span class="sxs-lookup"><span data-stu-id="51a0a-154">Understanding the User restricted from sending email alert</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[<span data-ttu-id="51a0a-155">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="51a0a-155">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="51a0a-156">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="51a0a-156">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

[<span data-ttu-id="51a0a-157">セキュリティ & コンプライアンスセンターのアラートポリシー</span><span class="sxs-lookup"><span data-stu-id="51a0a-157">Alert policies in the Security & Compliance Center</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)
