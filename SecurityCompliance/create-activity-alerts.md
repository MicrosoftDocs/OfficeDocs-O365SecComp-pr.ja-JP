---
title: Office 365 セキュリティ&amp;コンプライアンスセンターでアクティビティ警告を作成する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
description: ユーザーが office 365 で特定の操作&amp;を実行したときに office 365 が電子メール通知を送信できるように、セキュリティコンプライアンスセンターでアクティビティアラートを追加して管理します。
ms.openlocfilehash: 25262105332b5317ddf29d49e0364faed57f3d3a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214907"
---
# <a name="create-activity-alerts-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="5954d-103">Office 365 セキュリティ&amp;コンプライアンスセンターでアクティビティ警告を作成する</span><span class="sxs-lookup"><span data-stu-id="5954d-103">Create activity alerts in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="5954d-p101">ユーザーが Office 365 で特定の操作を実行したときに電子メール通知を送信するアクティビティ警告を作成できます。アクティビティアラートは、Office 365 監査ログでイベントを検索するのと似ていますが、通知が作成されたアクティビティのイベントが発生したときに電子メールメッセージが送信されるという点が異なります。</span><span class="sxs-lookup"><span data-stu-id="5954d-p101">You can create an activity alert that will send you an email notification when users perform specific activities in Office 365. Activity alerts are similar to searching for events in the Office 365 audit log, except that you'll be sent an email message when an event for an activity that you've created an alert for happens.</span></span> 
  
 <span data-ttu-id="5954d-p102">**監査ログを検索するのではなく、アクティビティアラートを使用する理由**特定のユーザーによって実行される特定の種類のアクティビティまたはアクティビティが、本当に知りたいと考えている場合があります。これらのアクティビティの監査ログを検索するのではなく、アクティビティ通知を使用して、ユーザーがこれらのアクティビティを実行するときに電子メールメッセージを送信するように Office 365 に通知することができます。たとえば、ユーザーが SharePoint でファイルを削除したときに通知するアクティビティ警告を作成したり、ユーザーが自分のメールボックスからメッセージを完全に削除したときに通知する通知を作成したりできます。送信される電子メール通知には、実行されたアクティビティとそれを実行したユーザーに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5954d-p102">**Why use activity alerts instead of searching the audit log?** There might be certain kinds of activity or activity performed by specific users that you really want to know about. Instead of having to remember to search the audit log for those activities, you can use activity alerts to have Office 365 send you an email message when users perform those activities. For example, you can create an activity alert to notify you when a user deletes files in SharePoint or you can create an alert to notify you when a user permanently deletes messages from their mailbox. The email notification sent to you includes information about which activity was performed and the user who performed it.</span></span> 

> [!NOTE]
> <span data-ttu-id="5954d-p103">新しいアクティビティ通知を作成するのではなく、Security & コンプライアンスセンターでアラートポリシーの使用を開始することをお勧めします。アラートポリシーは、ユーザーが特定のアクティビティを実行したときにアラートをトリガーする通知ポリシーを作成する機能や、Security & コンプライアンスセンターの [**通知の表示**] ページに通知を表示するなどの追加機能を提供します。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアラートポリシー](alert-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5954d-p103">We recommend that you start using alert policies in the Security & Compliance Center instead of creating new activity alerts. Alert policies provide addition functionality such as the ability to create an alert policy that triggers an alert when any user performs a specified activity, and displaying alerts on the **View alerts** page in the Security & Compliance Center. For more information, see [Alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="5954d-114">始める前に</span><span class="sxs-lookup"><span data-stu-id="5954d-114">Before you begin</span></span>

- <span data-ttu-id="5954d-p104">アクティビティアラートを管理するには、セキュリティ&amp;コンプライアンスセンターで組織の構成役割が割り当てられている必要があります。既定では、この役割は、コンプライアンス管理者および組織の管理役割グループに割り当てられます。役割グループへのメンバーの追加の詳細については、「[ユーザーに Office 365 &amp;セキュリティコンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5954d-p104">You must be assigned the Organization Configuration role in the Security &amp; Compliance Center to manage activity alerts. By default, this role is assigned to the Compliance Administrator and Organization Management role groups. For more information about adding members to role groups, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="5954d-p105">アクティビティ通知の使用を開始するには、まず、組織の監査ログを有効にする必要があります (または別の管理者)。これを行うには、[**アクティビティの通知**] ページで [**ユーザーと管理者のアクティビティの記録を開始**する] をクリックするだけです。(このリンクが表示されていない場合は、組織の監査が既に有効になっています。)セキュリティ&amp; /コンプライアンスセンターの [**監査ログの検索**] ページで監査をオンにすることもできます ( \*\* &amp;検索調査\*\* \*\*\*\* \>監査ログ検索に移動)。これは組織に1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5954d-p105">You (or another admin) must first turn on audit logging for your organization before you can start using activity alerts. To do this, just click **Start recording user and admin activity** on the **Activity alerts** page. (If you don't see this link, auditing has already been turned on for your organization.) You can also turn on auditing on the **Audit log search** page in the Security &amp; Compliance Center (go to **Search &amp; investigation** \> **Audit log search**). You only have to do this once for your organization.</span></span>
  
- <span data-ttu-id="5954d-p106">Office 365 監査ログで検索可能なものと同じ活動に対して通知を作成できます。通知を作成できる一般的なシナリオ (および監視対象の特定のアクティビティ) の一覧については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5954d-p106">You can create alerts for the same activities that you can search for in the Office 365 audit log. See the [More information](#more-information) section for a list of common scenarios (and the specific activity to monitor) that you can create alerts for.</span></span> 
    
- <span data-ttu-id="5954d-p107">セキュリティ&amp; /コンプライアンスセンターの [**アクティビティの通知**] ページを使用して、組織のアドレス帳に登録されているユーザーが実行したアクティビティに関する通知のみを作成できます。このページを使用して、アドレス帳に表示されていない外部ユーザーが実行したアクティビティに関する通知を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="5954d-p107">You can use the **Activity alerts** page in the Security &amp; Compliance Center to create alerts only for activity performed by users who are listed in your organization's address book. You can't use this page to create alerts for activity performed by external users who aren't listed in the address book.</span></span> 
    
## <a name="create-an-activity-alert"></a><span data-ttu-id="5954d-126">アクティビティアラートを作成する</span><span class="sxs-lookup"><span data-stu-id="5954d-126">Create an activity alert</span></span>

1. <span data-ttu-id="5954d-127">[https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts) に移動します。</span><span class="sxs-lookup"><span data-stu-id="5954d-127">Go to [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts).</span></span>
    
2. <span data-ttu-id="5954d-128">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5954d-128">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="5954d-129">[**アクティビティの通知**] ページで![、[](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)追加] アイコン [**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5954d-129">On the **Activity alerts** page, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New**.</span></span>

   <span data-ttu-id="5954d-130">アクティビティ警告を作成するためのフライアウトページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5954d-130">The flyout page to create an activity alert is displayed.</span></span>

    
    ![アクティビティアラートを作成する](media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. <span data-ttu-id="5954d-132">アクティビティアラートを作成するには、以下のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="5954d-132">Complete the following fields to create an activity alert:</span></span>
    
    <span data-ttu-id="5954d-p108">**名前**-通知の名前を入力します。アラート名は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5954d-p108">a. **Name** - Type a name for the alert. Alert names must be unique within your organization.</span></span>
    
    <span data-ttu-id="5954d-p109">b.**説明**(省略可能): 追跡するアクティビティやユーザー、電子メール通知の送信先ユーザーなど、アラートを説明します。説明では、他の管理者に通知する目的をすばやく簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="5954d-p109">b. **Description** (Optional) - Describe the alert, such as the activities and users being tracked, and the users that email notifications are sent to. Descriptions provide a quick and easy way to describe the purpose of the alert to other admins.</span></span>
    
    <span data-ttu-id="5954d-p110">[**警告の種類**]-[**カスタム**] オプションが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5954d-p110">c. **Alert type** - Make sure the **Custom** option is selected.</span></span> 

    <span data-ttu-id="5954d-p111">d.- \*\*\*\* [**この通知を送信するタイミング**] をクリックして、次の2つのフィールドを構成します。</span><span class="sxs-lookup"><span data-stu-id="5954d-p111">d. **Send this alert when** - Click **Send this alert when** and then configure these two fields:</span></span>
    
    - <span data-ttu-id="5954d-p112">[**アクティビティ**]-ドロップダウンリストをクリックして、通知を作成できるアクティビティを表示します。これは、Office 365 監査ログを検索するときに表示されるアクティビティリストと同じです。1つ以上の特定のアクティビティを選択することも、アクティビティグループ名をクリックしてグループ内のすべてのアクティビティを選択することもできます。これらのアクティビティの説明については、「 [Office 365 セキュリティ & コンプライアンスセンターで監査ログを検索](search-the-audit-log-in-security-and-compliance.md#audited-activities)する」の「監査アクティビティ」セクションを参照してください。ユーザーが通知に追加したアクティビティのいずれかを実行すると、電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="5954d-p112">**Activities** - Click the drop-down list to display the activities that you can create an alert for. This is the same activities list that's displayed when you search the Office 365 audit log. You can select one or more specific activities or you can click the activity group name to select all activities in the group. For a description of these activities, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities). When a user performs any of the activities that you've added to the alert, an email notification is sent.</span></span> 
    
     - <span data-ttu-id="5954d-p113">**ユーザー** -このボックスをクリックし、1人以上のユーザーを選択します。このボックスのユーザーが [**アクティビティ**] ボックスに追加したアクティビティを実行すると、通知が送信されます。組織内のユーザーが警告で指定された操作を実行したときに通知を送信するには、[**ユーザー** ] ボックスを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="5954d-p113">**Users** - Click this box and then select one or more users. If the users in this box perform the activities that you added to the **Activities** box, an alert will be sent. Leave the **Users** box blank to send an alert when any user in your organization performs the activities specified by the alert.</span></span> 

    <span data-ttu-id="5954d-p114">e. [この通知を**送信する] を**クリックします。 [**この通知を送信**する] をクリックし、[**受信者**] ボックスをクリックして、[ユーザー] ボックスで指定さ\*\*\*\* れたユーザーがアクティビティを実行したときに電子メール通知を受信するユーザーを追加する名前を入力します ([**アクティビティ**] ボックス)。既定では、受信者の一覧に追加されていることに注意してください。このリストから名前を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5954d-p114">e. **Send this alert to** - Click **Send this alert**, and then click in the **Recipients** box and type a name to add a users who will receive an email notification when a user (specified in the **Users** box) performs an activity (specified in the **Activities** box). Note that you are added to the list of recipients by default. You can remove your name from this list.</span></span>
    
5. <span data-ttu-id="5954d-155">[**保存**] をクリックして通知を作成します。</span><span class="sxs-lookup"><span data-stu-id="5954d-155">Click **Save** to create the alert.</span></span> 
    
    <span data-ttu-id="5954d-156">新しい通知が [**アクティビティの通知**] ページの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5954d-156">The new alert is displayed in the list on the **Activity alerts** page.</span></span> 
    
    ![セキュリティ&amp; /コンプライアンスセンターの [アクティビティの通知] ページに通知の一覧が表示されます。](media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    <span data-ttu-id="5954d-p115">通知の状態が **[オン**に設定されています。通知が送信されたときに電子メール通知を受信する受信者も一覧に表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5954d-p115">The status of the alert is set to **On**. Note that the recipients who will received an email notification when an alert is sent are also listed.</span></span> 
  
## <a name="turn-off-an-activity-alert"></a><span data-ttu-id="5954d-160">アクティビティ通知をオフにする</span><span class="sxs-lookup"><span data-stu-id="5954d-160">Turn off an activity alert</span></span>

<span data-ttu-id="5954d-p116">アクティビティ通知をオフにして、電子メール通知が送信されないようにすることができます。アクティビティアラートをオフにしても、組織のアクティビティアラートの一覧に表示されたままになり、そのプロパティを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5954d-p116">You can turn off an activity alert so that an email notification isn't sent. After you turn off the activity alert, it's still displayed in the list of activity alerts for your organization, and you can still view its properties.</span></span>
  
1. <span data-ttu-id="5954d-163">[https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts) に移動します。</span><span class="sxs-lookup"><span data-stu-id="5954d-163">Go to [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts).</span></span>
    
2. <span data-ttu-id="5954d-164">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5954d-164">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="5954d-165">組織のアクティビティアラートの一覧で、オフにする通知をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5954d-165">In the list of activity alerts for your organization, click the alert that you want to turn off.</span></span>
    
4. <span data-ttu-id="5954d-166">[**通知の編集**] ページで、 **[** 状態] を [**オフ**] に変更し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5954d-166">On the **Edit alert** page, click the **On** toggle switch to change the status to **Off**, and then click **Save**.</span></span>
    
    <span data-ttu-id="5954d-167">**アクティビティ警告**ページの通知の状態が [**オフ**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5954d-167">The status of the alert on the **Activity alerts** pages is set to **Off**.</span></span> 
    
<span data-ttu-id="5954d-168">アクティビティの警告をオンに戻すには、これらの手順を繰り返し、[**オフ**] 切り替えスイッチをクリックして状態を [**オン**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="5954d-168">To turn an activity alert back on, just repeat these steps and click the **Off** toggle switch to change the status to **On**.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="5954d-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5954d-169">More information</span></span>

- <span data-ttu-id="5954d-170">以下は、セキュリティ&amp; /コンプライアンスセンターの [この通知を送信します] フィールド (および [アクティビティの**通知**] ページの [**受信者**] の下に一覧表示されている) に指定されているユーザーに送信される電子メール通知の例です。</span><span class="sxs-lookup"><span data-stu-id="5954d-170">Here's an example of the email notification that is sent to the users that are specified in the Sent this alert to field (and listed under **Recipients** on the **Activity alerts** page ) in the Security &amp; Compliance Center.</span></span> 
    
    ![アクティビティアラートに対して送信される電子メール notifcation の例](media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- <span data-ttu-id="5954d-p117">アクティビティ通知を作成できる一般的なドキュメントと電子メールアクティビティを次に示します。表では、アクティビティ、通知を作成するアクティビティの名前、およびアクティビティがリストされているアクティビティグループの名前を [**アクティビティ**] ドロップダウンリストで説明します。アクティビティアラートを作成できるアクティビティの完全な一覧については、「 [Office 365 セキュリティ & コンプライアンスセンターで監査ログを検索](search-the-audit-log-in-security-and-compliance.md#audited-activities)する」の「監査アクティビティ」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5954d-p117">Here's are some common document and email activities that you can create an activity alerts for. The tables describes the activity, the name of the activity to create an alert for, and the name of the activity group that the activity is listed under in the **Activities** drop-down list. To see a complete list of the activities that you can create activity alerts for, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5954d-p118">すべてのユーザーによって実行される1つのアクティビティに対してアクティビティアラートを作成することもできます。または、1人または複数のユーザーによって実行された複数のアクティビティを追跡するアクティビティ警告を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5954d-p118">You might want to create an activity alert for just one activity that's performed by any user. Or you might want to create an activity alert that track multiple activities performed by one or mores users.</span></span> 
  
    <span data-ttu-id="5954d-177">次の表に、SharePoint または OneDrive for business のドキュメント関連の一般的なアクティビティを示します。</span><span class="sxs-lookup"><span data-stu-id="5954d-177">The following table lists some common document-related activities in SharePoint or OneDrive for Business.</span></span>
    
    |<span data-ttu-id="5954d-178">**ユーザーが実行する処理**</span><span class="sxs-lookup"><span data-stu-id="5954d-178">**When a user does this...**</span></span>|<span data-ttu-id="5954d-179">**このアクティビティの通知を作成する**</span><span class="sxs-lookup"><span data-stu-id="5954d-179">**Create an alert for this activity**</span></span>|<span data-ttu-id="5954d-180">**アクティビティグループ**</span><span class="sxs-lookup"><span data-stu-id="5954d-180">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5954d-181">サイト上のドキュメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="5954d-181">Views a document on a site.</span></span>  <br/> |<span data-ttu-id="5954d-182">ファイルへのアクセス</span><span class="sxs-lookup"><span data-stu-id="5954d-182">Accessed file</span></span>  <br/> |<span data-ttu-id="5954d-183">ファイルとフォルダーのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="5954d-183">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="5954d-184">文書を編集または変更します。</span><span class="sxs-lookup"><span data-stu-id="5954d-184">Edits or changes a document.</span></span>  <br/> |<span data-ttu-id="5954d-185">ファイルの変更</span><span class="sxs-lookup"><span data-stu-id="5954d-185">Modified file</span></span>  <br/> |<span data-ttu-id="5954d-186">ファイルとフォルダーのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="5954d-186">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="5954d-187">組織外のユーザーとドキュメントを共有します。</span><span class="sxs-lookup"><span data-stu-id="5954d-187">Shares a document with a user outside of your organization.</span></span>  <br/> |<span data-ttu-id="5954d-188">ファイル、フォルダー、またはサイトを共有する</span><span class="sxs-lookup"><span data-stu-id="5954d-188">Share file, folder, or site</span></span>  <br/> <span data-ttu-id="5954d-189">および</span><span class="sxs-lookup"><span data-stu-id="5954d-189">And</span></span>  <br/> <span data-ttu-id="5954d-190">共有への招待の作成</span><span class="sxs-lookup"><span data-stu-id="5954d-190">Created sharing invitation</span></span>  <br/> <span data-ttu-id="5954d-191">詳細については、「 [Office 365 監査ログで共有監査を使用する](use-sharing-auditing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5954d-191">For more information, see [Use sharing auditing in the Office 365 audit log](use-sharing-auditing.md).</span></span>  <br/> |<span data-ttu-id="5954d-192">共有アクティビティとアクセス要求アクティビティ</span><span class="sxs-lookup"><span data-stu-id="5954d-192">Sharing and access request activities</span></span>  <br/> |
    |<span data-ttu-id="5954d-193">ドキュメントをアップロードまたはダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5954d-193">Uploads or downloads a document.</span></span>  <br/> |<span data-ttu-id="5954d-194">ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="5954d-194">Uploaded file</span></span>  <br/> <span data-ttu-id="5954d-195">または</span><span class="sxs-lookup"><span data-stu-id="5954d-195">And/or</span></span>  <br/> <span data-ttu-id="5954d-196">ファイルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="5954d-196">Downloaded file</span></span>  <br/> |<span data-ttu-id="5954d-197">ファイルとフォルダーのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="5954d-197">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="5954d-198">サイトへのアクセス許可を変更します。</span><span class="sxs-lookup"><span data-stu-id="5954d-198">Changes the access permissions to a site.</span></span>  <br/> |<span data-ttu-id="5954d-199">サイト アクセス許可の変更</span><span class="sxs-lookup"><span data-stu-id="5954d-199">Modified site permissions</span></span>  <br/> |<span data-ttu-id="5954d-200">サイト管理アクティビティ</span><span class="sxs-lookup"><span data-stu-id="5954d-200">Site administration activities</span></span>  <br/> |

    <span data-ttu-id="5954d-201">次の表に、Exchange Online における一般的な電子メール関連アクティビティの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5954d-201">The following table lists some common email-related activities in Exchange Online.</span></span>

    |<span data-ttu-id="5954d-202">**ユーザーが実行する処理**</span><span class="sxs-lookup"><span data-stu-id="5954d-202">**When a user does this...**</span></span>|<span data-ttu-id="5954d-203">**このアクティビティの通知を作成する**</span><span class="sxs-lookup"><span data-stu-id="5954d-203">**Create an alert for this activity**</span></span>|<span data-ttu-id="5954d-204">**アクティビティグループ**</span><span class="sxs-lookup"><span data-stu-id="5954d-204">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5954d-205">メールボックスから電子メールメッセージを完全に削除 (パージ) します。</span><span class="sxs-lookup"><span data-stu-id="5954d-205">Permanently deletes (purges) an email message from their mailbox.</span></span>  <br/> |<span data-ttu-id="5954d-206">メールボックスからメッセージを削除した</span><span class="sxs-lookup"><span data-stu-id="5954d-206">Purged messages from mailbox</span></span>  <br/> | <span data-ttu-id="5954d-207">Exchange メールボックス アクティビティ</span><span class="sxs-lookup"><span data-stu-id="5954d-207">Exchange mailbox activities</span></span>  <br/> |
    |<span data-ttu-id="5954d-208">共有メールボックスから電子メールメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5954d-208">Sends an email message from a shared mailbox.</span></span>  <br/> |<span data-ttu-id="5954d-209">送信者権限を使ったメッセージの送信</span><span class="sxs-lookup"><span data-stu-id="5954d-209">Sent message using Send As permissions</span></span>  <br/> <span data-ttu-id="5954d-210">および</span><span class="sxs-lookup"><span data-stu-id="5954d-210">And</span></span>  <br/> <span data-ttu-id="5954d-211">代理送信権限を使ったメッセージの送信</span><span class="sxs-lookup"><span data-stu-id="5954d-211">Sent message using Send On Behalf permissions</span></span>  <br/> | <span data-ttu-id="5954d-212">Exchange メールボックス アクティビティ</span><span class="sxs-lookup"><span data-stu-id="5954d-212">Exchange mailbox activities</span></span>  <br/> |
   
- <span data-ttu-id="5954d-p119">セキュリティ&amp;コンプライアンスセンターの PowerShell で、**新しい activityalert**および**Set activityalert**コマンドレットを使用して、アクティビティ通知を作成および編集することもできます。これらのコマンドレットを使用してアクティビティ通知を作成または編集する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5954d-p119">You can also use the **New-ActivityAlert** and **Set-ActivityAlert** cmdlets in Security &amp; Compliance Center PowerShell to create and edit activity alerts. Keep the following things in mind if you use these cmdlets to create or edit activity alerts:</span></span> 
    
  - <span data-ttu-id="5954d-215">コマンドレットを使用して、[**アクティビティ**] ドロップダウンリストに表示されていないアラートにアクティビティを追加すると、"このアラートは、選択されていません" という通知を示す警告のプロパティページにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5954d-215">If you use a cmdlet to add an activity to the alert that isn't listed in the **Activities** drop-down list, a message is displayed in on the property page for the alert that says, "This alert has custom operations not listed in the picker."</span></span> 
    
  - <span data-ttu-id="5954d-p120">コマンドレットを使用してアクティビティ通知を作成または編集する場合は、組織外のユーザーに電子メール通知を送信することをお勧めします。この外部ユーザーは、通知の受信者の一覧に表示されます。しかし、この外部ユーザーを通知から削除すると、セキュリティ&amp;コンプライアンスセンターの [通知の**編集**] ページを使用して、そのユーザーを通知に再度追加することはできません。外部ユーザーを再追加するには、このコマンドレット\*\*\*\* を使用するか、または**新しい**通知コマンドレットを使用して同じ (または異なる) 外部ユーザーを新しい通知に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5954d-p120">A good reason to use the cmdlets to create or edit an activity alert is to send email notifications to someone outside of your organization. This external user will be listed in the list of recipients for the alert. But if you remove this external user from the alert, that user can't be re-added to the alert by using **Edit alert** page in the Security &amp; Compliance Center. You'll have to re-add the external user using the **Set-ActivityAlert** cmdlet, or use the **New-ActivityAlert** cmdlet to add the same (or different) external user to a new alert.</span></span> 
    
  

