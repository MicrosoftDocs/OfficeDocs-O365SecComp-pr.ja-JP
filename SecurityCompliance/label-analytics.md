---
title: ラベル分析によるラベル使用状況の表示
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 保持ラベルと機密ラベルを作成した後に、テナント全体でどのように使用されているかを確認することができます。 Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターのラベル分析で、どのラベルが最もよく使われているか、どこで適用されているかを簡単に確認できます。
ms.openlocfilehash: d0289eb79dca04262ef61d58a8e622ae6d7cbe93
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254574"
---
# <a name="view-label-usage-with-label-analytics"></a><span data-ttu-id="5c9b9-104">ラベル分析によるラベル使用状況の表示</span><span class="sxs-lookup"><span data-stu-id="5c9b9-104">View label usage with label analytics</span></span>

<span data-ttu-id="5c9b9-105">保持ラベルと機密ラベルを作成した後に、テナント全体でどのように使用されているかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-105">After you create your retention labels and sensitivity labels, you’ll want to see how they’re being used across your tenant.</span></span> <span data-ttu-id="5c9b9-106">Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターのラベル分析で、どのラベルが最もよく使われているか、どこで適用されているかを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-106">With label analytics in the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly see which labels are used the most and where they’re being applied.</span></span>

<span data-ttu-id="5c9b9-107">たとえば、ラベル分析で次を確認できます:</span><span class="sxs-lookup"><span data-stu-id="5c9b9-107">For example, with label analytics, you can view the:</span></span>

- <span data-ttu-id="5c9b9-108">コンテンツに適用された保持ラベルと機密ラベルの合計数。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-108">Total number of retention labels and sensitivity labels applied to content.</span></span>
- <span data-ttu-id="5c9b9-109">上位のラベルと各ラベルの適用回数。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-109">Top labels and the count of how many times each label was applied.</span></span>
- <span data-ttu-id="5c9b9-110">ラベルの適用場所と、各場所での適用回数。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-110">Locations where labels are applied and the count for each location.</span></span>
- <span data-ttu-id="5c9b9-111">保持レベルが変更または削除されたファイルとフォルダーの数。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-111">Count for how many files and folders had their retention label changed or removed.</span></span>

<span data-ttu-id="5c9b9-112">ラベル分析は、[[Microsoft 365 コンプライアンス センター]](https://compliance.microsoft.com/labelanalytics) または [[Microsoft 365 セキュリティ センター]](https://security.microsoft.com/labelanalytics)  >  **[分類]**  >  **[ラベル分析]** で確認できます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-112">You can find label analytics in the [Microsoft 365 compliance center](https://compliance.microsoft.com/labelanalytics) or [Microsoft 365 security center](https://security.microsoft.com/labelanalytics) > **Classification** > **Label analytics**.</span></span>

![ラベル分析のページ](media/label-analytics-page.png)

## <a name="sensitivity-label-usage"></a><span data-ttu-id="5c9b9-114">機密ラベルの使用状況</span><span class="sxs-lookup"><span data-stu-id="5c9b9-114">Sensitivity label usage</span></span>

<span data-ttu-id="5c9b9-115">機密ラベルの使用状況のデータは、Azure Information Protection のレポートから取得します。詳細については、「[Azure Information Protection の集中レポート](https://docs.microsoft.com/ja-JP/azure/information-protection/reports-aip)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-115">The data on sensitivity label usage is pulled from the reports for Azure Information Protection – for more information, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/ja-JP/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="5c9b9-116">Azure Information Protection のレポートは、Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティセンターの機密ラベルに対するラベル分析にも適用される[前提条件](https://docs.microsoft.com/ja-JP/azure/information-protection/reports-aip#prerequisites-for-azure-information-protection-analytics)があるのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-116">Note that the Azure Information Protection reports have [prerequisites](https://docs.microsoft.com/ja-JP/azure/information-protection/reports-aip#prerequisites-for-azure-information-protection-analytics) that also apply to label analytics on sensitivity labels in the Microsoft 365 compliance center and Microsoft 365 security center.</span></span> <span data-ttu-id="5c9b9-117">たとえば、これらのレポートは Azure Information Protection のクライアントとスキャン プログラムから Azure Log Analytics サービスに基づいて集中管理された場所に情報保護の監視イベントを送信した結果なので、Log Analytics を含む Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-117">For example, you need an Azure subscription that includes the Log Analytics because these reports are a result of sending information protection audit events from Azure Information Protection clients and scanners to a centralized location based on Azure Log Analytics service.</span></span>

<span data-ttu-id="5c9b9-118">機密ラベルの使用状況は:</span><span class="sxs-lookup"><span data-stu-id="5c9b9-118">For sensitivity label usage:</span></span>

- <span data-ttu-id="5c9b9-119">データの待機時間はありません。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-119">There is no latency in the data.</span></span> <span data-ttu-id="5c9b9-120">リアルタイムのレポートです。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-120">This is a real-time report.</span></span>
- <span data-ttu-id="5c9b9-121">上位の各ラベルの数を確認するには、棒グラフをポイントすると表示されるツール ヒントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-121">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="5c9b9-122">レポートでは、アプリごとに機密ラベルがどこに適用されているかを示します (保持ラベルは場所ごとに示されます)。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-122">The report shows where sensitivity labels are applied per app (whereas retention labels are shown per location).</span></span>

![機密ラベルの使用状況レポート](media/sensitivity-label-usage-report.png)

## <a name="retention-label-usage"></a><span data-ttu-id="5c9b9-124">保持ラベルの使用状況</span><span class="sxs-lookup"><span data-stu-id="5c9b9-124">Retention label usage</span></span>

<span data-ttu-id="5c9b9-125">このレポートでは、上位のラベルとそれがどこで適用されているかについてクイック ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-125">This report shows a quick view of what the top labels are and where they’re applied.</span></span> <span data-ttu-id="5c9b9-126">SharePoint や OneDrive のコンテンツがどのようにラベル付けされているかについての詳細は、「[ドキュメントのラベル アクティビティを表示する](view-label-activity-for-documents.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-126">For more detailed information on how content in SharePoint and OneDrive is labeled, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

<span data-ttu-id="5c9b9-127">保持ラベルの使用状況は:</span><span class="sxs-lookup"><span data-stu-id="5c9b9-127">For retention label usage:</span></span>

- <span data-ttu-id="5c9b9-128">データは、週ごとに集計されるため、データがレポートに表示されるまで最大 7 日間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-128">Data is aggregated weekly, so it may take up to seven days for data to appear in the report.</span></span>
- <span data-ttu-id="5c9b9-129">上位の各ラベルの数を確認するには、棒グラフをポイントすると表示されるツール ヒントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-129">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="5c9b9-130">レポートでは、場所ごとに保持ラベルがどこに適用されているかを示します (機密ラベルはアプリごとに示されます)。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-130">The report shows where retention labels are applied per location (whereas sensitivity labels are shown per app).</span></span>
- <span data-ttu-id="5c9b9-131">保持レベルは、テナントの全期間のデータの概要で、特定の日付範囲にフィルター処理はされません。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-131">For retention labels, this is a summary of the all-time data in your tenant; it’s not filtered to a specific date range.</span></span> <span data-ttu-id="5c9b9-132">これに対し、[ラベル アクティビティ エクスプローラー](view-label-activity-for-documents.md)は、過去 30 日間のみのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-132">By contrast, the [Label Activity Explorer](view-label-activity-for-documents.md) shows data from only the past 30 days.</span></span>

![保持ラベルの使用状況レポート](media/retention-label-usage-report.png)

## <a name="view-all-content-with-a-specific-retention-label"></a><span data-ttu-id="5c9b9-134">特定の保持ラベルが付いたコンテンツをすべて表示する</span><span class="sxs-lookup"><span data-stu-id="5c9b9-134">View all content with a specific retention label</span></span>

<span data-ttu-id="5c9b9-135">保持ラベルの使用状況レポートから、そのラベルが適用されたすべてのコンテンツを簡単に参照することができます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-135">From the retention label usage report, you can quickly explore all content with that label applied.</span></span> <span data-ttu-id="5c9b9-136">(この機能については、現在作業中のためすべてのラベル付けされたコンテンツを見るにはいくつかの手順が必要になります。)</span><span class="sxs-lookup"><span data-stu-id="5c9b9-136">(Note that we're currently working on this feature, so that it will take fewer steps to view all the labeled content.)</span></span>

<span data-ttu-id="5c9b9-137">最初に、レポートの下部にある **[詳細の表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-137">First, choose **View Details** at the bottom of the report.</span></span>

![保持ラベルの使用状況レポートの下部にある [詳細の表示] オプション](media/retention-label-usage-view-details.png)

<span data-ttu-id="5c9b9-139">次に、保持ラベル > **右側のウィンドウの [アイテムを参照する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-139">Then choose a retention label > **Explore items** in the right pane.</span></span>

![右側のウィンドウの [アイテムを参照する] オプション](media/retention-label-usage-explore-items.png)

<span data-ttu-id="5c9b9-141">そのラベルで、**[アクティビティ]** タブを選択すると、そのラベルの場所ごとのアイテム数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-141">For that label, you can choose the **Activity** tab to view a count of items with that label by location.</span></span>

![保持ラベルの [アクティビティ] タブ](media/retention-label-usage-activity-tab.png)

<span data-ttu-id="5c9b9-143">**[このラベルを含むアイテム]** タブも選択できます。それから、特定の場所について確認することができます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-143">You can also choose the **Items with this label** tab. Then you can drill into specific locations:</span></span>

- <span data-ttu-id="5c9b9-144">Exchange Online では、メールボックスの一覧とメールボックスごとにラベルが付いたアイテムの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-144">For Exchange Online, you see a list of mailboxes with the count of labeled items in each mailbox.</span></span>
- <span data-ttu-id="5c9b9-145">SharePoint Online と OneDrive for Business では、サイト コレクションの一覧と、OneDrive アカウントをそれぞれの場所のラベル付けされたアイテムの数と合わせて確認できます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-145">For SharePoint Online and OneDrive for Business, you see a list of site collections and OneDrive accounts with the count of labeled items in each location.</span></span>

<span data-ttu-id="5c9b9-146">メールボックスまたはサイト コレクションを選択すると、その場所の保持ラベルを含むアイテムの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-146">When you choose a mailbox or site collection, you can view a list of items with that retention label in that location.</span></span>

![[このラベルを含むアイテム] タブでその保持ラベルを持つすべてのアイテムを表示](media/retention-label-usage-content-explorer.png)

## <a name="permissions"></a><span data-ttu-id="5c9b9-148">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="5c9b9-148">Permissions</span></span>

<span data-ttu-id="5c9b9-149">ラベル分析を確認するには、Azure Active Directory で次のいずれかの役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-149">To view label analytics, you must be assigned one of the following roles in Azure Active Directory:</span></span>

- <span data-ttu-id="5c9b9-150">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="5c9b9-150">Global administrator</span></span>
- <span data-ttu-id="5c9b9-151">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="5c9b9-151">Compliance administrator</span></span>
- <span data-ttu-id="5c9b9-152">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="5c9b9-152">Security administrator</span></span>
- <span data-ttu-id="5c9b9-153">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="5c9b9-153">Security reader</span></span>

<span data-ttu-id="5c9b9-154">さらに、これらのレポートでは、Azure Monitor を使用して、組織が所有する Log Analytics ワークスペースにデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-154">In addition, note these reports use Azure Monitor to store the data in a Log Analytics workspace that your organization owns.</span></span> <span data-ttu-id="5c9b9-155">そのため、データが格納されている Azure Monitor のワークスペースの閲覧者としてユーザーを追加しておく必要があります。詳細については、「[Azure Information Protection の分析に必要なアクセス許可](https://docs.microsoft.com/ja-JP/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9b9-155">Therefore, the user should be added as a reader to the Azure Monitoring worksapce that holds the data - for more information, see [Permissions required for Azure Information Protection analytics](https://docs.microsoft.com/ja-JP/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span></span>

