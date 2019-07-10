---
title: Office 365 の脅威の調査と対応についての作業を開始する
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 38e9b67f-d188-490f-bc91-a1ae4b270441
ms.collection:
- M365-security-compliance
description: Office 365 の脅威の調査と応答、および開始する方法について説明します。
ms.openlocfilehash: 8bd5e68abfa036d1257fb08fb1dd2b730f7de821
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599253"
---
# <a name="get-started-with-threat-investigation-and-response-in-office-365-advanced-threat-protection"></a><span data-ttu-id="5ee12-103">Office 365 Advanced Threat Protection での脅威の調査と応答の概要</span><span class="sxs-lookup"><span data-stu-id="5ee12-103">Get started with threat investigation and response in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="5ee12-104">組織のセキュリティチームに参加している場合は、Office 365 の脅威調査および応答機能を使用して、ユーザーを攻撃から保護することができます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-104">If you are part of your organization's security team, you can use Office 365 threat investigation and response capabilities to protect your users from attacks.</span></span> <span data-ttu-id="5ee12-105">Office 365 Advanced Threat Protection プラン 2 (旧称 Office 365 Threat 知能) を使用すると、セキュリティアナリストと管理者は、洞察を得て、Office の365で何が起こっているかに基づいて操作を識別することによって、ユーザーの安全を確保することができます。environment.</span><span class="sxs-lookup"><span data-stu-id="5ee12-105">Office 365 Advanced Threat Protection Plan 2 (formerly known as Office 365 Threat Intelligence) helps security analysts and administrators keep users safe by bubbling up insights and identifying action based on what is happening in their your Office 365 environment.</span></span> <span data-ttu-id="5ee12-106">これらの洞察は、脅威インテリジェンスのデータとシステムの包括的なリポジトリに基づいています。これは、攻撃の動作や不審な動作に対応するパターンを見つけるためのものです。</span><span class="sxs-lookup"><span data-stu-id="5ee12-106">These insights are based on a comprehensive repository of threat intelligence data and systems to spot patterns that correspond to attack behaviors and suspicious activity.</span></span>
  
<span data-ttu-id="5ee12-107">脅威の調査と応答の詳細と、開始する方法については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ee12-107">Read this article to learn more about threat investigation and response, and how to get started.</span></span>
  
## <a name="what-are-the-threat-investigation-and-response-capabilities-included-in-office-365"></a><span data-ttu-id="5ee12-108">Office 365 に含まれている脅威の調査および応答機能について</span><span class="sxs-lookup"><span data-stu-id="5ee12-108">What are the threat investigation and response capabilities included in Office 365?</span></span>

<span data-ttu-id="5ee12-109">脅威の調査と応答の機能は、Office 365 セキュリティ&amp;コンプライアンスセンターで利用可能な脅威と、関連する応答アクションに関する洞察を促進します。</span><span class="sxs-lookup"><span data-stu-id="5ee12-109">Threat investigation and response capabilities help drive insights into threats and related response actions that are available in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="5ee12-110">これらの洞察は、組織のセキュリティチームが電子メールやファイルベースの攻撃から Office 365 ユーザーを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-110">These insights can help your organization's security team protect Office 365 users from email or file based attacks.</span></span> <span data-ttu-id="5ee12-111">機能は、ユーザーアクティビティ、認証、電子メール、侵害された Pc、セキュリティインシデントなど、複数のソースからの信号を監視し、データを収集するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-111">The capabilities help monitor signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="5ee12-112">ビジネス意思決定者および Office 365 の全体管理者、セキュリティ管理者、およびセキュリティアナリストは、この情報を使用して、Office 365 ユーザーに対する脅威を理解し、それに対応し、知的財産を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-112">Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use this information to understand and respond to threats against Office 365 users and protect their intellectual property.</span></span>

## <a name="get-acquainted-with-the-threat-dashboard-explorer-and-incidents"></a><span data-ttu-id="5ee12-113">脅威ダッシュボード、エクスプローラー、インシデントについて理解する</span><span class="sxs-lookup"><span data-stu-id="5ee12-113">Get acquainted with the Threat dashboard, Explorer, and Incidents</span></span>

<span data-ttu-id="5ee12-114">これらの脅威の調査と応答能力は、 &amp;セキュリティコンプライアンスセンターで、[脅威ダッシュボード](#threat-dashboard)、[脅威エクスプローラ](#threat-explorer)、[インシデント](get-started-with-ti.md#incidents)、攻撃などの一連のツールと応答ワークフローとして、さまざまな機能を備えています。 [シミュレータ](attack-simulator.md)、および自動調査 & 応答。</span><span class="sxs-lookup"><span data-stu-id="5ee12-114">These threat investigation and response capabilities surface in the Security &amp; Compliance Center, as a set of tools and response workflows, including the [threat dashboard](#threat-dashboard), [Threat Explorer](#threat-explorer), [Incidents](get-started-with-ti.md#incidents), [Attack Simulator](attack-simulator.md), and Automated Investigations & Response.</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="5ee12-115">脅威ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="5ee12-115">Threat dashboard</span></span>

<span data-ttu-id="5ee12-116">脅威ダッシュボード ([セキュリティダッシュボード](security-dashboard.md)とも呼ばれます) を使用して、どのような脅威が解決されたかをすばやく確認し、ビジネス意思決定者に対して Office 365 サービスがビジネスをどのようにセキュリティで保護しているかを視覚的に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-116">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![脅威ダッシュボード](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="5ee12-118">このダッシュボードを表示して使用するには&amp; 、セキュリティ/コンプライアンスセンターで、[**脅威管理** \> ]**ダッシュボード**に移動します。</span><span class="sxs-lookup"><span data-stu-id="5ee12-118">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="5ee12-119">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="5ee12-119">Threat Explorer</span></span>

<span data-ttu-id="5ee12-120">脅威[エクスプローラー (およびリアルタイム検出)](threat-explorer.md)を使用して、脅威を分析し、時間の経過と共に攻撃の量を確認し、脅威ファミリ、攻撃インフラストラクチャなどによるデータの分析を行います。</span><span class="sxs-lookup"><span data-stu-id="5ee12-120">Use the [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="5ee12-121">脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティアナリストの調査ワークフローの出発点です。</span><span class="sxs-lookup"><span data-stu-id="5ee12-121">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>
  
![脅威エクスプローラー](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="5ee12-123">このレポートを表示して使用するには&amp; 、セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5ee12-123">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
 ### <a name="incidents"></a><span data-ttu-id="5ee12-124">事件</span><span class="sxs-lookup"><span data-stu-id="5ee12-124">Incidents</span></span>

<span data-ttu-id="5ee12-125">インシデントリスト (調査とも呼ばれます) を使用して、フライトセキュリティインシデントの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="5ee12-125">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="5ee12-126">インシデントは、不審な電子メールメッセージなどの脅威を追跡し、さらに調査と修復を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-126">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365 の現在の脅威インシデントの一覧](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="5ee12-128">組織の現在のインシデントの一覧を表示するには、セキュリティ&amp; /コンプライアンスセンターで、[**脅威管理** \>の**レビュー** \> **インシデント**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5ee12-128">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![セキュリティ&amp; /コンプライアンスセンターで、[脅威管理\>のレビュー] を選択します。](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)
  
## <a name="learn-more-about-malware-amp-threats"></a><span data-ttu-id="5ee12-130">マルウェア&amp;の脅威の詳細情報</span><span class="sxs-lookup"><span data-stu-id="5ee12-130">Learn more about Malware &amp; Threats</span></span>

<span data-ttu-id="5ee12-131">Office 365 Advanced Threat Protection プラン2のサービスの一部として、セキュリティアナリストは既知の脅威に関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-131">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="5ee12-132">これは、ユーザーを安全に保つために実行できる追加の予防策/手順があるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-132">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![最近の脅威に関する情報を示すセキュリティ傾向](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-threat-investigation-and-response-capabilities"></a><span data-ttu-id="5ee12-134">これらの脅威の調査および応答機能をどのように入手できますか。</span><span class="sxs-lookup"><span data-stu-id="5ee12-134">How do we get these Threat investigation and response capabilities?</span></span>

<span data-ttu-id="5ee12-135">Office 365 の脅威 Invesigation および応答機能は、Office 365 Advanced Threat Protection プラン2および Enterprise E5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ee12-135">Office 365 Threat Invesigation and Response capabilities are included in Office 365 Advanced Threat Protection Plan 2 and Enterprise E5.</span></span> 

> [!TIP]
> <span data-ttu-id="5ee12-136">これらの脅威の調査および応答機能を含まない Office 365 サブスクリプションが組織にある場合は、それらをアドオンとして Office 365 Advanced Threat Protection と共に購入することができます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-136">If your organization has an Office 365 subscription that does not include these threat investigation and response capabilities, you can purchase these as an add-on along with Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="5ee12-137">プランオプションの詳細については、「 [office 365 Platform Service Description: office &amp; 365 Security コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) 」および「[購入または編集 (office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ee12-137">For more information about plan options, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span>
  
1. <span data-ttu-id="5ee12-138">Office 365 の全体管理者として[https://admin.microsoft.com](https://admin.microsoft.com) 、に移動して、office 365 の職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5ee12-138">As an Office 365 global administrator, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="5ee12-139">[**管理者** \> **課金**] を選択して、現在のサブスクリプションに含まれる内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ee12-139">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 
    - <span data-ttu-id="5ee12-140">**Office 365 Enterprise E5**が表示されている場合は、組織に Office 365 Advanced Threat Protection プラン2があります (脅威の調査と応答の機能を含みます)。</span><span class="sxs-lookup"><span data-stu-id="5ee12-140">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2 (which includes threat investigation and response capabilities).</span></span> 
    - <span data-ttu-id="5ee12-141">**Office 365 Enterprise E3**または**Office 365 enterprise E1**などの別のサブスクリプションが表示される場合は、「Office 365 Advanced Threat Protection プラン2」を追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5ee12-141">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="5ee12-142">(これを行うには、[**サブスクリプションの追加**] を選択します。)</span><span class="sxs-lookup"><span data-stu-id="5ee12-142">(To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="5ee12-143">Microsoft 365 管理センターで、[**ユーザー** \>の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ee12-143">In the Microsoft 365 admin center, choose **Users** \> **Active users**.</span></span>
    
5. <span data-ttu-id="5ee12-144">Office 365 Advanced Threat Protection プラン2ライセンスをアクティブなすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-144">Assign Office 365 Advanced Threat Protection Plan 2 licenses to all active users.</span></span> <span data-ttu-id="5ee12-145">(こののライセンスを持っているユーザーのみが、エクスプローラなどのレポートに表示されます)。</span><span class="sxs-lookup"><span data-stu-id="5ee12-145">(Only users who have a license for this will show up in reports, such as Explorer.)</span></span>
    
6. <span data-ttu-id="5ee12-146">Office 365 Advanced Threat Protection を使用する組織内のユーザーに役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5ee12-146">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="5ee12-147">「[ユーザーに Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照し、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ee12-147">See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span><br/>

  |<span data-ttu-id="5ee12-148">**実行する処理...**</span><span class="sxs-lookup"><span data-stu-id="5ee12-148">**To do this activity...**</span></span> <br/> |<span data-ttu-id="5ee12-149">**これらの役割の1つが必要です**</span><span class="sxs-lookup"><span data-stu-id="5ee12-149">**You must have one of these roles**</span></span> <br/> |  
  |:-----|:-----|
  |<span data-ttu-id="5ee12-150">脅威ダッシュボード (または新しい[セキュリティダッシュボード](security-dashboard.md)) を使用する</span><span class="sxs-lookup"><span data-stu-id="5ee12-150">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <span data-ttu-id="5ee12-151">最近の脅威または現在の脅威に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="5ee12-151">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="5ee12-152">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="5ee12-152">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="5ee12-153">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="5ee12-153">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="5ee12-154">セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="5ee12-154">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="5ee12-155">脅威[エクスプローラー (およびリアルタイム検出)](threat-explorer.md)を使用して脅威を分析する</span><span class="sxs-lookup"><span data-stu-id="5ee12-155">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>  <br/> |<span data-ttu-id="5ee12-156">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="5ee12-156">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="5ee12-157">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="5ee12-157">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="5ee12-158">セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="5ee12-158">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="5ee12-159">インシデント (調査とも呼ばれる) を表示する</span><span class="sxs-lookup"><span data-stu-id="5ee12-159">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="5ee12-160">インシデントに電子メールメッセージを追加する</span><span class="sxs-lookup"><span data-stu-id="5ee12-160">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="5ee12-161">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="5ee12-161">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="5ee12-162">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="5ee12-162">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="5ee12-163">セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="5ee12-163">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="5ee12-164">インシデントで電子メールアクションをトリガーする</span><span class="sxs-lookup"><span data-stu-id="5ee12-164">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="5ee12-165">疑わしい電子メールメッセージの検索と削除</span><span class="sxs-lookup"><span data-stu-id="5ee12-165">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="5ee12-166">Office 365 の全体管理者またはセキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="5ee12-166">Office 365 Global Administrator or Security Administrator</span></span>  <br/> <span data-ttu-id="5ee12-167">上記の役割の1つと検索と削除 (セキュリティ&amp;コンプライアンスセンターで割り当てられたもの)</span><span class="sxs-lookup"><span data-stu-id="5ee12-167">One of the roles above and Search and Purge (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="5ee12-168">Office 365 Advanced Threat Protection プラン2を Microsoft Defender ATP と統合する</span><span class="sxs-lookup"><span data-stu-id="5ee12-168">Integrate Office 365 Advanced Threat Protection Plan 2 with Microsoft Defender ATP</span></span>  <br/> <span data-ttu-id="5ee12-169">Office 365 Advanced Threat Protection プラン2を SIEM サーバーと統合する</span><span class="sxs-lookup"><span data-stu-id="5ee12-169">Integrate Office 365 Advanced Threat Protection Plan 2 with a SIEM server</span></span>  <br/> |<span data-ttu-id="5ee12-170">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="5ee12-170">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="5ee12-171">セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)</span><span class="sxs-lookup"><span data-stu-id="5ee12-171">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="5ee12-172">追加のアプリケーション (Microsoft Defender セキュリティセンター、SIEM サーバーなど) で割り当てられる適切な役割</span><span class="sxs-lookup"><span data-stu-id="5ee12-172">Appropriate role assigned in additional applications (such as Microsoft Defender Security Center or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="5ee12-173">役割、役割グループ、およびアクセス許可の詳細については、「 [Office 365 &amp;セキュリティコンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ee12-173">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="5ee12-174">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5ee12-174">Next steps</span></span>

- [<span data-ttu-id="5ee12-175">脅威のトラッカーについて-新知識と注目</span><span class="sxs-lookup"><span data-stu-id="5ee12-175">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="5ee12-176">配信された悪意のある電子メールを検索して調査する (Office 365 の脅威の調査と応答)</span><span class="sxs-lookup"><span data-stu-id="5ee12-176">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="5ee12-177">Microsoft Defender Advanced Threat Protection を使用して Office 365 の脅威の調査と応答を統合する</span><span class="sxs-lookup"><span data-stu-id="5ee12-177">Integrate Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="5ee12-178">アタックシミュレータについて</span><span class="sxs-lookup"><span data-stu-id="5ee12-178">Learn about Attack Simulator</span></span>](attack-simulator.md)
  
## <a name="additional-information"></a><span data-ttu-id="5ee12-179">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="5ee12-179">Additional information</span></span>

- [<span data-ttu-id="5ee12-180">Office 365 Advanced Threat Protection プランと価格設定</span><span class="sxs-lookup"><span data-stu-id="5ee12-180">Office 365 Advanced Threat Protection plans and pricing</span></span>](https://products.office.com/exchange/advance-threat-protection) 

- [<span data-ttu-id="5ee12-181">Office 365 Advanced Threat Protection サービスの説明</span><span class="sxs-lookup"><span data-stu-id="5ee12-181">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
