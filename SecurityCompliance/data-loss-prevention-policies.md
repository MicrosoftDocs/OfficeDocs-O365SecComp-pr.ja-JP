---
title: データ損失防止ポリシーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 1966b2a7-d1e2-4d92-ab61-42efbb137f5e
description: office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) ポリシーを使用すると、office 365 全体で機密情報を識別、監視、および自動保護することができます。
ms.openlocfilehash: bf30e7de625903c3cce53407901f627ef1345d66
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218977"
---
# <a name="overview-of-data-loss-prevention-policies"></a><span data-ttu-id="81377-103">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="81377-103">Overview of data loss prevention policies</span></span>

<span data-ttu-id="81377-p101">ビジネス標準および業界の規制に準拠するために、組織は機密情報を保護し、不注意による開示を防止する必要があります。組織外に漏洩しないようにする機密情報の例には、クレジットカード番号、社会保障番号、医療記録などの財務データまたは個人を特定できる情報 (PII) があります。office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) ポリシーを使用すると、office 365 全体で機密情報を識別、監視、および自動保護することができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p101">To comply with business standards and industry regulations, organizations need to protect sensitive information and prevent its inadvertent disclosure. Examples of sensitive information that you might want to prevent from leaking outside your organization include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>
  
<span data-ttu-id="81377-107">DLP ポリシーを使用すると、以下のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="81377-107">With a DLP policy, you can:</span></span>
  
- <span data-ttu-id="81377-108">**Exchange online、SharePoint Online、OneDrive for business などのさまざまな場所で機密情報を識別します。**</span><span class="sxs-lookup"><span data-stu-id="81377-108">**Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, and OneDrive for Business.**</span></span>
    
    <span data-ttu-id="81377-109">たとえば、任意の onedrive for business サイトに保存されているクレジットカード番号を含むドキュメントを特定したり、特定のユーザーの onedrive サイトのみを監視したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="81377-109">For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.</span></span>
    
- <span data-ttu-id="81377-110">**機密情報を誤って共有することを防ぎます**。</span><span class="sxs-lookup"><span data-stu-id="81377-110">**Prevent the accidental sharing of sensitive information**.</span></span> 
    
    <span data-ttu-id="81377-111">たとえば、組織外のユーザーと共有している正常性レコードが含まれているドキュメントまたは電子メールを特定し、そのドキュメントへのアクセスを自動的にブロックしたり、電子メールの送信をブロックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="81377-111">For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.</span></span>
    
- <span data-ttu-id="81377-112">**デスクトップ バージョンの Excel 2016、PowerPoint 2016、Word 2016 内の機密情報を監視し、保護します。**</span><span class="sxs-lookup"><span data-stu-id="81377-112">**Monitor and protect sensitive information in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016.**</span></span>
    
    <span data-ttu-id="81377-p102">Exchange online、SharePoint Online、OneDrive for business の場合と同様に、これらの Office 2016 デスクトッププログラムには、機密情報を識別し、DLP ポリシーを適用するための同じ機能が含まれています。DLP は、ユーザーがこれらの Office 2016 プログラムでコンテンツを共有するときの継続的な監視を提供します。</span><span class="sxs-lookup"><span data-stu-id="81377-p102">Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office 2016 desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office 2016 programs.</span></span>
    
- <span data-ttu-id="81377-115">**ユーザーがワークフローを中断せずに、コンプライアンスを準拠しつづける方法を学ぶよう支援します。**</span><span class="sxs-lookup"><span data-stu-id="81377-115">**Help users learn how to stay compliant without interrupting their workflow.**</span></span>
    
    <span data-ttu-id="81377-p103">ユーザーに対して、DLP ポリシーについての教育を行い、作業をブロックすることなく、準拠を維持することができます。たとえば、機密情報を含むドキュメントをユーザーが共有しようとすると、DLP ポリシーによって電子メール通知が送信されます。また、ビジネスがある場合にポリシーを上書きすることができるように、ドキュメントライブラリのコンテキストでポリシーヒントを表示することができます。位置.outlook on the web、outlook 2013 以降、Excel 2016、PowerPoint 2016、および Word 2016 にも同じポリシーヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81377-p103">You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook 2013 and later, Excel 2016, PowerPoint 2016, and Word 2016.</span></span>
    
- <span data-ttu-id="81377-119">**組織の dlp ポリシーに一致するコンテンツを示す DLP レポートを表示します。**</span><span class="sxs-lookup"><span data-stu-id="81377-119">**View DLP reports showing content that matches your organization's DLP policies.**</span></span>
    
    <span data-ttu-id="81377-p104">組織が DLP ポリシーに準拠しているかどうかを評価するために、各ポリシーとルールが一定期間に何回一致しているかを確認できます。DLP ポリシーを使用して、ユーザーがポリシーヒントを上書きし、誤検知を報告できる場合は、ユーザーが報告した情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="81377-p104">To assess how your organization is complying with a DLP policy, you can see how many matches each policy and rule has over time. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported.</span></span>
    
<span data-ttu-id="81377-122">Office 365 セキュリティ&amp;コンプライアンスセンターの [データ損失防止] ページで DLP ポリシーを作成して管理します。</span><span class="sxs-lookup"><span data-stu-id="81377-122">You create and manage DLP policies on the Data loss prevention page in the Office 365 Security &amp; Compliance Center.</span></span>
  
![Office 365 セキュリティ&amp; /コンプライアンスセンターのデータ損失防止ページ](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a><span data-ttu-id="81377-124">DLP ポリシーの内容</span><span class="sxs-lookup"><span data-stu-id="81377-124">What a DLP policy contains</span></span>

<span data-ttu-id="81377-125">DLP ポリシーにはいくつかの基本的な内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="81377-125">A DLP policy contains a few basic things:</span></span>
  
- <span data-ttu-id="81377-126">Exchange online、SharePoint online、OneDrive for business サイトなどのコンテンツの**場所**を保護する場所。</span><span class="sxs-lookup"><span data-stu-id="81377-126">Where to protect the content - **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites.</span></span> 
    
- <span data-ttu-id="81377-127">**ルール**を適用してコンテンツを保護するタイミングと方法。ルールは次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="81377-127">When and how to protect the content by enforcing **rules** comprised of:</span></span> 
    
  - <span data-ttu-id="81377-128">ルールを適用する前にコンテンツを一致させる必要がある**条件**。たとえば、組織外の人と共有されている社会保障番号を含むコンテンツのみを検索します。</span><span class="sxs-lookup"><span data-stu-id="81377-128">**Conditions** the content must match before the rule is enforced -- for example, look only for content containing Social Security numbers that's been shared with people outside your organization.</span></span> 
    
  - <span data-ttu-id="81377-129">**アクション** 条件に一致するコンテンツが検出されるときにルールで自動実行されるアクションです。たとえば、ドキュメントに対するアクセスをブロックし、ユーザーとコンプライアンスの担当者の両方に電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="81377-129">**Actions** that you want the rule to take automatically when content matching the conditions is found -- for example, block access to the document and send both the user and compliance officer an email notification.</span></span> 
    
<span data-ttu-id="81377-130">ルールを使用して特定の保護要件を満たすことができます。その後、DLP ポリシーを使用して、一般的な保護要件 (特定の規制に準拠するために必要なすべてのルールなど) をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="81377-130">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="81377-p105">たとえば、健康保険の携行性と責任に関する法律 (HIPAA) の対象になる情報の存在を検出するのに役立つ DLP ポリシーがあるとします。この DLP ポリシーにより、組織外のユーザーと共有している機密情報を含むドキュメントを検索することによって、すべての SharePoint Online サイトとすべての OneDrive for business サイト (where) で HIPAA データを保護することができます (条件) を行い、ドキュメントへのアクセスをブロックし、通知を送信します (アクション)。これらの要件は個別のルールとして格納され、管理とレポートを簡素化する DLP ポリシーとしてまとめられています。</span><span class="sxs-lookup"><span data-stu-id="81377-p105">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA). This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions). These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![図は、DLP ポリシーに場所とルールが含まれていることを示しています。](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a><span data-ttu-id="81377-135">場所</span><span class="sxs-lookup"><span data-stu-id="81377-135">Locations</span></span>

<span data-ttu-id="81377-p106">DLP ポリシーは、情報が Exchange online、SharePoint Online、OneDrive for business のいずれにあるかにかかわらず、Office 365 全体の機密情報を検索して保護することができます。すべての SharePoint サイトまたは OneDrive アカウント、特定のサイトまたはアカウントのみ、またはすべてのメールボックスを保護することを簡単に選択できます。特定のユーザーのメールボックスのみを選択することはまだできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="81377-p106">A DLP policy can find and protect sensitive information across Office 365, whether that information is located in Exchange Online, SharePoint Online, or OneDrive for Business. You can easily choose to protect all SharePoint sites or OneDrive accounts, just specific sites or accounts, or all mailboxes. Note that it's not yet possible to select just the mailboxes of specific users.</span></span>
  
![DLP ポリシーを適用できる場所のオプション](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
<span data-ttu-id="81377-p107">特定の SharePoint サイトまたは OneDrive アカウントを含めるか除外するかを選択すると、DLP ポリシーに含めることができるのは、そのような包含と除外を100以内にする必要があることに注意してください。この制限は存在しますが、組織全体のポリシーまたは場所全体に適用されるポリシーのいずれかを適用することによって、この制限を超えることができることを理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="81377-p107">Note that if you choose to include or exclude specific SharePoint sites or OneDrive accounts, a DLP policy can contain no more than 100 such inclusions and exclusions. Although this limit exists, understand that you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="rules"></a><span data-ttu-id="81377-142">ルール</span><span class="sxs-lookup"><span data-stu-id="81377-142">Rules</span></span>

<span data-ttu-id="81377-p108">ルールは、組織のコンテンツに対するビジネス要件を強制します。ポリシーには1つ以上のルールが含まれており、各ルールは条件とアクションで構成されます。各ルールの条件が満たされると、アクションが自動的に実行されます。ルールは、各ポリシーの優先度の高いルールから順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="81377-p108">Rules are what enforce your business requirements on your organization's content. A policy contains one or more rules, and each rule consists of conditions and actions. For each rule, when the conditions are met, the actions are taken automatically. Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="81377-147">また、ルールによって、コンテンツがルールに一致したことをユーザーに通知するオプション (ポリシーヒントと電子メール通知を含む) と管理者 (電子メールインシデントレポート付き) も表示されます。</span><span class="sxs-lookup"><span data-stu-id="81377-147">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="81377-148">以下に説明するルールのコンポーネントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="81377-148">Here are the components of a rule, each explained below.</span></span>
  
![DLP ルールエディターのセクション](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="81377-150">条件</span><span class="sxs-lookup"><span data-stu-id="81377-150">Conditions</span></span>

<span data-ttu-id="81377-p109">条件は、探している情報の種類と、アクションを実行するタイミングを決定するので重要です。たとえば、コンテンツに10を超える番号が含まれておらず、組織外のユーザーと共有されている場合を除き、パスポート番号を含むコンテンツを無視することができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p109">Conditions are important because they determine what types of information you're looking for, and when to take an action. For example, you might choose to ignore content containing passport numbers unless the content contains more than ten such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="81377-p110">条件は、検索している機密情報の種類や、ドキュメントの共有者など、**コンテンツ**に焦点\*\*\*\* を当てています。条件を使用して、さまざまなアクションをさまざまなリスクレベルに割り当てることができます。たとえば、内部的に共有されている機密コンテンツはリスクが低く、組織外のユーザーと共有する機密コンテンツよりも少ないアクションを必要とする場合があります。</span><span class="sxs-lookup"><span data-stu-id="81377-p110">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with. You can use conditions to assign different actions to different risk levels -- for example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![利用可能な DLP 条件の一覧](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="81377-156">以下の内容を判断できる条件が使用可能になっています。</span><span class="sxs-lookup"><span data-stu-id="81377-156">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="81377-157">コンテンツには、種類の機密情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81377-157">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="81377-p111">コンテンツにはラベルが含まれています。詳細については、「 [DLP ポリシーの条件としてラベルを使用する](data-loss-prevention-policies.md#label)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81377-p111">Content contains a label. For more information, see the below section [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#label).</span></span>
    
- <span data-ttu-id="81377-160">コンテンツが組織の内または外のユーザーと共有されている。</span><span class="sxs-lookup"><span data-stu-id="81377-160">Content is shared with people outside or inside your organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="81377-161">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="81377-161">Types of sensitive information</span></span>

<span data-ttu-id="81377-p112">DLP ポリシーは、機密情報の**種類**として定義された機密情報を保護するのに役立ちます。Office 365 には、クレジットカード番号、銀行口座番号、国民 ID 番号、パスポート番号など、多くの異なる地域にわたる多くの一般的な機密情報の種類の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81377-p112">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**. Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![使用できる機密情報の種類の一覧](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="81377-p113">DLP ポリシーは、クレジットカード番号などの機密情報の種類を検索するときに、単に16桁の数字を検索するだけではありません。各機密情報の種類は、次の組み合わせを使用して定義および検出されます。</span><span class="sxs-lookup"><span data-stu-id="81377-p113">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number. Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="81377-167">キーワード</span><span class="sxs-lookup"><span data-stu-id="81377-167">Keywords</span></span>
    
- <span data-ttu-id="81377-168">内部関数。チェックサムや構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="81377-168">Internal functions to validate checksums or composition</span></span>
    
- <span data-ttu-id="81377-169">パターン一致を検索するための正規表現の評価</span><span class="sxs-lookup"><span data-stu-id="81377-169">Evaluation of regular expressions to find pattern matches</span></span>
    
- <span data-ttu-id="81377-170">その他のコンテンツの検査</span><span class="sxs-lookup"><span data-stu-id="81377-170">Other content examination</span></span>
    
<span data-ttu-id="81377-171">これにより、DLP 検出によって高い精度が得られますが、これによって、人々の作業を中断できる誤検知の数が減少します。</span><span class="sxs-lookup"><span data-stu-id="81377-171">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="81377-172">操作</span><span class="sxs-lookup"><span data-stu-id="81377-172">Actions</span></span>

<span data-ttu-id="81377-173">コンテンツがルールの条件に一致する場合、コンテンツを自動的に保護するアクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="81377-173">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![使用できる DLP アクションの一覧](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="81377-175">アクションを使用できるようになったので、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="81377-175">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="81377-p114">**コンテンツへのアクセスを制限する**サイトコンテンツの場合、サイトコレクションの管理者、ドキュメントの所有者、およびドキュメントを最後に変更したユーザーを除くすべてのユーザーに対して、ドキュメントのアクセス許可が制限されていることを意味します。これらのユーザーは、ドキュメントから機密情報を削除したり、他の改善アクションを実行したりすることができます。ドキュメントが準拠している場合は、元のアクセス許可が自動的に復元されます。ドキュメントへのアクセスがブロックされると、ドキュメントはサイト上のライブラリに特別なポリシーヒントアイコンと共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="81377-p114">**Restrict access to the content** For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document. These people can remove the sensitive information from the document or take other remedial action. When the document is in compliance, the original permissions will be automatically restored. When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
    ![ドキュメントへのアクセスがブロックされていることを示すポリシーのヒント](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    <span data-ttu-id="81377-p115">電子メールコンテンツの場合、このアクションはメッセージの送信をブロックします。DLP ルールの構成方法に応じて、送信者には NDR が表示されるか、または (ルールが通知を使用している場合は) ポリシーヒントや電子メール通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="81377-p115">For email content, this action blocks the message from being sent. Depending on how the DLP rule is configured, the sender will see an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
    ![承認されていない受信者をメッセージから削除する必要があることを警告します。](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="81377-184">ユーザー通知とユーザーの優先</span><span class="sxs-lookup"><span data-stu-id="81377-184">User notifications and user overrides</span></span>

<span data-ttu-id="81377-p116">通知と上書きを使用して、ユーザーに DLP ポリシーについての教育を行い、作業をブロックすることなく準拠したままにすることができます。たとえば、機密情報を含むドキュメントをユーザーが共有しようとすると、DLP ポリシーによって電子メール通知が送信されます。また、ビジネスがある場合にポリシーを上書きすることができるように、ドキュメントライブラリのコンテキストでポリシーヒントを表示することができます。位置.</span><span class="sxs-lookup"><span data-stu-id="81377-p116">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![DLP ルールエディターのユーザー通知とユーザーオーバーライドのセクション](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="81377-p117">電子メールは、コンテンツを送信、共有、または最終変更したユーザー、サイトコンテンツ、サイトコレクション管理者、およびドキュメント所有者に通知することができます。また、電子メール通知から選択したものを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p117">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner. In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="81377-190">電子メール通知の送信に加えて、ユーザー通知にはポリシーヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81377-190">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="81377-191">outlook 2013 以降および web 上の outlook。</span><span class="sxs-lookup"><span data-stu-id="81377-191">In Outlook 2013 and later and Outlook on the web.</span></span>
    
- <span data-ttu-id="81377-192">SharePoint Online または OneDrive for business サイト上のドキュメントの場合。</span><span class="sxs-lookup"><span data-stu-id="81377-192">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="81377-193">Excel 2016、PowerPoint 2016、および Word 2016 で、DLP ポリシーに含まれるサイトにドキュメントが格納されている場合。</span><span class="sxs-lookup"><span data-stu-id="81377-193">In Excel 2016, PowerPoint 2016, and Word 2016, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="81377-p118">電子メール通知とポリシーヒントは、コンテンツが DLP ポリシーと競合する理由について説明します。選択した場合、電子メール通知とポリシーヒントを使用すると、ユーザーが誤検知を報告してルールを上書きしたり、業務上の理由を提供したりすることができます。これにより、ユーザーに DLP ポリシーについての教育を行い、ユーザーの作業を妨げることなくそれらを適用することができます。コンプライアンス担当者が定期的に情報をレビューできるように、上書きおよび誤検知に関する情報もレポート (DLP レポートを参照) およびインシデントレポート (次のセクション) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="81377-p118">The email notification and policy tip explain why content conflicts with a DLP policy. If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification. This can help you educate users about your DLP policies and enforce them without preventing people from doing their work. Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="81377-198">OneDrive for business アカウントのポリシーヒントは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="81377-198">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![OneDrive アカウントのドキュメントのポリシーヒント](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a><span data-ttu-id="81377-200">インシデント レポート</span><span class="sxs-lookup"><span data-stu-id="81377-200">Incident reports</span></span>

<span data-ttu-id="81377-p119">ルールが一致する場合は、イベントの詳細を使用して、コンプライアンス責任者 (または任意のユーザー) にインシデントレポートを送信できます。このレポートには、一致したアイテムに関する情報、ルールに一致した実際のコンテンツ、およびコンテンツを最後に変更したユーザーの名前が含まれます。電子メールメッセージの場合、このレポートには、DLP ポリシーに一致する元のメッセージも添付ファイルとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="81377-p119">When a rule is matched, you can send an incident report to your compliance officer (or any people you choose) with details of the event. This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content. For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>
  
![インシデント レポートを構成するためのページ](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="81377-205">グループ化演算子と論理演算子</span><span class="sxs-lookup"><span data-stu-id="81377-205">Grouping and logical operators</span></span>

<span data-ttu-id="81377-p120">多くの場合、DLP ポリシーには、米国の社会保障番号を含むすべてのコンテンツを特定するなどの簡単な要件があります。ただし、その他のシナリオでは、DLP ポリシーにより、より緩やかに定義されたデータを識別する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="81377-p120">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number. However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="81377-208">たとえば、米国の医療保険法 (HIPAA) の対象となるコンテンツを特定するには、次の情報を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81377-208">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="81377-209">米国の社会保障番号や薬品執行機関 (dea) 番号など、特定の種類の機密情報が含まれるコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="81377-209">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="81377-210">AND</span><span class="sxs-lookup"><span data-stu-id="81377-210">AND</span></span>
    
- <span data-ttu-id="81377-p121">患者の治療や、提供された医療サービスの説明など、識別が困難なコンテンツ。このコンテンツを特定するには、Diseases の国際分類 (icd-9-cm または icd-10 cm) のような非常に大きなキーワードリストのキーワードを一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="81377-p121">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided. Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="81377-p122">グループ化と論理演算子 (and、OR) を使用して、このような緩やかに定義されたデータを簡単に特定できます。DLP ポリシーを作成すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p122">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR). When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="81377-215">グループ機密情報の種類。</span><span class="sxs-lookup"><span data-stu-id="81377-215">Group sensitive information types.</span></span>
    
- <span data-ttu-id="81377-216">グループ内の機密情報の種類とグループの間の論理演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="81377-216">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="81377-217">グループ内での演算子の選択</span><span class="sxs-lookup"><span data-stu-id="81377-217">Choosing the operator within a group</span></span>

<span data-ttu-id="81377-218">グループ内では、ルールに一致するコンテンツについて、そのグループ内のすべての条件を満たす必要があるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="81377-218">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![グループ内のオペレーターを示すグループ](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="81377-220">グループを追加する</span><span class="sxs-lookup"><span data-stu-id="81377-220">Adding a group</span></span>

<span data-ttu-id="81377-221">グループを簡単に追加できます。グループには、そのグループ内に独自の条件と演算子を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="81377-221">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![[グループの追加] ボタン](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="81377-223">グループ間でのオペレーターの選択</span><span class="sxs-lookup"><span data-stu-id="81377-223">Choosing the operator between groups</span></span>

<span data-ttu-id="81377-224">グループ間では、ルールに一致するコンテンツについて、1つのグループまたはすべてのグループの条件を満たす必要があるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="81377-224">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="81377-225">たとえば、組み込みの**米国 HIPAA**ポリシーには、次のものを含むコンテンツを識別するためにグループ間で**and**演算子を使用するルールがあります。</span><span class="sxs-lookup"><span data-stu-id="81377-225">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="81377-226">グループ**PII 識別子**(少なくとも1つの SSN 番号**または**dea の番号)</span><span class="sxs-lookup"><span data-stu-id="81377-226">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="81377-227">**AND**</span><span class="sxs-lookup"><span data-stu-id="81377-227">**AND**</span></span>
    
- <span data-ttu-id="81377-228">グループ**医学条項**(少なくとも1つの ICD-9-センチキーワード**または**icd-10-センチキーワード)</span><span class="sxs-lookup"><span data-stu-id="81377-228">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![グループ間のオペレーターを示すグループ](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="81377-230">ルールが処理される優先度</span><span class="sxs-lookup"><span data-stu-id="81377-230">The priority by which rules are processed</span></span>

<span data-ttu-id="81377-p123">ポリシーでルールを作成する場合、各ルールには、作成された順序で優先度が割り当てられます。つまり、最初に作成されたルールの優先度、2番目に作成したルールの優先度が2番目になります。ルールを作成した後は、ルールを削除して再作成しない限り、その優先度を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="81377-p123">When you create rules in a policy, each rule is assigned a priority in the order in which it's created - meaning, the rule created first has first priority, the rule created second has second priority, and so on. After you create a rule, its priority can't be changed, except by deleting and re-creating it.</span></span>
  
![優先順位順のルール](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
<span data-ttu-id="81377-p124">コンテンツがルールに対して評価されない場合、ルールは優先順位に従って処理されます。コンテンツが複数のルールと一致する場合、ルールは優先順位に従って処理され、最も制限の厳しいアクションが適用されます。たとえば、コンテンツが次のすべてのルールに一致する場合は、ルール3が最も優先度の高いルールであるため、ルール3が適用されます。</span><span class="sxs-lookup"><span data-stu-id="81377-p124">When content is evaluated against rules, the rules are processed in priority order. If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced. For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="81377-237">ルール 1: ユーザーにのみ通知します。</span><span class="sxs-lookup"><span data-stu-id="81377-237">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="81377-238">ルール 2: ユーザーに通知し、アクセスを制限し、ユーザーによる上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="81377-238">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="81377-239">ルール 3: ユーザーに対して通知を行い、アクセスを制限し、ユーザーによる上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="81377-239">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="81377-240">ルール 4: ユーザーにのみ通知する</span><span class="sxs-lookup"><span data-stu-id="81377-240">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="81377-241">ルール 5: アクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="81377-241">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="81377-242">ルール 6: ユーザーに対して通知を行い、アクセスを制限し、ユーザーによる上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="81377-242">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="81377-243">この例では、最も制限の厳しいルールのみが適用されていても、すべてのルールの一致が監査ログに記録され、DLP レポートに表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="81377-243">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="81377-244">ポリシーヒントに関しては、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="81377-244">With respect to policy tips, note that:</span></span>
  
- <span data-ttu-id="81377-p125">最も高い優先度のポリシーヒントのみが表示されます。たとえば、コンテンツへのアクセスをブロックするルールからのポリシーヒントは、単に通知を送信するルールからのポリシーヒントに表示されます。これにより、ユーザーがポリシーヒントを重ねて表示するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p125">Only the policy tip from the highest priority, most restrictive rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="81377-248">	最も制限の厳しいルールでユーザーにルールを上書きすることを許可している場合は、このルールを上書きすることで、コンテンツに一致した他のルールもすべて上書きされます。</span><span class="sxs-lookup"><span data-stu-id="81377-248">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="81377-249">調整ルールを使用して、より簡単に、またはより簡単に一致するようにする</span><span class="sxs-lookup"><span data-stu-id="81377-249">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="81377-250">ユーザーが DLP ポリシーを作成して有効にした後は、次のような問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="81377-250">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="81377-251">機密情報の**ないコンテンツが**多すぎると、ルールに一致します。つまり、誤検知が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="81377-251">Too much content that **is not** sensitive information matches the rules - in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="81377-252">機密情報がルールに一致するコンテンツ**が**少なすぎる (つまり、保護アクションが機密情報に対して適用されない)。</span><span class="sxs-lookup"><span data-stu-id="81377-252">Too little content that **is** sensitive information matches the rules - in other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="81377-p126">これらの問題に対処するには、インスタンス数と一致精度を調整して、コンテンツがルールと一致するようにすることで、ルールを調整できます。ルールで使用される機密情報の種類ごとに、インスタンス数と一致精度の両方があります。</span><span class="sxs-lookup"><span data-stu-id="81377-p126">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules. Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="81377-255">インスタンス数</span><span class="sxs-lookup"><span data-stu-id="81377-255">Instance count</span></span>

<span data-ttu-id="81377-p127">インスタンス数は、特定の種類の機密情報がルールと一致するようにコンテンツを表示する必要があることを意味します。たとえば、1から9の一意の米国または英国のパスポート番号が識別される場合、コンテンツは以下のルールに一致します。</span><span class="sxs-lookup"><span data-stu-id="81377-p127">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule. For example, content will match the rule shown below if between 1 and 9 unique U.S. or U.K. passport numbers are identified.</span></span>
  
<span data-ttu-id="81377-p128">インスタンス数には、機密情報の種類とキーワードに**固有**の一致のみが含まれていることに注意してください。たとえば、電子メールに同じクレジットカード番号の10個のオカレンスが含まれている場合、その10回はクレジットカード番号の1つのインスタンスとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="81377-p128">Note that the instance count includes only **unique** matches for sensitive information types and keywords. For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span> 
  
<span data-ttu-id="81377-261">インスタンス数を使用してルールを調整するには、次のガイダンスがわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="81377-261">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="81377-p129">ルールをより簡単に一致させるには、**最小**数を減らすか、**最大**数を増やします。また、数値を削除することによって、 **max**を**任意**の値に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="81377-p129">To make the rule easier to match, decrease the **min** count and/or increase the **max** count. You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="81377-264">ルールが一致しにくくなるようにするには、**最小**数を増やします。</span><span class="sxs-lookup"><span data-stu-id="81377-264">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="81377-p130">通常は、低いインスタンス数 (たとえば、1-9) のルールでユーザー通知を送信するなど、制限の少ないアクションを使用します。また、より多くの制限付きアクション (ユーザーによる上書きを許可せずにコンテンツへのアクセスを制限するなど) を使用すると、より高いレベルのインスタンス数を持つルール (たとえば、10個など) になります。</span><span class="sxs-lookup"><span data-stu-id="81377-p130">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9). And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![ルールエディターのインスタンス数](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="81377-268">正確一致</span><span class="sxs-lookup"><span data-stu-id="81377-268">Match accuracy</span></span>

<span data-ttu-id="81377-p131">前述したように、機密情報の種類はさまざまな種類の証拠の組み合わせを使用して定義および検出されます。通常、機密情報の種類は、パターンと呼ばれる複数の組み合わせによって定義されます。より少ない証拠を必要とするパターンは、一致精度 (または信頼度) が低く、より多くの証拠が必要となるパターンの精度 (または信頼度が高い) になります。機密情報の種類ごとに使用される実際のパターンと信頼度の詳細については、「[機密情報の種類](what-the-sensitive-information-types-look-for.md)を調べる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81377-p131">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence. Commonly, a sensitive information type is defined by multiple such combinations, called patterns. A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level). To learn more about the actual patterns and confidence levels used by every sensitive information type, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
<span data-ttu-id="81377-273">たとえば、"クレジットカード番号" という名前の機密情報の種類は、次の2つのパターンで定義されます。</span><span class="sxs-lookup"><span data-stu-id="81377-273">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="81377-274">65% の信頼度が必要なパターン。</span><span class="sxs-lookup"><span data-stu-id="81377-274">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="81377-275">クレジットカード番号の形式の番号。</span><span class="sxs-lookup"><span data-stu-id="81377-275">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="81377-276">チェックサムを渡す数値。</span><span class="sxs-lookup"><span data-stu-id="81377-276">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="81377-277">85% の信頼度が必要なパターン。</span><span class="sxs-lookup"><span data-stu-id="81377-277">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="81377-278">クレジットカード番号の形式の番号。</span><span class="sxs-lookup"><span data-stu-id="81377-278">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="81377-279">チェックサムを渡す数値。</span><span class="sxs-lookup"><span data-stu-id="81377-279">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="81377-280">適切な形式のキーワードまたは有効期限の日付。</span><span class="sxs-lookup"><span data-stu-id="81377-280">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="81377-p132">ルールでは、これらの信頼レベル (または正確一致) を使用できます。通常は、一致精度の低いルールでユーザー通知を送信するなど、制限の少ないアクションを使用します。また、より正確に一致するルールを使用して、ユーザーによる上書きを許可することなくコンテンツへのアクセスを制限するなど、より制限の多いアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="81377-p132">You can use these confidence levels (or match accuracy) in your rules. Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy. And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="81377-284">クレジットカード番号などの特定の種類の機密情報がコンテンツで識別されると、1つの信頼レベルのみが返されることを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="81377-284">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="81377-285">すべての一致が1つのパターンに一致する場合は、そのパターンの信頼レベルが返されます。</span><span class="sxs-lookup"><span data-stu-id="81377-285">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="81377-p133">複数のパターンに一致するものがある場合 (つまり、2つの異なる信頼度レベルに一致するものがある場合)、1つのパターンだけを超える信頼レベルが返されます。これは厄介な部分です。たとえば、クレジットカードの場合、65% と 85% の両方のパターンが一致した場合は、その機密情報の種類に対して返される信頼度が 90% を超えているため、より多くの証拠がより信頼度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="81377-p133">If there are matches for more than one pattern (i.e., there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned. This is the tricky part. For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="81377-p134">そのため、クレジットカードに対して2つの相互排他的なルールを作成したい場合は、その精度は 65%、精度は 85% と一致しますが、精度の範囲は次のようになります。最初のルールでは、65% パターンに一致するものが1つだけ抽出されます。2番目のルールは、**少なくとも1つ**の 85% 一致に一致するものを取得し、信頼度の低い他の一致を**持つ可能性が**あります。</span><span class="sxs-lookup"><span data-stu-id="81377-p134">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this. The first rule picks up only matches of the 65% pattern. The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![一致精度の範囲が異なる2つのルール](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="81377-293">このような理由により、異なる一致 accuracies を持つルールを作成するためのガイダンスは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="81377-293">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="81377-294">通常、最小の信頼レベルは、 **min**および**max** (範囲ではない) に対して同じ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="81377-294">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="81377-295">最高度の信頼度は、通常、信頼度の低いものから100までの範囲です。</span><span class="sxs-lookup"><span data-stu-id="81377-295">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="81377-296">通常、信頼レベルは、信頼度の低いものから、信頼度の高いレベルのすぐ下までの範囲です。</span><span class="sxs-lookup"><span data-stu-id="81377-296">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="81377-297">DLP ポリシーにおける条件としてのラベルの使用</span><span class="sxs-lookup"><span data-stu-id="81377-297">Using a label as a condition in a DLP policy</span></span>

<span data-ttu-id="81377-298">ラベルを作成して、次のようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="81377-298">You can create a label and then:</span></span>
  
- <span data-ttu-id="81377-299">これを**公開**して、エンドユーザーがラベルをコンテンツに表示したり、手動で適用したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="81377-299">**Publish** it, so that end users can see and manually apply the label to content.</span></span> 
    
- <span data-ttu-id="81377-300">選択した条件に一致するコンテンツに**自動適用**します。</span><span class="sxs-lookup"><span data-stu-id="81377-300">**Auto-apply** it to content that matches the conditions that you choose.</span></span> 
    
<span data-ttu-id="81377-301">ラベルの詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81377-301">For more information about labels, see [Overview of retention labels](labels.md).</span></span>
  
<span data-ttu-id="81377-p135">ラベルを作成した後、そのラベルを DLP ポリシーの条件として使用できます。たとえば、次のような理由が考えられることがあります。</span><span class="sxs-lookup"><span data-stu-id="81377-p135">After you create a label, you can then use that label as a condition in your DLP policies. For example, you might want to do this because:</span></span>
  
- <span data-ttu-id="81377-p136">**機密**という名前のラベルを発行したので、組織内のユーザーは機密の電子メールやドキュメントにラベルを手動で適用することができます。このラベルを DLP ポリシーの条件として使用することにより、 **Confidential**というラベルが付けられたコンテンツを組織外のユーザーと共有することを制限できます。</span><span class="sxs-lookup"><span data-stu-id="81377-p136">You published a label named **Confidential**, so that people in your organization can manually apply the label to confidential email and documents. By using this label as a condition in your DLP policy, you can restrict content labeled **Confidential** from being shared with people outside your organization.</span></span> 
    
- <span data-ttu-id="81377-p137">その名前のプロジェクト用に**Alpine House**という名前のラベルを作成し、そのラベルを "alpine house" というキーワードを含むコンテンツに自動的に適用しました。このラベルを DLP ポリシーの条件として使用すると、このコンテンツを組織外のユーザーと共有しようとしているときに、エンドユーザーにポリシーヒントを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p137">You created a label named **Alpine House** for a project of that name, and then applied that label automatically to content containing the keywords "Alpine House". By using this label as a condition in your DLP policy, you can show a policy tip to end users when they're about to share this content with someone outside your organization.</span></span> 
    
- <span data-ttu-id="81377-p138">**Tax record**という名前のラベルを発行したので、レコード管理者は、レコードとして分類する必要があるコンテンツにラベルを手動で適用することができます。このラベルを DLP ポリシーの条件として使用することにより、このラベルを持つコンテンツを、itins や ssns などの他の種類の機密情報と共に検索できます。"**税レコード**" というラベルの付いたコンテンツに保護アクションを適用します。dlp レポートおよび監査ログデータから dlp ポリシーに関する詳細なアクティビティレポートを取得します。</span><span class="sxs-lookup"><span data-stu-id="81377-p138">You published a label named **Tax record**, so that your records manager can manually apply the label to content that needs to be classified as a record. By using this label as a condition in your DLP policy, you can look for content with this label in conjunction with other types of sensitive information such as ITINs or SSNs; apply protection actions to content labeled **Tax record**; and get detailed activity reports about the DLP policy from the DLP reports and audit log data.</span></span> 
    
- <span data-ttu-id="81377-p139">**エグゼクティブリーダーチーム**という名前のラベルを、重役グループの Exchange メールボックスと OneDrive アカウントに公開しました。このラベルを DLP ポリシーの条件として使用することにより、コンテンツとユーザーの同じサブセットに対して保存と保護の操作の両方を適用できます。</span><span class="sxs-lookup"><span data-stu-id="81377-p139">You published a label named **Executive Leadership Team - Sensitive** to the Exchange mailboxes and OneDrive accounts of a group of executives. By using this label as a condition in your DLP policy, you can enforce both retention and protection actions on the same subset of content and users.</span></span> 
    
<span data-ttu-id="81377-312">DLP ルールの条件としてラベルを使用することで、コンテンツ、場所、ユーザーの特定のセットに対して、保護アクションを選択的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="81377-312">By using labels as a condition in your DLP rules, can you selectively enforce protection actions on a specific set of content, locations, or users.</span></span>
  
![条件としてラベルを](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a><span data-ttu-id="81377-314">機密ラベルのサポートが予定されています</span><span class="sxs-lookup"><span data-stu-id="81377-314">Support for sensitivity labels is coming</span></span>

<span data-ttu-id="81377-p140">現在、保持ラベルは、[機密ラベル](sensitivity-labels.md)ではなく、条件としてのみ使用できることに注意してください。この条件では、現在、機密ラベルを使用するためのサポートが稼働しています。</span><span class="sxs-lookup"><span data-stu-id="81377-p140">Note that you can currently use only a retention label as a condition, not a [sensitivity label](sensitivity-labels.md). We're currently working on support for using a sensitivity label in this condition.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="81377-317">この機能と他の機能との関係</span><span class="sxs-lookup"><span data-stu-id="81377-317">How this feature relates to other features</span></span>

<span data-ttu-id="81377-318">機密情報が含まれるコンテンツには、いくつかの機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="81377-318">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="81377-319">保持[ラベル](labels.md#applying-a-retention-label-automatically-based-on-conditions)と[アイテム保持ポリシー](retention-policies.md)の両方で、このコンテンツに**保持**アクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="81377-319">A [retention label](labels.md#applying-a-retention-label-automatically-based-on-conditions) and a [retention policy](retention-policies.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="81377-p141">DLP ポリシーは、このコンテンツに対して**保護**アクションを強制できます。これらの操作を実行する前に、DLP ポリシーでは、ラベルを含むコンテンツに加えて、他の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="81377-p141">A DLP policy can enforce **protection** actions on this content. And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![機密情報に適用できる機能の図](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="81377-p142">DLP ポリシーは、機密情報に適用されるラベルまたはアイテム保持ポリシーよりも豊富な検出機能を備えていることに注意してください。DLP ポリシーは、機密情報が含まれるコンテンツに対する保護アクションを強制でき、機密情報がコンテンツから削除されると、その保護アクションはコンテンツの次回のスキャン時に取り消されます。ただし、機密情報が含まれるコンテンツにアイテム保持ポリシーまたはラベルを適用すると、機密情報が削除されても、1回限りの操作が取り消されます。</span><span class="sxs-lookup"><span data-stu-id="81377-p142">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information. A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned. But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information's removed.</span></span>
  
<span data-ttu-id="81377-p143">DLP ポリシー内の条件としてラベルを使用することにより、そのラベルを持つコンテンツに対してアイテム保持と保護アクションの両方を適用できます。機密情報が含まれているコンテンツと同じように、ラベルと機密情報の種類の両方がコンテンツを分類するために使用するプロパティであると考えることができます。これにより、そのコンテンツにアクションを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p143">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label. You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![ラベルを条件として使用する DLP ポリシーの図](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="81377-329">簡易設定と詳細設定</span><span class="sxs-lookup"><span data-stu-id="81377-329">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="81377-330">DLP ポリシーを作成する場合は、[簡易] または [詳細設定] のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="81377-330">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="81377-331">**簡易設定**を使用すると、ルールエディタを使用してルールを作成または変更しなくても、最も一般的な種類の DLP ポリシーを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="81377-331">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="81377-332">**[詳細設定**] ルールエディターを使用して、DLP ポリシーのすべての設定を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="81377-332">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="81377-p144">このトピックでは、単純な設定と高度な設定がまったく同じように動作しますが、条件とアクションで構成されるルールを適用することによって、ルールエディターは表示されません。DLP ポリシーを簡単に作成する方法です。</span><span class="sxs-lookup"><span data-stu-id="81377-p144">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions -- only with simple settings, you don't see the rule editor. It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="81377-335">簡易設定</span><span class="sxs-lookup"><span data-stu-id="81377-335">Simple settings</span></span>

<span data-ttu-id="81377-p145">最も一般的な DLP シナリオは、機密情報を含むコンテンツを組織外のユーザーと共有したり、コンテンツにアクセスできるユーザーを制限するなどの自動的な修復操作を実行したりするためのポリシーを作成することです。エンドユーザーまたは管理者の通知を送信し、イベントを後で調査するために監査します。ユーザーは、DLP を使用して機密情報を不用意に公開しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p145">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remedial action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation. People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="81377-p146">この目標を実現するには、DLP ポリシーを作成するときに [**簡易設定を使用**する] を選択します。これらの設定により、ルールエディターに移行せずに、最も一般的な DLP ポリシーを実装するために必要なものすべてが提供されます。</span><span class="sxs-lookup"><span data-stu-id="81377-p146">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**. These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![簡易および詳細設定の DLP オプション](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="81377-341">詳細設定</span><span class="sxs-lookup"><span data-stu-id="81377-341">Advanced settings</span></span>

<span data-ttu-id="81377-342">カスタマイズした DLP ポリシーをさらに作成する必要がある場合は、[**詳細設定を使用**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="81377-342">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="81377-343">詳細設定では、各ルールのインスタンス数と一致精度 (信頼度) を含む、すべての可能なオプションを完全に制御できるルールエディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81377-343">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="81377-344">セクションにすばやく移動するには、ルールエディターのトップナビゲーションにある項目をクリックして、以下のセクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="81377-344">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP ルールエディターのトップナビゲーションメニュー](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="81377-346">DLP ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="81377-346">DLP policy templates</span></span>

<span data-ttu-id="81377-p147">DLP ポリシーを作成する最初の手順は、保護する情報を選択することです。DLP テンプレートから開始することで、新しいルールセットを最初から作成する作業を保存し、既定でどのような種類の情報を含める必要があるかを判断できます。その後、これらの要件を追加または変更して、組織の特定の要件を満たすようにルールを微調整することができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p147">The first step in creating a DLP policy is choosing what information to protect. By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default. You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="81377-p148">構成済みの DLP ポリシーテンプレートを使用すると、HIPAA データ、PCI DSS データ、グラムリーチブライ-なる Act データ、またはロケール固有の個人情報 (P.I.) など、特定の種類の機密情報を検出するのに役立ちます。一般的な種類の機密情報を簡単に見つけて保護できるように、Office 365 に含まれているポリシーテンプレートには、まず、開始するために必要な最も一般的な機密情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81377-p148">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.). To make it easy for you to find and protect common types of sensitive information, the policy templates included in Office 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![米国愛国者法のテンプレートにフォーカスがあるデータ損失防止ポリシーのテンプレートの一覧](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="81377-p149">組織に固有の要件がある場合もあります。その場合は、[**カスタムポリシー** ] オプションを選択することにより、最初から DLP ポリシーを作成できます。カスタムポリシーは空であり、premade ルールは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="81377-p149">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option. A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="81377-355">DLP ポリシーをテスト モードで段階的にロールアウトする</span><span class="sxs-lookup"><span data-stu-id="81377-355">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="81377-p150">DLP ポリシーを作成するときには、徐々にロールアウトして影響を評価し、それらを完全に適用する前に有効性をテストする必要があります。たとえば、新しい DLP ポリシーを使用して、ユーザーが作業を完了するためにアクセスする必要がある数千のドキュメントへのアクセスを誤ってブロックすることはありません。</span><span class="sxs-lookup"><span data-stu-id="81377-p150">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="81377-358">大きな影響を与える可能性が高い DLP ポリシーを作成しているときは、次の順序に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="81377-358">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="81377-p151">**ポリシーヒントを使用せずにテストモードで開始**してから、DLP レポートとインシデントレポートを使用して影響を評価します。DLP レポートを使用して、ポリシー一致の数、場所、種類、および重要度を表示できます。結果に基づいて、必要に応じてルールを微調整することができます。テストモードでは、DLP ポリシーは、組織で作業しているユーザーの生産性に影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="81377-p151">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="81377-p152">**通知とポリシーヒントを使用してテストモードに移動**します。これにより、コンプライアンスポリシーについてユーザーに指導し、適用されるルールを準備することができます。この段階では、ユーザーに誤検知を報告して、さらにルールを調整できるようにすることも要求できます。</span><span class="sxs-lookup"><span data-stu-id="81377-p152">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="81377-p153">ルールのアクションが適用され、コンテンツが保護されるように、**ポリシーに対して完全な強制を開始**します。引き続き DLP レポートとインシデントレポートまたは通知を監視して、結果が意図したとおりであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="81377-p153">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
![テスト モードを使用しポリシーで有効化するオプション](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
<span data-ttu-id="81377-p154">DLP ポリシーは、ポリシー内のすべてのルールに影響を与える任意の時点でオフにすることができます。ただし、ルールエディターで状態を切り替えることによって、各ルールを個別に無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="81377-p154">You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>
  
![ポリシー内のルールを無効にするオプション](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)
  
## <a name="dlp-reports"></a><span data-ttu-id="81377-371">DLP レポート</span><span class="sxs-lookup"><span data-stu-id="81377-371">DLP reports</span></span>

<span data-ttu-id="81377-p155">DLP ポリシーを作成して有効にした後、意図したとおりに動作していることを確認し、準拠した状態を維持することができます。dlp レポートを使用すると、時間の経過と共に dlp ポリシーとルールの一致数をすばやく表示でき、誤検知と上書きの数をすばやく表示できます。レポートごとに、場所、時間枠、および特定のポリシー、ルール、またはアクションに一致するものを抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="81377-p155">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant. With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides. For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="81377-375">DLP レポートによって、ビジネス上の洞察を得ることができ、同時に以下のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="81377-375">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="81377-376">特定の期間に絞り込み、スパイクや傾向の理由を理解します。</span><span class="sxs-lookup"><span data-stu-id="81377-376">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="81377-377">組織のコンプライアンスポリシーに違反するビジネスプロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="81377-377">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="81377-378">DLP ポリシーのビジネスに及ぼす影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="81377-378">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="81377-379">さらに、DLP レポートを使用すると、DLP ポリシーの実行時にそれらのポリシーを調整できます。</span><span class="sxs-lookup"><span data-stu-id="81377-379">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![セキュリティ/コンプライアンスセンターのレポートダッシュボード](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="81377-381">DLP ポリシーのしくみ</span><span class="sxs-lookup"><span data-stu-id="81377-381">How DLP policies work</span></span>

<span data-ttu-id="81377-p156">DLP は、(単純なテキスト スキャンだけでなく) 詳細なコンテンツ分析を使用して、機密情報を検出します。この詳細なコンテンツ分析は、キーワード一致、辞書一致、正規表現の評価、内部関数などの方式を使用して、DLP ポリシーに一致するコンテンツを検出します。使用しているデータのうち、ごくわずかな割合のデータのみが機密性が高いと見なされる可能性があります。DLP ポリシーは、他のコンテンツを使用した作業を妨害したり影響を与えたりすることなく、対象データのみを識別、監視し、自動的に保護できます。</span><span class="sxs-lookup"><span data-stu-id="81377-p156">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="81377-386">ポリシーの同期</span><span class="sxs-lookup"><span data-stu-id="81377-386">Policies are synced</span></span>

<span data-ttu-id="81377-387">セキュリティ&amp; /コンプライアンスセンターで DLP ポリシーを作成すると、そのポリシーは中央ポリシーストアに格納され、次のようにさまざまなコンテンツソースと同期されます。</span><span class="sxs-lookup"><span data-stu-id="81377-387">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="81377-388">Exchange Online および outlook on the web および outlook 2013 以降</span><span class="sxs-lookup"><span data-stu-id="81377-388">Exchange Online, and from there to Outlook on the web and Outlook 2013 and later</span></span>
    
- <span data-ttu-id="81377-389">OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="81377-389">OneDrive for Business sites</span></span>
    
- <span data-ttu-id="81377-390">SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="81377-390">SharePoint Online sites</span></span>
    
- <span data-ttu-id="81377-391">Office 2016 デスクトップ プログラム (Excel 2016、PowerPoint 2016、Word 2016)</span><span class="sxs-lookup"><span data-stu-id="81377-391">Office 2016 desktop programs (Excel 2016, PowerPoint 2016, and Word 2016)</span></span>
    
<span data-ttu-id="81377-392">ポリシーが正しい場所に同期されると、コンテンツの評価とアクションの適用が開始されます。</span><span class="sxs-lookup"><span data-stu-id="81377-392">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="81377-393">OneDrive for Business サイトと SharePoint Online サイトのポリシー評価</span><span class="sxs-lookup"><span data-stu-id="81377-393">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="81377-p157">SharePoint Online サイトと OneDrive for business サイトのすべてにおいて、ドキュメントは常に変更されています。これにより、継続的に作成、編集、共有などが行われます。これは、ドキュメントがいつでも、DLP ポリシーに競合するか、または準拠していることを意味します。たとえば、ユーザーは、チームサイトに機密情報が含まれていないドキュメントをアップロードできますが、後で、別のユーザーが同じドキュメントを編集して機密情報を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p157">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on. This means documents can conflict or become compliant with a DLP policy at any time. For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="81377-p158">このため、DLP ポリシーは、バックグラウンドでポリシーに一致しているかどうか頻繁にドキュメントを確認します。これを、非同期のポリシー評価と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="81377-p158">For this reason, DLP policies check documents for policy matches frequently in the background. You can think of this as asynchronous policy evaluation.</span></span>
  
<span data-ttu-id="81377-p159">そのしくみは次のとおりです。ユーザーがサイトでドキュメントを追加または変更すると、検索エンジンによってコンテンツがスキャンされ、後で検索できるようになります。これが発生していますが、機密情報のためにコンテンツもスキャンされ、共有されているかどうかが確認されます。検出された機密情報は検索インデックスに安全に格納されるため、コンプライアンスチームのみがアクセスできますが、一般的なユーザーにはアクセスできません。オンにした各 DLP ポリシーはバックグラウンドで実行され (非同期)、ポリシーに一致するコンテンツについては検索頻度がよくチェックされ、不注意によるリークから保護するアクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="81377-p159">Here's how it works. As people add or change documents in their sites, the search engine scans the content, so that you can search for it later. While this is happening, the content's also scanned for sensitive information and to check if it's shared. Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users. Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![DLP ポリシーがコンテンツを非同期で評価する方法を示す図](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<span data-ttu-id="81377-p160">最後に、ドキュメントが DLP ポリシーに矛盾し、その後 DLP ポリシーに準拠するようになることがあります。たとえば、ユーザーがドキュメントにクレジット カード番号を追加する場合、DLP ポリシーによってドキュメントへのアクセスが自動的にブロックされる可能性があります。しかしユーザーが後で機密情報を削除すると、次にドキュメントが対象ポリシーに対して再び評価されるときに、アクション (この例ではブロック) が自動的に取り消されます。</span><span class="sxs-lookup"><span data-stu-id="81377-p160">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="81377-p161">DLP は、インデックス処理可能なすべてのコンテンツを評価します。既定でクロールされるファイルの種類の詳細については、「既定のクロールされた[ファイル名拡張子」および「解析されたファイルの種類 (SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkID=627430))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81377-p161">DLP evaluates any content that can be indexed. For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkID=627430).</span></span>
  
### <a name="policy-evaluation-in-exchange-online-outlook-2013-and-later-and-outlook-on-the-web"></a><span data-ttu-id="81377-410">Exchange Online、outlook 2013 以降、outlook on the web でのポリシー評価</span><span class="sxs-lookup"><span data-stu-id="81377-410">Policy evaluation in Exchange Online, Outlook 2013 and later, and Outlook on the web</span></span>

<span data-ttu-id="81377-411">exchange online を場所として含む DLP ポリシーを作成すると、ポリシーは Office 365 セキュリティ&amp;コンプライアンスセンターから exchange online に同期され、次に exchange online から web 上の outlook 2013 以降に同期されます。</span><span class="sxs-lookup"><span data-stu-id="81377-411">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook 2013 and later.</span></span>
  
<span data-ttu-id="81377-p162">メッセージが Outlook で構成されている場合、ユーザーは作成されたコンテンツが DLP ポリシーに照らして評価されるときに、ポリシーヒントを表示できます。メッセージが送信された後は、exchange 管理センターで作成された exchange トランスポートルールと dlp ポリシーと共に、メールフローの通常の一部として DLP ポリシーに対して評価されます (詳細については、次のセクションを参照してください)。DLP ポリシーは、メッセージと添付ファイルの両方をスキャンします。</span><span class="sxs-lookup"><span data-stu-id="81377-p162">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies. And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange transport rules and DLP policies created in the Exchange Admin Center (see the next section for more info). DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-2016-desktop-programs"></a><span data-ttu-id="81377-415">Office 2016 デスクトップ プログラムにおけるポリシー評価</span><span class="sxs-lookup"><span data-stu-id="81377-415">Policy evaluation in the Office 2016 desktop programs</span></span>

<span data-ttu-id="81377-p163">Excel 2016、PowerPoint 2016、および Word 2016 には、機密情報を識別し、DLP ポリシーを SharePoint Online と OneDrive for business として適用するのと同じ機能が含まれています。これらの Office 2016 プログラムは、自分の dlp ポリシーを中央ポリシーストアから直接同期し、dlp ポリシーに含まれているサイトから開いたドキュメントをユーザーが操作するときに、dlp ポリシーに対してコンテンツを継続的に評価します。</span><span class="sxs-lookup"><span data-stu-id="81377-p163">Excel 2016, PowerPoint 2016, and Word 2016 include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business. These Office 2016 programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="81377-p164">Office 2016 の DLP ポリシー評価は、プログラムのパフォーマンスや、コンテンツを扱うユーザーの生産性に影響を与えないように設計されています。大きなドキュメントで作業している場合や、ユーザーのコンピューターがビジー状態になっている場合は、ポリシーヒントが表示されるまで数秒かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="81377-p164">DLP policy evaluation in Office 2016 is designed not to affect the performance of the programs or the productivity of people working on content. If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>
  
## <a name="permissions"></a><span data-ttu-id="81377-420">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="81377-420">Permissions</span></span>

<span data-ttu-id="81377-p165">DLP ポリシーを作成するコンプライアンスチームのメンバーは、セキュリティ&amp;コンプライアンスセンターに対するアクセス許可が必要です。既定では、テナント管理者は、この場所にアクセスできるようになり、テナント管理者や他の&amp;ユーザーには、テナント管理者のすべてのアクセス許可を付与することなく、セキュリティコンプライアンスセンターへのアクセス権を付与することができます。そのためには、次のことを行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="81377-p165">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="81377-423">Office 365 でグループを作成し、コンプライアンス担当者をそのグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="81377-423">Create a group in Office 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="81377-424">セキュリティ&amp; /コンプライアンスセンターの [**アクセス許可**] ページで役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="81377-424">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 
    
3. <span data-ttu-id="81377-425">Office 365 グループをその役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="81377-425">Add the Office 365 group to the role group.</span></span>
    
<span data-ttu-id="81377-426">詳細については、「[Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81377-426">For more information, see [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="81377-p166">DLP ポリシーを作成して適用するときにのみ、これらのアクセス許可が必要になります。ポリシーを適用する場合に、コンテンツへのアクセスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="81377-p166">These permissions are required only to create and apply a DLP policy. Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="81377-429">DLP コマンドレットを検索する</span><span class="sxs-lookup"><span data-stu-id="81377-429">Find the DLP cmdlets</span></span>

<span data-ttu-id="81377-430">セキュリティ&amp; /コンプライアンスセンターのほとんどのコマンドレットを使用するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="81377-430">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="81377-431">リモート PowerShell を使用して Office 365 セキュリティ/コンプライアンス センターに接続する</span><span class="sxs-lookup"><span data-stu-id="81377-431">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="81377-432">次のいずれかの[Office 365 &amp;セキュリティコンプライアンスセンターコマンドレット](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)を使用する</span><span class="sxs-lookup"><span data-stu-id="81377-432">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="81377-p167">ただし、DLP レポートには、Exchange Online などの Office 365 間でデータをプルする必要があります。このため、DLP レポートのコマンドレットは Exchange Online powershell で使用できます (セキュリティ&amp;コンプライアンスセンターの powershell には含まれません)。そのため、DLP レポートのコマンドレットを使用するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="81377-p167">However, DLP reports need pull data from across Office 365, including Exchange Online. For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell. Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="81377-436">リモート PowerShell による Exchange Online への接続</span><span class="sxs-lookup"><span data-stu-id="81377-436">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="81377-437">次のいずれかのコマンドレットを DLP レポートに使用します。</span><span class="sxs-lookup"><span data-stu-id="81377-437">Use any of these cmdlets for the DLP reports:</span></span>
    
  - [<span data-ttu-id="81377-438">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="81377-438">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
  - [<span data-ttu-id="81377-439">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="81377-439">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    
## <a name="more-information"></a><span data-ttu-id="81377-440">詳細情報</span><span class="sxs-lookup"><span data-stu-id="81377-440">More information</span></span>

- [<span data-ttu-id="81377-441">テンプレートから DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="81377-441">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="81377-442">通知を送信して、DLP ポリシーのポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="81377-442">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="81377-443">FCI または他のプロパティを含むドキュメントを保護するために DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="81377-443">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="81377-444">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="81377-444">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="81377-445">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="81377-445">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="81377-446">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="81377-446">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="81377-447">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="81377-447">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    

