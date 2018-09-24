---
title: Office 365 の ATP の安全なリンク機能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 安全なリンク機能は、Office ドキュメントや電子メール メッセージのハイパーリンクのクリックの検証を提供します。フィッシング詐欺やその他の攻撃から組織を保護するために安全なリンクを使用します。
ms.openlocfilehash: 35975ee58763578586b78d7d1f281fde81e1139b
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972349"
---
# <a name="office-365-atp-safe-links"></a><span data-ttu-id="a8868-104">Office 365 の ATP の安全なリンク機能</span><span class="sxs-lookup"><span data-stu-id="a8868-104">Office 365 ATP Safe Links</span></span>

<span data-ttu-id="a8868-p102">Office 365 ATP 安全なリンク (ATP の安全なリンク) ( [Office 365 ATP の安全な添付ファイル](atp-safe-attachments.md)) とは、企業向けの[Office 365 の高度な脅威保護](office-365-atp.md)の一部として提供されるセキュリティ機能のセットです。ATP の安全なリンクは、電子メール メッセージ、および Office ドキュメントの web アドレス (Url) のクリックの検証を提供することにより、組織を保護するために役立ちます。保護は、Office 365 のセキュリティ チームが設定されている[ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)によって定義されています。</span><span class="sxs-lookup"><span data-stu-id="a8868-p102">Office 365 ATP Safe Links (ATP Safe Links) (along with [Office 365 ATP Safe Attachments](atp-safe-attachments.md)) is a set of security features offered as part of [Office 365 Advanced Threat Protection](office-365-atp.md) for enterprise organizations. ATP Safe Links can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents. Protection is defined through [ATP Safe Links policies](set-up-atp-safe-links-policies.md) that are set by your Office 365 security team.</span></span> 
  
<span data-ttu-id="a8868-p103">場所、ATP の安全なリンク ポリシーが表示されたら、Office 365 のグローバル管理者、セキュリティ管理者、およびセキュリティのリーダーことができます[脅威保護の詳細に関するレポートを表示](view-reports-for-atp.md)します。それらのレポート内の情報は、セキュリティ チームは、組織を保護するか、セキュリティ インシデントを調査するそれ以上の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a8868-p103">Once your ATP Safe Links policies are in place, Office 365 global administrators, security administrators, and security readers can [view reports for Advanced Threat Protection](view-reports-for-atp.md). The information in those reports can help your security team take further steps to protect your organization or research security incidents.</span></span>
         
## <a name="how-atp-safe-links-works-with-email"></a><span data-ttu-id="a8868-110">電子メールに対する ATP の安全なリンクがどのように機能するか</span><span class="sxs-lookup"><span data-stu-id="a8868-110">How ATP Safe Links works with email</span></span>

<span data-ttu-id="a8868-111">高レベルでは、ここでは ATP の安全なリンク保護のしくみの url (Office 365 でないオンプレミスでホストされている) 電子メール。</span><span class="sxs-lookup"><span data-stu-id="a8868-111">At a high level, here's how ATP Safe Links protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="a8868-112">ユーザーには、Url が含まれているいくつかの電子メール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8868-112">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="a8868-113">すべての電子メールを通過、インターネット プロトコル (IP) とエンベロープ、フィルター処理、Exchange のオンライン保護シグネチャ ・ ベースのマルウェアからの保護、スパム対策とマルウェア対策のフィルターが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a8868-113">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="a8868-114">電子メールは、他のユーザーの受信トレイに到着します。</span><span class="sxs-lookup"><span data-stu-id="a8868-114">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="a8868-115">ユーザーが、Office 365 にサインインし、電子メールの受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="a8868-115">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="a8868-116">ユーザーは、電子メール メッセージを開くと、電子メール メッセージ内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8868-116">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="a8868-p104">ATP の安全なリンク機能は、すぐに web サイトを開く前に URL をチェックします。ブロックされると、悪意のある、または安全では、URL が識別されます。</span><span class="sxs-lookup"><span data-stu-id="a8868-p104">The ATP Safe Links feature immediately checks the URL before opening the website. The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="a8868-119">URL がユーザーに適用されるポリシーの[カスタム」を書き換えない」の Url] ボックスの一覧](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれている web サイトにある場合は、web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a8868-119">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="a8868-120">組織の[ユーザー設定のブロックされた Url のリスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれている web サイトへの URL の場合は、[警告のページ](atp-safe-links-warning-pages.md)が開きます。</span><span class="sxs-lookup"><span data-stu-id="a8868-120">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="a8868-121">URL は、悪意があると判断された web サイトには、[警告ページ](atp-safe-links-warning-pages.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8868-121">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="a8868-122">URL がダウンロード可能なファイルに移動し、このようなコンテンツをスキャンするのには、組織の[安全なリンクの ATP のポリシー](set-up-atp-safe-links-policies.md)が構成されて、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="a8868-122">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="a8868-123">安全のための URL が確認された場合、web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a8868-123">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-office-documents"></a><span data-ttu-id="a8868-124">Office ドキュメントに対する ATP の安全なリンクがどのように機能するか</span><span class="sxs-lookup"><span data-stu-id="a8868-124">How ATP Safe Links works with Office documents</span></span>

<span data-ttu-id="a8868-125">高レベルでは、ここでは Url の Office 365 用リソースのアプリケーション (Word、Excel、および PowerPoint では、Windows や Mac、iOS または Android デバイス、Windows、OneNote オンライン、および Office オンライン上の Visio での Office アプリケーションの現在のバージョン) で ATP の安全なリンクの保護の動作します。</span><span class="sxs-lookup"><span data-stu-id="a8868-125">At a high level, here's how ATP Safe Links protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote Online, and Office Online):</span></span>
  
1. <span data-ttu-id="a8868-p105">ユーザーは、コンピューター、スマート フォンやタブレットに Office 365 用リソース インストールされています。(または、使用している Office オンラインのブラウザーで)。</span><span class="sxs-lookup"><span data-stu-id="a8868-p105">People have installed Office 365 ProPlus on their computer, smartphone, or tablet. (Or, they are using Office Online in their browser.)</span></span>
    
2. <span data-ttu-id="a8868-p106">ユーザーは、Word、Excel、PowerPoint、または Visio を開くし、Office 365 の企業、職場、学校のアカウントを使用してにサインインします。ドキュメントには、Url が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8868-p106">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account. The document contains URLs.</span></span>
    
3. <span data-ttu-id="a8868-130">ユーザーは、ドキュメントの URL をクリックすると、ATP の安全なリンク サービスのリンクがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="a8868-130">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
  - <span data-ttu-id="a8868-131">URL は、ユーザーに適用されるポリシーの[カスタム」を書き換えない」の Url] ボックスの一覧](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれている web サイトには、web サイトにそのユーザーが取得されます。</span><span class="sxs-lookup"><span data-stu-id="a8868-131">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
  - <span data-ttu-id="a8868-132">組織の[ユーザー設定のブロックされた Url のリスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれている web サイトへの URL の場合は、[警告ページ](atp-safe-links-warning-pages.md)にユーザーが取得されます。</span><span class="sxs-lookup"><span data-stu-id="a8868-132">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="a8868-133">悪意があると判断された web サイトへの URL の場合は、[警告ページ](atp-safe-links-warning-pages.md)にユーザーが取得されます。</span><span class="sxs-lookup"><span data-stu-id="a8868-133">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="a8868-134">URL がダウンロード可能なファイルに移動し、 [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)は、このようなダウンロードをスキャンするよう構成する場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="a8868-134">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
  - <span data-ttu-id="a8868-135">URL は、安全と見なされますが、web サイトにユーザーが取得されます。</span><span class="sxs-lookup"><span data-stu-id="a8868-135">If the URL is considered safe, the user is taken to the website.</span></span>

## <a name="new-features-added-to-atp-safe-links"></a><span data-ttu-id="a8868-136">ATP の安全なリンクに追加された新しい機能</span><span class="sxs-lookup"><span data-stu-id="a8868-136">New features added to ATP Safe Links</span></span>

<span data-ttu-id="a8868-p107">ATP の安全なリンクに新しい機能を追加することを継続しています。いくつかの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a8868-p107">We are continuing to add new features to ATP Safe Links. Here are several examples:</span></span>
  
- <span data-ttu-id="a8868-p108">遅延 2017年 10 月以降では、ATP の安全なリンクの保護に適用する Url の Url と同様に電子メールで Word、Excel、PowerPoint、および Visio など、Office 365 用リソースのドキュメントのウィンドウ、および Office に iOS および Android デバイス上のアプリ拡張されます。( [Office の最新の認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を使用することを確認してください。)</span><span class="sxs-lookup"><span data-stu-id="a8868-p108">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices. (Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span>
    
- <span data-ttu-id="a8868-141">2018年 3 月で以降では、ATP の安全なリンクの保護は、組織内のユーザー間で送信される電子メールに適用する拡張されます。</span><span class="sxs-lookup"><span data-stu-id="a8868-141">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization.</span></span>

- <span data-ttu-id="a8868-p109">ユーザーが Outlook Web アプリケーション (OWA) を使用している、2018年 6 月年 ATP の安全なリンクは、元の Url をレンダリングし、書き換えられた Url を表示しません。電子メールの元のリンクを表示するのにはこれができます。(この機能はまだ Outlook クライアント アプリケーションを使用します。)</span><span class="sxs-lookup"><span data-stu-id="a8868-p109">Beginning in June 2018, when people are using Outlook Web Application (OWA), ATP Safe Links renders original URLs, and not show rewritten URLs. This enables users to view original links in email. (This feature is not yet available for Outlook client apps.)</span></span>
    
- <span data-ttu-id="a8868-145">2018 の後半以降では、ATP の安全なリンクの保護を拡張 (オンラインの Word、Excel のオンライン、PowerPoint オンラインでは、および OneNote オンライン) オンライン Office および Office 365 用リソース mac 上での Url に適用するには</span><span class="sxs-lookup"><span data-stu-id="a8868-145">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac.</span></span>
    
- <span data-ttu-id="a8868-146">先頭 2018年 9 月で、[警告のページを Office 365 の分析ツール](atp-safe-links-warning-pages.md)の機能、新しい配色パターン、詳細についてとにもかかわらず、サイトを続行することには、警告と推奨事項が与えられます。</span><span class="sxs-lookup"><span data-stu-id="a8868-146">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> 
    
## <a name="how-to-get-atp-safe-links-protection"></a><span data-ttu-id="a8868-147">ATP の安全なリンクを保護する方法</span><span class="sxs-lookup"><span data-stu-id="a8868-147">How to get ATP Safe Links protection</span></span>

<span data-ttu-id="a8868-p110">ATP の安全なリンク機能は、[脅威の高度な保護](office-365-atp.md)、Office 365 エンタープライズ E5 に含まれているの一部です。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合は、アドオンとして脅威の高度な保護を購入できます。詳細についてを参照してください[Office 365 のプラットフォーム サービスの説明: Office 365 のセキュリティ&amp;コンプライアンス センター](https://technet.microsoft.com/en-us/library/dn933793.aspx) [購入またはビジネスのための Office 365 のアドオンを編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)するとします。</span><span class="sxs-lookup"><span data-stu-id="a8868-p110">ATP Safe Links features are part of [Advanced Threat Protection](office-365-atp.md), included in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span>
  
<span data-ttu-id="a8868-151">ATP の安全なリンク機能は、次のような場合アクティブです。</span><span class="sxs-lookup"><span data-stu-id="a8868-151">The ATP Safe Links features are active when:</span></span>
  
- <span data-ttu-id="a8868-p111">**ATP の安全なリンク ポリシーが設定されて**メールや Word、Excel、PowerPoint、および Visio のドキュメントです。( [Office 365 の ATP の安全なリンク ポリシーの設定](set-up-atp-safe-links-policies.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a8868-p111">**ATP Safe Links policies are set up** for email and for Word, Excel, PowerPoint, and Visio documents. (See [Set up ATP safe links policies in Office 365](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="a8868-p112">**現代の認証を使用する office 365 クライアント アプリケーションを構成**します。( [2016 の Office の最新の認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a8868-p112">**Office 365 client apps are configured to use Modern Authentication**. (See [Modern Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span> 
    
- <span data-ttu-id="a8868-p113">**ユーザーが Office 365 にサインインして**、職場、学校のアカウントを使用しています。(詳しくは、 [Office または Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a8868-p113">**Users have signed into Office 365** using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
- <span data-ttu-id="a8868-158">**組織の電子メールが Office 365 でホストされている**、オンプレミスのサーバーではなく。</span><span class="sxs-lookup"><span data-stu-id="a8868-158">**Your organization's email is hosted in Office 365**, not in an on-premises server.</span></span> 
    
## <a name="make-sure-atp-safe-links-protection-is-in-place"></a><span data-ttu-id="a8868-159">ATP の安全なリンクの保護が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8868-159">Make sure ATP Safe Links protection is in place</span></span>

<span data-ttu-id="a8868-p114">[脅威の高度な保護のためのレポートを表示する](view-reports-for-atp.md)ことでは、組織の安全なリンクの ATP の保護を使用する方法を表示する方法の 1 つ。さらに、グローバルまたはセキュリティ管理者は、 [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)を確認することを確認します。ATP の安全なリンク ポリシーは、保護に適用するか電子メール メッセージ内のハイパーリンクまたは Url にのみ、Office ドキュメントも同様を決定します。</span><span class="sxs-lookup"><span data-stu-id="a8868-p114">One good way to see how ATP Safe Links protection is working for your organization is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md). Additionally, as a global or security administrator, be sure to review your [ATP Safe Links policies](set-up-atp-safe-links-policies.md). ATP Safe Links policies determine whether protection applies to hyperlinks in email messages only, or to URLs in Office documents as well.</span></span>

## <a name="example-scenarios-where-atp-safe-links-protection-might-or-might-not-be-in-place"></a><span data-ttu-id="a8868-163">ATP の安全なリンクの保護の可能性があります、または配置できない場合がありますシナリオの例</span><span class="sxs-lookup"><span data-stu-id="a8868-163">Example scenarios where ATP Safe Links protection might or might not be in place</span></span>
  
<span data-ttu-id="a8868-p115">次の表では、ATP の安全なリンクの保護の可能性があります、または配置できない場合がありますいくつかのサンプル シナリオについて説明します。(すべてのこれらの場合にと仮定した組織には、Office 365 エンタープライズ E5。)</span><span class="sxs-lookup"><span data-stu-id="a8868-p115">The following table describes some example scenarios where ATP Safe Links protection might or might not be in place. (In all of these cases, we assume the organization has Office 365 Enterprise E5.)</span></span>
  
|<span data-ttu-id="a8868-166">**シナリオ例**</span><span class="sxs-lookup"><span data-stu-id="a8868-166">**Example scenario**</span></span>|<span data-ttu-id="a8868-167">**ATP の安全なリンクの保護はここで適用しますか。**</span><span class="sxs-lookup"><span data-stu-id="a8868-167">**Does ATP Safe Links protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8868-p116">Jean は、電子メールや Office ドキュメントの Url に対応する分析ツールの安全なリンク ポリシーのあるグループのメンバーです。ジャンはその他の PowerPoint の 2016年に送信されたプレゼンテーションを開くし、プレゼンテーションの URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8868-p116">Jean is a member of a group that has ATP Safe Links policies covering URLs in email and Office documents. Jean opens a presentation that someone sent in PowerPoint 2016, and then clicks a URL in the presentation.</span></span>  <br/> |<span data-ttu-id="a8868-p117">うん。ジャンのグループ、ジャンの電子メール、Jean が開き、Jean がサインインしている限り、Word、Excel、PowerPoint、または Visio のドキュメントと Office 365 用リソースまたはを使用して Windows、iOS、Android のデバイスに定義されている ATP の安全なリンク ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a8868-p117">Yes. The ATP Safe Links policies that are defined apply to Jean's group, Jean's email, and Word, Excel, PowerPoint, or Visio documents that Jean opens, so long as Jean is signed in and using Office 365 ProPlus on Windows, iOS, or Android devices.</span></span>  <br/> |
|<span data-ttu-id="a8868-p118">ないグローバル組織またはセキュリティ管理者が定義した、ATP の安全なリンク ポリシーまだ。山口さんは、悪意のある web サイトへの URL を含む電子メールを受信します。山口さんには認識されていない URL は、悪意のあるし、リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8868-p118">In Chris's organization, no global or security administrators have defined any ATP safe links policies yet. Chris receives an email that contains a URL to a malicious website. Chris is unaware the URL is malicious and clicks the link.</span></span>  <br/> |<span data-ttu-id="a8868-p119">違います。適切に保護するために組織内のすべてのユーザーに対して Url をカバーする既定のポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8868-p119">No. The default policy that covers URLs for everyone in the organization must be defined in order for protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="a8868-p120">Pat のないグローバル組織またはセキュリティ管理者が定義されているまたは ATP の安全なリンクのすべてのポリシーの編集が完了します。Pat は Word ドキュメントを開くし、ファイルの URL をクリックすると。</span><span class="sxs-lookup"><span data-stu-id="a8868-p120">In Pat's organization, no global or security administrators have defined or edited any ATP Safe Links policies yet. Pat opens a Word document and clicks a URL in the file.</span></span>  <br/> |<span data-ttu-id="a8868-p121">Office ドキュメントが含まれます。 ポリシーは、適切に保護するために定義しなければなりません。[Office 365 の ATP の安全なリンクのポリシーの設定](set-up-atp-safe-links-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8868-p121">No. A policy that includes Office documents must be defined in order for protection to be in place. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |
|<span data-ttu-id="a8868-p122">Lee の組織には、ATP の安全なリンクを持つポリシーを`http://tailspintoys.com`ブロックされた web サイトとして表示されます。Lee の URL を含む電子メール メッセージを受信する`http://tailspintoys.com/aboutus/trythispage`。Lee では、URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8868-p122">Lee's organization has a ATP Safe Links policy that has `http://tailspintoys.com` listed as a blocked website. Lee receives an email message that contains a URL to `http://tailspintoys.com/aboutus/trythispage`. Lee clicks the URL.  </span></span><br/> |<span data-ttu-id="a8868-p123">サイト全体とそのサブページがの一覧に含まれるすべての Url をブロックするかどうかによって異なります。[ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8868-p123">It depends on whether the entire site and all its subpages are included in the list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).  </span></span><br/> |
|<span data-ttu-id="a8868-187">青木さん、ジャンの仕事仲間、電子メールを送信しジャン、電子メールに悪意のある URL が含まれていることもできます。</span><span class="sxs-lookup"><span data-stu-id="a8868-187">Jamie, Jean's colleague, sends an email to Jean, not knowing that the email contains a malicious URL.</span></span>  <br/> |<span data-ttu-id="a8868-p124">組織内で送信される電子メールの ATP の安全なリンクのポリシーが定義されているかどうかによって異なります。[Office 365 の ATP の安全なリンクのポリシーの設定](set-up-atp-safe-links-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8868-p124">It depends on whether ATP Safe Links policies are defined for email sent within the organization. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |
   
## <a name="related-topics"></a><span data-ttu-id="a8868-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8868-190">Related topics</span></span>

[<span data-ttu-id="a8868-191">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a8868-191">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="a8868-192">Office 365 の ATP の安全なリンクのポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="a8868-192">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="a8868-193">ATP の安全な添付ファイルを Office 365 で</span><span class="sxs-lookup"><span data-stu-id="a8868-193">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="a8868-194">Office 365 の ATP のフィッシング詐欺対策機能</span><span class="sxs-lookup"><span data-stu-id="a8868-194">ATP anti-phishing capabilities in Office 365</span></span>](atp-anti-phishing.md)
  
[<span data-ttu-id="a8868-195">脅威の高度な保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="a8868-195">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

