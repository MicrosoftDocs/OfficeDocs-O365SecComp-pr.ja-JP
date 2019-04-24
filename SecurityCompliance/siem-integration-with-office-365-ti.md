---
title: Office 365 Advanced Threat Protection との SIEM の統合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 03/11/2019
ms.collection:
- M365-security-compliance
description: 組織の SIEM サーバーと office 365 Advanced threat Protection および関連する脅威イベントを office 365 アクティビティ管理 API に統合します。
ms.openlocfilehash: fa9dcda0556684b748068cbe5ee848ba443d7667
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260685"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a><span data-ttu-id="aef43-103">Office 365 Advanced Threat Protection との SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="aef43-103">SIEM integration with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="aef43-104">組織でセキュリティインシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 Advanced Threat Protection を SIEM サーバーに統合することができます。</span><span class="sxs-lookup"><span data-stu-id="aef43-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="aef43-105">SIEM の統合により、SIEM サーバーのレポートにある、Office 365 Advanced Protection によって検出されたマルウェアやフィッシングなどの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="aef43-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="aef43-106">SIEM 統合をセットアップするには、 [Office 365 アクティビティ管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用します。</span><span class="sxs-lookup"><span data-stu-id="aef43-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="aef43-107">office 365 Activity Management API は、組織の office 365 および Azure Active Directory のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="aef43-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="aef43-108">[office 365 advanced threat protection スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)は advanced threat protection と共に動作するため、組織が Office 365 Advanced threat protection プラン1または Plan 2 または Office 365 E5 を使用している場合でも、SIEM サーバー統合に同じ API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aef43-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="aef43-109">SIEM サーバーまたはその他の同様のシステムが監査をポーリングする必要があり**ます。一般的な**ワークロードを検出イベントにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="aef43-109">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="aef43-110">詳細については、「 [Office 365 Management api の概要](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aef43-110">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="aef43-111">また、 **AuditLogRecordType**の次の値は、Office 365 ATP イベントに関連しています。</span><span class="sxs-lookup"><span data-stu-id="aef43-111">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="aef43-112">列挙値: AuditLogRecordType - 型: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="aef43-112">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="aef43-113">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="aef43-113">AuditLogRecordType</span></span>

|<span data-ttu-id="aef43-114">値</span><span class="sxs-lookup"><span data-stu-id="aef43-114">Value</span></span>|<span data-ttu-id="aef43-115">メンバ名</span><span class="sxs-lookup"><span data-stu-id="aef43-115">Member name</span></span>|<span data-ttu-id="aef43-116">説明</span><span class="sxs-lookup"><span data-stu-id="aef43-116">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aef43-117">個</span><span class="sxs-lookup"><span data-stu-id="aef43-117">28</span></span>|<span data-ttu-id="aef43-118">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="aef43-118">ThreatIntelligence</span></span>|<span data-ttu-id="aef43-119">Exchange Online Protection と Office 365 Advanced Threat Protection からのフィッシングとマルウェアのイベント。</span><span class="sxs-lookup"><span data-stu-id="aef43-119">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="aef43-120">41</span><span class="sxs-lookup"><span data-stu-id="aef43-120">41</span></span>|<span data-ttu-id="aef43-121">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="aef43-121">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="aef43-122">ATP の安全なリンクは、Office 365 Advanced Threat Protection からのイベントをブロックする時間とブロックします。</span><span class="sxs-lookup"><span data-stu-id="aef43-122">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="aef43-123">47</span><span class="sxs-lookup"><span data-stu-id="aef43-123">47</span></span>|<span data-ttu-id="aef43-124">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="aef43-124">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="aef43-125">SharePoint Online、OneDrive for business、および Microsoft Teams for Office 365 Advanced Threat Protection のファイルのフィッシングとマルウェアイベント。</span><span class="sxs-lookup"><span data-stu-id="aef43-125">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="aef43-126">office 365 のグローバル管理者であるか、セキュリティ & コンプライアンスセンターに対してセキュリティ管理者の役割が割り当てられている必要があります。これは、SIEM と office 365 Advanced Threat Protection を統合するための設定です。</span><span class="sxs-lookup"><span data-stu-id="aef43-126">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="aef43-127">Office 365 環境の監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aef43-127">Audit logging must be turned on for your Office 365 environment.</span></span> <span data-ttu-id="aef43-128">この問題に関するヘルプを表示するには、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aef43-128">To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="aef43-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="aef43-129">Related topics</span></span>

[<span data-ttu-id="aef43-130">Office 365 の脅威の調査と対応</span><span class="sxs-lookup"><span data-stu-id="aef43-130">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)

[<span data-ttu-id="aef43-131">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="aef43-131">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="aef43-132">Office 365 セキュリティ&amp; /コンプライアンスセンターのスマートレポートと洞察</span><span class="sxs-lookup"><span data-stu-id="aef43-132">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="aef43-133">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="aef43-133">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
