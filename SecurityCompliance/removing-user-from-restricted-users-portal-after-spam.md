---
title: 迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/12/2019
ms.audience: ITPro
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
ms.openlocfilehash: 9370df691bfe30498e32115d7c77dd5cf02556f1
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692016"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="22048-103">迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="22048-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="22048-104">ユーザーが、スパムとして分類された Office 365 からの電子メールを継続的に送信する場合、送信中のメッセージの送信が制限されます。</span><span class="sxs-lookup"><span data-stu-id="22048-104">If a user continuously sends emails from Office 365 that are classified as spam, they will be restricted from sending any more messages outbound.</span></span> <span data-ttu-id="22048-105">ユーザーは、無効な送信者としてサービスに一覧表示され、次の状態を示す配信不能レポート (NDR) を受信します。</span><span class="sxs-lookup"><span data-stu-id="22048-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="22048-106">有効な送信者として認識されなかったため、メッセージを配信できませんでした。</span><span class="sxs-lookup"><span data-stu-id="22048-106">Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="22048-107">最も一般的な理由は、メールアドレスがスパムを送信している可能性があり、組織外のメッセージを送信することが許可されなくなったためです。</span><span class="sxs-lookup"><span data-stu-id="22048-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization.</span></span> <span data-ttu-id="22048-108">詳細については、メール管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="22048-108">Contact your email admin for assistance.</span></span> <span data-ttu-id="22048-109">リモートサーバーが ' 550 5.1.8 アクセスが拒否されましたが、正しくない送信送信者 ' が返されました</span><span class="sxs-lookup"><span data-stu-id="22048-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="22048-110">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="22048-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="22048-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="22048-111"></span></span>

<span data-ttu-id="22048-112">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="22048-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="22048-113">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="22048-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="22048-114">必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「スパム対策エントリ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22048-114">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="22048-115">以下の手順はリモート PowerShell 経由でも実行することができます。Get-HostedOutboundSpamFilterPolicy コマンドレットを使用して設定を確認し、 Set-HostedOutboundSpamFilterPolicy を使用して送信スパム ポリシー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="22048-115">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="22048-116">制限を解除するには、BlockedSenderAddress コマンドレットを使用して、制限されたユーザーの一覧を取得し、BlockedSenderAddress を削除します。</span><span class="sxs-lookup"><span data-stu-id="22048-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="22048-117">Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22048-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="22048-118">ブロックされた Office 365 メールアカウントの制限を削除する</span><span class="sxs-lookup"><span data-stu-id="22048-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="22048-119">このタスクは、「Office 365 Security & コンプライアンスセンター (SCC) で完了します。</span><span class="sxs-lookup"><span data-stu-id="22048-119">You complete this task in the Office 365 Security & Compliance Center (SCC).</span></span> <span data-ttu-id="22048-120">SCC の詳細について[は、「Office 365 Security & コンプライアンスセンター」を参照](go-to-the-securitycompliance-center.md)してください。</span><span class="sxs-lookup"><span data-stu-id="22048-120">[Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="22048-121">これらの機能を実行するには、**組織の管理**または**セキュリティ管理者**の役割グループに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="22048-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="22048-122">SCC の役割グループの詳細について[は、「Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可」を参照](permissions-in-the-security-and-compliance-center.md)してください。</span><span class="sxs-lookup"><span data-stu-id="22048-122">[Go to Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="22048-123">office 365 のグローバル管理者特権を持つ職場または学校のアカウントを使用して、office 365 セキュリティ/コンプライアンスセンターにサインインし、左側の一覧で [**脅威の管理**] を展開し、[**レビュー**] を選択して、[制限あり] を選択します。 **ユーザー**。</span><span class="sxs-lookup"><span data-stu-id="22048-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="22048-124">セキュリティ&amp; /コンプライアンスセンターの [制限された**ユーザー** ] ページ (以前のアクションセンター) に直接移動するには、次の URL を使用します。 >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="22048-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="22048-125">このページには、組織外へのメールの送信をブロックされているユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="22048-125">This page will contain the list of users that have been blocked from sending mail to outside of your organization.</span></span>  <span data-ttu-id="22048-126">制限を解除するユーザーを見つけ、[**ブロックの解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22048-126">Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="22048-127">フライアウトは、送信が制限されているアカウントの詳細に進みます。</span><span class="sxs-lookup"><span data-stu-id="22048-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="22048-128">アカウントが実際に侵害された場合に備えて、適切な操作を実行していることを確認するために、推奨事項を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22048-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="22048-129">完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22048-129">Click **Next** when done.</span></span>

4. <span data-ttu-id="22048-130">次の画面には、今後の侵害を防止するための推奨事項があります。</span><span class="sxs-lookup"><span data-stu-id="22048-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="22048-131">多要素認証 (MFA) を有効にし、パスワードを変更することは、優れた防衛策となります。</span><span class="sxs-lookup"><span data-stu-id="22048-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="22048-132">完了したら、[**ユーザーのブロック解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22048-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="22048-133">**[はい]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="22048-133">Click **Yes** to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="22048-134">制限が削除されるまでに最大30分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="22048-134">It may take up to 30 minutes before restrictions are removed.</span></span> 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="22048-135">この問題が発生した場合に管理者に警告を出す</span><span class="sxs-lookup"><span data-stu-id="22048-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="22048-136">また、テナント管理者は、ユーザーがその他の送信メッセージの送信を制限していることを示す警告を受信します。</span><span class="sxs-lookup"><span data-stu-id="22048-136">The tenant admins will also receive an alert stating that the user has been restricted from sending any more outbound messages.</span></span> <span data-ttu-id="22048-137">これは、すべてのテナントに対して提供され、[SCC alert policies] ページに一覧表示されます (「ユーザーがメールを送信して制限」というタイトルが付いています)。</span><span class="sxs-lookup"><span data-stu-id="22048-137">It is a default alert that is provided for all tenants and is listed in the SCC Alert policies page, titled "User restricted from sending email".</span></span> <span data-ttu-id="22048-138">警告の詳細について[は、「Office 365 Security & コンプライアンスセンターのアラートポリシー」](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22048-138">Go to [Alert policies in the Office 365 Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies) for more information on the alert.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="22048-139">関連情報</span><span class="sxs-lookup"><span data-stu-id="22048-139">For more information</span></span>

[<span data-ttu-id="22048-140">侵害された電子メールアカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="22048-140">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="22048-141">ユーザーがメール通知の送信を制限していることを理解する</span><span class="sxs-lookup"><span data-stu-id="22048-141">Understanding the User restricted from sending email alert</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[<span data-ttu-id="22048-142">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="22048-142">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="22048-143">Office 365 Security & コンプライアンスセンターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="22048-143">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
