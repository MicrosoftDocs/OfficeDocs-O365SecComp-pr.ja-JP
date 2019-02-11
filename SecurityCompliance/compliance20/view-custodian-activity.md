---
title: 管理者監査活動状況の表示
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 34e3fe207cf440c5992cdba7186e919a3968db22
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706148"
---
# <a name="view-custodian-audit-activity"></a><span data-ttu-id="ba610-102">管理者監査活動状況の表示</span><span class="sxs-lookup"><span data-stu-id="ba610-102">View custodian audit activity</span></span>

<span data-ttu-id="ba610-p101">ユーザーが特定のドキュメントを表示またはユーザーのメールボックスからアイテムを削除するかどうかを検索する必要がありますか。セキュリティ & コンプライアンス センターの既存の監査ログ検索ツールとは、高度な電子的証拠開示 (プレビュー) が統合されています。この埋め込まれた経験を使用すると、高度な電子的証拠開示 (プレビュー) の管理者の管理ツールを使用して、簡単にアクセスして通告、ケース内のアクティビティを検索して、調査を容易にします。</span><span class="sxs-lookup"><span data-stu-id="ba610-p101">Need to find if a user viewed a specific document or purged an item from their mailbox? Advanced eDiscovery (Preview) is now integrated with the existing audit log search tool in the Security & Compliance Center. Using this embedded experience, you can use the Advanced eDiscovery (Preview) Custodian Management tool to facilitate your investigation by easily accessing and searching the activity for custodians within your case.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ba610-106">始める前に</span><span class="sxs-lookup"><span data-stu-id="ba610-106">Before you begin</span></span>

<span data-ttu-id="ba610-p102">監査ログの参照、または監査ログの役割を割り当てる Exchange オンライン Office 365 の監査ログを検索する必要があります。既定では、これらの役割は、コンプライアンスの管理と Exchange 管理センターで [アクセス許可] ページで、組織の管理役割グループに割り当てられます。ユーザーに提供するには、高度な電子的証拠開示 (プレビュー) 監査ログは、最小レベルの権限を検索する機能を Exchange オンラインでカスタムの役割グループを作成、監査ログの参照、または監査ログの役割を追加して新しい役割の gr のメンバーとしてユーザーを追加oup。詳細については、Exchange Online のロール グループの管理を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba610-p102">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log. By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center. To give a user the ability to search the Advanced eDiscovery (Preview) audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group. For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba610-p103">セキュリティ & コンプライアンス センターで [アクセス許可] ページで監査ログの参照、または監査ログのロールにユーザーを割り当てる場合、Office 365 の監査ログを検索することはできません。Exchange のオンラインでのアクセス許可を割り当てることがあります。これは、監査ログを検索するために使用する基になるコマンドレットが Exchange Online のコマンドレットであるためです。</span><span class="sxs-lookup"><span data-stu-id="ba610-p103">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the Office 365 audit log. You have to assign the permissions in Exchange Online. This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-create-an-advanced-ediscovery-preview-audit-log-search"></a><span data-ttu-id="ba610-114">手順 1: 監査ログの検索は高度な電子的証拠開示 (プレビュー) を作成します。</span><span class="sxs-lookup"><span data-stu-id="ba610-114">Step 1: Create an Advanced eDiscovery (Preview) audit log search</span></span>

   1. <span data-ttu-id="ba610-115">**セキュリティ & コンプライアンス センター _gt 高度な電子的証拠開示 (プレビュー)** から既存のケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="ba610-115">Select an existing case from the **Security & Compliance Center > Advanced eDiscovery (Preview)**.</span></span>
   
   2. <span data-ttu-id="ba610-116">**通告**」タブに移動し、管理者を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba610-116">Navigate to the **Custodians** tab and select a custodian.</span></span>
   
   3. <span data-ttu-id="ba610-117">保管担当者を選択したら、詳細パネルから**管理者のアクティビティを表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba610-117">Once you have selected a custodian, click **View Custodian Activity** from the details panel.</span></span>
   
   4. <span data-ttu-id="ba610-118">次の検索条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="ba610-118">Configure the following search criteria:</span></span>
      
      <span data-ttu-id="ba610-p104">a.**活動**- を検索することができる活動を表示するドロップダウン リストをクリックします。検索を実行すると、選択したアクティビティの監査レコードのみが表示されます。**すべての活動の結果を表示する**を選択すると、他の検索条件を満たすすべての活動の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba610-p104">a. **Activities** - Click the drop-down list to display the activities that you can search for. After you run the search, only the audit records for the selected activities are displayed. Selecting **Show results for all activities** will display results for all activities that meet the other search criteria.</span></span>
      
      <span data-ttu-id="ba610-p105">b. の**開始日と終了日**には、その期間内に発生したイベントを表示する日付と時刻の範囲を選択します。過去 7 日間は、既定で選択されます。日付と時刻が世界協定時刻 (UTC) 形式で表示されます。最大日付範囲を指定することには、1 年間です。</span><span class="sxs-lookup"><span data-stu-id="ba610-p105">b. **Start date and End date** - Select a date and time range to display the events that occurred within that period. The last seven days are selected by default. The date and time are presented in Coordinated Universal Time (UTC) format. The maximum date range that you can specify is one year.</span></span>
      
      <span data-ttu-id="ba610-p106">結果、c.**通告**のでは、このボックスし、検索を表示するのには特定の管理者を選択] をクリックします。このボックスで選択したユーザーによって実行される、選択したアクティビティの監査レコードは、結果の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba610-p106">c. **Custodians** - Click in this box and then select a specific custodian to display search results for. Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
    
    1. <span data-ttu-id="ba610-p107">検索条件を使用して検索を実行する**検索**をクリックします。検索結果が読み込まれ、管理者のアクティビティの検索ページにしばらく [結果] で表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba610-p107">Click **Search** to run the search using your search criteria. The search results are loaded, and after a few moments they are displayed under Results on the Custodian Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="ba610-133">監査ログの検索結果を表示する手順 2。</span><span class="sxs-lookup"><span data-stu-id="ba610-133">Step 2: View the audit log search results</span></span>

<span data-ttu-id="ba610-p108">監査ログ検索の結果は [結果] で [管理者の監査ログ] ページで表示されます。150 イベント単位では、最大 5,000 (最新) のイベントが表示されます。多くのイベントを表示するには、[結果] ペインでスクロール バーを使用することができます。 またはを押すと、次に 150 のイベントを表示するには、shift キーを押しながら終了。</span><span class="sxs-lookup"><span data-stu-id="ba610-p108">The results of an audit log search are displayed under Results on the Custodian Audit log page. A maximum of 5,000 (newest) events are displayed in increments of 150 events. To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="ba610-137">検索結果には、検索によって返された各イベントに関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba610-137">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="ba610-138">**日付**: 日付と時間 (UTC 形式)、イベントが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ba610-138">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="ba610-p109">**IP アドレス**: アクティビティのログが記録されたときに使用されたデバイスの IP アドレスです。IP アドレスは、IPv4 または IPv6 アドレスの形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba610-p109">**IP address**: The IP address of the device that was used when the activity was logged. The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="ba610-141">**ユーザー**: ユーザー (またはサービス アカウント)、イベントをトリガーするアクションを実行しました。</span><span class="sxs-lookup"><span data-stu-id="ba610-141">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="ba610-p110">**アクティビティ**: ユーザーによって実行されたアクティビティです。この値は、アクティビティのドロップダウン リストで選択したアクティビティに対応します。Exchange 管理者の監査ログからイベントをこの列の値は、Exchange コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="ba610-p110">**Activity**: The activity performed by the user. This value corresponds to the activities that you selected in the Activities drop down list. For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="ba610-p111">**項目**: 作成または対応する活動の結果として変更されたオブジェクト。などの表示または変更されたファイルや更新されたユーザー アカウントです。すべてのアクティビティでは、この列の値があります。</span><span class="sxs-lookup"><span data-stu-id="ba610-p111">**Item**: The object that was created or modified as a result of the corresponding activity. For example, the file that was viewed or modified or the user account that was updated. Not all activities have a value in this column.</span></span>

- <span data-ttu-id="ba610-p112">**詳細**: アクティビティについての詳細です。もう一度、すべてのアクティビティでは、値があります。</span><span class="sxs-lookup"><span data-stu-id="ba610-p112">**Detail**: Additional detail about an activity. Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="ba610-150">手順 3: 検索結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="ba610-150">Step 3: Filter the search results</span></span>

<span data-ttu-id="ba610-p113">並べ替えだけでなく、監査ログの検索の結果を抽出することも。迅速に特定のユーザーまたは活動の結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="ba610-p113">In addition to sorting, you can also filter the results of an audit log search. This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="ba610-153">結果をフィルター処理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ba610-153">To filter the results:</span></span>

 1. <span data-ttu-id="ba610-154">作成し、監査ログの検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="ba610-154">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="ba610-155">結果が表示されたら、[**結果をフィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba610-155">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="ba610-156">各列見出しの下にキーワード ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba610-156">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="ba610-p114">フィルター処理の対象となる列の列見出しの下に表示されたボックスのいずれかをクリックして語句を入力します。検索結果が動的に調整され、フィルターに一致するイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba610-p114">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on. The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="ba610-159">フィルターをクリアするには、フィルター ボックスの [**X**] をクリックするか、[**フィルターの非表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba610-159">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="ba610-160">検索結果をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ba610-160">Export the search results to a file</span></span>

<span data-ttu-id="ba610-p115">監査ログの検索結果をローカル コンピューター上のコンマ区切り値 (CSV) ファイルにエクスポートできます。このファイルを Microsoft Excel で開いて、検索、並べ替え、フィルター処理、複数値セルを含む単一列の複数列への分割などの機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ba610-p115">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer. You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="ba610-163">監査ログの検索を実行して、目的の結果が得られるまで検索条件を変更します。</span><span class="sxs-lookup"><span data-stu-id="ba610-163">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="ba610-164">[結果のエクスポート] をクリックして、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ba610-164">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="ba610-p116">**読み込まれた結果の保存:**[**管理者監査ログの検索**] ページで、[**結果**] で表示されているエントリだけをエクスポートするには、このオプションを選択します。ダウンロードした CSV ファイルには、(日付、ユーザー、アクティビティ、項目、および詳細情報) ページ上の同じ列やデータ) が表示されますが含まれています。詳細については監査ログのエントリを含む CSV ファイルに列追加 (**複数**のタイトルになっている) にはが含まれます。ロードされて (表示) するのと同じ結果をエクスポートするため監査ログ検索ページでは、最大 5,000 のエントリがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="ba610-p116">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **Custodian Audit log search** page. The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details). An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry. Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="ba610-p117">**すべての結果をダウンロード:** 検索条件を満たす Office 365 の監査ログからすべてのエントリをエクスポートするには、このオプションを選択します。検索結果の大規模なセットは、**管理者の監査ログ**の検索ページに表示できる 5,000 の結果だけでなく、監査ログからすべてのエントリをダウンロードするには、このオプションを選択します。このオプションでは、監査ログから生データを CSV ファイルにダウンロードされ、AuditData をという名前の列内の監査ログ エントリからの追加情報が含まれています。ファイルが他のオプションを選択した場合にダウンロードされるものをはるかに超える可能性があるために、このエクスポート オプションを選択した場合、ファイルのダウンロードに長い時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ba610-p117">**Download all results:** Choose this option to export all entries from the Office 365 audit log that meet the search criteria. For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **Custodian Audit log** search page. This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData. It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="ba610-p118">1 回の監査ログの検索で、最大 50,000 件のエントリを CSV ファイルにダウンロードできます。50,000 件のエントリが CSV ファイルにダウンロードされた場合、検索条件に一致したエントリが 50,000 件を超える可能性があります。この制限を超えてエクスポートするには、日付範囲を使用して監査ログ エントリの件数を削減してみてください。50,000 件を超えるエントリをエクスポートするには、日付範囲を狭めて検索を複数回実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ba610-p118">You can download a maximum of 50,000 entries to a CSV file from a single audit log search. If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria. To export more than this limit, try using a date range to reduce the number of audit log entries. You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="ba610-177">エクスポート オプションを選択すると、CSV ファイルを開く、フォルダーに保存して、ダウンロード、または特定のフォルダーに保存するように要求するウィンドウの下部にあるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba610-177">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="ba610-178">表示の詳細については、フィルタ リング、または監査ログの検索結果をエクスポートするには[Office 365 のセキュリティ & コンプライアンス センターでの監査ログの検索](../search-the-audit-log-in-security-and-compliance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba610-178">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Office 365 Security & Compliance Center](../search-the-audit-log-in-security-and-compliance.md).</span></span>