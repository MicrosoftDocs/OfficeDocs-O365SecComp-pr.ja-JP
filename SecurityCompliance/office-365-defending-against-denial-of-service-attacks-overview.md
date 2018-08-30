---
title: Office 365 のサービス拒否の攻撃に対する防御
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
description: サービス拒否 (DoS) 攻撃の概要について説明します。
ms.openlocfilehash: b5a51ae332b32142d9ab993a29763b2160c3ce97
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531542"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="1e20f-103">Office 365 のサービス拒否の攻撃に対する防御</span><span class="sxs-lookup"><span data-stu-id="1e20f-103">Defending Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="1e20f-104">概要</span><span class="sxs-lookup"><span data-stu-id="1e20f-104">Introduction</span></span>
<span data-ttu-id="1e20f-105">マイクロソフトでは、200 以上のクラウド サービスについて、Microsoft Azure、マイクロソフトの Bing、Microsoft Office 365、Microsoft Dynamics 365、マイクロソフトの OneDrive、Skype、および Xbox Live を含む、グローバル クラウドでホストされている信頼できるインフラストラクチャを提供してください。100 以上のデータ センターのインフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="1e20f-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.</span></span>

<span data-ttu-id="1e20f-p101">重要なインターネット プレゼンスとクラウド サービスを提供する多くの著名なインターネット プロパティをグローバルな組織としては、マイクロソフトは、ハッカーや悪意のある他のユーザーの大規模な一般的なターゲットをします。ネットワーク クライアントとマイクロソフトのクラウド--間の通信レイヤーは、悪意のある攻撃の最大のターゲットのいずれかです。実際には、長年にわたって Microsoft が行われて継続的に永続的にネットワーク ・ ベースの cyberattack のいくつかのフォームの下にあります。、ほぼ常にマイクロソフトのインターネットのプロパティの少なくとも 1 つが発生している攻撃のいくつかのフォームです。信頼性と永続的なリスクの軽減、システムでこれらの攻撃を防ぐことができますマイクロソフトのクラウド サービスがなければ、オフラインにしてお客様に利用できません。</span><span class="sxs-lookup"><span data-stu-id="1e20f-p101">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals. The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks. In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack. At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack. Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

<span data-ttu-id="1e20f-111">マイクロソフトでは、そのクラウド サービスとネットワークを保護するのに多層防御のセキュリティの原則を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e20f-111">Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="1e20f-112">定義と、サービス拒否の攻撃の症状</span><span class="sxs-lookup"><span data-stu-id="1e20f-112">Definition and Symptoms of Denial-of-Service Attacks</span></span>
<span data-ttu-id="1e20f-p102">ネットワーク サービスを攻撃する方法の 1 つでは、サービスのホストに対するネットワークと正当なユーザーにサービスを拒否するようにサーバーが過負荷に多くの要求を作成します。これはサービス拒否 (DoS) 攻撃と呼ばれます。攻撃が実行すると、複数のアクター、エンドポイント、またはベクトルでは分散型サービス拒否 (DDoS) 攻撃と呼ばれます。手段、動機、およびターゲットが異なる場合、正しく機能しているからか、まったく、一時的または永続的にサービスやインターネット サイトを防ぐために個人または個人の努力の一般に DoS と DDoS 攻撃で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1e20f-p102">One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users. This is referred to as a denial-of-service (DoS) attack. When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack. Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="1e20f-117">(U. s. 証明書)、[米国のコンピューター緊急対応チーム](https://www.us-cert.gov/)には、DoS 攻撃の兆候が定義されています。</span><span class="sxs-lookup"><span data-stu-id="1e20f-117">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>
- <span data-ttu-id="1e20f-118">ネットワークのパフォーマンスの低下を通常 (とファイルを開く、またはインターネット サイトにアクセスする)</span><span class="sxs-lookup"><span data-stu-id="1e20f-118">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="1e20f-119">Web サイトが使用できません。</span><span class="sxs-lookup"><span data-stu-id="1e20f-119">Unavailability of a Web site</span></span>
- <span data-ttu-id="1e20f-120">Web サイトにアクセスすることができません。</span><span class="sxs-lookup"><span data-stu-id="1e20f-120">Inability to access a Web site</span></span>
- <span data-ttu-id="1e20f-121">受信したスパムの激増</span><span class="sxs-lookup"><span data-stu-id="1e20f-121">Dramatic increase in received spam</span></span>
- <span data-ttu-id="1e20f-122">ワイヤレスやワイヤード (有線) のインターネット接続の切断</span><span class="sxs-lookup"><span data-stu-id="1e20f-122">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="1e20f-123">Web または任意のインターネット サービスへのアクセスの長期的な損失</span><span class="sxs-lookup"><span data-stu-id="1e20f-123">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e20f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e20f-124">Related Topics</span></span>
- [<span data-ttu-id="1e20f-125">サービス拒否攻撃に対する防御の主要な原則</span><span class="sxs-lookup"><span data-stu-id="1e20f-125">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="1e20f-126">マイクロソフトのサービス拒否攻撃の防御戦略</span><span class="sxs-lookup"><span data-stu-id="1e20f-126">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="1e20f-127">マイクロソフトのクラウド サービスをサービス拒否の攻撃を防御</span><span class="sxs-lookup"><span data-stu-id="1e20f-127">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
