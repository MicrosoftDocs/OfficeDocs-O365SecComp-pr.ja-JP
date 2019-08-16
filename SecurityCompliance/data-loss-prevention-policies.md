---
title: データ損失防止の概要
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/12/2019
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: セキュリティ &amp; コンプライアンス センターのデータ損失防止 (DLP) ポリシーでは、Office 365 全体の機密情報を識別、監視、または自動的に保護できます。
ms.openlocfilehash: 9209adfa913b753ccbb665959cd165d3f2362d0a
ms.sourcegitcommit: 19939bc577937ff5e423500e9bedc0c29f729e20
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "36393917"
---
# <a name="overview-of-data-loss-prevention"></a><span data-ttu-id="19d36-103">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="19d36-103">Overview of data loss prevention policies</span></span>

> [!NOTE]
> <span data-ttu-id="19d36-104">最近、Office 365 Advanced Compliance のライセンスを取得しているユーザー向けに、データ損失防止機能が Microsoft Teams のチャットとチャネルのメッセージに追加されました。これはスタンドアロンのオプションとして提供されており、Office 365 E5 および Microsoft 365 E5 コンプライアンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="19d36-104">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="19d36-105">ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d36-105">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

<span data-ttu-id="19d36-106">ビジネスの標準や業界の規制に準拠するために、組織は機密情報を保護し、不注意による情報漏えいを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-106">To comply with business standards and industry regulations, organizations need to protect sensitive information and prevent its inadvertent disclosure.</span></span> <span data-ttu-id="19d36-107">機密情報には、財務データや個人情報 (PII) (クレジット カード番号、社会保障番号、健康記録など) があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-107">Examples of sensitive information that you might want to prevent from leaking outside your organization include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records.</span></span> <span data-ttu-id="19d36-108">Office 365 セキュリティ &amp; コンプライアンス センターのデータ損失防止 (DLP) ポリシーでは、Office 365 全体の機密情報を識別、監視、または自動的に保護できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-108">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span>
  
<span data-ttu-id="19d36-109">DLP ポリシーでは次のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="19d36-109">With a DLP policy, you can:</span></span>
  
- <span data-ttu-id="19d36-110">**Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teams などの複数の保管場所での機密情報の識別。**</span><span class="sxs-lookup"><span data-stu-id="19d36-110">**Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**</span></span>
    
    <span data-ttu-id="19d36-111">たとえば、OneDrive for Business サイトに保存されているクレジット カード番号を含む文書を特定したり、特定のユーザーの OneDrive サイトだけを監視したりできます。</span><span class="sxs-lookup"><span data-stu-id="19d36-111">For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.</span></span>
    
- <span data-ttu-id="19d36-112">**機密情報が誤って共有されるのを保護。**</span><span class="sxs-lookup"><span data-stu-id="19d36-112">**Prevent the accidental sharing of sensitive information**.</span></span> 
    
    <span data-ttu-id="19d36-113">たとえば、組織外のユーザーと共有されている健康記録を含むドキュメントやメールを識別し、そのドキュメントへのアクセスやメールが送信されるのを自動的にブロックできます。</span><span class="sxs-lookup"><span data-stu-id="19d36-113">For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.</span></span>
    
- <span data-ttu-id="19d36-114">**デスクトップ バージョンの Excel、PowerPoint、Word 内の機密情報の監視と保護。**</span><span class="sxs-lookup"><span data-stu-id="19d36-114">**Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**</span></span>
    
    <span data-ttu-id="19d36-115">Exchange Online、SharePoint Online、OneDrive for Business 同様、これらの Office デスクトップ プログラムにも機密情報を識別し、DLP ポリシーを適用する同じ機能が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="19d36-115">Just like in SharePoint Online and OneDrive for Business, these Office 2016 desktop programs include the same capabilities to identify sensitive information and apply DLP policies.</span></span> <span data-ttu-id="19d36-116">他のユーザーとこうした Office プログラムのコンテンツを共有すると、DLP によって継続的な監視が行われます。</span><span class="sxs-lookup"><span data-stu-id="19d36-116">DLP provides continuous monitoring when people share content in these Office 2016 programs.</span></span>
    
- <span data-ttu-id="19d36-117">**ワークフローを中断することなく準拠を維持する方法についてのユーザーに対する説明。**</span><span class="sxs-lookup"><span data-stu-id="19d36-117">**Help users learn how to stay compliant without interrupting their workflow.**</span></span>
    
    <span data-ttu-id="19d36-118">DLP ポリシーについてユーザーを教育し、作業を妨げることなく準拠を維持できるようにします。</span><span class="sxs-lookup"><span data-stu-id="19d36-118">You can educate your users about DLP policies and help them to remain compliant without blocking their work.</span></span> <span data-ttu-id="19d36-119">たとえば、ユーザーが機密情報を含むドキュメントを共有しようとした場合、DLP ポリシーは、メール通知をユーザーに送信すると共に、業務上の妥当性がある場合にはポリシーを無効にできるドキュメント ライブラリのコンテキストでポリシー ヒントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-119">You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Excel 2016, PowerPoint 2016, and Word 2016.
</span></span> <span data-ttu-id="19d36-120">Outlook on the web、Outlook、Excel、PowerPoint、Word でも同じポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-120">The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.</span></span>
    
- <span data-ttu-id="19d36-121">**組織の DLP ポリシーと一致するコンテンツを示す DLP レポートの表示。**</span><span class="sxs-lookup"><span data-stu-id="19d36-121">**View DLP reports showing content that matches your organization's DLP policies.**</span></span>
    
    <span data-ttu-id="19d36-122">DLP ポリシーへの組織の準拠状態を評価するには、各ポリシーやルールへの一致数の時間経過による変化を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-122">To assess how your organization is complying with a DLP policy, you can see how many matches each policy and rule has over time.</span></span> <span data-ttu-id="19d36-123">DLP ポリシーでポリシー ヒントの上書きおよび誤検知の報告がユーザーに許可されている場合は、ユーザーが報告した内容を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="19d36-123">If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported.</span></span>
    
<span data-ttu-id="19d36-124">Office 365 セキュリティ &amp; コンプライアンス センターの [データ損失防止] ページで、 DLP ポリシーを作成して管理します。</span><span class="sxs-lookup"><span data-stu-id="19d36-124">You create and manage DLP policies on the Data loss prevention page in the Office 365 Compliance Center.</span></span>
  
![Office 365 セキュリティ &amp; コンプライアンス センターの [データ損失防止] ページ](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a><span data-ttu-id="19d36-126">DLP ポリシーの内容</span><span class="sxs-lookup"><span data-stu-id="19d36-126">What a DLP policy contains</span></span>

<span data-ttu-id="19d36-127">DLP ポリシーにはいくつかの基本的な内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="19d36-127">A DLP policy contains a few basic things:</span></span>
  
- <span data-ttu-id="19d36-128">コンテンツを保護する場所: Exchange Online、SharePoint Online、OneDrive for Business のサイトの他、Microsoft Teams のチャットおよびチャネル メッセージなどの**保管場所**。</span><span class="sxs-lookup"><span data-stu-id="19d36-128">Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages.</span></span> 
    
- <span data-ttu-id="19d36-129">**ルール**を適用することによってコンテンツを保護する場合と方法は、次のもので構成されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-129">When and how to protect the content by enforcing **rules** comprised of:</span></span> 
    
  - <span data-ttu-id="19d36-130">ルールを適用する前にコンテンツが一致する必要がある**条件**。</span><span class="sxs-lookup"><span data-stu-id="19d36-130">**Conditions** the content must match before the rule is enforced.</span></span> <span data-ttu-id="19d36-131">たとえば、ルールは組織外のユーザーと共有されている社会保障番号を含むコンテンツのみを探すよう構成されていることがあります。</span><span class="sxs-lookup"><span data-stu-id="19d36-131">For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization.</span></span> 
    
  - <span data-ttu-id="19d36-132">条件に一致するコンテンツが見つかったときにルールが自動的に実行する**アクション**。</span><span class="sxs-lookup"><span data-stu-id="19d36-132">**Actions** that you want the rule to take automatically when content matching the conditions is found -- for example, block access to the document and send both the user and compliance officer an email notification.</span></span> <span data-ttu-id="19d36-133">たとえば、ドキュメントへのアクセスをブロックし、ユーザーおよびコンプライアンス責任者の双方にメール通知を送信するようにルールが構成されていることがあります。</span><span class="sxs-lookup"><span data-stu-id="19d36-133">For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification.</span></span> 
    
<span data-ttu-id="19d36-134">ルールを使用して特定の保護要件を満たし、DLP ポリシーを使用して一般的な保護要件をグループ化できます (たとえば、特定の規制に準拠する必要のあるすべてのルール)。</span><span class="sxs-lookup"><span data-stu-id="19d36-134">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="19d36-135">たとえば、Health Insurance Portability and Accountability Act (HIPAA) の対象となる情報の存在を検出する際に役立つ DLP ポリシーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="19d36-135">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="19d36-136">この DLP ポリシーは、HIPAA データ (対象) をすべての SharePoint Online サイトと OneDrive for Business サイト (場所) で保護するために、組織外の人物と共有するこの機密情報が含まれるドキュメント (条件) を検出し、そのドキュメントに対するアクセスをブロックして通知を送信 (アクション) できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-136">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that’s shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="19d36-137">これらの要件は、個別のルールとして保存され、簡単に管理およびレポートする DLP ポリシーとしてまとめてグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-137">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![図は、DLP ポリシーに場所とルールが含まれていることを示しています。](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a><span data-ttu-id="19d36-139">場所</span><span class="sxs-lookup"><span data-stu-id="19d36-139">Locations</span></span>

<span data-ttu-id="19d36-140">DLP ポリシーは、Office 365 全体で機密情報を検出して保護できます。情報が Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teams のいずれかに保存されていてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="19d36-140">A DLP policy can find and protect sensitive information across Office 365, whether that information is located in Exchange Online, SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="19d36-141">Exchange メール、Microsoft Teams のチャットとチャネル メッセージ、およびすべての SharePoint または OneDrive ライブラリ内のコンテンツを保護するか、ポリシーの特定の場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-141">You can choose to protect content in Exchange email, Microsoft Teams chats and channel messages, and all SharePoint or OneDrive libraries, or select specific locations for a policy.</span></span>
  
![DLP ポリシーを適用できる場所のオプション](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
<span data-ttu-id="19d36-143">特定の SharePoint サイトまたは OneDrive アカウントを含めるか、除外するかを選択した場合、DLP ポリシーに含めることができるのは、100 を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="19d36-143">If you choose to include or exclude specific SharePoint sites or OneDrive accounts, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="19d36-144">こうした制限はありますが、組織全体のポリシーまたは場所全体に適用されるポリシーを適用することで、この制限を超えることができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-144">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="rules"></a><span data-ttu-id="19d36-145">ルール</span><span class="sxs-lookup"><span data-stu-id="19d36-145">Rules</span></span>

<span data-ttu-id="19d36-146">ルールとは、組織のコンテンツにビジネス要件を適用するものです。</span><span class="sxs-lookup"><span data-stu-id="19d36-146">Rules are what enforce your business requirements on the information stored by your organization.</span></span> <span data-ttu-id="19d36-147">ポリシーには 1 つ以上のルールが含まれ、各ルールには、条件とアクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="19d36-147">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="19d36-148">ルールごとに、条件を満たすとアクションが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-148">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="19d36-149">ルールは、各ポリシー内の最も高位のルールから順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-149">Rules are executed sequentially, starting with the lowest order rule in each policy.</span></span>
  
<span data-ttu-id="19d36-150">また、ルールには、コンテンツがルールに一致していることを (ポリシー ヒントとメール通知を持つ) ユーザーと (メール インシデント レポートを持つ) 管理者に通知するオプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="19d36-150">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="19d36-151">ここでは、ルールの構成要素をそれぞれ詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="19d36-151">Here are the components of a rule, each explained below.</span></span>
  
![DLP ルール エディターのセクション](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="19d36-153">条件</span><span class="sxs-lookup"><span data-stu-id="19d36-153">Conditions</span></span>

<span data-ttu-id="19d36-154">条件は、探す情報の種類および操作をいつ実行するかを決定するため重要です。</span><span class="sxs-lookup"><span data-stu-id="19d36-154">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="19d36-155">たとえば、パスポート番号を含むコンテンツは、コンテンツに含まれる番号が 10 個より多く組織外のユーザーと共有されている場合以外は無視する、といった条件を作成できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-155">Conditions are important because they determine what types of information you’re looking for, and when to take an action. For example, you might choose to ignore documents containing passport numbers unless the document contains more than ten such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="19d36-156">条件は、探す機密情報の種類などの**コンテンツ**と、ドキュメントが共有されているユーザーなどの**コンテキスト**に注目します。</span><span class="sxs-lookup"><span data-stu-id="19d36-156">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="19d36-157">条件を使用して、さまざまな操作をリスクレベル別に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-157">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="19d36-158">たとえば、組織内で共有されている機密コンテンツは、組織外のユーザーと共有されている機密コンテンツよりリスク レベルが低く、必要なアクションを少なくする、といったことができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-158">For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![利用可能な DLP 条件の一覧](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="19d36-160">現在使用可能な条件では、以下のことを判定できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-160">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="19d36-161">コンテンツに機密情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="19d36-161">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="19d36-162">コンテンツにラベルが含まれている。</span><span class="sxs-lookup"><span data-stu-id="19d36-162">Content contains a label.</span></span> <span data-ttu-id="19d36-163">詳細については、以下の「[DLP ポリシーでラベルを条件として使用する](#using-a-label-as-a-condition-in-a-dlp-policy)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d36-163">For more information, see [Using a label as a condition in a DLP policy](#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="19d36-164">コンテンツが組織の内または外のユーザーと共有されている。</span><span class="sxs-lookup"><span data-stu-id="19d36-164">Content is shared with people outside or inside your organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="19d36-165">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="19d36-165">Types of sensitive information</span></span>

<span data-ttu-id="19d36-166">DLP ポリシーは、**機密情報の種類**として定義されている機密情報を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="19d36-166">A DLP policy can help  protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="19d36-167">Office 365 には、クレジット カード番号、銀行口座番号、国内 ID 番号、パスポート番号など、さまざまな分野の一般的な機密情報の種類の定義が数多く含まれていて、すぐに使用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-167">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![使用できる機密情報の種類の一覧](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="19d36-169">DLP ポリシーによってクレジット カード番号などの機密情報の種類を検索する場合、単に 16 桁の数字を検索するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="19d36-169">When a DLP policy looks for a sensitive information type such as a credit card number, it does not simply look for a 16-digit number.</span></span> <span data-ttu-id="19d36-170">機密情報のそれぞれの種類が定義され、以下の組み合わせを使用して検出されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-170">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="19d36-171">キーワード</span><span class="sxs-lookup"><span data-stu-id="19d36-171">Keywords</span></span>
    
- <span data-ttu-id="19d36-172">チェックサムや構成を検証するための内部関数</span><span class="sxs-lookup"><span data-stu-id="19d36-172">Internal functions to validate checksums or composition</span></span>
    
- <span data-ttu-id="19d36-173">パターンの一致を検出するための正規表現の評価</span><span class="sxs-lookup"><span data-stu-id="19d36-173">Evaluation of regular expressions to find pattern matches</span></span>
    
- <span data-ttu-id="19d36-174">その他のコンテンツの検査</span><span class="sxs-lookup"><span data-stu-id="19d36-174">Other content examination</span></span>
    
<span data-ttu-id="19d36-175">これにより、DLP 検出処理において、作業の中断原因となる誤検知の数を減らし、正確性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-175">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples’ work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="19d36-176">操作</span><span class="sxs-lookup"><span data-stu-id="19d36-176">Actions</span></span>

<span data-ttu-id="19d36-177">コンテンツがルールの条件と一致したら、操作を適用してコンテンツを自動的に保護できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-177">When content matches a condition in a rule, you can apply actions to automatically protect the document or content.</span></span>
  
![使用できる DLP 操作の一覧](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="19d36-179">現在は次のような操作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-179">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="19d36-180">**コンテンツへのアクセスを制限する** サイトのコンテンツの場合、これは、プライマリ サイト コレクション管理者、ドキュメントの所有者、ドキュメントを最後に変更したユーザーを除くすべてのユーザーについて、ドキュメントへのアクセス許可が制限されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="19d36-180">**Restrict access to the content** For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="19d36-181">これらのユーザーは、ドキュメントの機密情報の削除や、他の修正操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-181">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="19d36-182">ドキュメントがコンプライアンスを遵守した状態になった場合、元のアクセス許可が自動的に復元されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-182">When the document is in compliance, the original permissions will be automatically restored.</span></span> <span data-ttu-id="19d36-183">ドキュメントへのアクセスがブロックされているときは、サイトのライブラリでドキュメントに特別なポリシー ヒントのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-183">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
    ![ドキュメントへのアクセスがブロックされていることを示すポリシー ヒント](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    <span data-ttu-id="19d36-185">メール コンテンツの場合は、この操作によりメッセージの送信がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="19d36-185">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="19d36-186">DLP ルールの構成方法によっては、NDR または (ルールで通知が使用されている場合) ポリシー ヒントやメール通知が送信者に表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-186">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
    ![メッセージから権限のない受信者を削除する必要があることを示す警告](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="19d36-188">ユーザー通知とユーザーによる上書き</span><span class="sxs-lookup"><span data-stu-id="19d36-188">User notifications and user overrides</span></span>

<span data-ttu-id="19d36-189">通知と上書きを使用して、DLP ポリシーについてユーザーを教育し、作業を妨げることなく準拠を維持できるようにします。</span><span class="sxs-lookup"><span data-stu-id="19d36-189">You can educate your users about DLP policies and help them to remain compliant without blocking their work.</span></span> <span data-ttu-id="19d36-190">たとえば、ユーザーが機密情報を含むドキュメントを共有しようとした場合、DLP ポリシーは、メール通知をユーザーに送信すると共に、業務上の妥当性がある場合にはポリシーを無効にできるドキュメント ライブラリのコンテキストでポリシー ヒントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-190">You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Excel 2016, PowerPoint 2016, and Word 2016.
</span></span>
  
![DLP ルール エディターのユーザー通知とユーザーによる上書きのセクション](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="19d36-192">コンテンツを送信したユーザー、コンテンツを共有しているユーザー、または最後にコンテンツを変更したユーザーにメールで通知でき、サイト コンテンツについては、主要なサイト コレクション管理者とドキュメントの所有者に通知できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-192">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="19d36-193">さらに、メール通知から選択したユーザーを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-193">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="19d36-194">メール通知の送信に加えて、ユーザー通知にはポリシー ヒントも表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-194">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="19d36-195">Outlook および Outlook on the web の場合。</span><span class="sxs-lookup"><span data-stu-id="19d36-195">Troubleshooting delegation in Outlook and Outlook on the web</span></span>
    
- <span data-ttu-id="19d36-196">SharePoint Online または OneDrive for Business サイトにあるドキュメントの場合。</span><span class="sxs-lookup"><span data-stu-id="19d36-196">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="19d36-197">DLP ポリシーに含まれるサイトにドキュメントが格納されている場合に、Excel、PowerPoint、Word。</span><span class="sxs-lookup"><span data-stu-id="19d36-197">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="19d36-198">メール通知およびポリシー ヒントでは、コンテンツが DLP ポリシーに違反している理由が説明されています。</span><span class="sxs-lookup"><span data-stu-id="19d36-198">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="19d36-199">洗濯した場合、ユーザーが誤検知を報告するか業務上の妥当性を示すことによってルールを上書きすることを、メール通知およびポリシー ヒントで許可できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-199">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="19d36-200">これは、DLP ポリシーについてユーザーを教育し、ユーザーの仕事を妨げることなく DLP ポリシーを適用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="19d36-200">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="19d36-201">上書きおよび誤検知に関する情報は、レポート用に記録され (後の DLP レポートの詳細を参照)、インシデント レポート (次のセクションを参照) にも含まれるため、コンプライアンス責任者は定期的にこの情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-201">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="19d36-202">OneDrive for Business アカウントにおけるポリシー ヒントの表示内容を示します。</span><span class="sxs-lookup"><span data-stu-id="19d36-202">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![OneDrive アカウントでのドキュメントのポリシー ヒント](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a><span data-ttu-id="19d36-204">インシデント レポート</span><span class="sxs-lookup"><span data-stu-id="19d36-204">Incident reports</span></span>

<span data-ttu-id="19d36-205">ルールが一致する場合は、イベントの詳細を含むインシデント レポートをコンプライアンス担当者 (または選択したユーザー) に送信できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-205">When a rule is matched, you can send an incident report to your compliance officer with details of the event.</span></span> <span data-ttu-id="19d36-206">このレポートには、一致したアイテム、ルールに一致した実際のコンテンツ、コンテンツの最終変更者の名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="19d36-206">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="19d36-207">メール メッセージの場合、レポートには添付ファイルとして、DLP ポリシーに適合する元のメッセージも含まれます。</span><span class="sxs-lookup"><span data-stu-id="19d36-207">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>
  
![インシデント レポートを構成するためのページ](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="19d36-209">グループ化と論理演算子</span><span class="sxs-lookup"><span data-stu-id="19d36-209">Grouping and logical operators</span></span>

<span data-ttu-id="19d36-210">多くの場合、DLP ポリシーには、米国の社会保障番号が含まれているすべてのコンテンツを特定することなど、単純な要件が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19d36-210">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="19d36-211">ただし、DLP ポリシーによって、より大まかに定義されたデータを特定する必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-211">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="19d36-212">たとえば、米国の健康保険法 (HIPAA) の適用対象のコンテンツを特定するには、次を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-212">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="19d36-213">特定の種類の機密情報 (社会保障番号や麻薬取締局 (DEA) 番号など) を含んでいるコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="19d36-213">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="19d36-214">AND</span><span class="sxs-lookup"><span data-stu-id="19d36-214">AND</span></span>
    
- <span data-ttu-id="19d36-215">特定がより難しいコンテンツ (患者の治療に関する通信記録や提供された医療サービスの説明など)。</span><span class="sxs-lookup"><span data-stu-id="19d36-215">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="19d36-216">コンテンツを特定するには、国際疾病分類 (ICD-9-CM または ICD-10-CM) などの膨大なキーワード リストからキーワードを一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-216">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="19d36-217">このような大まかに定義されたデータを簡単に特定するには、グループ化と論理演算子 (AND、OR) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-217">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="19d36-218">DLP ポリシーを作成するときに、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-218">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="19d36-219">機密情報の種類をグループ化する。</span><span class="sxs-lookup"><span data-stu-id="19d36-219">Custom sensitive information types</span></span>
    
- <span data-ttu-id="19d36-220">グループ内の機密情報の種類の間、およびグループ自体の間で使用する論理演算子を選択する。</span><span class="sxs-lookup"><span data-stu-id="19d36-220">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="19d36-221">グループ内の演算子を選択する</span><span class="sxs-lookup"><span data-stu-id="19d36-221">Choosing the operator within a group</span></span>

<span data-ttu-id="19d36-222">グループ内では、コンテンツがルールに一致するためにそのグループが満たす必要のある条件が、そのグループ内のいずれかの条件なのか、すべての条件なのかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-222">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![グループ内の演算子を表示するグループ](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="19d36-224">グループを追加する</span><span class="sxs-lookup"><span data-stu-id="19d36-224">Adding a group as a geo admin</span></span>

<span data-ttu-id="19d36-225">独自の条件とグループ内で演算子を持つことができるグループをすばやく追加できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-225">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![[グループの追加] ボタン](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="19d36-227">グループ間の演算子を選択する</span><span class="sxs-lookup"><span data-stu-id="19d36-227">Choosing the operator between groups</span></span>

<span data-ttu-id="19d36-228">グループ間では、コンテンツがルールに一致するためにそのグループが満たす必要のある条件が、1 つのグループの条件のみなのか、すべてのグループの条件なのかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-228">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="19d36-229">たとえば、**米国 HIPAA** の組み込みポリシーには、次を含むコンテンツを特定するために、グループ間で **AND** 演算子を使用するルールがあります。</span><span class="sxs-lookup"><span data-stu-id="19d36-229">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="19d36-230">**PII 識別子** グループ (少なくとも 1 つの SSN 番号**または** DEA 番号)</span><span class="sxs-lookup"><span data-stu-id="19d36-230">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="19d36-231">**AND**</span><span class="sxs-lookup"><span data-stu-id="19d36-231">**AND**</span></span>
    
- <span data-ttu-id="19d36-232">**医学用語**グループ (少なくとも 1 つの ICD-9-CM キーワード**または** ICD-10-CM キーワード)</span><span class="sxs-lookup"><span data-stu-id="19d36-232">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![グループ間の演算子を表示するグループ](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="19d36-234">処理するルールの優先度</span><span class="sxs-lookup"><span data-stu-id="19d36-234">The priority by which rules are processed</span></span>

<span data-ttu-id="19d36-235">ポリシーでルールを作成すると、作成した順の優先度が各ルールに割り当てられます。つまり、最初に作成したルールの優先度が最も高くなり、2 番目に作成したルールの優先度は 2 番目になります。</span><span class="sxs-lookup"><span data-stu-id="19d36-235">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span> 
  
![優先度順のルール](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
<span data-ttu-id="19d36-237">DLP ポリシーを 1 つ以上設定したら、1 つまたは複数のポリシーの優先順位を変更できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-237">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="19d36-238">変更を行うには、ポリシーを選択し、**[ポリシーの編集]** を選び、**[優先度]** の一覧で優先度を指定します。</span><span class="sxs-lookup"><span data-stu-id="19d36-238">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

![ポリシーの優先度を設定する](media/dlp-set-policy-priority.png)

<span data-ttu-id="19d36-240">コンテンツがルールに対して評価されると、ルールは優先度順に処理されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-240">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="19d36-241">コンテンツが複数のルールに一致する場合、ルールは優先度順に処理され、最も制限が厳しい操作が適用されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-241">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="19d36-242">たとえば、コンテンツが以下のすべてのルールに一致する場合、最も優先度が高く、制限が厳しいルール 3 が適用されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-242">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="19d36-243">ルール 1: ユーザーに通知のみを行う</span><span class="sxs-lookup"><span data-stu-id="19d36-243">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="19d36-244">ルール 2: ユーザーに通知する、アクセスを制限する、ユーザーによる上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="19d36-244">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="19d36-245">ルール 3: ユーザーに通知する、アクセスを制限する、ユーザーによる上書きを許可しない</span><span class="sxs-lookup"><span data-stu-id="19d36-245">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="19d36-246">ルール 4: ユーザーに通知のみを行う</span><span class="sxs-lookup"><span data-stu-id="19d36-246">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="19d36-247">ルール 5: アクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="19d36-247">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="19d36-248">ルール 6: ユーザーに通知する、アクセスを制限する、ユーザーによる上書きを許可しない</span><span class="sxs-lookup"><span data-stu-id="19d36-248">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="19d36-249">この例では、最も制限が厳しいルールのみが適用された場合でも、すべてのルールに一致するものは監査ログに記録され、DLP レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-249">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="19d36-250">ポリシー ヒントについては、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="19d36-250">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="19d36-251">最も優先度が高く、制限が厳しいルールのポリシー ヒントのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-251">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="19d36-252">たとえば、単に通知を送信するルールのポリシー ヒントよりも、コンテンツへのアクセスを禁止するルールのポリシー ヒントの方が優先して表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-252">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="19d36-253">これにより、ポリシー ヒントがカスケード表示されるのを防止します。</span><span class="sxs-lookup"><span data-stu-id="19d36-253">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="19d36-254">	最も制限の厳しいルールでユーザーにルールを上書きすることを許可している場合は、このルールを上書きすることで、コンテンツに一致した他のルールもすべて上書きされます。</span><span class="sxs-lookup"><span data-stu-id="19d36-254">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="19d36-255">一致の難易度を上下するためにルールを調整する</span><span class="sxs-lookup"><span data-stu-id="19d36-255">For more information on these options, see Tuning rules to make them easier or harder to match.</span></span>

<span data-ttu-id="19d36-256">DLP ポリシーを作成して有効にすると、次の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-256">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="19d36-257">機密情報**ではない**大量のコンテンツがルールと一致します。つまり、多数の誤検知が発生します。</span><span class="sxs-lookup"><span data-stu-id="19d36-257">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="19d36-258">機密情報**である**コンテンツが小さすぎると、ルールと一致します。</span><span class="sxs-lookup"><span data-stu-id="19d36-258">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="19d36-259">言い換えると、保護操作は機密情報に対して実行されません。</span><span class="sxs-lookup"><span data-stu-id="19d36-259">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="19d36-260">このような問題に対処するには、インスタンス数と一致精度を変更してコンテンツがルールに一致する難易度を上下させて、ルールを調整します。</span><span class="sxs-lookup"><span data-stu-id="19d36-260">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="19d36-261">ルールに使用される各機密情報の種類には、インスタンス数と一致精度の両方があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-261">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="19d36-262">インスタンス数</span><span class="sxs-lookup"><span data-stu-id="19d36-262">Instance count</span></span>

<span data-ttu-id="19d36-263">インスタンス数とは、コンテンツがルールに一致すると評価される各機密情報の種類の出現回数です。</span><span class="sxs-lookup"><span data-stu-id="19d36-263">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="19d36-264">たとえば、1 から 9 の固有の米国または英国の間のコンテンツは、次のルールに一致します。</span><span class="sxs-lookup"><span data-stu-id="19d36-264">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="19d36-265">パスポート番号が識別されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-265">passport numbers are identified.</span></span>
  
<span data-ttu-id="19d36-266">インスタンス数では、機密情報の種類とキーワードの**一意**の一致のみがカウントされます。</span><span class="sxs-lookup"><span data-stu-id="19d36-266">Note that the instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="19d36-267">たとえば、メールの中に同じクレジット カード番号が 10 回出現する場合、その 10 回の出現は、クレジット カード番号の 1 つのインスタンスとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="19d36-267">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span> 
  
<span data-ttu-id="19d36-268">インスタンス数を使用してルールを調整する方法は簡単です。</span><span class="sxs-lookup"><span data-stu-id="19d36-268">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="19d36-269">ルールに一致させやすくするには、[**最小**] 数を減らし、[**最大**] 数を増やします。</span><span class="sxs-lookup"><span data-stu-id="19d36-269">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="19d36-270">また、[**最大**] の数値を削除して [**すべて**] に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="19d36-270">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="19d36-271">ルールに一致させにくくするには、[**最小**] 数を増やします。</span><span class="sxs-lookup"><span data-stu-id="19d36-271">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="19d36-272">通常、ユーザー通知の送信など、制限の緩い操作は、少ないインスタンス数 (たとえば 1 から 9) のルールで使用します。</span><span class="sxs-lookup"><span data-stu-id="19d36-272">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="19d36-273">また、ユーザーによる上書きを許可せずにコンテンツへのアクセスを制限するなど制限の厳しい操作は、高いインスタンス数 (たとえば 10 からすべて) のルールで使用します。</span><span class="sxs-lookup"><span data-stu-id="19d36-273">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![ルール エディターのインスタンス数](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="19d36-275">一致精度</span><span class="sxs-lookup"><span data-stu-id="19d36-275">Match accuracy</span></span>

<span data-ttu-id="19d36-276">前述のように、機密情報の種類の定義と検出には、さまざまな種類の証拠を組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="19d36-276">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="19d36-277">一般的に、機密情報の種類はそのような複数の組み合わせ (パターンと呼ばれます) で定義されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-277">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="19d36-278">必要な証拠が少ないパターンは一致精度 (信頼度) が低く、必要な証拠が多いパターンは一致精度 (信頼度) が高くなります。</span><span class="sxs-lookup"><span data-stu-id="19d36-278">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="19d36-279">各機密情報の種類に使用される実際のパターンと信頼度の詳細については、「[機密情報の種類で検索される情報](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d36-279">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
<span data-ttu-id="19d36-280">たとえば、クレジット カード番号という機密情報の種類は次の 2 つのパターンで定義されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-280">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="19d36-281">必要な信頼度が 65% のパターン:</span><span class="sxs-lookup"><span data-stu-id="19d36-281">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="19d36-282">クレジット カード番号の形式の番号。</span><span class="sxs-lookup"><span data-stu-id="19d36-282">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="19d36-283">チェックサムに合格する番号。</span><span class="sxs-lookup"><span data-stu-id="19d36-283">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="19d36-284">必要な信頼度が 85% のパターン:</span><span class="sxs-lookup"><span data-stu-id="19d36-284">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="19d36-285">クレジット カード番号の形式の番号。</span><span class="sxs-lookup"><span data-stu-id="19d36-285">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="19d36-286">チェックサムに合格する番号。</span><span class="sxs-lookup"><span data-stu-id="19d36-286">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="19d36-287">適切な形式のキーワードまたは有効期限。</span><span class="sxs-lookup"><span data-stu-id="19d36-287">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="19d36-288">ルールにはこれらの信頼度 (または一致精度) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-288">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="19d36-289">通常、ユーザー通知の送信など、制限の緩いアクションは、低い一致精度のルールで使用します。</span><span class="sxs-lookup"><span data-stu-id="19d36-289">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="19d36-290">また、ユーザーによる上書きを許可せずにコンテンツへのアクセスを制限するなど制限の厳しい操作は、高い一致制度のルールで使用します。</span><span class="sxs-lookup"><span data-stu-id="19d36-290">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="19d36-291">クレジット カード番号など、内容に含まれる各機密情報の種類が識別された場合、1 つの信頼度のみが返されることを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-291">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="19d36-292">すべての一致が 1 つのパターンの場合、そのパターンの信頼度が返されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-292">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="19d36-293">複数のパターンについて一致がある場合 (つまり、2 つの信頼度の一致がある場合)、他のパターンよりも高い信頼度のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-293">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="19d36-294">この点には注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-294">This is the tricky part.</span></span> <span data-ttu-id="19d36-295">たとえばクレジット カードの場合、65% のパターンと 85% のパターンの両方に一致する場合、証拠が多いほど信頼度が高くなるので、その機密情報の種類について返される信頼度は 90% を超えます。</span><span class="sxs-lookup"><span data-stu-id="19d36-295">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="19d36-296">そのため、クレジット カードについて相互排他的な 2 つのルールを作成し、65% の一致精度のルールと 85% の一致精度のルールである場合、一致精度の範囲は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="19d36-296">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="19d36-297">最初のルールでは、65% のパターンの一致のみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-297">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="19d36-298">2 つ目のルールでは、**少なくとも 1 つの** 85% のパターンの一致が選択され、他の低い信頼度の一致が**選択される可能性**があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-298">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![一致精度の範囲が異なる 2 つのルール](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="19d36-300">以上の理由から、一致精度が異なる複数のルールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19d36-300">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="19d36-301">通常、最も低い信頼度では、[**最小**] と [**最大**] に (範囲ではなく) 同じ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="19d36-301">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="19d36-302">通常、最も高い信頼度は、下位の信頼度のすぐ上の値から 100 の範囲です。</span><span class="sxs-lookup"><span data-stu-id="19d36-302">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="19d36-303">通常、範囲の信頼度を設定する場合、下位の信頼度のすぐ上の値から、上位の信頼度のすぐ下の値までの範囲にします。</span><span class="sxs-lookup"><span data-stu-id="19d36-303">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="19d36-304">DLP ポリシーでラベルを条件として使用する</span><span class="sxs-lookup"><span data-stu-id="19d36-304">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="19d36-305">ラベルを作成すると、次のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-305">You can create a label and then:</span></span>
  
- <span data-ttu-id="19d36-306">エンド ユーザーがラベルを確認したりコンテンツに手動で適用したりできるように、ラベルを**発行**します。</span><span class="sxs-lookup"><span data-stu-id="19d36-306">**Publish** it, so that end users can see and manually apply the label to content.</span></span> 
    
- <span data-ttu-id="19d36-307">選択した条件に一致するコンテンツにラベルを**自動適用**します。</span><span class="sxs-lookup"><span data-stu-id="19d36-307">**Auto-apply** it to content that matches the conditions that you choose.</span></span> 
    
<span data-ttu-id="19d36-308">保持ラベルの詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d36-308">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
<span data-ttu-id="19d36-309">ラベルを作成した後は、DLP ポリシーでそのラベルを条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-309">After you create a label, you can then use that label as a condition in your DLP policies.</span></span> <span data-ttu-id="19d36-310">たとえば、次のような場合があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-310">For example, you might want to do this because:</span></span>
  
- <span data-ttu-id="19d36-311">**社外秘**というラベルを発行して、組織内のユーザーが社外秘のメールとドキュメントにラベルを手動で適用できるようにした。</span><span class="sxs-lookup"><span data-stu-id="19d36-311">You published a label named **Confidential**, so that people in your organization can manually apply the label to confidential email and documents.</span></span> <span data-ttu-id="19d36-312">DLP ポリシーでこのラベルを条件として使用して、**社外秘**というラベルが付いたコンテンツを組織外のユーザーと共有できないように制限できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-312">By using this label as a condition in your DLP policy, you can restrict content labeled **Confidential** from being shared with people outside your organization.</span></span> 
    
- <span data-ttu-id="19d36-313">**Alpine House** というラベルをその名前のプロジェクト用に作成して、キーワード "Alpine House" を含むコンテンツにそのラベルを自動的に適用した。</span><span class="sxs-lookup"><span data-stu-id="19d36-313">You created a label named **Alpine House** for a project of that name, and then applied that label automatically to content containing the keywords "Alpine House".</span></span> <span data-ttu-id="19d36-314">DLP ポリシーでこのラベルを条件として使用して、エンド ユーザーが組織外のユーザーとこのコンテンツを共有しようとしたときにポリシーのヒントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-314">By using this label as a condition in your DLP policy, you can show a policy tip to end users when they're about to share this content with someone outside your organization.</span></span> 
    
- <span data-ttu-id="19d36-315">**納税記録**というラベルを発行して、納税記録に分類する必要があるコンテンツに納税記録管理者がそのラベルを手動で適用できるようにした。</span><span class="sxs-lookup"><span data-stu-id="19d36-315">You published a label named **Tax record**, so that your records manager can manually apply the label to content that needs to be classified as a record.</span></span> <span data-ttu-id="19d36-316">DLP ポリシーでこのラベルを条件として使用して、ITIN や SSN といった他の種類の機密性の高い情報と共にこのラベルの付いたコンテンツを検索したり、**納税記録**というラベルが付いたコンテンツに保護アクションを適用したり、DLP レポートと監査ログ データから DLP ポリシーに関する詳細なアクティビティ レポートを取得したりできます。</span><span class="sxs-lookup"><span data-stu-id="19d36-316">By using this label as a condition in your DLP policy, you can look for content with this label along with other types of sensitive information such as ITINs or SSNs; apply protection actions to content labeled **Tax record**; and get detailed activity reports about the DLP policy from the DLP reports and audit log data.</span></span> 
    
- <span data-ttu-id="19d36-317">**役員リーダー - 機密**というラベルを役員グループの Exchange メールボックスと OneDrive アカウントに発行した。</span><span class="sxs-lookup"><span data-stu-id="19d36-317">You published a label named **Executive Leadership Team - Sensitive** to the Exchange mailboxes and OneDrive accounts of a group of executives.</span></span> <span data-ttu-id="19d36-318">DLP ポリシーでこのラベルを条件として使用して、コンテンツとユーザーの同じサブセットに保持操作と保護操作の両方を適用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-318">By using this label as a condition in your DLP policy, you can enforce both retention and protection actions on the same subset of content and users.</span></span> 
    
<span data-ttu-id="19d36-319">DLP ルールでラベルを条件として使用して、特定のコンテンツ、場所、ユーザーに保護操作を適用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-319">By using labels as a condition in your DLP rules, can you selectively enforce protection actions on a specific set of content, locations, or users.</span></span>
  
![条件としてのラベル](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a><span data-ttu-id="19d36-321">機密ラベルのサポートを受ける</span><span class="sxs-lookup"><span data-stu-id="19d36-321">Support for sensitivity labels is coming</span></span>

<span data-ttu-id="19d36-322">現在は、[機密ラベル](sensitivity-labels.md)でなく、保持ラベルのみを条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-322">You can currently use only a retention label as a condition, not a [sensitivity label](sensitivity-labels.md).</span></span> <span data-ttu-id="19d36-323">現在、この条件において機密ラベルの使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="19d36-323">We're currently working on support for using a sensitivity label in this condition.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="19d36-324">この機能と他の機能の関係</span><span class="sxs-lookup"><span data-stu-id="19d36-324">How this feature relates to other features</span></span>

<span data-ttu-id="19d36-325">機密情報を含むコンテンツには複数の機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-325">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="19d36-326">[保持ラベル](labels.md#applying-a-retention-label-automatically-based-on-conditions)と[保持ポリシー](retention-policies.md)は、このコンテンツに**保持**操作を適用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-326">A [retention label](labels.md#applying-a-retention-label-automatically-based-on-conditions) and a [retention policy](retention-policies.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="19d36-327">DLP ポリシーは、このコンテンツに**保護**操作を適用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-327">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="19d36-328">ただし、これらの操作を適用する前に、DLP ポリシーにはラベルを含むコンテンツ以外にも一致する他の条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="19d36-328">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![機密情報に適用できる機能の図](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="19d36-330">DLP ポリシーには、機密情報に適用されるラベルや保持ポリシーよりも機能性の高い検出機能があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19d36-330">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="19d36-331">DLP ポリシーは、機密情報を含むコンテンツに保護アクションを適用できます。コンテンツから機密情報を削除すると、次回コンテンツがスキャンされたときにそれらの保護操作は取り消されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-331">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="19d36-332">ただし、機密情報を含むコンテンツに保持ポリシーまたはラベルが適用されている場合は、機密情報が削除された場合でも取り消されない 1 回限りの操作になります。</span><span class="sxs-lookup"><span data-stu-id="19d36-332">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="19d36-333">DLP ポリシーでラベルを条件として使用すると、そのラベルのコンテンツに保持操作と保護操作の両方を適用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-333">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="19d36-334">ラベルを含むコンテンツは機密情報を含むコンテンツとまったく同じように考えることができます。ラベルと機密情報の種類は両方とも、コンテンツの分類に使用されるプロパティです。このため、そのコンテンツに操作を適用できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-334">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![条件としてラベルを使用する DLP ポリシーの図](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="19d36-336">簡易設定と詳細設定</span><span class="sxs-lookup"><span data-stu-id="19d36-336">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="19d36-337">DLP ポリシーを作成するときは、次の簡易設定または詳細設定のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="19d36-337">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="19d36-338">**簡易設定**: ルール エディターを使ってルールを作成または変更することなく、最も一般的な種類の DLP ポリシーを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-338">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="19d36-339">**詳細設定**: ルール エディターを使って DLP ポリシーのすべての設定を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-339">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="19d36-340">見た目ではわかりませんが、条件とアクションで構成されるルールを適用することで、簡易設定と詳細設定はまったく同じように機能するのでご安心ください。簡易設定を使用する場合のみ、ルール エディターが表示されません。</span><span class="sxs-lookup"><span data-stu-id="19d36-340">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions -- only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="19d36-341">これにより、DLP ポリシーを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-341">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="19d36-342">簡易設定</span><span class="sxs-lookup"><span data-stu-id="19d36-342">Simple MAPI settings</span></span>

<span data-ttu-id="19d36-343">最も一般的な DLP のシナリオでは、ポリシーを作成して機密情報を含むコンテンツが組織外のユーザーと共有されるのを防ぎ、コンテンツにアクセス可能なユーザーを制限するなどの自動修復アクションを実行し、エンドユーザーや管理者に通知を送信し、後の調査のためにイベントを監査しています。</span><span class="sxs-lookup"><span data-stu-id="19d36-343">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remedial action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="19d36-344">ユーザーは、不注意による機密情報の漏洩を防ぐために DLP を使用します。</span><span class="sxs-lookup"><span data-stu-id="19d36-344">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="19d36-345">この目標を容易に達成するために、DLP ポリシーの作成時に [**簡易設定を使用**] を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-345">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="19d36-346">簡易設定では、ルール エディターに移動することなく、最も一般的な DLP ポリシーを実装するのに必要なすべてのものが提供されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-346">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![簡易設定と詳細設定の DLP オプション](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="19d36-348">詳細設定</span><span class="sxs-lookup"><span data-stu-id="19d36-348">Advanced settings</span></span>

<span data-ttu-id="19d36-349">よりカスタマイズされた DLP ポリシーを作成する必要がある場合は、[**詳細設定を使用**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-349">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="19d36-350">詳細設定では、ルール エディターが表示され、そこで各ルールのインスタンス数や一致精度 (信頼度) を含む、利用可能なオプションすべてを完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-350">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="19d36-351">セクションにすばやく移動するには、ルール エディターの上部のナビゲーションの項目をクリックして、下のセクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="19d36-351">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP ルール エディターの上部のナビゲーション メニュー](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="19d36-353">DLP ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="19d36-353">DLP policy templates</span></span>

<span data-ttu-id="19d36-354">DLP ポリシーの作成における最初のステップは、保護する情報を選択することです。</span><span class="sxs-lookup"><span data-stu-id="19d36-354">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="19d36-355">DLP テンプレートを使用すると、新しい一連のルールを初めから作成し、既定で含める必要がある情報の種類を判別するという労力を省くことができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-355">This saves you the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="19d36-356">その後、そうした要件を追加したり変更したりして、組織の特定の要件を満たすようにルールを調整できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-356">You can then add to or modify these requirements to fine tune the rule to meet your organization’s specific requirements.</span></span>
  
<span data-ttu-id="19d36-357">構成済みの DLP ポリシー テンプレートを使用すると、HIPAA データ、PCI DSS データ、グラム リーチ ブライリー法データ、またはロケール固有の個人情報 (P.I.) などの機密情報の特定の種類を検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="19d36-357">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (PII).</span></span> <span data-ttu-id="19d36-358">一般的な種類の機密情報を簡単に検出して保護できるように、Office 365 に含まれるポリシー テンプレートには、使用開始時に必要な最も一般的な機密情報の種類が既に含まれています。</span><span class="sxs-lookup"><span data-stu-id="19d36-358">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Office 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![米国愛国者法のテンプレートに注目したデータ損失防止ポリシーのテンプレートの一覧](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="19d36-360">組織には固有の要件がある場合もあるため、その場合は、[**カスタム ポリシー**] オプションを選択して、最初から DLP ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-360">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch.</span></span> <span data-ttu-id="19d36-361">カスタム ポリシーは空であり、既定のルールは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="19d36-361">A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="19d36-362">DLP ポリシーをテスト モードで段階的にロールアウトする</span><span class="sxs-lookup"><span data-stu-id="19d36-362">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="19d36-363">DLP ポリシーを作成するときは、完全に適用する前に、影響を評価し、有効性をテストしながら、段階的に展開することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-363">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="19d36-364">たとえば、ユーザーが業務を行うのに必要な大量のドキュメントへのアクセスを、新しい DLP ポリシーにより意図せずブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="19d36-364">For example, you don’t want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="19d36-365">大きな影響を与える可能性が高い DLP ポリシーを作成している場合は、次の順序に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="19d36-365">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="19d36-366">**ポリシー ヒントなしのテスト モードで開始**し、DLP レポートとインシデント レポートを使用して、影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="19d36-366">**Start in test mode without Policy Tips** and then use the DLP reports to assess the impact.</span></span> <span data-ttu-id="19d36-367">DLP レポートを使用すると、ポリシー一致の回数、場所、種類、および重要度を把握できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-367">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="19d36-368">その結果に基づいて、必要に応じてルールを細かく調整できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-368">Based on the results, you can fine tune the rules as needed.</span></span> <span data-ttu-id="19d36-369">テスト モードでは、DLP ポリシーは組織で業務に取り組んでいるユーザーの生産性に影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="19d36-369">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="19d36-p156">**通知とポリシー ヒントを利用するテスト モードに移行**して、コンプライアンス ポリシーについてユーザーを教育し、適用されるルールに対して準備できるようにします。この段階で、ルールをさらに精緻化できるように、ユーザーに誤検知を報告するよう依頼することもできます。</span><span class="sxs-lookup"><span data-stu-id="19d36-p156">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="19d36-372">**ポリシーの完全な適用を開始**し、ルールのアクションが適用され、コンテンツが保護されるようにします。</span><span class="sxs-lookup"><span data-stu-id="19d36-372">**Start full enforcement on the policies** so that the actions in the rules are applied and the content’s protected.</span></span> <span data-ttu-id="19d36-373">DLP レポートやインシデント レポート、通知を引き続き監視して、結果が計画どおりであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19d36-373">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
![テスト モードを使用しポリシーで有効化するオプション](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
<span data-ttu-id="19d36-375">いつでも DLP ポリシーを無効にできます。ポリシーのすべてのルールに反映されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-375">You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually.</span></span> <span data-ttu-id="19d36-376">ただし、ルール エディターで状態を切り替えることで、各ルールを個別に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="19d36-376">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>
  
![ポリシー内のルールを無効にするオプション](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

<span data-ttu-id="19d36-378">ポリシー内の複数のルールの優先順位を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="19d36-378">You can also change the priority of multiple rules in a policy.</span></span> <span data-ttu-id="19d36-379">変更するには、編集のためのポリシーを開きます。</span><span class="sxs-lookup"><span data-stu-id="19d36-379">To do that, open a policy for editing.</span></span> <span data-ttu-id="19d36-380">ルールの行では、省略記号 (**...**) を選択し、[**下へ移動**] または [**最後へ移動**] などのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="19d36-380">In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.</span></span>

![ルールの優先順位を設定する](media/dlp-set-rule-priority.png)
  
## <a name="dlp-reports"></a><span data-ttu-id="19d36-382">DLP レポート</span><span class="sxs-lookup"><span data-stu-id="19d36-382">DLP reports</span></span>

<span data-ttu-id="19d36-383">DLP ポリシーを作成して有効にしたら、意図したとおりに動作し、コンプライアンスの遵守に役立っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19d36-383">After you create and turn on your DLP policies, you’ll want to verify that they’re working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="19d36-384">DLP レポートを使用すると、DLP ポリシーとルールの一致の数の時間経過による変化や、誤検知と無効化の回数を、すぐに見ることができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-384">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="19d36-385">レポートごとに、場所や期間でこれらの一致をフィルター処理したり、さらには特定のポリシー、ルール、アクションで絞り込んだりできます。</span><span class="sxs-lookup"><span data-stu-id="19d36-385">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="19d36-386">DLP レポートを利用すると、ビジネスに関する洞察を得ると共に、以下のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="19d36-386">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="19d36-387">特定の期間に絞り込み、スパイクや傾向の理由を理解します。</span><span class="sxs-lookup"><span data-stu-id="19d36-387">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="19d36-388">組織のコンプライアンス ポリシーに違反するビジネス プロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="19d36-388">Discover business processes that violate your organization’s compliance policies.</span></span>
    
- <span data-ttu-id="19d36-389">DLP ポリシーのビジネスに及ぼす影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="19d36-389">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="19d36-390">さらに、DLP レポートを使用すると、DLP ポリシーの実行時にそれらのポリシーを調整できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-390">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![セキュリティとコンプライアンス センターのダッシュ ボードのレポート](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="19d36-392">DLP ポリシーのしくみ</span><span class="sxs-lookup"><span data-stu-id="19d36-392">How DLP policies work</span></span>

<span data-ttu-id="19d36-p161">DLP は、(単純なテキスト スキャンだけでなく) 詳細なコンテンツ分析を使用して、機密情報を検出します。この詳細なコンテンツ分析は、キーワード一致、辞書一致、正規表現の評価、内部関数などの方式を使用して、DLP ポリシーに一致するコンテンツを検出します。使用しているデータのうち、ごくわずかな割合のデータのみが機密性が高いと見なされる可能性があります。DLP ポリシーは、他のコンテンツを使用した作業を妨害したり影響を与えたりすることなく、対象データのみを識別、監視し、自動的に保護できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-p161">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="19d36-397">ポリシーの同期</span><span class="sxs-lookup"><span data-stu-id="19d36-397">Policies are synced</span></span>

<span data-ttu-id="19d36-398">セキュリティ &amp; コンプライアンス センターで DLP ポリシーを作成すると、集中管理ポリシー ストアに格納され、以下を含む各種コンテンツ ソースと同期されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-398">After you create a DLP policy in the  ComplianceAdmin, it’s stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="19d36-399">Exchange Online、そこから Outlook on the web、Outlook</span><span class="sxs-lookup"><span data-stu-id="19d36-399">Exchange Online, and from there to Outlook on the web and Outlook</span></span>
    
- <span data-ttu-id="19d36-400">OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="19d36-400">OneDrive for Business sites</span></span>
    
- <span data-ttu-id="19d36-401">SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="19d36-401">SharePoint Online sites</span></span>
    
- <span data-ttu-id="19d36-402">Office デスクトップ プログラム (Excel、PowerPoint、Word)</span><span class="sxs-lookup"><span data-stu-id="19d36-402">Office 2016 desktop programs (Excel 2016, PowerPoint 2016, and Word 2016)</span></span>

- <span data-ttu-id="19d36-403">Microsoft Teams チャネルおよびチャット メッセージ</span><span class="sxs-lookup"><span data-stu-id="19d36-403">Microsoft Teams chat threads and chat messages (preview)</span></span>
    
<span data-ttu-id="19d36-404">ポリシーが適切な場所に同期されると、コンテンツの評価とアクションの適用が開始されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-404">After the policy’s synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="19d36-405">OneDrive for Business サイトと SharePoint Online サイトのポリシー評価</span><span class="sxs-lookup"><span data-stu-id="19d36-405">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="19d36-406">すべての SharePoint Online サイトと OneDrive for Business サイトで、ドキュメントは常に変化し、作成、編集、共有などが継続的に行われています。</span><span class="sxs-lookup"><span data-stu-id="19d36-406">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they’re continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="19d36-407">つまり、ドキュメントはいつでも競合したり、DLP ポリシーに準拠するようになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-407">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="19d36-408">たとえば、あるユーザーがチーム サイトに機密情報を含まないドキュメントをアップロードし、後で別のユーザーが同じドキュメントを編集して機密情報を追加する、といったことが発生します。</span><span class="sxs-lookup"><span data-stu-id="19d36-408">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="19d36-409">このため、DLP ポリシーはバックグラウンドで頻繁にポリシーとの一致がドキュメントにあるかどうかを調べています。</span><span class="sxs-lookup"><span data-stu-id="19d36-409">For this reason, DLP policies check documents for policy matches frequently in the background.</span></span> <span data-ttu-id="19d36-410">これは非同期的なポリシーの評価と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-410">You can think of this as asynchronous policy evaluation.</span></span>
  
#### <a name="how-it-works"></a><span data-ttu-id="19d36-411">メカニズム</span><span class="sxs-lookup"><span data-stu-id="19d36-411">How it works</span></span>
 
<span data-ttu-id="19d36-412">ユーザーがサイトにドキュメントを追加したりドキュメントを変更したりすると、検索エンジンによってコンテンツがスキャンされるため、ユーザーが後で検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="19d36-412">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="19d36-413">これと併せて、コンテンツは機密情報に関してスキャンされ、共有されているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-413">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="19d36-414">見つかった機密情報は、コンプライアンス チームだけがアクセスでき、一般ユーザーはアクセスできないように、検索インデックスに安全に保存されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-414">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="19d36-415">有効にした DLP ポリシーはそれぞれバックグラウンドで (非同期に) 実行されるため、ポリシーと一致するコンテンツが頻繁に検索され、不注意によって漏えいされないようにアクションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-415">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![DLP ポリシーが非同期にコンテンツを評価する方法を示す図](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<span data-ttu-id="19d36-p165">最後に、ドキュメントが DLP ポリシーに矛盾し、その後 DLP ポリシーに準拠するようになることがあります。たとえば、ユーザーがドキュメントにクレジット カード番号を追加する場合、DLP ポリシーによってドキュメントへのアクセスが自動的にブロックされる可能性があります。しかしユーザーが後で機密情報を削除すると、次にドキュメントが対象ポリシーに対して再び評価されるときに、アクション (この例ではブロック) が自動的に取り消されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-p165">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="19d36-420">DLP は、インデックスを作成できるすべてのコンテンツを評価します。</span><span class="sxs-lookup"><span data-stu-id="19d36-420">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="19d36-421">既定でクロールされるファイルの種類の詳細については、「[SharePoint Server での既定のクロール対象ファイルのファイル名拡張子および解析対象ファイルの種類](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d36-421">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server 2013http://go.microsoft.com/fwlink/p/?LinkID=627430](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="19d36-422">Exchange Online、Outlook、Outlook on the web でのポリシーの評価</span><span class="sxs-lookup"><span data-stu-id="19d36-422">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="19d36-423">Exchange online を場所として含む DLP ポリシーを作成すると、このポリシーは Office 365 セキュリティ &amp; コンプライアンス センターから Exchange Online に同期され、その後、Exchange Online から Outlook on the web と Outlook に同期されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-423">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="19d36-424">メッセージが Outlook で作成される場合、作成中のコンテンツは DLP ポリシーに対して評価されるため、ユーザーはポリシー ヒントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="19d36-424">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="19d36-425">さらに、メッセージは、送信された後、通常のメール フローの一部として DLP ポリシーに対して評価されるほか、Exchange 管理センターで作成された (トランスポート ルールとしても知られる) Exchange メール フロー ルールや DLP ポリシーに対しても評価されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-425">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="19d36-426">DLP ポリシーは、メッセージと添付ファイルの両方をスキャンします。</span><span class="sxs-lookup"><span data-stu-id="19d36-426">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="19d36-427">Office デスクトップ プログラムにおけるポリシー評価</span><span class="sxs-lookup"><span data-stu-id="19d36-427">Policy evaluation in the Office 2016 desktop programs</span></span>

<span data-ttu-id="19d36-428">Excel、PowerPoint、Word には、機密情報を識別して DLP ポリシーを適用するための、SharePoint Online と OneDrive for Business と同じ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19d36-428">Excel 2016, PowerPoint 2016, and Word 2016 include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="19d36-429">これらの Office プログラムは、集中管理ポリシー ストアから直接 DLP ポリシーを同期し、DLP ポリシーに含まれるサイトから開かれたドキュメントをユーザーが扱うときに、DLP ポリシーに対してコンテンツを継続的に評価します。</span><span class="sxs-lookup"><span data-stu-id="19d36-429">These Office 2016 programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that’s included in a DLP policy.</span></span>
  
<span data-ttu-id="19d36-430">Office における DLP ポリシーの評価は、プログラムのパフォーマンス、またはコンテンツを扱っているユーザーの生産性に影響を与えることがないように設計されています。</span><span class="sxs-lookup"><span data-stu-id="19d36-430">DLP policy evaluation in Office 2016 is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="19d36-431">大規模なドキュメントを扱う場合、またはユーザーのコンピューターがビジー状態にある場合、ポリシー ヒントが表示されるまでに数秒かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="19d36-431">If they’re working on a large document, or the user’s computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="19d36-432">Microsoft Teams でのポリシーの評価</span><span class="sxs-lookup"><span data-stu-id="19d36-432">Policy evaluation in Microsoft Teams</span></span>
 
<span data-ttu-id="19d36-433">Microsoft teams を場所として含む DLP ポリシーを作成すると、Office 365 セキュリティ &amp; コンプライアンス センターからユーザー アカウントと Microsoft Teams のチャネルおよびチャット メッセージにポリシーが同期されます。</span><span class="sxs-lookup"><span data-stu-id="19d36-433">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="19d36-434">DLP ポリシーの構成方法によっては、ユーザーが Microsoft Teams のチャットやチャネル メッセージで機密情報を共有しようとしたときに、そのメッセージをブロックまたは取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="19d36-434">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="19d36-435">また、機密情報が含まれていて、ゲスト (外部ユーザー) と共有されているドキュメントは、このユーザー対しては開きません。</span><span class="sxs-lookup"><span data-stu-id="19d36-435">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="19d36-436">詳細については、「[データ損失防止と Microsoft Teams](dlp-microsoft-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d36-436">To learn more, see [Data loss prevention](dlp-microsoft-teams.md)</span></span>
 
## <a name="permissions"></a><span data-ttu-id="19d36-437">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="19d36-437">Permissions</span></span>

<span data-ttu-id="19d36-438">DLP ポリシーを作成するコンプライアンス チームのメンバーは、セキュリティ &amp; コンプライアンス センターへのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-438">Members of your compliance team who will create DLP policies need permissions to the Compliance Center.</span></span> <span data-ttu-id="19d36-439">既定では、テナント管理者はこの場所へのアクセス許可を持ち、コンプライアンス責任者や他のユーザーに対し、テナント管理者のすべてのアクセス許可を付与せずに、セキュリティ &amp; コンプライアンス センターへのアクセスを許可できます。これを行うには、次の操作を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="19d36-439">Members of your compliance team who will create DLP policies need permissions to the ComplianceAdmin. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the ComplianceAdmin, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="19d36-440">Office 365 でグループを作成して、コンプライアンス責任者をグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="19d36-440">Create a group in Office 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="19d36-441">セキュリティ &amp; コンプライアンス センターの [**アクセス許可**] ページで役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="19d36-441">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 
    
3. <span data-ttu-id="19d36-442">Office 365 のグループを役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="19d36-442">Add the Office 365 group to the role group.</span></span>
    
<span data-ttu-id="19d36-443">詳細については、「[Give users access to the Office 365 Security & Compliance Center (Office 365 セキュリティ/コンプライアンス センターへのアクセス権をユーザーに付与する)](grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d36-443">For more information, see [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="19d36-444">これらのアクセス許可は、DLP ポリシーを作成して適用するためにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="19d36-444">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="19d36-445">ポリシーの適用には、コンテンツへのアクセスは不要です。</span><span class="sxs-lookup"><span data-stu-id="19d36-445">Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="19d36-446">DLP コマンドレットを検索する</span><span class="sxs-lookup"><span data-stu-id="19d36-446">Find the DLP cmdlets</span></span>

<span data-ttu-id="19d36-447">セキュリティ &amp; コンプライアンス センターのほとんどのコマンドレットを使用するには、次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-447">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="19d36-448">リモート PowerShell を使用して Office 365 セキュリティ &amp; コンプライアンス センターに接続する</span><span class="sxs-lookup"><span data-stu-id="19d36-448">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    
2. <span data-ttu-id="19d36-449">これらの[ポリシーおよびコンプライアンスの dlp コマンドレット](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)のいずれかを使用する</span><span class="sxs-lookup"><span data-stu-id="19d36-449">Use any of these [policy-and-compliance-dlp cmdlets](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)</span></span>
    
<span data-ttu-id="19d36-450">ただし、DLP レポートは、Exchange Online を含む Office 365 全体からデータを取り込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-450">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="19d36-451">このため、**DLP レポート用のコマンドレットは、セキュリティ &amp; コンプライアンス センター Powershell ではなく Exchange Online Powershell で使用できます**。</span><span class="sxs-lookup"><span data-stu-id="19d36-451">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="19d36-452">したがって、DLP レポートのコマンドレットを使用するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d36-452">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="19d36-453">リモート PowerShell で Exchange Online に接続する</span><span class="sxs-lookup"><span data-stu-id="19d36-453">Connect to Exchange Online using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)
    
2. <span data-ttu-id="19d36-454">DLP レポート用のいずれかのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="19d36-454">Use any of these cmdlets for the DLP reports:</span></span>
    
  - [<span data-ttu-id="19d36-455">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="19d36-455">Get-DlpDetectionsReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetectionsReport?view=exchange-ps)
    
  - [<span data-ttu-id="19d36-456">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="19d36-456">Get-DlpDetailReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetailReport?view=exchange-ps)
    
## <a name="more-information"></a><span data-ttu-id="19d36-457">詳細情報</span><span class="sxs-lookup"><span data-stu-id="19d36-457">More information</span></span>

- [<span data-ttu-id="19d36-458">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="19d36-458">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="19d36-459">通知を送信して、DLP ポリシーのポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="19d36-459">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="19d36-460">FCI または他のプロパティを含むドキュメントを保護するために DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="19d36-460">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="19d36-461">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="19d36-461">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="19d36-462">機密情報の種類で検索される情報</span><span class="sxs-lookup"><span data-stu-id="19d36-462">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="19d36-463">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="19d36-463">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="19d36-464">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="19d36-464">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    

