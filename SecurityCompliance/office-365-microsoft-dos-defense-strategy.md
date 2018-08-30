---
title: Microsoft office 365 の DoS の防御戦略
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
description: サービス拒否 (DoS) 攻撃に対処するための Microsoft の防御戦略の概要について説明します。
ms.openlocfilehash: f172db5080ef73402c7e9bc61720eb0f87e844ac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531552"
---
# <a name="microsofts-denial-of-service-defense-strategy"></a><span data-ttu-id="10433-103">マイクロソフトのサービス拒否攻撃の防御戦略</span><span class="sxs-lookup"><span data-stu-id="10433-103">Microsoft's Denial-of-Service Defense Strategy</span></span>

<span data-ttu-id="10433-p101">ネットワーク ベースのサービス拒否 (DoS) 攻撃に対する防御の Microsoft の戦略は、当社の規模とグローバルなフット プリントのためある程度に一意です。このスケールでは、戦略といくつかの組織 (プロバイダーまたはお客様の組織) に一致する手法を使用する Microsoft を使用できます。DoS 戦略の基盤とは、グローバルな存在を活用することです。マイクロソフトでは、(これを書いている時点で 18 か月ごとに 2 倍になります)、重要なインターネット プレゼンスを提供すること、世界中の企業がインターネット プロバイダー、ピアリング プロバイダー (パブリックおよびプライベート)、およびプライベートと連携してください。このような大規模に存在することには、マイクロソフトが表面に非常に広い領域にわたって攻撃を吸収するが有効にします。</span><span class="sxs-lookup"><span data-stu-id="10433-p101">Microsoft's strategy for defending against network-based denial-of-service (DoS) attacks is somewhat unique due to our scale and global footprint. This scale allows Microsoft to utilize strategies and techniques that few organizations (providers or customer organizations) can match. The cornerstone of our DoS strategy is leveraging our global presence. Microsoft engages with Internet providers, peering providers (public and private), and private corporations all over the world, giving us a significant Internet presence (which as of this writing, doubles around every 18 months). Having such a large presence enables Microsoft to absorb attacks across a very large surface area.</span></span>

<span data-ttu-id="10433-p102">マイクロソフトは、固有の性質を指定するには、大企業で使用されるものとは異なる検出と緩和策のプロセスを使用します。私たちの戦略は、を介して、複数のエッジの検出と軽減、さらにグローバルな分散型軽減の分離に基づいています。多くの企業では、検出し、攻撃を軽減するサードパーティ製のソリューションを使用します。エッジ能力の拡大、個人または特定のエッジに対して、攻撃の重要性が非常に低いことが明らかになりました。固有の構成では、ための検出と緩和策のコンポーネントに分割しました。端にあるグローバル リスクの軽減を維持しながら、飽和点に近い場所に攻撃を検出することを可能にする多階層の検出を導入しました。この戦略により、複数の同時攻撃に対処します。</span><span class="sxs-lookup"><span data-stu-id="10433-p102">Given our unique nature, Microsoft uses detection and mitigation processes that differ from those used by large enterprises. Our strategy is based on a separation of detection and mitigation, as well as global, distributed mitigation through our many edges. Many enterprises use third-party solutions which detect and mitigate attacks at the edge. As our edge capacity grew, it became clear that the significance of any attack against individual or particular edges was very low. Because of our unique configuration, we have separated the detection and mitigation components. We have deployed multi-tiered detection that enables us to detect attacks closer to their saturation points while maintaining global mitigation at the edge. This strategy ensures we can handle multiple simultaneous attacks.</span></span>

<span data-ttu-id="10433-p103">DoS 攻撃からマイクロソフトが採用されている最も効果的かつ低コストの防御機能の 1 つは、攻撃対象領域を削減します。これにより、分析、処理、およびデータのインラインのスクラブとは異なり、端にある不要なトラフィックをドロップすることです。</span><span class="sxs-lookup"><span data-stu-id="10433-p103">One of the most effective and low-cost defenses employed by Microsoft against DoS attacks is to reduce our attack surface. Doing so enables us to drop unwanted traffic at the edge, as opposed to analyzing, processing and scrubbing the data inline.</span></span>

<span data-ttu-id="10433-p104">パブリック ネットワーク インターフェイスでは、マイクロソフトは、ファイアウォール、ネットワーク アドレス変換、および IP フィルター処理関数の特別な目的のセキュリティ デバイスを使用します。グローバルにコストの等しい複数のパス (ECMP) ルーティングを使用します。グローバル ECMP ルーティングは、サービスに到達する複数のグローバル ・ パスがあることを確認するネットワークのフレームワークです。これらの複数のパスのおかげで、サービスへの攻撃に制限する領域からの攻撃の発生元: エンド ・ ユーザーはそれらの領域でのサービスに到達する他のパスを使用すると同様に他の地域がこのような攻撃の影響を受けるにする必要があります。当社の内部 DoS 相関関連づけおよび検出を使用するシステム フローのデータ、パフォーマンスの測定値およびその他の情報を開発しました。これは、Microsoft ネットワーク上のさまざまなポイントから収集されたデータを分析し、Microsoft Azure 内で実行されている hyperscale のクラウド サービスとサービス。間のワークロードの DoS のインシデント対応チームは、チーム、エスカレーションの基準、およびさまざまなチームの連携し、インシデントの処理のためのプロトコル間での役割と責任の範囲を識別します。これらのソリューションでは、DoS 攻撃からのネットワーク ・ ベースの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="10433-p104">At the interface with the public network, Microsoft uses special-purpose security devices for firewall, network address translation, and IP filtering functions. We also use global equal-cost multi-path (ECMP) routing. Global ECMP routing is a network framework that ensures there are multiple global paths to reach a service. Thanks to these multiple paths, an attack against the service should be limited to the region from which the attack originates – other regions should be unaffected by this attack, as end users would use other paths to reach the service in those regions. We have also developed our own internal DoS correlation and detection system that uses flow data, performance metrics and other information. This is a hyperscale cloud service running within Microsoft Azure which analyzes data collected from various points on Microsoft networks and services. A cross-workload DoS incident response team identifies the roles and responsibilities across teams, the criteria for escalations, and the protocols for engaging various teams and for incident handling. These solutions provide network-based protection against DoS attacks.</span></span>

<span data-ttu-id="10433-126">最後に、クラウド ベースのワークロードは、プロトコルに基づく最適化のしきい値を構成し、帯域幅の使用は、一意にそのワークロードを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10433-126">Finally, cloud-based workloads are configured with optimized thresholds based on their protocol and bandwidth usage needs to uniquely protect that workload.</span></span>
