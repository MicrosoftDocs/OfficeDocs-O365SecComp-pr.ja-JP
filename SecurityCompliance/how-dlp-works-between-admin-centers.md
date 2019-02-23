---
title: セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの間で DLP がどのように機能するか
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: セキュリティ&amp; /コンプライアンスセンターの dlp が、Exchange 管理センターの dlp およびトランスポートルールとどのように連動するかについて説明します。
ms.openlocfilehash: 531a45308594d03dc219f50d989a08236b8b5e20
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215647"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="d6429-103">セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの間で DLP がどのように機能するか</span><span class="sxs-lookup"><span data-stu-id="d6429-103">How DLP works between the Security &amp; Compliance Center and Exchange Admin Center</span></span>

<span data-ttu-id="d6429-104">Office 365 では、2つの異なる管理センターでデータ損失防止 (DLP) ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d6429-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="d6429-p101">\*\* &amp;セキュリティ/コンプライアンスセンター\*\*では、SharePoint、OneDrive、および Exchange のコンテンツを保護するための単一の DLP ポリシーを作成できます。可能な場合は、ここで DLP ポリシーを作成することをお勧めします。詳細については、 [ &amp;セキュリティ/コンプライアンスセンター](data-loss-prevention-policies.md)の「DLP」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6429-p101">In the **Security &amp; Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange. When possible, we recommend that you create a DLP policy here. For more information, see [DLP in the Security &amp; Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="d6429-p102">**exchange 管理センター**では、exchange でのみコンテンツを保護できる DLP ポリシーを作成できます。このポリシーでは、Exchange トランスポートルールを使用できます。そのため、電子メールの処理に固有のオプションがあります。詳細については、「 [Exchange 管理センターでの DLP](https://go.microsoft.com/fwlink/?linkid=852311)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6429-p102">In the **Exchange Admin Center**, you can create a DLP policy to help protect content only in Exchange. This policy can use Exchange transport rules, so it has more options specific to handling email. For more information, see [DLP in the Exchange Admin Center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="d6429-111">これらの管理センターで作成された DLP ポリシーは、並行して機能します。このトピックでは、その方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6429-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![セキュリティ/コンプライアンスセンターと Exchange 管理センターの DLP ページ](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a><span data-ttu-id="d6429-113">セキュリティ&amp; /コンプライアンスセンターの dlp が Exchange 管理センターの dlp およびトランスポートルールとどのように連動するか</span><span class="sxs-lookup"><span data-stu-id="d6429-113">How DLP in the Security &amp; Compliance Center works with DLP and transport rules in the Exchange Admin Center</span></span>

<span data-ttu-id="d6429-p103">セキュリティ&amp; /コンプライアンスセンターで DLP ポリシーを作成すると、ポリシーに含まれるすべての場所にポリシーが展開されます。ポリシーに exchange Online が含まれている場合は、exchange 管理センターで作成された DLP ポリシーとまったく同じ方法でポリシーが同期され、適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6429-p103">After you create a DLP policy in the Security &amp; Compliance Center, the policy is deployed to all of the locations included in the policy. If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="d6429-p104">Exchange 管理センターで DLP ポリシーを作成した場合、これらのポリシーは、セキュリティ&amp;コンプライアンスセンターで作成した電子メールのポリシーと共に引き続き機能します。ただし、Exchange 管理センターで作成したルールは優先されることに注意してください。最初にすべての Exchange トランスポートルールが処理され、次にセキュリティ&amp;コンプライアンスセンターの DLP ルールが処理されます。</span><span class="sxs-lookup"><span data-stu-id="d6429-p104">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security &amp; Compliance Center. But note that rules created in the Exchange admin center take precedence. All Exchange transport rules are processed first, and then the DLP rules from the Security &amp; Compliance Center are processed.</span></span>
  
<span data-ttu-id="d6429-119">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d6429-119">This means that:</span></span>
  
- <span data-ttu-id="d6429-120">Exchange トランスポートルールによってブロックされているメッセージは、セキュリティ&amp;コンプライアンスセンターで作成された DLP ルールによってスキャンされません。</span><span class="sxs-lookup"><span data-stu-id="d6429-120">Messages that are blocked by Exchange transport rules won't get scanned by DLP rules created in the Security &amp; Compliance Center.</span></span>
    
- <span data-ttu-id="d6429-121">Exchange トランスポートルールによって、外部ユーザーの追加など、セキュリティ&amp;コンプライアンスセンターの dlp ポリシーに一致するようにメッセージが変更された場合、dlp ルールによって検出され、必要に応じてポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6429-121">If an Exchange transport rule modifies a message in a way that causes it to match a DLP policy in the Security &amp; Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="d6429-122">また、"stop 処理" アクションを使用する Exchange トランスポートルールは、セキュリティ&amp;コンプライアンスセンターの DLP ルールの処理には影響しません。ただし、処理は続行されます。</span><span class="sxs-lookup"><span data-stu-id="d6429-122">Also note that Exchange transport rules that use the "stop processing" action don't affect the processing of DLP rules in the Security &amp; Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="d6429-123">セキュリティ&amp; /コンプライアンスセンターおよび Exchange 管理センターのポリシーヒント</span><span class="sxs-lookup"><span data-stu-id="d6429-123">Policy tips in the Security &amp; Compliance Center vs. the Exchange Admin Center</span></span>

<span data-ttu-id="d6429-p105">ポリシーヒントは、Exchange 管理センターで作成された dlp ポリシーとメールフロールール、またはセキュリティ&amp; /コンプライアンスセンターで作成された dlp ポリシーによって機能しますが、両方を使用することはできません。これは、これらのポリシーが異なる場所に格納されているため、ポリシーヒントは1つの場所からのみ描画できるからです。</span><span class="sxs-lookup"><span data-stu-id="d6429-p105">Policy tips can work either with DLP policies and mail flow rules created in the Exchange Admin Center, or with DLP policies created in the Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="d6429-p106">exchange 管理センターでポリシーヒントを構成した場合は、セキュリティ&amp; /コンプライアンスセンターで設定したポリシーヒントは、outlook on the web および outlook 2013 以降のユーザーには表示されません。そのためには、exchange 管理センターのヒントをオフにします。これにより、セキュリティ&amp;コンプライアンスセンターへの切り替えを選択するまでは、現在の Exchange トランスポートルールが引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="d6429-p106">If you've configured policy tips in the Exchange Admin Center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange Admin Center. This ensures that your current Exchange transport rules will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="d6429-128">ポリシーヒントは1つの場所からしか描画できませんが、セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d6429-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange Admin Center.</span></span>
  

