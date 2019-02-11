---
title: Office 365 Cloud App Security 展開後の利用に関する作業
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: 設定すると、Office 365 のクラウド アプリケーションのセキュリティを展開すると、次のように、構成が正しいこと、および定期的な確認作業の準備ができなことを確認するのには、特定のタスクを実行する必要があります。
ms.openlocfilehash: 71b6793f2e325fcba3431ba5157640b29814ad30
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603708"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="907ea-103">Office 365 Cloud App Security 展開後の利用に関する作業</span><span class="sxs-lookup"><span data-stu-id="907ea-103">Utilization activities after rolling out Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="907ea-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="907ea-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="907ea-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="907ea-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="907ea-106">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="907ea-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="907ea-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="907ea-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="907ea-108">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="907ea-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="907ea-109">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="907ea-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="907ea-110">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="907ea-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="907ea-111">コースです!</span><span class="sxs-lookup"><span data-stu-id="907ea-111">You are here!</span></span>  <br/> [<span data-ttu-id="907ea-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="907ea-112">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="907ea-p101">Office 365 のクラウド アプリケーションのセキュリティは、Office 365 エンタープライズ E5 に使用できます。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合、Office 365 のクラウド アプリケーションのセキュリティがアドオンとして購入できます。(グローバル管理者は、Office 365 管理センターを選択して**請求** \> **サブスクリプションを追加**します)。詳細についてを参照してください[Office 365 のプラットフォーム サービスの説明: Office 365 のセキュリティ&amp;コンプライアンス センター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) [購入またはビジネスのための Office 365 のアドオンを編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)するとします。</span><span class="sxs-lookup"><span data-stu-id="907ea-p101">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="907ea-116">設定して、Office 365 のクラウド アプリケーションのセキュリティを構成することが後、に Office 365 のグローバル管理者または組織のセキュリティ管理者としての使用率、特定のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="907ea-116">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span> 

<span data-ttu-id="907ea-p102">これらのタスクを実行していることを確認 Office 365 のクラウド アプリケーションのセキュリティが正しく構成されている、ポリシーが最新で、組織が Office 365 の値を実現していますをしてみましょう。これらのタスクを計画するためのガイドとしてこの資料を使用します。</span><span class="sxs-lookup"><span data-stu-id="907ea-p102">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365. Use this article as a guide to help you plan for these tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="907ea-p103">この資料で説明するタスクを実行するには、グローバル管理者またはセキュリティ管理者である必要があります。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="907ea-p103">You must be a global administrator or security administrator to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a><span data-ttu-id="907ea-121">初期設定と Office 365 のクラウド アプリケーションのセキュリティの展開後の活動</span><span class="sxs-lookup"><span data-stu-id="907ea-121">Activities after the initial configuration and rollout of Office 365 Cloud App Security</span></span>

<span data-ttu-id="907ea-122">Office 365 のクラウド アプリケーションのセキュリティの構成し、展開、グローバル ・ アドミニストレーターまたはセキュリティ管理者として、考慮すべき点があります。</span><span class="sxs-lookup"><span data-stu-id="907ea-122">After Office 365 Cloud App Security is configured and rolled out, as a global administrator or security administrators, you have several things to consider:</span></span>
  
- <span data-ttu-id="907ea-123">どのような作業は、IT 部署の予定表に追加する必要があるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="907ea-123">What tasks need to be added to the IT department calendar?</span></span>
    
- <span data-ttu-id="907ea-124">どのように時間の経過とともに適切なポリシーが設定を使用する Office 365 のクラウド アプリケーションのセキュリティが構成されていることを確認しますか。</span><span class="sxs-lookup"><span data-stu-id="907ea-124">How can you make sure Office 365 Cloud App Security is configured to use the right set of policies over time?</span></span>
    
- <span data-ttu-id="907ea-125">IT 管理のチェーンを要約情報の種類を送信する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="907ea-125">What kinds of summary information should you send up the IT management chain?</span></span>
    
<span data-ttu-id="907ea-126">次の表には、継続的なタスクを実行して、IT 部門のカレンダーに追加することを考慮する必要があります、定期的なタスクについて簡単にまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="907ea-126">The following table briefly summarizes the ongoing tasks you'll want to perform and periodic tasks you should consider adding to your IT department's calendar.</span></span>
  
|<span data-ttu-id="907ea-127">**進行中のタスク**</span><span class="sxs-lookup"><span data-stu-id="907ea-127">**Ongoing tasks**</span></span>|<span data-ttu-id="907ea-128">**定期的なタスク**</span><span class="sxs-lookup"><span data-stu-id="907ea-128">**Periodic tasks**</span></span>|
|:-----|:-----|
| <span data-ttu-id="907ea-129">警告メッセージを送信する電子メール アカウントを監視します。</span><span class="sxs-lookup"><span data-stu-id="907ea-129">Monitor the email accounts to which you are sending alert messages</span></span>  <br/>  <span data-ttu-id="907ea-130">新しいサイバー攻撃に関する最新情報については、業界 cybersecurity ニュース フィードを監視します。</span><span class="sxs-lookup"><span data-stu-id="907ea-130">Monitor industry cybersecurity news feeds for the latest information about new cyber attacks</span></span>  <br/>  <span data-ttu-id="907ea-131">識別し、セキュリティの問題やリスクに対処するセキュリティ警告の動作します。</span><span class="sxs-lookup"><span data-stu-id="907ea-131">Act on security alerts to identify and address security incidents and risks</span></span>  <br/>  <span data-ttu-id="907ea-132">各セキュリティ上の問題と、中央のログでの解像度を集計します。</span><span class="sxs-lookup"><span data-stu-id="907ea-132">Summarize each security incident and resolution in a central log</span></span>  <br/> | <span data-ttu-id="907ea-133">スポット異常に Office 365 のクラウド アプリケーションのセキュリティ警告の毎月または四半期ごとのレビューを行い、傾向の分析</span><span class="sxs-lookup"><span data-stu-id="907ea-133">Perform monthly or quarterly reviews of Office 365 Cloud App Security alerts to spot anomalies and analyze trends</span></span>  <br/>  <span data-ttu-id="907ea-134">毎月または四半期ごとの拡張機能に含める Office 365 のクラウド アプリケーションのセキュリティとアドレスの新しい cyberattacks と cybersecurity の傾向を既存の Office 365 のクラウド アプリケーションのセキュリティ ポリシーのレビューを行う</span><span class="sxs-lookup"><span data-stu-id="907ea-134">Perform monthly or quarterly reviews of your existing Office 365 Cloud App Security policies to include enhancements in Office 365 Cloud App Security and address new cyberattacks and trends in cybersecurity</span></span>  <br/> |
   
<span data-ttu-id="907ea-135">によって、組織のサイズと目的の監視とセキュリティの名声を維持するのには、IT 管理のチェーンを含むの月ごとのサマリーをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="907ea-135">Depending on your organization's size and interest in monitoring and maintaining a security stature, you can compile a monthly summary for your IT management chain that includes:</span></span>
  
- <span data-ttu-id="907ea-136">Office 365 のクラウド アプリケーションのセキュリティと識別される、セキュリティ インシデントの種類</span><span class="sxs-lookup"><span data-stu-id="907ea-136">The different types of security incidents identified with Office 365 Cloud App Security</span></span>
    
- <span data-ttu-id="907ea-137">検出されたインシデントの数など、セキュリティ インシデントへの対応、集中管理されたログからの情報</span><span class="sxs-lookup"><span data-stu-id="907ea-137">Summary information from your central log of the security incidents, such as number of incidents detected</span></span>
    
- <span data-ttu-id="907ea-138">警告の傾向と、それらがどのように解決されました。</span><span class="sxs-lookup"><span data-stu-id="907ea-138">Alert trends and how they were addressed</span></span>
    
- <span data-ttu-id="907ea-139">Cybersecurity の最新の動向</span><span class="sxs-lookup"><span data-stu-id="907ea-139">The latest cybersecurity trends</span></span>
    
- <span data-ttu-id="907ea-140">Office 365 のクラウド アプリケーションのセキュリティ ポリシーを変更し、エンド ・ ユーザーに与える影響に関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="907ea-140">Recommendations for Office 365 Cloud App Security policy changes and their impact on end users</span></span>
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="907ea-141">Office 365 のクラウド アプリケーションのセキュリティを展開してから時間が経過した後の活動</span><span class="sxs-lookup"><span data-stu-id="907ea-141">Activities after time has passed since rolling out Office 365 Cloud App Security</span></span>

<span data-ttu-id="907ea-142">最初に構成されているか、Office 365 のクラウド アプリケーションのセキュリティ ポリシーを維持するため、時間のかかる時間が過ぎている場合は、組織のセキュリティ目標と現在の機能を反映した構成に戻るには、以下の手順を実行します。Office 365 のクラウド アプリケーションのセキュリティ。</span><span class="sxs-lookup"><span data-stu-id="907ea-142">If a protracted amount of time has passed since you initially configured or maintained your Office 365 Cloud App Security policies, take the following steps to get back to a configuration that reflects your organization's security goals and the current capabilities of Office 365 Cloud App Security:</span></span>
  
1. <span data-ttu-id="907ea-143">Office 365 のクラウド アプリケーションのセキュリティの構成の最終変更の日付を決定します。</span><span class="sxs-lookup"><span data-stu-id="907ea-143">Determine the date of the last configuration change for Office 365 Cloud App Security.</span></span>
    
2. <span data-ttu-id="907ea-p104">現在の Office 365 のクラウド アプリケーションのセキュリティ構成を理解し、必要に応じて、これらのポリシーを調整します。たとえば、電子メールを通じて通知が送信される場所を知っているを確認します。</span><span class="sxs-lookup"><span data-stu-id="907ea-p104">Understand your current Office 365 Cloud App Security configuration and adjust those policies as needed. For example, make sure you know where alerts are being sent via email.</span></span>
    
3. <span data-ttu-id="907ea-146">最後に Office 365 のクラウド アプリケーションのセキュリティを構成した後は、[ [Office 365 のクラウド アプリケーションのセキュリティの新](new-in-office-365-cas.md)製品の変更を参照してください。</span><span class="sxs-lookup"><span data-stu-id="907ea-146">See [what's new in Office 365 Cloud App Security](new-in-office-365-cas.md) for product changes since you last configured Office 365 Cloud App Security.</span></span> 
    
4. <span data-ttu-id="907ea-147">Office 365 のクラウド アプリケーションのセキュリティの警告やスポットの異常ログの分析を実行し、傾向を分析します。</span><span class="sxs-lookup"><span data-stu-id="907ea-147">Perform an analysis of Office 365 Cloud App Security alerts and logs to spot anomalies and analyze trends.</span></span>
    
5. <span data-ttu-id="907ea-148">最新のセキュリティ上の脅威を認識する業界の cybersecurity の傾向を確認してください。</span><span class="sxs-lookup"><span data-stu-id="907ea-148">Check industry cybersecurity trends to become aware of the latest security threats.</span></span>
    
6. <span data-ttu-id="907ea-p105">Office 365 のクラウド アプリケーションのセキュリティ ポリシーの現在のセットにする必要がある変更の分析を実行します。Office 365 のクラウド アプリケーションのセキュリティ機能の変更、現在の異常、および cybersecurity の傾向を反映します。既存のポリシーまたは新しいポリシーの作成、変更をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="907ea-p105">Perform an analysis of the changes that need to be made to the current set of Office 365 Cloud App Security policies. Incorporate Office 365 Cloud App Security feature changes, current anomalies, and cybersecurity trends. Recommend changes to existing policies or the creation of new policies.</span></span>
    
7. <span data-ttu-id="907ea-p106">ポリシーの変更を実装するための計画を作成します。通信 (交流) 必要に応じて、エンド ・ ユーザーに提案された変更の結果です。</span><span class="sxs-lookup"><span data-stu-id="907ea-p106">Make a plan for implementing the policy changes. Communicate (socialize) the consequences of the proposed changes with your end users as needed.</span></span>
    
8. <span data-ttu-id="907ea-154">Office 365 のクラウド アプリケーションのセキュリティ ポリシーの変更を実装します。</span><span class="sxs-lookup"><span data-stu-id="907ea-154">Implement the Office 365 Cloud App Security policy changes.</span></span>
    
9. <span data-ttu-id="907ea-155">エンド ・ ユーザーからのフィードバックと Office 365 のクラウド アプリケーションのセキュリティの警告を監視し、時間の経過のポリシーを調整します。</span><span class="sxs-lookup"><span data-stu-id="907ea-155">Monitor end user feedback and Office 365 Cloud App Security alerts and adjust policies over time.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="907ea-156">次のステップ</span><span class="sxs-lookup"><span data-stu-id="907ea-156">Next steps</span></span>

- [<span data-ttu-id="907ea-157">アクティビティを調査します。</span><span class="sxs-lookup"><span data-stu-id="907ea-157">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="907ea-158">サスペンド モードまたはユーザー アカウントを復元します。</span><span class="sxs-lookup"><span data-stu-id="907ea-158">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- [<span data-ttu-id="907ea-159">OAuth のアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="907ea-159">Manage OAuth apps</span></span>](manage-app-permissions-in-ocas.md)
    
- [<span data-ttu-id="907ea-160">Office 365 Cloud App Security でアプリ検出結果を確認する</span><span class="sxs-lookup"><span data-stu-id="907ea-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="907ea-161">サポートされている[Web トラフィックのログとデータ ソース](web-traffic-logs-and-data-sources-for-ocas.md)の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="907ea-161">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    

