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
ms.openlocfilehash: 7e2cef742339e54c094cfb0c3b32fbf596896a3d
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408302"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a><span data-ttu-id="ae7cc-103">配信された悪意のある電子メールを検索して調査する (Office 365 Advanced Threat Protection プラン 2)</span><span class="sxs-lookup"><span data-stu-id="ae7cc-103">Find and investigate malicious email that was delivered (Office 365 Advanced Threat Protection Plan 2)</span></span>

<span data-ttu-id="ae7cc-104">[Office 365 Advanced Threat Protection](office-365-atp.md)を使用すると、ユーザーが危険にさらされ、組織を保護するアクションを実行するアクティビティを調査できます。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-104">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put your users at risk and take action to protect your organization.</span></span> <span data-ttu-id="ae7cc-105">たとえば、組織のセキュリティチームに属している場合は、ユーザーに配信された不審な電子メールメッセージを見つけて調査することができます。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-105">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users.</span></span> <span data-ttu-id="ae7cc-106">これを行うには、[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-106">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="ae7cc-107">開始する前に</span><span class="sxs-lookup"><span data-stu-id="ae7cc-107">Before you begin...</span></span>

<span data-ttu-id="ae7cc-108">次の要件が満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-108">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="ae7cc-109">組織に[Office 365 Advanced Threat Protection](office-365-atp.md) (プラン1またはプラン 2) があり、[ライセンスがユーザーに割り当てら](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)れている。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-109">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Plan 1 or Plan 2) and [licenses are assigned to users](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="ae7cc-110">[Office 365 監査ログ](turn-audit-log-search-on-or-off.md)は、組織に対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-110">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="ae7cc-111">組織には、スパム対策、マルウェア対策、フィッシング対策などに対して定義されたポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-111">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="ae7cc-112">「 [Office 365 の脅威から保護](protect-against-threats.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-112">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="ae7cc-113">Office 365 の全体管理者であるか、セキュリティ管理者、またはセキュリティ&amp;コンプライアンスセンターで割り当てられている検索および削除の役割を持っているかどうか。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-113">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="ae7cc-114">「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可」を](permissions-in-the-security-and-compliance-center.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-114">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="ae7cc-115">疑わしいメールの処理</span><span class="sxs-lookup"><span data-stu-id="ae7cc-115">Dealing with suspicious emails</span></span>

<span data-ttu-id="ae7cc-116">悪意のある攻撃者は、ユーザーにメールを送信して、自分の資格情報をフィッシングし、会社の機密情報にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-116">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets!</span></span> <span data-ttu-id="ae7cc-117">これを防止するには、Office 365 で提供されている脅威保護サービス ( [Exchange Online protection](eop/exchange-online-protection-overview.md)や[Advanced threat protection](office-365-atp.md)など) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-117">In order to prevent this, you should use the threat protection services offered by Office 365, including [Exchange Online Protection](eop/exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="ae7cc-118">ただし、攻撃者が URL を含むユーザーにメールを送信し、その URL を後で悪意のあるコンテンツ (マルウェアなど) に対して使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-118">However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.).</span></span> <span data-ttu-id="ae7cc-119">または、組織内のユーザーが侵害され、そのユーザーが侵害されたときに、そのアカウントを使用して社内の他のユーザーに電子メールを送信したことがあります。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-119">Alternatively, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company.</span></span> <span data-ttu-id="ae7cc-120">これらのシナリオの両方をクリーンアップする際に、ユーザーの受信トレイから電子メールメッセージを削除することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-120">As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes.</span></span> <span data-ttu-id="ae7cc-121">このような状況では、[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)を活用して、それらの電子メールメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-121">In situations like these, you can leverage [Threat Explorer (or real-time detections)](threat-explorer.md) to find and remove those email messages!</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="ae7cc-122">配信された疑わしいメールを見つけて削除する</span><span class="sxs-lookup"><span data-stu-id="ae7cc-122">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="ae7cc-123">脅威エクスプローラー (エクスプローラーとも呼ばれます) は、メッセージの検索と削除、悪意のある電子メールの送信者の IP アドレスの識別、さらなる調査のためのインシデントの開始など、複数の目的で利用できる強力なレポートです。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-123">Threat Explorer (also referred to as Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="ae7cc-124">次の手順では、エクスプローラーを使用して受信者のメールボックスから悪意のある電子メールを検索し、削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-124">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span> 
  
1. <span data-ttu-id="ae7cc-125">に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="ae7cc-126">これにより、セキュリティ&amp;コンプライアンスセンターに移動します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-126">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="ae7cc-127">左側のナビゲーションで、[**脅威管理** \> **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-127">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>
    
3. <span data-ttu-id="ae7cc-128">[表示] メニューの [**すべての電子メール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-128">In the View menu, choose **All email**.</span></span><br/><span data-ttu-id="ae7cc-129">![[表示] メニューを使用して電子メールとコンテンツレポートを選択する](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span><span class="sxs-lookup"><span data-stu-id="ae7cc-129">![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span></span>
  
4. <span data-ttu-id="ae7cc-130">レポートに表示されるラベル (**配信**済み、**不明**、**迷惑メール**など) に注目してください。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-130">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span><br/><span data-ttu-id="ae7cc-131">![すべての電子メールのデータが表示されている脅威エクスプローラー](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span><span class="sxs-lookup"><span data-stu-id="ae7cc-131">![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span></span><br/><span data-ttu-id="ae7cc-132">(組織の電子メールメッセージに対して実行されたアクションによっては、**ブロック**されたり**置き換えら**れたりするなど、他のラベルが表示される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-132">(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)</span></span>
    
5. <span data-ttu-id="ae7cc-133">レポートで、[**配信**済み] を選択して、ユーザーの受信トレイに終了した電子メールのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-133">In the report, choose **Delivered** to view only emails that ended up in users' inboxes.</span></span><br/><span data-ttu-id="ae7cc-134">![[迷惑メールに配信済み] をクリックすると、そのデータがビューから削除されます。](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span><span class="sxs-lookup"><span data-stu-id="ae7cc-134">![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span></span>
  
6. <span data-ttu-id="ae7cc-135">グラフの下にある、グラフの下にある**電子メール**リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-135">Below the chart, review the **Email** list below the chart.</span></span><br/><span data-ttu-id="ae7cc-136">![グラフの下に、検出された電子メールメッセージの一覧を表示します。](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span><span class="sxs-lookup"><span data-stu-id="ae7cc-136">![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span></span>
  
7. <span data-ttu-id="ae7cc-137">リストで、その電子メールメッセージの詳細を表示するアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-137">In the list, choose an item to view more details about that email message.</span></span> <span data-ttu-id="ae7cc-138">たとえば、件名行をクリックして、送信者、受信者、添付ファイル、その他の同様の電子メールメッセージに関する情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-138">For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span><br/>![詳細および添付ファイルを含む、アイテムに関する追加情報を表示できます。](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. <span data-ttu-id="ae7cc-140">電子メールメッセージに関する情報を表示した後、リスト内の1つ以上のアイテムを選択して、 **+ アクション**をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-140">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
9. <span data-ttu-id="ae7cc-141">[ **+ アクション**] リストを使用して、[**削除済みアイテムに移動する**] などのアクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-141">Use the **+ Actions** list to apply an action, such as **Move to deleted** items.</span></span> <span data-ttu-id="ae7cc-142">これにより、選択したメッセージが受信者のメールボックスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ae7cc-142">This will delete the selected messages from the recipients' mailboxes.</span></span><br/><span data-ttu-id="ae7cc-143">![1つまたは複数の電子メールメッセージを選択する場合は、いくつかの使用可能なアクションから選択できます。](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span><span class="sxs-lookup"><span data-stu-id="ae7cc-143">![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ae7cc-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae7cc-144">Related topics</span></span>

[<span data-ttu-id="ae7cc-145">Office 365 Advanced Threat Protection プラン2</span><span class="sxs-lookup"><span data-stu-id="ae7cc-145">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="ae7cc-146">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="ae7cc-146">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="ae7cc-147">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="ae7cc-147">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

