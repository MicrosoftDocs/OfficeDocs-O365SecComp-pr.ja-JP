---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/04/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: 高度な脅威保護 office 365 にはには、なりすましのインテリジェンス、安全なリンク、安全な添付ファイル、および高度なフィッシング対策機能が含まれています。脅威の高度な保護も拡張されている SharePoint のオンライン、OneDrive 内のファイルにビジネス、およびマイクロソフトのチームです。
ms.openlocfilehash: 7d60ac9bff108a6746a5e89d05d70bba23d2671d
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741040"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="7288d-104">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7288d-104">Office 365 Advanced Threat Protection</span></span>

## <a name="overview-of-office-365-advanced-threat-protection"></a><span data-ttu-id="7288d-105">Office 365 の高度な脅威保護の概要</span><span class="sxs-lookup"><span data-stu-id="7288d-105">Overview of Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="7288d-106">Office 365 の高度な脅威保護 (ATP) は、悪意のある攻撃から組織を保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7288d-106">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="7288d-107">[ATP の安全な添付ファイル](atp-safe-attachments.md)にマルウェアが電子メールの添付ファイルをスキャン</span><span class="sxs-lookup"><span data-stu-id="7288d-107">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="7288d-108">電子メール メッセージおよび[ATP の安全なリンク](atp-safe-links.md)を含む Office ドキュメントでのスキャンの web アドレス (Url)</span><span class="sxs-lookup"><span data-stu-id="7288d-108">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="7288d-109">識別して、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)とライブラリがオンラインでの悪意のあるファイルをブロック</span><span class="sxs-lookup"><span data-stu-id="7288d-109">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="7288d-110">[スプーフィングのインテリジェンス](learn-about-spoof-intelligence.md)によって不正ななりすましの電子メール メッセージの確認</span><span class="sxs-lookup"><span data-stu-id="7288d-110">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="7288d-111">他のユーザーと[Office 365 の ATP のフィッシング対策機能](atp-anti-phishing.md)を持つ、組織のカスタム ドメインを偽装しようとするときを検出します。</span><span class="sxs-lookup"><span data-stu-id="7288d-111">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="7288d-p102">**Office 365 の ATP による保護は、安全なリンク、安全な添付ファイル、およびフィッシング詐欺対策のため、組織のセキュリティ チームを定義するポリシーによって決定されます**。ことが重要のポリシーを定義するのには、定期的に確認し、最新の状態にし、サービスに追加される新しい機能の利点をこれらのポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="7288d-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to define policies, and to periodically review and revise those policies to keep them up to date and to take advantages of new features that are added to the service.</span></span> 

<span data-ttu-id="7288d-p103">[レポートは、使用](view-reports-for-atp.md)は、組織の分析ツールを使用する方法を表示します。これらのレポートも表示できます領域を確認し、ポリシーを更新する必要があります。.、マルウェアをすべき、またはファイルかを確認するのにはマイクロソフトとマークされているファイルがあれば、[分析のためのマイクロソフトにファイルを送信](#submit-a-suspicious-file-to-microsoft-for-analysis)することができます。</span><span class="sxs-lookup"><span data-stu-id="7288d-p103">[Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>

## <a name="new-features-are-continually-being-added-to-atp"></a><span data-ttu-id="7288d-117">ATP に新機能が追加されているが継続的に</span><span class="sxs-lookup"><span data-stu-id="7288d-117">New features are continually being added to ATP</span></span>

<span data-ttu-id="7288d-p104">Office 365 に新しい機能を追加するのには継続していて、分析ツールが含まれています。ATP のポリシーを確認および更新するための呼び出しのいくつかの新機能の一覧を次に示します。ATP (または一般的な Microsoft 365) に導入された新機能に関する詳細については、[マイクロソフトの 365 のロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7288d-p104">We are continuing to add new features to Office 365, and that includes ATP. Below is a list of several new features, some of which call for an ATP policy to be reviewed and updated. To learn more about new features coming to ATP (or Microsoft 365 in general), visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).</span></span>


|<span data-ttu-id="7288d-121">機能の更新</span><span class="sxs-lookup"><span data-stu-id="7288d-121">Feature updates</span></span>  |<span data-ttu-id="7288d-122">アクション アイテム</span><span class="sxs-lookup"><span data-stu-id="7288d-122">Action items</span></span>  |
|---------|---------|
|<span data-ttu-id="7288d-p105">2018年 10 月年と、今後数か月にロールアウト、ユーザーが Outlook を使用しているまたは Outlook Web アプリケーション (OWA)、ATP の安全なリンク元の Url が表示されない場合は、Url を書き換えます。(このリンクはネイティブのレンダリングを呼び出して) します。</span><span class="sxs-lookup"><span data-stu-id="7288d-p105">Beginning in October 2018 and rolling out over the next several months, when people are using Outlook or Outlook Web Application (OWA), ATP Safe Links renders original URLs, not rewritten URLs. (We call this native link rendering.)</span></span><br><span data-ttu-id="7288d-125">ネイティブのリンクのレンダリングが、組織の利用可能な 365 (クイック実行) の Outlook と OWA の機能します。</span><span class="sxs-lookup"><span data-stu-id="7288d-125">When native link rendering is available for your organization, this feature will work in Outlook 365 (Click-to-Run) and OWA.</span></span>|<span data-ttu-id="7288d-126">なし</span><span class="sxs-lookup"><span data-stu-id="7288d-126">None</span></span>         |
|<span data-ttu-id="7288d-127">先頭 2018年 9 月で、[警告のページを Office 365 の分析ツール](atp-safe-links-warning-pages.md)の機能、新しい配色パターン、詳細についてとにもかかわらず、サイトを続行することには、警告と推奨事項が与えられます。</span><span class="sxs-lookup"><span data-stu-id="7288d-127">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> |<span data-ttu-id="7288d-128">なし</span><span class="sxs-lookup"><span data-stu-id="7288d-128">None</span></span>         |
|<span data-ttu-id="7288d-129">2018 の後半以降では、ATP の安全なリンクの保護を拡張 (オンラインの Word、Excel のオンライン、PowerPoint オンラインでは、および OneNote オンライン) オンライン Office および Office 365 用リソース mac 上での Url に適用するには</span><span class="sxs-lookup"><span data-stu-id="7288d-129">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac.</span></span>   |[<span data-ttu-id="7288d-130">確認し、ATP の安全なリンク ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="7288d-130">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md)  |
|<span data-ttu-id="7288d-131">遅延月 2018、セキュリティの[検査](quarantine-email-messages.md)機能に&amp;コンプライアンス センターは、 [SharePoint Online をビジネス、およびマイクロソフトのチームの OneDrive の分析ツール](atp-for-spo-odb-and-teams.md)を拡張します。</span><span class="sxs-lookup"><span data-stu-id="7288d-131">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to [ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> |[<span data-ttu-id="7288d-132">確認し、ATP の安全な添付ファイル ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="7288d-132">Review and edit your ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md) |
|<span data-ttu-id="7288d-133">2018年 3 月で以降では、ATP の安全なリンクの保護は、組織内のユーザー間で送信される電子メールに適用する拡張されます。</span><span class="sxs-lookup"><span data-stu-id="7288d-133">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization.</span></span> |[<span data-ttu-id="7288d-134">確認し、ATP の安全なリンク ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="7288d-134">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md) |
|<span data-ttu-id="7288d-135">遅延 2017年 10 月以降では、ATP の安全なリンクの保護に適用する Url の Url と同様に電子メールで Word、Excel、PowerPoint、および Visio など、Office 365 用リソースのドキュメントのウィンドウ、および Office に iOS および Android デバイス上のアプリ拡張されます。</span><span class="sxs-lookup"><span data-stu-id="7288d-135">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices.</span></span>  |<span data-ttu-id="7288d-136">[Office の最新の認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を使用するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7288d-136">Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span></span> |
  
## <a name="get-office-365-atp"></a><span data-ttu-id="7288d-137">Office 365 の ATP を取得します。</span><span class="sxs-lookup"><span data-stu-id="7288d-137">Get Office 365 ATP</span></span>

<span data-ttu-id="7288d-p106">[ [365 企業の Microsoft](https://www.microsoft.com/microsoft-365/enterprise/home)、Microsoft 365 ビジネス](https://www.microsoft.com/microsoft-365/business)、Office 365 のエンタープライズ E5、および Office 365 の教育 A5 などのサブスクリプションでは、office 365 の ATP が含まれます。組織が Office 365 の分析ツールが含まれていない Office 365 のサブスクリプションの場合は、アドオンとして可能性のある ATP を購入できます。詳細については、 [Office 365 高度な脅威保護サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7288d-p106">Office 365 ATP is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, and Office 365 Education A5. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 

## <a name="define-policies-for-atp"></a><span data-ttu-id="7288d-141">ATP のポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="7288d-141">Define policies for ATP</span></span>

<span data-ttu-id="7288d-142">ATP のポリシーを定義 (または編集) を割り当てる必要があります、次の表に記載されている役割のいずれか。</span><span class="sxs-lookup"><span data-stu-id="7288d-142">To define (or edit) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="7288d-143">役割</span><span class="sxs-lookup"><span data-stu-id="7288d-143">Role</span></span>  |<span data-ttu-id="7288d-144">場所と方法が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="7288d-144">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="7288d-145">Office 365 のグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7288d-145">Office 365 Global Administrator</span></span> |<span data-ttu-id="7288d-p107">Office 365 を購入するのに署名した人は、既定でグローバル管理者です。( [Office 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)の詳細についてを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7288d-p107">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="7288d-148">Office 365 のセキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="7288d-148">Office 365 Security Administrator</span></span> |<span data-ttu-id="7288d-149">管理者センター ([https://aka.ms/admincenter](https://aka.ms/admincenter))</span><span class="sxs-lookup"><span data-stu-id="7288d-149">Admin center ([https://aka.ms/admincenter](https://aka.ms/admincenter))</span></span>|
|<span data-ttu-id="7288d-150">Exchange オンライン組織の管理</span><span class="sxs-lookup"><span data-stu-id="7288d-150">Exchange Online Organization Management</span></span> |<span data-ttu-id="7288d-151">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="7288d-151">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="7288d-152">または</span><span class="sxs-lookup"><span data-stu-id="7288d-152">or</span></span> <br>  <span data-ttu-id="7288d-153">PowerShell コマンドレット (を参照してください[Exchange オンライン PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="7288d-153">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

<span data-ttu-id="7288d-154">ATP のポリシーを定義し、定期的に確認するのにはいくつかの種類があります。</span><span class="sxs-lookup"><span data-stu-id="7288d-154">There are several kinds of ATP policies to define and periodically review.</span></span>

1. <span data-ttu-id="7288d-155">**[Office 365 の ATP のフィッシング詐欺対策ポリシーを設定します](set-up-anti-phishing-policies.md)** 偽装ベースの攻撃を含む電子メール メッセージを送信する攻撃者に対して保護するためには、信頼されたユーザーまたはドメインからのように見えます。</span><span class="sxs-lookup"><span data-stu-id="7288d-155">**[Set up ATP anti-phishing policies in Office 365](set-up-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains.</span></span> 

2. <span data-ttu-id="7288d-156">**[Office 365 の ATP の安全なリンクのポリシーを設定](set-up-atp-safe-links-policies.md)** 組織の[ユーザー設定のブロックされた Url のリスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)と[カスタム」を書き換えない」の Url] ボックスの一覧](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を含みます。</span><span class="sxs-lookup"><span data-stu-id="7288d-156">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
3. <span data-ttu-id="7288d-157">**[Office 365 の ATP の安全な添付ファイル ポリシーを設定](set-up-atp-safe-attachments-policies.md)** し、[動的な配信およびプレビュー](dynamic-delivery-and-previewing.md)などのいくつかのオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="7288d-157">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** and choose from several options, such as [Dynamic Delivery and previewing](dynamic-delivery-and-previewing.md).</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="7288d-158">レポートを表示する分析ツールを使用する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7288d-158">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="7288d-p108">ATP のポリシーがあると後、は、サービスの操作方法を表示するレポートが利用できます。(Office 365 のセキュリティ & コンプライアンス センターでは、[**レポート**] に移動 > **ダッシュ ボード**です)。</span><span class="sxs-lookup"><span data-stu-id="7288d-p108">After your ATP policies are in place, reports are available to show how the service is working. (In the Office 365 Security & Compliance Center, go to **Reports** > **Dashboard**.)</span></span>

<span data-ttu-id="7288d-161">[![セキュリティ&amp;コンプライアンス センターのダッシュ ボードを使用して、脅威の高度な保護が作業しているを確認できます](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="7288d-161">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="7288d-162">移動すると、Office 365 のグローバル管理者、セキュリティ管理者、またはセキュリティのリーダー、[https://protection.office.com](https://protection.office.com)し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="7288d-162">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>
    
2. <span data-ttu-id="7288d-p109">**レポート**に > **のダッシュ ボード**です。(これらのレポートのヘルプを表示するには、[高度な脅威保護のためのレポートを表示する](view-reports-for-atp.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7288d-p109">Go to **Reports** > **Dashboard**. (To get help with these reports, see [View reports for Advanced Threat Protection](view-reports-for-atp.md).)</span></span>
    
3. <span data-ttu-id="7288d-p110">必要な場合、セキュリティ ポリシーを調整します。ヘルプを表示するには、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7288d-p110">If needed, make adjustments to your security policies. To get help with this, see the following resources:</span></span>
      - [<span data-ttu-id="7288d-167">Office 365 の ATP のフィッシング詐欺対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="7288d-167">ATP anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
      - [<span data-ttu-id="7288d-168">Office 365 の ATP の安全なリンクのポリシー</span><span class="sxs-lookup"><span data-stu-id="7288d-168">ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
      - [<span data-ttu-id="7288d-169">Office 365 の ATP の安全な添付ファイル ポリシー</span><span class="sxs-lookup"><span data-stu-id="7288d-169">ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="7288d-170">分析のためのマイクロソフトに不審なファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="7288d-170">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="7288d-p111">マルウェアである可能性があります疑いがあるファイルを取得する場合は、分析のためにマイクロソフトは、そのファイルを送信できます。[Windows Defender のセキュリティ情報発信のポータル](https://go.microsoft.com/fwlink/?linkid=857185)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="7288d-p111">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="7288d-173">分析のためにマイクロソフトに送信する電子メール メッセージ (添付ファイルの有無にかかわらず) を取得する場合[レポート メッセージのアドインを](enable-the-report-message-add-in.md)使用します。</span><span class="sxs-lookup"><span data-stu-id="7288d-173">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  

