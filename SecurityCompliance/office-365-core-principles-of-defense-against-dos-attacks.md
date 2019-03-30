---
title: サービス拒否攻撃に対する Office 365 の防御の中核となる原則
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Microsoft は、サービス拒否 (DoS) 攻撃に対する防御において、吸収、検出、軽減の中心となる原則を活用する方法について説明します。
ms.openlocfilehash: bbfffeaeb66fc83e80c274be9550a95dc8bd3f0d
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004104"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="9f76f-103">サービス拒否攻撃に対する防御の主要な原則</span><span class="sxs-lookup"><span data-stu-id="9f76f-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="9f76f-104">ネットワークベースの DoS 攻撃に対する防御の3つの主要な原則は、配賦、検出、および軽減です。</span><span class="sxs-lookup"><span data-stu-id="9f76f-104">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation.</span></span>
<span data-ttu-id="9f76f-105">自動処理は検出の前に発生し、軽減の前に検出が行われます。</span><span class="sxs-lookup"><span data-stu-id="9f76f-105">Absorption happens before detection, and detection happens before mitigation.</span></span> <span data-ttu-id="9f76f-106">配賦は、DoS 攻撃に対して最適な防衛策です。</span><span class="sxs-lookup"><span data-stu-id="9f76f-106">Absorption is the best defense against a DoS attacks.</span></span> <span data-ttu-id="9f76f-107">攻撃を検出できない場合は、軽減することはできません。</span><span class="sxs-lookup"><span data-stu-id="9f76f-107">If the attack can't be detected, it can't be mitigated.</span></span> <span data-ttu-id="9f76f-108">しかし、最小の DoS 攻撃を吸収できない場合でも、攻撃を検出するのに十分に長い時間がかかることはありません。</span><span class="sxs-lookup"><span data-stu-id="9f76f-108">But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="9f76f-109">一般的に、ほとんどの組織では、テクノロジと技術スキルに多大な投資が必要になるため、ほとんどの組織では、DoS 攻撃を吸収するために必要な余分な容量を購入することができません。</span><span class="sxs-lookup"><span data-stu-id="9f76f-109">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills.</span></span> <span data-ttu-id="9f76f-110">これは、Microsoft クラウドサービスを使用する場合のセキュリティ上の利点の1つを強調しています。当社のサービスの大規模では、費用対効果の高い方法でクラウドのお客様に強力なネットワーク保護を提供できます。</span><span class="sxs-lookup"><span data-stu-id="9f76f-110">This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner.</span></span> <span data-ttu-id="9f76f-111">しかし、規模の拡大にもかかわらず、吸収、検出、および軽減のバランスがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f76f-111">But even at our scale, though, there must still be a balance between absorption, detection, and mitigation.</span></span> <span data-ttu-id="9f76f-112">そのバランスを見つけるために、攻撃の成長率を調査して、どれくらいの量を吸収する必要があるかを予測します。</span><span class="sxs-lookup"><span data-stu-id="9f76f-112">To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="9f76f-113">検出は、cat とマウスのゲームです。</span><span class="sxs-lookup"><span data-stu-id="9f76f-113">Detection is a cat-and-mouse game.</span></span> <span data-ttu-id="9f76f-114">ユーザーが攻撃を仕掛けたり、システムを突破したりしようとする新しい方法を絶えず模索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f76f-114">You must constantly look for the new ways people are attacking you or trying to defeat your systems.</span></span> <span data-ttu-id="9f76f-115">> の緩和-> detect-> の緩和などは永続的な永続的な状態で、無期限に継続されます。</span><span class="sxs-lookup"><span data-stu-id="9f76f-115">Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="9f76f-116">DoS 攻撃からの防御</span><span class="sxs-lookup"><span data-stu-id="9f76f-116">Defending Against DoS Attacks</span></span>

<span data-ttu-id="9f76f-117">DoS 攻撃に対して適切に防御するには、早期の検出が不可欠です。</span><span class="sxs-lookup"><span data-stu-id="9f76f-117">To successfully defend against a DoS attack, early detection is essential.</span></span> <span data-ttu-id="9f76f-118">システムが過負荷になる前に攻撃を検出することによって、defenders は応答計画を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9f76f-118">By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="9f76f-119">次の式を使用すると、DoS 攻撃の影響におおよその時間を見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="9f76f-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="9f76f-120">**最大容量 (バイト/秒)/増加率 (バイト/秒) = 影響時間 (バイト/秒)**</span><span class="sxs-lookup"><span data-stu-id="9f76f-120">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="9f76f-121">影響が発生した後に検出時間が経過すると、DoS 攻撃が成功する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="9f76f-121">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful.</span></span> <span data-ttu-id="9f76f-122">影響が発生するまでの時間が非常に大きい場合は、軽減戦略を使用している場合は、攻撃対象のサービスをオンラインで利用可能な状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f76f-122">If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used.</span></span> <span data-ttu-id="9f76f-123">そのため、DoS 攻撃に対して防御するには、次の2つのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9f76f-123">Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="9f76f-124">最大処理能力の上限を上げるために、処理能力を向上させます (これにより、攻撃を検出するための時間が長くなります)。や</span><span class="sxs-lookup"><span data-stu-id="9f76f-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="9f76f-125">検出時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="9f76f-125">Decrease the time to detect.</span></span>

<span data-ttu-id="9f76f-126">キャパシティの増加は、直接の会計に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="9f76f-126">Increasing capacity has a direct fiscal impact.</span></span> <span data-ttu-id="9f76f-127">Microsoft では、少なくとも基本的な吸収処理能力を開発して、ある程度の DoS 攻撃に備えられるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9f76f-127">Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack.</span></span> <span data-ttu-id="9f76f-128">実際の吸収処理能力は顧客によって異なりますが、顧客ごとに、公開、リスク、および財務コストに対する独自のしきい値があります。</span><span class="sxs-lookup"><span data-stu-id="9f76f-128">The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay.</span></span> <span data-ttu-id="9f76f-129">最終的には、経済的な理由から、検出時間を短縮する方法による研究と時間の投資は、通常、最も費用対効果の高い防御となります。</span><span class="sxs-lookup"><span data-stu-id="9f76f-129">Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
