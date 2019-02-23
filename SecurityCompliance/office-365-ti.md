---
title: Office 365 脅威インテリジェンス
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection: M365-security-compliance
description: Advanced threat Protection の脅威インテリジェンス機能が組織との脅威を調査し、マルウェア、フィッシング、および Office 365 によって検出されたその他の攻撃に対応し、脅威指標を検索する方法について説明します。
ms.openlocfilehash: a55a17bae141c394ba01e1526615c5c1687340a2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216557"
---
# <a name="office-365-threat-intelligence"></a><span data-ttu-id="71bae-103">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="71bae-103">Office 365 Threat Intelligence</span></span>

<span data-ttu-id="71bae-104">office 365 の脅威インテリジェンス機能 Advanced threat Protection は、セキュリティアナリストおよび管理者が組織の Office 365 ユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="71bae-104">Threat intelligence capabilities in Office 365 Advanced Threat Protection help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="71bae-105">攻撃を特定し、監視し、理解するための簡単な方法</span><span class="sxs-lookup"><span data-stu-id="71bae-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="71bae-106">Exchange online および SharePoint online での脅威への迅速な対応</span><span class="sxs-lookup"><span data-stu-id="71bae-106">Helping to quickly address threats in Exchange Online and SharePoint Online</span></span>
    
3. <span data-ttu-id="71bae-107">組織に対する攻撃を防止するために、洞察と知識を提供する</span><span class="sxs-lookup"><span data-stu-id="71bae-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="71bae-p101">**脅威インテリジェンスが Office 365 Advanced Threat Protection プラン2に**含まれるようになりました。これは、 [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、office 365 Enterprise E5、office 365 など、特定のサブスクリプションに含まれています。教育用 A5、その他Office 365 atp を含まないサブスクリプションが組織にある場合は、atp をアドオンとして購入する可能性があります。詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71bae-p101">**Threat Intelligence is now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="71bae-110">変更点</span><span class="sxs-lookup"><span data-stu-id="71bae-110">What's changing?</span></span>

<span data-ttu-id="71bae-p102">以前は、office 365 脅威インテリジェンスは office 365 Enterprise E5 などのサブスクリプションに含まれていました。脅威インテリジェンス機能は office 365 Advanced Threat Protection プラン2の一部になっていますが (これは office 365 Enterprise E5 に含まれています)、これは依然として当てはまります。</span><span class="sxs-lookup"><span data-stu-id="71bae-p102">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 Enterprise E5. This is still the case, although Threat Intelligence features are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="71bae-p103">さらに、office 365 の脅威インテリジェンスは、一般法人向け office 365 のアドオンとして購入できるようになりました。現在、脅威インテリジェンスは Office 365 Advanced Threat Protection プラン2に含まれています。詳細については、「 [Office 365 Advanced Threat Protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71bae-p103">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers. Now, Threat Intelligence is included in Office 365 Advanced Threat Protection Plan 2. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="71bae-116">これには次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="71bae-116">Here's what all this means:</span></span>

- <span data-ttu-id="71bae-117">**組織に Office 365 Enterprise E5 が既**にインストールされている場合は、既に Advanced threat Protection プラン2があります。これには脅威インテリジェンス機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71bae-117">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes Threat Intelligence capabilities.</span></span>

- <span data-ttu-id="71bae-p104">**以前に組織が office 365 の脅威インテリジェンス (office 365 Advanced threat protection ではない)** を別の office 365 サブスクリプションへのアドオンとして使用していた場合は、office 365 advanced threat protection プラン2が使用されます。これには、高度な脅威保護と脅威インテリジェンス機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71bae-p104">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 2. This includes Advanced Threat Protection and Threat Intelligence capabilities.</span></span> 

- <span data-ttu-id="71bae-p105">**以前に組織で office 365 advanced threat protection (office 365 脅威インテリジェンスではない)** が、他の office 365 サブスクリプションへのアドオンとして既に存在していた場合は、office 365 advanced threat protection プラン1が使用されます。これには、高度な脅威保護 (ただし、脅威インテリジェンス機能ではない) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71bae-p105">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 1. This includes Advanced Threat Protection (but not Threat Intelligence capabilities).</span></span>

<span data-ttu-id="71bae-122">詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71bae-122">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-intelligence-capabilities"></a><span data-ttu-id="71bae-123">脅威インテリジェンス機能の概要</span><span class="sxs-lookup"><span data-stu-id="71bae-123">Get started with threat intelligence capabilities</span></span>

<span data-ttu-id="71bae-124">脅威インテリジェンスの詳細と、それを使用して組織内のユーザーをより安全なものにする方法については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71bae-124">Use the following resources to learn more about threat intelligence, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="71bae-125">[脅威インテリジェンスの概要](get-started-with-ti.md)(必要な役割に関する情報が含まれます)</span><span class="sxs-lookup"><span data-stu-id="71bae-125">[Get started with Threat Intelligence](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="71bae-126">脅威のトラッカーについて-新知識と注目</span><span class="sxs-lookup"><span data-stu-id="71bae-126">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="71bae-127">配信された悪意のある電子メールを検索して調査する</span><span class="sxs-lookup"><span data-stu-id="71bae-127">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="71bae-128">アタックシミュレータを使用する</span><span class="sxs-lookup"><span data-stu-id="71bae-128">Use Attack Simulator</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="71bae-129">Windows Defender Advanced Threat Protection と脅威インテリジェンスを統合する</span><span class="sxs-lookup"><span data-stu-id="71bae-129">Integrate Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="71bae-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="71bae-130">Related topics</span></span>

[<span data-ttu-id="71bae-131">Office 365 での脅威からの保護</span><span class="sxs-lookup"><span data-stu-id="71bae-131">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="71bae-132">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="71bae-132">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="71bae-133">Office 365 セキュリティ&amp; /コンプライアンスセンターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="71bae-133">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

