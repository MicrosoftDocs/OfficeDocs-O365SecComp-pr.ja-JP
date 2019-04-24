---
title: Office 365 Cloud App security のセキュリティポリシーのリファレンス情報
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aef6c88f-7f47-40ef-9503-2b400e3bc6fd
description: Office 365 のアクティビティポリシーと異常検出ポリシーに関するヘルプを取得します。
ms.openlocfilehash: db44b6cbf5b8c2783cba9862107120d2c33c1559
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264629"
---
# <a name="security-policy-reference-information-for-office-365-cloud-app-security"></a><span data-ttu-id="bc21e-103">Office 365 Cloud App security のセキュリティポリシーのリファレンス情報</span><span class="sxs-lookup"><span data-stu-id="bc21e-103">Security policy reference information for Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="bc21e-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="bc21e-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="bc21e-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="bc21e-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="bc21e-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="bc21e-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="bc21e-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="bc21e-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="bc21e-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="bc21e-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="bc21e-109">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="bc21e-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="bc21e-110">ここでは、</span><span class="sxs-lookup"><span data-stu-id="bc21e-110">You are here!</span></span>  <br/> [<span data-ttu-id="bc21e-111">次の手順</span><span class="sxs-lookup"><span data-stu-id="bc21e-111">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |[<span data-ttu-id="bc21e-112">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="bc21e-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="bc21e-113">Office 365 Cloud App Security では、全体管理者またはセキュリティ管理者の場合、組織に対して次の2種類のポリシーを定義または編集することができます。</span><span class="sxs-lookup"><span data-stu-id="bc21e-113">With Office 365 Cloud App Security, if you are a global administrator or security administrator, you can define or edit two kinds of policies for your organization:</span></span>
  
- <span data-ttu-id="bc21e-114">定義する**[アクティビティポリシー](activity-policies-and-alerts.md)** 。</span><span class="sxs-lookup"><span data-stu-id="bc21e-114">**[Activity policies](activity-policies-and-alerts.md)** that you define.</span></span> <span data-ttu-id="bc21e-115">これらのポリシーは、疑わしいと定義されているアクティビティ (組織にとって通常とは別の地域/国の他の地域/国のユーザーがサインインしようとした場合や、1時間以内にユーザーに対して大量のサインイン試行が発生した場合など) に基づいています。.</span><span class="sxs-lookup"><span data-stu-id="bc21e-115">These policies are based on activities that you define as suspicious, such as users attempting to sign in with admin credentials in other regions/countries outside what's normal for your organization, or an extreme number of sign-in attempts for a user within an hour.</span></span> <span data-ttu-id="bc21e-116">詳細については、「 [Office 365 Cloud App Security のアクティビティポリシーと通知](activity-policies-and-alerts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc21e-116">To learn more, see [Activity policies and alerts in Office 365 Cloud App Security](activity-policies-and-alerts.md).</span></span>
    
- <span data-ttu-id="bc21e-117">Office 365 Cloud App Security を使用して、すぐに使用できる**[異常検出ポリシー](anomaly-detection-policies-in-ocas.md)** 。</span><span class="sxs-lookup"><span data-stu-id="bc21e-117">**[Anomaly detection policies](anomaly-detection-policies-in-ocas.md)** that are available "out of the box" with Office 365 Cloud App Security.</span></span> <span data-ttu-id="bc21e-118">これらのポリシーは、疑わしいアクティビティを検出する自動アルゴリズムに基づいています。</span><span class="sxs-lookup"><span data-stu-id="bc21e-118">These policies are based on automatic algorithms that detect suspicious activity.</span></span> <span data-ttu-id="bc21e-119">これらの既定のポリシーは、異常を監視し、通知を自動的にトリガーします。</span><span class="sxs-lookup"><span data-stu-id="bc21e-119">These default policies watch for anomalies and trigger alerts automatically.</span></span> <span data-ttu-id="bc21e-120">詳細については、「 [Office 365 Cloud App Security」の「異常検出ポリシー](anomaly-detection-policies-in-ocas.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc21e-120">To learn more, see [Anomaly detection policies in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md).</span></span>
    

