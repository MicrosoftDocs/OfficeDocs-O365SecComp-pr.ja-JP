---
title: データ損失防止ポリシーの概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/29/2019
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) ポリシーを使用すると、office 365 全体で機密情報を識別、監視、および自動保護することができます。
ms.openlocfilehash: 4117a99afc804fd397deb45087c5058077f9ff60
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000020"
---
# <a name="overview-of-data-loss-prevention-policies"></a><span data-ttu-id="d1422-103">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="d1422-103">Overview of data loss prevention policies</span></span>

<span data-ttu-id="d1422-104">ビジネスの標準や業界の規制に準拠するために、組織は機密情報を保護し、不注意による情報漏えいを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-104">To comply with business standards and industry regulations, organizations need to protect sensitive information and prevent its inadvertent disclosure.</span></span> <span data-ttu-id="d1422-105">組織外への漏えいを防止する機密情報の例としては、財務データ、また個人情報 (PII) (クレジット カード番号、社会保障番号、健康記録など) があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-105">Examples of sensitive information that you might want to prevent from leaking outside your organization include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records.</span></span> <span data-ttu-id="d1422-106">office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) ポリシーを使用すると、office 365 全体で機密情報を識別、監視、および自動保護することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-106">With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>
  
<span data-ttu-id="d1422-107">DLP ポリシーを使用すると、以下のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="d1422-107">With a DLP policy, you can:</span></span>
  
- <span data-ttu-id="d1422-108">**Exchange online、SharePoint Online、OneDrive for business、Microsoft Teams など、さまざまな場所の機密情報を特定します。**</span><span class="sxs-lookup"><span data-stu-id="d1422-108">**Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**</span></span>
    
    <span data-ttu-id="d1422-109">たとえば、任意の onedrive for business サイトに保存されているクレジットカード番号を含むドキュメントを特定したり、特定のユーザーの onedrive サイトのみを監視したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-109">For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.</span></span>
    
- <span data-ttu-id="d1422-110">**機密情報を誤って共有することを防ぎます**。</span><span class="sxs-lookup"><span data-stu-id="d1422-110">**Prevent the accidental sharing of sensitive information**.</span></span> 
    
    <span data-ttu-id="d1422-111">たとえば、組織外のユーザーと共有している正常性レコードが含まれているドキュメントまたは電子メールを特定し、そのドキュメントへのアクセスを自動的にブロックしたり、電子メールの送信をブロックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-111">For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.</span></span>
    
- <span data-ttu-id="d1422-112">**デスクトップバージョンの Excel、PowerPoint、および Word の機密情報を監視して保護します。**</span><span class="sxs-lookup"><span data-stu-id="d1422-112">**Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**</span></span>
    
    <span data-ttu-id="d1422-113">Exchange online、SharePoint Online、OneDrive for business の場合と同様に、これらの Office デスクトッププログラムには、機密情報を識別し、DLP ポリシーを適用するための同じ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1422-113">Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies.</span></span> <span data-ttu-id="d1422-114">DLP は、ユーザーがこれらの Office プログラムでコンテンツを共有するときの継続的な監視を提供します。</span><span class="sxs-lookup"><span data-stu-id="d1422-114">DLP provides continuous monitoring when people share content in these Office programs.</span></span>
    
- <span data-ttu-id="d1422-115">**ユーザーがワークフローを中断せずに、コンプライアンスを準拠しつづける方法を学ぶよう支援します。**</span><span class="sxs-lookup"><span data-stu-id="d1422-115">**Help users learn how to stay compliant without interrupting their workflow.**</span></span>
    
    <span data-ttu-id="d1422-116">ユーザーに対して、DLP ポリシーについての教育を行い、作業をブロックすることなく、準拠を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-116">You can educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="d1422-117">たとえば、機密情報を含むドキュメントをユーザーが共有しようとすると、DLP ポリシーによって電子メール通知が送信されます。また、ビジネスがある場合にポリシーを上書きすることができるように、ドキュメントライブラリのコンテキストでポリシーヒントを表示することができます。位置.</span><span class="sxs-lookup"><span data-stu-id="d1422-117">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span> <span data-ttu-id="d1422-118">outlook on the web、outlook、Excel、PowerPoint、Word にも同じポリシーヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-118">The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.</span></span>
    
- <span data-ttu-id="d1422-119">**組織の dlp ポリシーに一致するコンテンツを示す DLP レポートを表示します。**</span><span class="sxs-lookup"><span data-stu-id="d1422-119">**View DLP reports showing content that matches your organization's DLP policies.**</span></span>
    
    <span data-ttu-id="d1422-120">組織がどの程度 DLP ポリシーに準拠しているかを評価するため、長期間にわたる、各ポリシーとルールの一致項目数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-120">To assess how your organization is complying with a DLP policy, you can see how many matches each policy and rule has over time.</span></span> <span data-ttu-id="d1422-121">DLP ポリシーを使用して、ユーザーがポリシーヒントを上書きし、誤検知を報告できる場合は、ユーザーが報告した情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1422-121">If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported.</span></span>
    
<span data-ttu-id="d1422-122">Office 365 セキュリティ&amp;コンプライアンスセンターの [データ損失防止] ページで DLP ポリシーを作成して管理します。</span><span class="sxs-lookup"><span data-stu-id="d1422-122">You create and manage DLP policies on the Data loss prevention page in the Office 365 Security &amp; Compliance Center.</span></span>
  
![Office 365 セキュリティ&amp; /コンプライアンスセンターのデータ損失防止ページ](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a><span data-ttu-id="d1422-124">DLP ポリシーの内容</span><span class="sxs-lookup"><span data-stu-id="d1422-124">What a DLP policy contains</span></span>

<span data-ttu-id="d1422-125">DLP ポリシーにはいくつかの基本的な内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1422-125">A DLP policy contains a few basic things:</span></span>
  
- <span data-ttu-id="d1422-126">Exchange online、SharePoint online、OneDrive for business のサイト、Microsoft Teams のチャットやチャネルなど、コンテンツの**場所**を保護する場所。</span><span class="sxs-lookup"><span data-stu-id="d1422-126">Where to protect the content - **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span> 
    
- <span data-ttu-id="d1422-127">**ルール**を適用してコンテンツを保護するタイミングと方法。ルールは次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-127">When and how to protect the content by enforcing **rules** comprised of:</span></span> 
    
  - <span data-ttu-id="d1422-128">ルールを適用する前にコンテンツを一致させる必要がある**条件**。たとえば、組織外の人と共有されている社会保障番号を含むコンテンツのみを検索します。</span><span class="sxs-lookup"><span data-stu-id="d1422-128">**Conditions** the content must match before the rule is enforced -- for example, look only for content containing Social Security numbers that's been shared with people outside your organization.</span></span> 
    
  - <span data-ttu-id="d1422-129">**アクション** 条件に一致するコンテンツが検出されるときにルールで自動実行されるアクションです。たとえば、ドキュメントに対するアクセスをブロックし、ユーザーとコンプライアンスの担当者の両方に電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="d1422-129">**Actions** that you want the rule to take automatically when content matching the conditions is found -- for example, block access to the document and send both the user and compliance officer an email notification.</span></span> 
    
<span data-ttu-id="d1422-130">ルールを使用して特定の保護要件を満たし、その後共通の保護要件 (たとえば、特定の規定に準拠することが必要なすべてのルール) をグループ化するために 1 つの DLP ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1422-130">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="d1422-131">たとえば、Health Insurance Portability and Accountability Act (HIPAA) の対象となる情報の存在を検出する際に役立つ DLP ポリシーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="d1422-131">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="d1422-132">この DLP ポリシーにより、組織外のユーザーと共有している機密情報を含むドキュメントを検索することによって、すべての SharePoint Online サイトとすべての OneDrive for business サイト (where) で HIPAA データを保護することができます (条件) を行い、ドキュメントへのアクセスをブロックし、通知を送信します (アクション)。</span><span class="sxs-lookup"><span data-stu-id="d1422-132">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="d1422-133">こうした要件は、個々のルールとして格納し、1 つの DLP ポリシーとしてグループ化することによって、管理とレポート作成を簡単に行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="d1422-133">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![図は、DLP ポリシーに場所とルールが含まれていることを示しています。](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a><span data-ttu-id="d1422-135">場所</span><span class="sxs-lookup"><span data-stu-id="d1422-135">Locations</span></span>

<span data-ttu-id="d1422-136">DLP ポリシーは、Exchange online、SharePoint Online、OneDrive for business、または Microsoft Teams に情報があるかどうかにかかわらず、Office 365 全体の機密情報を検索して保護することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-136">A DLP policy can find and protect sensitive information across Office 365, whether that information is located in Exchange Online, SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="d1422-137">Exchange 電子メール、Microsoft Teams のチャットおよびチャネル、すべての SharePoint または OneDrive ライブラリのコンテンツを保護するか、ポリシーの特定の場所を選択するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-137">You can choose to protect content in Exchange email, Microsoft Teams chats and channels, and all SharePoint or OneDrive libraries, or select specific locations for a policy.</span></span>
  
![DLP ポリシーを適用できる場所のオプション](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
<span data-ttu-id="d1422-139">特定の SharePoint サイトまたは OneDrive アカウントを含めるか除外するかを選択すると、DLP ポリシーに含めることができるのは、そのような包含と除外を100以内にする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-139">Note that if you choose to include or exclude specific SharePoint sites or OneDrive accounts, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="d1422-140">この制限は存在しますが、組織全体のポリシーまたは場所全体に適用されるポリシーのいずれかを適用することによって、この制限を超えることができることを理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="d1422-140">Although this limit exists, understand that you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="rules"></a><span data-ttu-id="d1422-141">ルール</span><span class="sxs-lookup"><span data-stu-id="d1422-141">Rules</span></span>

<span data-ttu-id="d1422-142">ルールは、組織のコンテンツに対するビジネス要件を強制します。</span><span class="sxs-lookup"><span data-stu-id="d1422-142">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="d1422-143">ポリシーには 1 つ以上のルールが含まれ、各ルールには、条件とアクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1422-143">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="d1422-144">ルールごとに、条件を満たすとアクションが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-144">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="d1422-145">ルールは、各ポリシーの優先度の高いルールから順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-145">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="d1422-146">また、ルールによって、コンテンツがルールに一致したことをユーザーに通知するオプション (ポリシーヒントと電子メール通知を含む) と管理者 (電子メールインシデントレポート付き) も表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-146">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="d1422-147">以下に説明するルールのコンポーネントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d1422-147">Here are the components of a rule, each explained below.</span></span>
  
![DLP ルールエディターのセクション](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="d1422-149">条件</span><span class="sxs-lookup"><span data-stu-id="d1422-149">Conditions</span></span>

<span data-ttu-id="d1422-150">条件は、探している情報の種類と、アクションを実行するタイミングを決定するので重要です。</span><span class="sxs-lookup"><span data-stu-id="d1422-150">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="d1422-151">たとえば、コンテンツに10を超える番号が含まれておらず、組織外のユーザーと共有されている場合を除き、パスポート番号を含むコンテンツを無視することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-151">For example, you might choose to ignore content containing passport numbers unless the content contains more than ten such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="d1422-152">条件は、検索している機密情報の種類や、ドキュメントの共有者など、**コンテンツ**に焦点\*\*\*\* を当てています。</span><span class="sxs-lookup"><span data-stu-id="d1422-152">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="d1422-153">条件を使用して、さまざまなアクションをさまざまなリスクレベルに割り当てることができます。たとえば、内部的に共有されている機密コンテンツはリスクが低く、組織外のユーザーと共有する機密コンテンツよりも少ないアクションを必要とする場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-153">You can use conditions to assign different actions to different risk levels -- for example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![利用可能な DLP 条件の一覧](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="d1422-155">以下の内容を判断できる条件が使用可能になっています。</span><span class="sxs-lookup"><span data-stu-id="d1422-155">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="d1422-156">コンテンツには、種類の機密情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1422-156">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="d1422-157">コンテンツにはラベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1422-157">Content contains a label.</span></span> <span data-ttu-id="d1422-158">詳細については、「 [DLP ポリシーの条件としてラベルを使用する](#using-a-label-as-a-condition-in-a-dlp-policy)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-158">For more information, see the below section [Using a label as a condition in a DLP policy](#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="d1422-159">コンテンツが組織の内または外のユーザーと共有されている。</span><span class="sxs-lookup"><span data-stu-id="d1422-159">Content is shared with people outside or inside your organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="d1422-160">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="d1422-160">Types of sensitive information</span></span>

<span data-ttu-id="d1422-161">DLP ポリシーは、機密情報の**種類**として定義された機密情報を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d1422-161">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="d1422-162">Office 365 には、クレジット カード番号、銀行口座番号、国民 ID 番号、パスポート番号など、さまざまな地域ですぐに利用できる多数の一般的な機密情報の種類の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1422-162">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![使用できる機密情報の種類の一覧](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="d1422-164">DLP ポリシーは、クレジットカード番号などの機密情報の種類を検索するときに、単に16桁の数字を検索するだけではありません。</span><span class="sxs-lookup"><span data-stu-id="d1422-164">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="d1422-165">機密情報のそれぞれの種類が定義され、以下の組み合わせを使用して検出されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-165">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="d1422-166">キーワード</span><span class="sxs-lookup"><span data-stu-id="d1422-166">Keywords</span></span>
    
- <span data-ttu-id="d1422-167">内部関数。チェックサムや構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="d1422-167">Internal functions to validate checksums or composition</span></span>
    
- <span data-ttu-id="d1422-168">パターン一致を検索するための正規表現の評価</span><span class="sxs-lookup"><span data-stu-id="d1422-168">Evaluation of regular expressions to find pattern matches</span></span>
    
- <span data-ttu-id="d1422-169">その他のコンテンツの検査</span><span class="sxs-lookup"><span data-stu-id="d1422-169">Other content examination</span></span>
    
<span data-ttu-id="d1422-170">これにより、DLP 検出によって高い精度が得られますが、これによって、人々の作業を中断できる誤検知の数が減少します。</span><span class="sxs-lookup"><span data-stu-id="d1422-170">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="d1422-171">アクション</span><span class="sxs-lookup"><span data-stu-id="d1422-171">Actions</span></span>

<span data-ttu-id="d1422-172">コンテンツがルールの条件に一致する場合、コンテンツを自動的に保護するアクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-172">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![使用できる DLP アクションの一覧](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="d1422-174">アクションを使用できるようになったので、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-174">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="d1422-175">**コンテンツへのアクセスを制限する**サイトコンテンツの場合、サイトコレクションの管理者、ドキュメントの所有者、およびドキュメントを最後に変更したユーザーを除くすべてのユーザーに対して、ドキュメントのアクセス許可が制限されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d1422-175">**Restrict access to the content** For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="d1422-176">これらの特別なユーザーの場合は、ドキュメントから機密情報を削除したり、他の是正措置を実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="d1422-176">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="d1422-177">ドキュメントがコンプライアンスを遵守した状態になった場合、元のアクセス許可が自動的に復元されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-177">When the document is in compliance, the original permissions will be automatically restored.</span></span> <span data-ttu-id="d1422-178">ドキュメントへのアクセスがブロックされると、そのサイト上のライブラリで特別なポリシー ヒントのアイコンがドキュメントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-178">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
    ![ドキュメントへのアクセスがブロックされていることを示すポリシーのヒント](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    <span data-ttu-id="d1422-180">電子メールコンテンツの場合、このアクションはメッセージの送信をブロックします。</span><span class="sxs-lookup"><span data-stu-id="d1422-180">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="d1422-181">DLP ルールの構成方法に応じて、送信者には NDR が表示されるか、または (ルールが通知を使用している場合は) ポリシーヒントや電子メール通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="d1422-181">Depending on how the DLP rule is configured, the sender will see an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
    ![承認されていない受信者をメッセージから削除する必要があることを警告します。](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="d1422-183">ユーザー通知とユーザーの優先</span><span class="sxs-lookup"><span data-stu-id="d1422-183">User notifications and user overrides</span></span>

<span data-ttu-id="d1422-184">通知と上書きを使用して、ユーザーに DLP ポリシーについての教育を行い、作業をブロックすることなく準拠したままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-184">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="d1422-185">たとえば、機密情報を含むドキュメントをユーザーが共有しようとすると、DLP ポリシーによって電子メール通知が送信されます。また、ビジネスがある場合にポリシーを上書きすることができるように、ドキュメントライブラリのコンテキストでポリシーヒントを表示することができます。位置.</span><span class="sxs-lookup"><span data-stu-id="d1422-185">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![DLP ルールエディターのユーザー通知とユーザーオーバーライドのセクション](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="d1422-187">電子メールは、コンテンツを送信、共有、または最終変更したユーザー、サイトコンテンツ、サイトコレクション管理者、およびドキュメント所有者に通知することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-187">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="d1422-188">また、電子メール通知から選択したものを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-188">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="d1422-189">電子メール通知の送信に加えて、ユーザー通知にはポリシーヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-189">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="d1422-190">outlook および outlook on the web。</span><span class="sxs-lookup"><span data-stu-id="d1422-190">In Outlook and Outlook on the web.</span></span>
    
- <span data-ttu-id="d1422-191">SharePoint Online または OneDrive for business サイト上のドキュメントの場合。</span><span class="sxs-lookup"><span data-stu-id="d1422-191">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="d1422-192">Excel、PowerPoint、および Word で、ドキュメントが DLP ポリシーに含まれるサイトに格納されている場合。</span><span class="sxs-lookup"><span data-stu-id="d1422-192">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="d1422-193">電子メール通知とポリシーヒントは、コンテンツが DLP ポリシーと競合する理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1422-193">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="d1422-194">選択した場合、電子メール通知とポリシーヒントを使用すると、ユーザーが誤検知を報告してルールを上書きしたり、業務上の理由を提供したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-194">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="d1422-195">これにより、ユーザーに DLP ポリシーについての教育を行い、ユーザーの作業を妨げることなくそれらを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-195">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="d1422-196">コンプライアンス担当者が定期的に情報をレビューできるように、上書きおよび誤検知に関する情報もレポート (DLP レポートを参照) およびインシデントレポート (次のセクション) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1422-196">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="d1422-197">OneDrive for business アカウントのポリシーヒントは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d1422-197">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![OneDrive アカウントのドキュメントのポリシーヒント](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a><span data-ttu-id="d1422-199">インシデント レポート</span><span class="sxs-lookup"><span data-stu-id="d1422-199">Incident reports</span></span>

<span data-ttu-id="d1422-200">ルールが一致する場合は、イベントの詳細を使用して、コンプライアンス責任者 (または任意のユーザー) にインシデントレポートを送信できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-200">When a rule is matched, you can send an incident report to your compliance officer (or any people you choose) with details of the event.</span></span> <span data-ttu-id="d1422-201">このレポートには、一致したアイテムに関する情報、ルールに一致した実際のコンテンツ、およびコンテンツを最後に変更したユーザーの名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1422-201">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="d1422-202">電子メールメッセージの場合、このレポートには、DLP ポリシーに一致する元のメッセージも添付ファイルとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1422-202">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>
  
![インシデント レポートを構成するためのページ](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="d1422-204">グループ化演算子と論理演算子</span><span class="sxs-lookup"><span data-stu-id="d1422-204">Grouping and logical operators</span></span>

<span data-ttu-id="d1422-205">多くの場合、DLP ポリシーには、米国の社会保障番号を含むすべてのコンテンツを特定するなどの簡単な要件があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-205">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="d1422-206">ただし、その他のシナリオでは、DLP ポリシーにより、より緩やかに定義されたデータを識別する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-206">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="d1422-207">たとえば、米国の医療保険法 (HIPAA) の対象となるコンテンツを特定するには、次の情報を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-207">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="d1422-208">米国の社会保障番号や薬品執行機関 (dea) 番号など、特定の種類の機密情報が含まれるコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="d1422-208">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="d1422-209">AND</span><span class="sxs-lookup"><span data-stu-id="d1422-209">AND</span></span>
    
- <span data-ttu-id="d1422-210">患者の治療や、提供された医療サービスの説明など、識別が困難なコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="d1422-210">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="d1422-211">このコンテンツを特定するには、Diseases の国際分類 (icd-9-cm または icd-10 cm) のような非常に大きなキーワードリストのキーワードを一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-211">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="d1422-212">グループ化と論理演算子 (and、OR) を使用して、このような緩やかに定義されたデータを簡単に特定できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-212">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="d1422-213">DLP ポリシーを作成すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-213">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="d1422-214">グループ機密情報の種類。</span><span class="sxs-lookup"><span data-stu-id="d1422-214">Group sensitive information types.</span></span>
    
- <span data-ttu-id="d1422-215">グループ内の機密情報の種類とグループの間の論理演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1422-215">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="d1422-216">グループ内での演算子の選択</span><span class="sxs-lookup"><span data-stu-id="d1422-216">Choosing the operator within a group</span></span>

<span data-ttu-id="d1422-217">グループ内では、ルールに一致するコンテンツについて、そのグループ内のすべての条件を満たす必要があるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-217">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![グループ内のオペレーターを示すグループ](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="d1422-219">グループを追加する</span><span class="sxs-lookup"><span data-stu-id="d1422-219">Adding a group</span></span>

<span data-ttu-id="d1422-220">グループを簡単に追加できます。グループには、そのグループ内に独自の条件と演算子を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-220">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![[グループの追加] ボタン](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="d1422-222">グループ間でのオペレーターの選択</span><span class="sxs-lookup"><span data-stu-id="d1422-222">Choosing the operator between groups</span></span>

<span data-ttu-id="d1422-223">グループ間では、ルールに一致するコンテンツについて、1つのグループまたはすべてのグループの条件を満たす必要があるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-223">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="d1422-224">たとえば、組み込みの**米国 HIPAA**ポリシーには、次のものを含むコンテンツを識別するためにグループ間で**and**演算子を使用するルールがあります。</span><span class="sxs-lookup"><span data-stu-id="d1422-224">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="d1422-225">グループ**PII 識別子**(少なくとも1つの SSN 番号**または**dea の番号)</span><span class="sxs-lookup"><span data-stu-id="d1422-225">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="d1422-226">**AND**</span><span class="sxs-lookup"><span data-stu-id="d1422-226">**AND**</span></span>
    
- <span data-ttu-id="d1422-227">グループ**医学条項**(少なくとも1つの ICD-9-センチキーワード**または**icd-10-センチキーワード)</span><span class="sxs-lookup"><span data-stu-id="d1422-227">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![グループ間のオペレーターを示すグループ](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="d1422-229">ルールが処理される優先度</span><span class="sxs-lookup"><span data-stu-id="d1422-229">The priority by which rules are processed</span></span>

<span data-ttu-id="d1422-230">ポリシーでルールを作成する場合、各ルールには、作成された順序で優先度が割り当てられます。つまり、最初に作成されたルールの優先度、2番目に作成したルールの優先度が2番目になります。</span><span class="sxs-lookup"><span data-stu-id="d1422-230">When you create rules in a policy, each rule is assigned a priority in the order in which it's created - meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span> <span data-ttu-id="d1422-231">ルールを作成した後は、ルールを削除して再作成しない限り、その優先度を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d1422-231">After you create a rule, its priority can't be changed, except by deleting and re-creating it.</span></span>
  
![優先順位順のルール](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
<span data-ttu-id="d1422-233">コンテンツがルールに対して評価されない場合、ルールは優先順位に従って処理されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-233">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="d1422-234">コンテンツが複数のルールと一致する場合、ルールは優先順位に従って処理され、最も制限の厳しいアクションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-234">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="d1422-235">たとえば、コンテンツが次のすべてのルールに一致する場合は、ルール3が最も優先度の高いルールであるため、ルール3が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-235">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="d1422-236">ルール 1: ユーザーにのみ通知します。</span><span class="sxs-lookup"><span data-stu-id="d1422-236">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="d1422-237">ルール 2: ユーザーに通知し、アクセスを制限し、ユーザーによる上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="d1422-237">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="d1422-238">ルール 3: ユーザーに対して通知を行い、アクセスを制限し、ユーザーによる上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="d1422-238">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="d1422-239">ルール 4: ユーザーにのみ通知する</span><span class="sxs-lookup"><span data-stu-id="d1422-239">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="d1422-240">ルール 5: アクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="d1422-240">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="d1422-241">ルール 6: ユーザーに対して通知を行い、アクセスを制限し、ユーザーによる上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="d1422-241">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="d1422-242">この例では、最も制限の厳しいルールのみが適用されていても、すべてのルールの一致が監査ログに記録され、DLP レポートに表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-242">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="d1422-243">ポリシーヒントに関しては、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-243">With respect to policy tips, note that:</span></span>
  
- <span data-ttu-id="d1422-244">最も高い優先度のポリシーヒントのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-244">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="d1422-245">たとえば、コンテンツへのアクセスをブロックするルールに基づくポリシー ヒントは、単に通知を送信するだけのルールのポリシー ヒントよりも優先されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-245">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="d1422-246">これによって、ユーザーにポリシー ヒントが多数表示されるという事態を避けられます。</span><span class="sxs-lookup"><span data-stu-id="d1422-246">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="d1422-247">	最も制限の厳しいルールでユーザーにルールを上書きすることを許可している場合は、このルールを上書きすることで、コンテンツに一致した他のルールもすべて上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d1422-247">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="d1422-248">調整ルールを使用して、より簡単に、またはより簡単に一致するようにする</span><span class="sxs-lookup"><span data-stu-id="d1422-248">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="d1422-249">ユーザーが DLP ポリシーを作成して有効にした後は、次のような問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="d1422-249">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="d1422-250">機密情報の**ないコンテンツが**多すぎると、ルールに一致します。つまり、誤検知が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="d1422-250">Too much content that **is not** sensitive information matches the rules - in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="d1422-251">機密情報がルールに一致するコンテンツ**が**少なすぎる (つまり、保護アクションが機密情報に対して適用されない)。</span><span class="sxs-lookup"><span data-stu-id="d1422-251">Too little content that **is** sensitive information matches the rules - in other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="d1422-252">これらの問題に対処するには、インスタンス数と一致精度を調整して、コンテンツがルールと一致するようにすることで、ルールを調整できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-252">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="d1422-253">ルールで使用される機密情報の種類ごとに、インスタンス数と一致精度の両方があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-253">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="d1422-254">インスタンス数</span><span class="sxs-lookup"><span data-stu-id="d1422-254">Instance count</span></span>

<span data-ttu-id="d1422-255">インスタンス数は、特定の種類の機密情報がルールと一致するようにコンテンツを表示する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d1422-255">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="d1422-256">たとえば、1から9の固有の米国または英国の場合、コンテンツは以下のルールに一致します。</span><span class="sxs-lookup"><span data-stu-id="d1422-256">For example, content will match the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="d1422-257">パスポート番号は識別されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-257">passport numbers are identified.</span></span>
  
<span data-ttu-id="d1422-258">インスタンス数には、機密情報の種類とキーワードに**固有**の一致のみが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-258">Note that the instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="d1422-259">たとえば、電子メールに同じクレジットカード番号の10個のオカレンスが含まれている場合、その10回はクレジットカード番号の1つのインスタンスとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="d1422-259">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span> 
  
<span data-ttu-id="d1422-260">インスタンス数を使用してルールを調整するには、次のガイダンスがわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="d1422-260">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="d1422-261">ルールをより簡単に一致させるには、**最小**数を減らすか、**最大**数を増やします。</span><span class="sxs-lookup"><span data-stu-id="d1422-261">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="d1422-262">また、数値を削除することによって、 **max**を**任意**の値に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1422-262">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="d1422-263">ルールが一致しにくくなるようにするには、**最小**数を増やします。</span><span class="sxs-lookup"><span data-stu-id="d1422-263">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="d1422-264">通常は、低いインスタンス数 (たとえば、1-9) のルールでユーザー通知を送信するなど、制限の少ないアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1422-264">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="d1422-265">また、より多くの制限付きアクション (ユーザーによる上書きを許可せずにコンテンツへのアクセスを制限するなど) を使用すると、より高いレベルのインスタンス数を持つルール (たとえば、10個など) になります。</span><span class="sxs-lookup"><span data-stu-id="d1422-265">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![ルールエディターのインスタンス数](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="d1422-267">正確一致</span><span class="sxs-lookup"><span data-stu-id="d1422-267">Match accuracy</span></span>

<span data-ttu-id="d1422-268">前述したように、機密情報の種類はさまざまな種類の証拠の組み合わせを使用して定義および検出されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-268">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="d1422-269">通常、機密情報の種類は、パターンと呼ばれる複数の組み合わせによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-269">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="d1422-270">より少ない証拠を必要とするパターンは、一致精度 (または信頼度) が低く、より多くの証拠が必要となるパターンの精度 (または信頼度が高い) になります。</span><span class="sxs-lookup"><span data-stu-id="d1422-270">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="d1422-271">機密情報の種類ごとに使用される実際のパターンと信頼度の詳細については、「[機密情報の種類](what-the-sensitive-information-types-look-for.md)を調べる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-271">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
<span data-ttu-id="d1422-272">たとえば、"クレジットカード番号" という名前の機密情報の種類は、次の2つのパターンで定義されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-272">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="d1422-273">65% の信頼度が必要なパターン。</span><span class="sxs-lookup"><span data-stu-id="d1422-273">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="d1422-274">クレジットカード番号の形式の番号。</span><span class="sxs-lookup"><span data-stu-id="d1422-274">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="d1422-275">チェックサムを渡す数値。</span><span class="sxs-lookup"><span data-stu-id="d1422-275">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="d1422-276">85% の信頼度が必要なパターン。</span><span class="sxs-lookup"><span data-stu-id="d1422-276">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="d1422-277">クレジットカード番号の形式の番号。</span><span class="sxs-lookup"><span data-stu-id="d1422-277">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="d1422-278">チェックサムを渡す数値。</span><span class="sxs-lookup"><span data-stu-id="d1422-278">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="d1422-279">適切な形式のキーワードまたは有効期限の日付。</span><span class="sxs-lookup"><span data-stu-id="d1422-279">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="d1422-280">ルールでは、これらの信頼レベル (または正確一致) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-280">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="d1422-281">通常は、一致精度の低いルールでユーザー通知を送信するなど、制限の少ないアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1422-281">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="d1422-282">また、より正確に一致するルールを使用して、ユーザーによる上書きを許可することなくコンテンツへのアクセスを制限するなど、より制限の多いアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1422-282">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="d1422-283">クレジットカード番号などの特定の種類の機密情報がコンテンツで識別されると、1つの信頼レベルのみが返されることを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="d1422-283">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="d1422-284">すべての一致が1つのパターンに一致する場合は、そのパターンの信頼レベルが返されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-284">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="d1422-285">複数のパターンに一致するものがある場合 (つまり、2つの異なる信頼度レベルに一致するものがある場合)、1つのパターンだけを超える信頼レベルが返されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-285">If there are matches for more than one pattern (i.e., there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="d1422-286">これは厄介な部分です。</span><span class="sxs-lookup"><span data-stu-id="d1422-286">This is the tricky part.</span></span> <span data-ttu-id="d1422-287">たとえば、クレジットカードの場合、65% と 85% の両方のパターンが一致した場合は、その機密情報の種類に対して返される信頼度が 90% を超えているため、より多くの証拠がより信頼度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="d1422-287">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="d1422-288">そのため、クレジットカードに対して2つの相互排他的なルールを作成したい場合は、その精度は 65%、精度は 85% と一致しますが、精度の範囲は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d1422-288">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="d1422-289">最初のルールでは、65% パターンに一致するものが1つだけ抽出されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-289">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="d1422-290">2番目のルールは、**少なくとも1つ**の 85% 一致に一致するものを取得し、信頼度の低い他の一致を**持つ可能性が**あります。</span><span class="sxs-lookup"><span data-stu-id="d1422-290">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![一致精度の範囲が異なる2つのルール](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="d1422-292">このような理由により、異なる一致 accuracies を持つルールを作成するためのガイダンスは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d1422-292">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="d1422-293">通常、最小の信頼レベルは、 **min**および**max** (範囲ではない) に対して同じ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1422-293">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="d1422-294">最高度の信頼度は、通常、信頼度の低いものから100までの範囲です。</span><span class="sxs-lookup"><span data-stu-id="d1422-294">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="d1422-295">通常、信頼レベルは、信頼度の低いものから、信頼度の高いレベルのすぐ下までの範囲です。</span><span class="sxs-lookup"><span data-stu-id="d1422-295">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="d1422-296">DLP ポリシーでの条件としてのラベルの使用</span><span class="sxs-lookup"><span data-stu-id="d1422-296">Using a label as a condition in a DLP policy</span></span>

<span data-ttu-id="d1422-297">ラベルを作成して、次のようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-297">You can create a label and then:</span></span>
  
- <span data-ttu-id="d1422-298">これを**公開**して、エンドユーザーがラベルをコンテンツに表示したり、手動で適用したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="d1422-298">**Publish** it, so that end users can see and manually apply the label to content.</span></span> 
    
- <span data-ttu-id="d1422-299">選択した条件に一致するコンテンツに**自動適用**します。</span><span class="sxs-lookup"><span data-stu-id="d1422-299">**Auto-apply** it to content that matches the conditions that you choose.</span></span> 
    
<span data-ttu-id="d1422-300">ラベルの詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-300">For more information about labels, see [Overview of retention labels](labels.md).</span></span>
  
<span data-ttu-id="d1422-301">ラベルを作成した後、そのラベルを DLP ポリシーの条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-301">After you create a label, you can then use that label as a condition in your DLP policies.</span></span> <span data-ttu-id="d1422-302">たとえば、次のような理由が考えられることがあります。</span><span class="sxs-lookup"><span data-stu-id="d1422-302">For example, you might want to do this because:</span></span>
  
- <span data-ttu-id="d1422-303">**機密**という名前のラベルを発行したので、組織内のユーザーは機密の電子メールやドキュメントにラベルを手動で適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-303">You published a label named **Confidential**, so that people in your organization can manually apply the label to confidential email and documents.</span></span> <span data-ttu-id="d1422-304">このラベルを DLP ポリシーの条件として使用することにより、 **Confidential**というラベルが付けられたコンテンツを組織外のユーザーと共有することを制限できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-304">By using this label as a condition in your DLP policy, you can restrict content labeled **Confidential** from being shared with people outside your organization.</span></span> 
    
- <span data-ttu-id="d1422-305">その名前のプロジェクト用に**Alpine House**という名前のラベルを作成し、そのラベルを "alpine house" というキーワードを含むコンテンツに自動的に適用しました。</span><span class="sxs-lookup"><span data-stu-id="d1422-305">You created a label named **Alpine House** for a project of that name, and then applied that label automatically to content containing the keywords "Alpine House".</span></span> <span data-ttu-id="d1422-306">このラベルを DLP ポリシーの条件として使用すると、このコンテンツを組織外のユーザーと共有しようとしているときに、エンドユーザーにポリシーヒントを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-306">By using this label as a condition in your DLP policy, you can show a policy tip to end users when they're about to share this content with someone outside your organization.</span></span> 
    
- <span data-ttu-id="d1422-307">**Tax record**という名前のラベルを発行したので、レコード管理者は、レコードとして分類する必要があるコンテンツにラベルを手動で適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-307">You published a label named **Tax record**, so that your records manager can manually apply the label to content that needs to be classified as a record.</span></span> <span data-ttu-id="d1422-308">このラベルを DLP ポリシーの条件として使用することにより、このラベルを持つコンテンツを、itins や ssns などの他の種類の機密情報と共に検索できます。"**税レコード**" というラベルの付いたコンテンツに保護アクションを適用します。dlp レポートおよび監査ログデータから dlp ポリシーに関する詳細なアクティビティレポートを取得します。</span><span class="sxs-lookup"><span data-stu-id="d1422-308">By using this label as a condition in your DLP policy, you can look for content with this label in conjunction with other types of sensitive information such as ITINs or SSNs; apply protection actions to content labeled **Tax record**; and get detailed activity reports about the DLP policy from the DLP reports and audit log data.</span></span> 
    
- <span data-ttu-id="d1422-309">**エグゼクティブリーダーチーム**という名前のラベルを、重役グループの Exchange メールボックスと OneDrive アカウントに公開しました。</span><span class="sxs-lookup"><span data-stu-id="d1422-309">You published a label named **Executive Leadership Team - Sensitive** to the Exchange mailboxes and OneDrive accounts of a group of executives.</span></span> <span data-ttu-id="d1422-310">このラベルを DLP ポリシーの条件として使用することにより、コンテンツとユーザーの同じサブセットに対して保存と保護の操作の両方を適用できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-310">By using this label as a condition in your DLP policy, you can enforce both retention and protection actions on the same subset of content and users.</span></span> 
    
<span data-ttu-id="d1422-311">DLP ルールの条件としてラベルを使用することで、コンテンツ、場所、ユーザーの特定のセットに対して、保護アクションを選択的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-311">By using labels as a condition in your DLP rules, can you selectively enforce protection actions on a specific set of content, locations, or users.</span></span>
  
![条件としてラベルを](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a><span data-ttu-id="d1422-313">機密ラベルのサポートが予定されています</span><span class="sxs-lookup"><span data-stu-id="d1422-313">Support for sensitivity labels is coming</span></span>

<span data-ttu-id="d1422-314">現在、保持ラベルは、[機密ラベル](sensitivity-labels.md)ではなく、条件としてのみ使用できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-314">Note that you can currently use only a retention label as a condition, not a [sensitivity label](sensitivity-labels.md).</span></span> <span data-ttu-id="d1422-315">この条件では、現在、機密ラベルを使用するためのサポートが稼働しています。</span><span class="sxs-lookup"><span data-stu-id="d1422-315">We're currently working on support for using a sensitivity label in this condition.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="d1422-316">この機能と他の機能との関係</span><span class="sxs-lookup"><span data-stu-id="d1422-316">How this feature relates to other features</span></span>

<span data-ttu-id="d1422-317">機密情報が含まれるコンテンツには、いくつかの機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-317">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="d1422-318">保持[ラベル](labels.md#applying-a-retention-label-automatically-based-on-conditions)と[アイテム保持ポリシー](retention-policies.md)の両方で、このコンテンツに**保持**アクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-318">A [retention label](labels.md#applying-a-retention-label-automatically-based-on-conditions) and a [retention policy](retention-policies.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="d1422-319">DLP ポリシーは、このコンテンツに対して**保護**アクションを強制できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-319">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="d1422-320">これらの操作を実行する前に、DLP ポリシーでは、ラベルを含むコンテンツに加えて、他の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-320">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![機密情報に適用できる機能の図](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="d1422-322">DLP ポリシーは、機密情報に適用されるラベルまたはアイテム保持ポリシーよりも豊富な検出機能を備えていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-322">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="d1422-323">DLP ポリシーは、機密情報が含まれるコンテンツに対する保護アクションを強制でき、機密情報がコンテンツから削除されると、その保護アクションはコンテンツの次回のスキャン時に取り消されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-323">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="d1422-324">ただし、機密情報が含まれるコンテンツにアイテム保持ポリシーまたはラベルを適用すると、機密情報が削除されても、1回限りの操作が取り消されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-324">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information's removed.</span></span>
  
<span data-ttu-id="d1422-325">DLP ポリシー内の条件としてラベルを使用することにより、そのラベルを持つコンテンツに対してアイテム保持と保護アクションの両方を適用できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-325">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="d1422-326">機密情報が含まれているコンテンツと同じように、ラベルと機密情報の種類の両方がコンテンツを分類するために使用するプロパティであると考えることができます。これにより、そのコンテンツにアクションを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-326">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![ラベルを条件として使用する DLP ポリシーの図](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="d1422-328">簡易設定と詳細設定</span><span class="sxs-lookup"><span data-stu-id="d1422-328">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="d1422-329">DLP ポリシーを作成する場合は、[簡易] または [詳細設定] のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1422-329">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="d1422-330">**簡易設定**を使用すると、ルールエディタを使用してルールを作成または変更しなくても、最も一般的な種類の DLP ポリシーを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-330">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="d1422-331">**[詳細設定**] ルールエディターを使用して、DLP ポリシーのすべての設定を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-331">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="d1422-332">このトピックでは、単純な設定と高度な設定がまったく同じように動作しますが、条件とアクションで構成されるルールを適用することによって、ルールエディターは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d1422-332">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions -- only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="d1422-333">DLP ポリシーを簡単に作成する方法です。</span><span class="sxs-lookup"><span data-stu-id="d1422-333">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="d1422-334">簡易設定</span><span class="sxs-lookup"><span data-stu-id="d1422-334">Simple settings</span></span>

<span data-ttu-id="d1422-335">最も一般的な DLP シナリオは、機密情報を含むコンテンツを組織外のユーザーと共有したり、コンテンツにアクセスできるユーザーを制限するなどの自動的な修復操作を実行したりするためのポリシーを作成することです。エンドユーザーまたは管理者の通知を送信し、イベントを後で調査するために監査します。</span><span class="sxs-lookup"><span data-stu-id="d1422-335">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remedial action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="d1422-336">ユーザーは、DLP を使用して機密情報を不用意に公開しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-336">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="d1422-337">この目標を実現するには、DLP ポリシーを作成するときに [**簡易設定を使用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1422-337">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="d1422-338">これらの設定により、ルールエディターに移行せずに、最も一般的な DLP ポリシーを実装するために必要なものすべてが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-338">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![簡易および詳細設定の DLP オプション](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="d1422-340">詳細設定</span><span class="sxs-lookup"><span data-stu-id="d1422-340">Advanced settings</span></span>

<span data-ttu-id="d1422-341">カスタマイズした DLP ポリシーをさらに作成する必要がある場合は、[**詳細設定を使用**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-341">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="d1422-342">詳細設定では、各ルールのインスタンス数と一致精度 (信頼度) を含む、すべての可能なオプションを完全に制御できるルールエディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-342">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="d1422-343">セクションにすばやく移動するには、ルールエディターのトップナビゲーションにある項目をクリックして、以下のセクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="d1422-343">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP ルールエディターのトップナビゲーションメニュー](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="d1422-345">DLP ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="d1422-345">DLP policy templates</span></span>

<span data-ttu-id="d1422-346">DLP ポリシーを作成する最初の手順は、保護する情報を選択することです。</span><span class="sxs-lookup"><span data-stu-id="d1422-346">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="d1422-347">DLP テンプレートから開始することで、新しいルールセットを最初から作成する作業を保存し、既定でどのような種類の情報を含める必要があるかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-347">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="d1422-348">その後、これらの要件を追加または変更して、組織の特定の要件を満たすようにルールを微調整することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-348">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="d1422-349">構成済みの DLP ポリシーテンプレートを使用すると、HIPAA データ、PCI DSS データ、グラムリーチブライ-なる Act データ、またはロケール固有の個人情報 (P.I.) など、特定の種類の機密情報を検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d1422-349">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="d1422-350">一般的な種類の機密情報を簡単に検出して保護するため、Office 365 に既に含まれているポリシー テンプレートには、開始にあたって必要となる最も一般的な種類の機密情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1422-350">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Office 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![米国愛国者法のテンプレートにフォーカスがあるデータ損失防止ポリシーのテンプレートの一覧](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="d1422-352">組織に固有の要件がある場合もあります。その場合は、[**カスタムポリシー** ] オプションを選択することにより、最初から DLP ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-352">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="d1422-353">カスタムポリシーは空であり、premade ルールは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d1422-353">A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="d1422-354">DLP ポリシーをテスト モードで段階的にロールアウトする</span><span class="sxs-lookup"><span data-stu-id="d1422-354">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="d1422-355">DLP ポリシーを作成する際、段階的にロールアウトして、影響を評価して有効性をテストしてから、完全に適用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-355">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="d1422-356">たとえば、新しい DLP ポリシーを使用して、ユーザーが作業を完了するためにアクセスする必要がある数千のドキュメントへのアクセスを誤ってブロックすることはありません。</span><span class="sxs-lookup"><span data-stu-id="d1422-356">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="d1422-357">大きな影響を与える可能性が高い DLP ポリシーを作成しているときは、次の順序に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1422-357">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="d1422-358">**ポリシーヒントを使用せずにテストモードで開始**してから、DLP レポートとインシデントレポートを使用して影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="d1422-358">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact.</span></span> <span data-ttu-id="d1422-359">DLP レポートを使用して、番号、場所、種類、およびポリシー一致の重要度を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-359">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="d1422-360">この結果に基づき、必要に応じてルールを詳細に調整できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-360">Based on the results, you can fine tune the rules as needed.</span></span> <span data-ttu-id="d1422-361">テスト モードでは、DLP ポリシーは組織で業務に取り組んでいるユーザーの生産性に影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="d1422-361">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="d1422-p152">**通知とポリシー ヒントを利用するテスト モードに移行**して、コンプライアンス ポリシーについてユーザーを教育し、適用されるルールに対して準備できるようにします。この段階で、ルールをさらに精緻化できるように、ユーザーに誤検知を報告するよう依頼することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1422-p152">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="d1422-364">ルールのアクションが適用され、コンテンツが保護されるように、**ポリシーに対して完全な強制を開始**します。</span><span class="sxs-lookup"><span data-stu-id="d1422-364">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected.</span></span> <span data-ttu-id="d1422-365">DLP レポート、インシデント レポート、通知を引き続き監視して、結果が意図したとおりであるか確認します。</span><span class="sxs-lookup"><span data-stu-id="d1422-365">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
![テスト モードを使用しポリシーで有効化するオプション](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
<span data-ttu-id="d1422-367">DLP ポリシーは、ポリシー内のすべてのルールに影響を与える任意の時点でオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-367">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="d1422-368">ただし、ルールエディターで状態を切り替えることによって、各ルールを個別に無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d1422-368">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>
  
![ポリシー内のルールを無効にするオプション](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)
  
## <a name="dlp-reports"></a><span data-ttu-id="d1422-370">DLP レポート</span><span class="sxs-lookup"><span data-stu-id="d1422-370">DLP reports</span></span>

<span data-ttu-id="d1422-371">DLP ポリシーを作成して有効にした後、意図したとおりに動作していることを確認し、準拠した状態を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-371">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="d1422-372">DLP レポートを使用すると、長期間にわたる、一致する DLP ポリシーとルールの数や、誤検知と上書きの数をすぐに表示できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-372">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="d1422-373">各レポートでは、それらの一致項目を場所、期間でフィルター処理したり、特定のポリシー、ルール、アクションに絞り込んだりすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="d1422-373">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="d1422-374">DLP レポートによって、ビジネス上の洞察を得ることができ、同時に以下のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="d1422-374">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="d1422-375">特定の期間に絞り込み、スパイクや傾向の理由を理解します。</span><span class="sxs-lookup"><span data-stu-id="d1422-375">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="d1422-376">組織のコンプライアンスポリシーに違反するビジネスプロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="d1422-376">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="d1422-377">DLP ポリシーのビジネスに及ぼす影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="d1422-377">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="d1422-378">さらに、DLP レポートを使用すると、DLP ポリシーの実行時にそれらのポリシーを調整できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-378">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![セキュリティ/コンプライアンスセンターのレポートダッシュボード](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="d1422-380">DLP ポリシーのしくみ</span><span class="sxs-lookup"><span data-stu-id="d1422-380">How DLP policies work</span></span>

<span data-ttu-id="d1422-p156">DLP は、(単純なテキスト スキャンだけでなく) 詳細なコンテンツ分析を使用して、機密情報を検出します。この詳細なコンテンツ分析は、キーワード一致、辞書一致、正規表現の評価、内部関数などの方式を使用して、DLP ポリシーに一致するコンテンツを検出します。使用しているデータのうち、ごくわずかな割合のデータのみが機密性が高いと見なされる可能性があります。DLP ポリシーは、他のコンテンツを使用した作業を妨害したり影響を与えたりすることなく、対象データのみを識別、監視し、自動的に保護できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-p156">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="d1422-385">ポリシーの同期</span><span class="sxs-lookup"><span data-stu-id="d1422-385">Policies are synced</span></span>

<span data-ttu-id="d1422-386">セキュリティ&amp; /コンプライアンスセンターで DLP ポリシーを作成すると、そのポリシーは中央ポリシーストアに格納され、次のようにさまざまなコンテンツソースと同期されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-386">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="d1422-387">Exchange Online、outlook on the web、outlook</span><span class="sxs-lookup"><span data-stu-id="d1422-387">Exchange Online, and from there to Outlook on the web and Outlook</span></span>
    
- <span data-ttu-id="d1422-388">OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="d1422-388">OneDrive for Business sites</span></span>
    
- <span data-ttu-id="d1422-389">SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="d1422-389">SharePoint Online sites</span></span>
    
- <span data-ttu-id="d1422-390">Office デスクトッププログラム (Excel、PowerPoint、および Word)</span><span class="sxs-lookup"><span data-stu-id="d1422-390">Office desktop programs (Excel, PowerPoint, and Word)</span></span>

- <span data-ttu-id="d1422-391">Microsoft Teams チャンネルおよびチャット</span><span class="sxs-lookup"><span data-stu-id="d1422-391">Microsoft Teams channels and chats</span></span>
    
<span data-ttu-id="d1422-392">ポリシーが正しい場所に同期されると、コンテンツの評価とアクションの適用が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-392">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="d1422-393">OneDrive for Business サイトと SharePoint Online サイトのポリシー評価</span><span class="sxs-lookup"><span data-stu-id="d1422-393">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="d1422-394">SharePoint Online サイトと OneDrive for business サイトのすべてにおいて、ドキュメントは常に変更されています。これにより、継続的に作成、編集、共有などが行われます。</span><span class="sxs-lookup"><span data-stu-id="d1422-394">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="d1422-395">つまり、ドキュメントが DLP ポリシーに矛盾したり、準拠したりといったことがいつでも発生します。</span><span class="sxs-lookup"><span data-stu-id="d1422-395">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="d1422-396">たとえば、ユーザーがチーム サイトに機密情報が含まれていないドキュメントをアップロードし、後で別の人がそのドキュメントを編集して機密情報を追加することがあります。</span><span class="sxs-lookup"><span data-stu-id="d1422-396">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="d1422-397">このため、DLP ポリシーは、バックグラウンドでポリシーに一致しているかどうか頻繁にドキュメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1422-397">For this reason, DLP policies check documents for policy matches frequently in the background.</span></span> <span data-ttu-id="d1422-398">これを、非同期のポリシー評価と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-398">You can think of this as asynchronous policy evaluation.</span></span>
  
#### <a name="how-it-works"></a><span data-ttu-id="d1422-399">しくみ</span><span class="sxs-lookup"><span data-stu-id="d1422-399">How it works</span></span>
 
<span data-ttu-id="d1422-400">ユーザーがサイトでドキュメントを追加または変更すると、検索エンジンによってコンテンツがスキャンされ、後で検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d1422-400">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="d1422-401">これが発生していますが、機密情報のためにコンテンツもスキャンされ、共有されているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-401">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="d1422-402">検出された機密情報は検索インデックスに安全に格納されるため、コンプライアンスチームのみがアクセスできますが、一般的なユーザーにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d1422-402">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="d1422-403">オンにした各 DLP ポリシーはバックグラウンドで実行され (非同期)、ポリシーに一致するコンテンツについては検索頻度がよくチェックされ、不注意によるリークから保護するアクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="d1422-403">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![DLP ポリシーがコンテンツを非同期で評価する方法を示す図](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<span data-ttu-id="d1422-p160">最後に、ドキュメントが DLP ポリシーに矛盾し、その後 DLP ポリシーに準拠するようになることがあります。たとえば、ユーザーがドキュメントにクレジット カード番号を追加する場合、DLP ポリシーによってドキュメントへのアクセスが自動的にブロックされる可能性があります。しかしユーザーが後で機密情報を削除すると、次にドキュメントが対象ポリシーに対して再び評価されるときに、アクション (この例ではブロック) が自動的に取り消されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-p160">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="d1422-408">DLP は、インデックス処理が可能なすべてのコンテンツを評価します。</span><span class="sxs-lookup"><span data-stu-id="d1422-408">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="d1422-409">既定でクロールされるファイルの種類の詳細については、「既定のクロールされた[ファイル名拡張子」および「解析されたファイルの種類 (SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-409">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="d1422-410">Exchange Online、outlook、outlook on the web でのポリシー評価</span><span class="sxs-lookup"><span data-stu-id="d1422-410">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="d1422-411">exchange online を場所として含む DLP ポリシーを作成すると、ポリシーは Office 365 セキュリティ&amp;コンプライアンスセンターから exchange online に同期され、次に exchange online から web 上の outlook および outlook 上の outlook に同期されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-411">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="d1422-412">メッセージが Outlook で構成されている場合、ユーザーは作成されたコンテンツが DLP ポリシーに照らして評価されるときに、ポリシーヒントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-412">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="d1422-413">メッセージが送信されると、exchange メールフロールール (トランスポートルールとも呼ばれる) と exchange 管理センターで作成された dlp ポリシーと共に、電子メールフローの通常の一部として DLP ポリシーに対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-413">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="d1422-414">DLP ポリシーは、メッセージと添付ファイルの両方をスキャンします。</span><span class="sxs-lookup"><span data-stu-id="d1422-414">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="d1422-415">Office デスクトッププログラムでのポリシー評価</span><span class="sxs-lookup"><span data-stu-id="d1422-415">Policy evaluation in the Office desktop programs</span></span>

<span data-ttu-id="d1422-416">Excel、PowerPoint、および Word には、機密情報を識別し、DLP ポリシーを SharePoint Online と OneDrive for business として適用するのと同じ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1422-416">Excel, PowerPoint, and Word include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="d1422-417">これらの Office プログラムは、自分の dlp ポリシーを中央ポリシーストアから直接同期し、dlp ポリシーに含まれているサイトから開いたドキュメントをユーザーが操作するときに、dlp ポリシーに対してコンテンツを継続的に評価します。</span><span class="sxs-lookup"><span data-stu-id="d1422-417">These Office programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="d1422-418">Office での DLP ポリシーの評価は、プログラムのパフォーマンスや、コンテンツを扱うユーザーの生産性に影響を与えないように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d1422-418">DLP policy evaluation in Office is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="d1422-419">大きなドキュメントで作業している場合や、ユーザーのコンピューターがビジー状態になっている場合は、ポリシーヒントが表示されるまで数秒かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-419">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="d1422-420">Microsoft Teams でのポリシー評価</span><span class="sxs-lookup"><span data-stu-id="d1422-420">Policy evaluation in Microsoft Teams</span></span>
 
<span data-ttu-id="d1422-421">場所として Microsoft Teams を含む DLP ポリシーを作成すると、Office 365 セキュリティ&amp;コンプライアンスセンターからユーザーアカウントおよび Microsoft teams のチャネルとチャットにポリシーが同期されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-421">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chats.</span></span> <span data-ttu-id="d1422-422">DLP ポリシーの構成方法によっては、Microsoft Teams のチャットやチャネルで機密情報を共有しようとすると、メッセージをブロックまたは取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="d1422-422">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel, the message can be blocked or revoked.</span></span> <span data-ttu-id="d1422-423">また、機密情報が含まれていて、ゲスト (外部ユーザー) と共有されているドキュメントは、それらのユーザーに対しては開きません。</span><span class="sxs-lookup"><span data-stu-id="d1422-423">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span>

<span data-ttu-id="d1422-424">たとえば、他のユーザーが Teams のチャットまたはチャネル内の機密情報を外部ユーザーと共有しようとしたとします。</span><span class="sxs-lookup"><span data-stu-id="d1422-424">For example, suppose that someone attempts to share sensitive information in a Teams chat or channel with external users.</span></span> <span data-ttu-id="d1422-425">これを防ぐために定義された DLP ポリシーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="d1422-425">Suppose there's a DLP policy defined to prevent this.</span></span> <span data-ttu-id="d1422-426">保護を適用すると、外部ユーザーに送信される機密情報を含むメッセージが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d1422-426">With protection in place, messages containing sensitive information sent to external users are deleted.</span></span> <span data-ttu-id="d1422-427">これは数秒で行われ、DLP ポリシーの構成方法に従って自動的に発生します。</span><span class="sxs-lookup"><span data-stu-id="d1422-427">This happens within seconds, and it happens automatically, according to how the DLP policy is configured.</span></span>

<span data-ttu-id="d1422-428">ポリシーヒントは、メッセージがブロックされた、または取り消された理由について送信者に通知します。</span><span class="sxs-lookup"><span data-stu-id="d1422-428">Policy tips notify senders about why their messages were blocked or revoked.</span></span> <span data-ttu-id="d1422-429">たとえば、送信者には、すべてのユーザーとの共有が許可されていない個人情報 (pii) が含まれていることや、pii を含むドキュメントを組織外のユーザーと共有できないことが通知されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d1422-429">For example, a sender might be told that their message contains personally identifiable information (PII) that is not allowed to be shared with anyone, or that a document that contains PII cannot be shared with people outside their organization.</span></span> <span data-ttu-id="d1422-430">送信者は、DLP ポリシーに準拠するようにメッセージを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d1422-430">The sender can then edit their message to be compliant with DLP policies.</span></span>
 
## <a name="permissions"></a><span data-ttu-id="d1422-431">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d1422-431">Permissions</span></span>

<span data-ttu-id="d1422-432">DLP ポリシーを作成するコンプライアンスチームのメンバーは、セキュリティ&amp;コンプライアンスセンターに対するアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1422-432">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="d1422-433">既定では、テナント管理者は、この場所にアクセスできるようになり、テナント管理者や他の&amp;ユーザーには、テナント管理者のすべてのアクセス許可を付与することなく、セキュリティコンプライアンスセンターへのアクセス権を付与することができます。そのためには、次のことを行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1422-433">By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="d1422-434">Office 365 でグループを作成し、コンプライアンス担当者をそのグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1422-434">Create a group in Office 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="d1422-435">セキュリティ&amp; /コンプライアンスセンターの [**アクセス許可**] ページで役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1422-435">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 
    
3. <span data-ttu-id="d1422-436">Office 365 グループをその役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1422-436">Add the Office 365 group to the role group.</span></span>
    
<span data-ttu-id="d1422-437">詳細については、「[Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1422-437">For more information, see [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="d1422-438">DLP ポリシーを作成して適用するときにのみ、これらのアクセス許可が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d1422-438">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="d1422-439">ポリシーを適用する場合に、コンテンツへのアクセスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d1422-439">Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="d1422-440">DLP コマンドレットを検索する</span><span class="sxs-lookup"><span data-stu-id="d1422-440">Find the DLP cmdlets</span></span>

<span data-ttu-id="d1422-441">セキュリティ&amp; /コンプライアンスセンターのほとんどのコマンドレットを使用するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-441">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="d1422-442">リモート PowerShell を使用して Office 365 セキュリティ/コンプライアンス センターに接続する</span><span class="sxs-lookup"><span data-stu-id="d1422-442">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    
2. <span data-ttu-id="d1422-443">これらの[ポリシーおよびコンプライアンス-dlp のコマンドレット](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)を使用する</span><span class="sxs-lookup"><span data-stu-id="d1422-443">Use any of these [policy-and-compliance-dlp cmdlets](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)</span></span>
    
<span data-ttu-id="d1422-444">ただし、DLP レポートには、Exchange Online などの Office 365 間でデータをプルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-444">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="d1422-445">このため、 **DLP レポートのコマンドレットは Exchange Online powershell で使用できます (セキュリティ&amp;コンプライアンスセンターの powershell に**は含まれません)。</span><span class="sxs-lookup"><span data-stu-id="d1422-445">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="d1422-446">そのため、DLP レポートのコマンドレットを使用するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1422-446">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="d1422-447">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1422-447">Connect to Exchange Online using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)
    
2. <span data-ttu-id="d1422-448">次のいずれかのコマンドレットを DLP レポートに使用します。</span><span class="sxs-lookup"><span data-stu-id="d1422-448">Use any of these cmdlets for the DLP reports:</span></span>
    
  - [<span data-ttu-id="d1422-449">get-dlpdetectionsreport</span><span class="sxs-lookup"><span data-stu-id="d1422-449">Get-DlpDetectionsReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetectionsReport?view=exchange-ps)
    
  - [<span data-ttu-id="d1422-450">取得-dlpのレポート</span><span class="sxs-lookup"><span data-stu-id="d1422-450">Get-DlpDetailReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetailReport?view=exchange-ps)
    
## <a name="more-information"></a><span data-ttu-id="d1422-451">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d1422-451">More information</span></span>

- [<span data-ttu-id="d1422-452">テンプレートから DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d1422-452">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="d1422-453">通知を送信して、DLP ポリシーのポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="d1422-453">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="d1422-454">FCI または他のプロパティを含むドキュメントを保護するために DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d1422-454">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="d1422-455">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="d1422-455">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="d1422-456">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="d1422-456">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="d1422-457">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="d1422-457">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="d1422-458">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="d1422-458">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    

