---
title: セキュリティ/コンプライアンス センターと Exchange 管理センターでの DLP の動作
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: セキュリティ & コンプライアンスセンターの DLP が、Exchange 管理センターの DLP およびメールフロールール (トランスポートルール) とどのように連動するかについて説明します。
ms.openlocfilehash: 96fd329ce134b9a9c47b80b846ebb6050c855319
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077563"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="918fe-103">セキュリティ/コンプライアンス センターと Exchange 管理センターでの DLP の動作</span><span class="sxs-lookup"><span data-stu-id="918fe-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="918fe-104">Office 365 では、2つの異なる管理センターでデータ損失防止 (DLP) ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="918fe-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="918fe-105">**セキュリティ _AMP_ コンプライアンスセンター**では、SharePoint、OneDrive、Exchange、および Microsoft Teams のコンテンツを保護するための単一の DLP ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="918fe-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="918fe-106">可能な場合は、ここで DLP ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="918fe-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="918fe-107">詳細については、「 [Security _AMP_ コンプライアンスセンターの DLP](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="918fe-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="918fe-108">**Exchange 管理センター**では、exchange でのみコンテンツを保護できる DLP ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="918fe-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="918fe-109">このポリシーでは、Exchange メールフロールール (トランスポートルールとも呼ばれます) を使用できるので、電子メールの処理に関するその他のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="918fe-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="918fe-110">詳細については、「 [Exchange 管理センターでの DLP](https://go.microsoft.com/fwlink/?linkid=852311)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="918fe-110">For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="918fe-111">これらの管理センターで作成された DLP ポリシーは、並行して機能します。このトピックでは、その方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="918fe-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![セキュリティ/コンプライアンスセンターと Exchange 管理センターの DLP ページ](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="918fe-113">セキュリティ & コンプライアンスセンターの DLP が Exchange 管理センターの DLP およびメールフロールールとどのように連動するか</span><span class="sxs-lookup"><span data-stu-id="918fe-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="918fe-114">セキュリティ & コンプライアンスセンターで DLP ポリシーを作成すると、そのポリシーに含まれるすべての場所にポリシーが展開されます。</span><span class="sxs-lookup"><span data-stu-id="918fe-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="918fe-115">ポリシーに Exchange Online が含まれている場合は、Exchange 管理センターで作成された DLP ポリシーとまったく同じ方法でポリシーが同期され、適用されます。</span><span class="sxs-lookup"><span data-stu-id="918fe-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="918fe-116">Exchange 管理センターで DLP ポリシーを作成した場合、これらのポリシーは、Security & コンプライアンスセンターで作成した電子メールのポリシーと共に引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="918fe-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="918fe-117">ただし、Exchange 管理センターで作成したルールは優先されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="918fe-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="918fe-118">最初にすべての Exchange メールフロールールが処理されてから、Security & コンプライアンスセンターの DLP ルールが処理されます。</span><span class="sxs-lookup"><span data-stu-id="918fe-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="918fe-119">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="918fe-119">This means that:</span></span>
  
- <span data-ttu-id="918fe-120">Exchange メールフロールールによってブロックされているメッセージは、Security & コンプライアンスセンターで作成された DLP ルールによってスキャンされることはありません。</span><span class="sxs-lookup"><span data-stu-id="918fe-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="918fe-121">Exchange メールフロールールによって、外部ユーザーの追加など、Security & コンプライアンスセンターの DLP ポリシーに一致するようにメッセージが変更された場合、DLP ルールによって検出され、必要に応じてポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="918fe-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="918fe-122">また、"stop 処理" アクションを使用する Exchange メールフロールールは、セキュリティ & コンプライアンスセンターでの DLP ルールの処理には影響しません。ただし、これらは処理されます。</span><span class="sxs-lookup"><span data-stu-id="918fe-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="918fe-123">セキュリティ & コンプライアンスセンターおよび Exchange 管理センターのポリシーヒント</span><span class="sxs-lookup"><span data-stu-id="918fe-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="918fe-124">ポリシーヒントは、Exchange 管理センターで作成された DLP ポリシーとメールフロールール、または Security & コンプライアンスセンターで作成された DLP ポリシーによって動作しますが、両方を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="918fe-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="918fe-125">これは、これらのポリシーが異なる場所に格納されているため、ポリシーヒントは1つの場所からのみ描画できるからです。</span><span class="sxs-lookup"><span data-stu-id="918fe-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="918fe-126">Exchange 管理センターでポリシーヒントを構成した場合は、セキュリティ & コンプライアンスセンターで構成するポリシーヒントは、Exchange 管理センターのヒントをオフにするまで、Outlook on the web および Outlook 2013 以降のユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="918fe-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="918fe-127">これにより、セキュリティ & コンプライアンスセンターへの切り替えを選択するまでは、現在の Exchange メールフロールールが引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="918fe-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="918fe-128">ポリシーヒントは1つの場所からしか描画できませんが、セキュリティ & コンプライアンスセンターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="918fe-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

