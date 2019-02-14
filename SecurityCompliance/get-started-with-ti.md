---
title: Office 365 脅威インテリジェンスの概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 38e9b67f-d188-490f-bc91-a1ae4b270441
ms.collection:
- M365-security-compliance
description: Office 365 の脅威インテリジェンスおよび開始する方法について説明します。
ms.openlocfilehash: f4480e6cdf5a845f591ad118858703dee4d4e631
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995238"
---
# <a name="get-started-with-office-365-advanced-threat-protection-plan-2-formerly-office-365-threat-intelligence"></a><span data-ttu-id="c4787-103">Office 365 高度な脅威保護計画 2 (以前、Office 365 の脅威インテリジェンス) を開始します。</span><span class="sxs-lookup"><span data-stu-id="c4787-103">Get started with Office 365 Advanced Threat Protection Plan 2 (formerly Office 365 Threat Intelligence)</span></span>

<span data-ttu-id="c4787-p101">組織のセキュリティ チームの一部の場合は、攻撃からユーザーを保護するために脅威のインテリジェンス機能を使用できます。Office 365 高度な脅威保護計画 2 (以前、Office 365 の脅威インテリジェンス) では、セキュリティ アナリストおよび管理者の意見をバブルでユーザーを安全に保つことし、で起こっているかに基づいてどのようなアクションを識別するは、Office 365 環境です。これらの情報は、脅威インテリジェンス データとシステムの動作や不審な動作を攻撃に対応するスポット カラーのパターンを包括的なリポジトリに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c4787-p101">If you are part of your organization's security team, you can use Threat Intelligence capabilities to protect your users from attacks. Office 365 Advanced Threat Protection Plan 2 (formerly Office 365 Threat Intelligence) helps security analysts and administrators keep users safe by bubbling up insights and identifying action based on what is happening in their your Office 365 environment. These insights are based on a comprehensive repository of threat intelligence data and systems to spot patterns that correspond to attack behaviors and suspicious activity.</span></span>
  
<span data-ttu-id="c4787-107">脅威インテリジェンスおよび開始する方法の詳細については、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4787-107">Read this article to learn more about Threat Intelligence and how to get started.</span></span>
  
## <a name="what-is-threat-intelligence"></a><span data-ttu-id="c4787-108">脅威インテリジェンスとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="c4787-108">What is Threat Intelligence?</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4787-p102">2019 の 2 月に開始し、今後数か月にロールアウト、Office 365 の脅威インテリジェンスは Office 365 高度な脅威保護計画 2、あらたな脅威保護機能となりつつあります。詳細については、 [Office 365 の高度な脅威保護の計画と価格設定](https://products.office.com/exchange/advance-threat-protection)と[Office 365 高度な脅威保護サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4787-p102">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="c4787-p103">脅威インテリジェンスの見識や Office 365 のセキュリティで使用できる情報のコレクションでは&amp;コンプライアンス センターです。これらの処理により、組織のセキュリティ チームが Office 365 のユーザーを攻撃から保護するのに役立ちます。脅威インテリジェンスは、信号を監視し、ユーザーの利用状況、認証、電子メール、セキュリティを侵害されたコンピューターは、セキュリティ問題など、複数のソースからデータを収集します。理解し、Office 365 のユーザーと知的に対する脅威に対応するビジネスの意思決定者と Office 365 のグローバル管理者、セキュリティ管理者、およびセキュリティ アナリストすべて情報を使用して Office 365 の脅威インテリジェンスを提供します。プロパティです。</span><span class="sxs-lookup"><span data-stu-id="c4787-p103">Threat Intelligence is a collection of insights and information available in the Office 365 Security &amp; Compliance Center. These insights can help your organization's security team protect Office 365 users from attacks. Threat Intelligence monitors signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents. Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use the information Office 365 Threat Intelligence provides to understand and respond to threats against Office 365 users and intellectual property.</span></span>
  
## <a name="get-acquainted-with-the-threat-dashboard-explorer-and-incidents"></a><span data-ttu-id="c4787-115">脅威のダッシュ ボード、エクスプ ローラー、およびインシデントに慣れる</span><span class="sxs-lookup"><span data-stu-id="c4787-115">Get acquainted with the Threat dashboard, Explorer, and Incidents</span></span>

<span data-ttu-id="c4787-116">セキュリティ インテリジェンスのサーフェスの脅威&amp;ツール、レポート、[ダッシュ ボードの脅威](get-started-with-ti.md#dashboard)、[脅威のエクスプ ローラー](get-started-with-ti.md#explorer)、[インシデント](get-started-with-ti.md#incidents)などのセットとして、コンプライアンスの中心です。</span><span class="sxs-lookup"><span data-stu-id="c4787-116">Threat Intelligence surfaces in the Security &amp; Compliance Center, as a set of tools and reports, including the [Threat dashboard](get-started-with-ti.md#dashboard), [Threat Explorer](get-started-with-ti.md#explorer), and [Incidents](get-started-with-ti.md#incidents).</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="c4787-117">脅威のダッシュ ボード</span><span class="sxs-lookup"><span data-stu-id="c4787-117">Threat dashboard</span></span>

<span data-ttu-id="c4787-118">どのような脅威の対処をすばやく表示する (これも呼びます[セキュリティ ダッシュ ボード](security-dashboard.md)) 脅威ダッシュ ボードを使用し、ビジネスの意思決定者にレポートを視覚的にどのように Office 365 サービスはセキュリティで保護するお客様のビジネスです。</span><span class="sxs-lookup"><span data-stu-id="c4787-118">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![脅威インテリジェンスのダッシュ ボード](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="c4787-120">表示、セキュリティで、デジタル ダッシュ ボードを使用して&amp;コンプライアンス センターでは、**脅威の管理**に移動\>**ダッシュ ボード**です。</span><span class="sxs-lookup"><span data-stu-id="c4787-120">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="c4787-121">脅威のエクスプ ローラー</span><span class="sxs-lookup"><span data-stu-id="c4787-121">Threat Explorer</span></span>

<span data-ttu-id="c4787-p104">脅威を分析し、時間の経過と共に攻撃のボリュームを参照してください、脅威の種類、攻撃者のインフラストラクチャ、データの分析にも (エクスプ ローラー) の脅威のエクスプ ローラーを使用します。脅威のエクスプ ローラーは、任意のセキュリティ ・ アナリストの調査のワークフローの開始場所です。</span><span class="sxs-lookup"><span data-stu-id="c4787-p104">Use the Threat Explorer (this is also called Explorer) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more. Threat Explorer is the starting place for any security analyst's investigation workflow.</span></span>
  
![脅威のエクスプ ローラー](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="c4787-125">表示、セキュリティで、このレポートを使用して&amp;コンプライアンス センターでは、**脅威の管理**に移動\>**エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="c4787-125">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
 ### <a name="incidents"></a><span data-ttu-id="c4787-126">インシデント</span><span class="sxs-lookup"><span data-stu-id="c4787-126">Incidents</span></span>

<span data-ttu-id="c4787-p105">(調査) インシデントの一覧を使用して、セキュリティ インシデントのフライトでの一覧を参照してください。インシデントは、不審な電子メール メッセージなどの脅威を追跡し、さらに調査し、改善策の実施に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4787-p105">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents. Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365 の脅威インテリジェンスの現在の問題の一覧](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="c4787-130">セキュリティで、組織の現在の問題の一覧を表示するのには&amp;コンプライアンス センターでは、**脅威の管理**に移動\>**レビュー** \> **インシデント**です。</span><span class="sxs-lookup"><span data-stu-id="c4787-130">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![セキュリティで&amp;コンプライアンス センターでは、脅威の管理を選択して\>のレビュー](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)
  
## <a name="learn-more-about-malware-amp-threats"></a><span data-ttu-id="c4787-132">マルウェアの詳細については&amp;の脅威</span><span class="sxs-lookup"><span data-stu-id="c4787-132">Learn more about Malware &amp; Threats</span></span>

<span data-ttu-id="c4787-p106">Office 365 高度な脅威保護計画 2 ソリューションの一部として、セキュリティ アナリストは、既知の脅威に関する詳細情報を確認できます。追加予防対策と手順のユーザーを安全に保つことを実行することができますがあるかどうかを判断するのには便利です。</span><span class="sxs-lookup"><span data-stu-id="c4787-p106">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat. This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![セキュリティ トレンドの最新の脅威に関する情報を表示](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-threat-intelligence"></a><span data-ttu-id="c4787-136">脅威インテリジェンスはどうすれば?</span><span class="sxs-lookup"><span data-stu-id="c4787-136">How do we get Threat Intelligence?</span></span>

<span data-ttu-id="c4787-p107">**脅威インテリジェンスは 2 では Office 365 高度な脅威保護計画の一部をここ**に含まれるで[365 企業の Microsoft](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 ビジネス](https://www.microsoft.com/microsoft-365/business)、Office 365 のエンタープライズ E5 などの特定のサブスクリプションでは、Office 365教育 A5 などです。組織が Office 365 の分析ツールが含まれていないサブスクリプションの場合は、アドオンとして可能性のある ATP を購入できます。詳細については、 [Office 365 の高度な脅威保護の計画と価格設定](https://products.office.com/exchange/advance-threat-protection)と[Office 365 高度な脅威保護サービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4787-p107">**Threat Intelligence is now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span>
  
1. <span data-ttu-id="c4787-139">Office 365 グローバル管理者に移動します。[https://portal.office.com](https://portal.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c4787-139">As an Office 365 global administrator, go to [https://portal.office.com](https://portal.office.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="c4787-140">**Admin**を選択して\>**請求**をして、現在のサブスクリプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4787-140">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 

    - <span data-ttu-id="c4787-141">**Office 365 エンタープライズ E5**が表示された場合、組織が Office 365 高度な脅威保護計画 2、脅威のインテリジェンスが含まれていますと。</span><span class="sxs-lookup"><span data-stu-id="c4787-141">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2, which includes Threat Intelligence.</span></span> 
    - <span data-ttu-id="c4787-p108">**Office 365 エンタープライズ E3**や**Office 365 エンタープライズ E1**など、別のサブスクリプションを参照してください場合は、脅威の保護計画の 2 の詳細を追加することを検討します。(そのために、選択 **+ 追加のサブスクリプション**)。</span><span class="sxs-lookup"><span data-stu-id="c4787-p108">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Advanced Threat Protection Plan 2. (To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="c4787-144">Office 365 管理センターで、[**ユーザ**] を選択します\>**アクティブなユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="c4787-144">In the Office 365 admin center, choose **Users** \> **Active users**.</span></span>
    
5. <span data-ttu-id="c4787-p109">すべてのアクティブなユーザーに Office 365 の高度な脅威保護のライセンスを割り当てます。(脅威インテリジェンス機能のライセンスを持つユーザーのみが表示レポートには、エクスプ ローラーなど)。</span><span class="sxs-lookup"><span data-stu-id="c4787-p109">Assign Office 365 Advanced Threat Protection licenses to all active users. (Only users who have a license for Threat Intelligence capabilities will show up in reports, such as Explorer.)</span></span>
    
6. <span data-ttu-id="c4787-p110">Office 365 の脅威の高度な保護を担当する組織内のユーザーにロールを割り当てます。参照してください[Office 365 のセキュリティにアクセスできるように&amp;コンプライアンス センター](grant-access-to-the-security-and-compliance-center.md)、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4787-p110">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection. See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="c4787-149">**このアクティビティを実行する.**</span><span class="sxs-lookup"><span data-stu-id="c4787-149">**To do this activity...**</span></span> <br/> |<span data-ttu-id="c4787-150">**これらの役割のいずれかする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="c4787-150">**You must have one of these roles**</span></span> <br/> |
|<span data-ttu-id="c4787-151">脅威のダッシュ ボード (または[セキュリティ ダッシュ ボード](security-dashboard.md)) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4787-151">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span>  <br/> <span data-ttu-id="c4787-152">最新のまたは現在の脅威に関する情報を表示</span><span class="sxs-lookup"><span data-stu-id="c4787-152">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="c4787-153">Office 365 のグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="c4787-153">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="c4787-154">(Azure Active Directory 管理センターに割り当てられている) セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="c4787-154">Security Administrator (assigned in the Azure Active Directory admin center)</span></span>  <br/> <span data-ttu-id="c4787-155">(Azure Active Directory 管理センターに割り当てられている) セキュリティ リーダー</span><span class="sxs-lookup"><span data-stu-id="c4787-155">Security Reader (assigned in the Azure Active Directory admin center)</span></span>  <br/> |
|<span data-ttu-id="c4787-156">脅威のエクスプ ローラー (エクスプ ローラーとも呼ばれます) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4787-156">Use Threat Explorer (also referred to as Explorer)</span></span>  <br/> <span data-ttu-id="c4787-157">脅威を分析します。</span><span class="sxs-lookup"><span data-stu-id="c4787-157">Analyze threats</span></span>  <br/> |<span data-ttu-id="c4787-158">Office 365 のグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="c4787-158">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="c4787-159">セキュリティ管理者 (セキュリティに割り当てられている&amp;コンプライアンス センター)</span><span class="sxs-lookup"><span data-stu-id="c4787-159">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="c4787-160">セキュリティ リーダー (セキュリティに割り当てられている&amp;コンプライアンス センター)</span><span class="sxs-lookup"><span data-stu-id="c4787-160">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
|<span data-ttu-id="c4787-161">ビューのインシデント (調査とも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="c4787-161">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="c4787-162">インシデントに電子メール メッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="c4787-162">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="c4787-163">Office 365 のグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="c4787-163">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="c4787-164">セキュリティ管理者 (セキュリティに割り当てられている&amp;コンプライアンス センター)</span><span class="sxs-lookup"><span data-stu-id="c4787-164">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="c4787-165">セキュリティ リーダー (セキュリティに割り当てられている&amp;コンプライアンス センター)</span><span class="sxs-lookup"><span data-stu-id="c4787-165">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
|<span data-ttu-id="c4787-166">インシデントの電子メール アクションをトリガー</span><span class="sxs-lookup"><span data-stu-id="c4787-166">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="c4787-167">検索し、不審な電子メール メッセージを削除</span><span class="sxs-lookup"><span data-stu-id="c4787-167">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="c4787-168">Office 365 グローバル アドミニストレーターまたはセキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="c4787-168">Office 365 Global Administrator or Security Administrator</span></span>  <br/> <span data-ttu-id="c4787-169">上の役割と検索と削除のいずれか (セキュリティに割り当てられている&amp;コンプライアンス センター)</span><span class="sxs-lookup"><span data-stu-id="c4787-169">One of the roles above and Search and Purge (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
|<span data-ttu-id="c4787-170">Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する</span><span class="sxs-lookup"><span data-stu-id="c4787-170">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>  <br/> <span data-ttu-id="c4787-171">SIEM サーバーと Office 365 の脅威インテリジェンスを統合します。</span><span class="sxs-lookup"><span data-stu-id="c4787-171">Integrate Office 365 Threat Intelligence with a SIEM server</span></span>  <br/> |<span data-ttu-id="c4787-172">Office 365 のグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="c4787-172">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="c4787-173">セキュリティ管理者 (セキュリティに割り当てられている&amp;コンプライアンス センター)</span><span class="sxs-lookup"><span data-stu-id="c4787-173">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="c4787-174">適切なロールがその他のアプリケーション (Windows Defender の高度な脅威保護のポータル、SIEM サーバーなど) に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c4787-174">Appropriate role assigned in additional applications (such as Windows Defender Advanced Threat Protection portal or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="c4787-175">役割、役割グループ、およびアクセス許可の詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="c4787-175">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="c4787-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="c4787-176">Next steps</span></span>

- [<span data-ttu-id="c4787-177">脅威のトラッカーが、注目すべき新しいについてください。</span><span class="sxs-lookup"><span data-stu-id="c4787-177">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="c4787-178">検索し、(Office 365 の脅威インテリジェンス) に配信された悪意のある電子メールを調査</span><span class="sxs-lookup"><span data-stu-id="c4787-178">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="c4787-179">Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する</span><span class="sxs-lookup"><span data-stu-id="c4787-179">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="c4787-180">攻撃シミュレータについてください。</span><span class="sxs-lookup"><span data-stu-id="c4787-180">Learn about Attack Simulator</span></span>](attack-simulator.md)
  

