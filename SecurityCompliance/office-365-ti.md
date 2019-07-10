---
title: Office 365 脅威の調査および対応
ms.author: deniseb
author: denisebmsft
manager: dansimp
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
ms.openlocfilehash: 7e0ce37b33ea2c019005585fd70107145fbfc8aa
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598083"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="4fafc-103">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="4fafc-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="4fafc-104">Office 365 の脅威の調査と応答機能[Advanced Threat Protection](office-365-atp.md)は、セキュリティアナリストおよび管理者が組織の office 365 ユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4fafc-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="4fafc-105">攻撃を特定し、監視し、理解するための簡単な方法</span><span class="sxs-lookup"><span data-stu-id="4fafc-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="4fafc-106">Exchange Online、SharePoint Online、OneDrive for Business、および Microsoft Teams での脅威への迅速な対応</span><span class="sxs-lookup"><span data-stu-id="4fafc-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="4fafc-107">組織に対する攻撃を防止するために、洞察と知識を提供する</span><span class="sxs-lookup"><span data-stu-id="4fafc-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="4fafc-108">メールベースの重要な脅威に対する自動調査と応答</span><span class="sxs-lookup"><span data-stu-id="4fafc-108">Automated investigation and response for critical email based threats</span></span>
    
 
## <a name="whats-changing"></a><span data-ttu-id="4fafc-109">変更点</span><span class="sxs-lookup"><span data-stu-id="4fafc-109">What's changing?</span></span>

<span data-ttu-id="4fafc-110">以前は、office 365 脅威インテリジェンスは Office 365 E5 などのサブスクリプションに含まれていました。</span><span class="sxs-lookup"><span data-stu-id="4fafc-110">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 E5.</span></span> <span data-ttu-id="4fafc-111">これは、脅威の調査と応答機能が Office 365 Advanced Threat Protection プラン 2 (およびこれは Office 365 E5 に含まれています) の一部であるためです。</span><span class="sxs-lookup"><span data-stu-id="4fafc-111">This is still the case, as threat investigation and response capabilities are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 E5).</span></span> 

<span data-ttu-id="4fafc-112">さらに、Office 365 の脅威インテリジェンスは、一般法人向け Office 365 のアドオンとして購入できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4fafc-112">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="4fafc-113">これらの機能は、office 365 Advanced Threat Protection プラン 2 (および Office 365 Advanced Threat Protection プラン 1) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="4fafc-113">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (along with all the features in Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="4fafc-114">詳細については、「 [Office 365 Advanced Threat Protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fafc-114">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="4fafc-115">これには次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="4fafc-115">Here's what all this means:</span></span>

- <span data-ttu-id="4fafc-116">**組織に Office 365 E5 が既**にインストールされている場合は、既に Advanced Threat Protection プラン2があり、これには脅威調査および応答機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4fafc-116">**If your organization already has Office 365 E5**, then you already have Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span>

- <span data-ttu-id="4fafc-117">**以前に組織で office 365 脅威インテリジェンス (office 365 Advanced Threat protection ではない)** が他の office 365 サブスクリプションへのアドオンとして使用されていた場合、Office 365 Advanced Threat protection プラン2が使用されるようになります。これには次のものが含まれます。脅威の調査と応答の機能。</span><span class="sxs-lookup"><span data-stu-id="4fafc-117">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="4fafc-118">**以前に組織で office 365 Advanced Threat protection (office 365 の脅威インテリジェンスは使用しない)** が他の office 365 サブスクリプションへのアドオンとしてインストールされていた場合は、Office 365 Advanced Threat protection プラン1をご利用になることになります。</span><span class="sxs-lookup"><span data-stu-id="4fafc-118">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="4fafc-119">これには、Office 365 Advanced Threat Protection プラン1が含まれます (ただし、脅威の調査および応答機能は含まれません)。</span><span class="sxs-lookup"><span data-stu-id="4fafc-119">This includes Office 365 Advanced Threat Protection Plan 1, (but not threat investigation and response capabilities).</span></span>

<span data-ttu-id="4fafc-120">詳細については、「 [office 365 Advanced Threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [Office 365 Advanced threat Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fafc-120">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="4fafc-121">脅威の調査と応答機能の概要</span><span class="sxs-lookup"><span data-stu-id="4fafc-121">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="4fafc-122">次のリソースを使用して、Office 365 の脅威の調査および応答機能の詳細と、それを使用して組織内のユーザーをより安全なものにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fafc-122">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="4fafc-123">[脅威の調査と応答の概要](get-started-with-ti.md)(必要な役割に関する情報が含まれます)</span><span class="sxs-lookup"><span data-stu-id="4fafc-123">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="4fafc-124">脅威のトラッカーについて-新知識と注目</span><span class="sxs-lookup"><span data-stu-id="4fafc-124">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="4fafc-125">自動化された調査と応答 (AIR) 機能を使用して時間と労力を節約する</span><span class="sxs-lookup"><span data-stu-id="4fafc-125">Save time and effort with Automated Investigation and Response (AIR) capabilities</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="4fafc-126">脅威エクスプローラー (またはリアルタイムの検出) を使用して、電子メールやファイル内の悪意のあるコンテンツを特定し、調査する</span><span class="sxs-lookup"><span data-stu-id="4fafc-126">Use Threat Explorer (or real-time detections) to identify and investigate malicious content in email and files</span></span>](threat-explorer.md)
    
- [<span data-ttu-id="4fafc-127">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="4fafc-127">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="4fafc-128">アタックシミュレータを使用して攻撃をシミュレートし、ユーザーの意識を向上させる</span><span class="sxs-lookup"><span data-stu-id="4fafc-128">Use Attack Simulator to simulate attacks and increase user awareness</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="4fafc-129">Microsoft Defender Advanced Threat Protection を使用して脅威調査および応答機能を統合する</span><span class="sxs-lookup"><span data-stu-id="4fafc-129">Integrate Threat Investigation and Response capabilities with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="4fafc-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fafc-130">Related topics</span></span>

[<span data-ttu-id="4fafc-131">脅威エクスプローラーのビュー</span><span class="sxs-lookup"><span data-stu-id="4fafc-131">Threat Explorer views</span></span>](threat-explorer-views.md)

[<span data-ttu-id="4fafc-132">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="4fafc-132">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="4fafc-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4fafc-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="4fafc-134">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="4fafc-134">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
