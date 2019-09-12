---
title: Office 365 脅威の調査および対応
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/23/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection の脅威インテリジェンス機能が、組織に対する脅威を調査し、マルウェア、フィッシング、および Office 365 がユーザーに代わって検出したその他の攻撃に対応し、脅威を検索する方法について説明します。切り替える.
ms.openlocfilehash: 0edf68f3383759a4cffd9cb7c25260a51913beb0
ms.sourcegitcommit: ff370e93b792204547694139ef99bc0848304570
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "36852769"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="e6dc6-103">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="e6dc6-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="e6dc6-104">Office 365 の脅威の調査と応答機能[Advanced Threat Protection](office-365-atp.md)は、セキュリティアナリストおよび管理者が組織の office 365 ユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
- <span data-ttu-id="e6dc6-105">Cyberattacks の識別、監視、理解を容易にする</span><span class="sxs-lookup"><span data-stu-id="e6dc6-105">Making it easy to identify, monitor and understand cyberattacks</span></span>
    
- <span data-ttu-id="e6dc6-106">Exchange Online、SharePoint Online、OneDrive for Business、および Microsoft Teams での脅威への迅速な対応</span><span class="sxs-lookup"><span data-stu-id="e6dc6-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
- <span data-ttu-id="e6dc6-107">組織に対する cyberattacks を防止するためにセキュリティ操作を支援するための洞察と知識の提供</span><span class="sxs-lookup"><span data-stu-id="e6dc6-107">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>

- <span data-ttu-id="e6dc6-108">重要な電子メールベースの脅威に対する自動化された[調査と対応](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-108">Employing [automated investigation and response](automated-investigation-response-office.md) for critical email-based threats</span></span>
    
<span data-ttu-id="e6dc6-109">脅威の調査と応答の機能は、Office 365 セキュリティ&amp;コンプライアンスセンターで利用可能な脅威と関連する応答アクションについての洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-109">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="e6dc6-110">これらの洞察は、組織のセキュリティチームが、電子メールまたはファイルベースの攻撃から Office 365 ユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-110">These insights can help your organization's security team protect Office 365 users from email- or file-based attacks.</span></span> <span data-ttu-id="e6dc6-111">機能は、ユーザーアクティビティ、認証、電子メール、侵害された Pc、セキュリティインシデントなど、複数のソースからの信号を監視し、データを収集するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-111">The capabilities help monitor signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="e6dc6-112">ビジネス意思決定者および Office 365 の全体管理者、セキュリティ管理者、およびセキュリティアナリストは、この情報を使用して Office 365 ユーザーに対する脅威を理解し、それに対処し、知的財産権を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-112">Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use this information to understand and respond to threats against Office 365 users and protect intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="e6dc6-113">脅威の調査と応答のツールについて理解する</span><span class="sxs-lookup"><span data-stu-id="e6dc6-113">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="e6dc6-114">脅威の調査と応答の機能は、 &amp;セキュリティコンプライアンスセンターにおいて、[脅威ダッシュボード](#threat-dashboard)、[エクスプローラー](#threat-explorer)、[インシデント](#incidents)、[アタックシミュレータ](#attack-simulator)を含む、一連のツールと応答のワークフローとして表示されます。[応答の自動調査 &](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-114">Threat investigation and response capabilities surface in the Security &amp; Compliance Center, as a set of tools and response workflows, including the [threat dashboard](#threat-dashboard), [Explorer](#threat-explorer), [Incidents](#incidents), [Attack Simulator](#attack-simulator), and [Automated Investigation & Response](automated-investigation-response-office.md).</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="e6dc6-115">脅威ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="e6dc6-115">Threat dashboard</span></span>

<span data-ttu-id="e6dc6-116">脅威ダッシュボード ([セキュリティダッシュボード](security-dashboard.md)とも呼ばれます) を使用して、どのような脅威が解決されたかをすばやく確認し、ビジネス意思決定者に対して Office 365 サービスがビジネスをどのようにセキュリティで保護しているかを視覚的に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-116">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![脅威ダッシュボード](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="e6dc6-118">このダッシュボードを表示して使用するには&amp; 、セキュリティ/コンプライアンスセンターで、[**脅威管理** \> ]**ダッシュボード**に移動します。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-118">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>

<span data-ttu-id="e6dc6-119">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e6dc6-119">To learn more about</span></span> 
  
### <a name="threat-explorer"></a><span data-ttu-id="e6dc6-120">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="e6dc6-120">Threat Explorer</span></span>

<span data-ttu-id="e6dc6-121">脅威[エクスプローラー (およびリアルタイム検出)](threat-explorer.md)を使用して脅威を分析し、時間の経過と共に攻撃の量を確認し、脅威ファミリ、攻撃インフラストラクチャなどによるデータの分析を行います。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-121">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="e6dc6-122">脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティアナリストの調査ワークフローの出発点です。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-122">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>
  
![脅威エクスプローラー](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="e6dc6-124">このレポートを表示して使用するには&amp; 、セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-124">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
### <a name="incidents"></a><span data-ttu-id="e6dc6-125">事件</span><span class="sxs-lookup"><span data-stu-id="e6dc6-125">Incidents</span></span>

<span data-ttu-id="e6dc6-126">インシデントリスト (調査とも呼ばれます) を使用して、フライトセキュリティインシデントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-126">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="e6dc6-127">インシデントは、不審な電子メールメッセージなどの脅威を追跡し、さらに調査と修復を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-127">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365 の現在の脅威インシデントの一覧](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="e6dc6-129">組織の現在のインシデントの一覧を表示するには、セキュリティ&amp; /コンプライアンスセンターで、[**脅威管理** \>の**レビュー** \> **インシデント**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-129">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![セキュリティ&amp; /コンプライアンスセンターで、[脅威管理\>のレビュー] を選択します。](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="e6dc6-131">アタックシミュレータ</span><span class="sxs-lookup"><span data-stu-id="e6dc6-131">Attack Simulator</span></span>

<span data-ttu-id="e6dc6-132">アタックシミュレータを使用して、組織内で現実的な cyberattacks を設定して実行し、実際の cyberattack がビジネスに影響を与える前に、脆弱性のある人物を特定します。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-132">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="e6dc6-133">詳細については、「 [Office 365 のアタックシミュレータ](attack-simulator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-133">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="e6dc6-134">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="e6dc6-134">Automated investigation and response</span></span>

<span data-ttu-id="e6dc6-135">自動化された調査と応答 (AIR) 機能を使用して、コンテンツ、デバイス、およびユーザーを組織内の脅威から危険に関連付ける時間と労力を節約します。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-135">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="e6dc6-136">AIR プロセスは、特定の警告がトリガーされたとき、またはセキュリティ操作チームによって開始されたときに開始できます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-136">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="e6dc6-137">詳細については、「 [Office 365 での自動インシデント応答 (AIR)](automated-investigation-response-office.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-137">To learn more, see [Automated Incident Response (AIR) with Office 365](automated-investigation-response-office.md).</span></span> 
  
## <a name="threat-intelligence-widgets"></a><span data-ttu-id="e6dc6-138">脅威インテリジェンスウィジェット</span><span class="sxs-lookup"><span data-stu-id="e6dc6-138">Threat intelligence widgets</span></span>

<span data-ttu-id="e6dc6-139">Office 365 Advanced Threat Protection プラン2のサービスの一部として、セキュリティアナリストは既知の脅威に関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-139">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="e6dc6-140">これは、ユーザーを安全に保つために実行できる追加の予防策/手順があるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-140">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![最近の脅威に関する情報を示すセキュリティ傾向](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="e6dc6-142">これらの機能はどのように入手できますか?</span><span class="sxs-lookup"><span data-stu-id="e6dc6-142">How do we get these capabilities?</span></span>

<span data-ttu-id="e6dc6-143">Office 365 の脅威の調査と応答の機能は、Office 365 Advanced Threat Protection プラン2および Enterprise E5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-143">Office 365 threat investigation and response capabilities are included in Office 365 Advanced Threat Protection Plan 2 and Enterprise E5.</span></span> 

> [!TIP]
> <span data-ttu-id="e6dc6-144">これらの脅威の調査および応答機能を備えていない Office 365 サブスクリプションが組織にある場合、Office 365 Advanced Threat Protection プラン2をアドオンとして購入する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-144">If your organization has an Office 365 subscription that does not include these threat investigation and response capabilities, you can potentially purchase Office 365 Advanced Threat Protection Plan 2 as an add-on.</span></span> <span data-ttu-id="e6dc6-145">プランオプションの詳細については、「 [office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」および「[購入または編集 (office 365 for business)](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-145">For more information about plan options, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span>
  
1. <span data-ttu-id="e6dc6-146">Office 365 の全体管理者として[https://admin.microsoft.com](https://admin.microsoft.com) 、に移動して、office 365 の職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-146">As an Office 365 global administrator, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="e6dc6-147">[**管理者** \> **課金**] を選択して、現在のサブスクリプションに含まれる内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-147">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 
    - <span data-ttu-id="e6dc6-148">**Office 365 Enterprise E5**が表示されている場合は、組織に Office 365 Advanced Threat Protection プラン2があります (脅威の調査と応答の機能を含みます)。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-148">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2 (which includes threat investigation and response capabilities).</span></span> 
    - <span data-ttu-id="e6dc6-149">**Office 365 Enterprise E3**または**Office 365 enterprise E1**などの別のサブスクリプションが表示される場合は、「Office 365 Advanced Threat Protection プラン2」を追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-149">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="e6dc6-150">(これを行うには、[**サブスクリプションの追加**] を選択します。)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-150">(To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="e6dc6-151">Microsoft 365 管理センターで、[**ユーザー** \>の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-151">In the Microsoft 365 admin center, choose **Users** \> **Active users**.</span></span>
    
4. <span data-ttu-id="e6dc6-152">Office 365 Advanced Threat Protection プラン2ライセンスをアクティブなすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-152">Assign Office 365 Advanced Threat Protection Plan 2 licenses to all active users.</span></span> <span data-ttu-id="e6dc6-153">(こののライセンスを持っているユーザーのみが、エクスプローラなどのレポートに表示されます)。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-153">(Only users who have a license for this will show up in reports, such as Explorer.)</span></span>
    
5. <span data-ttu-id="e6dc6-154">Office 365 Advanced Threat Protection を使用する組織内のユーザーに役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-154">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="e6dc6-155">「[ユーザーに Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照し、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-155">See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span><br/>

  |<span data-ttu-id="e6dc6-156">**実行する処理...**</span><span class="sxs-lookup"><span data-stu-id="e6dc6-156">**To do this activity...**</span></span> <br/> |<span data-ttu-id="e6dc6-157">**これらの役割の1つが必要です**</span><span class="sxs-lookup"><span data-stu-id="e6dc6-157">**You must have one of these roles**</span></span> <br/> |  
  |:-----|:-----|
  |<span data-ttu-id="e6dc6-158">脅威ダッシュボード (または新しい[セキュリティダッシュボード](security-dashboard.md)) を使用する</span><span class="sxs-lookup"><span data-stu-id="e6dc6-158">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <span data-ttu-id="e6dc6-159">最近の脅威または現在の脅威に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="e6dc6-159">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="e6dc6-160">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e6dc6-160">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="e6dc6-161">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-161">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="e6dc6-162">セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-162">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="e6dc6-163">脅威[エクスプローラー (およびリアルタイム検出)](threat-explorer.md)を使用して脅威を分析する</span><span class="sxs-lookup"><span data-stu-id="e6dc6-163">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>  <br/> |<span data-ttu-id="e6dc6-164">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e6dc6-164">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="e6dc6-165">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-165">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="e6dc6-166">セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-166">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="e6dc6-167">インシデント (調査とも呼ばれる) を表示する</span><span class="sxs-lookup"><span data-stu-id="e6dc6-167">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="e6dc6-168">インシデントに電子メールメッセージを追加する</span><span class="sxs-lookup"><span data-stu-id="e6dc6-168">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="e6dc6-169">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e6dc6-169">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="e6dc6-170">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-170">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="e6dc6-171">セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-171">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="e6dc6-172">インシデントで電子メールアクションをトリガーする</span><span class="sxs-lookup"><span data-stu-id="e6dc6-172">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="e6dc6-173">疑わしい電子メールメッセージの検索と削除</span><span class="sxs-lookup"><span data-stu-id="e6dc6-173">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="e6dc6-174">Office 365 の全体管理者またはセキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="e6dc6-174">Office 365 Global Administrator or Security Administrator</span></span>  <br/> <span data-ttu-id="e6dc6-175">上記の役割の1つと検索と削除 (セキュリティ&amp;コンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-175">One of the roles above and Search and Purge (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="e6dc6-176">Office 365 Advanced Threat Protection プラン2を Microsoft Defender ATP と統合する</span><span class="sxs-lookup"><span data-stu-id="e6dc6-176">Integrate Office 365 Advanced Threat Protection Plan 2 with Microsoft Defender ATP</span></span>  <br/> <span data-ttu-id="e6dc6-177">Office 365 Advanced Threat Protection プラン2を SIEM サーバーと統合する</span><span class="sxs-lookup"><span data-stu-id="e6dc6-177">Integrate Office 365 Advanced Threat Protection Plan 2 with a SIEM server</span></span>  <br/> |<span data-ttu-id="e6dc6-178">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e6dc6-178">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="e6dc6-179">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-179">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="e6dc6-180">追加のアプリケーション (Microsoft Defender セキュリティセンター、SIEM サーバーなど) で割り当てられる適切な役割</span><span class="sxs-lookup"><span data-stu-id="e6dc6-180">Appropriate role assigned in additional applications (such as Microsoft Defender Security Center or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="e6dc6-181">役割、役割グループ、およびアクセス許可の詳細については、「 [Office 365 &amp;セキュリティコンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6dc6-181">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="e6dc6-182">次の手順</span><span class="sxs-lookup"><span data-stu-id="e6dc6-182">Next steps</span></span>

- [<span data-ttu-id="e6dc6-183">脅威のトラッカーについて-新知識と注目</span><span class="sxs-lookup"><span data-stu-id="e6dc6-183">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="e6dc6-184">配信された悪意のある電子メールを検索して調査する (Office 365 の脅威の調査と応答)</span><span class="sxs-lookup"><span data-stu-id="e6dc6-184">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="e6dc6-185">Microsoft Defender Advanced Threat Protection を使用して Office 365 の脅威の調査と応答を統合する</span><span class="sxs-lookup"><span data-stu-id="e6dc6-185">Integrate Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="e6dc6-186">アタックシミュレータについて</span><span class="sxs-lookup"><span data-stu-id="e6dc6-186">Learn about Attack Simulator</span></span>](attack-simulator.md)
  

