---
title: セキュリティ & コンプライアンスセンターと Exchange 管理センターの間で DLP がどのように機能するか
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
description: セキュリティ & コンプライアンスセンターの dlp が、Exchange 管理センターの dlp およびメールフロールール (トランスポートルール) とどのように連動するかについて説明します。
ms.openlocfilehash: c20cf5d4e7b83a726b104a57b89f2d8f765d7f16
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341488"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="ea189-103">セキュリティ & コンプライアンスセンターと Exchange 管理センターの間で DLP がどのように機能するか</span><span class="sxs-lookup"><span data-stu-id="ea189-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="ea189-104">Office 365 では、2つの異なる管理センターでデータ損失防止 (DLP) ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ea189-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="ea189-p101">**セキュリティ & コンプライアンスセンター**では、SharePoint、OneDrive、および Exchange のコンテンツを保護するための単一の DLP ポリシーを作成できます。可能な場合は、ここで DLP ポリシーを作成することをお勧めします。詳細については、「 [Security & コンプライアンスセンターの DLP](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea189-p101">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange. When possible, we recommend that you create a DLP policy here. For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="ea189-p102">**exchange 管理センター**では、exchange でのみコンテンツを保護できる DLP ポリシーを作成できます。このポリシーでは、Exchange メールフロールール (トランスポートルールとも呼ばれます) を使用できるので、電子メールの処理に関するその他のオプションがあります。詳細については、「 [Exchange 管理センターでの DLP](https://go.microsoft.com/fwlink/?linkid=852311)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea189-p102">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange. This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email. For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="ea189-111">これらの管理センターで作成された DLP ポリシーは、並行して機能します。このトピックでは、その方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea189-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![セキュリティ/コンプライアンスセンターと Exchange 管理センターの DLP ページ](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="ea189-113">セキュリティ & コンプライアンスセンターの dlp が Exchange 管理センターの dlp およびメールフロールールとどのように連動するか</span><span class="sxs-lookup"><span data-stu-id="ea189-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="ea189-p103">セキュリティ & コンプライアンスセンターで DLP ポリシーを作成すると、そのポリシーに含まれるすべての場所にポリシーが展開されます。ポリシーに exchange Online が含まれている場合は、exchange 管理センターで作成された DLP ポリシーとまったく同じ方法でポリシーが同期され、適用されます。</span><span class="sxs-lookup"><span data-stu-id="ea189-p103">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy. If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="ea189-p104">Exchange 管理センターで DLP ポリシーを作成した場合、これらのポリシーは、Security & コンプライアンスセンターで作成した電子メールのポリシーと共に引き続き機能します。ただし、Exchange 管理センターで作成したルールは優先されることに注意してください。最初にすべての Exchange メールフロールールが処理されてから、Security & コンプライアンスセンターの DLP ルールが処理されます。</span><span class="sxs-lookup"><span data-stu-id="ea189-p104">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center. But note that rules created in the Exchange admin center take precedence. All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="ea189-119">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ea189-119">This means that:</span></span>
  
- <span data-ttu-id="ea189-120">Exchange メールフロールールによってブロックされているメッセージは、Security & コンプライアンスセンターで作成された DLP ルールによってスキャンされることはありません。</span><span class="sxs-lookup"><span data-stu-id="ea189-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="ea189-121">Exchange メールフロールールによって、外部ユーザーの追加など、Security & コンプライアンスセンターの dlp ポリシーに一致するようにメッセージが変更された場合、dlp ルールによって検出され、必要に応じてポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="ea189-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="ea189-122">また、"stop 処理" アクションを使用する Exchange メールフロールールは、セキュリティ & コンプライアンスセンターでの DLP ルールの処理には影響しません。ただし、これらは処理されます。</span><span class="sxs-lookup"><span data-stu-id="ea189-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="ea189-123">セキュリティ & コンプライアンスセンターおよび Exchange 管理センターのポリシーヒント</span><span class="sxs-lookup"><span data-stu-id="ea189-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="ea189-p105">ポリシーヒントは、Exchange 管理センターで作成された dlp ポリシーとメールフロールール、または Security & コンプライアンスセンターで作成された dlp ポリシーによって動作しますが、両方を使用することはできません。これは、これらのポリシーが異なる場所に格納されているため、ポリシーヒントは1つの場所からのみ描画できるからです。</span><span class="sxs-lookup"><span data-stu-id="ea189-p105">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="ea189-p106">exchange 管理センターでポリシーヒントを構成した場合は、セキュリティ & コンプライアンスセンターで構成するポリシーヒントは、exchange 管理センターのヒントをオフにするまで、outlook on the web および outlook 2013 以降のユーザーには表示されません。これにより、セキュリティ & コンプライアンスセンターへの切り替えを選択するまでは、現在の Exchange メールフロールールが引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="ea189-p106">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center. This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="ea189-128">ポリシーヒントは1つの場所からしか描画できませんが、セキュリティ & コンプライアンスセンターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ea189-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

