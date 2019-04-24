---
title: Office 365 Cloud App Security 展開後の利用方法
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: Office 365 Cloud App Security をセットアップしてロールアウトした後、特定のタスクを実行して構成が正しいことと、定期的なレビューの準備ができていることを確認してください。
ms.openlocfilehash: 232de4df1d1eb4debdddcee2c1d8672d1aeb4b21
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242545"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="5adc7-103">Office 365 Cloud App Security 展開後の利用方法</span><span class="sxs-lookup"><span data-stu-id="5adc7-103">Utilization activities after rolling out Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="5adc7-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="5adc7-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="5adc7-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="5adc7-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="5adc7-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="5adc7-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="5adc7-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="5adc7-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="5adc7-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="5adc7-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="5adc7-109">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="5adc7-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="5adc7-110">展開を開始する</span><span class="sxs-lookup"><span data-stu-id="5adc7-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="5adc7-111">ここでは、</span><span class="sxs-lookup"><span data-stu-id="5adc7-111">You are here!</span></span>  <br/> [<span data-ttu-id="5adc7-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="5adc7-112">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="5adc7-113">office 365 Cloud App Security は office 365 Enterprise E5 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="5adc7-113">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="5adc7-114">組織で別の office 365 Enterprise サブスクリプションを使用している場合、office 365 Cloud App Security をアドオンとして購入することができます。</span><span class="sxs-lookup"><span data-stu-id="5adc7-114">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="5adc7-115">(全体管理者として、Microsoft 365 管理センターで、[**課金** \>の**サブスクリプションの追加**] を選択します。)詳細については、「office 365 プラットフォームサービスの説明」を参照してください[。 office 365 セキュリティ&amp;コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)で、 [office 365 for business のアドオンを購入または編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)します。</span><span class="sxs-lookup"><span data-stu-id="5adc7-115">(As a global administrator, in the Microsoft 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="5adc7-116">office 365 Cloud App security をセットアップして構成した後、組織のために office 365 の全体管理者またはセキュリティ管理者として、特定の使用状況タスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5adc7-116">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span> 

<span data-ttu-id="5adc7-117">これらのタスクを実行することにより、office 365 Cloud App Security が適切に構成され、ポリシーが最新のものであり、組織が office 365 の価値を実感していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5adc7-117">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365.</span></span> <span data-ttu-id="5adc7-118">この記事を参考にして、これらのタスクを計画してください。</span><span class="sxs-lookup"><span data-stu-id="5adc7-118">Use this article as a guide to help you plan for these tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5adc7-119">この記事で説明されているタスクを実行するには、全体管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5adc7-119">You must be a global administrator or security administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="5adc7-120">詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5adc7-120">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a><span data-ttu-id="5adc7-121">Office 365 Cloud App Security の初期構成とロールアウト後のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="5adc7-121">Activities after the initial configuration and rollout of Office 365 Cloud App Security</span></span>

<span data-ttu-id="5adc7-122">Office 365 Cloud App Security を構成してロールアウトした後、全体管理者またはセキュリティ管理者として、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5adc7-122">After Office 365 Cloud App Security is configured and rolled out, as a global administrator or security administrators, you have several things to consider:</span></span>
  
- <span data-ttu-id="5adc7-123">IT 部門の予定表に追加する必要があるタスク</span><span class="sxs-lookup"><span data-stu-id="5adc7-123">What tasks need to be added to the IT department calendar?</span></span>
    
- <span data-ttu-id="5adc7-124">Office 365 Cloud App Security が、時間の経過とともに適切なポリシーセットを使用するように構成されていることを確認するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="5adc7-124">How can you make sure Office 365 Cloud App Security is configured to use the right set of policies over time?</span></span>
    
- <span data-ttu-id="5adc7-125">IT 管理チェーンを送信する必要がある要約情報の種類は何ですか。</span><span class="sxs-lookup"><span data-stu-id="5adc7-125">What kinds of summary information should you send up the IT management chain?</span></span>
    
<span data-ttu-id="5adc7-126">次の表に、実行する必要がある進行中のタスクと、IT 部門の予定表に追加する必要がある定期的なタスクを簡単にまとめています。</span><span class="sxs-lookup"><span data-stu-id="5adc7-126">The following table briefly summarizes the ongoing tasks you'll want to perform and periodic tasks you should consider adding to your IT department's calendar.</span></span>
  
|<span data-ttu-id="5adc7-127">**進行中のタスク**</span><span class="sxs-lookup"><span data-stu-id="5adc7-127">**Ongoing tasks**</span></span>|<span data-ttu-id="5adc7-128">**定期的なタスク**</span><span class="sxs-lookup"><span data-stu-id="5adc7-128">**Periodic tasks**</span></span>|
|:-----|:-----|
| <span data-ttu-id="5adc7-129">通知メッセージを送信する電子メールアカウントを監視する</span><span class="sxs-lookup"><span data-stu-id="5adc7-129">Monitor the email accounts to which you are sending alert messages</span></span>  <br/>  <span data-ttu-id="5adc7-130">新しいサイバー攻撃に関する最新情報について業界 cybersecurity ニュースフィードを監視する</span><span class="sxs-lookup"><span data-stu-id="5adc7-130">Monitor industry cybersecurity news feeds for the latest information about new cyber attacks</span></span>  <br/>  <span data-ttu-id="5adc7-131">セキュリティの警告に基づいてセキュリティインシデントとリスクを識別して解決する</span><span class="sxs-lookup"><span data-stu-id="5adc7-131">Act on security alerts to identify and address security incidents and risks</span></span>  <br/>  <span data-ttu-id="5adc7-132">中央ログで各セキュリティインシデントと解決策を要約する</span><span class="sxs-lookup"><span data-stu-id="5adc7-132">Summarize each security incident and resolution in a central log</span></span>  <br/> | <span data-ttu-id="5adc7-133">Office 365 Cloud App Security alerts の月次または四半期のレビューを実行して、異常を発見し、傾向を分析する</span><span class="sxs-lookup"><span data-stu-id="5adc7-133">Perform monthly or quarterly reviews of Office 365 Cloud App Security alerts to spot anomalies and analyze trends</span></span>  <br/>  <span data-ttu-id="5adc7-134">既存の office 365 cloud app security ポリシーの月次または四半期のレビューを実行して、office 365 cloud app security の機能強化を含み、cybersecurity の新しい cyberattacks およびトレンドを解決します。</span><span class="sxs-lookup"><span data-stu-id="5adc7-134">Perform monthly or quarterly reviews of your existing Office 365 Cloud App Security policies to include enhancements in Office 365 Cloud App Security and address new cyberattacks and trends in cybersecurity</span></span>  <br/> |
   
<span data-ttu-id="5adc7-135">組織の規模とセキュリティ stature の監視と保守に関する情報に応じて、次のものを含む IT 管理チェーンの月ごとのサマリーをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="5adc7-135">Depending on your organization's size and interest in monitoring and maintaining a security stature, you can compile a monthly summary for your IT management chain that includes:</span></span>
  
- <span data-ttu-id="5adc7-136">Office 365 Cloud App security で識別されるさまざまな種類のセキュリティインシデント</span><span class="sxs-lookup"><span data-stu-id="5adc7-136">The different types of security incidents identified with Office 365 Cloud App Security</span></span>
    
- <span data-ttu-id="5adc7-137">検出されたインシデント数などの、セキュリティインシデントの中央ログからの概要情報</span><span class="sxs-lookup"><span data-stu-id="5adc7-137">Summary information from your central log of the security incidents, such as number of incidents detected</span></span>
    
- <span data-ttu-id="5adc7-138">アラートの傾向とその対処方法</span><span class="sxs-lookup"><span data-stu-id="5adc7-138">Alert trends and how they were addressed</span></span>
    
- <span data-ttu-id="5adc7-139">最新の cybersecurity 傾向</span><span class="sxs-lookup"><span data-stu-id="5adc7-139">The latest cybersecurity trends</span></span>
    
- <span data-ttu-id="5adc7-140">Office 365 Cloud App Security policy の変更点とエンドユーザーへの影響に関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="5adc7-140">Recommendations for Office 365 Cloud App Security policy changes and their impact on end users</span></span>
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="5adc7-141">Office 365 Cloud App Security を展開してから経過した後のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="5adc7-141">Activities after time has passed since rolling out Office 365 Cloud App Security</span></span>

<span data-ttu-id="5adc7-142">Office 365 Cloud App Security ポリシーを最初に構成または管理してから、protracted の時間が経過した場合は、次の手順を実行して、組織のセキュリティ目標および現在の機能を反映した構成に戻すことができます。Office 365 Cloud App Security の場合:</span><span class="sxs-lookup"><span data-stu-id="5adc7-142">If a protracted amount of time has passed since you initially configured or maintained your Office 365 Cloud App Security policies, take the following steps to get back to a configuration that reflects your organization's security goals and the current capabilities of Office 365 Cloud App Security:</span></span>
  
1. <span data-ttu-id="5adc7-143">Office 365 Cloud App Security の最後の構成変更の日付を確認します。</span><span class="sxs-lookup"><span data-stu-id="5adc7-143">Determine the date of the last configuration change for Office 365 Cloud App Security.</span></span>
    
2. <span data-ttu-id="5adc7-144">現在の Office 365 Cloud App Security の構成を理解し、必要に応じてそれらのポリシーを調整します。</span><span class="sxs-lookup"><span data-stu-id="5adc7-144">Understand your current Office 365 Cloud App Security configuration and adjust those policies as needed.</span></span> <span data-ttu-id="5adc7-145">たとえば、通知が電子メールで送信されている場所を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5adc7-145">For example, make sure you know where alerts are being sent via email.</span></span>
    
3. <span data-ttu-id="5adc7-146">前回 office 365 cloud app security を構成した後の製品変更については、「 [office 365 cloud app security の新機能](new-in-office-365-cas.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5adc7-146">See [what's new in Office 365 Cloud App Security](new-in-office-365-cas.md) for product changes since you last configured Office 365 Cloud App Security.</span></span> 
    
4. <span data-ttu-id="5adc7-147">Office 365 Cloud App Security の警告とログの分析を実行して、異常を発見し、傾向を分析します。</span><span class="sxs-lookup"><span data-stu-id="5adc7-147">Perform an analysis of Office 365 Cloud App Security alerts and logs to spot anomalies and analyze trends.</span></span>
    
5. <span data-ttu-id="5adc7-148">業界 cybersecurity の傾向をチェックして、最新のセキュリティの脅威を認識します。</span><span class="sxs-lookup"><span data-stu-id="5adc7-148">Check industry cybersecurity trends to become aware of the latest security threats.</span></span>
    
6. <span data-ttu-id="5adc7-149">現在の Office 365 Cloud App Security ポリシーセットに対して行う必要のある変更の分析を行います。</span><span class="sxs-lookup"><span data-stu-id="5adc7-149">Perform an analysis of the changes that need to be made to the current set of Office 365 Cloud App Security policies.</span></span> <span data-ttu-id="5adc7-150">Office 365 Cloud App Security 機能の変更、現在の異常、cybersecurity の傾向を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="5adc7-150">Incorporate Office 365 Cloud App Security feature changes, current anomalies, and cybersecurity trends.</span></span> <span data-ttu-id="5adc7-151">既存のポリシーの変更または新しいポリシーの作成をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5adc7-151">Recommend changes to existing policies or the creation of new policies.</span></span>
    
7. <span data-ttu-id="5adc7-152">ポリシーの変更を実装するための計画を立ててください。</span><span class="sxs-lookup"><span data-stu-id="5adc7-152">Make a plan for implementing the policy changes.</span></span> <span data-ttu-id="5adc7-153">必要に応じて、提案された変更の結果をエンドユーザーに通知 (socialize) します。</span><span class="sxs-lookup"><span data-stu-id="5adc7-153">Communicate (socialize) the consequences of the proposed changes with your end users as needed.</span></span>
    
8. <span data-ttu-id="5adc7-154">Office 365 Cloud App Security policy の変更を実装します。</span><span class="sxs-lookup"><span data-stu-id="5adc7-154">Implement the Office 365 Cloud App Security policy changes.</span></span>
    
9. <span data-ttu-id="5adc7-155">エンドユーザーのフィードバックと Office 365 Cloud App Security alerts を監視して、ポリシーを徐々に調整します。</span><span class="sxs-lookup"><span data-stu-id="5adc7-155">Monitor end user feedback and Office 365 Cloud App Security alerts and adjust policies over time.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="5adc7-156">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5adc7-156">Next steps</span></span>

- [<span data-ttu-id="5adc7-157">アクティビティを調べる</span><span class="sxs-lookup"><span data-stu-id="5adc7-157">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="5adc7-158">ユーザーアカウントを中断または復元する</span><span class="sxs-lookup"><span data-stu-id="5adc7-158">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- [<span data-ttu-id="5adc7-159">OAuth アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="5adc7-159">Manage OAuth apps</span></span>](manage-app-permissions-in-ocas.md)
    
- [<span data-ttu-id="5adc7-160">Office 365 Cloud App Security でアプリ検出結果を確認する</span><span class="sxs-lookup"><span data-stu-id="5adc7-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="5adc7-161">サポートされている[Web トラフィックログとデータソース](web-traffic-logs-and-data-sources-for-ocas.md)の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="5adc7-161">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    

