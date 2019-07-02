---
title: SIEM server と Microsoft 365 の統合
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: '概要: この記事では、SIEM server と Microsoft 365 の統合の概要について説明します。'
ms.openlocfilehash: 9138cbc395b90f50fa60bf545066c17cf26d7edf
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014766"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="48f3f-103">SIEM server と Microsoft 365 のサービスおよびアプリケーションの統合</span><span class="sxs-lookup"><span data-stu-id="48f3f-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="48f3f-104">概要</span><span class="sxs-lookup"><span data-stu-id="48f3f-104">Overview</span></span>

<span data-ttu-id="48f3f-105">組織でセキュリティ情報およびイベント管理 (SIEM) サーバーを使用している場合、または SIEM サーバーを近いうちに購入する予定の場合は、Office 365 E5 を含む Microsoft 365 との統合方法について不思議に思うかもしれません。</span><span class="sxs-lookup"><span data-stu-id="48f3f-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 E5.</span></span> <span data-ttu-id="48f3f-106">SIEM サーバーが必要かどうかは、組織のセキュリティ要件など、さまざまな要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="48f3f-106">Whether you need a SIEM server depends on many factors, such as your organization's security requirements.</span></span> <span data-ttu-id="48f3f-107">Microsoft 365 はさまざまなセキュリティ機能を提供しています。ただし、組織のコンテンツとアプリケーションがオンプレミスとクラウド (ハイブリッドクラウドの展開の場合など) にある場合は、追加の保護のために SIEM サーバーを追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="48f3f-107">Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection.</span></span> <span data-ttu-id="48f3f-108">または、組織が特に厳しいセキュリティ要件を満たしている場合は、SIEM サーバーを環境に追加することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48f3f-108">Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="48f3f-109">SIEM server 統合 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="48f3f-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="48f3f-110">SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからのデータを受信できます。</span><span class="sxs-lookup"><span data-stu-id="48f3f-110">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="48f3f-111">次の表は、SIEM サーバーの入力と、SIEM サーバーの統合の詳細について説明するいくつかの Microsoft 365 サービスとアプリケーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="48f3f-111">The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="48f3f-112">Microsoft 365 サービスまたはアプリケーション</span><span class="sxs-lookup"><span data-stu-id="48f3f-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="48f3f-113">SIEM サーバーの入力</span><span class="sxs-lookup"><span data-stu-id="48f3f-113">SIEM server inputs</span></span> | <span data-ttu-id="48f3f-114">詳細については、リソースを参照してください</span><span class="sxs-lookup"><span data-stu-id="48f3f-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="48f3f-115">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="48f3f-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/><span data-ttu-id="48f3f-116">または</span><span class="sxs-lookup"><span data-stu-id="48f3f-116">or</span></span><br/>[<span data-ttu-id="48f3f-117">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="48f3f-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="48f3f-118">監査ログ</span><span class="sxs-lookup"><span data-stu-id="48f3f-118">Audit logs</span></span> | [<span data-ttu-id="48f3f-119">Office 365 Advanced Threat Protection との SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="48f3f-119">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="48f3f-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48f3f-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="48f3f-121">ログの統合</span><span class="sxs-lookup"><span data-stu-id="48f3f-121">Log integration</span></span> | [<span data-ttu-id="48f3f-122">SIEM と Microsoft Cloud App Security との統合</span><span class="sxs-lookup"><span data-stu-id="48f3f-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="48f3f-123">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="48f3f-123">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="48f3f-124">ログの統合</span><span class="sxs-lookup"><span data-stu-id="48f3f-124">Log integration</span></span> | [<span data-ttu-id="48f3f-125">SIEM ツールに通知を取得する</span><span class="sxs-lookup"><span data-stu-id="48f3f-125">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| <span data-ttu-id="48f3f-126">[Azure セキュリティセンター](https://docs.microsoft.com/azure/security-center/security-center-intro)(脅威の保護と脅威の検出)</span><span class="sxs-lookup"><span data-stu-id="48f3f-126">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="48f3f-127">アラート</span><span class="sxs-lookup"><span data-stu-id="48f3f-127">Alerts</span></span> | [<span data-ttu-id="48f3f-128">SIEM への Azure セキュリティデータのエクスポート-パイプライン構成-プレビュー</span><span class="sxs-lookup"><span data-stu-id="48f3f-128">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[<span data-ttu-id="48f3f-129">Azure Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="48f3f-129">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="48f3f-130">Azure モニター</span><span class="sxs-lookup"><span data-stu-id="48f3f-130">Azure Monitor</span></span> | [<span data-ttu-id="48f3f-131">発行Azure Monitor を使用して SIEM ツールと統合する</span><span class="sxs-lookup"><span data-stu-id="48f3f-131">(Blog) Use Azure Monitor to integrate with SIEM tools</span></span>](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[<span data-ttu-id="48f3f-132">Azure Active Directory Identity Protection</span><span class="sxs-lookup"><span data-stu-id="48f3f-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |<span data-ttu-id="48f3f-133">ログの統合</span><span class="sxs-lookup"><span data-stu-id="48f3f-133">Log integration</span></span> |[<span data-ttu-id="48f3f-134">Microsoft Graph Security API の警告と SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="48f3f-134">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="48f3f-135">監査ログを有効にする必要がある</span><span class="sxs-lookup"><span data-stu-id="48f3f-135">Audit logging must be turned on</span></span>

<span data-ttu-id="48f3f-136">SIEM サーバーの統合を構成する前に、監査ログが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="48f3f-136">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="48f3f-137">SharePoint Online、OneDrive for Business、および Azure Active Directory で[は、セキュリティ & コンプライアンスセンターで監査ログが有効になっ](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)ています。</span><span class="sxs-lookup"><span data-stu-id="48f3f-137">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="48f3f-138">Exchange Online で[は、Windows PowerShell を使用して監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)します。</span><span class="sxs-lookup"><span data-stu-id="48f3f-138">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="48f3f-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="48f3f-139">See Also</span></span>

[<span data-ttu-id="48f3f-140">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="48f3f-140">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="48f3f-141">クラウド導入のテスト ラボ ガイド (TLG)</span><span class="sxs-lookup"><span data-stu-id="48f3f-141">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


