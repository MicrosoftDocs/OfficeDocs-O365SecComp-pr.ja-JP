---
title: Office 365 でのサービス拒否攻撃に対する防御
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
description: サービス拒否 (DoS) 攻撃の概要。
ms.openlocfilehash: cd099bcb225cfa5dd1f44f14d4b7813bef8f7442
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091021"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="76b42-103">Office 365 でのサービス拒否攻撃に対する防御</span><span class="sxs-lookup"><span data-stu-id="76b42-103">Defending Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="76b42-104">概要</span><span class="sxs-lookup"><span data-stu-id="76b42-104">Introduction</span></span>
<span data-ttu-id="76b42-105">microsoft は、microsoft Azure、microsoft Bing、microsoft Office 365、microsoft Dynamics 365、microsoft OneDrive、Skype、Xbox Live などの200を超えるクラウドサービスのための信頼できるインフラストラクチャを提供しています。グローバルクラウドでホストされています。100を超えるデータセンターのインフラストラクチャ。</span><span class="sxs-lookup"><span data-stu-id="76b42-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.</span></span>

<span data-ttu-id="76b42-p101">大規模なインターネットプレゼンスがあり、クラウドサービスを提供する多くの主要なインターネットプロパティを持つグローバル組織の場合、Microsoft はハッカーやその他の悪意のある個人にとって大きな共通の標的となります。ネットワーク--クライアントと Microsoft Cloud 間の通信レイヤーは、悪意のある攻撃の最大目標の1つです。実際、多くの場合、Microsoft は何らかの形式のネットワークベースの cyberattack を使用して継続的かつ永続的に実行されています。ほぼすべての時間で、Microsoft のインターネットプロパティの少なくとも1つは何らかの形で攻撃を受けています。このような攻撃から防御できる信頼性と永続的なリスク軽減システムがない場合、Microsoft のクラウドサービスはオフラインになり、お客様は利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="76b42-p101">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals. The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks. In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack. At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack. Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

<span data-ttu-id="76b42-111">Microsoft では、多層防御セキュリティ原則を使用して、クラウドサービスとネットワークを保護しています。</span><span class="sxs-lookup"><span data-stu-id="76b42-111">Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="76b42-112">サービス拒否攻撃の定義と現象</span><span class="sxs-lookup"><span data-stu-id="76b42-112">Definition and Symptoms of Denial-of-Service Attacks</span></span>
<span data-ttu-id="76b42-p102">ネットワークサービスを攻撃する方法の1つは、サービスのホストに対して多数の要求を作成し、ネットワークやサーバーが正当なユーザーにサービスを拒否することです。これは、サービス拒否 (DoS) 攻撃と呼ばれます。複数のアクター、エンドポイント、またはベクトルによって攻撃が実行されると、その攻撃は分散型サービス拒否 (DDoS) 攻撃と呼ばれます。この方法は、motives とターゲットが異なることがありますが、DoS および DDoS 攻撃は一般に、インターネットサイトまたはサービスが、一時的または無限に機能しないようにするための個人または個人の努力から構成されます。</span><span class="sxs-lookup"><span data-stu-id="76b42-p102">One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users. This is referred to as a denial-of-service (DoS) attack. When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack. Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="76b42-117">[米国のコンピュータエマージェンシーレディネスチーム](https://www.us-cert.gov/)(米国-CERT) は、次のものを含む DoS 攻撃の兆候を定義します。</span><span class="sxs-lookup"><span data-stu-id="76b42-117">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>
- <span data-ttu-id="76b42-118">ネットワークのパフォーマンスが異常に遅くなる (ファイルを開くとき、またはインターネットサイトにアクセスするとき)</span><span class="sxs-lookup"><span data-stu-id="76b42-118">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="76b42-119">Web サイトの利用不可</span><span class="sxs-lookup"><span data-stu-id="76b42-119">Unavailability of a Web site</span></span>
- <span data-ttu-id="76b42-120">Web サイトへのアクセス不可</span><span class="sxs-lookup"><span data-stu-id="76b42-120">Inability to access a Web site</span></span>
- <span data-ttu-id="76b42-121">受信したスパムが飛躍的に増加する</span><span class="sxs-lookup"><span data-stu-id="76b42-121">Dramatic increase in received spam</span></span>
- <span data-ttu-id="76b42-122">ワイヤレスまたは有線のインターネット接続の切断</span><span class="sxs-lookup"><span data-stu-id="76b42-122">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="76b42-123">Web またはインターネットサービスへのアクセスが長期間失われる</span><span class="sxs-lookup"><span data-stu-id="76b42-123">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="76b42-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="76b42-124">Related Topics</span></span>
- [<span data-ttu-id="76b42-125">サービス拒否攻撃に対する防御の主要な原則</span><span class="sxs-lookup"><span data-stu-id="76b42-125">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="76b42-126">Microsoft のサービス拒否防御戦略</span><span class="sxs-lookup"><span data-stu-id="76b42-126">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="76b42-127">サービス拒否攻撃に対する Microsoft クラウドサービスの防御</span><span class="sxs-lookup"><span data-stu-id="76b42-127">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
