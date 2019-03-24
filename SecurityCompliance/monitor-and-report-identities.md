---
title: Microsoft 365 セキュリティで id を監視および報告する
description: 組織内の id を監視し、疑わしいまたは危険な動作を追跡する方法について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、id
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4b2dfec483f4365c7eff132e2a2401734358ad7a
ms.sourcegitcommit: ef27da3ea5340d6e7a2eaa1288e2e005ef8e4788
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2019
ms.locfileid: "30791789"
---
# <a name="monitor-and-report-identities-in-microsoft-365-security"></a><span data-ttu-id="277ff-104">Microsoft 365 セキュリティで id を監視および報告する</span><span class="sxs-lookup"><span data-stu-id="277ff-104">Monitor and report identities in Microsoft 365 security</span></span>

[!include[Prerelease�information](prerelease.md)]

<span data-ttu-id="277ff-105">組織内の id を監視し、疑わしいまたは危険な動作を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="277ff-105">You can monitor the identities in your organization and keep track of suspicious or risky behaviors.</span></span> <span data-ttu-id="277ff-106">**監視 & レポート**の [ **id** ] カテゴリでは、次のものを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="277ff-106">In the **Identities** category of **Monitoring & reports**, you can track:</span></span>

* <span data-ttu-id="277ff-107">検出された異常が最も多いユーザー</span><span class="sxs-lookup"><span data-stu-id="277ff-107">Users with the most detected anomalies</span></span>
* <span data-ttu-id="277ff-108">条件付きアクセスポリシーによってリスクとして報告されるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="277ff-108">How many users are reported at risk by conditional access policies</span></span>
* <span data-ttu-id="277ff-109">組織内のグローバル管理者の数</span><span class="sxs-lookup"><span data-stu-id="277ff-109">The number of global admins in your org</span></span>

![監視 & レポートページの id カテゴリ](./media/security-docs/identities.png)

<span data-ttu-id="277ff-111">特定の検出があるユーザーについては、Windows Defender セキュリティセンターで特定の警告を調べて調査することができます。</span><span class="sxs-lookup"><span data-stu-id="277ff-111">For users with specific detections, you can explore the specific alert and investigate in Windows Defender security center.</span></span> <span data-ttu-id="277ff-112">検出には、未知の場所からサインインしたユーザーなどの異常が含まれます。</span><span class="sxs-lookup"><span data-stu-id="277ff-112">Detections include anomalies such as users who sign in from unfamiliar locations.</span></span>

<span data-ttu-id="277ff-113">リスクイベントの完全なセットについては、「 [Azure Active Directory のリスクイベント](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="277ff-113">For a complete set of risk events, see [Azure Active Directory risk events](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events).</span></span>
