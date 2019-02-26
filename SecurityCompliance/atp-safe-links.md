---
title: Office 365 の ATP の安全なリンク機能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 02/11/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: '[安全なリンク] 機能を使用すると、Office ドキュメントや電子メールメッセージ内のハイパーリンクの時間を確認できます。安全なリンクを使用して、フィッシングやその他の攻撃から組織を保護します。'
ms.openlocfilehash: 4ae125d5a7bf8f98a87c4edb9e93e32a9b256420
ms.sourcegitcommit: 5b5bbced1577701bdb6befc8ed252e9d9e776529
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2019
ms.locfileid: "30245613"
---
# <a name="office-365-atp-safe-links"></a><span data-ttu-id="fd85c-104">Office 365 の ATP の安全なリンク機能</span><span class="sxs-lookup"><span data-stu-id="fd85c-104">Office 365 ATP Safe Links</span></span>

## <a name="overview-of-office-365-atp-safe-links"></a><span data-ttu-id="fd85c-105">Office 365 の ATP の安全なリンクの概要</span><span class="sxs-lookup"><span data-stu-id="fd85c-105">Overview of Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd85c-p102">この記事は、Office 365 Enterprise のお客様を対象としています。Outlook.com、office 365 Home、または office 365 Personal を使用していて、Outlook での安全なリンクに関する情報をお探しの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p102">This article is intended for Office 365 Enterprise customers. If you are using Outlook.com, Office 365 Home, or Office 365 Personal, and you're looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="fd85c-p103">office 365 の ATP の安全なリンク ( [Advanced Threat Protection](office-365-atp.md)の一部) は、[電子メールメッセージ](#how-atp-safe-links-works-with-email)や[Office ドキュメント](#how-atp-safe-links-works-with-office-documents)内の web アドレス (url) の確認時間を提供することにより、組織を保護するのに役立ちます。保護は、Office 365 セキュリティチームによって設定された[ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p103">Office 365 ATP Safe Links (part of [Advanced Threat Protection](office-365-atp.md)) can help protect your organization by providing time-of-click verification of web addresses (URLs) in [email messages](#how-atp-safe-links-works-with-email) and [Office documents](#how-atp-safe-links-works-with-office-documents). Protection is defined through [ATP Safe Links policies](set-up-atp-safe-links-policies.md) that are set by your Office 365 security team.</span></span> 
  
<span data-ttu-id="fd85c-p104">ATP の安全なリンクポリシーが確立されると、Office 365 のグローバル管理者、セキュリティ管理者、およびセキュリティ閲覧者は、 [Advanced Threat Protection のレポートを表示](view-reports-for-atp.md)できるようになります。これらのレポートの情報は、セキュリティチームが組織を保護したり、セキュリティインシデントを研究したりするために、さらに手順を実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p104">Once your ATP Safe Links policies are in place, Office 365 global administrators, security administrators, and security readers can [view reports for Advanced Threat Protection](view-reports-for-atp.md). The information in those reports can help your security team take further steps to protect your organization or research security incidents.</span></span>

<span data-ttu-id="fd85c-p105">[新機能が atp に追加される](office-365-atp.md#new-features-in-office-365-atp)と、Office 365 セキュリティチームは、組織の atp の安全なリンクポリシーを追加または編集することができます。また、新しく改訂された[警告ページ](atp-safe-links-warning-pages.md)や、Outlook でのネイティブリンクのレンダリングなどの変更と改善が見られることがあります。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p105">As [new features are added to ATP](office-365-atp.md#new-features-in-office-365-atp), your Office 365 security team can add or edit your organization's ATP Safe Links policies. In addition, you might notice changes and improvements, such as our newly revised [warning pages](atp-safe-links-warning-pages.md) and native link rendering in Outlook.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="fd85c-114">ATP の安全なリンクが電子メール内の url と連携する方法</span><span class="sxs-lookup"><span data-stu-id="fd85c-114">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="fd85c-115">高レベルでは、(オンプレミスではなく Office 365 でホストされている) 電子メール内の url に対して、ATP の安全なリンク保護がどのように機能するかを説明します。</span><span class="sxs-lookup"><span data-stu-id="fd85c-115">At a high level, here's how ATP Safe Links protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="fd85c-116">ユーザーが電子メールメッセージを受信します。その中には、url が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd85c-116">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="fd85c-117">すべての電子メールは、インターネットプロトコル (IP) とエンベロープフィルター、署名ベースのマルウェア対策、スパム対策およびマルウェア対策フィルターを適用する Exchange Online Protection によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-117">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="fd85c-118">電子メールは、ユーザーの受信トレイで到着します。</span><span class="sxs-lookup"><span data-stu-id="fd85c-118">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="fd85c-119">ユーザーが Office 365 にサインインし、電子メールの受信トレイに進みます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-119">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="fd85c-120">ユーザーが電子メールメッセージを開き、電子メールメッセージ内の URL をクリックしたとき。</span><span class="sxs-lookup"><span data-stu-id="fd85c-120">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="fd85c-p106">ATP の安全なリンク機能は、web サイトを開く前に、すぐに URL をチェックします。URL は、ブロック、悪意、または安全として識別されます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p106">The ATP Safe Links feature immediately checks the URL before opening the website. The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="fd85c-123">ユーザーに適用されるポリシーの["リライト not リライト" url リスト](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれる web サイトへの url がある場合は、その web サイトが開きます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-123">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="fd85c-124">URL が組織のカスタムブロックされた[url リスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれる web サイトに対するものである場合は、[警告ページ](atp-safe-links-warning-pages.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-124">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="fd85c-125">悪意があると判断された web サイトへの URL の場合は、[警告のページ](atp-safe-links-warning-pages.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-125">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="fd85c-126">URL がダウンロード可能なファイルに送られ、組織の[ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)がそのようなコンテンツをスキャンするように構成されている場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-126">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="fd85c-127">URL が安全であると判断された場合は、web サイトが開きます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-127">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="fd85c-128">Office ドキュメントの url で ATP の安全なリンクが機能するしくみ</span><span class="sxs-lookup"><span data-stu-id="fd85c-128">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="fd85c-129">大まかには、office 365 ProPlus アプリケーション (windows または Mac 上の Word、Excel、PowerPoint の現在のバージョン、iOS または Android デバイス上の Office アプリ、Visio on Windows、OneNote online、office online) の url に対して、ATP の安全なリンク保護がどのように機能するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fd85c-129">At a high level, here's how ATP Safe Links protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote Online, and Office Online):</span></span>
  
1. <span data-ttu-id="fd85c-p107">ユーザーは、コンピューター、スマートフォン、またはタブレットに Office 365 ProPlus をインストールしています。(または、ブラウザーで Office Online を使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p107">People have installed Office 365 ProPlus on their computer, smartphone, or tablet. (Or, they are using Office Online in their browser.)</span></span>
    
2. <span data-ttu-id="fd85c-p108">ユーザーが Word、Excel、PowerPoint、または Visio を開き、職場または学校のアカウントを使用して Office 365 Enterprise にサインインします。ドキュメントに url が含まれている。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p108">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account. The document contains URLs.</span></span>
    
3. <span data-ttu-id="fd85c-134">ユーザーがドキュメント内の URL をクリックすると、そのリンクは ATP の安全なリンクサービスによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-134">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
  - <span data-ttu-id="fd85c-135">ユーザーに適用されるポリシーの["リライト not リライト" url リスト](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれる web サイトへの url がの場合、そのユーザーが web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="fd85c-135">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
  - <span data-ttu-id="fd85c-136">URL が組織のカスタムブロックされた[url リスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれる web サイトに対するものである場合、ユーザーは[警告ページ](atp-safe-links-warning-pages.md)に移動されます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-136">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="fd85c-137">悪意があると判断された web サイトに URL が設定されている場合、ユーザーは[警告ページ](atp-safe-links-warning-pages.md)にジャンプします。</span><span class="sxs-lookup"><span data-stu-id="fd85c-137">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="fd85c-138">URL がダウンロード可能なファイルに送られ、そのようなダウンロードをスキャンするように[ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)が構成されている場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-138">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
  - <span data-ttu-id="fd85c-139">URL が安全であると判断された場合は、ユーザーが web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="fd85c-139">If the URL is considered safe, the user is taken to the website.</span></span>

## <a name="how-to-get-atp-safe-links-protection"></a><span data-ttu-id="fd85c-140">ATP の安全なリンク保護を取得する方法</span><span class="sxs-lookup"><span data-stu-id="fd85c-140">How to get ATP Safe Links protection</span></span>

<span data-ttu-id="fd85c-p109">最初に、サブスクリプションに[Advanced Threat Protection](office-365-atp.md)が含まれていることを確認します。ATP は、 [microsoft 365 enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、office 365 Enterprise E5、office 365 エデュケーション A5 などのサブスクリプションに含まれています。office 365 atp を含まない office 365 サブスクリプションが組織にある場合は、atp をアドオンとして購入する可能性があります。詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p109">First, make sure your subscription includes [Advanced Threat Protection](office-365-atp.md). ATP is included in in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 
  
<span data-ttu-id="fd85c-p110">次に、ATP の安全なリンクポリシーが定義されていることを確認します。(「 [Office 365 ATP 安全リンクポリシーを](set-up-atp-safe-links-policies.md)セットアップする」を参照してください)。ATP の安全なリンク機能は、次の場合にアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p110">Next, make sure your ATP Safe Links policies are defined. (See [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).) ATP Safe Links features are active when:</span></span>
  
- <span data-ttu-id="fd85c-p111">**ATP の安全なリンクポリシーは**、電子メール、Word、Excel、PowerPoint、および Visio ドキュメント用に設定されています。(「 [Office 365 で ATP の安全なリンクポリシーを設定](set-up-atp-safe-links-policies.md)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p111">**ATP Safe Links policies are set up** for email and for Word, Excel, PowerPoint, and Visio documents. (See [Set up ATP safe links policies in Office 365](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="fd85c-p112">**Office 365 クライアントアプリが先進認証を使用するように構成されている**(これは、Office ドキュメントの ATP の安全なリンク保護のためです)。(「 [Office 2016 のモダン認証」を](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p112">**Office 365 client apps are configured to use Modern Authentication** (this is for ATP Safe Links protection in Office documents). (See [Modern Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span> 
    
- <span data-ttu-id="fd85c-p113">ユーザーが職場または学校のアカウントを使用して**Office 365 にサインイン**している。(「 [office または office 365 へのサインイン」を](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p113">**Users have signed into Office 365** using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
- <span data-ttu-id="fd85c-152">**組織の電子メールは、Exchange Online Protection**を通過します。</span><span class="sxs-lookup"><span data-stu-id="fd85c-152">**Your organization's email passes through Exchange Online Protection**.</span></span>  

<span data-ttu-id="fd85c-p114">ATP ポリシーを定義 (または編集) するには、適切な役割が割り当てられている必要があります。次の表では、いくつかの例について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p114">To define (or edit) ATP policies, you must be assigned an appropriate role. Some examples are described in the following table:</span></span>

|<span data-ttu-id="fd85c-155">役割</span><span class="sxs-lookup"><span data-stu-id="fd85c-155">Role</span></span>  |<span data-ttu-id="fd85c-156">参照先/割り当て方法</span><span class="sxs-lookup"><span data-stu-id="fd85c-156">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="fd85c-157">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="fd85c-157">Office 365 Global Administrator</span></span> |<span data-ttu-id="fd85c-p115">Office 365 の購入へのサインアップをする場合、既定ではグローバル管理者になります。詳細については、「[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p115">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="fd85c-160">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="fd85c-160">Security Administrator</span></span> |<span data-ttu-id="fd85c-161">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="fd85c-161">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="fd85c-162">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="fd85c-162">Exchange Online Organization Management</span></span> |<span data-ttu-id="fd85c-163">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="fd85c-163">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="fd85c-164">または</span><span class="sxs-lookup"><span data-stu-id="fd85c-164">or</span></span> <br>  <span data-ttu-id="fd85c-165">PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="fd85c-165">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a><span data-ttu-id="fd85c-166">ATP の安全なリンク保護が適切であることを確認する方法</span><span class="sxs-lookup"><span data-stu-id="fd85c-166">How to make sure ATP Safe Links protection is in place</span></span>

<span data-ttu-id="fd85c-p116">全体管理者またはセキュリティ管理者は、必ず ATP の[安全なリンクポリシー](set-up-atp-safe-links-policies.md)を確認してください。ATP の安全なリンクポリシーは、保護を電子メールメッセージのみのハイパーリンクに適用するか、Office ドキュメント内の url にも適用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p116">As a global administrator or security administrator, be sure to review your [ATP Safe Links policies](set-up-atp-safe-links-policies.md). ATP Safe Links policies determine whether protection applies to hyperlinks in email messages only, or to URLs in Office documents as well.</span></span>

<span data-ttu-id="fd85c-169">atp 安全なリンクポリシーが確立されると、組織のセキュリティチームは、 [Advanced Threat protection のレポートを表示](view-reports-for-atp.md)することによって、組織のために atp の安全なリンク保護がどのように機能しているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fd85c-169">After ATP Safe Links policies are in place, your organization's security team can see see how ATP Safe Links protection is working for your organization is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span> 

## <a name="example-scenarios"></a><span data-ttu-id="fd85c-170">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="fd85c-170">Example scenarios</span></span>
  
<span data-ttu-id="fd85c-p117">次の表では、ATP の安全なリンク保護が適用される可能性がある、または導入されていない可能性があるシナリオの例を示します。(これらすべての場合において、組織に Office 365 Enterprise E5 があると想定しています)。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p117">The following table describes some example scenarios where ATP Safe Links protection might or might not be in place. (In all of these cases, we assume the organization has Office 365 Enterprise E5.)</span></span>
  
|<span data-ttu-id="fd85c-173">**シナリオ例**</span><span class="sxs-lookup"><span data-stu-id="fd85c-173">**Example scenario**</span></span>|<span data-ttu-id="fd85c-174">**この場合、ATP の安全なリンク保護が適用されますか。**</span><span class="sxs-lookup"><span data-stu-id="fd85c-174">**Does ATP Safe Links protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fd85c-p118">田中は、電子メールおよび Office ドキュメント内の url を対象とする、ATP の安全なリンクポリシーを持つグループのメンバーです。田中は、他のユーザーが送信した PowerPoint プレゼンテーションを開き、プレゼンテーション内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p118">Jean is a member of a group that has ATP Safe Links policies covering URLs in email and Office documents. Jean opens a PowerPoint presentation that someone sent, and then clicks a URL in the presentation.</span></span>  <br/> |<span data-ttu-id="fd85c-p119">うん。定義されている ATP の安全なリンクポリシーは、田中のグループ、田中の電子メール、および Word、Excel、PowerPoint、または Visio ドキュメントに適用されるため、田中がサインインして、Windows、iOS、または Android デバイス上で Office 365 ProPlus を使用している場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p119">Yes. The ATP Safe Links policies that are defined apply to Jean's group, Jean's email, and Word, Excel, PowerPoint, or Visio documents that Jean opens, so long as Jean is signed in and using Office 365 ProPlus on Windows, iOS, or Android devices.</span></span>  <br/> |
|<span data-ttu-id="fd85c-p120">Chris の組織では、グローバルまたはセキュリティ管理者がまだ ATP の安全なリンクポリシーを定義していません。Chris は、悪意のある web サイトへの URL を含む電子メールを受信します。Chris は、URL が悪意があることを認識しないので、リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p120">In Chris's organization, no global or security administrators have defined any ATP safe links policies yet. Chris receives an email that contains a URL to a malicious website. Chris is unaware the URL is malicious and clicks the link.</span></span>  <br/> |<span data-ttu-id="fd85c-p121">違います。組織内のすべてのユーザーの url を対象とする既定のポリシーは、保護を確立するために定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p121">No. The default policy that covers URLs for everyone in the organization must be defined in order for protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="fd85c-p122">Pat の組織では、グローバルまたはセキュリティ管理者は、まだ ATP の安全なリンクポリシーを定義または編集していません。[Pat] Word 文書を開き、ファイル内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p122">In Pat's organization, no global or security administrators have defined or edited any ATP Safe Links policies yet. Pat opens a Word document and clicks a URL in the file.</span></span>  <br/> |<span data-ttu-id="fd85c-p123">いいえ。 Office ドキュメントを含むポリシーは、保護を設定するために定義されている必要があります。「 [Set up ATP Safe Links policies in Office 365」を](set-up-atp-safe-links-policies.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p123">No. A policy that includes Office documents must be defined in order for protection to be in place. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |
|<span data-ttu-id="fd85c-p124">Lee の組織には、ブロック`http://tailspintoys.com`された web サイトとしてリストされている、ATP の安全なリンクポリシーがあります。Lee は、の URL が含まれる電子メール`http://tailspintoys.com/aboutus/trythispage`メッセージを受信します。Lee が URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p124">Lee's organization has a ATP Safe Links policy that has `http://tailspintoys.com` listed as a blocked website. Lee receives an email message that contains a URL to `http://tailspintoys.com/aboutus/trythispage`. Lee clicks the URL.  </span></span><br/> |<span data-ttu-id="fd85c-p125">これは、サイト全体とそのすべてのサブページがブロックする url の一覧に含まれているかどうかによって決まります。「 [ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-wtih-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p125">It depends on whether the entire site and all its subpages are included in the list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).  </span></span><br/> |
|<span data-ttu-id="fd85c-194">田中の仕事仲間は、電子メールが悪意のある URL を含んでいることを知らずに、田中に電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="fd85c-194">Jamie, Jean's colleague, sends an email to Jean, not knowing that the email contains a malicious URL.</span></span>  <br/> |<span data-ttu-id="fd85c-p126">これは、組織内で送信される電子メールに ATP の安全なリンクポリシーが定義されているかどうかによって決まります。「 [Set up ATP Safe Links policies in Office 365」を](set-up-atp-safe-links-policies.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd85c-p126">It depends on whether ATP Safe Links policies are defined for email sent within the organization. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |


  

