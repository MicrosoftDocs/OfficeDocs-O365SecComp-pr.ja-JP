---
title: 保管担当者監査アクティビティを表示する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f4bac6ae7a51b01ff6f9b303bb5c2f4911bdb53d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153909"
---
# <a name="view-custodian-audit-activity"></a><span data-ttu-id="69e25-102">保管担当者監査アクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="69e25-102">View custodian audit activity</span></span>

<span data-ttu-id="69e25-103">ユーザーが特定のドキュメントを表示したかどうか、またはメールボックスからアイテムを削除したかどうかを確認する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="69e25-103">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="69e25-104">上級電子情報開示は、セキュリティ & コンプライアンスセンターの既存の監査ログ検索ツールと統合されました。</span><span class="sxs-lookup"><span data-stu-id="69e25-104">Advanced eDiscovery is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="69e25-105">この組み込みの操作を使用すると、高度な電子情報開示保管担当者管理ツールを使用して、ケース内で保管担当者のアクティビティに容易にアクセスして検索することで、調査を促進できます。</span><span class="sxs-lookup"><span data-stu-id="69e25-105">Using this embedded experience, you can use the Advanced eDiscovery Custodian Management tool to facilitate your investigation by easily accessing and searching the activity for custodians within your case.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="69e25-106">始める前に</span><span class="sxs-lookup"><span data-stu-id="69e25-106">Before you begin</span></span>

<span data-ttu-id="69e25-107">Office 365 監査ログを検索するには、Exchange Online で [表示のみの監査ログまたは監査ログの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69e25-107">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log.</span></span> <span data-ttu-id="69e25-108">既定では、これらの役割は、Exchange 管理センターの [アクセス許可] ページで、コンプライアンス管理および組織の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="69e25-108">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="69e25-109">高度な電子情報開示監査ログを最低限の特権レベルで検索できるようにするには、Exchange Online でカスタム役割グループを作成し、表示のみの監査ログまたは監査ログの役割を追加し、そのユーザーを新しい役割グループのメンバーとして追加することができます。</span><span class="sxs-lookup"><span data-stu-id="69e25-109">To give a user the ability to search the Advanced eDiscovery audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="69e25-110">詳細については、「Manage role groups in Exchange Online」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e25-110">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69e25-111">セキュリティ & コンプライアンスセンターの [アクセス許可] ページでユーザーに監査ログまたは監査ログの役割を割り当てると、Office 365 の監査ログを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="69e25-111">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the Office 365 audit log.</span></span> <span data-ttu-id="69e25-112">Exchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="69e25-112">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="69e25-113">これは、監査ログの検索に使用される基礎となるコマンドレットが Exchange Online のコマンドレットであるためです。</span><span class="sxs-lookup"><span data-stu-id="69e25-113">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a><span data-ttu-id="69e25-114">手順 1: 保管担当者によって実行されたアクティビティの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="69e25-114">Step 1: Search the audit log for activities performed by a custodian</span></span>

1. <span data-ttu-id="69e25-115">**EDiscovery _GT_ Advanced ediscovery**に移動し、ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="69e25-115">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="69e25-116">[**保管担当者**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="69e25-116">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="69e25-117">リストから保管担当者を選択し、フライアウトページで [**保管担当者アクティビティの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69e25-117">Select a custodian from the list, and then click **View custodian activity** on the flyout page.</span></span>

    <span data-ttu-id="69e25-118">[保管担当者アクティビティ] 検索ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-118">The Custodian activities search page is displayed.</span></span> <span data-ttu-id="69e25-119">メモ前の手順で選択した保管担当者が [**保管担当者**] ドロップダウンボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-119">Note the custodian you selected in the previous step is displayed in the **Custodian** drop-down box.</span></span> <span data-ttu-id="69e25-120">ドロップダウンボックスではさまざまな保管担当者を選択できますが、一度に1つの保管担当者のアクティビティのみを検索できます。</span><span class="sxs-lookup"><span data-stu-id="69e25-120">You can select different custodians in the drop-down box, but you can only search for activities for one custodian at a time.</span></span>

    ![保管担当者アクティビティ検索ページ](../media/AeDCustodianActivities1.png)
   
4. <span data-ttu-id="69e25-122">次の検索条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="69e25-122">Configure the following search criteria:</span></span>
      
   <span data-ttu-id="69e25-123">a.</span><span class="sxs-lookup"><span data-stu-id="69e25-123">a.</span></span> <span data-ttu-id="69e25-124">**アクティビティ**-検索可能なアクティビティを表示するには、ドロップダウンリストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="69e25-124">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="69e25-125">検索を実行すると、選択したアクティビティの監査レコードのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-125">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="69e25-126">[**すべてのアクティビティの結果を表示する]** を選択すると、他の検索条件に一致する保管担当者によって実行されたすべてのアクティビティの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-126">Selecting **Show results for all activities** will display results for all activities performed by the custodian that match the other search criteria.</span></span>

      ![アクティビティの一覧](../media/CustodianActivityAudit.PNG)
      
      <span data-ttu-id="69e25-128">b.</span><span class="sxs-lookup"><span data-stu-id="69e25-128">b.</span></span> <span data-ttu-id="69e25-129">**開始日と終了日**-その期間内に発生したイベントを表示する日付と時刻の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="69e25-129">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="69e25-130">既定では、過去7日間が選択されています。</span><span class="sxs-lookup"><span data-stu-id="69e25-130">The last seven days are selected by default.</span></span> <span data-ttu-id="69e25-131">日付と時刻は、世界協定時刻 (UTC) 形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-131">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="69e25-132">指定できる最大日付範囲は1年です。</span><span class="sxs-lookup"><span data-stu-id="69e25-132">The maximum date range that you can specify is one year.</span></span>
      
      <span data-ttu-id="69e25-133">c.</span><span class="sxs-lookup"><span data-stu-id="69e25-133">c.</span></span> <span data-ttu-id="69e25-134">**保管担当者**このボックスをクリックしてから、検索結果を表示する特定の保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="69e25-134">**Custodians** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="69e25-135">このボックスで選択したユーザーが実行した選択されたアクティビティの監査レコードは、結果の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-135">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
      
   5. <span data-ttu-id="69e25-136">[追加] アイコン</span><span class="sxs-lookup"><span data-stu-id="69e25-136">Click</span></span>   ![[検索] ボタン](../media/SearchButton.PNG)  <span data-ttu-id="69e25-138">を使用して、検索条件を使用して検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="69e25-138">to run the search using your search criteria.</span></span> <span data-ttu-id="69e25-139">検索結果が読み込まれ、しばらくすると、保管担当者アクティビティ検索ページの [結果] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-139">The search results are loaded, and after a few moments they are displayed under Results on the Custodian Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="69e25-140">手順 2: 監査ログの検索結果を表示する</span><span class="sxs-lookup"><span data-stu-id="69e25-140">Step 2: View the audit log search results</span></span>

<span data-ttu-id="69e25-141">監査ログ検索の結果は、保管担当者監査ログページの [結果] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-141">The results of an audit log search are displayed under Results on the Custodian Audit log page.</span></span> <span data-ttu-id="69e25-142">最大 5000 (最新) イベントは、150イベントの増分で表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-142">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="69e25-143">その他のイベントを表示するには、結果ウィンドウのスクロールバーを使用するか、Shift + End キーを押して次の150イベントを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="69e25-143">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="69e25-144">検索結果には、検索によって返された各イベントに関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="69e25-144">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="69e25-145">**日付**: イベントが発生した日付と時刻 (UTC 形式)。</span><span class="sxs-lookup"><span data-stu-id="69e25-145">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="69e25-146">**Ip アドレス**: アクティビティのログが記録されたときに使用されたデバイスの ip アドレス。</span><span class="sxs-lookup"><span data-stu-id="69e25-146">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="69e25-147">IP アドレスは、IPv4 または IPv6 アドレスの形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-147">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="69e25-148">**ユーザー**: イベントをトリガーしたアクションを実行したユーザー (またはサービスアカウント)。</span><span class="sxs-lookup"><span data-stu-id="69e25-148">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="69e25-149">**アクティビティ**: ユーザーによって実行されたアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="69e25-149">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="69e25-150">この値は、[アクティビティ] ドロップダウンリストで選択したアクティビティに対応します。</span><span class="sxs-lookup"><span data-stu-id="69e25-150">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="69e25-151">Exchange 管理者監査ログからのイベントの場合、この列の値は Exchange コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="69e25-151">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="69e25-152">**Item**: 対応するアクティビティの結果として作成または変更されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="69e25-152">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="69e25-153">たとえば、表示または変更されたファイルや更新されたユーザーアカウントなどです。</span><span class="sxs-lookup"><span data-stu-id="69e25-153">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="69e25-154">この列には、すべてのアクティビティの値が含まれているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="69e25-154">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="69e25-155">**詳細**: アクティビティに関する追加の詳細情報。</span><span class="sxs-lookup"><span data-stu-id="69e25-155">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="69e25-156">この場合も、すべてのアクティビティに値が設定されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="69e25-156">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="69e25-157">手順 3: 検索結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="69e25-157">Step 3: Filter the search results</span></span>

<span data-ttu-id="69e25-158">並べ替えに加えて、監査ログの検索結果にフィルターを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="69e25-158">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="69e25-159">これは、特定のユーザーまたはアクティビティの結果をすばやくフィルター処理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="69e25-159">This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="69e25-160">結果をフィルター処理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="69e25-160">To filter the results:</span></span>

 1. <span data-ttu-id="69e25-161">監査ログの検索を作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="69e25-161">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="69e25-162">結果が表示されたら、[**結果をフィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69e25-162">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="69e25-163">各列見出しの下にキーワード ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-163">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="69e25-p115">フィルター処理の対象となる列の列見出しの下に表示されたボックスのいずれかをクリックして語句を入力します。検索結果が動的に調整され、フィルターに一致するイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-p115">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on. The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="69e25-166">フィルターをクリアするには、フィルター ボックスの [**X**] をクリックするか、[**フィルターの非表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69e25-166">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="69e25-167">検索結果をファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="69e25-167">Export the search results to a file</span></span>

<span data-ttu-id="69e25-p116">監査ログの検索結果をローカル コンピューター上のコンマ区切り値 (CSV) ファイルにエクスポートできます。このファイルを Microsoft Excel で開いて、検索、並べ替え、フィルター処理、複数値セルを含む単一列の複数列への分割などの機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="69e25-p116">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer. You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="69e25-170">監査ログの検索を実行して、目的の結果が得られるまで検索条件を変更します。</span><span class="sxs-lookup"><span data-stu-id="69e25-170">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="69e25-171">[結果のエクスポート] をクリックして、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="69e25-171">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="69e25-172">**読み込まれた結果の保存:**[**保管担当者監査ログの検索**] ページの [**結果**] の下に表示されるエントリのみをエクスポートするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="69e25-172">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **Custodian Audit log search** page.</span></span> <span data-ttu-id="69e25-173">ダウンロードされる CSV ファイルには、ページに表示されるのと同じ列 (およびデータ) (Date、User、Activity、Item、および Details) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="69e25-173">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="69e25-174">CSV ファイルには、監査ログエントリからの詳細情報が含まれている追加の列が含まれています (「 **more**」というタイトルが付いています)。</span><span class="sxs-lookup"><span data-stu-id="69e25-174">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="69e25-175">[監査ログの検索] ページでは、同じ結果をエクスポート (および表示可能) するので、最大5000エントリがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="69e25-175">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="69e25-176">**すべての結果をダウンロードします。** このオプションを選択すると、検索条件を満たす Office 365 監査ログからすべてのエントリがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="69e25-176">**Download all results:** Choose this option to export all entries from the Office 365 audit log that meet the search criteria.</span></span> <span data-ttu-id="69e25-177">検索結果のサイズが大きい場合は、このオプションを選択すると、**保管担当者監査ログ**の検索ページに表示される5000結果に加えて、監査ログからすべてのエントリがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="69e25-177">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **Custodian Audit log** search page.</span></span> <span data-ttu-id="69e25-178">このオプションでは、監査ログから CSV ファイルに生データをダウンロードし、AuditData という名前の列に監査ログエントリからの追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="69e25-178">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="69e25-179">このエクスポートオプションを選択すると、[その他] オプションを選択した場合に、ダウンロードするファイルのサイズが非常に大きくなる可能性があるので、このオプションを選択すると、ファイルのダウンロードに長い時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="69e25-179">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="69e25-p119">1 回の監査ログの検索で、最大 50,000 件のエントリを CSV ファイルにダウンロードできます。50,000 件のエントリが CSV ファイルにダウンロードされた場合、検索条件に一致したエントリが 50,000 件を超える可能性があります。この制限を超えてエクスポートするには、日付範囲を使用して監査ログ エントリの件数を削減してみてください。50,000 件を超えるエントリをエクスポートするには、日付範囲を狭めて検索を複数回実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="69e25-p119">You can download a maximum of 50,000 entries to a CSV file from a single audit log search. If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria. To export more than this limit, try using a date range to reduce the number of audit log entries. You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="69e25-184">エクスポートオプションを選択すると、CSV ファイルを開くか、[ダウンロード] フォルダーに保存するか、または特定のフォルダーに保存するかを確認するメッセージがウィンドウの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e25-184">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="69e25-185">監査ログの検索結果の表示、フィルター処理、またはエクスポートの詳細については、「 [Security _AMP_ コンプライアンスセンターでの監査ログの検索](../search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e25-185">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Security & Compliance Center](../search-the-audit-log-in-security-and-compliance.md).</span></span>
