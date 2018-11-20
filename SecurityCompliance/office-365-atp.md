---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/08/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: 高度な脅威保護 office 365 にはには、なりすましのインテリジェンス、安全なリンク、安全な添付ファイル、および高度なフィッシング対策機能が含まれています。脅威の高度な保護も拡張されている SharePoint のオンライン、OneDrive 内のファイルにビジネス、およびマイクロソフトのチームです。
ms.openlocfilehash: 1e6a2dc16bf5fb8dbf1b242a3495d8fb87cfda1c
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238479"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="ac0c8-104">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ac0c8-104">Office 365 Advanced Threat Protection</span></span>

## <a name="overview"></a><span data-ttu-id="ac0c8-105">概要</span><span class="sxs-lookup"><span data-stu-id="ac0c8-105">Overview</span></span>

<span data-ttu-id="ac0c8-106">Office 365 の高度な脅威保護 (ATP) は、悪意のある攻撃から組織を保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-106">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="ac0c8-107">[ATP の安全な添付ファイル](atp-safe-attachments.md)にマルウェアが電子メールの添付ファイルをスキャン</span><span class="sxs-lookup"><span data-stu-id="ac0c8-107">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="ac0c8-108">電子メール メッセージおよび[ATP の安全なリンク](atp-safe-links.md)を含む Office ドキュメントでのスキャンの web アドレス (Url)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-108">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="ac0c8-109">識別して、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)とライブラリがオンラインでの悪意のあるファイルをブロック</span><span class="sxs-lookup"><span data-stu-id="ac0c8-109">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="ac0c8-110">[スプーフィングのインテリジェンス](learn-about-spoof-intelligence.md)によって不正ななりすましの電子メール メッセージの確認</span><span class="sxs-lookup"><span data-stu-id="ac0c8-110">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="ac0c8-111">他のユーザーと[Office 365 の ATP のフィッシング対策機能](atp-anti-phishing.md)を持つ、組織のカスタム ドメインを偽装しようとするときを検出します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-111">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="ac0c8-p102">**Office 365 の ATP による保護は、安全なリンク、安全な添付ファイル、およびフィッシング詐欺対策のため、組織のセキュリティ チームを定義するポリシーによって決定されます**。定期的に確認し、最新の状態にし、サービスに追加される新しい機能の利点を利用規約を修正するに重要です。[レポートは、使用](view-reports-for-atp.md)は、組織の分析ツールを使用する方法を表示します。これらのレポートも表示できます領域を確認し、ポリシーを更新する必要があります。.、マルウェアをすべき、またはファイルかを確認するのにはマイクロソフトとマークされているファイルがあれば、[分析のためのマイクロソフトにファイルを送信](#submit-a-suspicious-file-to-microsoft-for-analysis)することができます。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to periodically review and revise your policies to keep them up to date and to take advantages of new features that are added to the service. [Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>

## <a name="new-features-are-continually-being-added-to-atp"></a><span data-ttu-id="ac0c8-117">ATP に新機能が追加されているが継続的に</span><span class="sxs-lookup"><span data-stu-id="ac0c8-117">New features are continually being added to ATP</span></span>

<span data-ttu-id="ac0c8-p103">Office 365 に新しい機能を追加するのには継続していて、分析ツールが含まれています。ATP のポリシーを確認および更新するための呼び出しのいくつかの新機能の一覧を次に示します。ATP (または一般的な Microsoft 365) に導入された新機能に関する詳細については、[マイクロソフトの 365 のロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p103">We are continuing to add new features to Office 365, and that includes ATP. Below is a list of several new features, some of which call for an ATP policy to be reviewed and updated. To learn more about new features coming to ATP (or Microsoft 365 in general), visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).</span></span>
  
- <span data-ttu-id="ac0c8-p104">遅延 2017年 10 月以降では、ATP の安全なリンクの保護に適用する Url の Url と同様に電子メールで Word、Excel、PowerPoint、および Visio など、Office 365 用リソースのドキュメントのウィンドウ、および Office に iOS および Android デバイス上のアプリ拡張されます。( [Office の最新の認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を使用することを確認してください。)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p104">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices. (Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span>
    
- <span data-ttu-id="ac0c8-p105">2018年 3 月で以降では、ATP の安全なリンクの保護は、組織内のユーザー間で送信される電子メールに適用する拡張されます。(を必ず[確認](set-up-atp-safe-links-policies.md)し、ATP の安全なリンク ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p105">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization. (Make sure to [review and edit your ATP Safe Links policies](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="ac0c8-125">遅延月 2018、セキュリティの[検査](quarantine-email-messages.md)機能に&amp;コンプライアンス センターは、 [SharePoint Online をビジネス、およびマイクロソフトのチームの OneDrive の分析ツール](atp-for-spo-odb-and-teams.md)を拡張します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-125">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to [ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>
 
- <span data-ttu-id="ac0c8-p106">2018 の後半以降では、ATP の安全なリンクの保護を拡張 (オンラインの Word、Excel のオンライン、PowerPoint オンラインでは、および OneNote オンライン) オンライン Office および Office 365 用リソース mac 上での Url に適用するには(を必ず[確認](set-up-atp-safe-links-policies.md)し、ATP の安全なリンク ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p106">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac. (Make sure to [review and edit your ATP Safe Links policies](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="ac0c8-128">先頭 2018年 9 月で、[警告のページを Office 365 の分析ツール](atp-safe-links-warning-pages.md)の機能、新しい配色パターン、詳細についてとにもかかわらず、サイトを続行することには、警告と推奨事項が与えられます。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-128">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> 
 
- <span data-ttu-id="ac0c8-p107">2018年 10 月年と、今後数か月にロールアウト、Outlook Web アプリケーション (OWA) を使用している人または、次の ATP の安全なリンク元の Url が表示されない場合は、Url を書き換えます。(このネイティブのリンクの表示/非表示を呼び出して) します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p107">Beginning in October 2018 and rolling out over the next several months, when people are using Outlook Web Application (OWA) or Outlook, ATP Safe Links renders original URLs, not rewritten URLs. (We call this native link visibility.)</span></span>

      
## <a name="get-office-365-atp"></a><span data-ttu-id="ac0c8-131">Office 365 の ATP を取得します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-131">Get Office 365 ATP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac0c8-p108">Office 365 の分析ツールは、Microsoft 365 エンタープライズ、Office 365 エンタープライズ E5、Office 365 の教育 A5、および[Microsoft 365 ビジネス](https://docs.microsoft.com/en-us/microsoft-365/business/security-features)など、サブスクリプションに含まれます。組織が Office 365 の分析ツールが含まれていない Office 365 のサブスクリプションの場合は、アドオンとして可能性のある ATP を購入できます。詳細については、 [Office 365 高度な脅威保護サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p108">Office 365 ATP is included in subscriptions, such as Microsoft 365 Enterprise, Office 365 Enterprise E5, Office 365 Education A5, and [Microsoft 365 Business](https://docs.microsoft.com/en-us/microsoft-365/business/security-features). If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 

1. <span data-ttu-id="ac0c8-135">グローバルまたはセキュリティ管理者には、[https://portal.office.com](https://portal.office.com)と Office 365 は、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-135">As a global or security administrator, go to [https://portal.office.com](https://portal.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="ac0c8-136">**Admin**を選択して\>**請求**をして、現在のサブスクリプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-136">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> <br/><span data-ttu-id="ac0c8-137">![管理者にして、グローバル管理者としてサインイン portal.office.com\>請求](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-137">![As a global admin, sign in at portal.office.com and go to Admin \> Billing](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)</span></span>
  
3. <span data-ttu-id="ac0c8-138">**Office 365 エンタープライズ E5**、 **Office 365 の教育 A5**、または**Microsoft 365 ビジネス**を表示する場合、組織は ATP をいます。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-138">If you see **Office 365 Enterprise E5**, **Office 365 Education A5**, or **Microsoft 365 Business**, then your organization has ATP.</span></span> <br/><span data-ttu-id="ac0c8-p109">**Office 365 エンタープライズ E3**や**Office 365 エンタープライズ E1**など、別のサブスクリプションを参照する場合は、分析ツールを追加することを検討してください。そのためには、 **+ 追加のサブスクリプション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p109">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding ATP. To do that, choose **+ Add subscription**.</span></span>
    
<span data-ttu-id="ac0c8-141">ATP を作成したら、次に、セキュリティ チーム用にポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-141">Once you have ATP, the next step is for your security team to define policies.</span></span> 
  
## <a name="define-policies-for-atp"></a><span data-ttu-id="ac0c8-142">ATP のポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-142">Define policies for ATP</span></span>

- <span data-ttu-id="ac0c8-143">信頼されたユーザーまたはドメインからのように見える**[Office 365 の ATP のフィッシング詐欺対策ポリシーを設定します](set-up-anti-phishing-policies.md)** 偽装ベースの攻撃を含む電子メール メッセージを送信する攻撃者から保護するため</span><span class="sxs-lookup"><span data-stu-id="ac0c8-143">**[Set up ATP anti-phishing policies in Office 365](set-up-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains</span></span> 

- <span data-ttu-id="ac0c8-144">**[Office 365 の ATP の安全なリンクのポリシーを設定](set-up-atp-safe-links-policies.md)** 組織の[ユーザー設定のブロックされた Url のリスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)と[カスタム」を書き換えない」の Url] ボックスの一覧](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を含む</span><span class="sxs-lookup"><span data-stu-id="ac0c8-144">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)</span></span>
    
- <span data-ttu-id="ac0c8-145">**[Office 365 の ATP の安全な添付ファイル ポリシーを設定](set-up-atp-safe-attachments-policies.md)** する[動的な配信およびプレビュー](dynamic-delivery-and-previewing.md)を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-145">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** that can include [Dynamic Delivery and previewing](dynamic-delivery-and-previewing.md)</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="ac0c8-146">レポートを表示する分析ツールを使用する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-146">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="ac0c8-147">ATP のポリシーがあると後、は、サービスの操作方法を表示するレポートが利用できます。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-147">After your ATP policies are in place, reports are available to show how the service is working.</span></span>

<span data-ttu-id="ac0c8-148">[![セキュリティ&amp;コンプライアンス センターのダッシュ ボードを使用して、脅威の高度な保護が作業しているを確認できます](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-148">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="ac0c8-p110">Office 365 グローバル管理者、セキュリティ管理者、またはセキュリティのリーダーをしていることを確認します。(を参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p110">Make sure that you are an Office 365 global administrator, security administrator, or security reader. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="ac0c8-151">[脅威の高度な保護に関するレポートを表示](view-reports-for-atp.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-151">[View reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span>
    
3. <span data-ttu-id="ac0c8-p111">必要な場合、セキュリティ ポリシーを調整します。次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p111">If needed, make adjustments to your security policies. See the following resources:</span></span>

  - [<span data-ttu-id="ac0c8-154">Office 365 の ATP のフィッシング詐欺対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac0c8-154">ATP anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
    
  - [<span data-ttu-id="ac0c8-155">Office 365 の ATP の安全なリンクのポリシー</span><span class="sxs-lookup"><span data-stu-id="ac0c8-155">ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
    
  - [<span data-ttu-id="ac0c8-156">Office 365 の ATP の安全な添付ファイル ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac0c8-156">ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="ac0c8-157">分析のためのマイクロソフトに不審なファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-157">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="ac0c8-p112">マルウェアである可能性があります疑いがあるファイルを取得する場合は、分析のためにマイクロソフトは、そのファイルを送信できます。[Windows Defender のセキュリティ情報発信のポータル](https://go.microsoft.com/fwlink/?linkid=857185)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-p112">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="ac0c8-160">分析のためにマイクロソフトに送信する電子メール メッセージ (添付ファイルの有無にかかわらず) を取得する場合[レポート メッセージのアドインを](enable-the-report-message-add-in.md)使用します。</span><span class="sxs-lookup"><span data-stu-id="ac0c8-160">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  

