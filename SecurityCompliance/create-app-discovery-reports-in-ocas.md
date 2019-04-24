---
title: Office 365 Cloud App Security を使用して アプリ 検出 レポートを作成する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: office 365 Cloud App Security を使用してレポートを作成します。これにより、組織内のユーザーが office 365 や他のアプリをどのように使用しているかを把握することができます。
ms.openlocfilehash: 23165a52a09e5bcde46ee3ab2110dc17d0faf7f4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259642"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a><span data-ttu-id="dff76-103">Office 365 Cloud App Security を使用して アプリ 検出 レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="dff76-103">Create app discovery reports using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="dff76-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="dff76-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="dff76-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="dff76-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="dff76-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="dff76-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="dff76-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="dff76-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="dff76-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="dff76-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="dff76-109">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="dff76-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="dff76-110">展開を開始する</span><span class="sxs-lookup"><span data-stu-id="dff76-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="dff76-111">ここでは、</span><span class="sxs-lookup"><span data-stu-id="dff76-111">You are here!</span></span>  <br/> [<span data-ttu-id="dff76-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="dff76-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="dff76-113">Office 365 cloud App security では、全体管理者、セキュリティ管理者、およびセキュリティ閲覧者が組織内のユーザーが使用しているクラウドサービスについて洞察を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="dff76-113">Office 365 Cloud App Security helps global administrators, security administrators, and security readers gain insight into the cloud services people in an organization are using.</span></span> <span data-ttu-id="dff76-114">たとえば、ユーザーがドキュメントを格納して共同作業する場所、および Office 365 の外部にあるアプリまたはサービスにアップロードされるデータの量を確認できます。</span><span class="sxs-lookup"><span data-stu-id="dff76-114">For example, you can see where users are storing and collaborating on documents and how much data is being uploaded to apps or services that are outside of Office 365.</span></span>
  
<span data-ttu-id="dff76-115">アプリ検出レポートを生成するには、ファイアウォールとプロキシから web トラフィックログファイルを手動でアップロードし、Office 365 Cloud app Security でレポートのファイルを解析して分析します。</span><span class="sxs-lookup"><span data-stu-id="dff76-115">To generate an app discovery report, you manually upload your web traffic log files from your firewalls and proxies, and then Office 365 Cloud App Security parses and analyzes those files for your report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dff76-116">この記事で説明されているタスクを実行するには、全体管理者、セキュリティ管理者、またはセキュリティリーダーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dff76-116">You must be a global administrator, security administrator, or security reader to perform the tasks described in this article.</span></span> <span data-ttu-id="dff76-117">詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dff76-117">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="create-a-report-with-app-discovery"></a><span data-ttu-id="dff76-118">アプリ検出を使用してレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="dff76-118">Create a report with app discovery</span></span>

<span data-ttu-id="dff76-119">アプリ検出レポートを作成するには、分析するログファイルのベンダーデータソースを特定し、ログファイルを選択して、レポートを要求します。</span><span class="sxs-lookup"><span data-stu-id="dff76-119">To create an app discovery report, you identify the vendor data source for the log files that you want to have analyzed, select the log files, and then request the report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dff76-120">ピークのトラフィック期間を含む web トラフィックログファイルを使用して、組織での使用の最適な表現を取得します。</span><span class="sxs-lookup"><span data-stu-id="dff76-120">Use web traffic log files that include peak traffic periods to get the best representation of usage in your organization.</span></span> 
  
1. <span data-ttu-id="dff76-121">[Office 365 Cloud App Security の web トラフィックログとデータソースを](web-traffic-logs-and-data-sources-for-ocas.md)収集します。</span><span class="sxs-lookup"><span data-stu-id="dff76-121">Collect your [web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span></span>
    
2. <span data-ttu-id="dff76-122">Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="dff76-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> 
       
3. <span data-ttu-id="dff76-123">[**検出** \> ] [**新しいレポートの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff76-123">Choose **Discover** \> **Create new report**.</span></span> <br><span data-ttu-id="dff76-124">![Office 365 CAS ポータルで、[検出] を選択します。](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span><span class="sxs-lookup"><span data-stu-id="dff76-124">![In the Office 365 CAS portal, choose Discover](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span></span><br>
  
4. <span data-ttu-id="dff76-125">レポートの名前と説明を指定し、[**データソース**] ボックスの一覧で web トラフィックログのデータソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="dff76-125">Specify a name and description for your report, and then select the data source for your web traffic logs in the **Data source** list.</span></span> <br><span data-ttu-id="dff76-126">![O365 CAS で、[ディスカバー \> ] [新しいレポートの作成] を選択します。](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span><span class="sxs-lookup"><span data-stu-id="dff76-126">![In O365 CAS, choose Discover \> Create new report](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span></span><br><span data-ttu-id="dff76-127">使用するデータソースが表示されていない場合は、追加するように要求することができます。</span><span class="sxs-lookup"><span data-stu-id="dff76-127">If a data source that you'd like to use is not listed, you can request that it be added.</span></span> <span data-ttu-id="dff76-128">[**データソース**] として [**その他**] を選択し、アップロードするデータソースの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="dff76-128">Select **Other** for **Data source**, and then type the name of the data source that you're trying to upload.</span></span> <span data-ttu-id="dff76-129">ログを確認して、それを生成したデータソースのサポートを追加するかどうかを確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="dff76-129">We'll review the log, and let you know if we add support for the data source that generated it.</span></span> 
  
5. <span data-ttu-id="dff76-130">収集したログファイルの場所に移動し、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="dff76-130">Browse to the location of the log files you collected and select the files.</span></span> <span data-ttu-id="dff76-131">ログファイルは、レポート用に選択したデータソースによって生成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dff76-131">The log files must have been generated by the data source that you chose for the report.</span></span>
    
6. <span data-ttu-id="dff76-132">[**作成**] をクリックして、レポート作成プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="dff76-132">Click **Create** to start the report creation process.</span></span> 
    
7. <span data-ttu-id="dff76-133">レポートの状態を表示するには、[**スナップショットレポートの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dff76-133">To see the status of the report, click **Manage snapshot reports**.</span></span> <span data-ttu-id="dff76-134">レポートの準備が整ったら、[レポートの**表示**] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dff76-134">When a report is ready, you'll see the **View report** option.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="dff76-135">次のステップ</span><span class="sxs-lookup"><span data-stu-id="dff76-135">Next steps</span></span>

- [<span data-ttu-id="dff76-136">通知を確認して処理を実行する</span><span class="sxs-lookup"><span data-stu-id="dff76-136">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="dff76-137">Office 365 Cloud App Security でアプリ検出結果を確認する</span><span class="sxs-lookup"><span data-stu-id="dff76-137">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="dff76-138">[Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する</span><span class="sxs-lookup"><span data-stu-id="dff76-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

