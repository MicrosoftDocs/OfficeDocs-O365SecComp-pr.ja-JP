---
title: SIEM と Office 365 の脅威インテリジェンスおよび Advanced threat Protection との統合
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
description: office 365 の脅威インテリジェンスと Advanced Threat Protection を使用して、組織の SIEM サーバーを office 365 アクティビティ管理 API と統合します。
ms.openlocfilehash: 854f763b72dfac1a5dc1442b1d9d123ed5439257
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087246"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a><span data-ttu-id="d49a3-103">SIEM と Office 365 の脅威インテリジェンスおよび Advanced threat Protection との統合</span><span class="sxs-lookup"><span data-stu-id="d49a3-103">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>

<span data-ttu-id="d49a3-p101">組織でセキュリティインシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 の脅威インテリジェンスと Advanced Threat Protection を SIEM サーバーに統合できます。SIEM の統合を使用すると、SIEM server レポートに、Office 365 の高度な保護と脅威のインテリジェンスによって検出されたマルウェアなどの情報を表示できます。SIEM 統合をセットアップするには、 [Office 365 アクティビティ管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d49a3-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence and Advanced Threat Protection with your SIEM server. SIEM integration enables you to view information, such as malware detected by Office 365 Advanced Protection and Threat Intelligence, in your SIEM server reports. To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="d49a3-p102">office 365 Activity Management API は、組織の office 365 および Azure Active Directory のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得します。[Office 365 advanced threat protection および脅威インテリジェンススキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)は、脅威インテリジェンスや advanced threat protection で機能するため、組織が高度な脅威保護を備えているが脅威インテリジェンスを持たない (またはその逆) 場合は、SIEM サーバーの統合にも同じ API を使用します。</span><span class="sxs-lookup"><span data-stu-id="d49a3-p102">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs. The [Office 365 Advanced Threat Protection and Threat Intelligence schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Threat Intelligence and/or Advanced Threat Protection, so if your organization has Advanced Threat Protection but not Threat Intelligence (or vice versa), you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="d49a3-p103">SIEM サーバーまたはその他の同様のシステムが監査をポーリングする必要があり**ます。一般的な**ワークロードを検出イベントにアクセスします。詳細については、「 [Office 365 Management api の概要](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d49a3-p103">The SIEM server or other similar system should poll the **audit.general** workload to access detection events. To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d49a3-111">office 365 のグローバル管理者であるか、セキュリティ & コンプライアンスセンターに対してセキュリティ管理者の役割が割り当てられている必要があります。これは、SIEM と office 365 Advanced Threat Protection を統合するための設定です。</span><span class="sxs-lookup"><span data-stu-id="d49a3-111">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="d49a3-p104">Office 365 環境の監査ログを有効にする必要があります。この問題に関するヘルプを表示するには、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d49a3-p104">Audit logging must be turned on for your Office 365 environment. To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d49a3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d49a3-114">Related topics</span></span>

[<span data-ttu-id="d49a3-115">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="d49a3-115">Office 365 Threat Intelligence</span></span>](office-365-ti.md)

[<span data-ttu-id="d49a3-116">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d49a3-116">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="d49a3-117">Office 365 セキュリティ&amp; /コンプライアンスセンターのスマートレポートと洞察</span><span class="sxs-lookup"><span data-stu-id="d49a3-117">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="d49a3-118">Office 365 セキュリティ&amp; /コンプライアンスセンターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="d49a3-118">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

