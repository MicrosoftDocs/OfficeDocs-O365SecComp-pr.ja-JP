---
title: サービス拒否攻撃に対する Office 365 の防御の中核となる原則
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Microsoft は、サービス拒否 (DoS) 攻撃に対する防御において、吸収、検出、軽減の中心となる原則を活用する方法について説明します。
ms.openlocfilehash: dfe179924f7414b0120697023f3daf7e6b6661b6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216007"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="81990-103">サービス拒否攻撃に対する防御の主要な原則</span><span class="sxs-lookup"><span data-stu-id="81990-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="81990-p101">ネットワークベースの DoS 攻撃に対する防御の3つの主要な原則は、配賦、検出、および軽減です。自動処理は検出の前に発生し、軽減の前に検出が行われます。配賦は、DoS 攻撃に対して最適な防衛策です。攻撃を検出できない場合は、軽減することはできません。しかし、最小の DoS 攻撃を吸収できない場合でも、攻撃を検出するのに十分に長い時間がかかることはありません。</span><span class="sxs-lookup"><span data-stu-id="81990-p101">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation. Absorption happens before detection, and detection happens before mitigation. Absorption is the best defense against a DoS attacks. If the attack can't be detected, it can't be mitigated. But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="81990-p102">一般的に、ほとんどの組織では、テクノロジと技術スキルに多大な投資が必要になるため、ほとんどの組織では、DoS 攻撃を吸収するために必要な余分な容量を購入することができません。これは、Microsoft クラウドサービスを使用する場合のセキュリティ上の利点の1つを強調しています。当社のサービスの大規模では、費用対効果の高い方法でクラウドのお客様に強力なネットワーク保護を提供できます。しかし、規模の拡大にもかかわらず、吸収、検出、および軽減のバランスがある必要があります。そのバランスを見つけるために、攻撃の成長率を調査して、どれくらいの量を吸収する必要があるかを予測します。</span><span class="sxs-lookup"><span data-stu-id="81990-p102">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills. This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner. But even at our scale, though, there must still be a balance between absorption, detection, and mitigation. To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="81990-p103">検出は、cat とマウスのゲームです。ユーザーが攻撃を仕掛けたり、システムを突破したりしようとする新しい方法を絶えず模索する必要があります。> の緩和-> detect-> の緩和などは永続的な永続的な状態で、無期限に継続されます。</span><span class="sxs-lookup"><span data-stu-id="81990-p103">Detection is a cat-and-mouse game. You must constantly look for the new ways people are attacking you or trying to defeat your systems. Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="81990-116">DoS 攻撃からの防御</span><span class="sxs-lookup"><span data-stu-id="81990-116">Defending Against DoS Attacks</span></span>

<span data-ttu-id="81990-p104">DoS 攻撃に対して適切に防御するには、早期の検出が不可欠です。システムが過負荷になる前に攻撃を検出することによって、defenders は応答計画を実行できます。</span><span class="sxs-lookup"><span data-stu-id="81990-p104">To successfully defend against a DoS attack, early detection is essential. By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="81990-119">次の式を使用すると、DoS 攻撃の影響におおよその時間を見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="81990-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="81990-120">**最大容量 (バイト/秒)/増加率 (バイト/秒) = 影響時間 (バイト/秒)**</span><span class="sxs-lookup"><span data-stu-id="81990-120">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="81990-p105">影響が発生した後に検出時間が経過すると、DoS 攻撃が成功する可能性が高くなります。影響が発生するまでの時間が非常に大きい場合は、軽減戦略を使用している場合は、攻撃対象のサービスをオンラインで利用可能な状態に保つ必要があります。そのため、DoS 攻撃に対して防御するには、次の2つのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="81990-p105">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful. If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used. Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="81990-124">最大処理能力の上限を上げるために、処理能力を向上させます (これにより、攻撃を検出するための時間が長くなります)。や</span><span class="sxs-lookup"><span data-stu-id="81990-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="81990-125">検出時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="81990-125">Decrease the time to detect.</span></span>

<span data-ttu-id="81990-p106">キャパシティの増加は、直接の会計に影響を与えます。Microsoft では、少なくとも基本的な吸収処理能力を開発して、ある程度の DoS 攻撃に備えられるようにすることをお勧めします。実際の吸収処理能力は顧客によって異なりますが、顧客ごとに、公開、リスク、および財務コストに対する独自のしきい値があります。最終的には、経済的な理由から、検出時間を短縮する方法による研究と時間の投資は、通常、最も費用対効果の高い防御となります。</span><span class="sxs-lookup"><span data-stu-id="81990-p106">Increasing capacity has a direct fiscal impact. Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack. The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay. Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
