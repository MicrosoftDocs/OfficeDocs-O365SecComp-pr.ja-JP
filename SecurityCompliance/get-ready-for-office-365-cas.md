---
title: Office 365 Cloud App Security の使用準備
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: Office 365 のクラウド アプリケーションのセキュリティの使用を開始します。
ms.openlocfilehash: 1d1ae464278a5d9aafa5a176298f03174b6a37dc
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603698"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a><span data-ttu-id="068b4-103">Office 365 Cloud App Security の使用準備</span><span class="sxs-lookup"><span data-stu-id="068b4-103">Get ready for Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="068b4-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="068b4-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="068b4-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="068b4-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="068b4-106">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="068b4-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="068b4-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="068b4-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="068b4-108">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="068b4-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |<span data-ttu-id="068b4-109">コースです!</span><span class="sxs-lookup"><span data-stu-id="068b4-109">You are here!</span></span>  <br/> [<span data-ttu-id="068b4-110">次の手順</span><span class="sxs-lookup"><span data-stu-id="068b4-110">Next step</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="068b4-111">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="068b4-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="068b4-112">使用します。</span><span class="sxs-lookup"><span data-stu-id="068b4-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="068b4-p101">オンにし、組織の Office 365 のクラウド アプリケーション セキュリティ (高度なセキュリティ管理と呼ばれていました) の実装を準備するには考慮する点があります。ガイドとしてこの資料を使用して、Office 365 のクラウド アプリケーションのセキュリティを計画します。</span><span class="sxs-lookup"><span data-stu-id="068b4-p101">As you prepare to turn on and implement Office 365 Cloud App Security (formerly known as Advanced Security Management) for your organization, there are a few things to take into account. Use this article as a guide to plan for Office 365 Cloud App Security.</span></span>
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a><span data-ttu-id="068b4-115">識別し、グローバル アカウントおよびセキュリティ管理者アカウントを保護する手順 1。</span><span class="sxs-lookup"><span data-stu-id="068b4-115">Step 1: Identify and protect your global and security administrator accounts</span></span>

<span data-ttu-id="068b4-p102">グローバル管理者、セキュリティ管理者、およびセキュリティのリーダーは、Office 365 のクラウド アプリケーションのセキュリティ ポリシーを表示、確認通知、およびレポートを使用してポータルにアクセスできます。グローバル管理者およびセキュリティ管理者は、ポリシーを定義し、組織を保護するために他のアクションを実行します。(詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md).)アクセス許可を高めた予防策として、組織のユーザー アカウントを確認します。</span><span class="sxs-lookup"><span data-stu-id="068b4-p102">Global administrators, security administrators, and security readers can access the Office 365 Cloud App Security portal to view policies, review alerts, and use reports. Global administrators and security administrators can define policies and take other actions to protect your organization. (For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).) Review your organization's user accounts that have elevated permissions as a precaution.</span></span> 
  
 <span data-ttu-id="068b4-119">**[グローバル管理者アカウントを保護する、Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**。</span><span class="sxs-lookup"><span data-stu-id="068b4-119">**[Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**.</span></span> 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a><span data-ttu-id="068b4-120">手順 2: は、監査、組織のログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="068b4-120">Step 2: Turn on audit logging for your organization</span></span>

<span data-ttu-id="068b4-p103">正しく動作する Office 365 のクラウド アプリケーションのセキュリティのためには、監査ログを有効にする必要があります。これは通常、Exchange Online 管理者またはグローバル ・ アドミニストレーターが行います。</span><span class="sxs-lookup"><span data-stu-id="068b4-p103">In order for Office 365 Cloud App Security to work correct, audit logging must be turned on. This is typically done by an Exchange Online administrator or a global administrator.</span></span>
  
 <span data-ttu-id="068b4-123">**[オンまたはオフ、Office 365 を有効にする監査ログの検索](turn-audit-log-search-on-or-off.md)** をします。</span><span class="sxs-lookup"><span data-stu-id="068b4-123">**[Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md)**.</span></span> 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="068b4-124">Office 365 のクラウド アプリケーションのセキュリティ関連ポータルには、手順 3。</span><span class="sxs-lookup"><span data-stu-id="068b4-124">Step 3: Go to the Office 365 Cloud App Security portal</span></span>

<span data-ttu-id="068b4-125">Office 365 のクラウド アプリケーションのセキュリティ関連ポータルにアクセスできます[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)署名します。</span><span class="sxs-lookup"><span data-stu-id="068b4-125">You can get to the Office 365 Cloud App Security portal by going to [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span> 

<span data-ttu-id="068b4-p104">取得することもありますから、Office 365 のセキュリティ&amp;コンプライアンス センターです。これを行う方法の 1 つを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="068b4-p104">You can also get there from the Office 365 Security &amp; Compliance Center. Here's one good way to do it:</span></span>

1. <span data-ttu-id="068b4-p105">[https://protection.office.com](https://protection.office.com)と符号インチ (これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="068b4-p105">Go to [https://protection.office.com](https://protection.office.com) and sign in. (This takes you to the Security &amp; Compliance Center.)</span></span>
    
2. <span data-ttu-id="068b4-130">**アラート**を参照して\>**詳細なアラートを管理**します。</span><span class="sxs-lookup"><span data-stu-id="068b4-130">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="068b4-131">Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに移動する**には、Office 365 のクラウド アプリケーションのセキュリティ**を選択してください。</span><span class="sxs-lookup"><span data-stu-id="068b4-131">Choose **Go to Office 365 Cloud App Security** to go to the Office 365 Cloud App Security portal.</span></span><br> <span data-ttu-id="068b4-132">![Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="068b4-132">![Choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br><span data-ttu-id="068b4-133">Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに移動すると、最初のページが表示は、[ポリシー] ページで次の図のようなです。</span><span class="sxs-lookup"><span data-stu-id="068b4-133">When you go to the Office 365 Cloud App Security portal, the first page you see is the Policies page, which resembles the following image:</span></span><br><span data-ttu-id="068b4-134">![ポリシー] ページで開始する場合、Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに移動すると、](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span><span class="sxs-lookup"><span data-stu-id="068b4-134">![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span></span><br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a><span data-ttu-id="068b4-135">ステップ 4: ポリシーを定義し、アラートを設定します&amp;アクション</span><span class="sxs-lookup"><span data-stu-id="068b4-135">Step 4: Define policies and set up alerts &amp; actions</span></span>

<span data-ttu-id="068b4-p106">グローバル管理者およびセキュリティ管理者は、Office 365 のクラウド アプリケーションのセキュリティのポリシーを定義します。ポリシーを定義する過程で、アラートとアクションも設定されています。アラートは、ビューに表示されますまたは電子メール経由で送信される条件に基づく通知です。</span><span class="sxs-lookup"><span data-stu-id="068b4-p106">Global administrators and security administrators define policies in Office 365 Cloud App Security. During the process of defining policies, alerts and actions are also set. An alert is a criteria-based notification that appears in a view or is sent via email.</span></span> 
  
<span data-ttu-id="068b4-p107">Office 365 のクラウド アプリケーションのセキュリティの警告の 2 種類があります: 不審な活動を検出する異常検知して警告し、アクティビティのアラートは、組織の典型的な可能性のあるアクティビティに定義されています。アラートでは、グローバル管理者およびセキュリティ管理者、組織にとっても、通常の Office 365 環境内のアクティビティがある場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="068b4-p107">There are two types of alerts in Office 365 Cloud App Security: anomaly detection alerts that detect suspicious activity, and activity alerts, which are defined for activities that might be atypical for your organization. Alerts notify global administrators and security administrators when there's an activity in your Office 365 environment that's unusual for your organization.</span></span>
  
<span data-ttu-id="068b4-141">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="068b4-141">See the following resources to learn more:</span></span>
  
- [<span data-ttu-id="068b4-142">Office 365 Cloud App Security のアクティビティ ポリシーと警告</span><span class="sxs-lookup"><span data-stu-id="068b4-142">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="068b4-143">Office 365 Cloud App Security の異常検出ポリシー</span><span class="sxs-lookup"><span data-stu-id="068b4-143">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="068b4-144">Office 365 のクラウド アプリケーションのセキュリティの警告を確認して処理</span><span class="sxs-lookup"><span data-stu-id="068b4-144">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    
## <a name="step-5-learn-about-your-organizations-cloud-usage"></a><span data-ttu-id="068b4-145">組織のクラウドの使用方法について、手順 5。</span><span class="sxs-lookup"><span data-stu-id="068b4-145">Step 5: Learn about your organization's cloud usage</span></span>

<span data-ttu-id="068b4-p108">グローバル管理者、セキュリティ管理者、またはセキュリティのリーダーとして、レポートとクラウドの探索のダッシュ ボード (生産性アプリケーションの検出とも呼ばれます) を通じて、組織のクラウドの使用方法について学習できます。このダッシュ ボードには、ユーザー、アプリケーション、web トラフィック、およびリスクのレベルについての情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="068b4-p108">As a global administrator, security administrator, or security reader, you can learn about your organization's cloud usage through reports and a Cloud Discovery dashboard (also called Productivity App Discovery). This dashboard shows information about users, apps, web traffic, and risk levels.</span></span>
  
![検出を選択して、Office 365 の CA のポータルでは、\>クラウド探索のダッシュ ボード](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="068b4-149">生産性アプリケーションの検出のダッシュ ボード、Office 365 のクラウド アプリケーションのセキュリティ ・ ポータル内に移動するのには、**検出**を選択します\>**クラウド探索のダッシュ ボード**です。</span><span class="sxs-lookup"><span data-stu-id="068b4-149">To go to the Productivity App Discovery dashboard, in the Office 365 Cloud App Security portal, choose **Discover** \> **Cloud Discovery dashboard**.</span></span>
  
![Office 365 CA ポータルでは、検出を選択します](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
<span data-ttu-id="068b4-p109">必要な情報を含むレポートを作成するには、組織のファイアウォールやプロキシのログ ファイルをアップロードします。詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="068b4-p109">To populate reports with the information you need, upload your log files from your organization's firewalls and proxies. To learn more, see the following resources:</span></span>
  
- [<span data-ttu-id="068b4-153">Office 365 のクラウド アプリケーションのセキュリティでのアプリケーション検出レポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="068b4-153">Create app discovery reports in Office 365 Cloud App Security</span></span>](create-app-discovery-reports-in-ocas.md)
    
- [<span data-ttu-id="068b4-154">Office 365 Cloud App Security でアプリ検出結果を確認する</span><span class="sxs-lookup"><span data-stu-id="068b4-154">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-6-manage-apps-that-your-organization-is-using-to-access-office-365"></a><span data-ttu-id="068b4-155">手順 6: 組織が Office 365 のアクセスに使用しているアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="068b4-155">Step 6: Manage apps that your organization is using to access Office 365</span></span>

<span data-ttu-id="068b4-p110">グローバル管理者またはセキュリティ管理者は、カスタム アプリケーションを Office 365 で、組織内のユーザーを使用しているサード ・ パーティ製のアプリケーションなどのアプリケーションを管理できます。たとえば、Office 365 を使用するカスタムのアプリケーションのダウンロードが他のこととします。ユーザーが使用してアプリケーションを確認する、信頼されていないアプリケーションは、アクセスを禁止したり、アプリケーションを追跡のための承認済みとしてマークできます。[OAuth の管理アプリケーションが Office 365 のクラウド アプリケーションのセキュリティを使用](manage-app-permissions-in-ocas.md)します。</span><span class="sxs-lookup"><span data-stu-id="068b4-p110">As a global administrator or security administrator, you can manage apps, such as custom apps or third-party apps, that people in your organization are using on their devices with Office 365. For example, suppose that someone has downloaded a custom app they want to use with Office 365. You can review the apps people are using, ban untrusted apps, or mark apps as approved for your tracking purposes. [Manage OAuth apps using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).</span></span>
  
## <a name="step-7-use-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="068b4-160">手順 7: Office 365 のクラウド アプリケーションのセキュリティと SIEM サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="068b4-160">Step 7: Use your SIEM server with Office 365 Cloud App Security</span></span>

<span data-ttu-id="068b4-p111">セキュリティ情報およびイベント管理 (SIEM) サーバーを使用する組織ですか。Office 365 クラウド アプリケーションのセキュリティにアラートの一元的な監視を有効にするのには、SIEM のサーバーに統合できます。SIEM サービスと統合すること、セキュリティの一般的なワークフローを維持する、セキュリティ手順を自動化すること、およびクラウド ベースの間に相関関連づけることの中に、クラウド アプリケーションの保護を強化することができ、設置型のイベント。SIEM エージェントは、サーバー上で実行し、Office 365 のクラウド アプリケーションのセキュリティからのアラートを取得、SIEM サーバーにそれらのアラートをストリームします。[SIEM の統合 Office 365 のクラウド アプリケーションのセキュリティ](integrate-your-siem-server-with-office-365-cas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="068b4-p111">Is your organization using a security information and event management (SIEM) server? Office 365 Cloud App Security can now integrate with your SIEM server to enable centralized monitoring of alerts. Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events. The SIEM agent runs on your server, pulls alerts from Office 365 Cloud App Security, and streams those alerts into your SIEM server. See [SIEM integration with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="068b4-166">次のステップ</span><span class="sxs-lookup"><span data-stu-id="068b4-166">Next steps</span></span>

- [<span data-ttu-id="068b4-167">Office 365 Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="068b4-167">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)
    
- <span data-ttu-id="068b4-168">[テスト ラボ ガイド](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)を実際に体験した Office 365 のクラウド アプリケーションのセキュリティの強力な機能を紹介し、概念実証を作成してください。</span><span class="sxs-lookup"><span data-stu-id="068b4-168">Try our [Test Lab Guide](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) for a hands-on experience where you can demonstrate the powerful features of Office 365 Cloud App Security and create a proof of concept.</span></span> 
    

