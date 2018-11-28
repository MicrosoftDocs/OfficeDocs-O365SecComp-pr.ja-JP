---
title: Office 365 Cloud App Security でアプリ検出結果を確認する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: セキュリティ管理の高度なアプリケーションの検出のレポートを確認することにより、組織内のユーザーがクラウドのアプリケーションを使用する方法の詳細については。ファイアウォールやプロキシのログ ファイルを使用してアプリケーションの検出のレポートを作成した後は、アプリケーションの検出のダッシュ ボードで、結果を確認します。
ms.openlocfilehash: ddf3826f5aac9d3c837cf66f1b97b4650df70f32
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706261"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a><span data-ttu-id="abe4a-104">Office 365 Cloud App Security でアプリ検出結果を確認する</span><span class="sxs-lookup"><span data-stu-id="abe4a-104">Review app discovery findings in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="abe4a-105">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="abe4a-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="abe4a-106">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="abe4a-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="abe4a-107">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="abe4a-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="abe4a-108">使用率。</span><span class="sxs-lookup"><span data-stu-id="abe4a-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="abe4a-109">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="abe4a-110">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="abe4a-111">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="abe4a-112">コースです!</span><span class="sxs-lookup"><span data-stu-id="abe4a-112">You are here!</span></span>  <br/> [<span data-ttu-id="abe4a-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="abe4a-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="abe4a-p102">クラウドの探索のダッシュ ボードは、クラウド アプリケーションの使用状況に関する詳細な情報を提供する組織の web トラフィックのログを使用して動作します。グローバル管理者、セキュリティ管理者、またはセキュリティのリーダーをしている、組織[で Office 365 のクラウド アプリケーションのセキュリティ アプリケーションの探索レポートを作成](create-app-discovery-reports-in-ocas.md)洞察を得るためにクラウド探索のダッシュ ボードを使用する場合は、どのように人で、組織は、Office 365 とその他のクラウド アプリケーションに使用しています。(クラウドの探索のダッシュ ボードとも呼ばれます生産性アプリケーション検出します。)</span><span class="sxs-lookup"><span data-stu-id="abe4a-p102">The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage. If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps. (The Cloud Discovery dashboard is also known as Productivity App Discovery.)</span></span>
  
 <span data-ttu-id="abe4a-117">**2018 年 3 月時点でクラウドの探索のダッシュ ボードには新機能**、組織内のユーザーの Office 365 とその他のアプリケーションの使用方法に関する詳細情報を表示するのにはより簡単にします。</span><span class="sxs-lookup"><span data-stu-id="abe4a-117">**As of March 2018, the Cloud Discovery dashboard has new features** that make it easier to view detailed information about how people in your organization are using Office 365 and other apps.</span></span> 
  
![クラウドの探索のダッシュ ボードが更新されました](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a><span data-ttu-id="abe4a-119">クラウドの探索のダッシュ ボードに移動します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-119">Go to the Cloud Discovery dashboard</span></span>

1. <span data-ttu-id="abe4a-p103">[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="abe4a-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="abe4a-122">セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="abe4a-122">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span><br/><span data-ttu-id="abe4a-123">(Office 365 のクラウド アプリケーションのセキュリティはまだ有効でない、グローバル管理者は、 [Office 365 のクラウド アプリケーションのセキュリティを有効にする](turn-on-office-365-cas.md)) 場合</span><span class="sxs-lookup"><span data-stu-id="abe4a-123">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="abe4a-124">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-124">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="abe4a-125">**検出**に\>**クラウド探索のダッシュ ボード**です。</span><span class="sxs-lookup"><span data-stu-id="abe4a-125">Go to **Discover** \> **Cloud Discovery dashboard**.</span></span>
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a><span data-ttu-id="abe4a-126">最上位ユーザー、IP アドレス、アプリケーション、およびリスクのレベルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="abe4a-126">See your top users, IP addresses, apps, and risk levels</span></span>

<span data-ttu-id="abe4a-127">クラウドの探索のダッシュ ボードでは、Office 365 で、組織、すべてのオープン アラート、最上位ユーザーは、およびリスクのレベルで使用されるアプリケーションの概要の概要について説明できます。</span><span class="sxs-lookup"><span data-stu-id="abe4a-127">The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.</span></span>
  
![クラウド探索 dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. <span data-ttu-id="abe4a-129">[**ダッシュ ボード**] タブで、画面の上部に、全体的なクラウド アプリケーション使用時、[概要] セクションで、組織内を探します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-129">On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen.</span></span> 
    
2. <span data-ttu-id="abe4a-130">組織で使用されているアプリケーションの**Office 365 のカテゴリ**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abe4a-130">See the **Office 365 categories** for apps that are used in your organization.</span></span> 
    
3. <span data-ttu-id="abe4a-131">Office 365 とその他のアプリケーションをこのビューでの使用量を確認するのには**検出されたアプリケーション**のウィジェットを見てください。</span><span class="sxs-lookup"><span data-stu-id="abe4a-131">Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view.</span></span> 
    
4. <span data-ttu-id="abe4a-132">Office 365 を使用し、クラウドのアプリケーションを組織内で最も人を識別するウィジェット**上のユーザー**と**一番上の IP アドレス**を確認します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-132">Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization.</span></span> 
    
5. <span data-ttu-id="abe4a-133">**本社所在地のアプリケーション**マップを使用して地理的な場所で人を使用しているアプリケーションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="abe4a-133">See where the apps people are using are by geographical location by using the **Apps headquarters location** map.</span></span> 
    
6. <span data-ttu-id="abe4a-p104">マップ] 領域で、上記を見て**リスクのレベル**の概要で検出されたアプリケーションのリスク ・ スコアです。同じグループと、**検出されたアプリケーション**の領域で使用しているカテゴリ別のリスクを見てことができます。たとえば、高、中、または低リスクのアプリケーションからは、各グループ内のトラフィック量を表示できます。</span><span class="sxs-lookup"><span data-stu-id="abe4a-p104">Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview. You can look at risks by the same groups and categories that you used in the **Discovered apps** area. For example, you can see how much traffic in each grouping is from high, medium, or low risk apps.</span></span> 
    
## <a name="dive-deeper-into-the-information"></a><span data-ttu-id="abe4a-137">中を深く探索情報</span><span class="sxs-lookup"><span data-stu-id="abe4a-137">Dive deeper into the information</span></span>

<span data-ttu-id="abe4a-138">クラウドの探索を使用するにはアプリケーション、サブドメイン、IP アドレス、およびユーザーについて詳しく説明をします。</span><span class="sxs-lookup"><span data-stu-id="abe4a-138">You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.</span></span>
  
1. <span data-ttu-id="abe4a-139">クラウドの探索のダッシュ ボードには、**検出されたアプリケーション**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-139">In the Cloud Discovery dashboard, choose the **Discovered apps** tab.</span></span> 
    
2. <span data-ttu-id="abe4a-140">「フィルター」セクションを使用すると、アプリケーション名カテゴリ、使用率のレベル、または見られる最後日付を表示します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-140">Use the filters section to view apps by name, category, usage level, or last seen date.</span></span>
    
3. <span data-ttu-id="abe4a-141">結果の一覧で、[**サブドメインを表示**する] リンクを表示するアプリケーション名を置きます。</span><span class="sxs-lookup"><span data-stu-id="abe4a-141">In the list of results, hover by an app name to reveal the **View sub-domains** link.</span></span><br/> <span data-ttu-id="abe4a-142">![サブドメインの詳細を表示するリンクを表示するアプリケーションの横にマウス ポインターを移動します。](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span><span class="sxs-lookup"><span data-stu-id="abe4a-142">![Hover next to an app to reveal a link to view subdomain details](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span></span><br/><span data-ttu-id="abe4a-143">選択したアプリケーションに関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="abe4a-143">Detailed information about the selected app will appear.</span></span>
    
4. <span data-ttu-id="abe4a-144">表示するには IP アドレスの詳細については、 **IP アドレス**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-144">To view details about IP addresses, choose the **IP addresses** tab.</span></span><br/><span data-ttu-id="abe4a-145">![クラウドの検出は、IP アドレスに関する詳細情報を示しています。](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span><span class="sxs-lookup"><span data-stu-id="abe4a-145">![Cloud Discovery shows detailed information about IP addresses](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span></span><br/><span data-ttu-id="abe4a-146">結果の一覧より詳細な情報を表示するのには個々 の IP アドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-146">In the list of results, select an individual IP address to view more detailed information.</span></span>
    
5. <span data-ttu-id="abe4a-147">組織内で Office 365 のユーザーに関する詳細を表示するには、[**ユーザー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-147">To view details about Office 365 users within your organization, choose the **Users** tab.</span></span><br/><span data-ttu-id="abe4a-148">![クラウドの検出 - ユーザー情報](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span><span class="sxs-lookup"><span data-stu-id="abe4a-148">![Cloud Discovery - users info](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span></span>
  
## <a name="exclude-entities"></a><span data-ttu-id="abe4a-149">エンティティを除外します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-149">Exclude entities</span></span>

<span data-ttu-id="abe4a-150">詳細な情報に集中するためには、特定のシステムのユーザーまたは IP アドレスを除外できます。</span><span class="sxs-lookup"><span data-stu-id="abe4a-150">You can exclude certain system users or IP addresses in order to focus on more specific information.</span></span>
  
1. <span data-ttu-id="abe4a-151">**設定**を選択して\>**雲の検出設定**します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-151">Choose **Settings** \> **Cloud Discovery settings**.</span></span>
    
2. <span data-ttu-id="abe4a-152">**エンティティを除外する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-152">Choose **Exclude entities**.</span></span>
    
3. <span data-ttu-id="abe4a-153">**除外するユーザー**または**除外される IP アドレス**のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-153">Choose either **Excluded users** or **Excluded IP addresses**.</span></span>
    
4. <span data-ttu-id="abe4a-154">ユーザーまたは IP アドレスを指定し、[**コメント**] ボックスで、これらのユーザーまたは IP アドレスを除外する理由についての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-154">Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses.</span></span> 
    
5. <span data-ttu-id="abe4a-155">[ **追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-155">Choose **Add**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="abe4a-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="abe4a-156">Next steps</span></span>

- [<span data-ttu-id="abe4a-157">確認し、アラート アクションを実行</span><span class="sxs-lookup"><span data-stu-id="abe4a-157">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="abe4a-158">アプリケーション検出レポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-158">Create app discovery reports</span></span>](create-app-discovery-reports-in-ocas.md)
    
- <span data-ttu-id="abe4a-159">[Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="abe4a-159">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

