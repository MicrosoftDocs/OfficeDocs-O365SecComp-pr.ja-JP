---
title: SIEM server と Microsoft 365 の統合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: '概要: この記事では、SIEM server と Microsoft 365 の統合の概要について説明します。'
ms.openlocfilehash: 3f906fb082ec2c1a026940d2b5701a3d1fbec393
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357498"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="a98fc-103">SIEM server と Microsoft 365 のサービスおよびアプリケーションの統合</span><span class="sxs-lookup"><span data-stu-id="a98fc-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="a98fc-104">概要</span><span class="sxs-lookup"><span data-stu-id="a98fc-104">Overview</span></span>

<span data-ttu-id="a98fc-p101">組織でセキュリティ情報およびイベント管理 (SIEM) サーバーを使用している場合、または SIEM サーバーを近いうちに購入する予定の場合は、Office 365 Enterprise を含む Microsoft 365 との統合方法を疑問に思うかもしれません。SIEM サーバーが必要かどうかは、組織のセキュリティ要件など、さまざまな要因によって異なります。Microsoft 365 はさまざまなセキュリティ機能を提供しています。ただし、組織のコンテンツとアプリケーションがオンプレミスとクラウド (ハイブリッドクラウドの展開の場合など) にある場合は、追加の保護のために SIEM サーバーを追加することを検討してください。または、組織が特に厳しいセキュリティ要件を満たしている場合は、SIEM サーバーを環境に追加することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a98fc-p101">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 Enterprise. Whether you need a SIEM server depends on many factors, such as your organization's security requirements. Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection. Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="a98fc-109">SIEM server 統合 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a98fc-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="a98fc-p102">SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからのデータを受信できます。次の表は、SIEM サーバーの入力と、SIEM サーバーの統合の詳細について説明するいくつかの Microsoft 365 サービスとアプリケーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="a98fc-p102">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications. The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="a98fc-112">Microsoft 365 サービスまたはアプリケーション</span><span class="sxs-lookup"><span data-stu-id="a98fc-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="a98fc-113">SIEM サーバーの入力</span><span class="sxs-lookup"><span data-stu-id="a98fc-113">SIEM server inputs</span></span> | <span data-ttu-id="a98fc-114">詳細については、リソースを参照してください</span><span class="sxs-lookup"><span data-stu-id="a98fc-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="a98fc-115">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a98fc-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/>   <span data-ttu-id="a98fc-116">または</span><span class="sxs-lookup"><span data-stu-id="a98fc-116">or</span></span>   <br/>[<span data-ttu-id="a98fc-117">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="a98fc-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="a98fc-118">監査ログ</span><span class="sxs-lookup"><span data-stu-id="a98fc-118">Audit logs</span></span> | [<span data-ttu-id="a98fc-119">SIEM と Office 365 の脅威インテリジェンスおよび Advanced threat Protection との統合</span><span class="sxs-lookup"><span data-stu-id="a98fc-119">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="a98fc-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a98fc-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="a98fc-121">ログの統合</span><span class="sxs-lookup"><span data-stu-id="a98fc-121">Log integration</span></span> | [<span data-ttu-id="a98fc-122">SIEM と Microsoft Cloud App Security との統合</span><span class="sxs-lookup"><span data-stu-id="a98fc-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="a98fc-123">Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a98fc-123">Office 365 Cloud App Security</span></span>](office-365-cas-overview.md) | <span data-ttu-id="a98fc-124">ログの統合</span><span class="sxs-lookup"><span data-stu-id="a98fc-124">Log integration</span></span> | [<span data-ttu-id="a98fc-125">SIEM サーバーと Office 365 Cloud App Security を統合する</span><span class="sxs-lookup"><span data-stu-id="a98fc-125">Integrate your SIEM server with Office 365 Cloud App Security</span></span>](integrate-your-siem-server-with-office-365-cas.md) |
| [<span data-ttu-id="a98fc-126">Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a98fc-126">Windows Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="a98fc-127">ログの統合</span><span class="sxs-lookup"><span data-stu-id="a98fc-127">Log integration</span></span> | [<span data-ttu-id="a98fc-128">SIEM ツールに通知を取得する</span><span class="sxs-lookup"><span data-stu-id="a98fc-128">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| <span data-ttu-id="a98fc-129">[Azure セキュリティセンター](https://docs.microsoft.com/azure/security-center/security-center-intro)(脅威の保護と脅威の検出)</span><span class="sxs-lookup"><span data-stu-id="a98fc-129">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="a98fc-130">アラート</span><span class="sxs-lookup"><span data-stu-id="a98fc-130">Alerts</span></span> | [<span data-ttu-id="a98fc-131">SIEM への Azure セキュリティデータのエクスポート-パイプライン構成-プレビュー</span><span class="sxs-lookup"><span data-stu-id="a98fc-131">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [<span data-ttu-id="a98fc-132">Azure Active Directory id 保護</span><span class="sxs-lookup"><span data-stu-id="a98fc-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | <span data-ttu-id="a98fc-133">監査ログ</span><span class="sxs-lookup"><span data-stu-id="a98fc-133">Audit logs</span></span> | [<span data-ttu-id="a98fc-134">Azure Active Directory 監査ログを統合する</span><span class="sxs-lookup"><span data-stu-id="a98fc-134">Integrate Azure Active Directory audit logs</span></span>](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [<span data-ttu-id="a98fc-135">Azure Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="a98fc-135">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="a98fc-136">ログの統合</span><span class="sxs-lookup"><span data-stu-id="a98fc-136">Log integration</span></span> | [<span data-ttu-id="a98fc-137">ATA SIEM ログリファレンス</span><span class="sxs-lookup"><span data-stu-id="a98fc-137">ATA SIEM log reference</span></span>](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="a98fc-138">監査ログを有効にする必要がある</span><span class="sxs-lookup"><span data-stu-id="a98fc-138">Audit logging must be turned on</span></span>

<span data-ttu-id="a98fc-139">SIEM サーバーの統合を構成する前に、監査ログが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a98fc-139">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="a98fc-140">SharePoint Online、OneDrive for business、および Azure Active Directory で[は、セキュリティ & コンプライアンスセンターで監査ログが有効になっ](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)ています。</span><span class="sxs-lookup"><span data-stu-id="a98fc-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="a98fc-141">Exchange Online で[は、Windows PowerShell を使用して監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)します。</span><span class="sxs-lookup"><span data-stu-id="a98fc-141">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="a98fc-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="a98fc-142">See Also</span></span>

[<span data-ttu-id="a98fc-143">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="a98fc-143">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="a98fc-144">クラウド導入のテスト ラボ ガイド (TLG)</span><span class="sxs-lookup"><span data-stu-id="a98fc-144">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


