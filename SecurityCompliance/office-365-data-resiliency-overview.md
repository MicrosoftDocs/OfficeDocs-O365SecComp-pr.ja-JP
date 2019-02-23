---
title: Office 365 でのデータの回復性
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Microsoft Office 365 のデータ復元性について理解します。
ms.openlocfilehash: 1e85f431edeec0a4548b1d37b65a4b1a6cbef8eb
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215637"
---
# <a name="data-resiliency-in-office-365"></a><span data-ttu-id="2303c-103">Office 365 でのデータの回復性</span><span class="sxs-lookup"><span data-stu-id="2303c-103">Data Resiliency in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="2303c-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="2303c-104">Introduction</span></span>
<span data-ttu-id="2303c-p101">クラウドコンピューティングの複雑な性質を考慮した場合、Microsoft は、問題が発生した場合には発生しないことに注意してください。クラウドサービスを設計することで、信頼性を最大化し、問題が発生した場合にお客様に悪影響を最小限に抑えることができます。複雑な物理インフラストラクチャに依存する従来の戦略にとどまらないようになり、クラウドサービスに直接冗長性が組み込まれています。より複雑な物理インフラストラクチャと、データの復元をサービスに提供し、お客様に高可用性を提供する、よりインテリジェントなソフトウェアを組み合わせて使用しています。</span><span class="sxs-lookup"><span data-stu-id="2303c-p101">Given the complex nature of cloud computing, Microsoft is mindful that it's not a case of if things will go wrong, but rather when. We design our cloud services to maximize reliability and minimize the negative effects on customers when things do go wrong. We have moved beyond the traditional strategy of relying on complex physical infrastructure, and we have built redundancy directly into our cloud services. We use a combination of less complex physical infrastructure and more intelligent software that builds data resiliency into our services and delivers high availability to our customers.</span></span> 

## <a name="resiliency-and-recoverability-are-built-in"></a><span data-ttu-id="2303c-109">回復性と回復性が組み込まれている</span><span class="sxs-lookup"><span data-stu-id="2303c-109">Resiliency and Recoverability Are Built-in</span></span> 
<span data-ttu-id="2303c-p102">復元と復旧での構築は、基礎となるインフラストラクチャとプロセスがある時点で失敗することを前提としています。ハードウェア (インフラストラクチャ) は失敗し、人間がミスを犯し、ソフトウェアにバグがあります。ソフトウェア開発者がクラウドの前にこれらの問題について考えていない場合は、これらの問題が一般的な it 実装でどのように処理されているかは、クラウドの前に大きく異なるということです。</span><span class="sxs-lookup"><span data-stu-id="2303c-p102">Building in resiliency and recovery starts with the assumption that the underlying infrastructure and processes will fail at some point: hardware (infrastructure) will fail, humans will make mistakes, and software will have bugs. While it would be incorrect to say that software developers were not thinking about these things before the cloud, how these issues were handled in a typical IT implementation was very different before the cloud:</span></span> 
- <span data-ttu-id="2303c-p103">最初に、ハードウェアおよびインフラストラクチャの保護は重要でした。これは、データセンターに 99.99% の信頼性が必要であり、ハードウェアベースのクラスタリング、デュアル電源装置、デュアルネットワークインターフェイス、および like を使用してサーバーを実装していました。</span><span class="sxs-lookup"><span data-stu-id="2303c-p103">First, hardware and infrastructure protections were significant. This meant having datacenters with 99.99% reliability required significant power and network redundancy, and servers were implemented with hardware-based clustering, dual power supplies, dual network interfaces, and the like.</span></span> 
- <span data-ttu-id="2303c-p104">次に、プロセスは最も重要です。運用チームは厳密な手順を維持し、変更ウィンドウを採用し、多くの場合、プロジェクト管理に大きなオーバーヘッドが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2303c-p104">Second, process was paramount. Operations teams maintained rigorous procedures, change windows were employed, and there was often significant project management overhead.</span></span> 
- <span data-ttu-id="2303c-p105">3番目に、展開は glacial ペースで行われました。ソースを所有することなくコードを展開することで、更新プログラムのリリースを待機し、メジャーバージョンのリリースによってハードウェアの交換と多大な資本支出が発生しています。さらに、問題を修正する唯一の方法は、ロールバックすることでした。そのため、ほとんどの IT 組織は、最新の状態を維持する作業を回避するために、メジャーリリースのみを展開します。</span><span class="sxs-lookup"><span data-stu-id="2303c-p105">Third, deployment took place at a glacial pace. Deploying code without owning the source meant waiting for patch releases, and major version releases involved hardware replacement and significant capital outlay. Moreover, the only way to correct a problem was to rollback. Thus, most IT organizations would deploy only major releases to avoid the work to keep up-to-date.</span></span> 
- <span data-ttu-id="2303c-120">最後に、展開されたシステムの規模や、interconnectedness のレベルも、従来よりもはるかに小さくなっています。</span><span class="sxs-lookup"><span data-stu-id="2303c-120">Finally, the scale of deployed systems, as well as the level of their interconnectedness was historically much smaller than it is now.</span></span> 

<span data-ttu-id="2303c-121">現在、お客様は品質を損なうことなく、microsoft の革新的な革新性を期待しています。これは、microsoft のサービスとソフトウェアが復元性と復元性を考慮して構築されている理由の1つです。</span><span class="sxs-lookup"><span data-stu-id="2303c-121">Today, customers expect continuous innovation from Microsoft without compromising quality, and this is one of the reasons why Microsoft's services and software are built with resiliency and recoverability in mind.</span></span> 

## <a name="office-365-data-resiliency-principles"></a><span data-ttu-id="2303c-122">Office 365 データの復元の原則</span><span class="sxs-lookup"><span data-stu-id="2303c-122">Office 365 Data Resiliency Principles</span></span> 
<span data-ttu-id="2303c-p106">復元性とは、クラウドベースのサービスが特定の種類の障害に耐えることができ、さらに顧客の視点から完全に機能していることを意味します。データの復元とは、Office 365 で発生したエラーに関係なく、重要な顧客データはそのまま変わらず影響を受けません。そのために、Office 365 サービスは、次の5つの復元の原則を中心に設計されています。</span><span class="sxs-lookup"><span data-stu-id="2303c-p106">Resiliency refers to the ability of a cloud-based service to withstand certain types of failures and yet remain fully-functional from the customers' perspective. Data resiliency means that no matter what failures occur within Office 365, critical customer data remains intact and unaffected. To that end, Office 365 services have been designed around five specific resiliency principles:</span></span> 
- <span data-ttu-id="2303c-p107">重要で重要ではないデータがあります。重要でないデータ (メッセージが開封されたかどうかなど) は、まれな障害のシナリオで削除できます。重要なデータ (たとえば、電子メールメッセージなどの顧客データ) は、コストがかかるために保護する必要があります。設計上の目的として、配信されるメールメッセージは常に重要であり、メッセージが開封されたかどうかは重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2303c-p107">There is critical and non-critical data. Non-critical data (for example, whether a message was read) can be dropped in rare failure scenarios. Critical data (for example, customer data such as email messages) should be protected at extreme cost. As a design goal, delivered mail messages are always critical, and things like whether a message has been read is non-critical.</span></span> 
- <span data-ttu-id="2303c-130">顧客データのコピーは、障害が発生しないようにするために、可能な限り多くの障害領域または障害ドメイン (データセンター、単一の資格情報 (プロセス、サーバー、またはオペレーター) によってアクセス可能) に分けて行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2303c-130">Copies of customer data must be separated into different fault zones or as many fault domains as possible (e.g., datacenters, accessible by single credentials (process, server, or operator)) to provide failure isolation.</span></span> 
- <span data-ttu-id="2303c-131">重要な顧客データを監視して、原子性、一貫性、分離性、耐久性 (ACID) の一部に失敗しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2303c-131">Critical customer data must be monitored for failing any part of Atomicity, Consistency, Isolation, Durability (ACID).</span></span> 
- <span data-ttu-id="2303c-p108">お客様のデータを破損から保護する必要があります。これは、積極的にスキャンまたは監視、修復、および回復可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2303c-p108">Customer data must be protected from corruption. It must be actively scanned or monitored, repairable, and recoverable.</span></span> 
- <span data-ttu-id="2303c-134">お客様のアクションによってデータが失われる可能性があるため、お客様は、誤って削除されたアイテムの復元を可能にする GUI を使用して、自分で復元できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2303c-134">Most data loss results from customer actions, so allow customers to recover on their own using a GUI that enables them to restore accidentally deleted items.</span></span> 
 
<span data-ttu-id="2303c-135">Office 365 は、これらの原則にクラウドサービスを構築して、堅牢なテストと検証を行いましたが、継続的な革新と改善のためのプラットフォームを確保する一方で、お客様の要件を満たすことと、それを上回ることができます。</span><span class="sxs-lookup"><span data-stu-id="2303c-135">Through the building of our cloud services to these principles, coupled with robust testing and validation, Office 365 is able to meet and exceed the requirements of customers while ensuring a platform for continuous innovation and improvement.</span></span> 

## <a name="related-links"></a><span data-ttu-id="2303c-136">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2303c-136">Related Links</span></span>

- [<span data-ttu-id="2303c-137">データの破損への対処</span><span class="sxs-lookup"><span data-stu-id="2303c-137">Dealing with Data Corruption</span></span>](office-365-dealing-with-data-corruption.md)
- [<span data-ttu-id="2303c-138">マルウェアと ランサムウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="2303c-138">Malware and Ransomware Protection</span></span>](office-365-malware-and-ransomware-protection.md)
- [<span data-ttu-id="2303c-139">監視と自動修復</span><span class="sxs-lookup"><span data-stu-id="2303c-139">Monitoring and Self-Healing</span></span>](office-365-monitoring-and-self-healing.md)
- [<span data-ttu-id="2303c-140">Exchange データの復元</span><span class="sxs-lookup"><span data-stu-id="2303c-140">Exchange Data Resiliency</span></span>](office-365-exchange-data-resiliency.md)
- [<span data-ttu-id="2303c-141">SharePoint データの復元</span><span class="sxs-lookup"><span data-stu-id="2303c-141">SharePoint Data Resiliency</span></span>](office-365-sharepoint-data-resiliency.md)