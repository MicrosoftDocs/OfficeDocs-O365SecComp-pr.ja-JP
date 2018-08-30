---
title: Office 365 のセキュリティ レポート&amp;コンプライアンス センター
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/1/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: 'Office 365 のセキュリティを使用して、 &amp; 、SharePoint Online および Exchange オンライン組織のさまざまなレポートを取得するのにはコンプライアンスの中心と Azure Active Directory を報告します。  '
ms.openlocfilehash: 0b633583e14a18c7cf579d10462cf41714397812
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531629"
---
# <a name="reports-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="0a0b0-103">Office 365 のセキュリティ レポート&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="0a0b0-103">Reports in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="0a0b0-p101">Office 365 のセキュリティ**レポートを表示する**ページを使用することができます&amp;、SharePoint Online 組織と Exchange Online 組織の監査レポートを簡単にアクセスするコンプライアンス センターです。レポートにアクセスできます Azure Active Directory (AD) ユーザー サインインが、ユーザーの利用状況を報告して、Azure AD の監査**レポートを表示する**ページからログに記録します。これは、Office 365 サブスクリプションを購入には、Microsoft Azure への無料サブスクリプションが含まれているためにです。Azure のこれらのレポートにアクセスするときに最初に 1 回限りの登録プロセスを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-p101">You can use the **View reports** page in the Office 365 Security &amp; Compliance Center to quickly access audit reports for your SharePoint Online and Exchange Online organizations. You can also access Azure Active Directory (AD) user sign-in reports, user activity reports, and the Azure AD audit log from the **View reports** page. This is because your paid Office 365 subscription includes a free subscription to Microsoft Azure. The first time that you try to access these Azure reports, you will have to complete a one-time registration process.</span></span> 
  
> [!TIP]
> <span data-ttu-id="0a0b0-108">Office 365 の組織内の利用状況に関するレポートを表示するには、 [Office 365 の管理センターでの活動レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-108">To view additional reports about activity in your Office 365 organization, see [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).</span></span> 
  
 <span data-ttu-id="0a0b0-109">**開始する前に**</span><span class="sxs-lookup"><span data-stu-id="0a0b0-109">**Before you begin**</span></span>
  
<span data-ttu-id="0a0b0-110">セキュリティ レポートを表示するのには次のアクセスを許可する必要があります&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-110">You need the following permissions to view reports in the Security &amp; Compliance Center.</span></span>
  
- <span data-ttu-id="0a0b0-p102">Exchange 管理センター (EAC) が、セキュリティ レポートを表示するのにはセキュリティのリーダーの役割を割り当てる必要がある&amp;コンプライアンス センターです。既定では、このロールは、EAC で組織の管理とセキュリティのリーダーの役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-p102">You have to be assigned the Security Reader role in the Exchange admin center (EAC) to view reports in the Security &amp; Compliance Center. By default, this role is assigned to the Organization Management and Security Reader role groups in the EAC.</span></span>
    
- <span data-ttu-id="0a0b0-p103">セキュリティの DLP コンプライアンス管理の役割を割り当てる必要がある&amp;、セキュリティの DLP レポート (および DLP ポリシー) を表示するのにはコンプライアンス センター&amp;コンプライアンス センター。セキュリティ コンプライアンス管理者、組織の管理、およびセキュリティ管理者の役割グループに既定では、このロールが割り当てられている&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-p103">You have to be assigned the DLP Compliance Management role in the Security &amp; Compliance Center to view DLP reports (and DLP policies) in the Security &amp; Compliance Center. By default, this role is assigned to the Compliance Administrator, Organization Management, and Security Administrator role groups in the Security &amp; Compliance Center.</span></span>
    
<span data-ttu-id="0a0b0-p104">さらに、EAC で DLP レポート (および DLP ポリシー) を表示するのには EAC のデータ損失の防止の役割を割り当てられる必要があります。既定では、このロールは、EAC でコンプライアンスの管理と組織管理の役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-p104">Additionally, you would have to be assigned the Data Loss Prevention role in the EAC to view DLP reports (and DLP policies) in the EAC. By default, this role is assigned to the Compliance Management and Organization Management role groups in the EAC.</span></span>
  
 <span data-ttu-id="0a0b0-117">**セキュリティ レポート] ページでビューを開くに&amp;コンプライアンス センター。**</span><span class="sxs-lookup"><span data-stu-id="0a0b0-117">**To open the View reports page in the Security &amp; Compliance Center:**</span></span>
  
1. <span data-ttu-id="0a0b0-118">[https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-118">Go to [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).</span></span>
    
2. <span data-ttu-id="0a0b0-119">Office 365 組織内のユーザー アカウントの資格情報を使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-119">Sign in to Office 365 using the credentials for a user account in your Office 365 organization.</span></span>
    
<span data-ttu-id="0a0b0-120">[**レポートの表示**] ページで、次の種類のレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-120">On the **View reports** page, you can view the following types of reports:</span></span> 
  
- [<span data-ttu-id="0a0b0-121">EOP の監査レポート</span><span class="sxs-lookup"><span data-stu-id="0a0b0-121">Auditing reports</span></span>](#auditing-reports)
- [<span data-ttu-id="0a0b0-122">監督機関による監査レポート</span><span class="sxs-lookup"><span data-stu-id="0a0b0-122">Supervisory review report</span></span>](#supervisory-review-report)
- [<span data-ttu-id="0a0b0-123">データ損失防止レポート</span><span class="sxs-lookup"><span data-stu-id="0a0b0-123">Data loss prevention reports</span></span>](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a><span data-ttu-id="0a0b0-124">監査レポート</span><span class="sxs-lookup"><span data-stu-id="0a0b0-124">Auditing reports</span></span>

<span data-ttu-id="0a0b0-125">次の表に、セキュリティ**レポートを表示する**ページで **[監査**] セクションのレポート&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-125">The following table describes the reports in the **Auditing** section on the **View reports** page in the Security &amp; Compliance Center.</span></span> 
  
|<span data-ttu-id="0a0b0-126">**レポート**</span><span class="sxs-lookup"><span data-stu-id="0a0b0-126">**Report**</span></span>|<span data-ttu-id="0a0b0-127">**説明**</span><span class="sxs-lookup"><span data-stu-id="0a0b0-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0a0b0-128">**Office 365 の監査ログ レポート**</span><span class="sxs-lookup"><span data-stu-id="0a0b0-128">**Office 365 audit log report**</span></span> <br/> |<span data-ttu-id="0a0b0-p105">Office 365 の組織では、Office 365 の監査ログのユーザーと管理者のアクティビティを検索できます。レポートには、ビジネス、および Office 365 のディレクトリ サービスは、Azure Active Directory の Exchange Online、SharePoint Online の OneDrive のエントリのユーザーと管理者の活動が含まれています。詳細についてを参照してください[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-p105">You can search the Office 365 audit log for user and admin activity in your Office 365 organization. The report contains entries user and admin activity in Exchange Online, SharePoint Online, OneDrive for Business, and Azure Active Directory, which is the directory service for Office 365. For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).  </span></span><br/> |
|<span data-ttu-id="0a0b0-132">**Azure AD レポート**</span><span class="sxs-lookup"><span data-stu-id="0a0b0-132">**Azure AD reports**</span></span> <br/> |<span data-ttu-id="0a0b0-p106">サインインし、アクティビティを使用する、異常なまたは不審なサインインの活動、Office 365 の組織内を検索するのには Microsoft Azure でレポートします。Azure AD の監査ログにイベントを表示することもできます。Azure でレポートを表示するには、だけで**Azure AD] ビューに表示**をクリックします。詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-p106">To look for unusual or suspicious sign-in activity in your Office 365 organization, you can use sign-in and activity reports in Microsoft Azure. You can also view events in the Azure AD audit log. To view reports in Azure, just click **View Azure AD reports**. For more information, see: </span></span><br/><br/><span data-ttu-id="0a0b0-137">[Office 365 の無料、Azure Active Directory のサブスクリプションを使用](use-your-free-azure-ad-subscription-in-office-365.md)します。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-137">[Use your free Azure Active Directory subscription in Office 365](use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <br/> <span data-ttu-id="0a0b0-138">[アクセスと使用状況レポートを表示](http://go.microsoft.com/fwlink/p/?LinkId=506902)します。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-138">[View your access and usage reports](http://go.microsoft.com/fwlink/p/?LinkId=506902).</span></span>  <br/> |
|<span data-ttu-id="0a0b0-139">**Exchange 監査レポート**</span><span class="sxs-lookup"><span data-stu-id="0a0b0-139">**Exchange audit reports**</span></span> <br/> | <span data-ttu-id="0a0b0-p107">Office 365 の監査機能を使用するには、組織の管理者が、Exchange のオンラインでの構成に加えた変更を追跡します。Microsoft データ センターの管理者、または委任された管理者が、Exchange Online 組織に加えられた変更が記録されます。Exchange オンライン、管理者の監査を有効にするには何も実行する必要はありませんので、デフォルトでログを有効にします。Exchange Online は、メールボックスの監査を使用すると、メールボックスの所有者以外のユーザーがメールボックスへのアクセスを追跡するログを提供します。各メールボックスの所有者以外のアクセスを追跡するログ出力のメールボックスの監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-p107">You can use the auditing functionality in Office 365 to track changes made to your Exchange Online configuration by your organization's administrators. Changes made to your Exchange Online organization by a Microsoft data center administrator or by a delegated administrator are also logged. For Exchange Online, administrator audit logging is enabled by default, so you don't have to do anything to turn it on. Exchange Online also provides mailbox audit logging to let you track access to mailboxes by someone other than the mailbox owner. You have to enable mailbox audit logging for each mailbox that you want to track non-owner access.  </span></span><br/>  <span data-ttu-id="0a0b0-p108">管理者とメールボックスの両方の監査ログ、監査ログ ・ エントリーを表示するのには、監査レポートを実行することができます。メッセージを電子メールに添付されている XML ファイルに 24 時間以内に送信する、メールボックス、管理者の監査ログをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-p108">For both admin and mailbox audit logging, you can run audit reports to view the audit log entries. You can also export mailbox and admin audit logs, which are sent to you within 24 hours in an XML file that is attached to email message. </span></span><br/><br/><span data-ttu-id="0a0b0-147">監査ログをエクスポートする方法の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-147">For more information about exporting audit logs, see:</span></span>  <br/><br/> [<span data-ttu-id="0a0b0-148">メールボックス監査ログのエクスポート</span><span class="sxs-lookup"><span data-stu-id="0a0b0-148">Export mailbox audit logs</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [<span data-ttu-id="0a0b0-149">表示し、データ センター管理者の監査ログのエクスポート</span><span class="sxs-lookup"><span data-stu-id="0a0b0-149">View and export the datacenter admin audit log</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [<span data-ttu-id="0a0b0-150">役割グループの変更を検索するか、管理者の監査ログ</span><span class="sxs-lookup"><span data-stu-id="0a0b0-150">Search the role group changes or administrator audit logs</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   <span data-ttu-id="0a0b0-151">[Exchange 監査レポート](http://go.microsoft.com/fwlink/p/?LinkID=395232)をします。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-151">[Exchange auditing reports](http://go.microsoft.com/fwlink/p/?LinkID=395232).</span></span>  <br/> |
   
## <a name="supervisory-review-report"></a><span data-ttu-id="0a0b0-152">監督機関による監査レポート</span><span class="sxs-lookup"><span data-stu-id="0a0b0-152">Supervisory review report</span></span>

<span data-ttu-id="0a0b0-p109">監督機関による監査レポートを使用するには、組織のすべての監督機関による監査ポリシーのステータスを表示できます。詳細については、[監督者の構成、組織のポリシーを確認する](configure-supervision-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-p109">With the supervisory review report, you can see the status of all the supervisory review policies in your organization. For more information, see [Configure supervisory review policies for your organization](configure-supervision-policies.md).</span></span>
  
## <a name="data-loss-prevention-reports"></a><span data-ttu-id="0a0b0-155">データ損失防止レポート</span><span class="sxs-lookup"><span data-stu-id="0a0b0-155">Data loss prevention reports</span></span>

<span data-ttu-id="0a0b0-p110">データ損失防止 (DLP) は、DLP ポリシーに関する情報が含まれているし、コンテンツに適用されているルールには、Office 365 の組織内の機密データが含まれているを報告します。DLP ポリシーとルールをベースとする DLP のアクションに関する情報を表示するレポートを構成することもできます。詳細については、[データ損失の防止についてのレポートのビュー](view-the-dlp-reports.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a0b0-p110">Data loss prevention (DLP) reports contain information about the DLP policies and rules that have been applied to content contain sensitive data in your Office 365 organization. You can also configure the report to display information about DLP actions that were based on your DLP policy and rules. For more information, see [View the report for data loss prevention](view-the-dlp-reports.md).</span></span>
