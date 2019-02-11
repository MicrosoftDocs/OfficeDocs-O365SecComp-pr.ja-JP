---
title: 電子メール通知を送信し、DLP ポリシーのポリシーのヒントを表示します。
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 87496bc5-9601-4473-8021-cb05c71369c1
description: 'ポリシーに関するヒントは、通知またはユーザーが使用してコンテンツを持つ DLP ポリシーと矛盾しているときに表示される警告です。意識を高めるし、組織のポリシーについてユーザーを教育するためには、電子メールによる通知とポリシーのヒントを使用できます。人にしているがブロックされていない有効なビジネスがある場合、ポリシーをオーバーライドする必要があることまたはポリシーが誤検出を検出するかどうかも設定できます。 '
ms.openlocfilehash: 78247a283b2a3b8d581a8b27fe0bf124ed46b222
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "25803998"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="03a2c-105">電子メール通知を送信し、DLP ポリシーのポリシーのヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-105">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="03a2c-p102">識別、監視、および Office 365 の間で機密情報を保護するのには、データ損失防止 (DLP) ポリシーを使用できます。機密性の高い情報を常に、DLP ポリシーに準拠して作業している組織内のユーザーがその作業で不必要にブロックしたくないです。これは、電子メールによる通知とポリシーのヒントが役立つことができます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p102">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365. You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done. This is where email notifications and policy tips can help.</span></span>
  
![メッセージ バーは、Excel 2016 のポリシーのヒントを表示します。](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="03a2c-110">ポリシー ヒント通知または他のユーザーは、DLP ポリシーと競合するコンテンツを使用する場合に表示される警告では、たとえば、Excel ブック内の個人を特定できる情報 (PII) が含まれています、ビジネス サイトの OneDrive のようなコンテンツの外部ユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-110">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>
  
<span data-ttu-id="03a2c-p103">意識を高めるし、組織のポリシーについてユーザーを教育するためには、電子メールによる通知とポリシーのヒントを使用できます。人にしているがブロックされていない有効なビジネスがある場合、ポリシーをオーバーライドする必要があることまたはポリシーが誤検出を検出するかどうかも設定できます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p103">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies. You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>
  
<span data-ttu-id="03a2c-113">Office 365 のセキュリティで&amp;コンプライアンス ・ センターでは、DLP ポリシーを作成するとき、ユーザー通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-113">In the Office 365 Security &amp; Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>
  
- <span data-ttu-id="03a2c-114">電子メール通知を送信する人を選択する問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-114">Send an email notification to the people you choose that describes the issue.</span></span>
    
- <span data-ttu-id="03a2c-115">DLP ポリシーと競合するコンテンツのポリシーに関するヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-115">Display a policy tip for content that conflicts with the DLP policy:</span></span>
    
  - <span data-ttu-id="03a2c-116">ポリシーのヒントは、Outlook 2013 以降で、web 上の Outlook で電子メールのメッセージが構成されているときに上の受信者にメッセージの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-116">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>
    
  - <span data-ttu-id="03a2c-p104">ビジネス アカウントまたは SharePoint Online サイトの OneDrive では、ドキュメントの項目に表示される警告のアイコンがポリシーのヒントが示されます。詳細を表示する項目を選択し、**情報**を選択![情報のウィンドウのアイコン](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png)ページを開くには、詳細ウィンドウの右上隅にします。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p104">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item. To view more information, you can select an item and then choose **Information**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span> 
    
  - <span data-ttu-id="03a2c-119">メッセージ バーおよびタブで Excel 2016、PowerPoint の 2016年とビジネス サイトまたは DLP ポリシーに含まれている SharePoint Online サイトの OneDrive に格納されている 2016 の Word ドキュメントでは、ポリシーのヒントが表示されます (**ファイル**] メニューの [ \> **情報**)。</span><span class="sxs-lookup"><span data-stu-id="03a2c-119">For Excel 2016, PowerPoint 2016, and Word 2016 documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view ( **File** menu \> **Info**).</span></span>
    
## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="03a2c-120">DLP ポリシーにユーザーの通知を追加します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-120">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="03a2c-121">DLP ポリシーを作成するときに電子メールによる通知とポリシーのヒントの両方は、**ユーザーの通知**] セクションの一部です。</span><span class="sxs-lookup"><span data-stu-id="03a2c-121">When you create a DLP policy, both email notifications and policy tips are part of the **User notifications** section.</span></span> 
  
1. <span data-ttu-id="03a2c-122">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="03a2c-p105">職場、学校のアカウントを使用して Office 365 にサインインします。Office 365 のセキュリティの&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p105">Sign in to Office 365 using your work or school account. You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="03a2c-125">セキュリティ&amp;コンプライアンス センター\>左側のナビゲーション\>**データの損失防止** \> **ポリシー** \> **+ ポリシーの作成**。</span><span class="sxs-lookup"><span data-stu-id="03a2c-125">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![[ポリシー] のボタンを作成します。](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="03a2c-127">DLP ポリシー テンプレートを保護する必要のある機密性の高い情報の種類を選択して\>**次**です。</span><span class="sxs-lookup"><span data-stu-id="03a2c-127">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="03a2c-128">空のテンプレートを使用して起動するのには [**カスタム**] を選択します\>**カスタム ポリシー** \> **次**です。</span><span class="sxs-lookup"><span data-stu-id="03a2c-128">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>
    
5. <span data-ttu-id="03a2c-129">ポリシーの名前\>**次**です。</span><span class="sxs-lookup"><span data-stu-id="03a2c-129">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="03a2c-130">DLP ポリシーで保護するための場所を選択するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="03a2c-130">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="03a2c-131">**Office 365 内のすべての場所**を選択して\>**次**です。</span><span class="sxs-lookup"><span data-stu-id="03a2c-131">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="03a2c-132">**自分で特定の場所を選択**を選択して\>**次**です。</span><span class="sxs-lookup"><span data-stu-id="03a2c-132">Choose **Let me choose specific locations** \> **Next**.</span></span>
    
    <span data-ttu-id="03a2c-133">オン/オフなど、すべての Exchange 電子メールまたは OneDrive のすべてのアカウントは、全体の場所を含めたり除外したり、その場所の**状態**を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-133">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="03a2c-134">のみ特定の SharePoint サイトまたは OneDrive アカウントは、スイッチ**の状態**と特定のサイトまたはアカウントを選択するのに**含める**] で [リンク] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03a2c-134">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> 
    
7. <span data-ttu-id="03a2c-135">選択の**詳細設定を使用する** \> **次**です。</span><span class="sxs-lookup"><span data-stu-id="03a2c-135">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="03a2c-136">**+ 新しいルール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-136">Choose **+ New rule**.</span></span>
    
9. <span data-ttu-id="03a2c-137">規則エディターで、[**ユーザー通知**の状態をオンにします。</span><span class="sxs-lookup"><span data-stu-id="03a2c-137">In the rule editor, under **User notifications**, switch the status on.</span></span>
    
    ![ルール エディターのユーザーの通知] セクション](media/47705927-c60b-4054-a072-ab914f33d15d.png)
  
## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="03a2c-139">電子メール通知を構成するためのオプション</span><span class="sxs-lookup"><span data-stu-id="03a2c-139">Options for configuring email notifications</span></span>

<span data-ttu-id="03a2c-140">DLP ポリシーのそれぞれのルールで、次のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-140">For each rule in a DLP policy, you can:</span></span>
  
- <span data-ttu-id="03a2c-p106">選択したユーザーに通知を送信します。これらのユーザーとしては、コンテンツ所有者、コンテンツの最終変更者、コンテンツが格納されているサイトの所有者、または特定のユーザーなどが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p106">Send the notification to the people you choose. These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>
    
- <span data-ttu-id="03a2c-p107">HTML またはトークンを使用して、通知に含まれるテキストをカスタマイズします。詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p107">Customize the text that's included in the notification by using HTML or tokens. See the section below for more information.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="03a2c-p108">個々 の受信者電子メール通知を送信することができます: グループまたは配布リストではありません。_gt 新しいコンテンツだけでは、電子メール通知をトリガーします。既存のコンテンツを編集するポリシーのヒントがない電子メール通知をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p108">Email notifications can be sent only to individual recipients—not groups or distribution lists. >  Only new content will trigger an email notification. Editing existing content will trigger policy tips but not an email notification.</span></span> 
  
![電子メール通知オプション](media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a><span data-ttu-id="03a2c-149">既定の電子メールの通知</span><span class="sxs-lookup"><span data-stu-id="03a2c-149">Default email notification</span></span>

<span data-ttu-id="03a2c-p109">通知では、電子メール、または"アクセスがブロックのドキュメントのアクション、「通知」など「メッセージがブロックされている」で始まる件名があります。通知メッセージの本文には、通知は、ドキュメントについては、ドキュメントが格納されているのし、ドキュメントのポリシーのヒントを表示、サイトに移動するためのリンクが含まれます (ポリシーのヒントについては、次のセクションを参照してください)、問題を解決する場所です。メッセージについて通知する場合は、通知メッセージが含まれる添付ファイルとして DLP ポリシーに一致します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p109">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents. If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips). If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>
  
![通知メッセージ](media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
<span data-ttu-id="03a2c-p110">既定では、通知には、サイト上の項目に対して以下のようなテキストが表示されます。通知テキストは、ルールごとに個別に構成されるため、表示されるテキストは、一致するルールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p110">By default, notifications display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="03a2c-156">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="03a2c-156">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="03a2c-157">**[SharePoint または OneDrive のビジネス ドキュメント用の既定の通知では、.**</span><span class="sxs-lookup"><span data-stu-id="03a2c-157">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="03a2c-158">**Outlook のメッセージの既定の通知では、.**</span><span class="sxs-lookup"><span data-stu-id="03a2c-158">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03a2c-159">通知を送りますが、上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="03a2c-159">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="03a2c-160">この項目は、組織内のポリシーと矛盾します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-160">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="03a2c-161">電子メール メッセージが組織のポリシーと競合、です。</span><span class="sxs-lookup"><span data-stu-id="03a2c-161">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="03a2c-162">アクセスをブロックし、通知を送信し、上書きを許可します</span><span class="sxs-lookup"><span data-stu-id="03a2c-162">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="03a2c-p111">この項目は、組織内でのポリシーと競合します。この競合を解決しない場合は、このファイルへのアクセスがブロックされています。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p111">This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="03a2c-p112">電子メール メッセージが組織のポリシーと競合、です。メッセージは、すべての受信者に配信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p112">Your email message conflicts with a policy in your organization. The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="03a2c-167">アクセスをブロックし、通知を送信します</span><span class="sxs-lookup"><span data-stu-id="03a2c-167">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="03a2c-p113">この項目は、組織内のポリシーと矛盾します。この項目へのアクセスは、その所有者、最終変更者、およびサイトコレクション管理者 (プライマリ) 以外のすべてのユーザーに対してブロックされます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p113">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="03a2c-p114">電子メール メッセージが組織のポリシーと競合、です。メッセージは、すべての受信者に配信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p114">Your email message conflicts with a policy in your organization. The message wasn't delivered to all recipients.</span></span>  <br/> |
   
### <a name="custom-email-notification"></a><span data-ttu-id="03a2c-172">カスタム電子メール通知</span><span class="sxs-lookup"><span data-stu-id="03a2c-172">Custom email notification</span></span>

<span data-ttu-id="03a2c-p115">エンド ・ ユーザーや管理者を既定の電子メール通知を送信する代わりに、カスタムの電子メール通知を作成することができます。カスタム電子メール通知は、HTML をサポートし、5,000 文字に制限します。HTML を使用すると、画像、書式、およびその他の通知でブランド化を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p115">You can create a custom email notification instead of sending the default email notification to your end users or admins. The custom email notification supports HTML and has a 5,000-character limit. You can use HTML to include images, formatting, and other branding in the notification.</span></span>
  
<span data-ttu-id="03a2c-p116">電子メール通知をカスタマイズするために次のトークンを使用することもできます。これらのトークンは、送信される通知で特定の情報で置き換えられる変数です。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p116">You can also use the following tokens to help customize the email notification. These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>

|<span data-ttu-id="03a2c-178">**トークン**</span><span class="sxs-lookup"><span data-stu-id="03a2c-178">**Token**</span></span>|<span data-ttu-id="03a2c-179">**説明**</span><span class="sxs-lookup"><span data-stu-id="03a2c-179">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03a2c-180">%% AppliedActions %%</span><span class="sxs-lookup"><span data-stu-id="03a2c-180">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="03a2c-181">コンテンツに適用されるアクションです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-181">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="03a2c-182">%% ContentURL %%</span><span class="sxs-lookup"><span data-stu-id="03a2c-182">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="03a2c-183">ビジネス サイトに SharePoint Online サイトまたは OneDrive 上のドキュメントの URL です。</span><span class="sxs-lookup"><span data-stu-id="03a2c-183">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="03a2c-184">%% MatchedConditions %%</span><span class="sxs-lookup"><span data-stu-id="03a2c-184">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="03a2c-p117">コンテンツと一致した条件です。コンテンツに関する問題のユーザーに通知するのにには、このトークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p117">The conditions that were matched by the content. Use this token to inform people of possible issues with the content.</span></span>  <br/> |
   
![トークンが表示される場所を示す通知メッセージ](media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="03a2c-188">ポリシー ヒントを構成するためのオプション</span><span class="sxs-lookup"><span data-stu-id="03a2c-188">Options for configuring policy tips</span></span>

<span data-ttu-id="03a2c-189">DLP ポリシー内の各ルールに関して、次の事柄を行うポリシー ヒントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-189">For each rule in a DLP policy, you can configure policy tips to:</span></span>
  
- <span data-ttu-id="03a2c-p118">この人に DLP ポリシーを使用するコンテンツが競合している競合を解決するのにはアクションを実行できるようにします。既定のテキストを使用することができます (次の表を参照してください) か、または組織の特定のポリシーに関するユーザー設定のテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p118">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict. You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>
    
- <span data-ttu-id="03a2c-p119">ユーザーによる DLP ポリシーの上書きを許可します。必要に応じて、次のことも行えます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p119">Allow the person to override the DLP policy. Optionally, you can:</span></span>
    
  - <span data-ttu-id="03a2c-p120">ユーザー ポリシーをオーバーライドするためのビジネス ・ ジャスティフィケーションを入力する必要があります。この情報をログに記録され、それを表示するには、セキュリティの [**レポート**] セクションで DLP のレポートに&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p120">Require the person to enter a business justification for overriding the policy. This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span> 
    
  - <span data-ttu-id="03a2c-p121">ユーザーが誤検知を報告し、DLP ポリシーを上書きできるようにします。この情報はレポート用にも記録されるので、誤検知を使用してルールを微調整できます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p121">Allow the person to report a false positive and override the DLP policy. This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>
    
![ポリシー ヒントのオプション](media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
<span data-ttu-id="03a2c-199">たとえば、個人を特定できる情報 (PII) を検出する DLP ポリシーがビジネス サイトの OneDrive を適用する必要があり、このポリシーには次の 3 つのルール。</span><span class="sxs-lookup"><span data-stu-id="03a2c-199">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>
  
1. <span data-ttu-id="03a2c-p122">最初のルール:5 個以下の対象機密情報インスタンスがドキュメントで検出され、ドキュメントが組織内のユーザーと共有されている場合、[**通知を送信**] アクションによってポリシー ヒントが表示されます。ポリシー ヒントについては、上書きオプションは必要ありません。このルールは単にユーザーに通知を行うだけで、アクセスをブロックするわけではないからです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p122">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip. For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span> 
    
2. <span data-ttu-id="03a2c-p123">2 つ目のルール: を超える文書で、この機密情報の 5 つのインスタンスが検出され、ドキュメントが組織内のユーザーと共有、**コンテンツへのアクセスをブロック**操作制限されるファイル、および、**のアクセス許可通知を送信する**アクションは、ビジネス ・ ジャスティフィケーションを提供することでこのルールのアクションをオーバーライドするメンバーを使用します。組織のビジネス、個人情報のデータを共有する内部の人を必要とし、DLP ポリシーは、この作業をブロックしたくないです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p123">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification. Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span> 
    
3. <span data-ttu-id="03a2c-p124">3 番目のルール:5 個を超える対象機密情報インスタンスがドキュメントで検出され、組織外のユーザーとドキュメントを共有する場合、[**コンテンツへのアクセスの禁止**] アクションによってファイルのアクセス許可が制限され、[**通知の送信**] アクションではこのルールのアクションの上書きをユーザーに許可しません。情報が外部共有されているためです。いかなる状況においても、組織内のユーザーが組織外で PII データを共有することを許可すべきではありません。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p124">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally. Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span> 
    
<span data-ttu-id="03a2c-206">ルールを上書きするポリシー ヒントを使用する際に把握しておくべきいくつかの点を以下に記します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-206">Here are some fine points to understand about using a policy tip to override a rule:</span></span>
  
- <span data-ttu-id="03a2c-207">オーバーライドするためのオプションは、1 つの規則、および以外はオーバーライドできませんが、通知を送信する) ルールのアクションのすべてを上書きします。</span><span class="sxs-lookup"><span data-stu-id="03a2c-207">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>
    
- <span data-ttu-id="03a2c-p125">DLP ポリシーでは、いくつかのルールに一致するコンテンツがありますが、最も制限の厳しい、最も高い優先順位の規則によるポリシーのヒントのみが表示されます。たとえば、単に通知を送信するルールをポリシーのヒントに表示されるコンテンツへのアクセスをブロック ルールをポリシー ヒントです。これは人が次々 にポリシーのヒントを表示することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p125">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="03a2c-211">最も制限の厳しいルールのポリシー ヒントによってルールの上書きがユーザーに許可される場合、対象ルールを上書きすると、コンテンツが一致する他のルールも上書きされます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-211">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="03a2c-212">OneDrive for Business サイトと SharePoint Online サイトのポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="03a2c-212">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="03a2c-213">ポリシーのヒントでは、ビジネス サイトや SharePoint Online サイトに、OneDrive 上のドキュメントが、DLP ポリシーの規則に一致して、そのルールは、ポリシーのヒントを使用して、ドキュメント上の特別なアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-213">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>
  
1. <span data-ttu-id="03a2c-214">ルールによってファイルに関する通知が送信される場合は、警告アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-214">If the rule sends a notification about the file, the warning icon appears.</span></span>
    
2. <span data-ttu-id="03a2c-215">ルールによってドキュメントへのアクセスがブロックされる場合には、ブロック済みアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-215">If the rule blocks access to the document, the blocked icon appears.</span></span>
    
![OneDrive アカウント内のドキュメントのポリシー ヒント アイコン](media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
<span data-ttu-id="03a2c-217">ドキュメントに対してアクションを実行する、アイテムを選択することができます\>**情報**を選択する![情報ウィンドウのアイコン](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png)ページを開くには、詳細ウィンドウの右上隅に\>**ポリシーのヒントを表示**します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-217">To take action on a document, you can select an item \> choose **Information**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>
  
<span data-ttu-id="03a2c-218">ポリシー ヒントにはコンテンツに関する問題が一覧表示され、ポリシー ヒントにオプションが構成されている場合には、[**解決**] を検索してから、ポリシー ヒントの [**上書き**] または誤検知の [**レポート**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-218">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span> 
  
![情報ペインの表示ポリシーのヒント](media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![上書きするオプションを使用するポリシーのヒント](media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
<span data-ttu-id="03a2c-p126">DLP ポリシーがサイトと同期され、コンテンツが定期的かつ非同期的に評価されます。それで、DLP ポリシーを作成してからポリシー ヒントが表示されるまで少しの遅延があります。ポリシーを解決または上書きしてから、サイトのドキュメントのアイコンが消えるまで同様の遅延が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p126">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips. There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>
  
### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="03a2c-223">サイト上のポリシー ヒントの既定テキスト</span><span class="sxs-lookup"><span data-stu-id="03a2c-223">Default text for policy tips on sites</span></span>

<span data-ttu-id="03a2c-p127">既定では、ポリシー ヒントは、サイト上の項目に対して以下のようなテキストを表示します。通知テキストは、ルールごとに個別に構成されるため、表示されるテキストは、一致するルールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p127">By default, policy tips display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="03a2c-226">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="03a2c-226">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="03a2c-227">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="03a2c-227">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03a2c-228">通知を送りますが、上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="03a2c-228">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="03a2c-229">この項目は、組織内のポリシーと矛盾します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-229">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="03a2c-230">アクセスをブロックし、通知を送信し、上書きを許可します</span><span class="sxs-lookup"><span data-stu-id="03a2c-230">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="03a2c-p128">この項目は、組織内でのポリシーと競合します。この競合を解決しない場合は、このファイルへのアクセスがブロックされています。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p128">This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="03a2c-233">アクセスをブロックし、通知を送信します</span><span class="sxs-lookup"><span data-stu-id="03a2c-233">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="03a2c-p129">この項目は、組織内のポリシーと矛盾します。この項目へのアクセスは、その所有者、最終変更者、およびサイトコレクション管理者 (プライマリ) 以外のすべてのユーザーに対してブロックされます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p129">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="03a2c-236">サイト上のポリシーのヒントについては、ユーザー設定のテキスト</span><span class="sxs-lookup"><span data-stu-id="03a2c-236">Custom text for policy tips on sites</span></span>

<span data-ttu-id="03a2c-p130">E メール通知から個別にポリシーのヒントのテキストをカスタマイズすることができます。電子メール通知 (セクションの上を参照) のユーザー設定のテキストとは異なり HTML またはトークン ポリシーのヒントについては、ユーザー設定のテキストは使用できません。代わりに、ポリシーのヒントについては、ユーザー設定のテキストは、テキストは 256 文字に制限されただけです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p130">You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="03a2c-240">ポリシーは、web 上の Outlook と Outlook 2013 以降でのヒントします。</span><span class="sxs-lookup"><span data-stu-id="03a2c-240">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="03a2c-p131">Web 上の Outlook と Outlook 2013 で新しい電子メールを作成して以降では、DLP ポリシー内のルールに一致するコンテンツを追加する場合、ポリシーに関するヒントが表示され、そのルールは、ポリシーのヒントを使用しています。メッセージが構成されているときに、受信者の上、メッセージの上部にあるポリシーのヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p131">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips. The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>
  
![構成されるメッセージの上部にあるポリシーのヒント](media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
<span data-ttu-id="03a2c-244">ポリシーは、機密性の高い情報は、メッセージの本文、件名、またはメッセージの添付ファイルにも次のようにするかどうかの作業をヒントします。</span><span class="sxs-lookup"><span data-stu-id="03a2c-244">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>
  
![ポリシーを示すヒントが DLP ポリシーを使用して添付ファイルが競合しています。](media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
<span data-ttu-id="03a2c-246">上書きを許可するようにポリシーのヒントを構成してが場合は、**詳細を表示する**を選択\>**オーバーライド**\>業務の妥当性を入力するか、誤検出を報告\>**をオーバーライド**します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-246">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>
  
![展開して [上書き] オプションを表示するメッセージにポリシーのヒント](media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![ポリシー ヒントをオーバーライドすることができます、ポリシーのヒント] ダイアログ ボックス](media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
<span data-ttu-id="03a2c-249">機密情報を電子メールに追加すると、あることを機密情報を追加すると、ポリシー ヒントが表示されるまでの待機時間に注意してください。</span><span class="sxs-lookup"><span data-stu-id="03a2c-249">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a><span data-ttu-id="03a2c-250">Outlook 2013 といくつかの条件のみのポリシー ヒントの表示後のサポート</span><span class="sxs-lookup"><span data-stu-id="03a2c-250">Outlook 2013 and later supports showing policy tips for only some conditions</span></span>

<span data-ttu-id="03a2c-251">現時点では、Outlook 2013 以降ではこれらの条件にのみ表示されているポリシーのヒントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="03a2c-251">Currently, Outlook 2013 and later supports showing policy tips only for these conditions:</span></span>

- <span data-ttu-id="03a2c-252">コンテンツが含まれています</span><span class="sxs-lookup"><span data-stu-id="03a2c-252">Content contains</span></span>
- <span data-ttu-id="03a2c-253">コンテンツを共有します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-253">Content is shared</span></span>

<span data-ttu-id="03a2c-p132">現在他の条件のポリシーのヒントを表示するためのサポートを作成しています。これらは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p132">We're currently working on support for showing policy tips for additional conditions. These include:</span></span>

- <span data-ttu-id="03a2c-256">電子メール添付ファイルのコンテンツをスキャンできませんでした。</span><span class="sxs-lookup"><span data-stu-id="03a2c-256">Any email attachment's content could not be scanned</span></span>
- <span data-ttu-id="03a2c-257">電子メール添付ファイルのコンテンツのスキャンを完了しませんでした。</span><span class="sxs-lookup"><span data-stu-id="03a2c-257">Any email attachment's content didn't complete scanning</span></span>
- <span data-ttu-id="03a2c-258">添付ファイルのファイル拡張子は、します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-258">Attachment file extension is</span></span>
- <span data-ttu-id="03a2c-259">添付ファイルにはパスワードで保護されました。</span><span class="sxs-lookup"><span data-stu-id="03a2c-259">Attachment is password protected</span></span>
- <span data-ttu-id="03a2c-260">ドキュメント プロパティは、します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-260">Document property is</span></span>
- <span data-ttu-id="03a2c-261">受信者のドメインとは</span><span class="sxs-lookup"><span data-stu-id="03a2c-261">Recipient domain is</span></span>
- <span data-ttu-id="03a2c-262">送信者の IP アドレスします。</span><span class="sxs-lookup"><span data-stu-id="03a2c-262">Sender IP address is</span></span>

<span data-ttu-id="03a2c-p133">コンテンツに合わせるし、コンテンツに対する防策を適用するでは、Outlook でこれらの条件すべてが動作する注意してください。ユーザーにポリシーのヒントの表示はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p133">Note that all of these conditions work in Outlook, where they will match content and enforce protective actions on content. But showing policy tips to users is not yet supported.</span></span>
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="03a2c-265">Office 365 のセキュリティと Exchange 管理センターでのポリシーのヒント&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="03a2c-265">Policy tips in the Exchange Admin Center vs. the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="03a2c-p134">ポリシー ヒントが DLP ポリシーのいずれかで作業し、メール フロー ルールが、Exchange 管理センターで、または Office 365 のセキュリティで作成した DLP ポリシーを使用して作成された&amp;コンプライアンス ・ センターが、両方です。これは、これらのポリシーが別の場所に格納されているポリシーのヒントは、1 つの場所からのみ描画できるためです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p134">Policy tips can work either with DLP policies and mail flow rules created in the Exchange Admin Center, or with DLP policies created in the Office 365 Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="03a2c-p135">Exchange 管理センターで、Office 365 のセキュリティを構成するすべてのポリシー ヒント ポリシー ヒントを構成したかどうかは&amp;コンプライアンス センターは、web 上の Outlook と Outlook 2013 および交換のヒントをオフにするまでは、後でユーザーに表示されません管理センターです。これは、現在の Exchange トランスポート ルールは Office 365 のセキュリティに切り替えるときに選択するまでの作業を続けることにより、&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p135">If you've configured policy tips in the Exchange Admin Center, any policy tips that you configure in the Office 365 Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange Admin Center. This ensures that your current Exchange transport rules will continue to work until you choose to switch over to the Office 365 Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="03a2c-270">ポリシーのヒントは、1 つの場所からのみ描画できるときに電子メール通知を常に送信される両方の Office 365 のセキュリティでは、DLP ポリシーを使用している場合でも&amp;コンプライアンス センターと、Exchange 管理センターです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-270">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Office 365 Security &amp; Compliance Center and the Exchange Admin Center.</span></span>
  
### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="03a2c-271">ポリシーの既定のテキストの電子メールをヒントします。</span><span class="sxs-lookup"><span data-stu-id="03a2c-271">Default text for policy tips in email</span></span>

<span data-ttu-id="03a2c-272">既定では、ポリシーのヒントは、電子メールは、次のようなテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-272">By default, policy tips display text similar to the following for email.</span></span>

|<span data-ttu-id="03a2c-273">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="03a2c-273">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="03a2c-274">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="03a2c-274">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03a2c-275">通知を送りますが、上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="03a2c-275">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="03a2c-276">電子メールは、組織内でのポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="03a2c-276">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="03a2c-277">アクセスをブロックし、通知を送信し、上書きを許可します</span><span class="sxs-lookup"><span data-stu-id="03a2c-277">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="03a2c-278">電子メールは、組織内でのポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="03a2c-278">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="03a2c-279">アクセスをブロックし、通知を送信します</span><span class="sxs-lookup"><span data-stu-id="03a2c-279">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="03a2c-280">電子メールは、組織内でのポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="03a2c-280">Your email conflicts with a policy in your organization.</span></span>  <br/> |
   
## <a name="policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="03a2c-281">Excel 2016、PowerPoint 2016、Word 2016 におけるポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="03a2c-281">Policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="03a2c-p136">ユーザーがデスクトップ バージョンの Excel 2016、PowerPoint 2016、Word 2016 内の機密情報を扱っている場合、ポリシー ヒントによってコンテンツが DLP ポリシーと矛盾することをリアルタイムでユーザーに通知できます。そのためには以下のことが必要となります。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p136">When people work with sensitive content in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016, policy tips can notify them in real time that the content conflicts with a DLP policy. This requires that:</span></span>
  
- <span data-ttu-id="03a2c-284">Office ドキュメントが、OneDrive for Business サイトまたは SharePoint Online サイトに格納されていること。</span><span class="sxs-lookup"><span data-stu-id="03a2c-284">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>
    
- <span data-ttu-id="03a2c-285">ポリシー ヒントを使用するように構成されている DLP ポリシーでは、サイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-285">The site is included in a DLP policy that's configured to use policy tips.</span></span>
    
<span data-ttu-id="03a2c-286">Office 2016 デスクトップ プログラムは、Office 365 から直接 DLP ポリシーを自動的に同期し、DLP ポリシーと競合しないでことを確認して、リアルタイムでポリシーのヒントを表示するドキュメントをスキャンし、します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-286">These Office 2016 desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>
  
<span data-ttu-id="03a2c-287">DLP ポリシーにおけるポリシー ヒントの構成法によっては、ユーザーがポリシー ヒントを単に無視すること、業務上の理由を提供してまたは提供せずにポリシーを上書きすること、誤検知を報告することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-287">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>
  
<span data-ttu-id="03a2c-288">ポリシー ヒントは、メッセージ バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-288">Policy tips appear on the Message Bar.</span></span>
  
![メッセージ バーは、Excel 2016 のポリシーのヒントを表示します。](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="03a2c-290">また、ポリシー ヒントは、Backstage ビューにも表示されます ([**ファイル**タブ)。</span><span class="sxs-lookup"><span data-stu-id="03a2c-290">And policy tips also appear in the Backstage view (on the **File** tab).</span></span> 
  
![Backstage は、Excel 2016 のポリシーのヒントを表示します。](media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
<span data-ttu-id="03a2c-292">DLP ポリシーのポリシー ヒントにこれらのオプションが設定されている場合、[**解決**] を選択した後、ポリシー ヒントの [**上書き**]、または誤検知の [**レポート**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="03a2c-292">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span> 
  
![Excel 2016 の Backstage 内のポリシーのヒント上のオプション](media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
<span data-ttu-id="03a2c-p137">こうした各 Office 2016 デスクトップ プログラムでは、ユーザーは、ポリシー ヒントを無効にすることを選択できます。無効にすると、通知を単に行うポリシー ヒントはメッセージ バーにも Backstage ビュー ([**ファイル**] タブ) にも表示されません。ただし、ブロックおよび上書きに関するポリシー ヒントは依然表示され、電子メール通知も引き続き受け取ります。さらに、ポリシー ヒントを無効にしても、適用されている DLP ポリシーがドキュメントに対して無効になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p137">In each of these Office 2016 desktop programs, people can choose to turn off policy tips. If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab). However, policy tips about blocking and overriding will still appear, and they will still receive the email notification. In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span> 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="03a2c-298">Excel 2016、PowerPoint 2016、Word 2016 におけるポリシー ヒントの既定テキスト</span><span class="sxs-lookup"><span data-stu-id="03a2c-298">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="03a2c-p138">既定では、ポリシー ヒントは、開いているドキュメントのメッセージ バーと Backstage ビューに次のようなテキストを表示します。通知テキストは、ルールごとに個別に構成されるため、表示されるテキストは、一致するルールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p138">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="03a2c-301">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="03a2c-301">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="03a2c-302">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="03a2c-302">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03a2c-303">通知を送りますが、上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="03a2c-303">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="03a2c-p139">このファイルは、組織内でのポリシーと競合します。詳細については、[**ファイル**] メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p139">This file conflicts with a policy in your organization. Go to the **File** menu for more information.  </span></span><br/> |
|<span data-ttu-id="03a2c-306">アクセスをブロックし、通知を送信し、上書きを許可します</span><span class="sxs-lookup"><span data-stu-id="03a2c-306">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="03a2c-p140">このファイルは、組織内でのポリシーと競合します。この競合を解決しない場合は、このファイルへのアクセスがブロックされています。詳細については、[**ファイル**] メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p140">This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  </span></span><br/> |
|<span data-ttu-id="03a2c-310">アクセスをブロックし、通知を送信します</span><span class="sxs-lookup"><span data-stu-id="03a2c-310">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="03a2c-p141">このファイルは、組織内でのポリシーと競合します。この競合を解決しない場合は、このファイルへのアクセスがブロックされています。詳細については、[**ファイル**] メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p141">This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  </span></span><br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="03a2c-314">ポリシーのユーザー設定のテキストが Excel 2016、2016 の PowerPoint、および Word 2016 のヒントします。</span><span class="sxs-lookup"><span data-stu-id="03a2c-314">Custom text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="03a2c-p142">E メール通知から個別にポリシーのヒントのテキストをカスタマイズすることができます。電子メール通知 (セクションの上を参照) のユーザー設定のテキストとは異なり HTML またはトークン ポリシーのヒントについては、ユーザー設定のテキストは使用できません。代わりに、ポリシーのヒントについては、ユーザー設定のテキストは、テキストは 256 文字に制限されただけです。</span><span class="sxs-lookup"><span data-stu-id="03a2c-p142">You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="03a2c-318">詳細情報</span><span class="sxs-lookup"><span data-stu-id="03a2c-318">More information</span></span>

- [<span data-ttu-id="03a2c-319">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="03a2c-319">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="03a2c-320">テンプレートから DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="03a2c-320">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="03a2c-321">FCI または他のプロパティが使用されているドキュメントを保護する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="03a2c-321">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="03a2c-322">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="03a2c-322">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="03a2c-323">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="03a2c-323">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    

