---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/09/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: 高度な脅威保護 office 365 にはには、なりすましのインテリジェンス、安全なリンク、安全な添付ファイル、および高度なフィッシング対策機能が含まれています。脅威の高度な保護も拡張されている SharePoint のオンライン、OneDrive 内のファイルにビジネス、およびマイクロソフトのチームです。
ms.openlocfilehash: def22368f8bc219ebceda797dd04b234bc3c4435
ms.sourcegitcommit: cda46434094bc2837dba90256d044ba77552df12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2018
ms.locfileid: "25850831"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="84ecc-104">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="84ecc-104">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="84ecc-105">Office 365 の高度な脅威保護 (ATP) は、悪意のある攻撃から組織を保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="84ecc-105">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="84ecc-106">[ATP の安全な添付ファイル](atp-safe-attachments.md)にマルウェアが電子メールの添付ファイルをスキャン</span><span class="sxs-lookup"><span data-stu-id="84ecc-106">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="84ecc-107">電子メール メッセージおよび[ATP の安全なリンク](atp-safe-links.md)を含む Office ドキュメントでのスキャンの web アドレス (Url)</span><span class="sxs-lookup"><span data-stu-id="84ecc-107">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="84ecc-108">識別して、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)とライブラリがオンラインでの悪意のあるファイルをブロック</span><span class="sxs-lookup"><span data-stu-id="84ecc-108">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="84ecc-109">[スプーフィングのインテリジェンス](learn-about-spoof-intelligence.md)によって不正ななりすましの電子メール メッセージの確認</span><span class="sxs-lookup"><span data-stu-id="84ecc-109">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="84ecc-110">他のユーザーと[Office 365 の ATP のフィッシング対策機能](atp-anti-phishing.md)を持つ、組織のカスタム ドメインを偽装しようとするときを検出します。</span><span class="sxs-lookup"><span data-stu-id="84ecc-110">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="84ecc-p102">**Office 365 の ATP による保護は、安全なリンク、安全な添付ファイル、およびフィッシング詐欺対策のため、組織のセキュリティ チームを定義するポリシーによって決定されます**。定期的に確認し、最新の状態にし、サービスに追加される新しい機能の利点を利用規約を修正するに重要です。[レポートは、使用](view-reports-for-atp.md)は、組織の分析ツールを使用する方法を表示します。これらのレポートも表示できます領域を確認し、ポリシーを更新する必要があります。.、マルウェアをすべき、またはファイルかを確認するのにはマイクロソフトとマークされているファイルがあれば、[分析のためのマイクロソフトにファイルを送信](#submit-a-suspicious-file-to-microsoft-for-analysis)することができます。</span><span class="sxs-lookup"><span data-stu-id="84ecc-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to periodically review and revise your policies to keep them up to date and to take advantages of new features that are added to the service. [Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>
      
## <a name="get-office-365-atp"></a><span data-ttu-id="84ecc-116">Office 365 の ATP を取得します。</span><span class="sxs-lookup"><span data-stu-id="84ecc-116">Get Office 365 ATP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84ecc-p103">Office 365 の分析ツールは、Microsoft 365 エンタープライズ、Office 365 エンタープライズ E5、Office 365 の教育 A5、および[Microsoft 365 ビジネス](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc)など、サブスクリプションに含まれます。組織が Office 365 の分析ツールが含まれていない Office 365 のサブスクリプションの場合は、アドオンとして可能性のある ATP を購入できます。詳細については、 [Office 365 高度な脅威保護サービスの説明](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ecc-p103">Office 365 ATP is included in subscriptions, such as Microsoft 365 Enterprise, Office 365 Enterprise E5, Office 365 Education A5, and [Microsoft 365 Business](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc). If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx).</span></span> 

1. <span data-ttu-id="84ecc-120">グローバルまたはセキュリティ管理者には、[https://portal.office.com](https://portal.office.com)と Office 365 は、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="84ecc-120">As a global or security administrator, go to [https://portal.office.com](https://portal.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="84ecc-121">**Admin**を選択して\>**請求**をして、現在のサブスクリプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="84ecc-121">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> <br/><span data-ttu-id="84ecc-122">![管理者にして、グローバル管理者としてサインイン portal.office.com\>請求](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)</span><span class="sxs-lookup"><span data-stu-id="84ecc-122">![As a global admin, sign in at portal.office.com and go to Admin \> Billing](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)</span></span>
  
3. <span data-ttu-id="84ecc-123">**Office 365 エンタープライズ E5**、 **Office 365 の教育 A5**、または**Microsoft 365 ビジネス**を表示する場合、組織は ATP をいます。</span><span class="sxs-lookup"><span data-stu-id="84ecc-123">If you see **Office 365 Enterprise E5**, **Office 365 Education A5**, or **Microsoft 365 Business**, then your organization has ATP.</span></span> <br/><span data-ttu-id="84ecc-p104">**Office 365 エンタープライズ E3**や**Office 365 エンタープライズ E1**など、別のサブスクリプションを参照する場合は、分析ツールを追加することを検討してください。そのためには、 **+ 追加のサブスクリプション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="84ecc-p104">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding ATP. To do that, choose **+ Add subscription**.</span></span>
    
<span data-ttu-id="84ecc-126">ATP を作成したら、次に、セキュリティ チーム用にポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="84ecc-126">Once you have ATP, the next step is for your security team to define policies.</span></span> 
  
## <a name="define-policies-for-atp"></a><span data-ttu-id="84ecc-127">ATP のポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="84ecc-127">Define policies for ATP</span></span>

- <span data-ttu-id="84ecc-128">信頼されたユーザーまたはドメインからのように見える**[Office 365 の ATP のフィッシング詐欺対策ポリシーを設定します](set-up-anti-phishing-policies.md)** 偽装ベースの攻撃を含む電子メール メッセージを送信する攻撃者から保護するため</span><span class="sxs-lookup"><span data-stu-id="84ecc-128">**[Set up ATP anti-phishing policies in Office 365](set-up-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains</span></span> 

- <span data-ttu-id="84ecc-129">**[Office 365 の ATP の安全なリンクのポリシーを設定](set-up-atp-safe-links-policies.md)** 組織の[ユーザー設定のブロックされた Url のリスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)と[カスタム」を書き換えない」の Url] ボックスの一覧](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を含む</span><span class="sxs-lookup"><span data-stu-id="84ecc-129">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)</span></span>
    
- <span data-ttu-id="84ecc-130">**[Office 365 の ATP の安全な添付ファイル ポリシーを設定](set-up-atp-safe-attachments-policies.md)** する[動的な配信およびプレビュー](dynamic-delivery-and-previewing.md)を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="84ecc-130">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** that can include [Dynamic Delivery and previewing](dynamic-delivery-and-previewing.md)</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="84ecc-131">レポートを表示する分析ツールを使用する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ecc-131">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="84ecc-132">ATP のポリシーがあると後、は、サービスの操作方法を表示するレポートが利用できます。</span><span class="sxs-lookup"><span data-stu-id="84ecc-132">After your ATP policies are in place, reports are available to show how the service is working.</span></span>

<span data-ttu-id="84ecc-133">[![セキュリティ&amp;コンプライアンス センターのダッシュ ボードを使用して、脅威の高度な保護が作業しているを確認できます](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="84ecc-133">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="84ecc-p105">Office 365 グローバル管理者、セキュリティ管理者、またはセキュリティのリーダーをしていることを確認します。(を参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="84ecc-p105">Make sure that you are an Office 365 global administrator, security administrator, or security reader. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="84ecc-136">[脅威の高度な保護に関するレポートを表示](view-reports-for-atp.md)します。</span><span class="sxs-lookup"><span data-stu-id="84ecc-136">[View reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span>
    
3. <span data-ttu-id="84ecc-p106">必要な場合、セキュリティ ポリシーを調整します。次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ecc-p106">If needed, make adjustments to your security policies. See the following resources:</span></span>

  - [<span data-ttu-id="84ecc-139">Office 365 の ATP のフィッシング詐欺対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="84ecc-139">ATP anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
    
  - [<span data-ttu-id="84ecc-140">Office 365 の ATP の安全なリンクのポリシー</span><span class="sxs-lookup"><span data-stu-id="84ecc-140">ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
    
  - [<span data-ttu-id="84ecc-141">Office 365 の ATP の安全な添付ファイル ポリシー</span><span class="sxs-lookup"><span data-stu-id="84ecc-141">ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="84ecc-142">分析のためのマイクロソフトに不審なファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="84ecc-142">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="84ecc-p107">マルウェアである可能性があります疑いがあるファイルを取得する場合は、分析のためにマイクロソフトは、そのファイルを送信できます。[Windows Defender のセキュリティ情報発信のポータル](https://go.microsoft.com/fwlink/?linkid=857185)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="84ecc-p107">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="84ecc-145">分析のためにマイクロソフトに送信する電子メール メッセージ (添付ファイルの有無にかかわらず) を取得する場合[レポート メッセージのアドインを](enable-the-report-message-add-in.md)使用します。</span><span class="sxs-lookup"><span data-stu-id="84ecc-145">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="84ecc-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="84ecc-146">Related topics</span></span>

[<span data-ttu-id="84ecc-147">脅威の高度な保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="84ecc-147">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="84ecc-148">Threat management in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="84ecc-148">Threat management in the Office 365 Security &amp; Compliance Center</span></span>](threat-management.md)
  

