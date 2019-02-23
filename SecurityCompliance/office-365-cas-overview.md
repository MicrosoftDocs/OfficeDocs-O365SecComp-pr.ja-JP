---
title: Office 365 Cloud App Security の概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'office 365 Cloud App Security では、office 365 の不審なアクティビティについての洞察が得られるため、問題が発生する可能性があり、必要に応じて、セキュリティの問題に対処するための処置を取ることができます。 '
ms.openlocfilehash: 974858a547d9af2db600f9856efbce619a3b38e4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220177"
---
# <a name="overview-of-office-365-cloud-app-security"></a><span data-ttu-id="ac298-103">Office 365 Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="ac298-103">Overview of Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="ac298-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ac298-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="ac298-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ac298-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="ac298-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ac298-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="ac298-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="ac298-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ac298-108">ここでは、</span><span class="sxs-lookup"><span data-stu-id="ac298-108">You are here!</span></span>  <br/> [<span data-ttu-id="ac298-109">次の手順</span><span class="sxs-lookup"><span data-stu-id="ac298-109">Next step</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="ac298-110">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="ac298-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="ac298-111">展開を開始する</span><span class="sxs-lookup"><span data-stu-id="ac298-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="ac298-112">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="ac298-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="ac298-p101">office 365 Cloud App Security は office 365 Enterprise E5 で利用できます。組織で別の office 365 Enterprise サブスクリプションを使用している場合、office 365 Cloud App Security をアドオンとして購入することができます。(全体管理者として、Office 365 管理センターで、[**課金** \>の**サブスクリプションの追加**] を選択します。)詳細については、「office 365 プラットフォームサービスの説明」を参照してください[。 office 365 セキュリティ&amp;コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)で、 [office 365 for business のアドオンを購入または編集](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)します。</span><span class="sxs-lookup"><span data-stu-id="ac298-p101">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span> 
  
<span data-ttu-id="ac298-p102">office 365 Cloud App Security では、office 365 の不審なアクティビティを把握しているため、問題が発生する可能性がある状況を調査し、必要に応じて、セキュリティの問題に対処するための処置を取ることができます。office 365 Cloud App Security では、例外的または不審なアクティビティに対してトリガーされた通知の通知を受け取ることができます。組織のデータが office 365 にどのようにアクセスおよび使用されているかを確認し、ユーザーアカウントに疑わしいアクティビティが発生して中断し、通知がトリガーされた後、ユーザーが Office 365 アプリに再度ログインする。この記事では、Office 365 Cloud App のセキュリティ機能の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac298-p102">Office 365 Cloud App Security gives you insight into suspicious activity in Office 365 so you can investigate situations that are potentially problematic and, if needed, take action to address security issues. With Office 365 Cloud App Security, you can receive notifications of triggered alerts for atypical or suspicious activities, see how your organization's data in Office 365 is accessed and used, suspend user accounts exhibiting suspicious activity, and require users to log back in to Office 365 apps after an alert has been triggered. Read this article to get an overview of Office 365 Cloud App Security features and capabilities.</span></span>
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="ac298-119">Office 365 Cloud App Security ポータルを見つける方法</span><span class="sxs-lookup"><span data-stu-id="ac298-119">How to find the Office 365 Cloud App Security portal</span></span>

> [!NOTE]
> <span data-ttu-id="ac298-p103">office 365 Cloud App Security ポータルにアクセスするには、office 365 全体管理者、セキュリティ管理者、またはセキュリティリーダである必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac298-p103">To access the Office 365 Cloud App Security portal, you must be an Office 365 global administrator, security administrator, or security reader. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
<span data-ttu-id="ac298-122">Office 365 Cloud App Security ポータルにアクセスするには、に[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)移動してサインインします。</span><span class="sxs-lookup"><span data-stu-id="ac298-122">You can get to the Office 365 Cloud App Security portal by going to [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span> 

<span data-ttu-id="ac298-p104">Office 365 セキュリティ&amp;コンプライアンスセンターから入手することもできます。そのためには、次のいずれかの方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac298-p104">You can also get there from the Office 365 Security &amp; Compliance Center. Here's one good way to do it:</span></span>
  
1. <span data-ttu-id="ac298-p105">に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。(これにより、セキュリティ&amp;コンプライアンスセンターに移動できます。)</span><span class="sxs-lookup"><span data-stu-id="ac298-p105">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span>
    
2. <span data-ttu-id="ac298-127">セキュリティ&amp; /コンプライアンスセンターで、[**警告** \>の**管理] [詳細通知の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac298-127">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span> <br/><span data-ttu-id="ac298-128">![Office 365 Cloud App Security に移動するには、[高度な通知の管理] を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="ac298-128">![Choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="ac298-129">(office 365 cloud app security がまだ有効になっておらず、全体管理者である場合は、 [office 365 Cloud app security を有効](turn-on-office-365-cas.md)にします。)</span><span class="sxs-lookup"><span data-stu-id="ac298-129">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="ac298-130">[ **Office 365 Cloud App Security に移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac298-130">Choose **Go to Office 365 Cloud App Security**.</span></span> 
    
## <a name="policies"></a><span data-ttu-id="ac298-131">[Policies]</span><span class="sxs-lookup"><span data-stu-id="ac298-131">Policies</span></span>

<span data-ttu-id="ac298-p106">Office 365 Cloud App Security は、組織に対して定義されているポリシーを使用して動作します。Office 365 Cloud App Security を使用すると、組織は多数の事前に定義された異常検出ポリシーとアクティビティポリシーのいくつかのテンプレートを取得します。これらのポリシーは、一般的な異常を検出し、危険な IP アドレスからログインしているユーザーを識別し、ランサムウェアのアクティビティを検出し、企業以外の IP アドレスから管理者アクティビティを検出するなどの目的で設計されています。</span><span class="sxs-lookup"><span data-stu-id="ac298-p106">Office 365 Cloud App Security works with the policies that are defined for your organization. With Office 365 Cloud App Security, your organization gets many predefined anomaly detection policies and several templates for activity policies. These policies are designed to detect general anomalies, identify users logging in from a risky IP address, detect ransomware activities, detect administrator activities from non-corporate IP addresses, and more.</span></span>
  
![CAS ポータルで、[コントロール\>テンプレート] を選択してポリシーテンプレートを表示または作成します。](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
<span data-ttu-id="ac298-136">ポリシーテンプレートを表示または使用するには、Office 365 Cloud App Security ポータルで、[**コントロール** \> **テンプレート**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac298-136">To view/use policy templates, in the Office 365 Cloud App Security portal, go to **Control** \> **Templates**.</span></span> 
  
![O365 CAS ポータルで、[コントロール] を選択します。](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
<span data-ttu-id="ac298-138">ポリシーの詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac298-138">To learn more about policies, see the following resources:</span></span>
  
- [<span data-ttu-id="ac298-139">Office 365 Cloud App Security のアクティビティ ポリシーと警告</span><span class="sxs-lookup"><span data-stu-id="ac298-139">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="ac298-140">Office 365 Cloud App Security の異常検出ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac298-140">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a><span data-ttu-id="ac298-141">警告</span><span class="sxs-lookup"><span data-stu-id="ac298-141">Alerts</span></span>

<span data-ttu-id="ac298-p107">ポリシーが定義されている場合、検出された疑わしいまたは例外的なアクティビティについて通知されます。組織の通知を表示するには、画面上部のナビゲーションバーにある [**通知**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac298-p107">When policies are defined, alerts notify you about suspicious or atypical activities that were detected. To view alerts for your organization, choose **Alerts** in the navigation bar across the top of the screen.</span></span> 
  
![[通知] ページには、トリガーされた通知と実行されたアクションが表示されます。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
<span data-ttu-id="ac298-p108">アラートがトリガーされたときに、その通知を確認して、何が起こっているのかについて詳しく知ることができます。その後も、アクティビティが疑わしい場合は、アクションを実行できます。たとえば、問題についてユーザーに通知したり、ユーザーの office 365 へのサインインを中断したり、office 365 アプリにサインインし直すようにユーザーに要求することができます。</span><span class="sxs-lookup"><span data-stu-id="ac298-p108">As alerts are triggered you can review them to learn more about what is going on. Then, if the activity is still suspicious, you can take action. For example, you can notify a user about an issue, suspend a user from signing in to Office 365, or require a user to sign back in to Office 365 apps.</span></span>
  
<span data-ttu-id="ac298-148">通知の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac298-148">To learn more about alerts, see the following resources:</span></span>
  
- [<span data-ttu-id="ac298-149">Office 365 Cloud App Security のアクティビティ ポリシーと警告</span><span class="sxs-lookup"><span data-stu-id="ac298-149">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="ac298-150">Office 365 Cloud App Security の異常検出ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac298-150">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="ac298-151">Office 365 Cloud App Security alerts を確認してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="ac298-151">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a><span data-ttu-id="ac298-152">アクティビティログ</span><span class="sxs-lookup"><span data-stu-id="ac298-152">Activity logs</span></span>

<span data-ttu-id="ac298-153">Office 365 Cloud App Security のアクティビティログページにあるユーザーアクティビティに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac298-153">View information about user activities on your Activity log page in Office 365 Cloud App Security.</span></span>
  
![O365 CAS ポータルで、[アクティビティログ\>の調査] を選択します。](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
<span data-ttu-id="ac298-155">このページを表示するには、Office 365 Cloud App Security ポータルで、[ \*\*\*\* \> **アクティビティログ**の調査] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac298-155">To get to this page, in the Office 365 Cloud App Security portal, go to **Investigate** \> **Activity log**.</span></span> 
  
![O365 CAS ポータルで、[調査] を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
<span data-ttu-id="ac298-p109">web トラフィックログは Office 365 Cloud App Security でも使用できます。これらのログファイルに含まれる詳細については、「ユーザーのアクティビティ」を参照してください。ログファイルは、Barracuda、ブルーコート、チェックポイント、Cisco、clavister、Dell SonicWALL、for et、Juniper、McAfee、Microsoft、Palo Alto、Sophos、Squid、websence、Zscaler などから使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac298-p109">You can use your web traffic logs with Office 365 Cloud App Security, too. The more details that are included in those log files, the better visibility you'll have into user activity. You can use log files from Barracuda, Blue Coat, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, Squid, Websence, Zscaler, and more.</span></span>
  
[<span data-ttu-id="ac298-160">Office 365 Cloud App Security の web トラフィックログとデータソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ac298-160">Learn about web traffic logs and data sources for Office 365 Cloud App Security</span></span>](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a><span data-ttu-id="ac298-161">OAuth アプリ</span><span class="sxs-lookup"><span data-stu-id="ac298-161">OAuth apps</span></span>

<span data-ttu-id="ac298-162">office 365 Cloud App Security では、組織内のユーザーが office 365 のデータにアクセスするサードパーティ製アプリを使用することを許可または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="ac298-162">With Office 365 Cloud App Security, you can allow or prevent people in your organization to use third-party apps that access data in Office 365.</span></span>
  
![O365 CAS では、[調査] メニューから [OAuth アプリの管理] ページにアクセスできます。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
<span data-ttu-id="ac298-164">このページを表示するには、「 **OAuth アプリ**を**調査** \>する」に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac298-164">To get to this page, go to **Investigate** \> **OAuth apps**.</span></span> 
  
![O365 CAS ポータルで、[調査] を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[<span data-ttu-id="ac298-166">Office 365 Cloud App Security を使用して OAuth アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="ac298-166">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a><span data-ttu-id="ac298-167">クラウド検出ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="ac298-167">Cloud Discovery Dashboard</span></span>

<span data-ttu-id="ac298-p110">**クラウド検出ダッシュボード**(**生産性アプリの検出**とも呼ばれます) は、組織内でのクラウドアプリの使用に関する情報を示しています。このダッシュボードを使用して、アプリ、ユーザー、トラフィック、トランザクションなどに関する情報を表示できます。クラウド検出ダッシュボードは、次のようなイメージです。</span><span class="sxs-lookup"><span data-stu-id="ac298-p110">The **Cloud Discovery Dashboard**, also referred to as **Productivity App Discovery**, shows information about cloud app usage within your organization. You can view information about apps, users, traffic, transactions, and more using this dashboard. The Cloud Discovery Dashboard resembles the following image:</span></span> 
  
![Office 365 CAS ポータルで、[クラウド検出\>ダッシュボードの検出] を選択します。](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="ac298-172">このダッシュボードにアクセスするには、Office 365 cloud App Security ポータルで、[ \*\*\*\* \> **cloud Discovery dashboard**の検出] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac298-172">To get to this dashboard, in the Office 365 Cloud App Security portal, go to **Discover** \> **Cloud Discovery dashboard**.</span></span> 
  
![Office 365 CAS ポータルで、[検出] を選択します。](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[<span data-ttu-id="ac298-174">Office 365 Cloud App Security でアプリ検出結果を確認する</span><span class="sxs-lookup"><span data-stu-id="ac298-174">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a><span data-ttu-id="ac298-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="ac298-175">Next steps</span></span>

- <span data-ttu-id="ac298-176">[Office 365 Cloud App Security の使用例と利用状況ガイド](https://aka.ms/O365CASGuide)を取得する</span><span class="sxs-lookup"><span data-stu-id="ac298-176">Get the [Office 365 Cloud App Security Use Cases and Usage Guide](https://aka.ms/O365CASGuide)</span></span>
    
- [<span data-ttu-id="ac298-177">Office 365 Cloud App Security の使用準備</span><span class="sxs-lookup"><span data-stu-id="ac298-177">Get ready for Office 365 Cloud App Security</span></span>](get-ready-for-office-365-cas.md)
    

