---
title: メール通知を送信して、DLP ポリシーのポリシーのヒントを表示する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 'ポリシー ヒントは、誰かがコンテンツを使用していて、それが DLP ポリシーと競合している場合に表示される通知または警告です。メール通知とポリシー ヒントを使用して、組織のポリシーに関する認識を高め、ユーザーの教育に役立てることができます。また、業務上の正当な理由がある場合や、ポリシーが誤検知した場合にブロックされないように、ユーザーにポリシーを上書きするオプションを提供することもできます。 '
ms.openlocfilehash: fbaabd674de97ffce32b8caae8e2b41471e52569
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410922"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="8fd09-105">メール通知を送信して、DLP ポリシーのポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="8fd09-105">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="8fd09-p102">データ損失防止 (DLP) ポリシーを使用して、Office 365 全体の機密情報の識別、監視、保護を行うことができます。このような機密情報を扱う組織内のユーザーを DLP ポリシーに準拠させつつ、不必要にブロックしてユーザーの作業が完了できないような事態は避けたいでしょう。このような場合に、メール通知とポリシー ヒントが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p102">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365. You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done. This is where email notifications and policy tips can help.</span></span>
  
![メッセージ バーに Excel 2016 のポリシー ヒントが表示される](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="8fd09-110">ポリシー ヒントは、誰かがコンテンツを使用していて、それが DLP ポリシーと競合している場合に表示される通知または警告です。たとえば、個人情報 (PII) が含まれ、外部ユーザーと共有されている OneDrive for Business サイト上の Excel ブックなどのコンテンツがこれに該当します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-110">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>
  
<span data-ttu-id="8fd09-p103">メール通知とポリシー ヒントを使用して、組織のポリシーに関する認識を高め、ユーザーの教育に役立てることができます。また、業務上の正当な理由がある場合や、ポリシーが誤検知した場合にブロックされないように、ユーザーにポリシーを上書きするオプションを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p103">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies. You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>
  
<span data-ttu-id="8fd09-113">Office 365 セキュリティ/コンプライアンス センターでは、DLP ポリシーを作成するときに、ユーザー通知を構成して次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-113">In the Office 365 Security &amp; Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>
  
- <span data-ttu-id="8fd09-114">選択したユーザーに、問題を説明するメール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-114">Send an email notification to the people you choose that describes the issue.</span></span>
    
- <span data-ttu-id="8fd09-115">DLP ポリシーと競合しているコンテンツのポリシー ヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-115">Display a policy tip for content that conflicts with the DLP policy:</span></span>
    
  - <span data-ttu-id="8fd09-116">Outlook on the web および Outlook 2013 以降のメールの場合は、メッセージの作成中、受信者の上のメッセージの上部にポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-116">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>
    
  - <span data-ttu-id="8fd09-p104">OneDrive for Business アカウントまたは SharePoint Online サイトのドキュメントの場合は、アイテムに表示される警告アイコンによってポリシー ヒントが示されます。詳細を見るには、アイテムを選んだ後、ページの右上隅にある **[情報]**![情報ウィンドウ アイコン](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) を選択し、詳細ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p104">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item. To view more information, you can select an item and then choose **Information**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span> 
    
  - <span data-ttu-id="8fd09-119">DLP ポリシーに含まれる OneDrive for Business サイトまたは SharePoint Online サイトに保存されている Excel 2016、PowerPoint 2016、Word 2016 ドキュメントの場合、ポリシー ヒントはメッセージ バーおよび Backstage ビュー (**[ファイル]** メニュー \> **[情報]**) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-119">For Excel 2016, PowerPoint 2016, and Word 2016 documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view ( **File** menu \> **Info**).</span></span>
    
## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="8fd09-120">ユーザー通知を DLP ポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="8fd09-120">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="8fd09-121">DLP ポリシーを作成すると、メール通知とポリシー ヒントはどちらも **[ユーザー通知]** セクションの一部になります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-121">When you create a DLP policy, both email notifications and policy tips are part of the **User notifications** section.</span></span> 
  
1. <span data-ttu-id="8fd09-122">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="8fd09-p105">職場または学校のアカウントを使用して、Office 365 にサインインします。これで、Office 365 セキュリティ/コンプライアンス センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p105">Sign in to Office 365 using your work or school account. You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="8fd09-125">セキュリティ/コンプライアンス センターの左側のナビゲーションで、**[データ損失防止]** \> **[ポリシー]** \> **[+ ポリシーの作成]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-125">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![[ポリシーの作成] ボタン](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="8fd09-127">必要な種類の機密情報を保護する DLP ポリシー テンプレートを選び、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-127">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="8fd09-128">空のテンプレートから始めるには、**[カスタム]** \> **[カスタム ポリシー]** \> **[次へ]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-128">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>
    
5. <span data-ttu-id="8fd09-129">ポリシーの名前を設定し、**[次へ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-129">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="8fd09-130">DLP ポリシーで保護する場所を選ぶには、次のいずれかを行います。</span><span class="sxs-lookup"><span data-stu-id="8fd09-130">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="8fd09-131">**[Office 365 のすべての場所]** \> **[次へ]** と選びます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-131">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="8fd09-132">**[自分で特定の場所を選択する]** \> **[次へ]** と選びます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-132">Choose **Let me choose specific locations** \> **Next**.</span></span>
    
    <span data-ttu-id="8fd09-133">すべての Exchange メールやすべての OneDrive アカウントなど、特定の場所全体を含めたり除外したりするには、その場所の **[状態]** をオンまたはオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-133">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="8fd09-134">特定の SharePoint サイトまたは OneDrive アカウントだけを含めるには、**[状態]** をオンに切り替えた後、**[含める]** の下のリンクをクリックして、特定のサイトまたはアカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-134">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> 
    
7. <span data-ttu-id="8fd09-135">**[詳細設定を使う]** \> **[次へ]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-135">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="8fd09-136">**[+ 新しいルール]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-136">Choose **+ New rule**.</span></span>
    
9. <span data-ttu-id="8fd09-137">ルール エディターで、**[ユーザー通知]** の状態をオンにします。</span><span class="sxs-lookup"><span data-stu-id="8fd09-137">In the rule editor, under **User notifications**, switch the status on.</span></span>
    
    ![ルール エディターのユーザー通知セクション](media/47705927-c60b-4054-a072-ab914f33d15d.png)
  
## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="8fd09-139">メール通知を設定するためのオプション</span><span class="sxs-lookup"><span data-stu-id="8fd09-139">Options for configuring email notifications</span></span>

<span data-ttu-id="8fd09-140">DLP ポリシーのそれぞれのルールで、次のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-140">For each rule in a DLP policy, you can:</span></span>
  
- <span data-ttu-id="8fd09-p106">選択したユーザーに通知を送信します。これらのユーザーとしては、コンテンツ所有者、コンテンツの最終変更者、コンテンツが格納されているサイトの所有者、または特定のユーザーなどが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p106">Send the notification to the people you choose. These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>
    
- <span data-ttu-id="8fd09-p107">HTML またはトークンを使用して、通知に含まれるテキストをカスタマイズできます。詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p107">Customize the text that's included in the notification by using HTML or tokens. See the section below for more information.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="8fd09-p108">メール通知は、個別の受信者にのみ送信できます。グループまたは配布リストには送信できません。メール通知をトリガーするのは、新しいコンテンツだけです。既存のコンテンツを編集すると、ポリシー ヒントはトリガーされますが、メール通知はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p108">Email notifications can be sent only to individual recipients—not groups or distribution lists. >  Only new content will trigger an email notification. Editing existing content will trigger policy tips but not an email notification.</span></span> 
  
![メール通知オプション](media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a><span data-ttu-id="8fd09-149">既定のメール通知</span><span class="sxs-lookup"><span data-stu-id="8fd09-149">Default email notification</span></span>

<span data-ttu-id="8fd09-p109">通知には、実行されるアクションから始まる件名行があります。たとえば、メールの場合は、“通知”、“メッセージがブロックされました” など、ドキュメントの場合は、“アクセスがブロックされました” などと表示されます。ドキュメントに関する通知の場合、通知メッセージの本文には、ドキュメントが保存されているサイトに移動し、ドキュメントのポリシー ヒントを表示するリンクが含まれています。ここで問題を解決できます (ポリシー ヒントについては、以下のセクションを参照)。メールに関する通知の場合、通知には DLP ポリシーと一致するメッセージが添付ファイルとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p109">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents. If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips). If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>
  
![通知メッセージ](media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
<span data-ttu-id="8fd09-p110">既定では、通知には、サイト上の項目に対して以下のようなテキストが表示されます。通知テキストは、ルールごとに個別に構成されるため、表示されるテキストは、一致するルールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p110">By default, notifications display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="8fd09-156">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="8fd09-156">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="8fd09-157">**SharePoint または OneDrive for Business のドキュメントの既定の通知内容**</span><span class="sxs-lookup"><span data-stu-id="8fd09-157">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="8fd09-158">**Outlook メッセージの既定の通知内容**</span><span class="sxs-lookup"><span data-stu-id="8fd09-158">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8fd09-159">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="8fd09-159">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="8fd09-160">このアイテムは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="8fd09-160">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="8fd09-161">あなたのメール メッセージは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="8fd09-161">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="8fd09-162">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="8fd09-162">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="8fd09-p111">このアイテムは組織のポリシーと競合しています。この競合を解決しないと、このファイルへのアクセスがブロックされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p111">This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="8fd09-165">あなたのメール メッセージは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="8fd09-165">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="8fd09-166">メッセージはすべての受信者に配信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="8fd09-166">The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="8fd09-167">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="8fd09-167">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="8fd09-p113">このアイテムは組織内のポリシーと競合します。アイテムの所有者、最後に更新した人、プライマリ サイト コレクションの管理者を除くすべてのユーザーが、このアイテムへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p113">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="8fd09-p114">あなたのメール メッセージは、組織のポリシーと競合しています。メッセージは、すべての受信者には配信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p114">Your email message conflicts with a policy in your organization. The message wasn't delivered to all recipients.</span></span>  <br/> |
   
### <a name="custom-email-notification"></a><span data-ttu-id="8fd09-172">ユーザー設定のメール通知</span><span class="sxs-lookup"><span data-stu-id="8fd09-172">Custom email notification</span></span>

<span data-ttu-id="8fd09-p115">エンド ユーザーまたは管理者に既定のメール通知を送信する代わりに、カスタムのメール通知を作成することができます。ユーザー設定のメール通知は、HTML に対応しており、5,000 文字の制限があります。HTML を使用すると、通知に画像、書式、その他のブランド設定を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p115">You can create a custom email notification instead of sending the default email notification to your end users or admins. The custom email notification supports HTML and has a 5,000-character limit. You can use HTML to include images, formatting, and other branding in the notification.</span></span>
  
<span data-ttu-id="8fd09-p116">また、次のトークンを使用して、メール通知をカスタマイズすることもできます。これらのトークンは、送信される通知の固有の情報によって置き換えられる変数です。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p116">You can also use the following tokens to help customize the email notification. These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>

|<span data-ttu-id="8fd09-178">**トークン**</span><span class="sxs-lookup"><span data-stu-id="8fd09-178">**Token**</span></span>|<span data-ttu-id="8fd09-179">**説明**</span><span class="sxs-lookup"><span data-stu-id="8fd09-179">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8fd09-180">%%AppliedActions%%</span><span class="sxs-lookup"><span data-stu-id="8fd09-180">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="8fd09-181">アクションがコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-181">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="8fd09-182">%%ContentURL%%</span><span class="sxs-lookup"><span data-stu-id="8fd09-182">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="8fd09-183">SharePoint Online サイトまたは OneDrive for Business サイトのドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="8fd09-183">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="8fd09-184">%%MatchedConditions%%</span><span class="sxs-lookup"><span data-stu-id="8fd09-184">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="8fd09-p117">コンテンツと一致した条件。コンテンツで想定される問題をユーザーに通知する場合にこのトークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p117">The conditions that were matched by the content. Use this token to inform people of possible issues with the content.</span></span>  <br/> |
   
![トークンがどこに表示されているかを示す通知メッセージ](media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="8fd09-188">ポリシー ヒントを構成するためのオプション</span><span class="sxs-lookup"><span data-stu-id="8fd09-188">Options for configuring policy tips</span></span>

<span data-ttu-id="8fd09-189">DLP ポリシー内の各ルールに関して、次の事柄を行うポリシー ヒントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-189">For each rule in a DLP policy, you can configure policy tips to:</span></span>
  
- <span data-ttu-id="8fd09-p118">コンテンツが DLP ポリシーと競合していることをユーザーに通知して、競合を解決するアクションを実行できるようにします。既定のテキスト (下記の表を参照) を使用するか、または組織の特定のポリシーに関するユーザー設定のテキストを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p118">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict. You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>
    
- <span data-ttu-id="8fd09-p119">ユーザーによる DLP ポリシーの上書きを許可します。必要に応じて、次のことも行えます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p119">Allow the person to override the DLP policy. Optionally, you can:</span></span>
    
  - <span data-ttu-id="8fd09-p120">ポリシーを無効にするための業務上の正当な理由の入力をユーザーに求めることができます。この情報はログに記録され、セキュリティ/コンプライアンス センターの **[レポート]** セクションの DLP レポートで確認できます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p120">Require the person to enter a business justification for overriding the policy. This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span> 
    
  - <span data-ttu-id="8fd09-p121">ユーザーが誤検知を報告し、DLP ポリシーを上書きできるようにします。この情報はレポート用にも記録されるので、誤検知を使用してルールを微調整できます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p121">Allow the person to report a false positive and override the DLP policy. This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>
    
![ポリシー ヒント オプション](media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
<span data-ttu-id="8fd09-199">たとえば、個人を特定できる情報 (PII) を検出する DLP ポリシーを OneDrive for Business サイトに適用する場合、このポリシーに次の 3 つのルールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-199">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>
  
1. <span data-ttu-id="8fd09-p122">最初のルール:5 個以下の対象機密情報インスタンスがドキュメントで検出され、ドキュメントが組織内のユーザーと共有されている場合、[**通知を送信**] アクションによってポリシー ヒントが表示されます。ポリシー ヒントについては、上書きオプションは必要ありません。このルールは単にユーザーに通知を行うだけで、アクセスをブロックするわけではないからです。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p122">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip. For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span> 
    
2. <span data-ttu-id="8fd09-p123">2 番目のルール: 5 個を超える対象機密情報インスタンスがドキュメントで検出され、組織内のユーザーとドキュメントを共有する場合、**[コンテンツへのアクセスの禁止]** アクションによってファイルのアクセス許可が制限され、**[通知の送信]** アクションでは業務上の理由を提供することによってこのルールのアクションの上書きをユーザーに許可します。場合によっては、組織のビジネスにおいて内部ユーザーが PII データを共有する必要が生じ、DLP ポリシーによってその作業をブロックしたくないことがあります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p123">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification. Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span> 
    
3. <span data-ttu-id="8fd09-p124">3 番目のルール:5 個を超える対象機密情報インスタンスがドキュメントで検出され、組織外のユーザーとドキュメントを共有する場合、[**コンテンツへのアクセスの禁止**] アクションによってファイルのアクセス許可が制限され、[**通知の送信**] アクションではこのルールのアクションの上書きをユーザーに許可しません。情報が外部共有されているためです。いかなる状況においても、組織内のユーザーが組織外で PII データを共有することを許可すべきではありません。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p124">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally. Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span> 
    
<span data-ttu-id="8fd09-206">ルールを上書きするポリシー ヒントを使用する際に把握しておくべきいくつかの点を以下に記します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-206">Here are some fine points to understand about using a policy tip to override a rule:</span></span>
  
- <span data-ttu-id="8fd09-207">上書きオプションはルールごとのオプションで、対象ルール内のすべてのアクションを上書きします (ただし、上書きできない通知の送信は除きます)。</span><span class="sxs-lookup"><span data-stu-id="8fd09-207">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>
    
- <span data-ttu-id="8fd09-p125">コンテンツが 1 つの DLP ポリシー内の複数のルールに一致する可能性がありますが、その場合には最も制限的で優先順位の高いルールのポリシー ヒントのみが表示されます。たとえば、単に通知を送信するルールのポリシー ヒントよりも、コンテンツへのアクセスを禁止するルールのポリシー ヒントの方が優先して表示されます。これにより、ポリシー ヒントがカスケード表示されるのを防止します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p125">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="8fd09-211">	最も制限の厳しいルールでユーザーにルールを上書きすることを許可している場合は、このルールを上書きすることで、コンテンツに一致した他のルールもすべて上書きされます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-211">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="8fd09-212">OneDrive for Business サイトおよび SharePoint Online サイトのポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="8fd09-212">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="8fd09-213">OneDrive for Business サイトまたは SharePoint Online サイト上のドキュメントが DLP ポリシー内のルールに一致し、そのルールがポリシー ヒントを使用する場合、ポリシー ヒントは特別なアイコンをドキュメント上に表示します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-213">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>
  
1. <span data-ttu-id="8fd09-214">ルールがファイルに関する通知を送信する場合、警告アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-214">If the rule sends a notification about the file, the warning icon appears.</span></span>
    
2. <span data-ttu-id="8fd09-215">ルールがドキュメントへのアクセスをブロックする場合、ブロックされたアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-215">If the rule blocks access to the document, the blocked icon appears.</span></span>
    
![OneDrive アカウントのドキュメントのポリシー ヒント アイコン](media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
<span data-ttu-id="8fd09-217">文書で操作を行うには、アイテムを選択し、ページの右上隅にある **[情報]**![情報ウィンドウ アイコン](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) を選択し、詳細ウィンドウを開き、**ポリシー ヒント**を表示します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-217">To take action on a document, you can select an item \> choose **Information**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>
  
<span data-ttu-id="8fd09-218">ポリシー ヒントにはコンテンツに関する問題が一覧表示され、ポリシー ヒントにオプションが構成されている場合には、[**解決**] を検索してから、ポリシー ヒントの [**上書き**] または誤検知の [**レポート**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-218">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span> 
  
![ポリシー ヒントが表示されている情報ウィンドウ](media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![上書きするオプションを使用するポリシーのヒント](media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
<span data-ttu-id="8fd09-p126">DLP ポリシーがサイトと同期され、コンテンツが定期的かつ非同期的に評価されます。それで、DLP ポリシーを作成してからポリシー ヒントが表示されるまで少しの遅延があります。ポリシーを解決または上書きしてから、サイトのドキュメントのアイコンが消えるまで同様の遅延が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p126">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips. There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>
  
### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="8fd09-223">サイト上のポリシー ヒントの既定テキスト</span><span class="sxs-lookup"><span data-stu-id="8fd09-223">Default text for policy tips on sites</span></span>

<span data-ttu-id="8fd09-p127">既定では、ポリシー ヒントは、サイト上の項目に対して以下のようなテキストを表示します。通知テキストは、ルールごとに個別に構成されるため、表示されるテキストは、一致するルールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p127">By default, policy tips display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="8fd09-226">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="8fd09-226">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="8fd09-227">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="8fd09-227">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8fd09-228">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="8fd09-228">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="8fd09-229">このアイテムは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="8fd09-229">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="8fd09-230">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="8fd09-230">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="8fd09-p128">このアイテムは組織のポリシーと競合しています。この競合を解決しないと、このファイルへのアクセスがブロックされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p128">This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="8fd09-233">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="8fd09-233">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="8fd09-p129">このアイテムは組織内のポリシーと競合します。アイテムの所有者、最後に更新した人、プライマリ サイト コレクションの管理者を除くすべてのユーザーが、このアイテムへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p129">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="8fd09-236">サイトのポリシー ヒントのユーザー設定テキスト</span><span class="sxs-lookup"><span data-stu-id="8fd09-236">Custom text for policy tips on sites</span></span>

<span data-ttu-id="8fd09-p130">メール通知とは別に、ポリシー ヒントのテキストをカスタマイズすることができます。メール通知のユーザー設定テキストとは異なり (上のセクションを参照)、ポリシー ヒントのユーザー設定テキストでは HTML もトークンも使用できません。代わりに、ポリシー ヒントのユーザー設定テキストは、プレーン テキストで、256 文字の制限があります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p130">You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="8fd09-240">Outlook on the web および Outlook 2013 以降におけるポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="8fd09-240">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="8fd09-p131">Outlook on the web および Outlook 2013 以降で新しいメールを作成するとき、DLP ポリシーのルールに一致するコンテンツを追加し、そのルールがポリシー ヒントを使用する場合、ポリシー ヒントが表示されます。ポリシー ヒントは、メッセージの作成中、受信者の上のメッセージの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p131">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips. The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>
  
![作成中のメッセージの上部に表示されるポリシー ヒント](media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
<span data-ttu-id="8fd09-244">ポリシー ヒントは、次のように、機密情報がメッセージの本文、件名行、またはメッセージの添付ファイルに含まれる場合でも機能します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-244">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>
  
![添付ファイルが DLP ポリシーと競合していることを示すポリシー ヒント](media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
<span data-ttu-id="8fd09-246">ポリシー ヒントが上書きできるように構成されている場合は、**[詳細の表示]**、**[上書き]** を選択し、業務上の妥当性を入力するか、誤検知を報告し、**[上書き]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-246">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>
  
![展開されて上書きオプションを示す、メッセージ内のポリシー ヒント](media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![ポリシー ヒントを上書きできるポリシー ヒント ダイアログ](media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
<span data-ttu-id="8fd09-249">メールに機密情報を追加すると、機密情報を追加してからポリシー ヒントが表示されるまでに遅延が生じる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8fd09-249">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a><span data-ttu-id="8fd09-250">Outlook 2013 以降では、一部の条件に対するポリシー ヒントのみが表示</span><span class="sxs-lookup"><span data-stu-id="8fd09-250">Outlook 2013 and later supports showing policy tips for only some conditions</span></span>

<span data-ttu-id="8fd09-251">現在、Outlook 2013 以降では、次の条件に対するポリシー ヒントのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-251">Currently, Outlook 2013 and later supports showing policy tips only for these conditions:</span></span>

- <span data-ttu-id="8fd09-252">コンテンツが含まれている</span><span class="sxs-lookup"><span data-stu-id="8fd09-252">Content contains</span></span>
- <span data-ttu-id="8fd09-253">コンテンツが共有されている</span><span class="sxs-lookup"><span data-stu-id="8fd09-253">Content is shared</span></span>

<span data-ttu-id="8fd09-p132">現在、以下の追加条件のポリシー ヒント表示のサポートに取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p132">We're currently working on support for showing policy tips for additional conditions. These include:</span></span>

- <span data-ttu-id="8fd09-256">メールの添付ファイルのコンテンツをスキャンできなかった</span><span class="sxs-lookup"><span data-stu-id="8fd09-256">Any email attachment's content could not be scanned</span></span>
- <span data-ttu-id="8fd09-257">メールの添付ファイルのコンテンツのスキャンが完了しなかった</span><span class="sxs-lookup"><span data-stu-id="8fd09-257">Any email attachment's content didn't complete scanning</span></span>
- <span data-ttu-id="8fd09-258">添付ファイル拡張子が</span><span class="sxs-lookup"><span data-stu-id="8fd09-258">Attachment file extension is</span></span>
- <span data-ttu-id="8fd09-259">添付ファイルがパスワードで保護されている</span><span class="sxs-lookup"><span data-stu-id="8fd09-259">Attachment is password protected</span></span>
- <span data-ttu-id="8fd09-260">文書のプロパティが</span><span class="sxs-lookup"><span data-stu-id="8fd09-260">Document property is</span></span>
- <span data-ttu-id="8fd09-261">受信者ドメインが</span><span class="sxs-lookup"><span data-stu-id="8fd09-261">Recipient domain is</span></span>
- <span data-ttu-id="8fd09-262">送信者の IP アドレスが</span><span class="sxs-lookup"><span data-stu-id="8fd09-262">Sender IP address is</span></span>

<span data-ttu-id="8fd09-p133">これらのすべての条件は、条件がコンテンツに一致し、コンテンツに関して保護アクションが適用される Outlook で機能しますが、ユーザーへのポリシー ヒントの表示はまだサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p133">Note that all of these conditions work in Outlook, where they will match content and enforce protective actions on content. But showing policy tips to users is not yet supported.</span></span>
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="8fd09-265">Exchange 管理センターと Office 365 セキュリティ/コンプライアンス センターでのポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="8fd09-265">Policy tips in the Exchange admin center vs. the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="8fd09-p134">ポリシー ヒントは、Exchange 管理センターで作成される DLP ポリシーとメール フロー ルール、または Office 365 セキュリティ/コンプライアンス センターで作成される DLP ポリシーのいずれかによって機能します。両方ではありません。これは、これらのポリシーは異なる場所に保存されますが、ポリシー ヒントは 1 つの場所からのみ適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p134">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Office 365 Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="8fd09-p135">Exchange 管理センターでポリシー ヒントを構成した場合、Office 365 セキュリティ/コンプライアンス センターで構成するポリシー ヒントは、Exchange 管理センターでヒントをオフにしない限り、Outlook on the web および Outlook 2013 以降でユーザーに表示されません。これにより、Office 365 セキュリティ/コンプライアンス センターへの切り替えを選択するまで、現在の Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) が動作し続けます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p135">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Office 365 Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center. This ensures that your current Exchange mail flow rules (also known as transport rules) will continue to work until you choose to switch over to the Office 365 Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="8fd09-270">ポリシー ヒントは 1 つの場所からのみ適用されますが、Office 365 セキュリティ/コンプライアンス センターおよび Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、メール通知は常に送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8fd09-270">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Office 365 Security &amp; Compliance Center and the Exchange admin center.</span></span>
  
### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="8fd09-271">メールのポリシー ヒントの既定のテキスト</span><span class="sxs-lookup"><span data-stu-id="8fd09-271">Default text for policy tips in email</span></span>

<span data-ttu-id="8fd09-272">既定では、ポリシー ヒントは、次のようなテキストでメールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-272">By default, policy tips display text similar to the following for email.</span></span>

|<span data-ttu-id="8fd09-273">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="8fd09-273">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="8fd09-274">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="8fd09-274">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8fd09-275">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="8fd09-275">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="8fd09-276">メールは組織内のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="8fd09-276">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="8fd09-277">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="8fd09-277">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="8fd09-278">メールは組織内のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="8fd09-278">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="8fd09-279">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="8fd09-279">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="8fd09-280">メールは組織内のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="8fd09-280">Your email conflicts with a policy in your organization.</span></span>  <br/> |
   
## <a name="policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="8fd09-281">Excel 2016、PowerPoint 2016、Word 2016 におけるポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="8fd09-281">Policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="8fd09-p136">ユーザーがデスクトップ バージョンの Excel 2016、PowerPoint 2016、Word 2016 内の機密情報を扱っている場合、ポリシー ヒントによってコンテンツが DLP ポリシーと矛盾することをリアルタイムでユーザーに通知できます。そのためには以下のことが必要となります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p136">When people work with sensitive content in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016, policy tips can notify them in real time that the content conflicts with a DLP policy. This requires that:</span></span>
  
- <span data-ttu-id="8fd09-284">Office ドキュメントが OneDrive for Business サイトまたは SharePoint Online サイトに保存されていること。</span><span class="sxs-lookup"><span data-stu-id="8fd09-284">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>
    
- <span data-ttu-id="8fd09-285">サイトが、ポリシー ヒントを使用するように構成された DLP ポリシーに含まれていること。</span><span class="sxs-lookup"><span data-stu-id="8fd09-285">The site is included in a DLP policy that's configured to use policy tips.</span></span>
    
<span data-ttu-id="8fd09-286">これらの Office 2016 デスクトップ プログラムは、Office 365 から直接 DLP ポリシーを自動的に同期し、ドキュメントをスキャンして、DLP ポリシーと矛盾がないことを確認し、リアルタイムでポリシー ヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-286">These Office 2016 desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>
  
<span data-ttu-id="8fd09-287">DLP ポリシーにおけるポリシー ヒントの構成法によっては、ユーザーがポリシー ヒントを単に無視すること、業務上の理由を提供してまたは提供せずにポリシーを上書きすること、誤検知を報告することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-287">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>
  
<span data-ttu-id="8fd09-288">ポリシー ヒントは、メッセージ バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-288">Policy tips appear on the Message Bar.</span></span>
  
![メッセージ バーに Excel 2016 のポリシー ヒントが表示される](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="8fd09-290">ポリシー ヒントは、(**[ファイル]** タブ上の) Backstage ビューにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-290">And policy tips also appear in the Backstage view (on the **File** tab).</span></span> 
  
![Excel 2016 の Backstage にポリシー ヒントが表示される](media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
<span data-ttu-id="8fd09-292">DLP ポリシーのポリシー ヒントにこれらのオプションが設定されている場合、[**解決**] を選択した後、ポリシー ヒントの [**上書き**]、または誤検知の [**レポート**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8fd09-292">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span> 
  
![Excel 2016 の Backstage のポリシー ヒントに関するオプション](media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
<span data-ttu-id="8fd09-p137">こうした各 Office 2016 デスクトップ プログラムでは、ユーザーは、ポリシー ヒントを無効にすることを選択できます。無効にすると、通知を単に行うポリシー ヒントはメッセージ バーにも Backstage ビュー ([**ファイル**] タブ) にも表示されません。ただし、ブロックおよび上書きに関するポリシー ヒントは依然表示され、電子メール通知も引き続き受け取ります。さらに、ポリシー ヒントを無効にしても、適用されている DLP ポリシーがドキュメントに対して無効になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p137">In each of these Office 2016 desktop programs, people can choose to turn off policy tips. If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab). However, policy tips about blocking and overriding will still appear, and they will still receive the email notification. In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span> 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="8fd09-298">Excel 2016、PowerPoint 2016、Word 2016 におけるポリシー ヒントの既定テキスト</span><span class="sxs-lookup"><span data-stu-id="8fd09-298">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="8fd09-p138">既定では、ポリシー ヒントは、開いているドキュメントのメッセージ バーと Backstage ビューに次のようなテキストを表示します。通知テキストは、ルールごとに個別に構成されるため、表示されるテキストは、一致するルールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p138">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="8fd09-301">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="8fd09-301">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="8fd09-302">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="8fd09-302">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8fd09-303">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="8fd09-303">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="8fd09-p139">このファイルは組織内のポリシーと競合します。詳細については、**[ファイル]** メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p139">This file conflicts with a policy in your organization. Go to the **File** menu for more information.  </span></span><br/> |
|<span data-ttu-id="8fd09-306">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="8fd09-306">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="8fd09-p140">このファイルは組織内のポリシーと競合します。この競合を解決しないと、このファイルへのアクセスがブロックされる可能性があります。詳細については、**[ファイル]** メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p140">This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  </span></span><br/> |
|<span data-ttu-id="8fd09-310">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="8fd09-310">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="8fd09-p141">このファイルは組織内のポリシーと競合します。この競合を解決しないと、このファイルへのアクセスがブロックされる可能性があります。詳細については、**[ファイル]** メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p141">This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  </span></span><br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="8fd09-314">Excel 2016、PowerPoint 2016、Word 2016 におけるポリシー ヒントのユーザー設定テキスト</span><span class="sxs-lookup"><span data-stu-id="8fd09-314">Custom text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="8fd09-p142">メール通知とは別に、ポリシー ヒントのテキストをカスタマイズすることができます。メール通知のユーザー設定テキストとは異なり (上のセクションを参照)、ポリシー ヒントのユーザー設定テキストでは HTML もトークンも使用できません。代わりに、ポリシー ヒントのユーザー設定テキストは、プレーン テキストで、256 文字の制限があります。</span><span class="sxs-lookup"><span data-stu-id="8fd09-p142">You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="8fd09-318">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8fd09-318">More information</span></span>

- [<span data-ttu-id="8fd09-319">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="8fd09-319">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="8fd09-320">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="8fd09-320">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="8fd09-321">FCI または他のプロパティが使用されているドキュメントを保護する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="8fd09-321">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="8fd09-322">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="8fd09-322">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="8fd09-323">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="8fd09-323">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    

