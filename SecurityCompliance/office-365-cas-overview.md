---
title: Office 365 Cloud App Security の概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'Office 365 のクラウド アプリケーションのセキュリティを使用する可能性のある問題があると、必要な場合は、セキュリティ問題に対処するアクションを実行するような状況を調査することができますので、Office 365 で不審な動作を把握できます。 '
ms.openlocfilehash: 84d5b412b62bf113101d6322032f3b643d87d741
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531875"
---
# <a name="overview-of-office-365-cloud-app-security"></a><span data-ttu-id="1b23e-103">Office 365 Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="1b23e-103">Overview of Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="1b23e-104">評価 * *\>**</span><span class="sxs-lookup"><span data-stu-id="1b23e-104">****Evaluation** \>**</span></span>|<span data-ttu-id="1b23e-105">計画 * *\>**</span><span class="sxs-lookup"><span data-stu-id="1b23e-105">****Planning** \>**</span></span>|<span data-ttu-id="1b23e-106">配置 * *\>**</span><span class="sxs-lookup"><span data-stu-id="1b23e-106">****Deployment** \>**</span></span>|<span data-ttu-id="1b23e-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="1b23e-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1b23e-108">コースです!</span><span class="sxs-lookup"><span data-stu-id="1b23e-108">You are here!</span></span>  <br/> [<span data-ttu-id="1b23e-109">次の手順</span><span class="sxs-lookup"><span data-stu-id="1b23e-109">Next step</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="1b23e-110">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="1b23e-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="1b23e-111">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="1b23e-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="1b23e-112">使用します。</span><span class="sxs-lookup"><span data-stu-id="1b23e-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="1b23e-p101">Office 365 のクラウド アプリケーションのセキュリティは、Office 365 エンタープライズ E5 に使用できます。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合、Office 365 のクラウド アプリケーションのセキュリティがアドオンとして購入できます。(グローバル管理者は、Office 365 管理センターを選択して**請求** \> **サブスクリプションを追加**します)。詳細についてを参照してください[Office 365 のプラットフォーム サービスの説明: Office 365 のセキュリティ&amp;コンプライアンス センター](https://technet.microsoft.com/en-us/library/dn933793.aspx) [購入またはビジネスのための Office 365 のアドオンを編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)するとします。</span><span class="sxs-lookup"><span data-stu-id="1b23e-p101">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="1b23e-p102">Office 365 のクラウド アプリケーションのセキュリティを使用する可能性のある問題があると、必要な場合は、セキュリティ問題に対処するアクションを実行するような状況を調査することができますので、Office 365 で不審な動作を把握できます。Office 365 のクラウド アプリケーションのセキュリティ、例外、または不審な活動に対してトリガーされたアラートの通知を受け取る、Office 365 の組織のデータがアクセス方法と使用方法、ユーザー アカウントが、不審なアクティビティが発生することを中断し、必要とするを参照してください。アラートがトリガーされた後、Office 365 アプリケーションに再度ログインするユーザーです。Office 365 のクラウド アプリケーションのセキュリティ機能と機能の概要を取得するには、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b23e-p102">Office 365 Cloud App Security gives you insight into suspicious activity in Office 365 so you can investigate situations that are potentially problematic and, if needed, take action to address security issues. With Office 365 Cloud App Security, you can receive notifications of triggered alerts for atypical or suspicious activities, see how your organization's data in Office 365 is accessed and used, suspend user accounts exhibiting suspicious activity, and require users to log back in to Office 365 apps after an alert has been triggered. Read this article to get an overview of Office 365 Cloud App Security features and capabilities.</span></span>
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="1b23e-119">Office 365 のクラウド アプリケーションのセキュリティ関連ポータルを検索する方法</span><span class="sxs-lookup"><span data-stu-id="1b23e-119">How to find the Office 365 Cloud App Security portal</span></span>

> [!NOTE]
> <span data-ttu-id="1b23e-p103">Office 365 のクラウド アプリケーションのセキュリティ関連ポータルにアクセスするには、グローバル管理者、セキュリティ管理者、またはセキュリティのリーダーが必要です。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="1b23e-p103">To access the Office 365 Cloud App Security portal, you must be a global administrator, security administrator, or security reader. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
<span data-ttu-id="1b23e-p104">Office 365 のセキュリティを通じて Office 365 のクラウド アプリケーションのセキュリティのポータルを表示する&amp;コンプライアンス センターです。これを行う方法の 1 つを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="1b23e-p104">You can get to the Office 365 Cloud App Security portal through the Office 365 Security &amp; Compliance Center. Here's one good way to do it:</span></span>
  
1. <span data-ttu-id="1b23e-p105">[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="1b23e-p105">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="1b23e-126">セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="1b23e-126">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span> 
    
    ![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    <span data-ttu-id="1b23e-128">(Office 365 のクラウド アプリケーションのセキュリティはまだ有効でない、グローバル管理者は、 [Office 365 のクラウド アプリケーションのセキュリティを有効にする](turn-on-office-365-cas.md)) 場合</span><span class="sxs-lookup"><span data-stu-id="1b23e-128">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="1b23e-129">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b23e-129">Choose **Go to Office 365 Cloud App Security**.</span></span> 
    
## <a name="policies"></a><span data-ttu-id="1b23e-130">[Policies]</span><span class="sxs-lookup"><span data-stu-id="1b23e-130">Policies</span></span>

<span data-ttu-id="1b23e-p106">Office 365 クラウド アプリケーションのセキュリティは、組織に対して定義されているポリシーと連携します。Office 365 クラウド アプリケーションのセキュリティでは、組織は、10 個の定義済みの異常検出のポリシーとポリシーのアクティビティ テンプレートがいくつかを取得します。全般の異常を検出、危険な IP アドレスからログインするユーザーを識別する、ransomware アクティビティを検出、企業以外の IP アドレス、および複数の管理者のアクティビティを検出するのには、これらのポリシーが設計されています。</span><span class="sxs-lookup"><span data-stu-id="1b23e-p106">Office 365 Cloud App Security works with the policies that are defined for your organization. With Office 365 Cloud App Security, your organization gets 10 predefined anomaly detection policies and several templates for activity policies. These policies are designed to detect general anomalies, identify users logging in from a risky IP address, detect ransomware activities, detect administrator activities from non-corporate IP addresses, and more.</span></span>
  
![CA ポータルでは、コントロールを選択して\>を表示またはポリシー ・ テンプレートを作成するためのテンプレート](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
<span data-ttu-id="1b23e-135">ビュー/ポリシー テンプレート、Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに、使用する**コントロール**に移動して\>**のテンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="1b23e-135">To view/use policy templates, in the Office 365 Cloud App Security portal, go to **Control** \> **Templates**.</span></span> 
  
![O365 CA ポータルでは、コントロールを選択します](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
<span data-ttu-id="1b23e-137">ポリシーに関する詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b23e-137">To learn more about policies, see the following resources:</span></span>
  
- [<span data-ttu-id="1b23e-138">Office 365 Cloud App Security のアクティビティ ポリシーと警告</span><span class="sxs-lookup"><span data-stu-id="1b23e-138">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="1b23e-139">Office 365 Cloud App Security の異常検出ポリシー</span><span class="sxs-lookup"><span data-stu-id="1b23e-139">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a><span data-ttu-id="1b23e-140">アラート</span><span class="sxs-lookup"><span data-stu-id="1b23e-140">Alerts</span></span>

<span data-ttu-id="1b23e-p107">ポリシーを定義したら、検出された疑わしい、または典型的な活動について通知します。組織の警告を表示するには、画面の上部にナビゲーション ・ バーの**アラート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b23e-p107">When policies are defined, alerts notify you about suspicious or atypical activities that were detected. To view alerts for your organization, choose **Alerts** in the navigation bar across the top of the screen.</span></span> 
  
![[アラート] ページで、トリガーされたアラートと行った操作を確認できます。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
<span data-ttu-id="1b23e-p108">アラートがトリガーされると、何が起こっているの詳細については、それらを確認できます。次に、アクティビティがまだ疑わしい場合は、アクションを実行できます。問題についてユーザーに通知することができますから、Office 365 にサインインするユーザーを一時停止にもう一度アプリケーションを Office 365 にサインインするユーザーを必要とします。</span><span class="sxs-lookup"><span data-stu-id="1b23e-p108">As alerts are triggered you can review them to learn more about what is going on. Then, if the activity is still suspicious, you can take action. For example, you can notify a user about an issue, suspend a user from signing in to Office 365, or require a user to sign back in to Office 365 apps.</span></span>
  
<span data-ttu-id="1b23e-147">警告に関する詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b23e-147">To learn more about alerts, see the following resources:</span></span>
  
- [<span data-ttu-id="1b23e-148">Office 365 Cloud App Security のアクティビティ ポリシーと警告</span><span class="sxs-lookup"><span data-stu-id="1b23e-148">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="1b23e-149">Office 365 Cloud App Security の異常検出ポリシー</span><span class="sxs-lookup"><span data-stu-id="1b23e-149">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="1b23e-150">Office 365 のクラウド アプリケーションのセキュリティの警告を確認して処理</span><span class="sxs-lookup"><span data-stu-id="1b23e-150">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a><span data-ttu-id="1b23e-151">動作状況のログ</span><span class="sxs-lookup"><span data-stu-id="1b23e-151">Activity logs</span></span>

<span data-ttu-id="1b23e-152">Office 365 のクラウド アプリケーションのセキュリティで、利用状況ログ] ページで、ユーザーの活動に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="1b23e-152">View information about user activities on your Activity log page in Office 365 Cloud App Security.</span></span>
  
![O365 CA ポータルでは、調査を選択して\>アクティビティ ・ ログ](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
<span data-ttu-id="1b23e-154">**調査**には、Office 365 のクラウド アプリケーションのセキュリティ ポータルでは、このページを表示するのには\>**のアクティビティのログ**です。</span><span class="sxs-lookup"><span data-stu-id="1b23e-154">To get to this page, in the Office 365 Cloud App Security portal, go to **Investigate** \> **Activity log**.</span></span> 
  
![O365 CA ポータルでは、調査を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
<span data-ttu-id="1b23e-p109">すぎると Office 365 のクラウド アプリケーションのセキュリティ、web のトラフィックのログを使用できます。ログ ファイルの詳細については、それらに含まれている、可視性が向上すれば、ユーザーの利用状況にします。Barracuda、青いコート、チェック ポイント、シスコ、Clavister、Dell の SonicWALL、Fortinet、ビャクシン、McAfee、マイクロソフト、パロアルト、Sophos、Squid、Websence、Zscaler などからのログ ファイルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1b23e-p109">You can use your web traffic logs with Office 365 Cloud App Security, too. The more details that are included in those log files, the better visibility you'll have into user activity. You can use log files from Barracuda, Blue Coat, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, Squid, Websence, Zscaler, and more.</span></span>
  
[<span data-ttu-id="1b23e-159">Office 365 のクラウド アプリケーションのセキュリティは、web トラフィックのログとデータ ソースについてください。</span><span class="sxs-lookup"><span data-stu-id="1b23e-159">Learn about web traffic logs and data sources for Office 365 Cloud App Security</span></span>](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="app-permissions"></a><span data-ttu-id="1b23e-160">アプリケーションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="1b23e-160">App permissions</span></span>

<span data-ttu-id="1b23e-161">Office 365 のクラウド アプリケーションのセキュリティ、許可したり、Office 365 のデータにアクセスするサードパーティ製アプリケーションを使用する組織内のユーザーを禁止できます。</span><span class="sxs-lookup"><span data-stu-id="1b23e-161">With Office 365 Cloud App Security, you can allow or prevent people in your organization to use third-party apps that access data in Office 365.</span></span>
  
![O365 の CA では、[調査] メニューの [アプリケーション アクセス許可の管理] ページを表示できます。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
<span data-ttu-id="1b23e-163">**調査**にこのページを表示して、 \> **アプリケーションのアクセスを許可**します。</span><span class="sxs-lookup"><span data-stu-id="1b23e-163">To get to this page, go to **Investigate** \> **App permissions**.</span></span> 
  
![O365 CA ポータルでは、調査を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[<span data-ttu-id="1b23e-165">Office 365 Cloud App Security を使用してアプリのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="1b23e-165">Manage app permissions using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a><span data-ttu-id="1b23e-166">クラウド探索のダッシュ ボード</span><span class="sxs-lookup"><span data-stu-id="1b23e-166">Cloud Discovery Dashboard</span></span>

<span data-ttu-id="1b23e-p110">**クラウド探索のダッシュ ボード****の生産性アプリケーションの検出**とも呼ばれるには、組織内でのクラウド アプリケーションの使用状況に関する情報が表示されます。アプリケーション、ユーザー、トラフィック、トランザクション、およびデジタル ダッシュ ボードを使用して複数の情報を表示することができます。クラウド探索のダッシュ ボードには、次のイメージが似ています。</span><span class="sxs-lookup"><span data-stu-id="1b23e-p110">The **Cloud Discovery Dashboard**, also referred to as **Productivity App Discovery**, shows information about cloud app usage within your organization. You can view information about apps, users, traffic, transactions, and more using this dashboard. The Cloud Discovery Dashboard resembles the following image:</span></span> 
  
![検出を選択して、Office 365 の CA のポータルでは、\>クラウド探索のダッシュ ボード](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="1b23e-171">**検出**には、Office 365 のクラウド アプリケーションのセキュリティのポータルでは、このダッシュ ボードを表示する\>**クラウド探索のダッシュ ボード**です。</span><span class="sxs-lookup"><span data-stu-id="1b23e-171">To get to this dashboard, in the Office 365 Cloud App Security portal, go to **Discover** \> **Cloud Discovery dashboard**.</span></span> 
  
![Office 365 CA ポータルでは、検出を選択します](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[<span data-ttu-id="1b23e-173">Office 365 Cloud App Security でアプリ検出結果を確認する</span><span class="sxs-lookup"><span data-stu-id="1b23e-173">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a><span data-ttu-id="1b23e-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="1b23e-174">Next steps</span></span>

- <span data-ttu-id="1b23e-175">[Office 365 クラウド アプリケーション セキュリティの使用例と使用に関するガイド](https://aka.ms/O365CASGuide)</span><span class="sxs-lookup"><span data-stu-id="1b23e-175">Get the [Office 365 Cloud App Security Use Cases and Usage Guide](https://aka.ms/O365CASGuide)</span></span>
    
- [<span data-ttu-id="1b23e-176">Office 365 Cloud App Security の使用準備</span><span class="sxs-lookup"><span data-stu-id="1b23e-176">Get ready for Office 365 Cloud App Security</span></span>](get-ready-for-office-365-cas.md)
    

