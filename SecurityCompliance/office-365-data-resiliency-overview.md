---
title: Office 365 でのデータの回復性
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Microsoft Office 365 のデータのリカバリ性を理解します。
ms.openlocfilehash: 7d43c766615ff1520c6529427116c42795da8565
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532425"
---
# <a name="data-resiliency-in-office-365"></a><span data-ttu-id="d02fc-103">Office 365 でのデータの回復性</span><span class="sxs-lookup"><span data-stu-id="d02fc-103">Data Resiliency in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="d02fc-104">概要</span><span class="sxs-lookup"><span data-stu-id="d02fc-104">Introduction</span></span>
<span data-ttu-id="d02fc-p101">クラウド コンピューティングの複雑な性質を指定するには、マイクロソフトでは注意がないこと、大文字と小文字の場合はうまくは行かないが、ときにではなく。信頼性を最大化し、障害発生時にお客様にマイナスの影響を最小化するクラウド サービスを設計します。複雑な物理インフラストラクチャに依存することの従来の戦略をより後に移動して、クラウド サービスに冗長性を組み込みました。あまり複雑な物理インフラストラクチャとは、当社のサービスにデータの復元を構築し、お客様に高可用性を実現するよりインテリジェントなソフトウェアの組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="d02fc-p101">Given the complex nature of cloud computing, Microsoft is mindful that it's not a case of if things will go wrong, but rather when. We design our cloud services to maximize reliability and minimize the negative effects on customers when things do go wrong. We have moved beyond the traditional strategy of relying on complex physical infrastructure, and we have built redundancy directly into our cloud services. We use a combination of less complex physical infrastructure and more intelligent software that builds data resiliency into our services and delivers high availability to our customers.</span></span> 

## <a name="resiliency-and-recoverability-are-built-in"></a><span data-ttu-id="d02fc-109">弾力性とリカバリ性が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="d02fc-109">Resiliency and Recoverability Are Built-in</span></span> 
<span data-ttu-id="d02fc-p102">ある時点で、基になるインフラストラクチャとプロセスが失敗することを前提に弾力性とリカバリの構築を開始: ハードウェア (インフラストラクチャ) は失敗し、人間は間違いをし、ソフトウェアのバグがあります。あるように、ソフトウェア開発者が、クラウドの前にこれらの問題を考えると正しい、一般的な IT の実装でこれらの問題が処理する方法でした、クラウドの前に非常に異なる。</span><span class="sxs-lookup"><span data-stu-id="d02fc-p102">Building in resiliency and recovery starts with the assumption that the underlying infrastructure and processes will fail at some point: hardware (infrastructure) will fail, humans will make mistakes, and software will have bugs. While it would be incorrect to say that software developers were not thinking about these things before the cloud, how these issues were handled in a typical IT implementation was very different before the cloud:</span></span> 
- <span data-ttu-id="d02fc-p103">最初に、ハードウェアとインフラストラクチャの保護は大きなものでした。これは、意味しており、99.99% の信頼性が必要な重要な電源とネットワークの冗長性を持つデータ センターおよびサーバーは、ハードウェア ・ ベースのクラスタ リング、デュアル電源装置、デュアル ・ ネットワーク ・ インタ フェースなどで実装されました。</span><span class="sxs-lookup"><span data-stu-id="d02fc-p103">First, hardware and infrastructure protections were significant. This meant having datacenters with 99.99% reliability required significant power and network redundancy, and servers were implemented with hardware-based clustering, dual power supplies, dual network interfaces, and the like.</span></span> 
- <span data-ttu-id="d02fc-p104">次に、プロセスは非常に重要でした。運用チームは、厳格な手順は、windows が採用されている場合、変更を維持し、多くの場合重要なプロジェクト管理のオーバーヘッドが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d02fc-p104">Second, process was paramount. Operations teams maintained rigorous procedures, change windows were employed, and there was often significant project management overhead.</span></span> 
- <span data-ttu-id="d02fc-p105">第三に、展開が行わ氷河のペースで。修正プログラムのリリースを待っている間のもので、ソースを所有することがなくコードを展開して、メジャー バージョンが関連するハードウェアの交換および資本支出を大幅に解放します。さらに、ロールバックすることが問題を解決する唯一の方法でした。したがって、ほとんどの IT 組織は、最新の状態を維持するための作業を避けるために主なリリースを展開しました。</span><span class="sxs-lookup"><span data-stu-id="d02fc-p105">Third, deployment took place at a glacial pace. Deploying code without owning the source meant waiting for patch releases, and major version releases involved hardware replacement and significant capital outlay. Moreover, the only way to correct a problem was to rollback. Thus, most IT organizations would deploy only major releases to avoid the work to keep up-to-date.</span></span> 
- <span data-ttu-id="d02fc-120">最後に、展開済みのシステムでは、小数点以下桁数だけでなく、相互のレベルは、従来よりはるかに小さいよりも、今すぐでした。</span><span class="sxs-lookup"><span data-stu-id="d02fc-120">Finally, the scale of deployed systems, as well as the level of their interconnectedness was historically much smaller than it is now.</span></span> 

<span data-ttu-id="d02fc-121">今日では、品質を損なうことがなくお客様がマイクロソフトの継続的な技術革新を期待し、弾力性とリカバリ性を念頭にマイクロソフトのサービスおよびソフトウェアを構築する理由の理由の一でしょう。</span><span class="sxs-lookup"><span data-stu-id="d02fc-121">Today, customers expect continuous innovation from Microsoft without compromising quality, and this is one of the reasons why Microsoft's services and software are built with resiliency and recoverability in mind.</span></span> 

## <a name="office-365-data-resiliency-principles"></a><span data-ttu-id="d02fc-122">Office 365 のデータのリカバリ性の原則</span><span class="sxs-lookup"><span data-stu-id="d02fc-122">Office 365 Data Resiliency Principles</span></span> 
<span data-ttu-id="d02fc-p106">弾力性は、特定の種類の障害に耐えられるを維持し、ながら完全なお客様の観点からするクラウド ベースのサービスの機能を指します。データの復元では、ことも、Office 365 内でどのような障害が発生すると、重要な顧客データはそのままの状態と影響を受けていないことを示します。そのために、Office 365 のサービスを提供しているには、約 5 つの特定の弾力性の原則が設計されています。</span><span class="sxs-lookup"><span data-stu-id="d02fc-p106">Resiliency refers to the ability of a cloud-based service to withstand certain types of failures and yet remain fully-functional from the customers' perspective. Data resiliency means that no matter what failures occur within Office 365, critical customer data remains intact and unaffected. To that end, Office 365 services have been designed around five specific resiliency principles:</span></span> 
- <span data-ttu-id="d02fc-p107">重要な重要でないデータがあります。まれな障害シナリオでは、重要ではない (たとえば、かどうかメッセージが読み取られたデータ) を削除できます。極端なコストで重要なデータ (たとえば、電子メール メッセージなどの顧客データ) を保護する必要があります。設計目標では、配信されたメール メッセージは、常に重要なと、メッセージが開封されたかどうかといったことが重要ではないです。</span><span class="sxs-lookup"><span data-stu-id="d02fc-p107">There is critical and non-critical data. Non-critical data (for example, whether a message was read) can be dropped in rare failure scenarios. Critical data (for example, customer data such as email messages) should be protected at extreme cost. As a design goal, delivered mail messages are always critical, and things like whether a message has been read is non-critical.</span></span> 
- <span data-ttu-id="d02fc-130">顧客データのコピーは、さまざまな障害のゾーンに区切る必要がありますか、障害の分離を提供する限り (例えば、データ センター、(プロセス、サーバー、または演算子) の 1 つの資格情報でアクセス可能な) ドメインの障害の多くとします。</span><span class="sxs-lookup"><span data-stu-id="d02fc-130">Copies of customer data must be separated into different fault zones or as many fault domains as possible (e.g., datacenters, accessible by single credentials (process, server, or operator)) to provide failure isolation.</span></span> 
- <span data-ttu-id="d02fc-131">原子性、一貫性、独立性、持続性 (ACID) の任意の部分の失敗の重要な顧客データを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02fc-131">Critical customer data must be monitored for failing any part of Atomicity, Consistency, Isolation, Durability (ACID).</span></span> 
- <span data-ttu-id="d02fc-p108">顧客データは、破損から保護する必要があります。積極的にスキャンまたは監視対象、リペアが可能なおよび回復可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02fc-p108">Customer data must be protected from corruption. It must be actively scanned or monitored, repairable, and recoverable.</span></span> 
- <span data-ttu-id="d02fc-134">顧客のアクションからのほとんどのデータが失われる結果は、お客様が誤って削除したアイテムを復元することを可能にする GUI を使用して独自のリカバリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d02fc-134">Most data loss results from customer actions, so allow customers to recover on their own using a GUI that enables them to restore accidentally deleted items.</span></span> 
 
<span data-ttu-id="d02fc-135">これらの原則は、堅牢なテストと検証を組み合わせることにクラウド サービスの構築は、Office 365 に対応し、継続的な革新および改善するためのプラットフォームを確保しながら、お客様の要件を上回ることです。</span><span class="sxs-lookup"><span data-stu-id="d02fc-135">Through the building of our cloud services to these principles, coupled with robust testing and validation, Office 365 is able to meet and exceed the requirements of customers while ensuring a platform for continuous innovation and improvement.</span></span> 

## <a name="related-links"></a><span data-ttu-id="d02fc-136">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d02fc-136">Related Links</span></span>

- [<span data-ttu-id="d02fc-137">データの破損への対処</span><span class="sxs-lookup"><span data-stu-id="d02fc-137">Dealing with Data Corruption</span></span>](office-365-dealing-with-data-corruption.md)
- [<span data-ttu-id="d02fc-138">マルウェアと ランサムウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="d02fc-138">Malware and Ransomware Protection</span></span>](office-365-malware-and-ransomware-protection.md)
- [<span data-ttu-id="d02fc-139">監視と自動修復</span><span class="sxs-lookup"><span data-stu-id="d02fc-139">Monitoring and Self-Healing</span></span>](office-365-monitoring-and-self-healing.md)
- [<span data-ttu-id="d02fc-140">Exchange データの復元</span><span class="sxs-lookup"><span data-stu-id="d02fc-140">Exchange Data Resiliency</span></span>](office-365-exchange-data-resiliency.md)
- [<span data-ttu-id="d02fc-141">SharePoint データの復元</span><span class="sxs-lookup"><span data-stu-id="d02fc-141">SharePoint Data Resiliency</span></span>](office-365-sharepoint-data-resiliency.md)