---
title: 配信された悪意のある電子メールを検索して調査する (Office 365 の脅威の調査と応答
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
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
ms.openlocfilehash: d19833a5d2acf69b79cca7e58c5796d967337c9f
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "30732250"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a><span data-ttu-id="b6505-103">配信された悪意のある電子メールを検索して調査する (Office 365 Advanced Threat Protection プラン 2)</span><span class="sxs-lookup"><span data-stu-id="b6505-103">Find and investigate malicious email that was delivered (Office 365 Advanced Threat Protection Plan 2)</span></span>

<span data-ttu-id="b6505-104">[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)を使用すると、ユーザーが危険にさらされ、組織を保護するアクションを実行するアクティビティを調査できます。</span><span class="sxs-lookup"><span data-stu-id="b6505-104">[Office 365 Advanced Threat Protection Plan 2](office-365-ti.md) enables you to investigate activities that put your users at risk and take action to protect your organization.</span></span> <span data-ttu-id="b6505-105">たとえば、組織のセキュリティチームに属している場合は、ユーザーに配信された不審な電子メールメッセージを見つけて調査することができます。</span><span class="sxs-lookup"><span data-stu-id="b6505-105">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users.</span></span> <span data-ttu-id="b6505-106">これは、[脅威エクスプローラー](get-started-with-ti.md#threat-explorer)を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b6505-106">You can do this by using [Threat Explorer](get-started-with-ti.md#threat-explorer).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b6505-107">office 365 脅威インテリジェンスは office 365 Advanced threat protection プラン2に加えて、追加の脅威保護機能と共に提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b6505-107">Office 365 Threat Intelligence is now Office 365 Advanced Threat Protection Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="b6505-108">詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6505-108">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b6505-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="b6505-109">Before you begin...</span></span>

<span data-ttu-id="b6505-110">次の要件が満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b6505-110">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="b6505-111">組織では、 [office 365 Advanced Threat Protection プラン 2](office-365-ti.md)を使用しており、 [office 365 for business のユーザーにライセンスを割り当て](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)ます。</span><span class="sxs-lookup"><span data-stu-id="b6505-111">Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md) and [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
- <span data-ttu-id="b6505-112">[Office 365 監査ログ](turn-audit-log-search-on-or-off.md)は、組織に対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b6505-112">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="b6505-113">組織には、スパム対策、マルウェア対策、フィッシング対策などに対して定義されたポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="b6505-113">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="b6505-114">「 [Office 365 Advanced Threat Protection](office-365-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6505-114">See [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="b6505-115">Office 365 の全体管理者であるか、セキュリティ管理者、またはセキュリティ&amp;コンプライアンスセンターで割り当てられている検索および削除の役割を持っているかどうか。</span><span class="sxs-lookup"><span data-stu-id="b6505-115">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="b6505-116">「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可」を](permissions-in-the-security-and-compliance-center.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6505-116">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="b6505-117">疑わしいメールの処理</span><span class="sxs-lookup"><span data-stu-id="b6505-117">Dealing with suspicious emails</span></span>

<span data-ttu-id="b6505-118">悪意のある攻撃者は、ユーザーにメールを送信して、自分の資格情報をフィッシングし、会社の機密情報にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6505-118">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets!</span></span> <span data-ttu-id="b6505-119">これを防止するには、Office 365 で提供されている脅威保護サービス (Exchange Online protection や Advanced threat protection など) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6505-119">In order to prevent this, you should use the threat protection services offered by Office 365, including Exchange Online Protection and Advanced Threat Protection.</span></span> <span data-ttu-id="b6505-120">ただし、攻撃者が url を含むユーザーにメールを送信し、その url を後で悪意のあるコンテンツ (マルウェアなど) に対して使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6505-120">However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.).</span></span> <span data-ttu-id="b6505-121">または、組織内のユーザーが侵害され、そのユーザーが侵害されたときに、そのアカウントを使用して社内の他のユーザーに電子メールを送信したことがあります。</span><span class="sxs-lookup"><span data-stu-id="b6505-121">Alternatively, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company.</span></span> <span data-ttu-id="b6505-122">これらのシナリオの両方をクリーンアップする際に、ユーザーの受信トレイから電子メールメッセージを削除することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6505-122">As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes.</span></span> <span data-ttu-id="b6505-123">このような状況では、脅威エクスプローラーを活用して、これらの電子メールメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b6505-123">In situations like these, you can leverage Threat Explorer to find and remove those email messages!</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="b6505-124">配信された疑わしいメールを見つけて削除する</span><span class="sxs-lookup"><span data-stu-id="b6505-124">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="b6505-125">[脅威エクスプローラー](get-started-with-ti.md#threat-explorer)(エクスプローラーとも呼ばれます) は、メッセージの検索と削除、悪意のある電子メールの送信者の IP アドレスの識別、さらなる調査のためのインシデントの開始など、複数の目的に使用できる強力なレポートです。</span><span class="sxs-lookup"><span data-stu-id="b6505-125">[Threat Explorer](get-started-with-ti.md#threat-explorer) (also referred to as Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="b6505-126">次の手順では、エクスプローラーを使用して受信者のメールボックスから悪意のある電子メールを検索し、削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="b6505-126">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span> 
  
1. <span data-ttu-id="b6505-127">に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="b6505-127">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="b6505-128">これにより、セキュリティ&amp;コンプライアンスセンターに移動します。</span><span class="sxs-lookup"><span data-stu-id="b6505-128">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="b6505-129">左側のナビゲーションで、[**脅威管理** \> **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6505-129">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>
    
3. <span data-ttu-id="b6505-130">[表示] メニューの [**すべての電子メール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6505-130">In the View menu, choose **All email**.</span></span><br/><span data-ttu-id="b6505-131">![[表示] メニューを使用して電子メールとコンテンツレポートを選択する](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span><span class="sxs-lookup"><span data-stu-id="b6505-131">![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span></span>
  
4. <span data-ttu-id="b6505-132">レポートに表示されるラベル (**配信**済み、**不明**、**迷惑メール**など) に注目してください。</span><span class="sxs-lookup"><span data-stu-id="b6505-132">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span><br/><span data-ttu-id="b6505-133">![すべての電子メールのデータが表示されている脅威エクスプローラー](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span><span class="sxs-lookup"><span data-stu-id="b6505-133">![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span></span><br/><span data-ttu-id="b6505-134">(組織の電子メールメッセージに対して実行されたアクションによっては、**ブロック**されたり**置き換えら**れたりするなど、他のラベルが表示される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="b6505-134">(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)</span></span>
    
5. <span data-ttu-id="b6505-135">レポートで、[**配信**済み] を選択して、ユーザーの受信トレイに終了した電子メールのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="b6505-135">In the report, choose **Delivered** to view only emails that ended up in users' inboxes.</span></span><br/><span data-ttu-id="b6505-136">![[迷惑メールに配信済み] をクリックすると、そのデータがビューから削除されます。](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span><span class="sxs-lookup"><span data-stu-id="b6505-136">![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span></span>
  
6. <span data-ttu-id="b6505-137">グラフの下にある、グラフの下にある**電子メール**リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6505-137">Below the chart, review the **Email** list below the chart.</span></span><br/><span data-ttu-id="b6505-138">![グラフの下に、検出された電子メールメッセージの一覧を表示します。](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span><span class="sxs-lookup"><span data-stu-id="b6505-138">![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span></span>
  
7. <span data-ttu-id="b6505-139">リストで、その電子メールメッセージの詳細を表示するアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6505-139">In the list, choose an item to view more details about that email message.</span></span> <span data-ttu-id="b6505-140">たとえば、件名行をクリックして、送信者、受信者、添付ファイル、その他の同様の電子メールメッセージに関する情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="b6505-140">For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span><br/>![詳細および添付ファイルを含む、アイテムに関する追加情報を表示できます。](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. <span data-ttu-id="b6505-142">電子メールメッセージに関する情報を表示した後、リスト内の1つ以上のアイテムを選択して、 **+ アクション**をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="b6505-142">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
9. <span data-ttu-id="b6505-143">[ **+ アクション**] リストを使用して、[**削除済みアイテムに移動する**] などのアクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="b6505-143">Use the **+ Actions** list to apply an action, such as **Move to deleted** items.</span></span> <span data-ttu-id="b6505-144">これにより、選択したメッセージが受信者のメールボックスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="b6505-144">This will delete the selected messages from the recipients' mailboxes.</span></span><br/><span data-ttu-id="b6505-145">![1つまたは複数の電子メールメッセージを選択する場合は、いくつかの使用可能なアクションから選択できます。](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span><span class="sxs-lookup"><span data-stu-id="b6505-145">![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b6505-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6505-146">Related topics</span></span>

[<span data-ttu-id="b6505-147">Office 365 Advanced Threat Protection プラン2</span><span class="sxs-lookup"><span data-stu-id="b6505-147">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="b6505-148">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="b6505-148">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="b6505-149">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="b6505-149">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

