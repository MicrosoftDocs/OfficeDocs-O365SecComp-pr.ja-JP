---
title: Office 365 で配信された悪意のある電子メールを検索して調査する
keywords: TIMailData-インライン、セキュリティインシデント、インシデント、ATP PowerShell、電子メールマルウェア、侵害されたユーザー、電子メールフィッシング、電子メールマルウェア、電子メールヘッダーの読み取り、ヘッダーの読み取り、電子メールのヘッダーを開く
ms.author: deniseb
author: denisebmsft
manager: dansimp
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
ms.openlocfilehash: a57e72c74a7b2f819ecee7fbf604795e4a094693
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761683"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="eaf02-104">Office 365 で配信された悪意のある電子メールを検索して調査する</span><span class="sxs-lookup"><span data-stu-id="eaf02-104">Find and investigate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="eaf02-105">[Office 365 Advanced Threat Protection](office-365-atp.md)を使用すると、組織内のユーザーにリスクがあるというアクティビティを調査し、組織を保護するための処置を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-105">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="eaf02-106">たとえば、組織のセキュリティチームに属している場合は、配信された不審な電子メールメッセージを見つけて調査することができます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="eaf02-107">これを行うには、[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="eaf02-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="eaf02-108">Before you begin...</span></span>

<span data-ttu-id="eaf02-109">次の要件が満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eaf02-109">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="eaf02-110">組織では、 [Office 365 Advanced Threat Protection](office-365-atp.md)と[ライセンスがユーザーに割り当てら](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)れています。</span><span class="sxs-lookup"><span data-stu-id="eaf02-110">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="eaf02-111">[Office 365 監査ログ](turn-audit-log-search-on-or-off.md)は、組織に対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="eaf02-111">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="eaf02-112">組織には、スパム対策、マルウェア対策、フィッシング対策などに対して定義されたポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-112">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="eaf02-113">「 [Office 365 の脅威から保護](protect-against-threats.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf02-113">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="eaf02-114">Office 365 の全体管理者であるか、セキュリティ管理者、またはセキュリティ&amp;コンプライアンスセンターで割り当てられている検索および削除の役割を持っているかどうか。</span><span class="sxs-lookup"><span data-stu-id="eaf02-114">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="eaf02-115">「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可」を](permissions-in-the-security-and-compliance-center.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf02-115">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="eaf02-116">操作によっては、新しいプレビューの役割が割り当てられている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-116">For some actions, you must also have a new Preview role assigned.</span></span> 

#### <a name="preview-role-permissions"></a><span data-ttu-id="eaf02-117">ロールの権限のプレビュー</span><span class="sxs-lookup"><span data-stu-id="eaf02-117">Preview role permissions</span></span>

<span data-ttu-id="eaf02-118">メッセージヘッダーを表示したり、メールメッセージの内容をダウンロードしたりするなど、特定の操作を実行するには、別の適切な Office 365 役割グループに*プレビュー*が追加された新しい役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-118">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate Office 365 role group.</span></span> <span data-ttu-id="eaf02-119">次の表で、必要な役割とアクセス許可を明確にします。</span><span class="sxs-lookup"><span data-stu-id="eaf02-119">The following table clarifies required roles and permissions.</span></span>

|<span data-ttu-id="eaf02-120">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="eaf02-120">Activity</span></span>  |<span data-ttu-id="eaf02-121">役割グループ</span><span class="sxs-lookup"><span data-stu-id="eaf02-121">Role group</span></span> |<span data-ttu-id="eaf02-122">必要なプレビューの役割</span><span class="sxs-lookup"><span data-stu-id="eaf02-122">Preview role needed?</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="eaf02-123">脅威エクスプローラー (およびリアルタイム検出) を使用して脅威を分析する</span><span class="sxs-lookup"><span data-stu-id="eaf02-123">Use Threat Explorer (and real-time detections) to analyze threats</span></span>     |<span data-ttu-id="eaf02-124">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="eaf02-124">Office 365 Global Administrator</span></span> <br> <span data-ttu-id="eaf02-125">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="eaf02-125">Security Administrator</span></span> <br> <span data-ttu-id="eaf02-126">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="eaf02-126">Security Reader</span></span>     | <span data-ttu-id="eaf02-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="eaf02-127">No</span></span>   |
|<span data-ttu-id="eaf02-128">脅威エクスプローラー (およびリアルタイム検出) を使用して、電子メールメッセージのヘッダーを表示し、検疫された電子メールメッセージをプレビューしてダウンロードする</span><span class="sxs-lookup"><span data-stu-id="eaf02-128">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>    |<span data-ttu-id="eaf02-129">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="eaf02-129">Office 365 Global Administrator</span></span> <br> <span data-ttu-id="eaf02-130">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="eaf02-130">Security Administrator</span></span> <br><span data-ttu-id="eaf02-131">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="eaf02-131">Security Reader</span></span>   |       <span data-ttu-id="eaf02-132">いいえ</span><span class="sxs-lookup"><span data-stu-id="eaf02-132">No</span></span>  |
|<span data-ttu-id="eaf02-133">脅威エクスプローラーを使用してヘッダーを表示し、メールボックスに配信された電子メールメッセージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="eaf02-133">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>     |<span data-ttu-id="eaf02-134">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="eaf02-134">Office 365 Global Administrator</span></span> <br><span data-ttu-id="eaf02-135">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="eaf02-135">Security Administrator</span></span> <br> <span data-ttu-id="eaf02-136">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="eaf02-136">Security Reader</span></span> <br> <span data-ttu-id="eaf02-137">プレビュー</span><span class="sxs-lookup"><span data-stu-id="eaf02-137">Preview</span></span>   |   <span data-ttu-id="eaf02-138">はい</span><span class="sxs-lookup"><span data-stu-id="eaf02-138">Yes</span></span>      |

> [!NOTE]
> <span data-ttu-id="eaf02-139">*プレビュー*は役割であり、役割グループではありません。Office 365 の既存の役割グループにプレビューの役割を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-139">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="eaf02-140">Office 365 のグローバル管理者の役割には、Microsoft 365 管理[https://admin.microsoft.com](https://admin.microsoft.com)センター () が割り当てられており、セキュリティ管理者およびセキュリティリーダーの役割が Office 365[https://protection.office.com](https://protection.office.com)Security & コンプライアンスセンター () に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-140">The Office 365 Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="eaf02-141">役割とアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf02-141">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="eaf02-142">配信された疑わしいメールを見つけて削除する</span><span class="sxs-lookup"><span data-stu-id="eaf02-142">Find and delete suspicious email that was delivered</span></span>

<span data-ttu-id="eaf02-143">脅威エクスプローラーは、メッセージの検索と削除、悪意のある電子メールの送信者の IP アドレスの識別、さらなる調査のためのインシデントの開始など、複数の目的に使用できる強力なレポートです。</span><span class="sxs-lookup"><span data-stu-id="eaf02-143">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="eaf02-144">次の手順では、エクスプローラーを使用して受信者のメールボックスから悪意のある電子メールを検索し、削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-144">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span>

1. <span data-ttu-id="eaf02-145">に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="eaf02-145">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="eaf02-146">これにより、セキュリティ&amp;コンプライアンスセンターに移動します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-146">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="eaf02-147">左側のナビゲーションで、[**脅威管理** \> **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-147">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>

    ![配信アクションと配信場所フィールドを含むエクスプローラ。](media/ThreatExFields.PNG)

    <span data-ttu-id="eaf02-149">[**特別なアクション**] 列が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-149">You may notice the new **Special actions** column.</span></span> <span data-ttu-id="eaf02-150">この機能は、管理者に電子メールの処理の結果を伝えることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="eaf02-150">This feature is aimed at telling admins the outcome of processing an email.</span></span> <span data-ttu-id="eaf02-151">[**特別なアクション**] 列には、**配信アクション**と**配信場所**と同じ場所でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-151">The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**.</span></span> <span data-ttu-id="eaf02-152">脅威エクスプローラの電子メールのタイムラインの最後に特別なアクションが更新されることがあります。これは、管理者にとって、探しやすさを向上させるための新機能です。</span><span class="sxs-lookup"><span data-stu-id="eaf02-152">Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.</span></span>

3. <span data-ttu-id="eaf02-153">電子メールのタイムラインを表示するには、電子メールメッセージの件名をクリックし、[**電子メールのタイムライン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eaf02-153">To view an email timeline, click on the subject of an email message, and then click **Email timeline**.</span></span> <span data-ttu-id="eaf02-154">(**概要**や**詳細**など、パネル上の他の見出しの中に表示されます)。</span><span class="sxs-lookup"><span data-stu-id="eaf02-154">(It appears among other headings on the panel like **Summary** or **Details**.)</span></span>

    <span data-ttu-id="eaf02-155">電子メールのタイムラインを開くと、そのメールの配信後イベントを示す表が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-155">Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail.</span></span> <span data-ttu-id="eaf02-156">その他のイベントが電子メールに追加されていない場合は、元の配信に対して1つのイベントが表示されます。これは、**フィッシング**のように verdict によって**ブロック**されているように見えます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-156">In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**.</span></span> <span data-ttu-id="eaf02-157">このタブには、電子メールのタイムライン全体をエクスポートするオプションもあります。これにより、タブ上のすべての詳細と、電子メールの詳細 (件名、送信者、受信者、ネットワーク、およびメッセージ ID など) がエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-157">The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).</span></span>

    <span data-ttu-id="eaf02-158">メールが到着した後に発生したイベントを理解するために、さまざまな場所をチェックするのにかかる時間が短くなるため、電子メールのタイムラインはランダム化されます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-158">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="eaf02-159">複数のイベントが電子メールで同時に発生するか、または同じ時刻になると、それらのイベントはタイムラインビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-159">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span> 
    
    <span data-ttu-id="eaf02-160">メールへのポスト配信が発生する一部のイベントは、[**特殊なアクション**] 列に記録されます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-160">Some events that happen post-delivery to your mail are captured in the **Special actions** column.</span></span> <span data-ttu-id="eaf02-161">電子メールのタイムラインの情報と、電子メールの送信後の特別なアクションを組み合わせることにより、管理者は、ポリシーの動作、電子メールが最終的にルーティングされた場所、場合によっては最終的な評価がどのようなものであるかを把握できます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-161">Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was.</span></span> 

4. <span data-ttu-id="eaf02-162">[**表示**] メニューの [**すべての電子メール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eaf02-162">In the **View** menu, choose **All email**.</span></span>

    ![[表示] メニューを使用して電子メールとコンテンツレポートを選択する](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    <span data-ttu-id="eaf02-164">レポートに表示されるラベル (**配信**済み、**不明**、**迷惑メール**など) に注目してください。</span><span class="sxs-lookup"><span data-stu-id="eaf02-164">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span>

    ![すべての電子メールのデータが表示されている脅威エクスプローラー](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    <span data-ttu-id="eaf02-166">(組織の電子メールメッセージに対して実行されたアクションによっては、**ブロック**や**置換**などの他のラベルが表示されることがあります)。</span><span class="sxs-lookup"><span data-stu-id="eaf02-166">(Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)</span></span>
    
6. <span data-ttu-id="eaf02-167">レポートで、[**配信**済み] を選択すると、ユーザーの受信トレイで終了した電子メールメッセージのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-167">In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.</span></span>

    ![[迷惑メールに配信済み] をクリックすると、そのデータがビューから削除されます。](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
7. <span data-ttu-id="eaf02-169">グラフの下にある、グラフの下にある**電子メール**リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-169">Below the chart, review the **Email** list below the chart.</span></span>

    ![グラフの下に、検出された電子メールメッセージの一覧を表示します。](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
8. <span data-ttu-id="eaf02-171">リストで、その電子メールメッセージの詳細を表示するアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-171">In the list, choose an item to view more details about that email message.</span></span> <span data-ttu-id="eaf02-172">たとえば、件名行をクリックして、送信者、受信者、添付ファイル、その他の同様の電子メールメッセージに関する情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-172">For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span>

    ![アイテムに関する追加情報を表示することができます。](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
9. <span data-ttu-id="eaf02-174">電子メールメッセージに関する情報を表示した後、リスト内の1つ以上のアイテムを選択して、 **+ アクション**をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-174">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
10. <span data-ttu-id="eaf02-175">[ **+ アクション**] リストを使用して、[**削除済みアイテムに移動する**] などのアクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-175">Use the **+ Actions** list to apply an action, such as **Move to deleted** items.</span></span> <span data-ttu-id="eaf02-176">これにより、選択したメッセージが受信者のメールボックスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-176">This deletes the selected messages from the recipients' mailboxes.</span></span>

    ![1つまたは複数の電子メールメッセージを選択する場合は、いくつかの使用可能なアクションから選択できます。](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## <a name="dealing-with-suspicious-email-messages"></a><span data-ttu-id="eaf02-178">疑わしい電子メールメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="eaf02-178">Dealing with suspicious email messages</span></span>

<span data-ttu-id="eaf02-179">悪意のある攻撃者は、組織内のユーザーにメールを送信しようとして、資格情報をフィッシングし、会社の機密情報にアクセスできる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-179">Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets.</span></span> <span data-ttu-id="eaf02-180">これを防止するために、 [Exchange Online protection](eop/exchange-online-protection-overview.md)や[Advanced threat Protection](office-365-atp.md)などの Office 365 の脅威保護サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-180">To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](eop/exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="eaf02-181">ただし、後で悪意のあるコンテンツ (マルウェアなど) を指すリンク (URL) を含む電子メールを攻撃者が送信することもあります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-181">However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware).</span></span> <span data-ttu-id="eaf02-182">または、組織内のユーザーが侵害されていて、危険にさらされている間に、攻撃者が自分のアカウントを使用して組織内の他のユーザーに電子メールを送信したことを認識することもあります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-182">Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization.</span></span> <span data-ttu-id="eaf02-183">これらのシナリオの処理の一部として、不審な電子メールメッセージをユーザーの受信トレイから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-183">As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes.</span></span> <span data-ttu-id="eaf02-184">そのためには、[脅威エクスプローラー](threat-explorer.md)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-184">To do that, you can use [Threat Explorer](threat-explorer.md).</span></span>

## <a name="finding-re-routed-email-messages-after-actions-are-taken"></a><span data-ttu-id="eaf02-185">操作の実行後に再ルーティングされた電子メールメッセージの検出</span><span class="sxs-lookup"><span data-stu-id="eaf02-185">Finding re-routed email messages after actions are taken</span></span>

<span data-ttu-id="eaf02-186">脅威エクスプローラーでは、セキュリティ運用チームに、疑わしい電子メールを調査するために必要な詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-186">Threat Explorer provides your security operations team with the details they need to investigate suspicious email.</span></span> <span data-ttu-id="eaf02-187">セキュリティ運用チームは、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-187">Your security operations team can:</span></span>

- [<span data-ttu-id="eaf02-188">電子メールのヘッダーを表示し、電子メールの本文をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="eaf02-188">View the email headers and download the email body</span></span>](#view-the-email-headers-and-download-the-email-body) 

- [<span data-ttu-id="eaf02-189">配信アクションと場所を確認する</span><span class="sxs-lookup"><span data-stu-id="eaf02-189">Check the delivery action and location</span></span>](#check-the-delivery-action-and-location)

- [<span data-ttu-id="eaf02-190">メールのタイムラインを表示する</span><span class="sxs-lookup"><span data-stu-id="eaf02-190">View the timeline of your email</span></span>](#view-the-timeline-of-your-email)

### <a name="view-the-email-headers-and-download-the-email-body"></a><span data-ttu-id="eaf02-191">電子メールのヘッダーを表示し、電子メールの本文をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="eaf02-191">View the email headers and download the email body</span></span>

<span data-ttu-id="eaf02-192">電子メールのヘッダーをプレビューし、電子メール本文の本文をダウンロードする機能は、脅威エクスプローラの強力な機能です。</span><span class="sxs-lookup"><span data-stu-id="eaf02-192">The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer.</span></span> <span data-ttu-id="eaf02-193">適切な[アクセス許可](permissions-in-the-security-and-compliance-center.md)を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-193">Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned.</span></span> <span data-ttu-id="eaf02-194">「[役割の権限のプレビュー](#preview-role-permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf02-194">See [Preview role permissions](#preview-role-permissions).</span></span>

<span data-ttu-id="eaf02-195">メッセージヘッダーと電子メールのダウンロードオプションにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-195">To access your message header and email download options, follow these steps:</span></span> 

1. <span data-ttu-id="eaf02-196">に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="eaf02-196">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="eaf02-197">これにより、セキュリティ&amp;コンプライアンスセンターに移動します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-197">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="eaf02-198">左側のナビゲーションで、[**脅威管理** \> **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-198">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>

3. <span data-ttu-id="eaf02-199">脅威エクスプローラの表で、件名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eaf02-199">Click on a subject in the Threat Explorer table.</span></span> 

    <span data-ttu-id="eaf02-200">これにより、ヘッダープレビューと電子メールダウンロードリンクの両方が配置されたフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-200">This opens the flyout, where both header preview and email download links are positioned.</span></span>

    ![ページ上のダウンロードおよびプレビューリンクを含む脅威エクスプローラのポップアップ。](media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> <span data-ttu-id="eaf02-202">この機能は、ユーザーのメールボックスに存在しない電子メールメッセージには表示されません。これは、電子メールがドロップされた場合や配信に失敗した場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-202">This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed.</span></span> <span data-ttu-id="eaf02-203">電子メールメッセージがユーザーのメールボックスから削除された場合、管理者は "メールが見つかりません" というエラーメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="eaf02-203">In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.</span></span>

### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="eaf02-204">配信アクションと場所を確認する</span><span class="sxs-lookup"><span data-stu-id="eaf02-204">Check the delivery action and location</span></span>

<span data-ttu-id="eaf02-205">[脅威エクスプローラー (およびリアルタイムの検出)](threat-explorer.md)で、[前の**配信状態**] 列ではなく、**配信アクション**と**配信場所**の列が作成されました。</span><span class="sxs-lookup"><span data-stu-id="eaf02-205">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="eaf02-206">この結果、電子メールメッセージがどこにあるかをより完全に把握できます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-206">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="eaf02-207">この変更の目的の1つは、検索を簡単に実行することですが、最終的には問題の電子メールメッセージの場所がひとめでわかることになります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-207">Part of the goal of this change is to make hunting easier for security operations, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="eaf02-208">配信状態は、次の2つの列に分けられました。</span><span class="sxs-lookup"><span data-stu-id="eaf02-208">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="eaf02-209">**配信アクション**-この電子メールの状態は何ですか。</span><span class="sxs-lookup"><span data-stu-id="eaf02-209">**Delivery action** - What is the status of this email?</span></span>

- <span data-ttu-id="eaf02-210">**配信場所**-この電子メールは、結果としてルーティングされましたか?</span><span class="sxs-lookup"><span data-stu-id="eaf02-210">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="eaf02-211">配信アクションは、既存のポリシーまたは検出のために電子メールに対して実行されたアクションです。</span><span class="sxs-lookup"><span data-stu-id="eaf02-211">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="eaf02-212">電子メールで実行可能なアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="eaf02-212">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="eaf02-213">**配信**済み–電子メールはユーザーの受信トレイまたはフォルダーに配信され、ユーザーは直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-213">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

- <span data-ttu-id="eaf02-214">**Junked** –電子メールがユーザーの迷惑フォルダーまたは削除されたフォルダーに送信され、ユーザーは迷惑メールまたは削除されたフォルダー内の電子メールメッセージにアクセスできる。</span><span class="sxs-lookup"><span data-stu-id="eaf02-214">**Junked** – email was sent to either user’s junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

- <span data-ttu-id="eaf02-215">[**ブロック**済み]: 検疫された、失敗した、または削除された電子メールメッセージ。</span><span class="sxs-lookup"><span data-stu-id="eaf02-215">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="eaf02-216">(ユーザーが完全にアクセスすることはできません。)</span><span class="sxs-lookup"><span data-stu-id="eaf02-216">(This is completely inaccessible by the user.)</span></span>

- <span data-ttu-id="eaf02-217">[**置換**] –悪意のある添付ファイルが、添付ファイルが悪意のあるファイルに置き換えられた場合の電子メール。</span><span class="sxs-lookup"><span data-stu-id="eaf02-217">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
<span data-ttu-id="eaf02-218">[配信場所] には、配信後に実行されるポリシーと検出の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-218">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="eaf02-219">配信アクションにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="eaf02-219">It's linked to a Delivery Action.</span></span> <span data-ttu-id="eaf02-220">このフィールドは、問題のメールが検出されたときに実行される処理を把握するために追加されました。</span><span class="sxs-lookup"><span data-stu-id="eaf02-220">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="eaf02-221">配信場所の指定可能な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="eaf02-221">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="eaf02-222">**受信トレイまたはフォルダー** –メールが受信トレイまたはフォルダーにある (メールルールに従って)。</span><span class="sxs-lookup"><span data-stu-id="eaf02-222">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

- <span data-ttu-id="eaf02-223">**オンプレミスまたは外部**–メールボックスがクラウド上に存在していますが、オンプレミスになっています。</span><span class="sxs-lookup"><span data-stu-id="eaf02-223">**On-prem or external** – The mailbox doesn’t exist on cloud but is on-premises.</span></span>

- <span data-ttu-id="eaf02-224">**迷惑メールフォルダー** –電子メールはユーザーの迷惑メールフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-224">**Junk folder** – The email is in a user's Junk folder.</span></span>

- <span data-ttu-id="eaf02-225">**削除済みアイテムフォルダー** –電子メールはユーザーの [削除済みアイテム] フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="eaf02-225">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

- <span data-ttu-id="eaf02-226">**検疫**–検疫内の電子メール。ユーザーのメールボックスには含まれません。</span><span class="sxs-lookup"><span data-stu-id="eaf02-226">**Quarantine** – The email in quarantine, and not in a user’s mailbox.</span></span>

- <span data-ttu-id="eaf02-227">**Failed** –メールがメールボックスに到達できませんでした。</span><span class="sxs-lookup"><span data-stu-id="eaf02-227">**Failed** – The email failed to reach the mailbox.</span></span>

- <span data-ttu-id="eaf02-228">**削除**–メールフロー内の任意の場所に電子メールが失われます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-228">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="eaf02-229">メールのタイムラインを表示する</span><span class="sxs-lookup"><span data-stu-id="eaf02-229">View the timeline of your email</span></span>
  
<span data-ttu-id="eaf02-230">**電子メールタイムライン**は、セキュリティ運用チームにとって使いやすいようにするための脅威エクスプローラーのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="eaf02-230">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="eaf02-231">電子メールで複数のイベントが同時に発生するか、または同じ時刻に近いときに、これらのイベントがタイムラインビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-231">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="eaf02-232">電子メールへの配信後に発生する一部のイベントは、[**特殊なアクション**] 列に記録されます。</span><span class="sxs-lookup"><span data-stu-id="eaf02-232">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="eaf02-233">メールメッセージのタイムラインからの情報と、配信後に実行された特別な操作によって、管理者はポリシーと脅威の処理についての洞察を得ることができます (メールがルーティングされた場所や、場合によっては最終的な評価は何かなど)。</span><span class="sxs-lookup"><span data-stu-id="eaf02-233">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="eaf02-234">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaf02-234">Related topics</span></span>

[<span data-ttu-id="eaf02-235">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="eaf02-235">Office 365 Advanced Threat Protection</span></span>](office-365-ti.md)
  
[<span data-ttu-id="eaf02-236">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="eaf02-236">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="eaf02-237">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="eaf02-237">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

