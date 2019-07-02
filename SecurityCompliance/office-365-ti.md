---
title: Office 365 脅威の調査および対応
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/18/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection の脅威インテリジェンス機能が、組織に対する脅威を調査し、マルウェア、フィッシング、および Office 365 がユーザーに代わって検出したその他の攻撃に対応し、脅威を検索する方法について説明します。切り替える.
ms.openlocfilehash: c8b0815368e80151f8ee55161b9bcbaa98065228
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852811"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="8b91f-103">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="8b91f-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="8b91f-104">Office 365 の脅威の調査と応答機能[Advanced Threat Protection](office-365-atp.md)は、セキュリティアナリストおよび管理者が組織の office 365 ユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8b91f-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="8b91f-105">攻撃を特定し、監視し、理解するための簡単な方法</span><span class="sxs-lookup"><span data-stu-id="8b91f-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="8b91f-106">Exchange Online、SharePoint Online、OneDrive for Business、および Microsoft Teams での脅威への迅速な対応</span><span class="sxs-lookup"><span data-stu-id="8b91f-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="8b91f-107">組織に対する攻撃を防止するために、洞察と知識を提供する</span><span class="sxs-lookup"><span data-stu-id="8b91f-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="8b91f-108">メールベースの重要な脅威に対する自動調査と応答</span><span class="sxs-lookup"><span data-stu-id="8b91f-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="8b91f-109">**Office 365 Advanced Threat protection And threat の調査と応答 (旧称 office 365 Threat 知能) は、office 365 Advanced Threat Protection プラン 2**と、に含まれている追加の脅威保護機能とともに提供されています。[microsoft 365 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、Office 365 E5、office 365 A5 などの特定のサブスクリプション。Office 365 ATP を含まないサブスクリプションが組織にある場合は、ATP をアドオンとして購入する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b91f-109">**Office 365 Advanced Threat Protection and Threat Investigation and Response (previously known as Office 365 Threat Intelligence) are now Office 365 Advanced Threat Protection Plan 2**, along with additional threat protection capabilities included in in certain subscriptions, such as [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 E5, Office 365 A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="8b91f-110">詳細については、「 [office 365 Advanced Threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [Office 365 Advanced threat Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b91f-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="8b91f-111">変更点</span><span class="sxs-lookup"><span data-stu-id="8b91f-111">What's changing?</span></span>

<span data-ttu-id="8b91f-112">以前は、office 365 脅威インテリジェンスは Office 365 E5 などのサブスクリプションに含まれていました。</span><span class="sxs-lookup"><span data-stu-id="8b91f-112">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 E5.</span></span> <span data-ttu-id="8b91f-113">これは、脅威の調査と応答機能が Office 365 Advanced Threat Protection プラン 2 (およびこれは Office 365 E5 に含まれています) の一部であるためです。</span><span class="sxs-lookup"><span data-stu-id="8b91f-113">This is still the case, as threat investigation and response capabilities are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 E5).</span></span> 

<span data-ttu-id="8b91f-114">さらに、Office 365 の脅威インテリジェンスは、一般法人向け Office 365 のアドオンとして購入できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8b91f-114">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="8b91f-115">これらの機能は、office 365 Advanced Threat Protection プラン 2 (および Office 365 Advanced Threat Protection プラン 1) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b91f-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (along with all the features in Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="8b91f-116">詳細については、「 [Office 365 Advanced Threat Protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b91f-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="8b91f-117">これには次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="8b91f-117">Here's what all this means:</span></span>

- <span data-ttu-id="8b91f-118">**組織に Office 365 E5 が既**にインストールされている場合は、既に Advanced Threat Protection プラン2があり、これには脅威調査および応答機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b91f-118">**If your organization already has Office 365 E5**, then you already have Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span>

- <span data-ttu-id="8b91f-119">**以前に組織で office 365 脅威インテリジェンス (office 365 Advanced Threat protection ではない)** が他の office 365 サブスクリプションへのアドオンとして使用されていた場合、Office 365 Advanced Threat protection プラン2が使用されるようになります。これには次のものが含まれます。脅威の調査と応答の機能。</span><span class="sxs-lookup"><span data-stu-id="8b91f-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="8b91f-120">**以前に組織で office 365 Advanced Threat protection (office 365 の脅威インテリジェンスは使用しない)** が他の office 365 サブスクリプションへのアドオンとしてインストールされていた場合は、Office 365 Advanced Threat protection プラン1をご利用になることになります。</span><span class="sxs-lookup"><span data-stu-id="8b91f-120">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="8b91f-121">これには、Office 365 Advanced Threat Protection プラン1が含まれます (ただし、脅威の調査および応答機能は含まれません)。</span><span class="sxs-lookup"><span data-stu-id="8b91f-121">This includes Office 365 Advanced Threat Protection Plan 1, (but not threat investigation and response capabilities).</span></span>

<span data-ttu-id="8b91f-122">詳細については、「 [office 365 Advanced Threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [Office 365 Advanced threat Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b91f-122">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="8b91f-123">脅威の調査と応答機能の概要</span><span class="sxs-lookup"><span data-stu-id="8b91f-123">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="8b91f-124">次のリソースを使用して、Office 365 の脅威の調査および応答機能の詳細と、それを使用して組織内のユーザーをより安全なものにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b91f-124">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="8b91f-125">[脅威の調査と応答の概要](get-started-with-ti.md)(必要な役割に関する情報が含まれます)</span><span class="sxs-lookup"><span data-stu-id="8b91f-125">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="8b91f-126">脅威のトラッカーについて-新知識と注目</span><span class="sxs-lookup"><span data-stu-id="8b91f-126">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="8b91f-127">自動化された調査と応答 (AIR) 機能を使用して時間と労力を節約する</span><span class="sxs-lookup"><span data-stu-id="8b91f-127">Save time and effort with Automated Investigation and Response (AIR) capabilities</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="8b91f-128">脅威エクスプローラー (またはリアルタイムの検出) を使用して、電子メールやファイル内の悪意のあるコンテンツを特定し、調査する</span><span class="sxs-lookup"><span data-stu-id="8b91f-128">Use Threat Explorer (or real-time detections) to identify and investigate malicious content in email and files</span></span>](threat-explorer.md)
    
- [<span data-ttu-id="8b91f-129">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="8b91f-129">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="8b91f-130">アタックシミュレータを使用して攻撃をシミュレートし、ユーザーの意識を向上させる</span><span class="sxs-lookup"><span data-stu-id="8b91f-130">Use Attack Simulator to simulate attacks and increase user awareness</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="8b91f-131">Microsoft Defender Advanced Threat Protection を使用して脅威調査および応答機能を統合する</span><span class="sxs-lookup"><span data-stu-id="8b91f-131">Integrate Threat Investigation and Response capabilities with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="8b91f-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b91f-132">Related topics</span></span>

[<span data-ttu-id="8b91f-133">脅威エクスプローラーのビュー</span><span class="sxs-lookup"><span data-stu-id="8b91f-133">Threat Explorer views</span></span>](threat-explorer-views.md)

[<span data-ttu-id="8b91f-134">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="8b91f-134">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="8b91f-135">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8b91f-135">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="8b91f-136">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="8b91f-136">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
