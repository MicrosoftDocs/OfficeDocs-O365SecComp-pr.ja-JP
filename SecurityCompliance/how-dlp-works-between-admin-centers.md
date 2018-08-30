---
title: セキュリティと DLP のしくみ&amp;コンプライアンス センターおよび Exchange 管理センター
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 学習方法セキュリティの DLP&amp;コンプライアンス センターは、Exchange 管理センターで DLP とトランスポートの規則で動作します。
ms.openlocfilehash: bc7494f504c2c0ffa668562d6e64b9f29992e24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532426"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="63786-103">セキュリティと DLP のしくみ&amp;コンプライアンス センターおよび Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="63786-103">How DLP works between the Security &amp; Compliance Center and Exchange Admin Center</span></span>

<span data-ttu-id="63786-104">、Office 365 では、2 つの異なる管理センターでのデータ損失防止 (DLP) ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="63786-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="63786-p101">**セキュリティ&amp;コンプライアンス センター**、SharePoint、OneDrive、および Exchange のコンテンツを保護するために 1 つの DLP ポリシーを作成することができます。可能であれば、ここでは、DLP ポリシーを作成することをお勧めします。詳細についてを参照してください[セキュリティの DLP&amp;コンプライアンス センター](data-loss-prevention-policies.md)です。</span><span class="sxs-lookup"><span data-stu-id="63786-p101">In the **Security &amp; Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange. When possible, we recommend that you create a DLP policy here. For more information, see [DLP in the Security &amp; Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="63786-p102">**Exchange 管理センター**では、Exchange でのみコンテンツを保護するための DLP ポリシーを作成できます。このポリシーは、電子メールを処理する特定その他のオプションがあるために、Exchange のトランスポート ルールを使用できます。詳細については、 [Exchange 管理センターで DLP](https://go.microsoft.com/fwlink/?linkid=852311)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63786-p102">In the **Exchange Admin Center**, you can create a DLP policy to help protect content only in Exchange. This policy can use Exchange transport rules, so it has more options specific to handling email. For more information, see [DLP in the Exchange Admin Center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="63786-111">DLP ポリシー センターの機能を並べてこのトピックで説明をこれらの管理ツールで作成する方法です。</span><span class="sxs-lookup"><span data-stu-id="63786-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![セキュリティおよびコンプライアンス センターや Exchange 管理センターで DLP のページ](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a><span data-ttu-id="63786-113">どのようにセキュリティの DLP&amp;コンプライアンス センターは、Exchange 管理センターでの DLP とトランスポート ルールと連携</span><span class="sxs-lookup"><span data-stu-id="63786-113">How DLP in the Security &amp; Compliance Center works with DLP and transport rules in the Exchange Admin Center</span></span>

<span data-ttu-id="63786-p103">セキュリティで DLP ポリシーを作成した後&amp;コンプライアンス センターでは、ポリシーのすべてのポリシーに含まれている場所に配置します。Exchange Online にポリシーが含まれている場合ポリシーのある同期し、Exchange 管理センターで作成した DLP ポリシーとまったく同じ方法で適用されます。</span><span class="sxs-lookup"><span data-stu-id="63786-p103">After you create a DLP policy in the Security &amp; Compliance Center, the policy is deployed to all of the locations included in the policy. If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="63786-p104">DLP ポリシーを作成したら、Exchange 管理センターで、これらのポリシーが引き続きすべてのポリシー、セキュリティで作成した電子メールの密接に共同作業&amp;コンプライアンス センターです。Exchange 管理センターで作成されたルールの優先順位に注意してください。すべての Exchange トランスポート ルールが最初に処理し、セキュリティの規則を DLP&amp;コンプライアンス センターで処理されます。</span><span class="sxs-lookup"><span data-stu-id="63786-p104">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security &amp; Compliance Center. But note that rules created in the Exchange admin center take precedence. All Exchange transport rules are processed first, and then the DLP rules from the Security &amp; Compliance Center are processed.</span></span>
  
<span data-ttu-id="63786-119">これは、ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="63786-119">This means that:</span></span>
  
- <span data-ttu-id="63786-120">Exchange トランスポート ルールによってブロックされているメッセージは DLP ルールの作成で、セキュリティでスキャンされることはありません&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="63786-120">Messages that are blocked by Exchange transport rules won't get scanned by DLP rules created in the Security &amp; Compliance Center.</span></span>
    
- <span data-ttu-id="63786-121">Exchange トランスポート ルールが、セキュリティでは、DLP ポリシーに一致するようにメッセージを変更するかどうかは&amp;コンプライアンス センター]-[外部のユーザーには、DLP の規則はこれを検出し、必要に応じてポリシーを適用するを追加するなど。</span><span class="sxs-lookup"><span data-stu-id="63786-121">If an Exchange transport rule modifies a message in a way that causes it to match a DLP policy in the Security &amp; Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="63786-122">」の処理を停止する] アクションを使用するトランスポート ルールを Exchange が DLP の処理に影響しないが、セキュリティの規則も&amp;コンプライアンス センター - それらはまだ処理します。</span><span class="sxs-lookup"><span data-stu-id="63786-122">Also note that Exchange transport rules that use the "stop processing" action don't affect the processing of DLP rules in the Security &amp; Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="63786-123">ポリシーのセキュリティのヒント&amp;Exchange 管理センターとコンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="63786-123">Policy tips in the Security &amp; Compliance Center vs. the Exchange Admin Center</span></span>

<span data-ttu-id="63786-p105">ポリシー ヒントは DLP ポリシーのいずれかで作業し、メール フロー ルールが Exchange 管理センターで、またはセキュリティで作成した DLP ポリシーを作成した&amp;コンプライアンス ・ センターが、両方です。これは、これらのポリシーが別の場所に格納されているポリシーのヒントは、1 つの場所からのみ描画できるためです。</span><span class="sxs-lookup"><span data-stu-id="63786-p105">Policy tips can work either with DLP policies and mail flow rules created in the Exchange Admin Center, or with DLP policies created in the Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="63786-p106">Exchange 管理センターでセキュリティを構成するすべてのポリシー ヒントのポリシー ヒントを構成したかどうかは&amp;コンプライアンス センターは、web 上の Outlook と Outlook 2013 および Exchange 管理センターでのヒントをオフにするまでは、後でユーザーに表示されません。こうと、現在の Exchange トランスポート ルールは、セキュリティに切り替えるときに選択するまでの作業を引き続き&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="63786-p106">If you've configured policy tips in the Exchange Admin Center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange Admin Center. This ensures that your current Exchange transport rules will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="63786-128">ポリシーのヒントは、1 つの場所からのみ描画できるときに電子メール通知を常に送信される、両方のセキュリティでは、DLP ポリシーを使用している場合でも&amp;コンプライアンス センターと、Exchange 管理センターです。</span><span class="sxs-lookup"><span data-stu-id="63786-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange Admin Center.</span></span>
  

