---
title: Office 365 Microsoft の DoS 防御戦略
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: サービス拒否 (DoS) 攻撃に対処するための Microsoft の防御戦略の概要について説明します。
ms.openlocfilehash: 0b0cf20e6282c85ede05edda3979ae5a7295ac78
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090819"
---
# <a name="microsofts-denial-of-service-defense-strategy"></a><span data-ttu-id="c18c4-103">Microsoft のサービス拒否防御戦略</span><span class="sxs-lookup"><span data-stu-id="c18c4-103">Microsoft's Denial-of-Service Defense Strategy</span></span>

<span data-ttu-id="c18c4-p101">Microsoft のネットワークベースのサービス拒否 (DoS) 攻撃を防御する戦略は、拡張およびグローバルな設置面積によって、ある程度は独自性があります。このスケールにより、Microsoft は、組織 (プロバイダーやお客様の組織) が一致できる戦略や手法を利用できるようになります。DoS 戦略の基礎として、グローバルなプレゼンスを活用しています。Microsoft は、世界中のインターネットプロバイダー、ピアリングプロバイダー (パブリックおよびプライベート)、および民間企業と連携して、非常に多くのインターネットプレゼンスを提供しています (この執筆の時点では、18か月ごとに2倍になります)。このような大規模なプレゼンスを使用することにより、Microsoft が非常に大きな領域を越えて攻撃を吸収できます。</span><span class="sxs-lookup"><span data-stu-id="c18c4-p101">Microsoft's strategy for defending against network-based denial-of-service (DoS) attacks is somewhat unique due to our scale and global footprint. This scale allows Microsoft to utilize strategies and techniques that few organizations (providers or customer organizations) can match. The cornerstone of our DoS strategy is leveraging our global presence. Microsoft engages with Internet providers, peering providers (public and private), and private corporations all over the world, giving us a significant Internet presence (which as of this writing, doubles around every 18 months). Having such a large presence enables Microsoft to absorb attacks across a very large surface area.</span></span>

<span data-ttu-id="c18c4-p102">この固有の性質から、Microsoft は大企業で使用されていたものとは異なる検出および軽減プロセスを使用します。この戦略は、さまざまなエッジを通じて、検出と緩和、およびグローバルな分散型の軽減を分離することに基づいています。多くの企業では、エッジに対する攻撃を検出して軽減するサードパーティ製のソリューションを使用しています。エッジの処理能力が拡大するにつれて、個々のエッジまたは特定のエッジに対する攻撃の重大性が非常に低いことが明らかになりました。独自の構成により、検出と軽減のコンポーネントが分離されています。エッジでグローバルな軽減を維持しつつ、飽和点に近い攻撃を検出できる複数層の検出を展開しています。この戦略では、複数の同時攻撃を処理できることを保証します。</span><span class="sxs-lookup"><span data-stu-id="c18c4-p102">Given our unique nature, Microsoft uses detection and mitigation processes that differ from those used by large enterprises. Our strategy is based on a separation of detection and mitigation, as well as global, distributed mitigation through our many edges. Many enterprises use third-party solutions which detect and mitigate attacks at the edge. As our edge capacity grew, it became clear that the significance of any attack against individual or particular edges was very low. Because of our unique configuration, we have separated the detection and mitigation components. We have deployed multi-tiered detection that enables us to detect attacks closer to their saturation points while maintaining global mitigation at the edge. This strategy ensures we can handle multiple simultaneous attacks.</span></span>

<span data-ttu-id="c18c4-p103">DoS 攻撃に対して Microsoft が採用する最も効果的かつ低コストの防御の1つは、攻撃対象を減らすことです。これにより、データをインラインで分析、処理、およびスクラビングするのではなく、エッジで不要なトラフィックを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c18c4-p103">One of the most effective and low-cost defenses employed by Microsoft against DoS attacks is to reduce our attack surface. Doing so enables us to drop unwanted traffic at the edge, as opposed to analyzing, processing and scrubbing the data inline.</span></span>

<span data-ttu-id="c18c4-p104">Microsoft では、パブリックネットワークとのインターフェイスで、ファイアウォール、ネットワークアドレス変換、および IP フィルター機能に特別な目的のセキュリティデバイスを使用しています。また、グローバルな同等コストのマルチパス (ecmp) ルーティングも使用します。グローバル ecmp routing は、1つのサービスに到達するためのグローバルパスが複数存在することを保証するネットワークフレームワークです。これらの複数のパスにより、サービスに対する攻撃は、攻撃が発生した地域に制限される必要があります。また、エンドユーザーは他のパスを使用してそれらの地域のサービスに到達するため、他の地域はこの攻撃による影響を受けないようにする必要があります。また、フローデータ、パフォーマンス指標、その他の情報を使用する独自の内部 DoS 相互関係および検出システムも開発しています。これは microsoft Azure 内で実行される hyperscale cloud service で、microsoft のネットワークおよびサービスのさまざまな時点から収集されたデータを分析します。ワークロード間の DoS インシデント対応チームは、teams 全体の役割と責任、エスカレーションの条件、およびさまざまなチームやインシデント処理を行うためのプロトコルを特定します。これらのソリューションは、DoS 攻撃に対するネットワークベースの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="c18c4-p104">At the interface with the public network, Microsoft uses special-purpose security devices for firewall, network address translation, and IP filtering functions. We also use global equal-cost multi-path (ECMP) routing. Global ECMP routing is a network framework that ensures there are multiple global paths to reach a service. Thanks to these multiple paths, an attack against the service should be limited to the region from which the attack originates – other regions should be unaffected by this attack, as end users would use other paths to reach the service in those regions. We have also developed our own internal DoS correlation and detection system that uses flow data, performance metrics and other information. This is a hyperscale cloud service running within Microsoft Azure which analyzes data collected from various points on Microsoft networks and services. A cross-workload DoS incident response team identifies the roles and responsibilities across teams, the criteria for escalations, and the protocols for engaging various teams and for incident handling. These solutions provide network-based protection against DoS attacks.</span></span>

<span data-ttu-id="c18c4-126">最後に、クラウドベースのワークロードは、プロトコルに基づいて最適化されたしきい値を使用して構成され、帯域幅の使用量はそのワークロードを一意に保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18c4-126">Finally, cloud-based workloads are configured with optimized thresholds based on their protocol and bandwidth usage needs to uniquely protect that workload.</span></span>
