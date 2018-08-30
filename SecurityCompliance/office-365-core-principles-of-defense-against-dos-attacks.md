---
title: サービス拒否の攻撃に対する防御の主要な原則を office 365
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
description: 方法マイクロソフトでは、吸収、検出、およびサービス拒否 (DoS) 攻撃の防御で軽減の主要な原則を利用します。
ms.openlocfilehash: 8355a7897c788241092363a23e198423e81c587a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531544"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="96d23-103">サービス拒否攻撃に対する防御の主要な原則</span><span class="sxs-lookup"><span data-stu-id="96d23-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>
<span data-ttu-id="96d23-p101">原則は、吸収、検出、およびリスク軽減は、ネットワーク ベースの DoS 攻撃に対する防御と、3 つのコアです。吸収を検出する前に発生し、軽減する前に検出が行われます。配賦は、DoS 攻撃に対する最善の防御です。攻撃が検出された場合を軽減することはできません。ですが、最小の DoS 攻撃もを吸収することはできません、する場合、サービスはことはめったに攻撃を検出するのに十分な長さです。</span><span class="sxs-lookup"><span data-stu-id="96d23-p101">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation. Absorption happens before detection, and detection happens before mitigation. Absorption is the best defense against a DoS attacks. If the attack can't be detected, it can't be mitigated. But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="96d23-p102">もちろんは一般にテクノロジーとの技術的なスキルに多大な投資が必要なためこの DoS 攻撃を吸収するために必要な余分な容量を購入するほとんどの組織に経済的に実現します。これは、Microsoft クラウド サービスを使用する場合のセキュリティ上の利点の 1 つを強調表示します。当社のサービスの膨大なスケールでは、クラウドのお客様に低コストで強力なネットワーク保護を提供できます。ですが、スケールであっても、存在する必要があります吸収、検出、およびリスク軽減のバランスです。そのバランスを見つけるには、量を吸収する必要がありますを見積もるための攻撃の増加率を検討します。</span><span class="sxs-lookup"><span data-stu-id="96d23-p102">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills. This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner. But even at our scale, though, there must still be a balance between absorption, detection, and mitigation. To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="96d23-p103">検出は、cat-and-mouse ゲームです。新しい働き方が攻撃するか、システムを突破しようとしていますを常に探す必要があります。Mitigate] メニューの [アプリケーションの自動検出] のメニューの [Mitigate など、永続的な永続的な状態であり、無期限に続行されます。</span><span class="sxs-lookup"><span data-stu-id="96d23-p103">Detection is a cat-and-mouse game. You must constantly look for the new ways people are attacking you or trying to defeat your systems. Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="96d23-116">DoS 攻撃に対する防御</span><span class="sxs-lookup"><span data-stu-id="96d23-116">Defending Against DoS Attacks</span></span>
<span data-ttu-id="96d23-p104">正常には、DoS 攻撃に対する防御を早期に検出する必要があります。攻撃を検出するシステムが倒される前に、防側は、対応計画を実行できます。</span><span class="sxs-lookup"><span data-stu-id="96d23-p104">To successfully defend against a DoS attack, early detection is essential. By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="96d23-119">次の数式は、DoS 攻撃の影響を与えるまでの時間を概算することができます。</span><span class="sxs-lookup"><span data-stu-id="96d23-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="96d23-120">**最大容量 (最大容量 X の成長率)/= 時間への影響**</span><span class="sxs-lookup"><span data-stu-id="96d23-120">**Maximum Capacity / (Maximum Capacity X Growth Rate) = Time to Impact**</span></span>

<span data-ttu-id="96d23-p105">可能性がありますし、後の時間の影響、検出に時間が発生した場合、DoS 攻撃を受けます。影響の時間の前に検出に時間が発生した場合、攻撃対象となるサービス継続してオンラインでアクセス可能な軽減戦略を使用する場合。したがって、DoS 攻撃に対する防御を行うだけの 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="96d23-p105">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful. If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used. Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="96d23-124">(これは、攻撃を検出するためにより多くの時間を提供する) 最大容量の上限を上げるに容量を増やすまたは</span><span class="sxs-lookup"><span data-stu-id="96d23-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="96d23-125">検出する時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="96d23-125">Decrease the time to detect.</span></span>

<span data-ttu-id="96d23-p106">容量を増やすことと、直接会計への影響があります。お客様が、少なくとも基本的な吸収を開発することをお勧めします容量、DoS 攻撃のいくつかのレベルを維持できることを確認します。各顧客には、リスク、リスク、および財務の支出の独自のしきい値とは、実際の吸収能力をお客様に異なります。最終的には、経済的な理由により、調査および時間の検出に時間を短縮する方法での投資は、通常最も費用効果の高い防御。</span><span class="sxs-lookup"><span data-stu-id="96d23-p106">Increasing capacity has a direct fiscal impact. Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack. The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay. Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
