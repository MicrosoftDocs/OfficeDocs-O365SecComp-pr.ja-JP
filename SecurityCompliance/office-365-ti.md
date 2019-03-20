---
title: Office 365 の脅威の調査と対応
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/09/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: office 365 Advanced threat Protection の脅威インテリジェンス機能が、組織に対する脅威を調査し、マルウェア、フィッシング、および office 365 がユーザーに代わって検出したその他の攻撃に対応し、脅威を検索する方法について説明します。切り替える.
ms.openlocfilehash: 3d7bc40c4d5bec0c218adf093655cbbccde07ff9
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693506"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="b1152-103">Office 365 の脅威の調査と対応</span><span class="sxs-lookup"><span data-stu-id="b1152-103">Office 365 Threat Investigation and Response</span></span>

<span data-ttu-id="b1152-104">Office 365 の脅威の調査と応答機能[Advanced Threat Protection](office-365-atp.md)は、セキュリティアナリストおよび管理者が組織の office 365 ユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b1152-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="b1152-105">攻撃を特定し、監視し、理解するための簡単な方法</span><span class="sxs-lookup"><span data-stu-id="b1152-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="b1152-106">Exchange online、SharePoint Online、OneDrive for business、および Microsoft Teams での脅威への迅速な対応</span><span class="sxs-lookup"><span data-stu-id="b1152-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="b1152-107">組織に対する攻撃を防止するために、洞察と知識を提供する</span><span class="sxs-lookup"><span data-stu-id="b1152-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="b1152-108">メールベースの重要な脅威に対する自動調査と応答</span><span class="sxs-lookup"><span data-stu-id="b1152-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b1152-109">**office 365 advanced threat protection and threat の調査と応答 (旧称 office 365 Threat 知能) は、office 365 Advanced threat protection プラン 2**と、に含まれている追加の脅威保護機能とともに提供されています。[microsoft 365 enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、office 365 Enterprise E5、office 365 エデュケーション A5 などの特定のサブスクリプション。Office 365 atp を含まないサブスクリプションが組織にある場合は、atp をアドオンとして購入する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1152-109">**Office 365 Advanced Threat Protection and Threat Investigation and Response (previously known as Office 365 Threat Intelligence) are now Office 365 Advanced Threat Protection Plan 2**, along with additional threat protection capabilities included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="b1152-110">詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1152-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="b1152-111">変更点</span><span class="sxs-lookup"><span data-stu-id="b1152-111">What's changing?</span></span>

<span data-ttu-id="b1152-112">以前は、office 365 脅威インテリジェンスは office 365 Enterprise E5 などのサブスクリプションに含まれていました。</span><span class="sxs-lookup"><span data-stu-id="b1152-112">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 Enterprise E5.</span></span> <span data-ttu-id="b1152-113">これは、脅威の調査と応答機能が office 365 Advanced threat Protection プラン 2 (およびこれは office 365 Enterprise E5 に含まれています) の一部であるためです。</span><span class="sxs-lookup"><span data-stu-id="b1152-113">This is still the case, as threat investigation and response capabilities are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="b1152-114">さらに、office 365 の脅威インテリジェンスは、一般法人向け office 365 のアドオンとして購入できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b1152-114">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="b1152-115">これらの機能は、office 365 advanced threat protection プラン 2 (および office 365 advanced threat protection プラン 1) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1152-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (along with all the features in Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="b1152-116">詳細については、「 [Office 365 Advanced Threat Protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1152-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="b1152-117">これには次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="b1152-117">Here's what all this means:</span></span>

- <span data-ttu-id="b1152-118">**組織に Office 365 Enterprise E5 が既**にインストールされている場合は、既に Advanced threat Protection プラン2があり、これには脅威調査および応答機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b1152-118">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span>

- <span data-ttu-id="b1152-119">**以前に組織で office 365 脅威インテリジェンス (office 365 Advanced threat protection ではない)** が他の office 365 サブスクリプションへのアドオンとして使用されていた場合、office 365 advanced threat protection プラン2が使用されるようになります。これには次のものが含まれます。脅威の調査と応答の機能。</span><span class="sxs-lookup"><span data-stu-id="b1152-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="b1152-120">**以前に組織で office 365 advanced threat protection (office 365 脅威インテリジェンスではない)** が、他の office 365 サブスクリプションへのアドオンとして既に存在していた場合は、office 365 advanced threat protection プラン1が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b1152-120">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="b1152-121">これには、Office 365 Advanced threat Protection プラン1が含まれます (ただし、脅威の調査および応答機能は含まれません)。</span><span class="sxs-lookup"><span data-stu-id="b1152-121">This includes Office 365 Advanced Threat Protection Plan 1, (but not threat investigation and response capabilities).</span></span>

<span data-ttu-id="b1152-122">詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1152-122">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="b1152-123">脅威の調査と応答機能の概要</span><span class="sxs-lookup"><span data-stu-id="b1152-123">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="b1152-124">次のリソースを使用して、Office 365 の脅威の調査および応答機能の詳細と、それを使用して組織内のユーザーをより安全なものにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1152-124">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="b1152-125">[脅威の調査と応答の概要](get-started-with-ti.md)(必要な役割に関する情報が含まれます)</span><span class="sxs-lookup"><span data-stu-id="b1152-125">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="b1152-126">脅威のトラッカーについて-新知識と注目</span><span class="sxs-lookup"><span data-stu-id="b1152-126">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="b1152-127">配信された悪意のある電子メールを検索して調査する</span><span class="sxs-lookup"><span data-stu-id="b1152-127">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="b1152-128">アタックシミュレータを使用する</span><span class="sxs-lookup"><span data-stu-id="b1152-128">Use Attack Simulator</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="b1152-129">脅威の調査と応答を Windows Defender Advanced threat Protection と統合する</span><span class="sxs-lookup"><span data-stu-id="b1152-129">Integrate Threat Investigation and Response with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="b1152-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1152-130">Related topics</span></span>

[<span data-ttu-id="b1152-131">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="b1152-131">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="b1152-132">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b1152-132">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="b1152-133">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b1152-133">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
