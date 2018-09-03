---
title: Office 365 の脅威インテリジェンスと脅威の高度な保護と SIEM の統合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
description: Office 365 の脅威インテリジェンスと Office 365 の活動の管理 API を使用しての脅威保護の高度な組織の SIEM のサーバーを統合します。
ms.openlocfilehash: 40c84b9d7b7ec4c9b15383e3ffbbabf839294def
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782144"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a><span data-ttu-id="370f1-103">Office 365 の脅威インテリジェンスと脅威の高度な保護と SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="370f1-103">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>

<span data-ttu-id="370f1-p101">組織がセキュリティ インシデントとイベント管理 (SIEM) サーバーを使用している場合、SIEM のサーバーに Office 365 の脅威インテリジェンスと高度な脅威保護を統合できます。SIEM の統合により、SIEM サーバー レポートで Office 365 の高度な保護と脅威のインテリジェンスによって検出されたマルウェアなどの情報を表示することができます。SIEM の統合を設定するには、 [Office 365 の活動の管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用します。</span><span class="sxs-lookup"><span data-stu-id="370f1-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence and Advanced Threat Protection with your SIEM server. SIEM integration enables you to view information, such as malware detected by Office 365 Advanced Protection and Threat Intelligence, in your SIEM server reports. To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="370f1-p102">Office 365 の活動の管理 API は、組織の Office 365 と Azure Active Directory の動作状況のログから、ユーザー、管理者、システム、およびポリシー アクションとイベントについての情報を取得します。[Office 365 の高度な脅威保護し脅威インテリジェンス スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)動作脅威インテリジェンスと高度な脅威保護の組織に脅威インテリジェンスではありませんが (またはその逆) の高度な脅威保護がある場合は、することができます。まだ、SIEM サーバー統合のため同じ API を使用します。</span><span class="sxs-lookup"><span data-stu-id="370f1-p102">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs. The [Office 365 Advanced Threat Protection and Threat Intelligence schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Threat Intelligence and/or Advanced Threat Protection, so if your organization has Advanced Threat Protection but not Threat Intelligence (or vice versa), you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="370f1-p103">SIEM サーバーまたは他の同様のシステムは必要があります**audit.general**ワークロードへのアクセスの検出イベントをポーリングします。詳細を参照してください[Office 365 の管理 Api を使用](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)します。</span><span class="sxs-lookup"><span data-stu-id="370f1-p103">The SIEM server or other similar system should poll the **audit.general** workload to access detection events. To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="370f1-111">Office 365 のグローバル管理者であるか、SIEM の統合 Office 365 の脅威インテリジェンスと脅威の高度な保護を設定するのには、セキュリティとコンプライアンスの中心に割り当てられているセキュリティ管理者の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="370f1-111">You must be an Office 365 global administrator or have the security administrator role assigned in the Security & Compliance Center to set up SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection.</span></span></br><span data-ttu-id="370f1-p104">Office 365 環境の監査ログをオンにする必要があります。ヘルプを表示するには、[オンまたはオフ、Office 365 を有効にする監査ログの検索](turn-audit-log-search-on-or-off.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="370f1-p104">Audit logging must be turned on for your Office 365 environment. To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="370f1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="370f1-114">Related topics</span></span>

[<span data-ttu-id="370f1-115">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="370f1-115">Office 365 Threat Intelligence</span></span>](office-365-ti.md)

[<span data-ttu-id="370f1-116">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="370f1-116">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="370f1-117">スマート レポートと Office 365 のセキュリティ情報&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="370f1-117">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="370f1-118">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="370f1-118">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

