---
title: Microsoft 365 セキュリティセンターのセキュリティ状態を監視および報告する
description: Microsoft 365 セキュリティセンターが、保護とセキュリティの状態の概要を一目で確認できるようにする方法について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、状態
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 0a0bcbde7daa79aabda30013fca2560384545feb
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263129"
---
# <a name="monitor-and-report-security-status-in-microsoft-365-security-center"></a><span data-ttu-id="7db05-104">Microsoft 365 セキュリティセンターのセキュリティ状態を監視および報告する</span><span class="sxs-lookup"><span data-stu-id="7db05-104">Monitor and report security status in Microsoft 365 security center</span></span>

<span data-ttu-id="7db05-105">microsoft 365 セキュリティセンターは、microsoft 365 環境での保護とセキュリティの状態の概要を一目で確認できます。</span><span class="sxs-lookup"><span data-stu-id="7db05-105">The Microsoft 365 security center provides at a glance summary of protection and security status across your Microsoft 365 environment.</span></span>

<span data-ttu-id="7db05-106">セキュリティセンターには、日常業務の一部としてセキュリティアナリストや管理者が追跡するさまざまな領域をカバーする、**監視 & レポート**セクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7db05-106">The security center includes a **Monitoring & reports** section which features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span> <span data-ttu-id="7db05-107">ドリルダウンの場合、カードは詳細なレポートと、場合によっては管理オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="7db05-107">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="7db05-108">ビューをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="7db05-108">Customize views</span></span>

<span data-ttu-id="7db05-109">既定では、監視カードとレポートカードは次のカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="7db05-109">By default, monitoring and report cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="7db05-110">[id](monitor-and-report-identities.md) –ユーザーアカウントと資格情報</span><span class="sxs-lookup"><span data-stu-id="7db05-110">[Identities](monitor-and-report-identities.md) – user accounts and credentials</span></span>
* <span data-ttu-id="7db05-111">[データ](monitor-data.md)–電子メールとドキュメントのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="7db05-111">[Data](monitor-data.md) – email and document contents</span></span>
* <span data-ttu-id="7db05-112">[デバイス](monitor-devices.md)–コンピューター、携帯電話、その他のデバイス</span><span class="sxs-lookup"><span data-stu-id="7db05-112">[Devices](monitor-devices.md) – computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="7db05-113">[アプリ](monitor-apps.md)–プログラムと接続されたオンラインサービス</span><span class="sxs-lookup"><span data-stu-id="7db05-113">[Apps](monitor-apps.md) – programs and attached online services</span></span>

<span data-ttu-id="7db05-114">[**グループ化] トピック**に切り替えてカードを再配置し、次のようにグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7db05-114">Switch to **Group by topic**, to rearrange the cards and group them into the following:</span></span>

* <span data-ttu-id="7db05-115">**リスク**–リスクが発生している可能性がある、アカウントやデバイスなどのエンティティを強調するカード。</span><span class="sxs-lookup"><span data-stu-id="7db05-115">**Risk** – cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="7db05-116">これらのカードは、新しい脅威のキャンペーンや権限のあるクラウドアプリなど、潜在的なリスクのソースも強調しています。</span><span class="sxs-lookup"><span data-stu-id="7db05-116">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="7db05-117">**検出の傾向**–新しい脅威の検出、異常、およびポリシー違反を強調するカード</span><span class="sxs-lookup"><span data-stu-id="7db05-117">**Detection trends** – cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="7db05-118">**構成と正常性**–セキュリティ制御の構成と展開をカバーするカード (デバイスのオンボード状態を管理サービスに含める)</span><span class="sxs-lookup"><span data-stu-id="7db05-118">**Configuration and health** – cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="7db05-119">**other** –他のトピックに分類されていない他のすべてのカード</span><span class="sxs-lookup"><span data-stu-id="7db05-119">**Other** – all other cards not categorized under other topics</span></span>
