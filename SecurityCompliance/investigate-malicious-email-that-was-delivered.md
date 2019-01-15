---
title: 検索し、(Office 365 の脅威インテリジェンス) に配信された悪意のある電子メールを調査
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/6/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
description: 脅威インテリジェンスを使用して検出し、悪意のある電子メールを調査する方法について説明します。
ms.openlocfilehash: b6d4f8a5d1fcfce4461b91796b1264f94d1eb4d1
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014919"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-threat-intelligence"></a><span data-ttu-id="4d602-103">検索し、(Office 365 の脅威インテリジェンス) に配信された悪意のある電子メールを調査</span><span class="sxs-lookup"><span data-stu-id="4d602-103">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>

<span data-ttu-id="4d602-p101">[Office 365 の脅威インテリジェンス](office-365-ti.md)を使用すると、ユーザーを危険にさらされ、組織を保護するためにアクションを実行するアクティビティを調べることができます。などの組織のセキュリティ チームの一部の場合は、検索して、ユーザーに配信された不審な電子メール メッセージを調査します。[脅威のエクスプ ローラー](get-started-with-ti.md#threat-explorer)を使用してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4d602-p101">[Office 365 Threat Intelligence](office-365-ti.md) enables you to investigate activities that put your users at risk and take action to protect your organization. For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users. You can do this by using [Threat Explorer](get-started-with-ti.md#threat-explorer).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4d602-p102">脅威インテリジェンスを office 365 は、Office 365 エンタープライズ E5 に使用できます。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合、Office 365 の脅威インテリジェンスはアドオンとして購入できます。(グローバル管理者は、Office 365 管理センターを選択して**請求** \> **サブスクリプションを追加**します)。詳細についてを参照してください[Office 365 のプラットフォーム サービスの説明: Office 365 のセキュリティ&amp;コンプライアンス センター](https://technet.microsoft.com/en-us/library/dn933793.aspx) [購入またはビジネスのための Office 365 のアドオンを編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)するとします。</span><span class="sxs-lookup"><span data-stu-id="4d602-p102">Office 365 Threat Intelligence is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Threat Intelligence can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="4d602-110">始める前にしています.</span><span class="sxs-lookup"><span data-stu-id="4d602-110">Before you begin...</span></span>

<span data-ttu-id="4d602-111">次の要件が満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4d602-111">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="4d602-112">組織は、 [Office 365 の脅威インテリジェンス](office-365-ti.md)および[ビジネス向けの Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)には。</span><span class="sxs-lookup"><span data-stu-id="4d602-112">Your organization has [Office 365 Threat Intelligence](office-365-ti.md) and [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
- <span data-ttu-id="4d602-113">[Office 365 の監査ログ](turn-audit-log-search-on-or-off.md)有効にする組織。</span><span class="sxs-lookup"><span data-stu-id="4d602-113">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="4d602-p103">組織には、スパム対策、マルウェア対策、フィッシング対策などのために定義されているポリシーがあります。参照してください[では、Office 365 のセキュリティ管理の脅威&amp;コンプライアンス センター](threat-management.md)です。</span><span class="sxs-lookup"><span data-stu-id="4d602-p103">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on. See [Threat management in the Office 365 Security &amp; Compliance Center](threat-management.md).</span></span>
    
- <span data-ttu-id="4d602-p104">Office 365 のグローバル管理者またはセキュリティ管理者またはセキュリティに割り当てられている検索とパージのロールのいずれかがある&amp;コンプライアンス センターです。参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="4d602-p104">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="4d602-118">不審な電子メールを処理します。</span><span class="sxs-lookup"><span data-stu-id="4d602-118">Dealing with suspicious emails</span></span>

<span data-ttu-id="4d602-p105">悪意のある攻撃者は、自分の資格情報をフィッシング、しようとするユーザーにメールを送信して、企業の機密情報にアクセスできる場合があります!これを回避するためには、Exchange のオンライン保護と高度な脅威保護を含め、Office 365 が提供する脅威の保護サービスを使用してください。ただし、攻撃者は URL を含む、ユーザーにメールを送信し、(マルウェアなどの悪意のあるコンテンツを後でのみその URL のポイントを確認すると、時間があります。または、する場合があることが、組織内のユーザーが侵害された場合、その攻撃者、社内の他のユーザーに電子メールを送信するのにはそのアカウントを使用してそのユーザーが危険にさらされたときに。これらのシナリオの両方をクリーンアップの一部として、ユーザーの受信トレイから電子メール メッセージを削除する場合があります。このような場合は、脅威のエクスプ ローラーを検索し、それらの電子メール メッセージを削除するを活用することができます!</span><span class="sxs-lookup"><span data-stu-id="4d602-p105">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets! In order to prevent this, you should use the threat protection services offered by Office 365, including Exchange Online Protection and Advanced Threat Protection. However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.). Alternatively, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company. As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes. In situations like these, you can leverage Threat Explorer to find and remove those email messages!</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="4d602-125">検索し、配信された不審な電子メールを削除</span><span class="sxs-lookup"><span data-stu-id="4d602-125">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="4d602-p106">[脅威のエクスプ ローラー](get-started-with-ti.md#threat-explorer)(エクスプ ローラーとも呼ばれる) は、強力なレポートを検索する、メッセージを削除して、悪意のある電子メールの送信者の IP アドレスを識別する、またはサポート案件の詳細な調査を開始するなど、複数の目的に使用できます。次の手順では、エクスプ ローラーを使用して検索して、悪意のある電子メールを受信者のメールボックスから削除するに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="4d602-p106">[Threat Explorer](get-started-with-ti.md#threat-explorer) (also referred to as Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation. The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span> 
  
1. <span data-ttu-id="4d602-p107">[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。これで、セキュリティには、&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="4d602-p107">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="4d602-130">左側のナビゲーションでは、**脅威の管理**を選択します。 \> **エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="4d602-130">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>
    
3. <span data-ttu-id="4d602-131">[表示] メニューで、**すべての電子メール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d602-131">In the View menu, choose **All email**.</span></span><br/><span data-ttu-id="4d602-132">![[表示] メニューを使用して、e メールとコンテンツのレポートから選択するには](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span><span class="sxs-lookup"><span data-stu-id="4d602-132">![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span></span>
  
4. <span data-ttu-id="4d602-133">**配信された**、**不明な**または**迷惑メールに配信される**など、レポートに表示されるラベルが貼付されてください。</span><span class="sxs-lookup"><span data-stu-id="4d602-133">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span><br/><span data-ttu-id="4d602-134">![脅威のエクスプ ローラーがすべての電子メールのデータを表示します。](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span><span class="sxs-lookup"><span data-stu-id="4d602-134">![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span></span><br/><span data-ttu-id="4d602-135">(によって、組織の電子メール メッセージに対して実行されたアクションを**ブロック**または**Replaced**など、追加のラベルを参照可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="4d602-135">(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)</span></span>
    
5. <span data-ttu-id="4d602-136">レポートで、ユーザの受信ボックスで、最終的に e メールだけを表示するのには**出荷**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d602-136">In the report, choose **Delivered** to view only emails that ended up in users' inboxes.</span></span><br/><span data-ttu-id="4d602-137">![ビューからデータを削除する「迷惑メールを配信する」をクリックすると](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span><span class="sxs-lookup"><span data-stu-id="4d602-137">![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span></span>
  
6. <span data-ttu-id="4d602-138">、グラフの下には、グラフの下の**電子メール**リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d602-138">Below the chart, review the **Email** list below the chart.</span></span><br/><span data-ttu-id="4d602-139">![グラフの下には、検出された電子メール メッセージの一覧を表示します。](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span><span class="sxs-lookup"><span data-stu-id="4d602-139">![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span></span>
  
7. <span data-ttu-id="4d602-p108">の一覧では、その電子メール メッセージに関する詳細情報を表示する項目を選択します。たとえば、送信者、受信者、添付ファイル、およびその他の同様の電子メール メッセージに関する情報を表示するのには [件名] 行をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d602-p108">In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span><br/>![詳細、添付ファイルなどのアイテムに関する追加情報を表示することができます。](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. <span data-ttu-id="4d602-143">電子メール メッセージに関する情報を表示するには後に、、 **+ アクション**をアクティブにするのには、ボックスの一覧で 1 つまたは複数の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d602-143">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
9. <span data-ttu-id="4d602-p109">**+ アクション**のリストを使用すると、アイテムの**削除を移動する**などのアクションを適用できます。選択されたメッセージの受信者のメールボックスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="4d602-p109">Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.</span></span><br/><span data-ttu-id="4d602-146">![1 つまたは複数の電子メール メッセージを選択すると、使用可能ないくつかのアクションから選択できます。](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span><span class="sxs-lookup"><span data-stu-id="4d602-146">![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4d602-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d602-147">Related topics</span></span>

[<span data-ttu-id="4d602-148">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="4d602-148">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="4d602-149">Office 365 での脅威からの保護</span><span class="sxs-lookup"><span data-stu-id="4d602-149">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="4d602-150">Office 365 の高度な脅威保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="4d602-150">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

