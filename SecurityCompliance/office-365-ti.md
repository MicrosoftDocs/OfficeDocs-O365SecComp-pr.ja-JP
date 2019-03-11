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
description: Advanced threat Protection の脅威インテリジェンス機能が組織との脅威を調査し、マルウェア、フィッシング、および Office 365 によって検出されたその他の攻撃に対応し、脅威指標を検索する方法について説明します。
ms.openlocfilehash: 1d076ed6ca48b8423ad92d5ea71bd87167b8519a
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524001"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="1aa5a-103">Office 365 の脅威の調査と対応</span><span class="sxs-lookup"><span data-stu-id="1aa5a-103">Office 365 Threat Investigation and Response</span></span>

<span data-ttu-id="1aa5a-104">Office 365 の脅威の調査と応答機能 Advanced Threat Protection は、セキュリティアナリストおよび管理者が組織の office 365 ユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-104">Threat investigation and response capabilities in Office 365 Advanced Threat Protection help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="1aa5a-105">攻撃を特定し、監視し、理解するための簡単な方法</span><span class="sxs-lookup"><span data-stu-id="1aa5a-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="1aa5a-106">Exchange online、SharePoint Online、ビジネスおよび Microsoft Teams の1台のドライブでの脅威への迅速な対応</span><span class="sxs-lookup"><span data-stu-id="1aa5a-106">Helping to quickly address threats in Exchange Online, SharePoint Online, One Drive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="1aa5a-107">組織に対する攻撃を防止するために、洞察と知識を提供する</span><span class="sxs-lookup"><span data-stu-id="1aa5a-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="1aa5a-108">メールベースの重要な脅威に対する自動調査と応答</span><span class="sxs-lookup"><span data-stu-id="1aa5a-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1aa5a-109">office **365 の脅威の調査と応答 (旧称 office 365 THreat 知能) は、office 365 Advanced THreat Protection プラン 2**( [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)などの特定のサブスクリプションに含まれています) の一部になっています。[Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、office 365 Enterprise E5、Office 365 エデュケーション A5 など。Office 365 atp を含まないサブスクリプションが組織にある場合は、atp をアドオンとして購入する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-109">**Office 365 THreat Investigation and Responses (previously known as Office 365 Threat Intelligence) is now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="1aa5a-110">詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="1aa5a-111">変更点</span><span class="sxs-lookup"><span data-stu-id="1aa5a-111">What's changing?</span></span>

<span data-ttu-id="1aa5a-112">以前は、office 365 の脅威調査と応答機能は、office 365 Enterprise E5 などのサブスクリプションに含まれていました。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-112">Formerly, Office 365 Threat investigation and responses capabilities were included in subscriptions, such as Office 365 Enterprise E5.</span></span> <span data-ttu-id="1aa5a-113">これは依然としていますが、これらの機能は office 365 Advanced Threat Protection プラン2の一部になっています (これは office 365 Enterprise E5 に含まれています)。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-113">This is still the case, and now these features are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="1aa5a-114">さらに、office 365 の脅威の調査と応答の capbailities は、一般法人向け office 365 のアドオンとして購入できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-114">In addition, Office 365 Threat investigation and response capbailities were formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="1aa5a-115">これらの機能は office 365 advanced threat protection プラン2に含まれています (これには office 365 advanced threat protection プラン 1) も含まれています。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (which also includes Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="1aa5a-116">詳細については、「 [Office 365 Advanced Threat Protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="1aa5a-117">これには次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-117">Here's what all this means:</span></span>

- <span data-ttu-id="1aa5a-118">**組織に Office 365 Enterprise E5 が既**にインストールされている場合は、既に Advanced threat Protection プラン2があり、これには脅威調査および応答機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-118">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes Threat investigation and response capabilities.</span></span>

- <span data-ttu-id="1aa5a-119">**以前に組織が office 365 の脅威インテリジェンス (office 365 Advanced threat protection ではない)** を別の office 365 サブスクリプションへのアドオンとして使用していた場合は、office 365 advanced threat protection プラン2が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="1aa5a-120">これには、高度な脅威保護の計画1および脅威の調査と応答の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-120">This includes Advanced Threat Protection Plan 1 and Threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="1aa5a-121">**以前に組織で office 365 advanced threat protection (office 365 脅威インテリジェンスではない)** が、他の office 365 サブスクリプションへのアドオンとして既に存在していた場合は、office 365 advanced threat protection プラン1が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-121">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="1aa5a-122">これには、高度な脅威保護 (ただし、脅威 investigaiton および応答機能は含まれません) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-122">This includes Advanced Threat Protection (but not Threat investigaiton and response capabilities).</span></span>

<span data-ttu-id="1aa5a-123">詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-123">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigaiton-and-response-capabilities"></a><span data-ttu-id="1aa5a-124">脅威 investigaiton および応答機能の概要</span><span class="sxs-lookup"><span data-stu-id="1aa5a-124">Get started with threat investigaiton and response capabilities</span></span>

<span data-ttu-id="1aa5a-125">次のリソースを使用して、Office 365 の脅威の調査および応答機能の詳細と、それを使用して組織内のユーザーをより安全なものにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1aa5a-125">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="1aa5a-126">[脅威の調査と応答の概要](get-started-with-ti.md)(必要な役割に関する情報が含まれます)</span><span class="sxs-lookup"><span data-stu-id="1aa5a-126">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="1aa5a-127">脅威のトラッカーについて-新知識と注目</span><span class="sxs-lookup"><span data-stu-id="1aa5a-127">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="1aa5a-128">配信された悪意のある電子メールを検索して調査する</span><span class="sxs-lookup"><span data-stu-id="1aa5a-128">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="1aa5a-129">アタックシミュレータを使用する</span><span class="sxs-lookup"><span data-stu-id="1aa5a-129">Use Attack Simulator</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="1aa5a-130">脅威の調査と応答を Windows Defender Advanced threat Protection と統合する</span><span class="sxs-lookup"><span data-stu-id="1aa5a-130">Integrate Threat Investigation and Response with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="1aa5a-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="1aa5a-131">Related topics</span></span>

[<span data-ttu-id="1aa5a-132">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="1aa5a-132">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="1aa5a-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1aa5a-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="1aa5a-134">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1aa5a-134">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 