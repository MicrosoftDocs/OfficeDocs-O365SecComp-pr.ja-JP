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
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 1966b2a7-d1e2-4d92-ab61-42efbb137f5e
description: Office 365 のセキュリティでデータ損失防止 (DLP) ポリシーを使用して&amp;コンプライアンス センターでは、識別、監視、および Office 365 の間で自動的に機密情報を保護することができます。
ms.openlocfilehash: c33fe53797f86208e7cd033029949737a5c84d2f
ms.sourcegitcommit: 397a5fe594e4cf4bb64c0c6f233d310ef3cbd922
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "25540423"
---
# <a name="overview-of-data-loss-prevention-policies"></a><span data-ttu-id="a401f-103">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="a401f-103">Overview of data loss prevention policies</span></span>

<span data-ttu-id="a401f-p101">ビジネス標準および業界の規制に準拠して、組織の機密情報を保護し、不注意による情報漏洩を防止する必要があります。組織外のリークを防止することもできますが、機密情報の例には、財務データやクレジット カード番号、社会保障番号、医療記録などの個人を特定できる情報 (PII) が含まれます。Office 365 のセキュリティでデータ損失防止 (DLP) ポリシーを使用して&amp;コンプライアンス センターでは、識別、監視、および Office 365 の間で自動的に機密情報を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p101">To comply with business standards and industry regulations, organizations need to protect sensitive information and prevent its inadvertent disclosure. Examples of sensitive information that you might want to prevent from leaking outside your organization include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>
  
<span data-ttu-id="a401f-107">DLP ポリシーを使用すると、以下のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="a401f-107">With a DLP policy, you can:</span></span>
  
- <span data-ttu-id="a401f-108">**Exchange のオンライン、SharePoint Online では、ビジネスのための OneDrive など、多くの場所の間で機密情報を識別します。**</span><span class="sxs-lookup"><span data-stu-id="a401f-108">**Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, and OneDrive for Business.**</span></span>
    
    <span data-ttu-id="a401f-109">ビジネスのサイトの任意の OneDrive に格納されているクレジット カード番号を含むすべてのドキュメントを識別するなど、特定の人の OneDrive のサイトだけを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="a401f-109">For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.</span></span>
    
- <span data-ttu-id="a401f-110">**機密情報を誤って共有することを防ぎます**。</span><span class="sxs-lookup"><span data-stu-id="a401f-110">**Prevent the accidental sharing of sensitive information**.</span></span> 
    
    <span data-ttu-id="a401f-111">などの任意の文書や、組織外のユーザーと共有されている状態のレコードを含む電子メールを識別して、自動的にそのドキュメントへのアクセスをブロックしたりから送信される電子メールをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="a401f-111">For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.</span></span>
    
- <span data-ttu-id="a401f-112">**デスクトップ バージョンの Excel 2016、PowerPoint 2016、Word 2016 内の機密情報を監視し、保護します。**</span><span class="sxs-lookup"><span data-stu-id="a401f-112">**Monitor and protect sensitive information in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016.**</span></span>
    
    <span data-ttu-id="a401f-p102">同じように Exchange のオンライン、SharePoint Online では、ビジネス、OneDrive にこれら Office 2016 デスクトップ プログラムには、機密情報を識別し、DLP ポリシーを適用すると同じ機能です。DLP では、これらの Office 2016 プログラム内のコンテンツを共有した場合に、継続的な監視を提供します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p102">Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office 2016 desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office 2016 programs.</span></span>
    
- <span data-ttu-id="a401f-115">**ユーザーがワークフローを中断せずに、コンプライアンスを準拠しつづける方法を学ぶよう支援します。**</span><span class="sxs-lookup"><span data-stu-id="a401f-115">**Help users learn how to stay compliant without interrupting their workflow.**</span></span>
    
    <span data-ttu-id="a401f-p103">DLP ポリシーについてユーザーを教育し、自分の作業をブロックすることがなく準拠を維持できるようにできます。などの場合は、ユーザーが機密情報を含むドキュメントを共有しようとすると、DLP ポリシー両方電子メール通知を送信でき、ビジネスがある場合、ポリシーを無効にすることができるドキュメント ライブラリのコンテキストでポリシーに関するヒントを表示両端揃えします。同様のポリシーのヒントは、web、Outlook 2013 と後で、2016 の Excel、PowerPoint 2016、および Word 2016 の Outlook にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p103">You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook 2013 and later, Excel 2016, PowerPoint 2016, and Word 2016.</span></span>
    
- <span data-ttu-id="a401f-119">**DLP のビューでは、組織の DLP ポリシーに一致する表示内容を報告します。**</span><span class="sxs-lookup"><span data-stu-id="a401f-119">**View DLP reports showing content that matches your organization's DLP policies.**</span></span>
    
    <span data-ttu-id="a401f-p104">DLP ポリシーを使用して、組織が遵守する方法を評価するには、各ポリシーに一致する数を確認でき、ルールには、時間の経過と共にします。DLP ポリシーは、ポリシーのヒントをオーバーライドし、誤検出を報告するユーザーを許可している場合は、ユーザーから報告された何も表示できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p104">To assess how your organization is complying with a DLP policy, you can see how many matches each policy and rule has over time. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported.</span></span>
    
<span data-ttu-id="a401f-122">作成し、Office 365 のセキュリティでは、データ損失防止ページ上の DLP ポリシーを管理する&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="a401f-122">You create and manage DLP policies on the Data loss prevention page in the Office 365 Security &amp; Compliance Center.</span></span>
  
![Office 365 のセキュリティでは、データ損失防止ページ&amp;コンプライアンス センター](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a><span data-ttu-id="a401f-124">DLP ポリシーの内容</span><span class="sxs-lookup"><span data-stu-id="a401f-124">What a DLP policy contains</span></span>

<span data-ttu-id="a401f-125">DLP ポリシーにはいくつかの基本的な内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a401f-125">A DLP policy contains a few basic things:</span></span>
  
- <span data-ttu-id="a401f-126">コンテンツ ・ ビジネス サイトの Exchange のオンライン、SharePoint Online では、OneDrive などの**場所**を保護する場所です。</span><span class="sxs-lookup"><span data-stu-id="a401f-126">Where to protect the content - **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites.</span></span> 
    
- <span data-ttu-id="a401f-127">**ルール**を適用してコンテンツを保護するタイミングと方法。ルールは次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a401f-127">When and how to protect the content by enforcing **rules** comprised of:</span></span> 
    
  - <span data-ttu-id="a401f-128">社会保障番号を含む、組織外のユーザーと共有されているコンテンツだけをたとえば、次の**条件**の規則を適用する - 前に内容が一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a401f-128">**Conditions** the content must match before the rule is enforced -- for example, look only for content containing Social Security numbers that's been shared with people outside your organization.</span></span> 
    
  - <span data-ttu-id="a401f-129">**アクション** 条件に一致するコンテンツが検出されるときにルールで自動実行されるアクションです。たとえば、ドキュメントに対するアクセスをブロックし、ユーザーとコンプライアンスの担当者の両方に電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="a401f-129">**Actions** that you want the rule to take automatically when content matching the conditions is found -- for example, block access to the document and send both the user and compliance officer an email notification.</span></span> 
    
<span data-ttu-id="a401f-130">特定の保護要件を満たすためにルールを使用し、DLP ポリシーを使用してすべての特定の規制に準拠するために必要なルールなどの一般的な保護要件をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-130">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="a401f-p105">たとえば、DLP ポリシーについては、医療保険の携行性と責任に関する法律 (HIPAA) の存在を検出するのに役立つがあります。この DLP ポリシーがデータを保護 HIPAA (何) すべての SharePoint Online サイトやビジネス サイト (where) のすべての OneDrive の間で (、組織外のユーザーと共有されている機密情報を含むすべてのドキュメントを検索します。条件) とは、ドキュメントへのアクセスをブロックし、(アクション) の通知を送信します。これらの要件は個々 のルールとして格納されているし、管理とレポート作成を簡略化する DLP ポリシーとしてグループ化します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p105">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA). This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions). These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![図は、DLP ポリシーに場所とルールが含まれていることを示しています。](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a><span data-ttu-id="a401f-135">場所</span><span class="sxs-lookup"><span data-stu-id="a401f-135">Locations</span></span>

<span data-ttu-id="a401f-p106">DLP ポリシーでは、検索でき、その情報が SharePoint Online では、Exchange のオンラインまたはビジネスのための OneDrive であるかどうか、Office 365 の間で機密情報を保護することができます。ことも簡単にできますすべての SharePoint サイトまたは OneDrive のアカウントを保護するだけで特定のサイトまたは取引先企業、またはすべてのメールボックス。まだ特定のユーザーのメールボックスのみを選択することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a401f-p106">A DLP policy can find and protect sensitive information across Office 365, whether that information is located in Exchange Online, SharePoint Online, or OneDrive for Business. You can easily choose to protect all SharePoint sites or OneDrive accounts, just specific sites or accounts, or all mailboxes. Note that it's not yet possible to select just the mailboxes of specific users.</span></span>
  
![DLP ポリシーを適用できる場所のオプション](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
<span data-ttu-id="a401f-p107">ノートの特定の SharePoint サイトまたは OneDrive アカウントを含めたり除外したりする場合は、DLP ポリシーによって、100 を超えない含めることができますこのようなインクルードとエクスクルードします。この制限が存在しますが、組織全体のポリシーまたは全体の場所に適用されるポリシーを適用することによってこの制限を超えることができることを理解します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p107">Note that if you choose to include or exclude specific SharePoint sites or OneDrive accounts, a DLP policy can contain no more than 100 such inclusions and exclusions. Although this limit exists, understand that you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="rules"></a><span data-ttu-id="a401f-142">ルール</span><span class="sxs-lookup"><span data-stu-id="a401f-142">Rules</span></span>

<span data-ttu-id="a401f-p108">規則は、組織のコンテンツには、お客様のビジネス要件を適用するものです。ポリシーには、1 つまたは複数のルールが含まれていて、各規則は、条件とアクションで構成されます。規則ごとに、条件が満たされると、アクションが作成され、自動的にします。ルールは、各ポリシーの最高優先順位のルールから、順番に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p108">Rules are what enforce your business requirements on your organization's content. A policy contains one or more rules, and each rule consists of conditions and actions. For each rule, when the conditions are met, the actions are taken automatically. Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="a401f-147">ルールには、(ポリシーのヒントやメール通知) を持つユーザーに通知するオプションも用意されています、コンテンツ (電子メール インシデント レポート) を持つ管理者がルールに該当します。</span><span class="sxs-lookup"><span data-stu-id="a401f-147">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="a401f-148">ここでは、ルールの構成要素をそれぞれ詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="a401f-148">Here are the components of a rule, each explained below.</span></span>
  
![DLP ルール エディターのセクション](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="a401f-150">条件</span><span class="sxs-lookup"><span data-stu-id="a401f-150">Conditions</span></span>

<span data-ttu-id="a401f-p109">条件は、どの種類の情報を探して、およびアクションを実行するタイミングを判断するために重要です。などのコンテンツが 10 を超えるような数値が含まれていて、組織外のユーザーと共有されていない限り、コンテンツの含まれるパスポート番号を無視することもできます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p109">Conditions are important because they determine what types of information you're looking for, and when to take an action. For example, you might choose to ignore content containing passport numbers unless the content contains more than ten such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="a401f-p110">条件は、**コンテンツ**をどのような種類の機密情報を探しているなどなどの**コンテキスト**でドキュメントを共有する集中します。異なったリスク レベルに異なるアクションを割り当てるには条件を使用することができます--たとえば、機密性の高いコンテンツを社内で共有可能性がありますリスクの軽減、組織外のユーザーと共有する機密性の高いコンテンツよりも少ない操作を必要とします。</span><span class="sxs-lookup"><span data-stu-id="a401f-p110">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with. You can use conditions to assign different actions to different risk levels -- for example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![利用可能な DLP 条件の一覧](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="a401f-156">以下の内容を判断できる条件が使用可能になっています。</span><span class="sxs-lookup"><span data-stu-id="a401f-156">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="a401f-157">コンテンツには、機密性の高い情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a401f-157">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="a401f-p111">コンテンツには、ラベルが含まれています。詳細についてを参照してください、次のセクションの[DLP ポリシーの条件としてのラベルを使用](data-loss-prevention-policies.md#label)します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p111">Content contains a label. For more information, see the below section [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#label).</span></span>
    
- <span data-ttu-id="a401f-160">コンテンツが組織の内または外のユーザーと共有されている。</span><span class="sxs-lookup"><span data-stu-id="a401f-160">Content is shared with people outside or inside your organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="a401f-161">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="a401f-161">Types of sensitive information</span></span>

<span data-ttu-id="a401f-p112">DLP ポリシーは、**機密性の高い情報の種類**として定義されている機密情報を保護できます。Office 365 には、クレジット カード番号、銀行口座番号、国 ID 番号、パスポート番号などを使用する準備ができている多くの異なる地域間での多くの一般的な種類の機密情報の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a401f-p112">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**. Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![使用できる機密情報の種類の一覧](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="a401f-p113">DLP ポリシーは、クレジット カード番号などの機密性の高い情報の種類を検索するときにだけでは検索しません 16 桁の番号です。機密性の高い情報の各種類を定義しの組み合わせを使用して検出されました。</span><span class="sxs-lookup"><span data-stu-id="a401f-p113">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number. Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="a401f-167">キーワード</span><span class="sxs-lookup"><span data-stu-id="a401f-167">Keywords</span></span>
    
- <span data-ttu-id="a401f-168">内部関数。チェックサムや構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="a401f-168">Internal functions to validate checksums or composition</span></span>
    
- <span data-ttu-id="a401f-169">パターン一致を検索するための正規表現の評価</span><span class="sxs-lookup"><span data-stu-id="a401f-169">Evaluation of regular expressions to find pattern matches</span></span>
    
- <span data-ttu-id="a401f-170">その他のコンテンツの検査</span><span class="sxs-lookup"><span data-stu-id="a401f-170">Other content examination</span></span>
    
<span data-ttu-id="a401f-171">各人の作業を中断することができますが、偽陽性の数を削減しながら高度な精度を実現する DLP の検出に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a401f-171">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="a401f-172">操作</span><span class="sxs-lookup"><span data-stu-id="a401f-172">Actions</span></span>

<span data-ttu-id="a401f-173">コンテンツには、ルールの条件が一致すると、自動的にコンテンツを保護するためのアクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-173">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![使用できる DLP アクションの一覧](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="a401f-175">発売中のアクションは、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="a401f-175">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="a401f-p114">**コンテンツへのアクセスを制限します。** サイトのコンテンツ、ドキュメントのアクセス権がプライマリ サイト コレクション管理者、ドキュメントの所有者、およびドキュメントの最終更新者以外のすべてのユーザーに対して制限されていることを意味します。これらの人々 では、機密性の高い情報を文書から削除したり、他の改善措置を実行することができます。ドキュメントは、コンプライアンスでは、元のアクセス許可が自動的に復元します。ドキュメントへのアクセスがブロックされると、ドキュメントがサイトのライブラリでは、特別なポリシー ヒントのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p114">**Restrict access to the content** For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document. These people can remove the sensitive information from the document or take other remedial action. When the document is in compliance, the original permissions will be automatically restored. When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
    ![ドキュメントへのアクセスがブロックされていることを示すポリシーのヒント](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    <span data-ttu-id="a401f-p115">E メールの内容には、この操作はから送信されるメッセージをブロックします。DLP ルールの構成方法によっては、送信者は NDR を見たり (かどうかは、ルールを使用して通知) ポリシーのヒントや電子メールの通知します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p115">For email content, this action blocks the message from being sent. Depending on how the DLP rule is configured, the sender will see an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
    ![権限のない受信者をメッセージから削除する必要があることを警告](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="a401f-184">ユーザーに通知し、ユーザーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="a401f-184">User notifications and user overrides</span></span>

<span data-ttu-id="a401f-p116">通知を使用することができ、DLP ポリシーについてユーザーを教育し、自分の作業をブロックすることがなく準拠を維持するためにオーバーライドします。などの場合は、ユーザーが機密情報を含むドキュメントを共有しようとすると、DLP ポリシー両方電子メール通知を送信でき、ビジネスがある場合、ポリシーを無効にすることができるドキュメント ライブラリのコンテキストでポリシーに関するヒントを表示両端揃えします。</span><span class="sxs-lookup"><span data-stu-id="a401f-p116">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![ユーザーの通知およびユーザー DLP ルール エディターのセクションをオーバーライドします。](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="a401f-p117">電子メールの送信、共有、または最後のコンテンツと、サイトのコンテンツは、サイト コレクションの管理者とドキュメント所有者を変更したユーザーに通知できます。さらに、追加したり、ユーザーを削除する電子メール通知を選択します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p117">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner. In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="a401f-190">電子メール通知を送信するだけでなく、ユーザーへの通知には、ポリシーに関するヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a401f-190">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="a401f-191">2013 およびそれ以降の Outlook と web 上の Outlook です。</span><span class="sxs-lookup"><span data-stu-id="a401f-191">In Outlook 2013 and later and Outlook on the web.</span></span>
    
- <span data-ttu-id="a401f-192">ビジネス サイトのドキュメントを SharePoint Online または OneDrive で。</span><span class="sxs-lookup"><span data-stu-id="a401f-192">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="a401f-193">Excel の 2016年 2016 の PowerPoint、および Word 2016、サイトのドキュメントが格納されている場合に含まれている DLP ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="a401f-193">In Excel 2016, PowerPoint 2016, and Word 2016, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="a401f-p118">E メール通知とポリシーのヒントは、コンテンツが DLP ポリシーと競合する理由について説明します。選択した場合、e メール通知とポリシーのヒントは、誤検知の報告や、業務の妥当性を提供することにより、ルールを無効にユーザーを許可できます。これは、DLP ポリシーについてユーザーを教育し、業務遂行を禁止することがなくそれを適用することができます。オーバーライドと誤検出についての情報も (DLP レポートについては、下記参照) を報告するための記録は、インシデントに含まれているレポート (次のセクション)、法令遵守責任者は、この情報を定期的に確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a401f-p118">The email notification and policy tip explain why content conflicts with a DLP policy. If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification. This can help you educate users about your DLP policies and enforce them without preventing people from doing their work. Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="a401f-198">ポリシー ヒントがどんなものか、OneDrive のビジネス アカウントには、ここで。</span><span class="sxs-lookup"><span data-stu-id="a401f-198">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![OneDrive アカウント内のドキュメントのポリシーのヒント](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a><span data-ttu-id="a401f-200">インシデント レポート</span><span class="sxs-lookup"><span data-stu-id="a401f-200">Incident reports</span></span>

<span data-ttu-id="a401f-p119">ルールが一致する場合は、イベントの詳細を法令遵守責任者 (または選択した任意のユーザー) にインシデント レポートを送信できます。このレポートには、一致した項目の規則、およびコンテンツの最終更新者の名前に一致する実際のコンテンツに関する情報が含まれています。、電子メール メッセージのレポートも含まれています添付ファイルとして DLP ポリシーに一致する元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="a401f-p119">When a rule is matched, you can send an incident report to your compliance officer (or any people you choose) with details of the event. This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content. For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>
  
![インシデント レポートを構成するためのページ](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="a401f-205">グループ化、および論理演算子</span><span class="sxs-lookup"><span data-stu-id="a401f-205">Grouping and logical operators</span></span>

<span data-ttu-id="a401f-p120">多くの場合、DLP ポリシーは、米国社会保障番号を含むすべてのコンテンツを識別するように簡単な要件を持っています。ただし、他のシナリオでは、DLP ポリシーはより大まかに定義されたデータを識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a401f-p120">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number. However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="a401f-208">たとえば、米国健康保険法律 (HIPAA) の対象のコンテンツを特定するを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a401f-208">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="a401f-209">米国社会保障番号や製薬執行局 (DEA) 番号などの機密情報の特定の種類を含むコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="a401f-209">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="a401f-210">AND</span><span class="sxs-lookup"><span data-stu-id="a401f-210">AND</span></span>
    
- <span data-ttu-id="a401f-p121">コンテンツをより識別が困難な患者のケアや医療サービスの提供の説明に関する通信などです。このコンテンツを識別するには、国際分類の病気 (ICD ・ 9 ・ CM または ICD-10-CM) など、非常に大規模なキーワード リストのキーワードに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a401f-p121">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided. Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="a401f-p122">グループ化演算子と論理演算子 (AND、OR) を使用して大まかに定義されたそのようなデータを簡単に識別できます。DLP ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p122">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR). When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="a401f-215">機密性の高い情報の種類をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="a401f-215">Group sensitive information types.</span></span>
    
- <span data-ttu-id="a401f-216">グループ内の機密性の高い情報の種類間、およびグループ全体の論理演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="a401f-216">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="a401f-217">グループ内で演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="a401f-217">Choosing the operator within a group</span></span>

<span data-ttu-id="a401f-218">、グループ内で、ルールと一致するコンテンツのグループの条件の一部またはすべてを満たしていなければならないかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-218">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![グループは、グループ内での演算子の表示](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="a401f-220">グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="a401f-220">Adding a group</span></span>

<span data-ttu-id="a401f-221">独自の条件とそのグループの中で演算子を持つことができるグループをすばやく追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a401f-221">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![グループ化] ボタンを追加します。](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="a401f-223">グループ間の演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="a401f-223">Choosing the operator between groups</span></span>

<span data-ttu-id="a401f-224">グループ間で、規則に一致するコンテンツの 1 つのグループ、またはグループのすべての条件を満たす必要があるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-224">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="a401f-225">たとえば、組み込みの**米国 HIPAA**のポリシーでは、含まれているコンテンツを識別するためにグループ間で**AND**演算子を使用するルールがされています。</span><span class="sxs-lookup"><span data-stu-id="a401f-225">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="a401f-226">**PII 識別子**(少なくとも 1 つ SSN 番号**または**DEA) グループから</span><span class="sxs-lookup"><span data-stu-id="a401f-226">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="a401f-227">**AND**</span><span class="sxs-lookup"><span data-stu-id="a401f-227">**AND**</span></span>
    
- <span data-ttu-id="a401f-228">**医療用語**(1 つ以上の ICD ・ 9 ・ CM キーワード**または**ICD-10-CM キーワード) のグループから</span><span class="sxs-lookup"><span data-stu-id="a401f-228">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![グループのグループ間の演算子の表示](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="a401f-230">ルールの処理の優先順位</span><span class="sxs-lookup"><span data-stu-id="a401f-230">The priority by which rules are processed</span></span>

<span data-ttu-id="a401f-p123">ポリシーの規則を作成すると、各ルールが作成されていること - つまり、作成したルールは、最初に最初の優先順位が順に優先順位を割り当てられている、2 番目に作成されたルールは、2 番目の優先度というように。ルールを作成したら、その優先順位は変更できませんを削除して再作成することを除きます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p123">When you create rules in a policy, each rule is assigned a priority in the order in which it's created - meaning, the rule created first has first priority, the rule created second has second priority, and so on. After you create a rule, its priority can't be changed, except by deleting and re-creating it.</span></span>
  
![優先順位の規則](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
<span data-ttu-id="a401f-p124">ルールの内容が評価されると、ルールは、優先度順に処理します。コンテンツには、複数の規則が一致すると、ルールは、優先度順に処理し、最も限定的なアクションが適用されます。などのコンテンツには、次の規則のすべてが一致すると、ルール 3 が適用される優先順位が最も高い、最も制限の厳しいルールであるため。</span><span class="sxs-lookup"><span data-stu-id="a401f-p124">When content is evaluated against rules, the rules are processed in priority order. If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced. For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="a401f-237">規則 1: にのみユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a401f-237">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="a401f-238">規則 2: ユーザーへの通知へのアクセスを制限でき、ユーザーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="a401f-238">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="a401f-239">規則 3: ユーザーへの通知へのアクセスを制限し、ユーザーのオーバーライドを許可しません。</span><span class="sxs-lookup"><span data-stu-id="a401f-239">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="a401f-240">規則 4: にのみユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a401f-240">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="a401f-241">規則 5: アクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="a401f-241">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="a401f-242">規則 6: ユーザーへの通知へのアクセスを制限し、ユーザーのオーバーライドを許可しません。</span><span class="sxs-lookup"><span data-stu-id="a401f-242">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="a401f-243">最も制限の厳しいルールのみが適用される場合でもこの例では、すべてのルールに一致するものが監査ログに記録し、DLP レポートに示すようを確認します。</span><span class="sxs-lookup"><span data-stu-id="a401f-243">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="a401f-244">ポリシーのヒントについては、基準点に注意します。</span><span class="sxs-lookup"><span data-stu-id="a401f-244">With respect to policy tips, note that:</span></span>
  
- <span data-ttu-id="a401f-p125">のみ最高の優先順位からポリシー ヒント、最も制限の厳しいルールが表示されます。たとえば、単に通知を送信するルールをポリシーのヒントに表示されるコンテンツへのアクセスをブロック ルールをポリシー ヒントです。これは人が次々 にポリシーのヒントを表示することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p125">Only the policy tip from the highest priority, most restrictive rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="a401f-248">最も制限の厳しいルールのポリシー ヒントによってルールの上書きがユーザーに許可される場合、対象ルールを上書きすると、コンテンツが一致する他のルールも上書きされます。</span><span class="sxs-lookup"><span data-stu-id="a401f-248">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="a401f-249">難易と一致するようにするためのルールの調整</span><span class="sxs-lookup"><span data-stu-id="a401f-249">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="a401f-250">人を作成して、DLP ポリシーを有効にすると、場合によってこれらの問題に実行します。</span><span class="sxs-lookup"><span data-stu-id="a401f-250">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="a401f-251">内容が機密情報の**ではありません**が、ルール - つまり、誤検知が多すぎると一致しているが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="a401f-251">Too much content that **is not** sensitive information matches the rules - in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="a401f-252">機密情報に**は**ルールに一致することは-機密性の高い情報に防策を適用していないつまり、少なすぎるの内容。</span><span class="sxs-lookup"><span data-stu-id="a401f-252">Too little content that **is** sensitive information matches the rules - in other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="a401f-p126">これらの問題に対処するためは、インスタンスの数を調整することによって、ルールを調整しすることが困難、またはルールに一致するコンテンツを簡単に正確に一致します。ルールで使用されている機密性の高い情報の種類ごとには、両方のインスタンスをカウントして正確に一致します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p126">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules. Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="a401f-255">インスタンスの数</span><span class="sxs-lookup"><span data-stu-id="a401f-255">Instance count</span></span>

<span data-ttu-id="a401f-p127">インスタンスの数は、単に機密情報の特定の種類の繰り返しの回数が規則に一致するコンテンツのために存在する必要があります。などのコンテンツ固有米国または英国の 1 から 9 の間でパスポート番号が識別を次に示す規則に一致します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p127">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule. For example, content will match the rule shown below if between 1 and 9 unique U.S. or U.K. passport numbers are identified.</span></span>
  
<span data-ttu-id="a401f-p128">インスタンスの数に機密性の高い情報の種類とキーワードの**一意**の一致のみが含まれることに注意してください。たとえば、電子メールには、同一のクレジット カード番号の 10 回が含まれている場合、その 10 回は、クレジット カード番号の 1 つのインスタンスとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p128">Note that the instance count includes only **unique** matches for sensitive information types and keywords. For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span> 
  
<span data-ttu-id="a401f-261">インスタンスの数を使用すると、ルールを調整して、このガイドでは簡単です。</span><span class="sxs-lookup"><span data-stu-id="a401f-261">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="a401f-p129">ルールを一致するように簡単にようにするには、**最小**の数を減らすし、**最大**数を増やします。設定することも**最大**に**任意**の数値を削除することによって。</span><span class="sxs-lookup"><span data-stu-id="a401f-p129">To make the rule easier to match, decrease the **min** count and/or increase the **max** count. You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="a401f-264">ルールを困難に一致するようにするには、**最小**数を増やします。</span><span class="sxs-lookup"><span data-stu-id="a401f-264">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="a401f-p130">通常、下のインスタンスの数 (たとえば、1 ~ 9) のルールで、ユーザーの通知を送信するより制限の少ないアクションを使用します。(たとえば、10 のいずれか) のインスタンスの数を上位のルールで、ユーザーのオーバーライドを許可することがなくコンテンツへのアクセスを制限するより制限の厳しいアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p130">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9). And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![規則エディターでインスタンスをカウントします。](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="a401f-268">一致精度</span><span class="sxs-lookup"><span data-stu-id="a401f-268">Match accuracy</span></span>

<span data-ttu-id="a401f-p131">前述したように、機密性の高い情報の種類が定義され、証拠の種類の組み合わせを使用して検出します。一般的には、機密性の高い情報の種類は、このようなパターンと呼ばれる複数の組み合わせによって定義されます。以下の証拠を必要とするパターンは、一致精度の低い (または信頼度のレベル)、確実な証拠には、一致精度の高い (または信頼度のレベル) が必要なパターンの中に。実際のパターンとすべての機密情報の種類で使用されている信頼レベルの詳細については、[どのような機密性の高い情報の種類を探して](what-the-sensitive-information-types-look-for.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a401f-p131">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence. Commonly, a sensitive information type is defined by multiple such combinations, called patterns. A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level). To learn more about the actual patterns and confidence levels used by every sensitive information type, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
<span data-ttu-id="a401f-273">たとえば、クレジット カード番号で指定された情報の機密性の高い型は、2 つのパターンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="a401f-273">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="a401f-274">65% 自信を必要とするパターン。</span><span class="sxs-lookup"><span data-stu-id="a401f-274">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="a401f-275">クレジット カード番号の形式での数です。</span><span class="sxs-lookup"><span data-stu-id="a401f-275">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="a401f-276">チェックサムを通過する数です。</span><span class="sxs-lookup"><span data-stu-id="a401f-276">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="a401f-277">85% 自信を必要とするパターン。</span><span class="sxs-lookup"><span data-stu-id="a401f-277">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="a401f-278">クレジット カード番号の形式での数です。</span><span class="sxs-lookup"><span data-stu-id="a401f-278">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="a401f-279">チェックサムを通過する数です。</span><span class="sxs-lookup"><span data-stu-id="a401f-279">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="a401f-280">キーワードまたは正しい形式で有効期限の日付。</span><span class="sxs-lookup"><span data-stu-id="a401f-280">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="a401f-p132">これらを使用して信頼レベル (または一致精度) ルールにします。通常、一致精度の下でのルールで、ユーザーの通知を送信するより制限の少ないアクションを使用します。一致精度を上げるとルールでユーザーのオーバーライドを許可することがなくコンテンツへのアクセスを制限するより制限の厳しいアクションを使用する.</span><span class="sxs-lookup"><span data-stu-id="a401f-p132">You can use these confidence levels (or match accuracy) in your rules. Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy. And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="a401f-284">コンテンツで、クレジット カード番号などの機密情報の特定の種類が識別されると、1 つの信頼度のレベルだけが返されることを理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a401f-284">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="a401f-285">1 つのパターンのすべての一致する場合は、そのパターンの信頼レベルが返されます。</span><span class="sxs-lookup"><span data-stu-id="a401f-285">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="a401f-p133">複数のパターンに一致するものがある場合 (つまり、2 つの異なる信頼レベルと一致するもの) があるだけで 1 つのパターンのいずれかより高い信頼レベルが返されます。これは、注意が必要です。などのクレジット カードは、65% と 85% の両方のパターンが一致する場合、信頼レベルが返されますの確実な証拠より自信を意味するため機密性の高い情報の種類は 90% を超えています。</span><span class="sxs-lookup"><span data-stu-id="a401f-p133">If there are matches for more than one pattern (i.e., there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned. This is the tricky part. For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="a401f-p134">クレジット カード、65% の一致精度の 1 つは、85% の一致の精度を 1 つの相互に排他的な 2 つのルールを作成する場合は、一致精度の範囲は次のとおりです。最初のルールは、65% のパターンの一致するものだけを選択します。2 番目のルールの選択は、85% の**少なくとも 1 つ**の一致**ができる可能性がある**とその他の信頼性の低い一致に一致します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p134">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this. The first rule picks up only matches of the 65% pattern. The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![一致精度の異なる範囲の 2 つの規則](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="a401f-293">これらの理由から、別の一致が精度ルールを作成するためのガイダンスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a401f-293">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="a401f-294">最下位の信頼レベルは、通常の**最小値**と**最大**(範囲ではなく) 同じ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a401f-294">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="a401f-295">最高の信頼レベルは、通常から 100 に下限の信頼レベルのすぐ上の範囲です。</span><span class="sxs-lookup"><span data-stu-id="a401f-295">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="a401f-296">中間の信頼レベルは、通常より高い信頼レベルの下だけに下限の信頼レベルのすぐ上から範囲です。</span><span class="sxs-lookup"><span data-stu-id="a401f-296">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="a401f-297">DLP ポリシーにおける条件としてのラベルの使用</span><span class="sxs-lookup"><span data-stu-id="a401f-297">Using a label as a condition in a DLP policy</span></span>

<span data-ttu-id="a401f-298">ラベルを作成することができ、。</span><span class="sxs-lookup"><span data-stu-id="a401f-298">You can create a label and then:</span></span>
  
- <span data-ttu-id="a401f-299">**発行**エンド ・ ユーザーを参照してくださいして手動でコンテンツにラベルを適用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a401f-299">**Publish** it, so that end users can see and manually apply the label to content.</span></span> 
    
- <span data-ttu-id="a401f-300">選択した条件に一致するコンテンツは、**自動適用**します。</span><span class="sxs-lookup"><span data-stu-id="a401f-300">**Auto-apply** it to content that matches the conditions that you choose.</span></span> 
    
<span data-ttu-id="a401f-301">ラベルの詳細については、「[ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a401f-301">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
<span data-ttu-id="a401f-p135">ラベルを作成した後は、DLP ポリシーにそのラベルを条件として、使用できます。などのためにこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p135">After you create a label, you can then use that label as a condition in your DLP policies. For example, you might want to do this because:</span></span>
  
- <span data-ttu-id="a401f-p136">**社外秘**」という名前のラベルを発行したは、組織内のユーザーが機密性の高い電子メールやドキュメントにラベルを手動で適用できますように。このラベルを使用すると、DLP ポリシーの条件として、組織外のユーザーと共有されているから**社外秘**というラベルの付いたコンテンツを制限できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p136">You published a label named **Confidential**, so that people in your organization can manually apply the label to confidential email and documents. By using this label as a condition in your DLP policy, you can restrict content labeled **Confidential** from being shared with people outside your organization.</span></span> 
    
- <span data-ttu-id="a401f-p137">**アルペン ハウス**をという名前の名前、プロジェクトのラベルを作成し、「高山の家」のキーワードを含むコンテンツ自動的ラベルを適用します。このラベルを使用すると、DLP ポリシーの条件として、組織外のユーザーとコンテンツを共有しようとしている場合に、エンド ・ ユーザーにポリシーに関するヒントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p137">You created a label named **Alpine House** for a project of that name, and then applied that label automatically to content containing the keywords "Alpine House". By using this label as a condition in your DLP policy, you can show a policy tip to end users when they're about to share this content with someone outside your organization.</span></span> 
    
- <span data-ttu-id="a401f-p138">**税レコード**、という名前のラベルを発行したは、レコード管理者がレコードとして分類される必要があるコンテンツにラベルを手動で適用できますように。このラベルを使用すると、DLP ポリシーの条件として、ITINs または Ssn; などの機密情報の他の種類と組み合わせて、このラベルのコンテンツを検索すること**税レコード**というラベルの付いたコンテンツへの保護操作を適用します。DLP レポートから DLP ポリシーについての詳細な利用状況レポートを取得し、監査ログのデータです。</span><span class="sxs-lookup"><span data-stu-id="a401f-p138">You published a label named **Tax record**, so that your records manager can manually apply the label to content that needs to be classified as a record. By using this label as a condition in your DLP policy, you can look for content with this label in conjunction with other types of sensitive information such as ITINs or SSNs; apply protection actions to content labeled **Tax record**; and get detailed activity reports about the DLP policy from the DLP reports and audit log data.</span></span> 
    
- <span data-ttu-id="a401f-p139">Exchange メールボックスと経営幹部のグループのアカウントを OneDrive に**経営幹部のリーダーシップ ・ チームの区別**をというラベルを公開しました。このラベルを使用すると、DLP ポリシーの条件として、コンテンツとユーザーの同じサブセットの保存と保護の両方のアクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p139">You published a label named **Executive Leadership Team - Sensitive** to the Exchange mailboxes and OneDrive accounts of a group of executives. By using this label as a condition in your DLP policy, you can enforce both retention and protection actions on the same subset of content and users.</span></span> 
    
<span data-ttu-id="a401f-312">ラベルを使用して、DLP ルールの条件として、ことがでくを選択して適用内容、場所、またはユーザーの特定のセットの操作を保護します。</span><span class="sxs-lookup"><span data-stu-id="a401f-312">By using labels as a condition in your DLP rules, can you selectively enforce protection actions on a specific set of content, locations, or users.</span></span>
  
![ラベルを条件として](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="a401f-314">この機能をその他の機能に関連する方法</span><span class="sxs-lookup"><span data-stu-id="a401f-314">How this feature relates to other features</span></span>

<span data-ttu-id="a401f-315">いくつかの機能は、機密情報を含むコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-315">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="a401f-316">[条件に基づいて自動的にラベルを適用する][保存期間のラベル](labels.md#applying-a-retention-label-automatically-based-on-conditions)と[リテンション ・ ポリシー](retention-policies.md)両方このコンテンツの**保存**の操作を適用できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-316">A [retention label](labels.md#applying-a-retention-label-automatically-based-on-conditions)[Applying a label automatically based on conditions] and a [retention policy](retention-policies.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="a401f-p140">DLP ポリシーは、このコンテンツの**保護**操作を適用できます。これらのアクションを適用する前に、DLP ポリシーがその他の条件を満たす必要があるだけでなく、ラベルが含まれているコンテンツを要求できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p140">A DLP policy can enforce **protection** actions on this content. And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![機密情報に適用できる機能の図](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="a401f-p141">DLP ポリシーが機密情報に適用されるラベルまたは保持ポリシーよりも豊富な検出機能を持つことに注意してください。DLP ポリシーは、機密性の高い情報を含むコンテンツの防策を適用でき、機密性の高い情報をコンテンツから削除する場合、防策は取り消されます次回コンテンツのスキャンします。機密情報を含むコンテンツにアイテム保持ポリシーまたはラベルを適用する場合、機密性の高い情報が削除された場合でも元に戻すことなくが 1 回限りのアクション。</span><span class="sxs-lookup"><span data-stu-id="a401f-p141">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information. A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned. But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information's removed.</span></span>
  
<span data-ttu-id="a401f-p142">ラベルを使用して、DLP ポリシーの条件として、そのラベルにコンテンツを保存および保護の両方のアクションを適用できます。機密情報を含むコンテンツと同じようにラベルを含むコンテンツを考えることができます - および機密情報の種類とラベルの両方が、そのコンテンツに対してアクションを設定できるように、コンテンツを分類するためのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a401f-p142">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label. You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![DLP ポリシーの条件としてラベルを使用しての図](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="a401f-326">簡単な設定と高度の設定</span><span class="sxs-lookup"><span data-stu-id="a401f-326">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="a401f-327">DLP ポリシーを作成するときに単純または高度な設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="a401f-327">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="a401f-328">**単純な設定**しやすいようにルールを作成または変更、規則エディターを使用せず、DLP ポリシーの最も一般的な種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="a401f-328">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="a401f-329">**詳細設定**エディターを使用してルール DLP ポリシーのすべての設定を完全に制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="a401f-329">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="a401f-p143">心配する必要は、簡単な設定と高度な設定作業とまったく同じ条件とアクションの - 簡単な設定でのみで構成されたルールを適用することで、規則エディターが表示されません。DLP ポリシーを作成する簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="a401f-p143">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions -- only with simple settings, you don't see the rule editor. It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="a401f-332">簡単な設定</span><span class="sxs-lookup"><span data-stu-id="a401f-332">Simple settings</span></span>

<span data-ttu-id="a401f-p144">DLP 一般的には、コンテンツにアクセスできるユーザー、組織、および制限などの自動改善措置を取る外のユーザーと共有されているから機密情報を含むコンテンツを保護するためにポリシーを作成する、エンド ・ ユーザーまたは管理者の通知を送信して、後で調査のためのイベントを監査します。ユーザーは、機密情報の不注意な開示を防ぐため、DLP を使用します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p144">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remedial action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation. People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="a401f-p145">DLP ポリシーを作成するときに、この目標を達成するためを容易には、**単純な設定を使用する**を選択できます。これらの設定は、規則エディターに移動することがなく、最も一般的な DLP ポリシーを実装するために必要なものすべてを提供します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p145">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**. These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![DLP シンプルかつ高度な設定オプション](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="a401f-338">詳細設定</span><span class="sxs-lookup"><span data-stu-id="a401f-338">Advanced settings</span></span>

<span data-ttu-id="a401f-339">複数のカスタマイズされた DLP ポリシーを作成する場合は、**詳細設定を使用する**ことができます。</span><span class="sxs-lookup"><span data-stu-id="a401f-339">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="a401f-340">規則エディターで、インスタンスの数を含む、すべての可能なオプションを完全に制御している各ルールの精度 (信頼度) を一致させる高度な設定を参照して表示されます。</span><span class="sxs-lookup"><span data-stu-id="a401f-340">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="a401f-341">セクションにすばやく移動する、するには、そのセクションの下に移動するルール エディターの上部のナビゲーション内のアイテムをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a401f-341">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP ルール エディターの上部のナビゲーション メニュー](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="a401f-343">DLP ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="a401f-343">DLP policy templates</span></span>

<span data-ttu-id="a401f-p146">DLP ポリシーを作成する最初の手順は、保護するためにどのような情報を選択することです。DLP テンプレートから始めて、最初からルールの新しいセットを作成し、既定でどの種類の情報を含める必要があることを理解することの作業時間を節約できます。追加し、または、組織の特定の要件を満たすためにルールを微調整するのにはこれらの要件を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p146">The first step in creating a DLP policy is choosing what information to protect. By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default. You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="a401f-p147">構成済みの DLP ポリシー テンプレートは、データの HIPAA、PCI DSS データ、グラム リーチ ブライリー法データ、またはロケール固有であっても個人を特定できる情報 (P.I.) などの機密情報の特定の種類を検出するのに役立ちます。簡単に検索し、一般的な種類の機密情報を保護するためにを Office 365 で既に含まれているポリシー テンプレートには、開始するために必要な最も一般的な機密情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a401f-p147">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.). To make it easy for you to find and protect common types of sensitive information, the policy templates included in Office 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![米国愛国者法のテンプレートにフォーカスがあるデータ損失防止ポリシーのテンプレートの一覧](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="a401f-p148">組織は、独自の固有の要件にもあります、場合を作成できます DLP ポリシー最初から**カスタム ポリシー**オプションを選択します。カスタム ポリシーでは、空し、既製のルールが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="a401f-p148">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option. A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="a401f-352">DLP ポリシーをテスト モードで段階的にロールアウトする</span><span class="sxs-lookup"><span data-stu-id="a401f-352">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="a401f-p149">DLP ポリシーを作成するときは、徐々 に展開の影響を評価し、これらの有効性を完全に使用を強制する前にテストを検討してください。たとえば、誤って何千もの人が作業を完了するためにへのアクセスを必要とするドキュメントへのアクセスをブロックする新しい DLP ポリシーたくないです。</span><span class="sxs-lookup"><span data-stu-id="a401f-p149">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="a401f-355">かどうかは、大規模な潜在的な影響を持つ DLP ポリシーを作成する、お勧めしますこの順序に従います。</span><span class="sxs-lookup"><span data-stu-id="a401f-355">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="a401f-p150">**ポリシーのヒントなしでテスト モードで開始**し、使用して、DLP を報告し、インシデントの影響を評価するレポートします。数、場所、種類、およびポリシーの一致の重大度レベルを表示するのには、DLP のレポートを使用できます。結果に基づいて、微調整できます規則に応じて。テスト モードでは、DLP ポリシーでは、組織内で作業しているユーザーの生産性は影響ありません。</span><span class="sxs-lookup"><span data-stu-id="a401f-p150">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="a401f-p151">**通知とポリシーのヒントをテスト モードに移行**するため、コンプライアンス ・ ポリシーについてユーザーを教育し、適用するルール用に準備を開始することができます。この段階では、ユーザーがルールをさらに絞り込むことができますように偽陽性の報告も要求できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p151">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="a401f-p152">**ポリシーに完全に保護の開始**ルール内のアクションが適用され、コンテンツの保護されているようにします。DLP のレポートおよびインシデント レポートや、結果が意図したものかどうかを確認する通知の監視を続けます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p152">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
![テスト モードを使用しポリシーで有効化するオプション](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
<span data-ttu-id="a401f-p153">DLP ポリシーを無効にするにはいつでもでは、ポリシー内のすべての規則に影響を与えます。ただし、各ルールもオフにできます個別に規則エディターでは、その状態を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p153">You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>
  
![ポリシー内のルールを無効にするオプション](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)
  
## <a name="dlp-reports"></a><span data-ttu-id="a401f-368">DLP レポート</span><span class="sxs-lookup"><span data-stu-id="a401f-368">DLP reports</span></span>

<span data-ttu-id="a401f-p154">作成して、DLP ポリシーを有効にした後ことを意図したとおりに動作して、準拠を維持することを確認します。DLP レポートでは、DLP ポリシーの数をすばやく表示することができます、ルールと、偽陽性の数と一致して、オーバーライドします。各レポートでは、場所、時間帯でこれらの文字列にフィルターを適用しても特定のポリシー、ルール、またはアクションを絞り込むため。</span><span class="sxs-lookup"><span data-stu-id="a401f-p154">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant. With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides. For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="a401f-372">DLP レポートによって、ビジネス上の洞察を得ることができ、同時に以下のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="a401f-372">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="a401f-373">特定の期間に絞り込み、スパイクや傾向の理由を理解します。</span><span class="sxs-lookup"><span data-stu-id="a401f-373">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="a401f-374">組織のコンプライアンス ・ ポリシーに違反するビジネス ・ プロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="a401f-374">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="a401f-375">DLP ポリシーのビジネスに及ぼす影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="a401f-375">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="a401f-376">さらに、DLP レポートを使用すると、DLP ポリシーの実行時にそれらのポリシーを調整できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-376">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![セキュリティとコンプライアンスのセンターでのレポートのダッシュ ボード](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="a401f-378">DLP ポリシーのしくみ</span><span class="sxs-lookup"><span data-stu-id="a401f-378">How DLP policies work</span></span>

<span data-ttu-id="a401f-p155">DLP は、(単純なテキスト スキャンだけでなく) 詳細なコンテンツ分析を使用して、機密情報を検出します。この詳細なコンテンツ分析は、キーワード一致、辞書一致、正規表現の評価、内部関数などの方式を使用して、DLP ポリシーに一致するコンテンツを検出します。使用しているデータのうち、ごくわずかな割合のデータのみが機密性が高いと見なされる可能性があります。DLP ポリシーは、他のコンテンツを使用した作業を妨害したり影響を与えたりすることなく、対象データのみを識別、監視し、自動的に保護できます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p155">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="a401f-383">ポリシーの同期</span><span class="sxs-lookup"><span data-stu-id="a401f-383">Policies are synced</span></span>

<span data-ttu-id="a401f-384">セキュリティで DLP ポリシーを作成した後&amp;コンプライアンス ・ センターを持ち、一元管理されたポリシー ストアに格納されているなど、さまざまなコンテンツ ソースにし、同期します。</span><span class="sxs-lookup"><span data-stu-id="a401f-384">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="a401f-385">オンラインでしから、web 上の Outlook および Outlook 2013 とそれ以降</span><span class="sxs-lookup"><span data-stu-id="a401f-385">Exchange Online, and from there to Outlook on the web and Outlook 2013 and later</span></span>
    
- <span data-ttu-id="a401f-386">OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="a401f-386">OneDrive for Business sites</span></span>
    
- <span data-ttu-id="a401f-387">SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="a401f-387">SharePoint Online sites</span></span>
    
- <span data-ttu-id="a401f-388">Office 2016 デスクトップ プログラム (Excel 2016、PowerPoint 2016、Word 2016)</span><span class="sxs-lookup"><span data-stu-id="a401f-388">Office 2016 desktop programs (Excel 2016, PowerPoint 2016, and Word 2016)</span></span>
    
<span data-ttu-id="a401f-389">ポリシーは、適切な場所に同期のコンテンツを評価し、アクションを適用するが起動します。</span><span class="sxs-lookup"><span data-stu-id="a401f-389">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="a401f-390">OneDrive for Business サイトと SharePoint Online サイトのポリシー評価</span><span class="sxs-lookup"><span data-stu-id="a401f-390">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="a401f-p156">SharePoint Online サイトやビジネス サイトの OneDrive のすべてに、ドキュメントが常に変化、継続的にして作成する、編集、共有、およびためにします。つまり、ドキュメントの競合または DLP ポリシーに準拠して任意の時点になることができます。などの人が自分のチーム サイトに機密情報が含まれていないドキュメントをアップロードできますが、ほかの人がその後、同じドキュメントを編集し、機密情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p156">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on. This means documents can conflict or become compliant with a DLP policy at any time. For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="a401f-p157">このため、DLP ポリシーは、バックグラウンドでポリシーに一致しているかどうか頻繁にドキュメントを確認します。これを、非同期のポリシー評価と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p157">For this reason, DLP policies check documents for policy matches frequently in the background. You can think of this as asynchronous policy evaluation.</span></span>
  
<span data-ttu-id="a401f-p158">ここでは、そのしくみです。ユーザーを追加または、サイト内のドキュメントを変更すると、検索エンジンは、それを後で検索することができるように、コンテンツをスキャンします。これが発生すると、コンテンツは、機密性の高い情報とで共有されるかどうかを確認するにもスキャンされます。コンプライアンス チームのみが、それがない標準的なユーザーにアクセスできるように安全には、存在するすべての機密情報を格納し、検索インデックスには。各 DLP ポリシーを有効にするバック グラウンドで (非同期的に実行)、ポリシーに一致する任意のコンテンツを頻繁に検索をチェックし、偶発的なリークから保護するためにアクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p158">Here's how it works. As people add or change documents in their sites, the search engine scans the content, so that you can search for it later. While this is happening, the content's also scanned for sensitive information and to check if it's shared. Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users. Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![DLP ポリシーが非同期的にコンテンツを評価するかを示す図](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<span data-ttu-id="a401f-p159">最後に、ドキュメントが DLP ポリシーに矛盾し、その後 DLP ポリシーに準拠するようになることがあります。たとえば、ユーザーがドキュメントにクレジット カード番号を追加する場合、DLP ポリシーによってドキュメントへのアクセスが自動的にブロックされる可能性があります。しかしユーザーが後で機密情報を削除すると、次にドキュメントが対象ポリシーに対して再び評価されるときに、アクション (この例ではブロック) が自動的に取り消されます。</span><span class="sxs-lookup"><span data-stu-id="a401f-p159">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="a401f-p160">DLP では、インデックスを作成できる任意のコンテンツを評価します。どのような種類のファイルは、既定でクロールの詳細については、[既定のファイル名拡張子をクロールし SharePoint Server 2013 でのファイルの種類を解析](https://go.microsoft.com/fwlink/p/?LinkID=627430)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a401f-p160">DLP evaluates any content that can be indexed. For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkID=627430).</span></span>
  
### <a name="policy-evaluation-in-exchange-online-outlook-2013-and-later-and-outlook-on-the-web"></a><span data-ttu-id="a401f-407">オンライン Exchange、Outlook 2013 以降で、および web 上の Outlook でのポリシーの評価</span><span class="sxs-lookup"><span data-stu-id="a401f-407">Policy evaluation in Exchange Online, Outlook 2013 and later, and Outlook on the web</span></span>

<span data-ttu-id="a401f-408">Office 365 のセキュリティ ポリシーが同期の場所として Exchange Online は、DLP ポリシーを作成するときに&amp;オンラインの Exchange との間、Exchange Online を web 上で Outlook と Outlook 2013 以降でのコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="a401f-408">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook 2013 and later.</span></span>
  
<span data-ttu-id="a401f-p161">メッセージは、Outlook で構成されている、ユーザーは作成されているコンテンツは、DLP ポリシーに対して評価されると、このポリシーのヒントを確認できます。メール フローは、トランスポート ルールを Exchange および Exchange 管理センターで作成した DLP ポリシーの通常の一部として DLP ポリシーに対して評価、メッセージが送信されると (詳細については、次のセクションを参照してください)。DLP ポリシーは、メッセージと添付ファイルの両方をスキャンします。</span><span class="sxs-lookup"><span data-stu-id="a401f-p161">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies. And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange transport rules and DLP policies created in the Exchange Admin Center (see the next section for more info). DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-2016-desktop-programs"></a><span data-ttu-id="a401f-412">Office 2016 デスクトップ プログラムにおけるポリシー評価</span><span class="sxs-lookup"><span data-stu-id="a401f-412">Policy evaluation in the Office 2016 desktop programs</span></span>

<span data-ttu-id="a401f-p162">Excel 2016、2016 の PowerPoint、および Word 2016 には、機密情報を識別し、SharePoint Online およびビジネスのための OneDrive として DLP ポリシーを適用する同じ機能が含まれます。2016 の Office プログラムは、一元管理されたポリシー ストアから直接 DLP ポリシーを同期し、DLP ポリシーに含まれるサイトから開かれているドキュメントで作業するときに、継続的に DLP ポリシーに対してコンテンツを評価し、します。</span><span class="sxs-lookup"><span data-stu-id="a401f-p162">Excel 2016, PowerPoint 2016, and Word 2016 include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business. These Office 2016 programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="a401f-p163">Office 2016 の DLP ポリシーの評価は、プログラムのパフォーマンスやコンテンツを使用するユーザーの生産性に影響しないように設計されています。大きな文書で作業している、またはユーザーのコンピューターがビジー状態、ポリシーに関するヒントが表示される、いくつか秒かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a401f-p163">DLP policy evaluation in Office 2016 is designed not to affect the performance of the programs or the productivity of people working on content. If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>
  
## <a name="permissions"></a><span data-ttu-id="a401f-417">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a401f-417">Permissions</span></span>

<span data-ttu-id="a401f-p164">DLP ポリシーの作成は、コンプライアンス ・ チームのメンバーには、セキュリティを保護するアクセス許可が必要があります&amp;コンプライアンス センターです。既定では、テナント管理者は、この場所にアクセスし、セキュリティを保護するコンプライアンス担当役員およびその他の人のアクセス権を与えることができます&amp;すべてのテナント管理者のアクセス許可を付与せず、コンプライアンス センターこれを行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a401f-p164">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="a401f-420">Office 365 でグループを作成し、コンプライアンス担当者をそのグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="a401f-420">Create a group in Office 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="a401f-421">セキュリティの**アクセス許可**] ページで役割グループの作成&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="a401f-421">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 
    
3. <span data-ttu-id="a401f-422">Office 365 グループをその役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="a401f-422">Add the Office 365 group to the role group.</span></span>
    
<span data-ttu-id="a401f-423">詳細については、「[Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a401f-423">For more information, see [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="a401f-p165">DLP ポリシーを作成して適用するときにのみ、これらのアクセス許可が必要になります。ポリシーを適用する場合に、コンテンツへのアクセスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a401f-p165">These permissions are required only to create and apply a DLP policy. Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="a401f-426">DLP コマンドレットを検索します。</span><span class="sxs-lookup"><span data-stu-id="a401f-426">Find the DLP cmdlets</span></span>

<span data-ttu-id="a401f-427">セキュリティのほとんどのコマンドレットを使用する&amp;コンプライアンス センターでは、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a401f-427">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="a401f-428">リモート PowerShell を使用して Office 365 セキュリティ/コンプライアンス センターに接続する</span><span class="sxs-lookup"><span data-stu-id="a401f-428">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="a401f-429">次のいずれかを使用して、 [Office 365 のセキュリティ&amp;コマンドレットのコンプライアンス センター](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="a401f-429">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="a401f-p166">ただし、DLP のレポートでは、Exchange Online を含め、Office 365 の間でからデータをプルする必要があります。DLP レポートの場合、コマンドレットは、セキュリティではなく--Exchange オンライン Powershell で使用可能なため、&amp;コンプライアンス センター Powershell。したがって、コマンドレットを使用して、DLP のレポートをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a401f-p166">However, DLP reports need pull data from across Office 365, including Exchange Online. For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell. Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="a401f-433">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="a401f-433">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="a401f-434">DLP のレポートには、これらのコマンドレットのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="a401f-434">Use any of these cmdlets for the DLP reports:</span></span>
    
  - [<span data-ttu-id="a401f-435">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="a401f-435">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
  - [<span data-ttu-id="a401f-436">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="a401f-436">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    
## <a name="more-information"></a><span data-ttu-id="a401f-437">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a401f-437">More information</span></span>

- [<span data-ttu-id="a401f-438">テンプレートから DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a401f-438">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="a401f-439">DLP ポリシーに関する通知を送信してポリシー ヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="a401f-439">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="a401f-440">FCI または他のプロパティが使用されているドキュメントを保護する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a401f-440">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="a401f-441">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="a401f-441">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="a401f-442">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="a401f-442">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="a401f-443">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="a401f-443">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="a401f-444">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="a401f-444">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    

