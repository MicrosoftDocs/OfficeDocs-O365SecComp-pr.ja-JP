---
title: SIEM Microsoft 365 とサーバーの統合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- SIEM
description: '概要: は、SIEM Microsoft 365 とサーバーの統合の概要を取得するには、この記事を読みます。'
ms.openlocfilehash: bd512ca6d75928712e3444581a78610a0869123d
ms.sourcegitcommit: 63ed467fc3e1ab1ab9ee122df97c64737169834e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842685"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="c7042-103">SIEM Microsoft 365 のサービスおよびアプリケーションとサーバの統合</span><span class="sxs-lookup"><span data-stu-id="c7042-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="c7042-104">概要</span><span class="sxs-lookup"><span data-stu-id="c7042-104">Overview</span></span>

<span data-ttu-id="c7042-p101">組織が、セキュリティ情報およびイベント管理 (SIEM) サーバーを使用する場合、または SIEM サーバーをすぐに取得することを計画している場合は、する依存関係をすることをどのように統合 Office 365 の企業を含む、Microsoft の 365 です。SIEM サーバーする必要があるかどうかは、組織のセキュリティ要件など、多くの要因によって異なります。Microsoft 365 には、さまざまなセキュリティ機能が用意されています。ただし、組織の設置型とクラウド (ハイブリッド クラウドの展開の場合) のようにコンテンツやアプリケーションが、余分な保護のための SIEM サーバーを追加を検討可能性があります。または、特別、厳格なセキュリティ要件を満たす必要がありますがある場合、は、SIEM サーバーを環境内に追加を検討する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7042-p101">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 Enterprise. Whether you need a SIEM server depends on many factors, such as your organization's security requirements. Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection. Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="c7042-109">SIEM サーバー統合 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c7042-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="c7042-p102">SIEM サーバーは、さまざまな Microsoft 365 サービスとアプリケーションからデータを受信できます。次の表に、いくつかの Microsoft 365 サービスと SIEM サーバーの入力と SIEM サーバ統合の詳細についての参照先のアプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="c7042-p102">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications. The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="c7042-112">Microsoft 365 サービスまたはアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c7042-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="c7042-113">SIEM サーバーの入力</span><span class="sxs-lookup"><span data-stu-id="c7042-113">SIEM server inputs</span></span> | <span data-ttu-id="c7042-114">リソースの詳細</span><span class="sxs-lookup"><span data-stu-id="c7042-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="c7042-115">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c7042-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/>   <span data-ttu-id="c7042-116">または</span><span class="sxs-lookup"><span data-stu-id="c7042-116">or</span></span>   <br/>[<span data-ttu-id="c7042-117">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="c7042-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="c7042-118">監査ログ</span><span class="sxs-lookup"><span data-stu-id="c7042-118">Audit logs</span></span> | [<span data-ttu-id="c7042-119">Office 365 の脅威インテリジェンスと脅威の高度な保護と SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="c7042-119">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="c7042-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c7042-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="c7042-121">ログの統合</span><span class="sxs-lookup"><span data-stu-id="c7042-121">Log integration</span></span> | [<span data-ttu-id="c7042-122">マイクロソフト クラウド アプリケーションのセキュリティと SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="c7042-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="c7042-123">Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c7042-123">Office 365 Cloud App Security</span></span>](office-365-cas-overview.md) | <span data-ttu-id="c7042-124">ログの統合</span><span class="sxs-lookup"><span data-stu-id="c7042-124">Log integration</span></span> | [<span data-ttu-id="c7042-125">SIEM サーバーと Office 365 Cloud App Security を統合する</span><span class="sxs-lookup"><span data-stu-id="c7042-125">Integrate your SIEM server with Office 365 Cloud App Security</span></span>](integrate-your-siem-server-with-office-365-cas.md) |
| [<span data-ttu-id="c7042-126">Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c7042-126">Windows Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="c7042-127">ログの統合</span><span class="sxs-lookup"><span data-stu-id="c7042-127">Log integration</span></span> | [<span data-ttu-id="c7042-128">SIEM ツールに警告をプルします。</span><span class="sxs-lookup"><span data-stu-id="c7042-128">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| <span data-ttu-id="c7042-129">[Azure のセキュリティ センター](https://docs.microsoft.com/azure/security-center/security-center-intro)(脅威保護し、脅威の検出)</span><span class="sxs-lookup"><span data-stu-id="c7042-129">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="c7042-130">警告</span><span class="sxs-lookup"><span data-stu-id="c7042-130">Alerts</span></span> | [<span data-ttu-id="c7042-131">SIEM のパイプラインの構成 - プレビューに azure のセキュリティ データをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c7042-131">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [<span data-ttu-id="c7042-132">Azure Active Directory Id の保護</span><span class="sxs-lookup"><span data-stu-id="c7042-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | <span data-ttu-id="c7042-133">監査ログ</span><span class="sxs-lookup"><span data-stu-id="c7042-133">Audit logs</span></span> | [<span data-ttu-id="c7042-134">Azure Active Directory の監査ログを統合します。</span><span class="sxs-lookup"><span data-stu-id="c7042-134">Integrate Azure Active Directory audit logs</span></span>](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [<span data-ttu-id="c7042-135">Azure の高度な脅威の分析</span><span class="sxs-lookup"><span data-stu-id="c7042-135">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="c7042-136">ログの統合</span><span class="sxs-lookup"><span data-stu-id="c7042-136">Log integration</span></span> | [<span data-ttu-id="c7042-137">ATA SIEM のログの参照</span><span class="sxs-lookup"><span data-stu-id="c7042-137">ATA SIEM log reference</span></span>](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="c7042-138">監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7042-138">Audit logging must be turned on</span></span>

<span data-ttu-id="c7042-139">SIEM サーバー統合を構成する前に監査ログを有効にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7042-139">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="c7042-140">SharePoint、オンライン ビジネス、および、Azure Active Directory の[セキュリティとコンプライアンス ・ センターの監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)するための OneDrive です。</span><span class="sxs-lookup"><span data-stu-id="c7042-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="c7042-141">Exchange オンラインで[Windows PowerShell で監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)します。</span><span class="sxs-lookup"><span data-stu-id="c7042-141">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="c7042-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7042-142">See Also</span></span>

[<span data-ttu-id="c7042-143">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="c7042-143">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="c7042-144">クラウド導入のテスト ラボ ガイド (TLG)</span><span class="sxs-lookup"><span data-stu-id="c7042-144">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


