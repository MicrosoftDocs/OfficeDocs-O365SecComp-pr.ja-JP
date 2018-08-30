---
title: Office 365 のセキュリティでのアクティビティの通知を作成&amp;コンプライアンス センター
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
description: 追加し、セキュリティでのアクティビティの通知を管理する&amp;ユーザーは、Office 365 で特定のアクティビティを実行するときに電子メール通知が、Office 365 を送信するためのコンプライアンス センターです。
ms.openlocfilehash: 409c1ff4c7fdd0d2d071bdb2eab08ec49357ed8a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532542"
---
# <a name="create-activity-alerts-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="22d7a-103">Office 365 のセキュリティでのアクティビティの通知を作成&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="22d7a-103">Create activity alerts in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="22d7a-p101">活動アラートを送信する電子メール通知ユーザーが Office 365 で特定のアクティビティを実行するときを作成することができます。アクティビティのアラートは、Office 365 の監査ログのイベントを検索するようなが、電子メール メッセージの通知を作成したアクティビティのイベントを送信することが行われます。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p101">You can create an activity alert that will send you an email notification when users perform specific activities in Office 365. Activity alerts are similar to searching for events in the Office 365 audit log, except that you'll be sent an email message when an event for an activity that you've created an alert for happens.</span></span> 
  
 <span data-ttu-id="22d7a-p102">**監査ログを検索する代わりにアクティビティのアラートを使用する理由ですか?** 特定の種類のアクティビティまたはアクティビティが本当に知りたい特定のユーザーによって実行される可能性があります。それらの活動の監査ログを検索するのにのではなくして、Office 365 のユーザーがそれらの活動を実行するときに、電子メール メッセージを送信するアクティビティのアラートを使用できます。たとえば、ユーザーが SharePoint でファイルを削除またはユーザーが自分のメールボックスからメッセージを完全に削除したときに通知するアラートを作成するときに通知する警告活動を作成します。電子メールに通知送信するにはには、どのアクティビティを実行し、それを実行したユーザーに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p102">**Why use activity alerts instead of searching the audit log?** There might be certain kinds of activity or activity performed by specific users that you really want to know about. Instead of having to remember to search the audit log for those activities, you can use activity alerts to have Office 365 send you an email message when users perform those activities. For example, you can create an activity alert to notify you when a user deletes files in SharePoint or you can create an alert to notify you when a user permanently deletes messages from their mailbox. The email notification sent to you includes information about which activity was performed and the user who performed it.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="22d7a-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="22d7a-111">Before you begin</span></span>

- <span data-ttu-id="22d7a-p103">セキュリティで組織の構成の役割を割り当てる必要があります&amp;アクティビティのアラートを管理するためのコンプライアンス センターです。既定では、この役割はコンプライアンス管理者および組織の管理役割グループに割り当てられます。役割グループにメンバーを追加する方法の詳細についてを参照してください[Office 365 のセキュリティにアクセスできるように&amp;コンプライアンス センター](grant-access-to-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p103">You must be assigned the Organization Configuration role in the Security &amp; Compliance Center to manage activity alerts. By default, this role is assigned to the Compliance Administrator and Organization Management role groups. For more information about adding members to role groups, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="22d7a-p104">(または別の管理者) する必要があります最初に監査ログの記録を組織のアクティビティのアラートの使用を開始する前にします。これを行うには、クリックして**ユーザーと管理者のアクティビティの記録を開始****アクティビティのアラート**] ページにします。(このリンクが表示されない場合は、監査が既に有効になって、組織の。)**監査ログの検索**] ページで、セキュリティ監査にすることも&amp;コンプライアンス センター (を参照して**検索&amp;調査** \> **監査ログの検索**)。のみこれを行う 1 回の組織があります。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p104">You (or another admin) must first turn on audit logging for your organization before you can start using activity alerts. To do this, just click **Start recording user and admin activity** on the **Activity alerts** page. (If you don't see this link, auditing has already been turned on for your organization.) You can also turn on auditing on the **Audit log search** page in the Security &amp; Compliance Center (go to **Search &amp; investigation** \> **Audit log search**). You only have to do this once for your organization.</span></span>
    
- <span data-ttu-id="22d7a-p105">**[通知**] ページを使用するには、セキュリティで&amp;、組織のアドレス帳に記載されているユーザーによって実行されたアクティビティに対してのみ警告を作成するコンプライアンス センターです。外部のユーザーによって実行されるアクティビティのアラートを作成するのには、このページを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p105">You can use the **Alerts** page in the Security &amp; Compliance Center to create alerts only for activity performed by users who are listed in your organization's address book. You can't use this page to create alerts for activity performed by external users.</span></span> 
    
- <span data-ttu-id="22d7a-121">[詳細について](#more-information)はを参照してくださいの警告を作成することができます一般的なシナリオ (特定のアクティビティを監視する) の一覧のセクションです。</span><span class="sxs-lookup"><span data-stu-id="22d7a-121">See the [More information](#more-information) section for a list of common scenarios (and the specific activity to monitor) that you can create alerts for.</span></span> 
    
- <span data-ttu-id="22d7a-122">Office 365 の監査ログを検索することができますアクティビティのアラートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="22d7a-122">You can create alerts for the same activities that you can search for in the Office 365 audit log.</span></span> 
    
## <a name="create-an-activity-alert"></a><span data-ttu-id="22d7a-123">活動通知を作成します。</span><span class="sxs-lookup"><span data-stu-id="22d7a-123">Create an activity alert</span></span>

1. <span data-ttu-id="22d7a-124">[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="22d7a-124">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="22d7a-125">職場、学校のアカウントを使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-125">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="22d7a-126">左側のウィンドウでは、**警告**をクリックし、**通知の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-126">In the left pane, click **Alerts**, and then click **Manage alerts**.</span></span>
    
4. <span data-ttu-id="22d7a-127">**アクティビティのアラート**] ページで、**アラートの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-127">On the **Activity alerts** page, click **Add an alert**.</span></span>
    
    ![活動通知を追加します。](media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
5. <span data-ttu-id="22d7a-129">警告を作成する次のフィールドを完了します。</span><span class="sxs-lookup"><span data-stu-id="22d7a-129">Complete the following fields to create an alert:</span></span>
    
    <span data-ttu-id="22d7a-p106">a.**名**には、警告の名前を入力します。警告名は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p106">a. **Name** - Type a name for the alert. Alert names must be unique within your organization.</span></span>
    
    <span data-ttu-id="22d7a-p107">b.**の説明**(オプション) の活動と、追跡されているユーザーなどのアラートの説明し、電子メール通知をユーザーに送信します。説明は、他の管理者に警告の目的を説明する簡単ですばやい方法です。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p107">b. **Description** (Optional) - Describe the alert, such as the activities and users being tracked, and the users that email notifications are sent to. Descriptions provide a quick and easy way to describe the purpose of the alert to other admins.</span></span>
    
    <span data-ttu-id="22d7a-p108">c.**この警告を送信**- をクリックして**この警告を送信**し、これら 2 つのフィールドを構成します。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p108">c. **Send this alert when** - Click **Send this alert when** and then configure these two fields:</span></span>
    
    - <span data-ttu-id="22d7a-p109">**活動**- のための警告を作成する活動を表示するドロップダウン リストを一覧表示] をクリックします。これは、Office 365 の監査ログを検索するときに表示される同じアクティビティのリストです。1 つまたは複数の特定の活動を選択することや、グループ内のすべてのアクティビティを選択するアクティビティのグループ名をクリックすることができます。これらのアクティビティについては、[監査ログが Office 365 のセキュリティとコンプライアンス ・ センターの](search-the-audit-log-in-security-and-compliance.md#audited-activities)検索「のアクティビティを監査する」セクションを参照してください。ユーザーは、いずれかのアラートに追加したアクティビティを実行するときに電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p109">**Activities** - Click the drop-down list to display the activities that you can create an alert for. This is the same activities list that's displayed when you search the Office 365 audit log. You can select one or more specific activities or you can click the activity group name to select all activities in the group. For a description of these activities, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities). When a user performs any of the activities that you've added to the alert, an email notification is sent.</span></span> 
    
     - <span data-ttu-id="22d7a-p110">**ユーザー**は、このボックスをクリックし、1 つまたは複数のユーザーを選択します。このボックス内のユーザーのアクティビティを**アクティビティ**ボックスに追加した場合、アラートが送信されます。**ユーザー**ボックスは、組織内のすべてのユーザーが警告で指定されたアクティビティを実行したときにアラートを送信するのには、空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p110">**Users** - Click this box and then select one or more users. If the users in this box perform the activities that you added to the **Activities** box, an alert will be sent. Leave the **Users** box blank to send an alert when any user in your organization performs the activities specified by the alert.</span></span> 
    
    <span data-ttu-id="22d7a-p111">**この通知を送信**- d.**この警告を送信**、] をクリックして、[**宛先**] ボックスでをクリックし、(、[**ユーザー** ] ボックスで指定された) ユーザーがアクティビティを実行すると、電子メール通知を受信するユーザーを追加する名前を入力 (で指定されている、**アクティビティ**ボックスの場合)。既定の受信者の一覧に追加されますに注意してください。この一覧から名前を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p111">d. **Send this alert to** - Click **Send this alert**, and then click in the **Recipients** box and type a name to add a users who will receive an email notification when a user (specified in the **Users** box) performs an activity (specified in the **Activities** box). Note that you are added to the list of recipients by default. You can remove your name from this list.</span></span>
    
6. <span data-ttu-id="22d7a-150">アラートを作成するのには**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-150">Click **Save** to create the alert.</span></span> 
    
    <span data-ttu-id="22d7a-151">新しい警告は、[**アクティビティのアラート**] ページで、一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="22d7a-151">The new alert is displayed in the list on the **Activity alerts** page.</span></span> 
    
    ![セキュリティでのアクティビティの通知] ページでアラートの一覧が表示されます&amp;コンプライアンス センター](media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    <span data-ttu-id="22d7a-p112">アラートの状態は、**上**に設定されます。アラートが送信されるときに電子メール通知を受信した受信者も表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p112">The status of the alert is set to **On**. Note that the recipients who will received an email notification when an alert is sent are also listed.</span></span> 
  
## <a name="turn-off-an-activity-alert"></a><span data-ttu-id="22d7a-155">活動アラートをオフにします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-155">Turn off an activity alert</span></span>

<span data-ttu-id="22d7a-p113">電子メール通知が送信されないように、アクティビティのアラートを無効にできます。アクティビティのアラートを無効にした後、組織の活動の警告の一覧に表示されたままと、そのプロパティを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p113">You can turn off an activity alert so that an email notification isn't sent. After you turn off the activity alert, it's still displayed in the list of activity alerts for your organization, and you can still view its properties.</span></span>
  
1. <span data-ttu-id="22d7a-158">[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="22d7a-158">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="22d7a-159">職場、学校のアカウントを使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-159">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="22d7a-160">左側のウィンドウでは、**警告**をクリックし、**アクティビティの通知の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-160">In the left pane, click **Alerts**, and then click **Manage activity alerts**.</span></span>
    
4. <span data-ttu-id="22d7a-161">組織の通知の一覧で、警告を無効にするをクリックします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-161">In the list of alerts for your organization, click the alert that you want to turn off.</span></span>
    
5. <span data-ttu-id="22d7a-162">[**警告の編集**] ページで**の**切り替えスイッチを [**オフ**の状態を変更する] をクリックし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-162">On the **Edit alert** page, click the **On** toggle switch to change the status to **Off**, and then click **Save**.</span></span>
    
    <span data-ttu-id="22d7a-163">アクティビティのアラート ページでアラートの状態が**無効**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="22d7a-163">The status of the alert on the Activity alerts pages is set to **Off**.</span></span> 
    
<span data-ttu-id="22d7a-164">アクティビティのアラートをオンに戻す、次の手順を繰り返し、**上**に状態を変更するのには**オフ**の切り替えスイッチをクリックします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-164">To turn an activity alert back on, just repeat these steps and click the **Off** toggle switch to change the status to **On**.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="22d7a-165">詳細情報</span><span class="sxs-lookup"><span data-stu-id="22d7a-165">More information</span></span>

- <span data-ttu-id="22d7a-166">フィールド ([**アクティビティのアラート**] ページで、**宛先**の下に表示されている) にもセキュリティにはこの警告の送信で指定されているユーザーに送信される電子メール通知の例を次のとおりです&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="22d7a-166">Here's an example of the email notification that is sent to the users that are specified in the Sent this alert to field (and listed under **Recipients** on the **Activity alerts** page ) in the Security &amp; Compliance Center.</span></span> 
    
    ![活動アラートの送信、電子メール notifcation の例](media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- <span data-ttu-id="22d7a-p114">ここでは、に関するアラートは、いくつか一般的なドキュメント、電子メール活動を活動を作成することができます。テーブルでは、アクティビティの警告を作成するアクティビティの名前とアクティビティは、**アクティビティ**」ドロップ ダウン リストに記載されている活動グループの名前について説明します。アクティビティのアラートを作成する活動の完全な一覧を表示するには、[監査ログが Office 365 のセキュリティとコンプライアンス ・ センターの](search-the-audit-log-in-security-and-compliance.md#audited-activities)検索「のアクティビティを監査する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p114">Here's are some common document and email activities that you can create an activity alerts for. The tables describes the activity, the name of the activity to create an alert for, and the name of the activity group that the activity is listed under in the **Activities** drop-down list. To see a complete list of the activities that you can create activity alerts for, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="22d7a-p115">任意のユーザーによって実行されるアクティビティを 1 つの活動警告を作成する場合があります。1 つまたは複数によって実行される複数のアクティビティを追跡するアクティビティのアラートを作成することもユーザーです。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p115">You might want to create an activity alert for just one activity that's performed by any user. Or you might want to create an activity alert that track multiple activities performed by one or mores users.</span></span> 
  
    <span data-ttu-id="22d7a-173">次の表は、SharePoint またはビジネスのための OneDrive で一般的ないくつかのドキュメントに関連する活動をします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-173">The following table lists some common document-related activities in SharePoint or OneDrive for Business.</span></span>
    
    |<span data-ttu-id="22d7a-174">**この.**</span><span class="sxs-lookup"><span data-stu-id="22d7a-174">**When a user does this...**</span></span>|<span data-ttu-id="22d7a-175">**このアクティビティのアラートを作成します。**</span><span class="sxs-lookup"><span data-stu-id="22d7a-175">**Create an alert for this activity**</span></span>|<span data-ttu-id="22d7a-176">**アクティビティ グループ**</span><span class="sxs-lookup"><span data-stu-id="22d7a-176">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="22d7a-177">サイト上のドキュメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="22d7a-177">Views a document on a site.</span></span>  <br/> |<span data-ttu-id="22d7a-178">アクセスされるファイル</span><span class="sxs-lookup"><span data-stu-id="22d7a-178">Accessed file</span></span>  <br/> |<span data-ttu-id="22d7a-179">ファイルとフォルダーの活動</span><span class="sxs-lookup"><span data-stu-id="22d7a-179">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="22d7a-180">編集したり、ドキュメントを変更します。</span><span class="sxs-lookup"><span data-stu-id="22d7a-180">Edits or changes a document.</span></span>  <br/> |<span data-ttu-id="22d7a-181">変更されたファイル</span><span class="sxs-lookup"><span data-stu-id="22d7a-181">Modified file</span></span>  <br/> |<span data-ttu-id="22d7a-182">ファイルとフォルダーの活動</span><span class="sxs-lookup"><span data-stu-id="22d7a-182">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="22d7a-183">組織外のユーザーとドキュメントを共有します。</span><span class="sxs-lookup"><span data-stu-id="22d7a-183">Shares a document with a user outside of your organization.</span></span>  <br/> |<span data-ttu-id="22d7a-184">ファイル、フォルダー、または共有サイト</span><span class="sxs-lookup"><span data-stu-id="22d7a-184">Share file, folder, or site</span></span>  <br/> <span data-ttu-id="22d7a-185">および</span><span class="sxs-lookup"><span data-stu-id="22d7a-185">And</span></span>  <br/> <span data-ttu-id="22d7a-186">共有への招待を作成します。</span><span class="sxs-lookup"><span data-stu-id="22d7a-186">Created sharing invitation</span></span>  <br/> <span data-ttu-id="22d7a-187">詳細については、 [Office 365 の監査ログに監査を共有使用](use-sharing-auditing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22d7a-187">For more information, see [Use sharing auditing in the Office 365 audit log](use-sharing-auditing.md).</span></span>  <br/> |<span data-ttu-id="22d7a-188">共有とアクセスの要求活動</span><span class="sxs-lookup"><span data-stu-id="22d7a-188">Sharing and access request activities</span></span>  <br/> |
    |<span data-ttu-id="22d7a-189">アップロードまたはドキュメントをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-189">Uploads or downloads a document.</span></span>  <br/> |<span data-ttu-id="22d7a-190">アップロードされたファイル</span><span class="sxs-lookup"><span data-stu-id="22d7a-190">Uploaded file</span></span>  <br/> <span data-ttu-id="22d7a-191">または</span><span class="sxs-lookup"><span data-stu-id="22d7a-191">And/or</span></span>  <br/> <span data-ttu-id="22d7a-192">ダウンロードしたファイル</span><span class="sxs-lookup"><span data-stu-id="22d7a-192">Downloaded file</span></span>  <br/> |<span data-ttu-id="22d7a-193">ファイルとフォルダーの活動</span><span class="sxs-lookup"><span data-stu-id="22d7a-193">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="22d7a-194">サイトへのアクセス許可を変更します。</span><span class="sxs-lookup"><span data-stu-id="22d7a-194">Changes the access permissions to a site.</span></span>  <br/> |<span data-ttu-id="22d7a-195">変更されたサイトのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="22d7a-195">Modified site permissions</span></span>  <br/> |<span data-ttu-id="22d7a-196">サイト管理業務</span><span class="sxs-lookup"><span data-stu-id="22d7a-196">Site administration activities</span></span>  <br/> |

    <span data-ttu-id="22d7a-197">次の表は、Exchange Online で一般的ないくつか電子メールに関連する活動をします。</span><span class="sxs-lookup"><span data-stu-id="22d7a-197">The following table lists some common email-related activities in Exchange Online.</span></span>

    |<span data-ttu-id="22d7a-198">**この.**</span><span class="sxs-lookup"><span data-stu-id="22d7a-198">**When a user does this...**</span></span>|<span data-ttu-id="22d7a-199">**このアクティビティのアラートを作成します。**</span><span class="sxs-lookup"><span data-stu-id="22d7a-199">**Create an alert for this activity**</span></span>|<span data-ttu-id="22d7a-200">**アクティビティ グループ**</span><span class="sxs-lookup"><span data-stu-id="22d7a-200">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="22d7a-201">完全に削除 (パージ)、電子メール メッセージのユーザーのメールボックスから。</span><span class="sxs-lookup"><span data-stu-id="22d7a-201">Permanently deletes (purges) an email message from their mailbox.</span></span>  <br/> |<span data-ttu-id="22d7a-202">メールボックスから削除されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="22d7a-202">Purged messages from mailbox</span></span>  <br/> | <span data-ttu-id="22d7a-203">Exchange メールボックスの動作</span><span class="sxs-lookup"><span data-stu-id="22d7a-203">Exchange mailbox activities</span></span>  <br/> |
    |<span data-ttu-id="22d7a-204">共有メールボックスから電子メール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="22d7a-204">Sends an email message from a shared mailbox.</span></span>  <br/> |<span data-ttu-id="22d7a-205">送信者アクセス許可を使用してメッセージを送信</span><span class="sxs-lookup"><span data-stu-id="22d7a-205">Sent message using Send As permissions</span></span>  <br/> <span data-ttu-id="22d7a-206">および</span><span class="sxs-lookup"><span data-stu-id="22d7a-206">And</span></span>  <br/> <span data-ttu-id="22d7a-207">代理送信アクセス許可を使用してメッセージを送信</span><span class="sxs-lookup"><span data-stu-id="22d7a-207">Sent message using Send On Behalf permissions</span></span>  <br/> | <span data-ttu-id="22d7a-208">Exchange メールボックスの動作</span><span class="sxs-lookup"><span data-stu-id="22d7a-208">Exchange mailbox activities</span></span>  <br/> |
   
- <span data-ttu-id="22d7a-p116">セキュリティでは、**新規 ActivityAlert**と**セット ActivityAlert**コマンドレットを使用することも&amp;コンプライアンス センターの PowerShell を作成し、アクティビティのアラートを編集します。アクティビティのアラートを作成またはこれらのコマンドレットを使用する場合、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p116">You can also use the **New-ActivityAlert** and **Set-ActivityAlert** cmdlets in Security &amp; Compliance Center PowerShell to create and edit activity alerts. Keep the following things in mind if you use these cmdlets to create or edit activity alerts:</span></span> 
    
  - <span data-ttu-id="22d7a-211">」このアラートには、ピッカーに表示されていないカスタムの操作です"という、警告のプロパティ ページでメッセージを表示**アクティビティ**」ドロップ ダウン リストに含まれていないアラートにアクティビティを追加するのには、コマンドレットを使用する場合</span><span class="sxs-lookup"><span data-stu-id="22d7a-211">If you use a cmdlet to add an activity to the alert that isn't listed in the **Activities** drop-down list, a message is displayed in on the property page for the alert that says, "This alert has custom operations not listed in the picker."</span></span> 
    
  - <span data-ttu-id="22d7a-p117">コマンドレットを使用して作成するか、アクティビティのアラートを編集するのには相応の理由では、組織外のユーザーに電子メール通知を送信します。この外部ユーザーは、アラートの受信者の一覧に表示されます。そのユーザーをセキュリティの**警告の編集**] ページを使用して警告を再度追加することはできません通知と外部ユーザーを削除する場合ですが、&amp;コンプライアンス センターです。**セット ActivityAlert**コマンドレットを使用して外部ユーザーを再度追加する必要があるしたり、**新規 ActivityAlert**コマンドレットを使用して新しいアラートを外部ユーザーが同じ (または異なる) を追加します。</span><span class="sxs-lookup"><span data-stu-id="22d7a-p117">A good reason to use the cmdlets to create or edit an activity alert is to send email notifications to someone outside of your organization. This external user will be listed in the list of recipients for the alert. But if you remove this external user from the alert, that user can't be re-added to the alert by using **Edit alert** page in the Security &amp; Compliance Center. You'll have to re-add the external user using the **Set-ActivityAlert** cmdlet, or use the **New-ActivityAlert** cmdlet to add the same (or different) external user to a new alert.</span></span> 
    
  

