---
title: Office 365 Cloud App Security でアプリ検出結果を確認する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: Office アプリケーションの検出レポートを確認する 365 cloud app Security は、組織内のユーザーがクラウドアプリをどのように使用するかについて詳しく知るのに役立ちます。 ファイアウォールとプロキシからのログファイルを使用してアプリ探索レポートを作成した後、アプリ検出ダッシュボードで結果を確認します。
ms.openlocfilehash: f50ad372450b2a1404829eeb6f6964c1d954dccd
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264977"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a><span data-ttu-id="59575-104">Office 365 Cloud App Security でアプリ検出結果を確認する</span><span class="sxs-lookup"><span data-stu-id="59575-104">Review app discovery findings in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="59575-105">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="59575-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="59575-106">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="59575-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="59575-107">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="59575-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="59575-108">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="59575-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="59575-109">評価の開始</span><span class="sxs-lookup"><span data-stu-id="59575-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="59575-110">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="59575-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="59575-111">展開を開始する</span><span class="sxs-lookup"><span data-stu-id="59575-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="59575-112">ここでは、</span><span class="sxs-lookup"><span data-stu-id="59575-112">You are here!</span></span>  <br/> [<span data-ttu-id="59575-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="59575-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="59575-114">クラウド検出ダッシュボードは、組織の web トラフィックログと連携して、クラウドアプリの使用状況に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="59575-114">The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage.</span></span> <span data-ttu-id="59575-115">グローバル管理者、セキュリティ管理者、またはセキュリティリーダーで、組織が[Office 365 cloud app security でアプリ探索レポートを作成](create-app-discovery-reports-in-ocas.md)している場合は、クラウド検出ダッシュボードを使用して、ユーザーの組織は Office 365 とその他のクラウドアプリを使用しています。</span><span class="sxs-lookup"><span data-stu-id="59575-115">If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps.</span></span> <span data-ttu-id="59575-116">(クラウド検出ダッシュボードは、生産性アプリの検出とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="59575-116">(The Cloud Discovery dashboard is also known as Productivity App Discovery.)</span></span>
  
 <span data-ttu-id="59575-117">クラウド検出ダッシュボードを使用すると、組織内のユーザーが Office 365 およびその他のアプリをどのように使用しているかについての詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="59575-117">The Cloud Discovery dashboard enables you to view detailed information about how people in your organization are using Office 365 and other apps.</span></span> 
  
![クラウド検出ダッシュボードが更新されました](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a><span data-ttu-id="59575-119">クラウド検出ダッシュボードに移動する</span><span class="sxs-lookup"><span data-stu-id="59575-119">Go to the Cloud Discovery dashboard</span></span>

1. <span data-ttu-id="59575-120">Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="59575-120">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
    
2. <span data-ttu-id="59575-121">[ **Cloud Discovery dashboard**の**検出** \> ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="59575-121">Go to **Discover** \> **Cloud Discovery dashboard**.</span></span>
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a><span data-ttu-id="59575-122">上位ユーザー、IP アドレス、アプリ、およびリスクレベルを表示する</span><span class="sxs-lookup"><span data-stu-id="59575-122">See your top users, IP addresses, apps, and risk levels</span></span>

<span data-ttu-id="59575-123">クラウド検出ダッシュボードには、組織内の Office 365 で使用されるアプリ、オープン通知、トップユーザー、およびリスクレベルの概要が示されています。</span><span class="sxs-lookup"><span data-stu-id="59575-123">The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.</span></span>
  
![クラウド検出のダッシュボート](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. <span data-ttu-id="59575-125">[**ダッシュボード**] タブで、画面の上部にある [概要] セクションで、組織でのクラウドアプリ全体の使用法を確認します。</span><span class="sxs-lookup"><span data-stu-id="59575-125">On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen.</span></span> 
    
2. <span data-ttu-id="59575-126">組織で使用されているアプリについては、「 **Office 365 カテゴリ**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59575-126">See the **Office 365 categories** for apps that are used in your organization.</span></span> 
    
3. <span data-ttu-id="59575-127">検出された**アプリ**ウィジェットを見て、Office 365 およびこのビュー内の他のアプリの使用状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="59575-127">Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view.</span></span> 
    
4. <span data-ttu-id="59575-128">[**上位ユーザー** ] および [**上位 IP アドレス**] ウィジェットを参照して、組織内で Office 365 および cloud アプリを使用しているユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="59575-128">Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization.</span></span> 
    
5. <span data-ttu-id="59575-129">「**アプリの本部**」マップを使用して、ユーザーが使用しているアプリが地理的な場所によってどのように使用されるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="59575-129">See where the apps people are using are by geographical location by using the **Apps headquarters location** map.</span></span> 
    
6. <span data-ttu-id="59575-130">「maps」領域の上にある「**リスクレベル**の概要」で、検出されたアプリのリスクスコアを確認します。</span><span class="sxs-lookup"><span data-stu-id="59575-130">Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview.</span></span> <span data-ttu-id="59575-131">[検出された**アプリ**] 領域で使用したものと同じグループとカテゴリを使用して、リスクを確認できます。</span><span class="sxs-lookup"><span data-stu-id="59575-131">You can look at risks by the same groups and categories that you used in the **Discovered apps** area.</span></span> <span data-ttu-id="59575-132">たとえば、各グループのトラフィックのうち、高、中、低のリスクアプリからのトラフィックの量を確認できます。</span><span class="sxs-lookup"><span data-stu-id="59575-132">For example, you can see how much traffic in each grouping is from high, medium, or low risk apps.</span></span> 
    
## <a name="dive-deeper-into-the-information"></a><span data-ttu-id="59575-133">情報を深く掘り下げる</span><span class="sxs-lookup"><span data-stu-id="59575-133">Dive deeper into the information</span></span>

<span data-ttu-id="59575-134">クラウド検出を使用すると、アプリ、サブドメイン、IP アドレス、およびユーザーの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="59575-134">You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.</span></span>
  
1. <span data-ttu-id="59575-135">クラウド検出ダッシュボードで、[検出された**アプリ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="59575-135">In the Cloud Discovery dashboard, choose the **Discovered apps** tab.</span></span> 
    
2. <span data-ttu-id="59575-136">[フィルター] セクションを使用して、名前、カテゴリ、使用レベル、または最後に表示された日付でアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="59575-136">Use the filters section to view apps by name, category, usage level, or last seen date.</span></span>
    
3. <span data-ttu-id="59575-137">結果の一覧で、アプリ名の上にカーソルを移動して、[**サブドメインの表示**] リンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="59575-137">In the list of results, hover by an app name to reveal the **View sub-domains** link.</span></span><br/> <span data-ttu-id="59575-138">![アプリの横にカーソルを移動して、サブドメインの詳細を表示するリンクを表示する](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span><span class="sxs-lookup"><span data-stu-id="59575-138">![Hover next to an app to reveal a link to view subdomain details](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span></span><br/><span data-ttu-id="59575-139">選択したアプリに関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="59575-139">Detailed information about the selected app will appear.</span></span>
    
4. <span data-ttu-id="59575-140">ip アドレスの詳細を表示するには、[ **ip アドレス**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="59575-140">To view details about IP addresses, choose the **IP addresses** tab.</span></span><br/><span data-ttu-id="59575-141">![クラウド検出では、IP アドレスに関する詳細情報が表示される](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span><span class="sxs-lookup"><span data-stu-id="59575-141">![Cloud Discovery shows detailed information about IP addresses](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span></span><br/><span data-ttu-id="59575-142">結果の一覧で、個別の IP アドレスを選択して、より詳細な情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="59575-142">In the list of results, select an individual IP address to view more detailed information.</span></span>
    
5. <span data-ttu-id="59575-143">組織内の Office 365 ユーザーの詳細を表示するには、[**ユーザー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="59575-143">To view details about Office 365 users within your organization, choose the **Users** tab.</span></span><br/><span data-ttu-id="59575-144">![クラウド検出-ユーザー情報](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span><span class="sxs-lookup"><span data-stu-id="59575-144">![Cloud Discovery - users info](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span></span>
  
## <a name="exclude-entities"></a><span data-ttu-id="59575-145">エンティティを除外する</span><span class="sxs-lookup"><span data-stu-id="59575-145">Exclude entities</span></span>

<span data-ttu-id="59575-146">特定のシステムユーザーまたは IP アドレスを除外して、より具体的な情報に焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="59575-146">You can exclude certain system users or IP addresses in order to focus on more specific information.</span></span>
  
1. <span data-ttu-id="59575-147">[**設定** \> ] [**クラウド検出設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="59575-147">Choose **Settings** \> **Cloud Discovery settings**.</span></span>
    
2. <span data-ttu-id="59575-148">[**エンティティを除外**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="59575-148">Choose **Exclude entities**.</span></span>
    
3. <span data-ttu-id="59575-149">除外された**ユーザー**または除外された**IP アドレス**のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="59575-149">Choose either **Excluded users** or **Excluded IP addresses**.</span></span>
    
4. <span data-ttu-id="59575-150">ユーザーまたは ip アドレスを指定し、[**コメント**] ボックスに、それらのユーザーまたは ip アドレスを除外する理由についての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="59575-150">Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses.</span></span> 
    
5. <span data-ttu-id="59575-151">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="59575-151">Choose **Add**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="59575-152">次のステップ</span><span class="sxs-lookup"><span data-stu-id="59575-152">Next steps</span></span>

- [<span data-ttu-id="59575-153">通知を確認して処理を実行する</span><span class="sxs-lookup"><span data-stu-id="59575-153">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="59575-154">アプリ検出レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="59575-154">Create app discovery reports</span></span>](create-app-discovery-reports-in-ocas.md)
    
- <span data-ttu-id="59575-155">[Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する</span><span class="sxs-lookup"><span data-stu-id="59575-155">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

