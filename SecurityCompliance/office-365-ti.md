---
title: Office 365 脅威の調査および対応
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/20/2019
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
ms.openlocfilehash: c99712553646a6ceff22005952289b2ca3e1dbf4
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478186"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="55ea4-103">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="55ea4-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="55ea4-104">Office 365 の脅威の調査と応答機能[Advanced Threat Protection](office-365-atp.md)は、セキュリティアナリストおよび管理者が組織の office 365 ユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
- <span data-ttu-id="55ea4-105">攻撃を特定し、監視し、理解するための簡単な方法</span><span class="sxs-lookup"><span data-stu-id="55ea4-105">Making it easy to identify, monitor and understand attacks</span></span>
    
- <span data-ttu-id="55ea4-106">Exchange Online、SharePoint Online、OneDrive for Business、および Microsoft Teams での脅威への迅速な対応</span><span class="sxs-lookup"><span data-stu-id="55ea4-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
- <span data-ttu-id="55ea4-107">組織に対する攻撃を防止するために、洞察と知識を提供する</span><span class="sxs-lookup"><span data-stu-id="55ea4-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

- <span data-ttu-id="55ea4-108">メールベースの重要な脅威に対する自動化された[調査と対応](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="55ea4-108">Employing [automated investigation and response](automated-investigation-response-office.md) for critical email based threats</span></span>
    
<span data-ttu-id="55ea4-109">脅威の調査と応答の詳細と、開始する方法については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55ea4-109">Read this article to learn more about threat investigation and response, and how to get started.</span></span>
  
## <a name="threat-investigation-and-response-in-office-365"></a><span data-ttu-id="55ea4-110">Office 365 での脅威の調査と応答</span><span class="sxs-lookup"><span data-stu-id="55ea4-110">Threat investigation and response in Office 365</span></span>

<span data-ttu-id="55ea4-111">脅威の調査と応答の機能は、Office 365 セキュリティ&amp;コンプライアンスセンターで利用可能な脅威と、関連する応答アクションに関する洞察を促進します。</span><span class="sxs-lookup"><span data-stu-id="55ea4-111">Threat investigation and response capabilities help drive insights into threats and related response actions that are available in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="55ea4-112">これらの洞察は、組織のセキュリティチームが、電子メールまたはファイルベースの攻撃から Office 365 ユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-112">These insights can help your organization's security team protect Office 365 users from email- or file-based attacks.</span></span> <span data-ttu-id="55ea4-113">機能は、ユーザーアクティビティ、認証、電子メール、侵害された Pc、セキュリティインシデントなど、複数のソースからの信号を監視し、データを収集するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-113">The capabilities help monitor signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="55ea4-114">ビジネス意思決定者および Office 365 の全体管理者、セキュリティ管理者、およびセキュリティアナリストは、この情報を使用して、Office 365 ユーザーに対する脅威を理解し、それに対応し、知的財産を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-114">Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use this information to understand and respond to threats against Office 365 users and protect their intellectual property.</span></span>

## <a name="get-acquainted-with-the-threat-dashboard-explorer-and-incidents"></a><span data-ttu-id="55ea4-115">脅威ダッシュボード、エクスプローラー、インシデントについて理解する</span><span class="sxs-lookup"><span data-stu-id="55ea4-115">Get acquainted with the Threat dashboard, Explorer, and Incidents</span></span>

<span data-ttu-id="55ea4-116">脅威の調査と応答の機能は、 &amp;セキュリティコンプライアンスセンターにおいて、[脅威ダッシュボード](#threat-dashboard)、[エクスプローラー](#threat-explorer)、[インシデント](#incidents)、[アタックシミュレータ](attack-simulator.md)を含む、一連のツールと応答のワークフローとして表示されます。[応答の自動調査 &](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="55ea4-116">Threat investigation and response capabilities surface in the Security &amp; Compliance Center, as a set of tools and response workflows, including the [threat dashboard](#threat-dashboard), [Explorer](#threat-explorer), [Incidents](#incidents), [Attack Simulator](attack-simulator.md), and [Automated Investigation & Response](automated-investigation-response-office.md).</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="55ea4-117">脅威ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="55ea4-117">Threat dashboard</span></span>

<span data-ttu-id="55ea4-118">脅威ダッシュボード ([セキュリティダッシュボード](security-dashboard.md)とも呼ばれます) を使用して、どのような脅威が解決されたかをすばやく確認し、ビジネス意思決定者に対して Office 365 サービスがビジネスをどのようにセキュリティで保護しているかを視覚的に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-118">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![脅威ダッシュボード](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="55ea4-120">このダッシュボードを表示して使用するには&amp; 、セキュリティ/コンプライアンスセンターで、[**脅威管理** \> ]**ダッシュボード**に移動します。</span><span class="sxs-lookup"><span data-stu-id="55ea4-120">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="55ea4-121">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="55ea4-121">Threat Explorer</span></span>

<span data-ttu-id="55ea4-122">脅威[エクスプローラー (およびリアルタイム検出)](threat-explorer.md)を使用して脅威を分析し、時間の経過と共に攻撃の量を確認し、脅威ファミリ、攻撃インフラストラクチャなどによるデータの分析を行います。</span><span class="sxs-lookup"><span data-stu-id="55ea4-122">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="55ea4-123">脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティアナリストの調査ワークフローの出発点です。</span><span class="sxs-lookup"><span data-stu-id="55ea4-123">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>
  
![脅威エクスプローラー](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="55ea4-125">このレポートを表示して使用するには&amp; 、セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="55ea4-125">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
### <a name="incidents"></a><span data-ttu-id="55ea4-126">事件</span><span class="sxs-lookup"><span data-stu-id="55ea4-126">Incidents</span></span>

<span data-ttu-id="55ea4-127">インシデントリスト (調査とも呼ばれます) を使用して、フライトセキュリティインシデントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="55ea4-127">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="55ea4-128">インシデントは、不審な電子メールメッセージなどの脅威を追跡し、さらに調査と修復を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-128">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365 の現在の脅威インシデントの一覧](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="55ea4-130">組織の現在のインシデントの一覧を表示するには、セキュリティ&amp; /コンプライアンスセンターで、[**脅威管理** \>の**レビュー** \> **インシデント**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="55ea4-130">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![セキュリティ&amp; /コンプライアンスセンターで、[脅威管理\>のレビュー] を選択します。](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)
  
## <a name="learn-more-about-malware-and-threats"></a><span data-ttu-id="55ea4-132">マルウェアと脅威の詳細情報</span><span class="sxs-lookup"><span data-stu-id="55ea4-132">Learn more about malware and threats</span></span>

<span data-ttu-id="55ea4-133">Office 365 Advanced Threat Protection プラン2のサービスの一部として、セキュリティアナリストは既知の脅威に関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-133">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="55ea4-134">これは、ユーザーを安全に保つために実行できる追加の予防策/手順があるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-134">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![最近の脅威に関する情報を示すセキュリティ傾向](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="55ea4-136">これらの機能はどのように入手できますか?</span><span class="sxs-lookup"><span data-stu-id="55ea4-136">How do we get these capabilities?</span></span>

<span data-ttu-id="55ea4-137">Office 365 の脅威の調査と応答の機能は、Office 365 Advanced Threat Protection プラン2および Enterprise E5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="55ea4-137">Office 365 threat investigation and response capabilities are included in Office 365 Advanced Threat Protection Plan 2 and Enterprise E5.</span></span> 

> [!TIP]
> <span data-ttu-id="55ea4-138">これらの脅威の調査および応答機能を含まない Office 365 サブスクリプションが組織にある場合は、それらをアドオンとして Office 365 Advanced Threat Protection と共に購入することができます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-138">If your organization has an Office 365 subscription that does not include these threat investigation and response capabilities, you can purchase these as an add-on along with Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="55ea4-139">プランオプションの詳細については、「 [office 365 Platform Service Description: office &amp; 365 Security コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) 」および「[購入または編集 (office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55ea4-139">For more information about plan options, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span>
  
1. <span data-ttu-id="55ea4-140">Office 365 の全体管理者として[https://admin.microsoft.com](https://admin.microsoft.com) 、に移動して、office 365 の職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="55ea4-140">As an Office 365 global administrator, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="55ea4-141">[**管理者** \> **課金**] を選択して、現在のサブスクリプションに含まれる内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="55ea4-141">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 
    - <span data-ttu-id="55ea4-142">**Office 365 Enterprise E5**が表示されている場合は、組織に Office 365 Advanced Threat Protection プラン2があります (脅威の調査と応答の機能を含みます)。</span><span class="sxs-lookup"><span data-stu-id="55ea4-142">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2 (which includes threat investigation and response capabilities).</span></span> 
    - <span data-ttu-id="55ea4-143">**Office 365 Enterprise E3**または**Office 365 enterprise E1**などの別のサブスクリプションが表示される場合は、「Office 365 Advanced Threat Protection プラン2」を追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="55ea4-143">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="55ea4-144">(これを行うには、[**サブスクリプションの追加**] を選択します。)</span><span class="sxs-lookup"><span data-stu-id="55ea4-144">(To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="55ea4-145">Microsoft 365 管理センターで、[**ユーザー** \>の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="55ea4-145">In the Microsoft 365 admin center, choose **Users** \> **Active users**.</span></span>
    
4. <span data-ttu-id="55ea4-146">Office 365 Advanced Threat Protection プラン2ライセンスをアクティブなすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-146">Assign Office 365 Advanced Threat Protection Plan 2 licenses to all active users.</span></span> <span data-ttu-id="55ea4-147">(こののライセンスを持っているユーザーのみが、エクスプローラなどのレポートに表示されます)。</span><span class="sxs-lookup"><span data-stu-id="55ea4-147">(Only users who have a license for this will show up in reports, such as Explorer.)</span></span>
    
5. <span data-ttu-id="55ea4-148">Office 365 Advanced Threat Protection を使用する組織内のユーザーに役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="55ea4-148">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="55ea4-149">「[ユーザーに Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照し、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55ea4-149">See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span><br/>

  |<span data-ttu-id="55ea4-150">**実行する処理...**</span><span class="sxs-lookup"><span data-stu-id="55ea4-150">**To do this activity...**</span></span> <br/> |<span data-ttu-id="55ea4-151">**これらの役割の1つが必要です**</span><span class="sxs-lookup"><span data-stu-id="55ea4-151">**You must have one of these roles**</span></span> <br/> |  
  |:-----|:-----|
  |<span data-ttu-id="55ea4-152">脅威ダッシュボード (または新しい[セキュリティダッシュボード](security-dashboard.md)) を使用する</span><span class="sxs-lookup"><span data-stu-id="55ea4-152">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <span data-ttu-id="55ea4-153">最近の脅威または現在の脅威に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="55ea4-153">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="55ea4-154">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="55ea4-154">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="55ea4-155">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="55ea4-155">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="55ea4-156">セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="55ea4-156">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="55ea4-157">脅威[エクスプローラー (およびリアルタイム検出)](threat-explorer.md)を使用して脅威を分析する</span><span class="sxs-lookup"><span data-stu-id="55ea4-157">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>  <br/> |<span data-ttu-id="55ea4-158">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="55ea4-158">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="55ea4-159">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="55ea4-159">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="55ea4-160">セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="55ea4-160">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="55ea4-161">インシデント (調査とも呼ばれる) を表示する</span><span class="sxs-lookup"><span data-stu-id="55ea4-161">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="55ea4-162">インシデントに電子メールメッセージを追加する</span><span class="sxs-lookup"><span data-stu-id="55ea4-162">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="55ea4-163">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="55ea4-163">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="55ea4-164">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="55ea4-164">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="55ea4-165">セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="55ea4-165">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="55ea4-166">インシデントで電子メールアクションをトリガーする</span><span class="sxs-lookup"><span data-stu-id="55ea4-166">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="55ea4-167">疑わしい電子メールメッセージの検索と削除</span><span class="sxs-lookup"><span data-stu-id="55ea4-167">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="55ea4-168">Office 365 の全体管理者またはセキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="55ea4-168">Office 365 Global Administrator or Security Administrator</span></span>  <br/> <span data-ttu-id="55ea4-169">上記の役割の1つと検索と削除 (セキュリティ&amp;コンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="55ea4-169">One of the roles above and Search and Purge (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="55ea4-170">Office 365 Advanced Threat Protection プラン2を Microsoft Defender ATP と統合する</span><span class="sxs-lookup"><span data-stu-id="55ea4-170">Integrate Office 365 Advanced Threat Protection Plan 2 with Microsoft Defender ATP</span></span>  <br/> <span data-ttu-id="55ea4-171">Office 365 Advanced Threat Protection プラン2を SIEM サーバーと統合する</span><span class="sxs-lookup"><span data-stu-id="55ea4-171">Integrate Office 365 Advanced Threat Protection Plan 2 with a SIEM server</span></span>  <br/> |<span data-ttu-id="55ea4-172">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="55ea4-172">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="55ea4-173">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="55ea4-173">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="55ea4-174">追加のアプリケーション (Microsoft Defender セキュリティセンター、SIEM サーバーなど) で割り当てられる適切な役割</span><span class="sxs-lookup"><span data-stu-id="55ea4-174">Appropriate role assigned in additional applications (such as Microsoft Defender Security Center or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="55ea4-175">役割、役割グループ、およびアクセス許可の詳細については、「 [Office 365 &amp;セキュリティコンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55ea4-175">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="55ea4-176">次のステップ</span><span class="sxs-lookup"><span data-stu-id="55ea4-176">Next steps</span></span>

- [<span data-ttu-id="55ea4-177">脅威のトラッカーについて-新知識と注目</span><span class="sxs-lookup"><span data-stu-id="55ea4-177">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="55ea4-178">配信された悪意のある電子メールを検索して調査する (Office 365 の脅威の調査と応答)</span><span class="sxs-lookup"><span data-stu-id="55ea4-178">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="55ea4-179">Microsoft Defender Advanced Threat Protection を使用して Office 365 の脅威の調査と応答を統合する</span><span class="sxs-lookup"><span data-stu-id="55ea4-179">Integrate Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="55ea4-180">アタックシミュレータについて</span><span class="sxs-lookup"><span data-stu-id="55ea4-180">Learn about Attack Simulator</span></span>](attack-simulator.md)
  

