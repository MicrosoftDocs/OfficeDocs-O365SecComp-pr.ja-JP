---
title: 配信された悪意のある電子メールを検索して調査する (Office 365 の脅威の調査と応答
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 脅威の調査と応答機能を使用して、悪意のある電子メールを検索して調査する方法について説明します。
ms.openlocfilehash: 5f8c615bed07b75cd3c06ec48f5ba73586f0f6d5
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394292"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a><span data-ttu-id="9fc2e-103">配信された悪意のある電子メールを検索して調査する (Office 365 Advanced Threat Protection プラン 2)</span><span class="sxs-lookup"><span data-stu-id="9fc2e-103">Find and investigate malicious email that was delivered (Office 365 Advanced Threat Protection Plan 2)</span></span>

<span data-ttu-id="9fc2e-104">[Office 365 Advanced Threat Protection](office-365-atp.md)を使用すると、ユーザーが危険にさらされ、組織を保護するアクションを実行するアクティビティを調査できます。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-104">[Office 365 Advanced Threat Protection](office-365-atp.md) lets you to investigate activities that put your users at risk and take action to protect your organization.</span></span> <span data-ttu-id="9fc2e-105">たとえば、組織のセキュリティチームに属している場合は、ユーザーに配信された不審な電子メールメッセージを見つけて調査することができます。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-105">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users.</span></span> <span data-ttu-id="9fc2e-106">これを行うには、[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-106">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="9fc2e-107">開始する前に</span><span class="sxs-lookup"><span data-stu-id="9fc2e-107">Before you begin...</span></span>

<span data-ttu-id="9fc2e-108">次の要件が満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-108">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="9fc2e-109">組織に[Office 365 Advanced Threat Protection](office-365-atp.md) (プラン1またはプラン 2) があり、[ライセンスがユーザーに割り当てら](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)れている。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-109">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Plan 1 or Plan 2) and [licenses are assigned to users](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="9fc2e-110">[Office 365 監査ログ](turn-audit-log-search-on-or-off.md)は、組織に対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-110">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="9fc2e-111">組織には、スパム対策、マルウェア対策、フィッシング対策などに対して定義されたポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-111">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="9fc2e-112">「 [Office 365 の脅威から保護](protect-against-threats.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-112">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="9fc2e-113">Office 365 の全体管理者であるか、セキュリティ管理者、またはセキュリティ&amp;コンプライアンスセンターで割り当てられている検索および削除の役割を持っているかどうか。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-113">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="9fc2e-114">「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可」を](permissions-in-the-security-and-compliance-center.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-114">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="9fc2e-115">疑わしいメールの処理</span><span class="sxs-lookup"><span data-stu-id="9fc2e-115">Dealing with suspicious emails</span></span>

<span data-ttu-id="9fc2e-116">悪意のある攻撃者は、ユーザーにメールを送信して、自分の資格情報をフィッシングし、会社の機密情報にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-116">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets!</span></span> <span data-ttu-id="9fc2e-117">これを回避するには、 [Exchange Online protection](eop/exchange-online-protection-overview.md)や[Advanced threat Protection](office-365-atp.md)などの Office 365 の脅威保護サービスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-117">To prevent this, you should use the threat protection services in Office 365, including [Exchange Online Protection](eop/exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="9fc2e-118">ただし、攻撃者が URL を含むユーザーにメールを送信し、その URL を後で悪意のあるコンテンツ (マルウェアなど) に対して使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-118">However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.).</span></span> <span data-ttu-id="9fc2e-119">または、組織内のユーザーが侵害されていて、そのユーザーが侵害されている間に、攻撃者がそのアカウントを使用して社内の他のユーザーに電子メールを送信していることにも気付きます。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-119">Alternately, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company.</span></span> <span data-ttu-id="9fc2e-120">これらのシナリオの両方をクリーンアップする際に、ユーザーの受信トレイから電子メールメッセージを削除することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-120">As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes.</span></span> <span data-ttu-id="9fc2e-121">このような状況では、[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)を活用して、それらの電子メールメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-121">In situations like these, you can leverage [Threat Explorer (or real-time detections)](threat-explorer.md) to find and remove those email messages!</span></span>

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a><span data-ttu-id="9fc2e-122">再ルーティングされたメールは、アクションの実行後に配置されます。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-122">Where re-routed emails are located after actions are taken</span></span>

<span data-ttu-id="9fc2e-123">脅威エクスプローラーのリアルタイム検出によって、配信状況の場所に [配信アクション] フィールドと [配信場所] フィールドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-123">Threat Explorer real-time detections has added the Delivery Action and Delivery Location fields in the place of Delivery Status.</span></span> <span data-ttu-id="9fc2e-124">これにより、メールがどこにあるかをより完全に把握できます。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-124">This results in a more complete picture of where your emails land.</span></span> <span data-ttu-id="9fc2e-125">この変更の目的の一環として、セキュリティを確保したユーザーを探しやすくしていますが、最終的に問題のあるメールの場所がひとめでわかることになります。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-125">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem emails at a glance.</span></span>

<span data-ttu-id="9fc2e-126">配信状態は、次の2つの列に分けられました。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-126">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="9fc2e-127">**配信アクション**-この電子メールの状態は何ですか。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-127">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="9fc2e-128">**配信場所**-この電子メールは、結果としてルーティングされましたか?</span><span class="sxs-lookup"><span data-stu-id="9fc2e-128">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="9fc2e-129">配信アクションは、既存のポリシーまたは検出のために電子メールに対して実行されたアクションです。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-129">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="9fc2e-130">電子メールで実行可能なアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-130">Here are the possible actions an email can take:</span></span>

1. <span data-ttu-id="9fc2e-131">**配信**済み–電子メールはユーザーの受信トレイまたはフォルダーに配信され、ユーザーは直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-131">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
2. <span data-ttu-id="9fc2e-132">**Junked** –電子メールがユーザーの迷惑メールフォルダーまたは削除されたフォルダーに送信され、ユーザーは迷惑メールまたは削除されたフォルダー内のメールにアクセスできる。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-132">**Junked** – email was sent to either user’s junk folder or deleted folder, and the user has access to emails in their Junk or Deleted folder.</span></span>
3. <span data-ttu-id="9fc2e-133">[**ブロック**済み] –検疫済み、失敗、または削除されたすべての電子メール。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-133">**Blocked** – any emails that's quarantined, that  failed, or was dropped.</span></span> <span data-ttu-id="9fc2e-134">ユーザーが完全にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-134">This is completely inaccessible by the user!</span></span>
4. <span data-ttu-id="9fc2e-135">[**置換**] –悪意のある添付ファイルが、添付ファイルが悪意のあるファイルに置き換えられた場合の電子メール。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-135">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
<span data-ttu-id="9fc2e-136">[配信場所] には、配信後に実行されるポリシーと検出の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-136">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="9fc2e-137">配信アクションにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-137">It's linked to a Delivery Action.</span></span> <span data-ttu-id="9fc2e-138">このフィールドは、問題のメールが検出されたときに実行される処理を把握するために追加されました。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-138">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="9fc2e-139">配信場所の指定可能な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-139">Here are the possible values of delivery location:</span></span>

1. <span data-ttu-id="9fc2e-140">**受信トレイまたはフォルダー** –電子メールは、受信トレイまたはフォルダー (メールルールに従って) にあります。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-140">**Inbox or folder** – The email is in inbox or a folder (according to your email rules).</span></span>
2. <span data-ttu-id="9fc2e-141">**オンプレミスまたは外部**–メールボックスがクラウド上に存在していますが、オンプレミスになっています。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-141">**On-prem or external** – The mailbox doesn’t exist on cloud but is on -premises.</span></span>
3. <span data-ttu-id="9fc2e-142">**[迷惑**メール] フォルダー–ユーザーの [迷惑メール] フォルダーにあるメール。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-142">**Junk folder** – The email in in the Junk folder of a user.</span></span>
4. <span data-ttu-id="9fc2e-143">**削除済みアイテムフォルダー** –ユーザーの [削除済みアイテム] フォルダー内の電子メール。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-143">**Deleted items folder** – The email in the Deleted items folder of a user.</span></span>
5. <span data-ttu-id="9fc2e-144">**検疫**–検疫内の電子メール。ユーザーのメールボックスには含まれません。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-144">**Quarantine** – The email in quarantine, and is not in a user’s mailbox.</span></span>
6. <span data-ttu-id="9fc2e-145">**Failed** –メールがメールボックスに到達できませんでした。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-145">**Failed** – The email failed to reach the mailbox.</span></span>
7. <span data-ttu-id="9fc2e-146">**削除**-電子メールはメールフローのどこかに失われます。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-146">**Dropped** – The email gets lost somewhere in the Mailflow.</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="9fc2e-147">配信された疑わしいメールを見つけて削除する</span><span class="sxs-lookup"><span data-stu-id="9fc2e-147">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="9fc2e-148">脅威エクスプローラー (エクスプローラーとも呼ばれます) は、メッセージの検索と削除、悪意のある電子メールの送信者の IP アドレスの識別、さらなる調査のためのインシデントの開始など、複数の目的で利用できる強力なレポートです。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-148">Threat Explorer (sometimes called Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="9fc2e-149">次の手順では、エクスプローラーを使用して受信者のメールボックスから悪意のある電子メールを検索し、削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-149">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span>

<span data-ttu-id="9fc2e-150">以前の配信状態フィールドへの変更を確認するには (現在、配信アクションと配信場所):</span><span class="sxs-lookup"><span data-stu-id="9fc2e-150">To see the changes to the former Delivery Status field (now Delivery Action and Delivery Location):</span></span> 

1. <span data-ttu-id="9fc2e-151">に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-151">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="9fc2e-152">これにより、セキュリティ&amp;コンプライアンスセンターに移動します。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-152">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="9fc2e-153">左側のナビゲーションで、[**脅威管理** \> **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fc2e-153">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>

![脅威エクスプローラーのスクリーンショット。](media/Threat Explorer Delivery Action and Delivery Location.PNG)

<!--Comment>
    
3. In the View menu, choose **All email**.<br/>![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.<br/>![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only emails that ended up in users' inboxes.<br/>![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.<br/>![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.<br/>![You can view additional information about an item, including details and any attachments](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.<br/>![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
-->
## <a name="related-topics"></a><span data-ttu-id="9fc2e-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fc2e-155">Related topics</span></span>

[<span data-ttu-id="9fc2e-156">Office 365 Advanced Threat Protection プラン2</span><span class="sxs-lookup"><span data-stu-id="9fc2e-156">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="9fc2e-157">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="9fc2e-157">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="9fc2e-158">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="9fc2e-158">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

