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
ms.openlocfilehash: 2a579e850d16b730a777ce6c4e5c0446305a027d
ms.sourcegitcommit: 3a376619dbae472495c29da7c061f5c5faeeaddb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2018
ms.locfileid: "26282741"
---
# <a name="create-activity-alerts-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="f448e-103">Office 365 のセキュリティでのアクティビティの通知を作成&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="f448e-103">Create activity alerts in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="f448e-p101">活動アラートを送信する電子メール通知ユーザーが Office 365 で特定のアクティビティを実行するときを作成することができます。アクティビティのアラートは、Office 365 の監査ログのイベントを検索するようなが、電子メール メッセージの通知を作成したアクティビティのイベントを送信することが行われます。</span><span class="sxs-lookup"><span data-stu-id="f448e-p101">You can create an activity alert that will send you an email notification when users perform specific activities in Office 365. Activity alerts are similar to searching for events in the Office 365 audit log, except that you'll be sent an email message when an event for an activity that you've created an alert for happens.</span></span> 
  
 <span data-ttu-id="f448e-p102">**監査ログを検索する代わりにアクティビティのアラートを使用する理由ですか?** 特定の種類のアクティビティまたはアクティビティが本当に知りたい特定のユーザーによって実行される可能性があります。それらの活動の監査ログを検索するのにのではなくして、Office 365 のユーザーがそれらの活動を実行するときに、電子メール メッセージを送信するアクティビティのアラートを使用できます。たとえば、ユーザーが SharePoint でファイルを削除またはユーザーが自分のメールボックスからメッセージを完全に削除したときに通知するアラートを作成するときに通知する警告活動を作成します。電子メールに通知送信するにはには、どのアクティビティを実行し、それを実行したユーザーに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f448e-p102">**Why use activity alerts instead of searching the audit log?** There might be certain kinds of activity or activity performed by specific users that you really want to know about. Instead of having to remember to search the audit log for those activities, you can use activity alerts to have Office 365 send you an email message when users perform those activities. For example, you can create an activity alert to notify you when a user deletes files in SharePoint or you can create an alert to notify you when a user permanently deletes messages from their mailbox. The email notification sent to you includes information about which activity was performed and the user who performed it.</span></span> 

> [!NOTE]
> <span data-ttu-id="f448e-p103">新しいアクティビティのアラートを作成する代わりに、セキュリティとコンプライアンス センターでアラート ・ ポリシーを使用して起動することをお勧めします。アラート ・ ポリシーは、すべてのユーザーを行い、指定したアクティビティでは、セキュリティとコンプライアンス センターに**通知を表示する**ページの警告を表示するときに警告を発生させる警告ポリシーを作成する機能などの追加機能を提供します。詳細についてを参照してください[では、Office 365 のセキュリティ ポリシーの警告&amp;コンプライアンス センター](alert-policies.md)です。</span><span class="sxs-lookup"><span data-stu-id="f448e-p103">We recommend that you start using alert policies in the Security & Compliance Center instead of creating new activity alerts. Alert policies provide addition functionality such as the ability to create an alert policy that triggers an alert when any user performs a specified activity, and displaying alerts on the **View alerts** page in the Security & Compliance Center. For more information, see [Alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="f448e-114">はじめに</span><span class="sxs-lookup"><span data-stu-id="f448e-114">Before you begin</span></span>

- <span data-ttu-id="f448e-p104">セキュリティで組織の構成の役割を割り当てる必要があります&amp;アクティビティのアラートを管理するためのコンプライアンス センターです。既定では、この役割はコンプライアンス管理者および組織の管理役割グループに割り当てられます。役割グループにメンバーを追加する方法の詳細についてを参照してください[Office 365 のセキュリティにアクセスできるように&amp;コンプライアンス センター](grant-access-to-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="f448e-p104">You must be assigned the Organization Configuration role in the Security &amp; Compliance Center to manage activity alerts. By default, this role is assigned to the Compliance Administrator and Organization Management role groups. For more information about adding members to role groups, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="f448e-p105">(または別の管理者) する必要があります最初に監査ログの記録を組織のアクティビティのアラートの使用を開始する前にします。これを行うには、クリックして**ユーザーと管理者のアクティビティの記録を開始\*\*\*\*アクティビティのアラート**] ページにします。(このリンクが表示されない場合は、監査が既に有効になって、組織の。)**監査ログの検索**] ページで、セキュリティ監査にすることも&amp;コンプライアンス センター (を参照して**検索&amp;調査** \> **監査ログの検索**)。のみこれを行う 1 回の組織があります。</span><span class="sxs-lookup"><span data-stu-id="f448e-p105">You (or another admin) must first turn on audit logging for your organization before you can start using activity alerts. To do this, just click **Start recording user and admin activity** on the **Activity alerts** page. (If you don't see this link, auditing has already been turned on for your organization.) You can also turn on auditing on the **Audit log search** page in the Security &amp; Compliance Center (go to **Search &amp; investigation** \> **Audit log search**). You only have to do this once for your organization.</span></span>
  
- <span data-ttu-id="f448e-p106">Office 365 の監査ログを検索することができますアクティビティのアラートを作成できます。[詳細について](#more-information)はを参照してくださいの警告を作成することができます一般的なシナリオ (特定のアクティビティを監視する) の一覧のセクションです。</span><span class="sxs-lookup"><span data-stu-id="f448e-p106">You can create alerts for the same activities that you can search for in the Office 365 audit log. See the [More information](#more-information) section for a list of common scenarios (and the specific activity to monitor) that you can create alerts for.</span></span> 
    
- <span data-ttu-id="f448e-p107">**アクティビティのアラート**] ページを使用するには、セキュリティで&amp;、組織のアドレス帳に記載されているユーザーによって実行されたアクティビティに対してのみ警告を作成するコンプライアンス センターです。アドレス帳に記載されていない外部のユーザーによって実行されるアクティビティのアラートを作成するのには、このページを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="f448e-p107">You can use the **Activity alerts** page in the Security &amp; Compliance Center to create alerts only for activity performed by users who are listed in your organization's address book. You can't use this page to create alerts for activity performed by external users who aren't listed in the address book.</span></span> 
    
## <a name="create-an-activity-alert"></a><span data-ttu-id="f448e-126">活動通知を作成します。</span><span class="sxs-lookup"><span data-stu-id="f448e-126">Create an activity alert</span></span>

1. <span data-ttu-id="f448e-127">[https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts) に移動します。</span><span class="sxs-lookup"><span data-stu-id="f448e-127">Go to [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts).</span></span>
    
2. <span data-ttu-id="f448e-128">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f448e-128">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="f448e-129">**アクティビティのアラート**] ページをクリックして![の追加アイコン](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新規**です。</span><span class="sxs-lookup"><span data-stu-id="f448e-129">On the **Activity alerts** page, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New**.</span></span>

   <span data-ttu-id="f448e-130">活動警告を作成するポップアップ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f448e-130">The flyout page to create an activity alert is displayed.</span></span>

    
    ![活動通知を作成します。](media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. <span data-ttu-id="f448e-132">活動アラートを作成するのには、次のフィールドを完了します。</span><span class="sxs-lookup"><span data-stu-id="f448e-132">Complete the following fields to create an activity alert:</span></span>
    
    <span data-ttu-id="f448e-p108">a.**名**には、警告の名前を入力します。警告名は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f448e-p108">a. **Name** - Type a name for the alert. Alert names must be unique within your organization.</span></span>
    
    <span data-ttu-id="f448e-p109">b.**の説明**(オプション) の活動と、追跡されているユーザーなどのアラートの説明し、電子メール通知をユーザーに送信します。説明は、他の管理者に警告の目的を説明する簡単ですばやい方法です。</span><span class="sxs-lookup"><span data-stu-id="f448e-p109">b. **Description** (Optional) - Describe the alert, such as the activities and users being tracked, and the users that email notifications are sent to. Descriptions provide a quick and easy way to describe the purpose of the alert to other admins.</span></span>
    
    <span data-ttu-id="f448e-p110">c.**警告の種類**に [**カスタム**] オプションが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f448e-p110">c. **Alert type** - Make sure the **Custom** option is selected.</span></span> 

    <span data-ttu-id="f448e-p111">d.**この警告を送信**- をクリックして**この警告を送信**し、これら 2 つのフィールドを構成します。</span><span class="sxs-lookup"><span data-stu-id="f448e-p111">d. **Send this alert when** - Click **Send this alert when** and then configure these two fields:</span></span>
    
    - <span data-ttu-id="f448e-p112">**活動**- のための警告を作成する活動を表示するドロップダウン リストを一覧表示] をクリックします。これは、Office 365 の監査ログを検索するときに表示される同じアクティビティのリストです。1 つまたは複数の特定の活動を選択することや、グループ内のすべてのアクティビティを選択するアクティビティのグループ名をクリックすることができます。これらのアクティビティについては、[監査ログが Office 365 のセキュリティとコンプライアンス ・ センターの](search-the-audit-log-in-security-and-compliance.md#audited-activities)検索「のアクティビティを監査する」セクションを参照してください。ユーザーは、いずれかのアラートに追加したアクティビティを実行するときに電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="f448e-p112">**Activities** - Click the drop-down list to display the activities that you can create an alert for. This is the same activities list that's displayed when you search the Office 365 audit log. You can select one or more specific activities or you can click the activity group name to select all activities in the group. For a description of these activities, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities). When a user performs any of the activities that you've added to the alert, an email notification is sent.</span></span> 
    
     - <span data-ttu-id="f448e-p113">**ユーザー**は、このボックスをクリックし、1 つまたは複数のユーザーを選択します。このボックス内のユーザーのアクティビティを**アクティビティ**ボックスに追加した場合、アラートが送信されます。**ユーザー**ボックスは、組織内のすべてのユーザーが警告で指定されたアクティビティを実行したときにアラートを送信するのには、空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="f448e-p113">**Users** - Click this box and then select one or more users. If the users in this box perform the activities that you added to the **Activities** box, an alert will be sent. Leave the **Users** box blank to send an alert when any user in your organization performs the activities specified by the alert.</span></span> 

    <span data-ttu-id="f448e-p114">**この通知を送信**- e.**この警告を送信**、] をクリックして、[**宛先**] ボックスでをクリックし、(、[**ユーザー** ] ボックスで指定された) ユーザーがアクティビティを実行すると、電子メール通知を受信するユーザーを追加する名前を入力 (で指定されている、**アクティビティ**ボックスの場合)。既定の受信者の一覧に追加されますに注意してください。この一覧から名前を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f448e-p114">e. **Send this alert to** - Click **Send this alert**, and then click in the **Recipients** box and type a name to add a users who will receive an email notification when a user (specified in the **Users** box) performs an activity (specified in the **Activities** box). Note that you are added to the list of recipients by default. You can remove your name from this list.</span></span>
    
5. <span data-ttu-id="f448e-155">アラートを作成するのには**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f448e-155">Click **Save** to create the alert.</span></span> 
    
    <span data-ttu-id="f448e-156">新しい警告は、[**アクティビティのアラート**] ページで、一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f448e-156">The new alert is displayed in the list on the **Activity alerts** page.</span></span> 
    
    ![セキュリティでのアクティビティの通知] ページでアラートの一覧が表示されます&amp;コンプライアンス センター](media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    <span data-ttu-id="f448e-p115">アラートの状態は、**上**に設定されます。アラートが送信されるときに電子メール通知を受信した受信者も表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f448e-p115">The status of the alert is set to **On**. Note that the recipients who will received an email notification when an alert is sent are also listed.</span></span> 
  
## <a name="turn-off-an-activity-alert"></a><span data-ttu-id="f448e-160">活動アラートをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f448e-160">Turn off an activity alert</span></span>

<span data-ttu-id="f448e-p116">電子メール通知が送信されないように、アクティビティのアラートを無効にできます。アクティビティのアラートを無効にした後、組織の活動の警告の一覧に表示されたままと、そのプロパティを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f448e-p116">You can turn off an activity alert so that an email notification isn't sent. After you turn off the activity alert, it's still displayed in the list of activity alerts for your organization, and you can still view its properties.</span></span>
  
1. <span data-ttu-id="f448e-163">[https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts) に移動します。</span><span class="sxs-lookup"><span data-stu-id="f448e-163">Go to [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts).</span></span>
    
2. <span data-ttu-id="f448e-164">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f448e-164">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="f448e-165">組織の活動の警告の一覧で、警告を無効にするをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f448e-165">In the list of activity alerts for your organization, click the alert that you want to turn off.</span></span>
    
4. <span data-ttu-id="f448e-166">[**警告の編集**] ページで**の**切り替えスイッチを [**オフ**の状態を変更する] をクリックし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f448e-166">On the **Edit alert** page, click the **On** toggle switch to change the status to **Off**, and then click **Save**.</span></span>
    
    <span data-ttu-id="f448e-167">**アクティビティのアラート**のページでアラートの状態が**無効**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f448e-167">The status of the alert on the **Activity alerts** pages is set to **Off**.</span></span> 
    
<span data-ttu-id="f448e-168">アクティビティのアラートをオンに戻す、次の手順を繰り返し、**上**に状態を変更するのには**オフ**の切り替えスイッチをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f448e-168">To turn an activity alert back on, just repeat these steps and click the **Off** toggle switch to change the status to **On**.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="f448e-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f448e-169">More information</span></span>

- <span data-ttu-id="f448e-170">フィールド ([**アクティビティのアラート**] ページで、**宛先**の下に表示されている) にもセキュリティにはこの警告の送信で指定されているユーザーに送信される電子メール通知の例を次のとおりです&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="f448e-170">Here's an example of the email notification that is sent to the users that are specified in the Sent this alert to field (and listed under **Recipients** on the **Activity alerts** page ) in the Security &amp; Compliance Center.</span></span> 
    
    ![活動アラートの送信、電子メール notifcation の例](media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- <span data-ttu-id="f448e-p117">ここでは、に関するアラートは、いくつか一般的なドキュメント、電子メール活動を活動を作成することができます。テーブルでは、アクティビティの警告を作成するアクティビティの名前とアクティビティは、**アクティビティ**」ドロップ ダウン リストに記載されている活動グループの名前について説明します。アクティビティのアラートを作成する活動の完全な一覧を表示するには、[監査ログが Office 365 のセキュリティとコンプライアンス ・ センターの](search-the-audit-log-in-security-and-compliance.md#audited-activities)検索「のアクティビティを監査する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f448e-p117">Here's are some common document and email activities that you can create an activity alerts for. The tables describes the activity, the name of the activity to create an alert for, and the name of the activity group that the activity is listed under in the **Activities** drop-down list. To see a complete list of the activities that you can create activity alerts for, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f448e-p118">任意のユーザーによって実行されるアクティビティを 1 つの活動警告を作成する場合があります。1 つまたは複数によって実行される複数のアクティビティを追跡するアクティビティのアラートを作成することもユーザーです。</span><span class="sxs-lookup"><span data-stu-id="f448e-p118">You might want to create an activity alert for just one activity that's performed by any user. Or you might want to create an activity alert that track multiple activities performed by one or mores users.</span></span> 
  
    <span data-ttu-id="f448e-177">次の表は、SharePoint またはビジネスのための OneDrive で一般的ないくつかのドキュメントに関連する活動をします。</span><span class="sxs-lookup"><span data-stu-id="f448e-177">The following table lists some common document-related activities in SharePoint or OneDrive for Business.</span></span>
    
    |<span data-ttu-id="f448e-178">**この.**</span><span class="sxs-lookup"><span data-stu-id="f448e-178">**When a user does this...**</span></span>|<span data-ttu-id="f448e-179">**このアクティビティのアラートを作成します。**</span><span class="sxs-lookup"><span data-stu-id="f448e-179">**Create an alert for this activity**</span></span>|<span data-ttu-id="f448e-180">**アクティビティ グループ**</span><span class="sxs-lookup"><span data-stu-id="f448e-180">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f448e-181">サイト上のドキュメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="f448e-181">Views a document on a site.</span></span>  <br/> |<span data-ttu-id="f448e-182">アクセスされるファイル</span><span class="sxs-lookup"><span data-stu-id="f448e-182">Accessed file</span></span>  <br/> |<span data-ttu-id="f448e-183">ファイルとフォルダーの活動</span><span class="sxs-lookup"><span data-stu-id="f448e-183">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="f448e-184">編集したり、ドキュメントを変更します。</span><span class="sxs-lookup"><span data-stu-id="f448e-184">Edits or changes a document.</span></span>  <br/> |<span data-ttu-id="f448e-185">変更されたファイル</span><span class="sxs-lookup"><span data-stu-id="f448e-185">Modified file</span></span>  <br/> |<span data-ttu-id="f448e-186">ファイルとフォルダーの活動</span><span class="sxs-lookup"><span data-stu-id="f448e-186">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="f448e-187">組織外のユーザーとドキュメントを共有します。</span><span class="sxs-lookup"><span data-stu-id="f448e-187">Shares a document with a user outside of your organization.</span></span>  <br/> |<span data-ttu-id="f448e-188">ファイル、フォルダー、または共有サイト</span><span class="sxs-lookup"><span data-stu-id="f448e-188">Share file, folder, or site</span></span>  <br/> <span data-ttu-id="f448e-189">および</span><span class="sxs-lookup"><span data-stu-id="f448e-189">And</span></span>  <br/> <span data-ttu-id="f448e-190">共有への招待を作成します。</span><span class="sxs-lookup"><span data-stu-id="f448e-190">Created sharing invitation</span></span>  <br/> <span data-ttu-id="f448e-191">詳細については、 [Office 365 の監査ログに監査を共有使用](use-sharing-auditing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f448e-191">For more information, see [Use sharing auditing in the Office 365 audit log](use-sharing-auditing.md).</span></span>  <br/> |<span data-ttu-id="f448e-192">共有とアクセスの要求活動</span><span class="sxs-lookup"><span data-stu-id="f448e-192">Sharing and access request activities</span></span>  <br/> |
    |<span data-ttu-id="f448e-193">アップロードまたはドキュメントをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f448e-193">Uploads or downloads a document.</span></span>  <br/> |<span data-ttu-id="f448e-194">アップロードされたファイル</span><span class="sxs-lookup"><span data-stu-id="f448e-194">Uploaded file</span></span>  <br/> <span data-ttu-id="f448e-195">または</span><span class="sxs-lookup"><span data-stu-id="f448e-195">And/or</span></span>  <br/> <span data-ttu-id="f448e-196">ダウンロードしたファイル</span><span class="sxs-lookup"><span data-stu-id="f448e-196">Downloaded file</span></span>  <br/> |<span data-ttu-id="f448e-197">ファイルとフォルダーの活動</span><span class="sxs-lookup"><span data-stu-id="f448e-197">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="f448e-198">サイトへのアクセス許可を変更します。</span><span class="sxs-lookup"><span data-stu-id="f448e-198">Changes the access permissions to a site.</span></span>  <br/> |<span data-ttu-id="f448e-199">変更されたサイトのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f448e-199">Modified site permissions</span></span>  <br/> |<span data-ttu-id="f448e-200">サイト管理業務</span><span class="sxs-lookup"><span data-stu-id="f448e-200">Site administration activities</span></span>  <br/> |

    <span data-ttu-id="f448e-201">次の表は、Exchange Online で一般的ないくつか電子メールに関連する活動をします。</span><span class="sxs-lookup"><span data-stu-id="f448e-201">The following table lists some common email-related activities in Exchange Online.</span></span>

    |<span data-ttu-id="f448e-202">**この.**</span><span class="sxs-lookup"><span data-stu-id="f448e-202">**When a user does this...**</span></span>|<span data-ttu-id="f448e-203">**このアクティビティのアラートを作成します。**</span><span class="sxs-lookup"><span data-stu-id="f448e-203">**Create an alert for this activity**</span></span>|<span data-ttu-id="f448e-204">**アクティビティ グループ**</span><span class="sxs-lookup"><span data-stu-id="f448e-204">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f448e-205">完全に削除 (パージ)、電子メール メッセージのユーザーのメールボックスから。</span><span class="sxs-lookup"><span data-stu-id="f448e-205">Permanently deletes (purges) an email message from their mailbox.</span></span>  <br/> |<span data-ttu-id="f448e-206">メールボックスから削除されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="f448e-206">Purged messages from mailbox</span></span>  <br/> | <span data-ttu-id="f448e-207">Exchange メールボックスの動作</span><span class="sxs-lookup"><span data-stu-id="f448e-207">Exchange mailbox activities</span></span>  <br/> |
    |<span data-ttu-id="f448e-208">共有メールボックスから電子メール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f448e-208">Sends an email message from a shared mailbox.</span></span>  <br/> |<span data-ttu-id="f448e-209">送信者アクセス許可を使用してメッセージを送信</span><span class="sxs-lookup"><span data-stu-id="f448e-209">Sent message using Send As permissions</span></span>  <br/> <span data-ttu-id="f448e-210">および</span><span class="sxs-lookup"><span data-stu-id="f448e-210">And</span></span>  <br/> <span data-ttu-id="f448e-211">代理送信アクセス許可を使用してメッセージを送信</span><span class="sxs-lookup"><span data-stu-id="f448e-211">Sent message using Send On Behalf permissions</span></span>  <br/> | <span data-ttu-id="f448e-212">Exchange メールボックスの動作</span><span class="sxs-lookup"><span data-stu-id="f448e-212">Exchange mailbox activities</span></span>  <br/> |
   
- <span data-ttu-id="f448e-p119">セキュリティでは、**新規 ActivityAlert**と**セット ActivityAlert**コマンドレットを使用することも&amp;コンプライアンス センターの PowerShell を作成し、アクティビティのアラートを編集します。アクティビティのアラートを作成またはこれらのコマンドレットを使用する場合、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f448e-p119">You can also use the **New-ActivityAlert** and **Set-ActivityAlert** cmdlets in Security &amp; Compliance Center PowerShell to create and edit activity alerts. Keep the following things in mind if you use these cmdlets to create or edit activity alerts:</span></span> 
    
  - <span data-ttu-id="f448e-215">」このアラートには、ピッカーに表示されていないカスタムの操作です"という、警告のプロパティ ページでメッセージを表示**アクティビティ**」ドロップ ダウン リストに含まれていないアラートにアクティビティを追加するのには、コマンドレットを使用する場合</span><span class="sxs-lookup"><span data-stu-id="f448e-215">If you use a cmdlet to add an activity to the alert that isn't listed in the **Activities** drop-down list, a message is displayed in on the property page for the alert that says, "This alert has custom operations not listed in the picker."</span></span> 
    
  - <span data-ttu-id="f448e-p120">コマンドレットを使用して作成するか、アクティビティのアラートを編集するのには相応の理由では、組織外のユーザーに電子メール通知を送信します。この外部ユーザーは、アラートの受信者の一覧に表示されます。そのユーザーをセキュリティの**警告の編集**] ページを使用して警告を再度追加することはできません通知と外部ユーザーを削除する場合ですが、&amp;コンプライアンス センターです。**セット ActivityAlert**コマンドレットを使用して外部ユーザーを再度追加する必要があるしたり、**新規 ActivityAlert**コマンドレットを使用して新しいアラートを外部ユーザーが同じ (または異なる) を追加します。</span><span class="sxs-lookup"><span data-stu-id="f448e-p120">A good reason to use the cmdlets to create or edit an activity alert is to send email notifications to someone outside of your organization. This external user will be listed in the list of recipients for the alert. But if you remove this external user from the alert, that user can't be re-added to the alert by using **Edit alert** page in the Security &amp; Compliance Center. You'll have to re-add the external user using the **Set-ActivityAlert** cmdlet, or use the **New-ActivityAlert** cmdlet to add the same (or different) external user to a new alert.</span></span> 
    
  

