---
title: Office 365 Cloud App Security の使用の準備
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/15/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: Office 365 Cloud App Security の使用を開始する
ms.openlocfilehash: 89718adcbb7c77735db3009937d887e88d4a8bc3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254026"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a><span data-ttu-id="cec3b-103">Office 365 Cloud App Security の使用の準備</span><span class="sxs-lookup"><span data-stu-id="cec3b-103">Get ready for Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="cec3b-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="cec3b-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="cec3b-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="cec3b-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="cec3b-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="cec3b-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="cec3b-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cec3b-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="cec3b-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="cec3b-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |<span data-ttu-id="cec3b-109">ここでは、</span><span class="sxs-lookup"><span data-stu-id="cec3b-109">You are here!</span></span>  <br/> [<span data-ttu-id="cec3b-110">次の手順</span><span class="sxs-lookup"><span data-stu-id="cec3b-110">Next step</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="cec3b-111">展開を開始する</span><span class="sxs-lookup"><span data-stu-id="cec3b-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="cec3b-112">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="cec3b-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="cec3b-113">Office 365 Cloud App Security を組織に対して有効にして実装する準備ができたら、いくつかの点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cec3b-113">As you prepare to turn on and implement Office 365 Cloud App Security for your organization, there are a few things to take into account.</span></span> <span data-ttu-id="cec3b-114">この記事は、Office 365 Cloud App Security を計画する際のガイドとしてご利用ください。</span><span class="sxs-lookup"><span data-stu-id="cec3b-114">Use this article as a guide to plan for Office 365 Cloud App Security.</span></span>
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a><span data-ttu-id="cec3b-115">手順 1: グローバルおよびセキュリティ管理者アカウントを識別して保護する</span><span class="sxs-lookup"><span data-stu-id="cec3b-115">Step 1: Identify and protect your global and security administrator accounts</span></span>

<span data-ttu-id="cec3b-116">グローバル管理者、セキュリティ管理者、およびセキュリティ閲覧者は、Office 365 Cloud App security ポータルにアクセスして、ポリシーの表示、通知の確認、およびレポートの使用を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-116">Global administrators, security administrators, and security readers can access the Office 365 Cloud App Security portal to view policies, review alerts, and use reports.</span></span> <span data-ttu-id="cec3b-117">グローバル管理者とセキュリティ管理者は、ポリシーを定義し、組織を保護するためのその他のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-117">Global administrators and security administrators can define policies and take other actions to protect your organization.</span></span> <span data-ttu-id="cec3b-118">(詳細については、「 [Office 365 セキュリティ&amp;センターコンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください)。安全性の高い権限を持つ組織のユーザーアカウントを確認します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-118">(For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).) Review your organization's user accounts that have elevated permissions as a precaution.</span></span> 
  
 <span data-ttu-id="cec3b-119">**[Office 365 のグローバル管理者アカウントを保護](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)** します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-119">**[Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**.</span></span> 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a><span data-ttu-id="cec3b-120">手順 2: 組織の監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="cec3b-120">Step 2: Turn on audit logging for your organization</span></span>

<span data-ttu-id="cec3b-121">Office 365 Cloud App Security を正しく動作させるには、監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cec3b-121">In order for Office 365 Cloud App Security to work correct, audit logging must be turned on.</span></span> <span data-ttu-id="cec3b-122">これは、通常、Exchange Online 管理者または全体管理者によって行われます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-122">This is typically done by an Exchange Online administrator or a global administrator.</span></span>
  
 <span data-ttu-id="cec3b-123">**[Office 365 監査ログの検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)** します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-123">**[Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md)**.</span></span> 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="cec3b-124">手順 3: Office 365 Cloud App Security ポータルに移動する</span><span class="sxs-lookup"><span data-stu-id="cec3b-124">Step 3: Go to the Office 365 Cloud App Security portal</span></span>

<span data-ttu-id="cec3b-125">Office 365 Cloud App Security ポータルにアクセスするには、に[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)移動してサインインします。</span><span class="sxs-lookup"><span data-stu-id="cec3b-125">You can get to the Office 365 Cloud App Security portal by going to [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span> 

<span data-ttu-id="cec3b-126">Office 365 セキュリティ&amp;コンプライアンスセンターから入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-126">You can also get there from the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="cec3b-127">そのためには、次のいずれかの方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cec3b-127">Here's one good way to do it:</span></span>

1. <span data-ttu-id="cec3b-128">に[https://protection.office.com](https://protection.office.com)移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="cec3b-128">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="cec3b-129">(これにより、セキュリティ&amp;コンプライアンスセンターに移動できます。)</span><span class="sxs-lookup"><span data-stu-id="cec3b-129">(This takes you to the Security &amp; Compliance Center.)</span></span>
    
2. <span data-ttu-id="cec3b-130">[**アラート** \> ] **[advanced alerts の管理**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-130">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="cec3b-131">[ **office 365 cloud app security に移動**] を選択して、office 365 Cloud app security ポータルに移動します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-131">Choose **Go to Office 365 Cloud App Security** to go to the Office 365 Cloud App Security portal.</span></span><br> <span data-ttu-id="cec3b-132">![Office 365 Cloud App Security に移動するには、[高度な通知の管理] を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="cec3b-132">![Choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br><span data-ttu-id="cec3b-133">Office 365 Cloud App Security ポータルに移動すると、最初に表示されるページは [ポリシー] ページになります。これは次の画像のようになります。</span><span class="sxs-lookup"><span data-stu-id="cec3b-133">When you go to the Office 365 Cloud App Security portal, the first page you see is the Policies page, which resembles the following image:</span></span><br><span data-ttu-id="cec3b-134">![Office 365 Cloud App Security ポータルに移動するときに、[ポリシー] ページから始めます。](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span><span class="sxs-lookup"><span data-stu-id="cec3b-134">![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span></span><br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a><span data-ttu-id="cec3b-135">手順 4: ポリシーを定義し、通知&amp;アクションをセットアップする</span><span class="sxs-lookup"><span data-stu-id="cec3b-135">Step 4: Define policies and set up alerts &amp; actions</span></span>

<span data-ttu-id="cec3b-136">グローバル管理者とセキュリティ管理者は、Office 365 Cloud App security でポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-136">Global administrators and security administrators define policies in Office 365 Cloud App Security.</span></span> <span data-ttu-id="cec3b-137">ポリシーの定義プロセスでは、アラートとアクションも設定されます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-137">During the process of defining policies, alerts and actions are also set.</span></span> <span data-ttu-id="cec3b-138">通知は、ビューに表示される、または電子メール経由で送信される基準に基づく通知です。</span><span class="sxs-lookup"><span data-stu-id="cec3b-138">An alert is a criteria-based notification that appears in a view or is sent via email.</span></span> 
  
<span data-ttu-id="cec3b-139">Office 365 Cloud App Security には2種類の通知があります。不審なアクティビティを検出する異常検出アラートと、組織にとって例外的なアクティビティに対して定義されたアクティビティアラートがあります。</span><span class="sxs-lookup"><span data-stu-id="cec3b-139">There are two types of alerts in Office 365 Cloud App Security: anomaly detection alerts that detect suspicious activity, and activity alerts, which are defined for activities that might be atypical for your organization.</span></span> <span data-ttu-id="cec3b-140">通知は、組織にとって一般的でない Office 365 環境にアクティビティがある場合に、グローバル管理者とセキュリティ管理者に通知します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-140">Alerts notify global administrators and security administrators when there's an activity in your Office 365 environment that's unusual for your organization.</span></span>
  
<span data-ttu-id="cec3b-141">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cec3b-141">See the following resources to learn more:</span></span>
  
- [<span data-ttu-id="cec3b-142">Office 365 Cloud App Security のアクティビティ ポリシーと警告</span><span class="sxs-lookup"><span data-stu-id="cec3b-142">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="cec3b-143">Office 365 Cloud App Security の異常検出ポリシー</span><span class="sxs-lookup"><span data-stu-id="cec3b-143">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="cec3b-144">Office 365 Cloud App Security alerts を確認してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="cec3b-144">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    

## <a name="step-5-set-up-conditional-access-app-control"></a><span data-ttu-id="cec3b-145">手順 5: 条件付きアクセスアプリコントロールを設定する</span><span class="sxs-lookup"><span data-stu-id="cec3b-145">Step 5: Set up Conditional Access App Control</span></span>

<span data-ttu-id="cec3b-146">ユーザーがどのアプリを使用できるかなど、特定の条件に基づいて、組織のアプリでコントロールを設定して適用します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-146">Set up and enforce controls on your organization's apps, based on certain conditions, such as which users can use what apps, and where.</span></span> <span data-ttu-id="cec3b-147">機密性の高いドキュメントをダウンロードおよび暗号化できるかどうかを決定し、特定のアプリへのアクセスをブロックし、特定のアプリに対して読み取り専用モードを設定し、企業以外のネットワークからのユーザーセッションを制限します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-147">Define user app access and session policies to determine whether sensitive documents can be downloaded and encrypted, block access to certain apps, set up read-only mode for certain apps, and restrict user sessions from non-corporate networks.</span></span>

<span data-ttu-id="cec3b-148">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cec3b-148">See the following resources to learn more:</span></span>

- [<span data-ttu-id="cec3b-149">Office 365 Cloud App Security アプリの条件付きアクセス制御を使用してアプリを保護する</span><span class="sxs-lookup"><span data-stu-id="cec3b-149">Protect apps with Office 365 Cloud App Security Conditional Access App Control</span></span>](ocas-conditional-access-app-control.md)

- [<span data-ttu-id="cec3b-150">Office 365 アプリ用のアプリの条件付きアクセス制御を展開する</span><span class="sxs-lookup"><span data-stu-id="cec3b-150">Deploy Conditional Access App Control for Office 365 apps</span></span>](ocas-deploy-conditional-access-app-control.md)

## <a name="step-6-learn-about-your-organizations-cloud-usage"></a><span data-ttu-id="cec3b-151">手順 6: 組織のクラウド使用状況について学びます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-151">Step 6: Learn about your organization's cloud usage</span></span>

<span data-ttu-id="cec3b-152">グローバル管理者、セキュリティ管理者、またはセキュリティ閲覧者は、レポートとクラウド検出ダッシュボード (生産性アプリの検出とも呼ばれます) を使用して、組織のクラウド使用状況について理解することができます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-152">As a global administrator, security administrator, or security reader, you can learn about your organization's cloud usage through reports and a Cloud Discovery dashboard (also called Productivity App Discovery).</span></span> <span data-ttu-id="cec3b-153">このダッシュボードには、ユーザー、アプリ、web トラフィック、およびリスクレベルに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-153">This dashboard shows information about users, apps, web traffic, and risk levels.</span></span>
  
![Office 365 CAS ポータルで、[クラウド検出\>ダッシュボードの検出] を選択します。](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="cec3b-155">プロダクティビティアプリの探索ダッシュボードに移動するには、Office 365 cloud App Security ポータルで、[**クラウド検出ダッシュボード**の**検出** \> ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-155">To go to the Productivity App Discovery dashboard, in the Office 365 Cloud App Security portal, choose **Discover** \> **Cloud Discovery dashboard**.</span></span>
  
![Office 365 CAS ポータルで、[検出] を選択します。](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
<span data-ttu-id="cec3b-157">レポートに必要な情報を設定するには、組織のファイアウォールとプロキシからログファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="cec3b-157">To populate reports with the information you need, upload your log files from your organization's firewalls and proxies.</span></span> <span data-ttu-id="cec3b-158">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cec3b-158">To learn more, see the following resources:</span></span>
  
- [<span data-ttu-id="cec3b-159">Office 365 Cloud app Security でアプリ検出レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="cec3b-159">Create app discovery reports in Office 365 Cloud App Security</span></span>](create-app-discovery-reports-in-ocas.md)
    
- [<span data-ttu-id="cec3b-160">Office 365 Cloud App Security でアプリ検出結果を確認する</span><span class="sxs-lookup"><span data-stu-id="cec3b-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-7-manage-apps-that-your-organization-is-using-to-access-office-365"></a><span data-ttu-id="cec3b-161">手順 7: 組織が Office 365 へのアクセスに使用しているアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="cec3b-161">Step 7: Manage apps that your organization is using to access Office 365</span></span>

<span data-ttu-id="cec3b-162">グローバル管理者またはセキュリティ管理者として、組織内のユーザーが Office 365 を使用してデバイス上で使用している、カスタムアプリやサードパーティアプリなどのアプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-162">As a global administrator or security administrator, you can manage apps, such as custom apps or third-party apps, that people in your organization are using on their devices with Office 365.</span></span> <span data-ttu-id="cec3b-163">たとえば、ユーザーが Office 365 で使用するカスタムアプリをダウンロードしたとします。</span><span class="sxs-lookup"><span data-stu-id="cec3b-163">For example, suppose that someone has downloaded a custom app they want to use with Office 365.</span></span> <span data-ttu-id="cec3b-164">ユーザーが使用しているアプリを確認したり、信頼されていないアプリを禁止したり、追跡の目的でアプリを承認済みとしてマークしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-164">You can review the apps people are using, ban untrusted apps, or mark apps as approved for your tracking purposes.</span></span> <span data-ttu-id="cec3b-165">[Office 365 Cloud App Security を使用して OAuth アプリを管理](manage-app-permissions-in-ocas.md)します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-165">[Manage OAuth apps using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).</span></span>
  
## <a name="step-8-create-a-maintenance-plan"></a><span data-ttu-id="cec3b-166">手順 8: メンテナンス計画を作成する</span><span class="sxs-lookup"><span data-stu-id="cec3b-166">Step 8: Create a maintenance plan</span></span>

<span data-ttu-id="cec3b-167">office 365 Cloud App security をセットアップして構成した後、組織のために office 365 の全体管理者またはセキュリティ管理者として、特定の使用状況タスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cec3b-167">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span>
<span data-ttu-id="cec3b-168">これらのタスクを実行することにより、office 365 Cloud App Security が適切に構成され、ポリシーが最新のものであり、組織が office 365 の価値を実感していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-168">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365.</span></span> <span data-ttu-id="cec3b-169">この記事を参考にして、これらのタスクを計画してください。</span><span class="sxs-lookup"><span data-stu-id="cec3b-169">Use this article as a guide to help you plan for these tasks.</span></span> <span data-ttu-id="cec3b-170">[Office 365 Cloud App Security をロールアウトした後の使用](utilization-activities-for-ocas.md)状況のアクティビティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cec3b-170">See [Utilization activities after rolling out Office 365 Cloud App Security](utilization-activities-for-ocas.md).</span></span>

## <a name="optional-step-9-use-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="cec3b-171">オプション手順 9: SIEM サーバーを Office 365 Cloud App Security で使用する</span><span class="sxs-lookup"><span data-stu-id="cec3b-171">(Optional) Step 9: Use your SIEM server with Office 365 Cloud App Security</span></span>

<span data-ttu-id="cec3b-172">組織はセキュリティ情報およびイベント管理 (SIEM) サーバーを使用していますか。</span><span class="sxs-lookup"><span data-stu-id="cec3b-172">Is your organization using a security information and event management (SIEM) server?</span></span> <span data-ttu-id="cec3b-173">Office 365 Cloud App Security を SIEM サーバーと統合して、アラートの集中監視を有効にすることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cec3b-173">Office 365 Cloud App Security can now integrate with your SIEM server to enable centralized monitoring of alerts.</span></span> <span data-ttu-id="cec3b-174">SIEM サービスとの統合により、通常のセキュリティワークフローを維持しながら、セキュリティ手順を自動化し、クラウドベースのイベントとオンプレミスのイベントとを関連付けることで、クラウドアプリケーションをより適切に保護することができます。</span><span class="sxs-lookup"><span data-stu-id="cec3b-174">Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events.</span></span> <span data-ttu-id="cec3b-175">SIEM エージェントは、サーバー上で実行され、Office 365 Cloud App Security から通知を取得し、それらのアラートを SIEM サーバーに転送します。</span><span class="sxs-lookup"><span data-stu-id="cec3b-175">The SIEM agent runs on your server, pulls alerts from Office 365 Cloud App Security, and streams those alerts into your SIEM server.</span></span> <span data-ttu-id="cec3b-176">「 [SIEM integration with Office 365 Cloud App Security」を](integrate-your-siem-server-with-office-365-cas.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="cec3b-176">See [SIEM integration with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="cec3b-177">次のステップ</span><span class="sxs-lookup"><span data-stu-id="cec3b-177">Next steps</span></span>

- [<span data-ttu-id="cec3b-178">Office 365 Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="cec3b-178">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)
    
- <span data-ttu-id="cec3b-179">Office 365 Cloud App Security の強力な機能をデモンストレーションし、概念実証を作成するための実践的な操作については、[テストラボガイド](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="cec3b-179">Try our [Test Lab Guide](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) for a hands-on experience where you can demonstrate the powerful features of Office 365 Cloud App Security and create a proof of concept.</span></span> 
    

