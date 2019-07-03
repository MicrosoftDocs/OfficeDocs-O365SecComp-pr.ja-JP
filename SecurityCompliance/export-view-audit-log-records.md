---
title: 監査ログレコードをエクスポート、構成、および表示する
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: Office 365 監査ログ検索の結果をエクスポートして CSV ファイルにダウンロードした後、Excel の Power Query エディターの JSON 変換機能を使用して、AuditData 列の JSON オブジェクトの各プロパティをそれぞれの列に分割できます。 これは、探している特定の監査データをすばやく見つけるのに役立ちます。
ms.openlocfilehash: 7dac373e8f25ead38dddbe2663e521b35b3153ef
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35462930"
---
# <a name="export-configure-and-view-audit-log-records"></a><span data-ttu-id="b9a60-104">監査ログレコードをエクスポート、構成、および表示する</span><span class="sxs-lookup"><span data-stu-id="b9a60-104">Export, configure, and view audit log records</span></span>

<span data-ttu-id="b9a60-105">Office 365 監査ログを検索し、検索結果を CSV ファイルにダウンロードした後、ファイルには、各イベントに関する追加情報を含む**Auditdata**という名前の列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-105">After you search the Office 365 audit log and download the search results to a CSV file, the file contains a column named **AuditData**, which contains additional information about each event.</span></span> <span data-ttu-id="b9a60-106">この列のデータは、JSON オブジェクトとして書式設定されています。これには、*プロパティと値*のペアとして構成され、コンマで区切られた複数のプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9a60-106">The data in this column is formatted as a JSON object, which contains multiple properties that are configured as *property:value* pairs separated by commas.</span></span> <span data-ttu-id="b9a60-107">Excel の Power Query エディターで JSON 変換機能を使用して、 **Auditdata**列の json オブジェクトの各プロパティを複数の列に分割し、各プロパティがそれぞれの列を持つようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-107">You can use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into multiple columns so that each property has its own column.</span></span> <span data-ttu-id="b9a60-108">これにより、これらのプロパティの1つ以上に対して並べ替えとフィルター処理を行うことができます。これにより、探している特定の監査データをすばやく見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-108">This lets you sort and filter on one or more of these properties, which can help you quickly locate the specific auditing data you're looking for.</span></span>

## <a name="step-1-export-audit-log-search-results"></a><span data-ttu-id="b9a60-109">手順 1: 監査ログの検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b9a60-109">Step 1: Export audit log search results</span></span>

<span data-ttu-id="b9a60-110">最初の手順として、監査ログを検索し、結果をコンマ区切り値 (CSV) ファイルとしてローカルコンピューターにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b9a60-110">The first step is to search the audit log and then export the results in a comma-separated value (CSV) file to your local computer.</span></span>
  
1. <span data-ttu-id="b9a60-111">[監査ログの検索](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log)を実行し、目的の結果が得られるまで、必要に応じて検索条件を修正します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-111">Run an [audit log search](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) and revise the search criteria if necessary until you have the desired results.</span></span>
    
2. <span data-ttu-id="b9a60-112">[**結果のエクスポート**] をクリックし、[**すべての結果をダウンロード**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-112">Click **Export results** and select **Download all results**.</span></span> 
    
   ![[すべての結果をダウンロード] をクリックします。](media/ExportAuditSearchResults.png)

   <span data-ttu-id="b9a60-114">このオプションは、手順1で実行した監査ログ検索からすべての監査レコードをエクスポートし、その生データを監査ログから CSV ファイルにダウンロードするために使用します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-114">This option to exports all the audit records from the audit log search you ran in step 1, and downloads the raw data from the audit log to a CSV file.</span></span> 

   <span data-ttu-id="b9a60-115">ウィンドウの下部に、CSV ファイルを開くか保存するかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-115">A message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span> 

3. <span data-ttu-id="b9a60-116">[保存] をクリックし**て名前を付けて保存 >** 、CSV ファイルをローカルコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-116">Click **Save > Save as** and save the CSV file to your local computer.</span></span> <span data-ttu-id="b9a60-117">多くの検索結果をダウンロードするには、しばらく時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="b9a60-117">It takes a while to download many search results.</span></span> <span data-ttu-id="b9a60-118">通常は、すべてのアクティビティまたは広範な日付範囲を検索する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-118">This is typically the case when searching for all activities or a broad date range.</span></span> <span data-ttu-id="b9a60-119">CSV ファイルのダウンロードが完了すると、ウィンドウの下部にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-119">A message at the bottom of the windows is displayed when the CSV file is finished downloading.</span></span>
 
   ![CSV ファイルのダウンロードが完了したときに表示されるメッセージ](media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > <span data-ttu-id="b9a60-121">1つの監査ログ検索から CSV ファイルに最大5万エントリをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-121">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="b9a60-122">5万エントリが CSV ファイルにダウンロードされた場合は、検索条件に一致する5万イベントの数がを超える可能性があると考えられます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-122">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="b9a60-123">この制限を超える値をエクスポートするには、日付範囲を使用して監査ログレコードの数を減らしてみてください。</span><span class="sxs-lookup"><span data-stu-id="b9a60-123">To export more than this limit, try using a date range to reduce the number of audit log records.</span></span> <span data-ttu-id="b9a60-124">5万を超えるエントリをエクスポートするには、短い日付範囲で複数の検索を実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9a60-124">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a><span data-ttu-id="b9a60-125">手順 2: Power Query エディターを使用してエクスポートされた監査ログを書式設定する</span><span class="sxs-lookup"><span data-stu-id="b9a60-125">Step 2: Format the exported audit log using the Power Query Editor</span></span>

<span data-ttu-id="b9a60-126">次の手順では、Excel の Power Query エディターで JSON 変換機能を使用して、 **Auditdata**列の json オブジェクトの各プロパティをそれぞれの列に分割します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-126">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="b9a60-127">次に、列をフィルター処理して、特定のプロパティの値に基づいてレコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-127">Then you filter columns to view records based on the values of specific properties.</span></span> <span data-ttu-id="b9a60-128">これは、探している特定の監査データをすばやく見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-128">This can help you quickly locate the specific auditing data you're looking for.</span></span>

1. <span data-ttu-id="b9a60-129">Excel for Office 365、Excel 2019、または Excel 2016 に対して空のブックを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-129">Open a blank workbook in Excel for Office 365, Excel 2019, or Excel 2016.</span></span>
    
2.  <span data-ttu-id="b9a60-130">[**データ**] タブの [ **Get & Transform Data** ] リボングループで、[ **Text/CSV**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9a60-130">On the **Data** tab, in the **Get & Transform Data** ribbon group, click **From Text/CSV**.</span></span>

    ![[データ] タブの [テキスト/CSV から] をクリックします。](media/JSONTransformOpenCSVFile.png)

3. <span data-ttu-id="b9a60-132">手順1でダウンロードした CSV ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-132">Open the CSV file that you downloaded in Step 1.</span></span>
    
4. <span data-ttu-id="b9a60-133">表示されたウィンドウで、[**データの変換**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9a60-133">In the window that's displayed, click **Transform Data**.</span></span>

   ![[データの変換] をクリックします。](media/JSONOpenPowerQuery.png)

<span data-ttu-id="b9a60-135">CSV ファイルが**クエリエディター**で開かれます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-135">The CSV file is opened in the **Query Editor**.</span></span> <span data-ttu-id="b9a60-136">**CreationDate**、 **UserIds**、 **Operations**、および**auditdata**の4つの列があります。</span><span class="sxs-lookup"><span data-stu-id="b9a60-136">There are four columns: **CreationDate**, **UserIds**, **Operations**, and **AuditData**.</span></span> <span data-ttu-id="b9a60-137">**Auditdata**列は、複数のプロパティを含む JSON オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="b9a60-137">The **AuditData** column is a JSON object that contains multiple properties.</span></span> <span data-ttu-id="b9a60-138">次の手順では、JSON オブジェクトの各プロパティに対して列を作成します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-138">The next step is to create a column for each property in the JSON object.</span></span>
    
5. <span data-ttu-id="b9a60-139">**Auditdata**列のタイトルを右クリックし、[**変換**] をクリックして、[ **JSON**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9a60-139">Right-click the title in the **AuditData** column, click **Transform**, and then click **JSON**.</span></span> 
 
   ![[AuditData] 列を右クリックし、[変換] をクリックして、[JSON] を選択します。](media/JSONTransform.png)

6. <span data-ttu-id="b9a60-141">**Auditdata**列の右上隅で、[展開] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9a60-141">In the upper-right corner of the **AuditData** column, click the expand icon.</span></span>
    
   ![[AuditData] 列で、[expand] アイコンをクリックします。](media/JSONTransformExpandIcon.png)

   <span data-ttu-id="b9a60-143">**Auditdata**列の JSON オブジェクトのプロパティの一部のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-143">A partial list of the properties in the JSON objects in the **AuditData** column is displayed.</span></span>

7. <span data-ttu-id="b9a60-144">[**詳細を読み込む**] をクリックして、[ **auditdata** ] 列の JSON オブジェクトのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-144">Click **Load more** to display all properties in the JSON objects in the **AuditData** column.</span></span>

   ![[詳細を読み込む] をクリックして、JSON オブジェクトのすべてのプロパティを表示します。](media/JSONTransformLoadJSONProperties.png)

   <span data-ttu-id="b9a60-146">含める必要のないプロパティの横にあるチェックボックスの選択を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-146">You can unselect the checkbox next to any property that you don't want to include.</span></span> <span data-ttu-id="b9a60-147">調査に役に立たない列を削除することは、監査ログに表示されるデータの量を減らすための適切な方法です。</span><span class="sxs-lookup"><span data-stu-id="b9a60-147">Eliminating columns that aren't useful for your investigation is a good way to reduce the amount of data displayed in the audit log.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="b9a60-148">前のスクリーンショットに表示されている JSON プロパティは、CSV ファイルの最初の1000行の**Auditdata**列にあるプロパティに基づいています ([**さらに読み込む**] をクリックした後)。</span><span class="sxs-lookup"><span data-stu-id="b9a60-148">The JSON properties displayed in the previous screenshot (after you click **Load more**) are based on the properties found in the **AuditData** column from the first 1,000 rows in the CSV file.</span></span> <span data-ttu-id="b9a60-149">最初の1000行の後のレコードに異なる JSON プロパティがある場合、 **Auditdata**列が複数の列に分割されていると、これらのプロパティ (および対応する列) は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b9a60-149">If there are different JSON properties in records after the first 1,000 rows, these properties (and a corresponding column) won't be included when the **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="b9a60-150">これを防ぐには、監査ログの検索を再実行し、返されるレコード数が少なくなるように検索条件を絞ることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b9a60-150">To help prevent this, consider re-running the audit log search and narrow the search criteria so that fewer records are returned.</span></span> <span data-ttu-id="b9a60-151">もう1つの回避策として、[**操作**] 列のアイテムにフィルターを適用して、[ **auditdata** ] 列で JSON オブジェクトを変換する前に、行数を減らします (上記の手順5を実行する前)。</span><span class="sxs-lookup"><span data-stu-id="b9a60-151">Another workaround is to filter items in the **Operations** column to reduce the number of rows (before you perform step 5 above) before transforming the JSON object in the **AuditData** column.</span></span>

8. <span data-ttu-id="b9a60-152">次のいずれかの操作を実行して、選択されている各 JSON プロパティに対して追加される列のタイトルを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-152">Do one of the following things to format the title of the columns that are added for each JSON property that's selected.</span></span>

    - <span data-ttu-id="b9a60-153">[**元の列名をプレフィックスとして使用**する] チェックボックスをオフにして、JSON プロパティの名前を列名として使用します。たとえば、 **RecordType**または**sourcefilename**のようになります。</span><span class="sxs-lookup"><span data-stu-id="b9a60-153">Unselect the **Use original column name as prefix** checkbox to use the name of the JSON property as the column names; for example, **RecordType** or **SourceFileName**.</span></span>
    
   - <span data-ttu-id="b9a60-154">[**元の列名をプレフィックスとして使用**する] チェックボックスをオンのままにして、auditdata プレフィックスを列名に追加します。たとえば、 **Auditdata**または**auditdata ファイル名**です。</span><span class="sxs-lookup"><span data-stu-id="b9a60-154">Leave the **Use original column name as prefix** checkbox selected to add the AuditData prefix to the column names; for example, **AuditData.RecordType** or **AuditData.SourceFileName**.</span></span>

9. <span data-ttu-id="b9a60-155">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9a60-155">Click **OK**.</span></span>
    
    <span data-ttu-id="b9a60-156">**Auditdata**列は複数の列に分割されます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-156">The **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="b9a60-157">新しい列はそれぞれ、AuditData JSON オブジェクトのプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="b9a60-157">Each new column corresponds to a property in the AuditData JSON object.</span></span> <span data-ttu-id="b9a60-158">列の各行には、プロパティの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9a60-158">Each row in the column contains the value for the property.</span></span> <span data-ttu-id="b9a60-159">プロパティに値が含まれていない場合は、 *null*値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-159">If the property doesn't contain a value, the *null* value is displayed.</span></span> <span data-ttu-id="b9a60-160">Excel では、null 値を持つセルは空になります。</span><span class="sxs-lookup"><span data-stu-id="b9a60-160">In Excel, cells with null values are empty.</span></span>
  
10. <span data-ttu-id="b9a60-161">[**ホーム**] タブで、[**閉じる & Load** ] をクリックして Power Query Editor を閉じ、変換された CSV ファイルを Excel ブックで開きます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-161">On the **Home** tab, click **Close & Load** to close the Power Query Editor and open the transformed CSV file in an Excel workbook.</span></span> 

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a><span data-ttu-id="b9a60-162">監査ログをエクスポートして表示するためのヒント</span><span class="sxs-lookup"><span data-stu-id="b9a60-162">Tips for exporting and viewing the audit log</span></span>

<span data-ttu-id="b9a60-163">ここでは、JSON 変換機能を使用して、 **Auditdata**列を複数の列に分割する前と後の監査ログをエクスポートおよび表示する際のヒントと例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-163">Here are some tips and examples of exporting and viewing the audit log before and after you use the JSON transform feature to split the **AuditData** column into multiple columns.</span></span>

- <span data-ttu-id="b9a60-164">**RecordType**列をフィルター処理して、特定の Office 365 サービスまたは機能領域のレコードのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-164">Filter the **RecordType** column to display only the records from a specific Office 365 service or functional area.</span></span> <span data-ttu-id="b9a60-165">たとえば、SharePoint 共有に関連するイベントを表示するには、[ **14** ] (sharepoint 共有アクティビティによってトリガーされたレコードの列挙値) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-165">For example, to show events related to SharePoint sharing, you would select **14** (the enum value for records triggered by SharePoint sharing activities).</span></span> <span data-ttu-id="b9a60-166">**RecordType**列に表示される列挙値に対応する office 365 サービスの一覧については、「 [office 365 監査ログの詳細なプロパティ](detailed-properties-in-the-office-365-audit-log.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9a60-166">For a list of the Office 365 services that correspond to the enum values displayed in the **RecordType** column, see [Detailed properties in the Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span>

- <span data-ttu-id="b9a60-167">[**操作**] 列をフィルター処理して、特定のアクティビティのレコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-167">Filter the **Operations** column to display the records for specific activities.</span></span> <span data-ttu-id="b9a60-168">セキュリティ & コンプライアンスセンターの監査ログ検索ツールで検索可能なアクティビティに対応するほとんどの操作の一覧については、「 [security & コンプライアンスセンターで監査ログを検索](search-the-audit-log-in-security-and-compliance.md#audited-activities)する」の「監査アクティビティ」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9a60-168">For a list of most operations that correspond to a searchable activity in the audit log search tool in the Security & Compliance Center, see the "Audited activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>

- <span data-ttu-id="b9a60-169">セキュリティ & コンプライアンスセンターで監査ログ検索ツールを使用する代わりに、Exchange Online Powershell で[search-unifiedauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog)コマンドレットを使用して、Office 365 監査ログの検索結果を CSV ファイルにエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-169">Instead of using the audit log search tool in the Security & Compliance Center, you can use the [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) cmdlet in Exchange Online Powershell to export the results of an Office 365 audit log search to a CSV file.</span></span> <span data-ttu-id="b9a60-170">その後、手順2で説明されているのと同じ手順に従って、Power Query エディターを使用して監査ログを書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-170">Then you can follow the same procedure described in Step 2 to format the audit log using the Power Query editor.</span></span> <span data-ttu-id="b9a60-171">PowerShell コマンドレットを使用する場合の利点の1つは、 *RecordType*パラメーターを使用して特定の Office 365 サービスからのイベントを検索できることです。</span><span class="sxs-lookup"><span data-stu-id="b9a60-171">One advantage of using the PowerShell cmdlet is that you can search for events from a specific Office 365 service by using the *RecordType* parameter.</span></span> <span data-ttu-id="b9a60-172">ここでは、PowerShell を使用して監査レコードを CSV ファイルにエクスポートする例をいくつか示します。このため、Power Query editor を使用して、「 **Auditdata** 」列の JSON オブジェクトを変換することができます (手順2を参照)。</span><span class="sxs-lookup"><span data-stu-id="b9a60-172">Here are few examples of using PowerShell to export audit records to a CSV file so you can use the Power Query editor to transform the JSON object in the **AuditData** column as described in Step 2.</span></span>

   <span data-ttu-id="b9a60-173">この例では、次のコマンドを実行して、SharePoint 共有操作に関連するすべてのレコードを返します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-173">In this example, run the following commands to return all records related to SharePoint sharing operations.</span></span> 
   
   ```
   $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
   ```

   ```
   $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
   ```

   - <span data-ttu-id="b9a60-174">検索結果は、次の4つの列 (CreationDate、UserIds、RecordType、AuditData) を含む*Powershellauditlog ログ*という名前の CSV ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-174">The search results are exported to a CSV file named *PowerShellAuditlog* that contains four columns: CreationDate, UserIds, RecordType, AuditData).</span></span>

   - <span data-ttu-id="b9a60-175">*RecordType*パラメーターの値として、レコードの種類の名前または列挙値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-175">You can use the name or enum value for the record type as the value for the *RecordType* parameter.</span></span> <span data-ttu-id="b9a60-176">レコードの種類の名前とそれに対応する列挙値の一覧については、「 [Office 365 Management ACTIVITY API スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)の*AuditLogRecordType*テーブル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9a60-176">For a list of record type names and their corresponding enum values, see the *AuditLogRecordType* table in [Office 365 Management Activity API schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).</span></span>
   
   - <span data-ttu-id="b9a60-177">このパラメーターには、1つの値のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b9a60-177">You can only include a single value for this parameter.</span></span> <span data-ttu-id="b9a60-178">他のレコードの種類の監査レコードを検索するには、2つの前のコマンドを再度実行して、別のレコードの種類を指定し、それらの結果を元の CSV ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-178">To search for audit records for other record types, you have to run the two previous commands again to specify a different record type and append those results to the original CSV file.</span></span> <span data-ttu-id="b9a60-179">たとえば、次の2つのコマンドを実行して、同じ日付範囲の SharePoint ファイルアクティビティを PowerShellAuditlog ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b9a60-179">For example, you would run these two commands to add SharePoint file activities from the same date range to the PowerShellAuditlog.csv file.</span></span>

       ```
      $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
      ```

      ```
      $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
      ```
