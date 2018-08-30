---
title: コンテンツの検索では、Office 365 の ID のリストを CSV ファイルを準備します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: Results.csv または Items.csv のインデックスを持たないファイルから既存のコンテンツの検索を使用すると、特定の電子メール メッセージを表すオブジェクト ID] ボックスの一覧の検索を作成できます。ID] ボックスの一覧の検索は通常、部分的にインデックス付けされたメールボックス アイテムの取得に使用されます。
ms.openlocfilehash: 28e4a66e5c9be1817881004b1e4b3a3e6d4bfdb9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532544"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a><span data-ttu-id="5721f-104">コンテンツの検索では、Office 365 の ID のリストを CSV ファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="5721f-104">Prepare a CSV file for an ID list Content Search in Office 365</span></span>

<span data-ttu-id="5721f-p102">特定のメールボックスの電子メール メッセージおよびその他のメールボックス アイテムを Exchange Id のリストを使用して検索することができます。(正式には対象の検索と呼ばれる)、ID] ボックスの一覧の検索を作成するには、コンマ区切り値 (CSV) ファイルを検索する特定のメールボックスのアイテムを識別するを送信します。この CSV ファイルには、 **Results.csv**ファイルまたはコンテンツの検索結果をエクスポートするか、コンテンツ検索のレポートから、既存のコンテンツの検索をエクスポートするときに含まれている**インデックス付けされない Items.csv**ファイルを使用します。特定のアイテムを検索して、新しい ID] ボックスの一覧の検索を作成し、CSV ファイルを送信を示すためにこれらのファイルのいずれかを編集します。</span><span class="sxs-lookup"><span data-stu-id="5721f-p102">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs. To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for. For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search. Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span> 
  
<span data-ttu-id="5721f-109">ID のリストの検索を作成するプロセスの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5721f-109">Here's a quick overview of the process for creating an ID list search.</span></span>
  
1. <span data-ttu-id="5721f-110">作成し、セキュリティの新しいまたはガイドのコンテンツの検索を実行する&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="5721f-110">Create and run a new or guided Content Search in the Security &amp; Compliance Center.</span></span>
    
2. <span data-ttu-id="5721f-p103">コンテンツの検索結果をエクスポートするか、コンテンツの検索レポートをエクスポートします。詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5721f-p103">Export the content search results or export the content search report. For more information, see:</span></span>
    
    - [<span data-ttu-id="5721f-113">Office 365 のセキュリティ コンテンツの検索結果をエクスポートする&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="5721f-113">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
    - [<span data-ttu-id="5721f-114">コンテンツ検索のレポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5721f-114">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
3. <span data-ttu-id="5721f-p104">**Results.csv**ファイルまたは**インデックスを持たない Items.csv**を編集し、[ID] ボックスの一覧の検索条件に含める特定のメールボックスのアイテムを識別します。ID] ボックスの一覧の検索の CSV ファイルを準備するため[の手順](#prepare-the-csv-file-for-an-id-list-search)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5721f-p104">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search. See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span> 
    
4. <span data-ttu-id="5721f-p105">新しい ID のリストを作成 ([手順](#create-an-id-list-search)を参照してください) を検索し、準備した CSV ファイルを送信します。作成される検索クエリのみが検索対象項目は CSV ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5721f-p105">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared. The search query that's created will only search for the items selected in the CSV file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5721f-p106">ID] ボックスの一覧の検索は、メールボックスのアイテムにのみサポートされます。SharePoint を検索することはできませんし、OneDrive のドキュメント ID の検索を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="5721f-p106">ID list searches are only supported for mailbox items. You can't search for SharePoint and OneDrive documents in an ID list search.</span></span> 
  
 <span data-ttu-id="5721f-p107">**な ID] ボックスの一覧の検索を作成する理由ですか?** ID] ボックスの一覧検索を使って検索するアイテムが、 **Results.csv**または**Items.csv のインデックスを持たない**ファイル内のメタデータに基づいて、電子的証拠開示要求への応答がある場合を決定することがされていない場合は、プレビュー、および、その項目があるかどうかをエクスポートし、調査をしている場合に応答します。ID] ボックスの一覧の検索は通常、特定のインデックスの項目のセットを検索して使用します。</span><span class="sxs-lookup"><span data-stu-id="5721f-p107">**Why create an ID list search?** If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating. ID list searches are typically used to search for and return a specific set of unindexed items.</span></span> 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="5721f-124">ID] ボックスの一覧の検索の CSV ファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="5721f-124">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="5721f-p108">検索結果やコンテンツの検索では、レポートをエクスポートした後は、ID] ボックスの一覧の検索の CSV ファイルを準備するのには次の手順を行うことができます。この CSV ファイルは、[ID] ボックスの一覧の検索のすべての項目を識別します。</span><span class="sxs-lookup"><span data-stu-id="5721f-p108">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search. This CSV file will identify every item in the ID list search.</span></span>
  
<span data-ttu-id="5721f-p109">SharePoint サイトおよび OneDrive のアカウントを含む検索結果から CSV ファイルを使用することができますが、ID] ボックスの一覧の検索のメールボックスのアイテム*のみ*を選択することに注意してください。SharePoint または OneDrive でドキュメントを選択した場合は、CSV ファイルで ID のリストの検索を作成するときに検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="5721f-p109">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search. If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span> 
  
1. <span data-ttu-id="5721f-129">**Results.csv**または**Items.csv のインデックスを持たない**ファイルを Excel で開きます。</span><span class="sxs-lookup"><span data-stu-id="5721f-129">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span> 
    
2. <span data-ttu-id="5721f-p110">新しい列を挿入し、名前を**選択しています**。列を挿入する位置は関係ありません。利便性のため、最初の列の左側に挿入することを検討します。</span><span class="sxs-lookup"><span data-stu-id="5721f-p110">Insert a new column and name it **Selected**. It doesn't matter where you insert the column. For convenience, consider inserting it to the left of the first column.</span></span>
    
3. <span data-ttu-id="5721f-p111">**選択済**] 列で、 **[はい]** を検索する項目に対応するセルに入力します。検索するすべての項目に対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5721f-p111">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for. Repeat this step for every item that you want to search for.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="5721f-p112">Excel で CSV ファイルを開くと、**汎用的な****ドキュメント ID**列のデータ形式が変更されます。これは、結果、科学的表記法で、アイテムのドキュメント ID を表示します。たとえば、「4.81037E + 11」として「481037338205」の ID が表示されるドキュメントがあるドキュメント ID の正しい形式を復元するのには**番号**を**文書の ID**列のデータ形式を変更するのには次の手順を実行するにはしないこれを行う場合、CSV ファイルを使用する ID] ボックスの一覧の検索は失敗します。</span><span class="sxs-lookup"><span data-stu-id="5721f-p112">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**. This results in displaying the document ID for an item in scientific notation. For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID. If you don't do this, the ID list search that uses the CSV file will fail.</span></span> 
  
4. <span data-ttu-id="5721f-139">全体の**ドキュメントの ID**列を右クリックし、**セルの書式設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5721f-139">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>
    
5. <span data-ttu-id="5721f-140">[**分類**] ボックスで、**番号**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5721f-140">In the **Category** box, click **Number**.</span></span>
    
6. <span data-ttu-id="5721f-p113">小数点以下の桁数を**0**に変更し、変更内容を保存するのには **[ok]** をクリックします。番号をドキュメントの ID 列の値が変更されたことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5721f-p113">Change the number of decimal places to **0**, and then click **OK** to save your changes. Notice that the values in the Document ID column are changed to numbers.</span></span> 
    
    <span data-ttu-id="5721f-143">例をここでは、CSV ファイルの ID] ボックスの一覧のコンテンツの検索に送信する準備が整っています。</span><span class="sxs-lookup"><span data-stu-id="5721f-143">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>
    
    ![コンテンツ検索の対象となる CSV ファイルの例](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. <span data-ttu-id="5721f-p114">CSV ファイルを保存または**名前を付けて**保存するを使用して別のファイル名を持つファイルです。どちらの場合も、必ず CSV 形式でファイルを保存してください。</span><span class="sxs-lookup"><span data-stu-id="5721f-p114">Save the CSV file or use **Save As** to the save the file with different file name. In both cases, be sure to save the file with the CSV format.</span></span> 
  
## <a name="create-an-id-list-search"></a><span data-ttu-id="5721f-147">ID のリストの検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="5721f-147">Create an ID list search</span></span>

<span data-ttu-id="5721f-148">次の手順では、新規の ID のリスト コンテンツの検索を作成し、前の手順で準備した CSV ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="5721f-148">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5721f-p115">作成します ID] ボックスの一覧検索しないコンテンツの検索の結果またはレポートをエクスポートした後に 2 つ以上の日。検索結果、または 2 日以上前のエクスポート場所を報告する必要があります、検索結果または更新された CSV ファイルを生成するレポート再エクスポートします。更新された CSV ファイルのいずれかを準備し、ID] ボックスの一覧の検索の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5721f-p115">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search. If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files. Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span> 
  
1. <span data-ttu-id="5721f-152">セキュリティ&amp;コンプライアンス センター] に移動**検索&amp;調査** \> **コンテンツの検索**。</span><span class="sxs-lookup"><span data-stu-id="5721f-152">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**.</span></span>
    
2. <span data-ttu-id="5721f-153">[**検索**] ページで、矢印をクリックして次に![追加アイコン](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新しい検索** **ID] ボックスの一覧での検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5721f-153">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>
    
    ![新しい検索ドロップダウン ・ リストから ID] ボックスの一覧での検索] をクリックします。](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. <span data-ttu-id="5721f-155">**ID] ボックスの一覧で検索**のフライアウトで、[名前を検索 (および必要に応じて説明する)**参照**] をクリックして、前の手順で準備した CSV ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5721f-155">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span> 
    
    <span data-ttu-id="5721f-p116">Office 365 では、CSV ファイルを検証しようとしています。エラー メッセージが表示されます、検証が失敗した場合、検証エラーのトラブルシューティングに役立ちそうにします。CSV ファイルには ID のリストの検索を作成するのには正常に検証します。</span><span class="sxs-lookup"><span data-stu-id="5721f-p116">Office 365 attempts to validate the CSV file. If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors. The CSV file has to be successfully validated to create an ID list search.</span></span>
    
4. <span data-ttu-id="5721f-159">後、CSV ファイルの検証が成功し、[ID] ボックスの一覧の検索を作成する**検索**します。</span><span class="sxs-lookup"><span data-stu-id="5721f-159">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span> 
    
    <span data-ttu-id="5721f-160">ここでは、予想される検索結果と、ID] ボックスの一覧の検索のために生成されるクエリの例です。</span><span class="sxs-lookup"><span data-stu-id="5721f-160">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>
    
    ![詳細ペインで、対象となるコンテンツの検索の検索クエリ](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    <span data-ttu-id="5721f-162">ID 検索の統計情報に表示される推定のアイテム数が CSV ファイルで選択した項目の数に一致する必要があります注意してください。</span><span class="sxs-lookup"><span data-stu-id="5721f-162">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>
    
5. <span data-ttu-id="5721f-163">プレビューまたは [ID] ボックスの一覧の検索によって返されるアイテムをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5721f-163">Preview or export the items returned by the ID list search.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5721f-p117">ID のリストの検索を作成した後、メールボックスを移動すると、検索のクエリは、指定した項目を返しません。メールボックスを移動すると、メールボックス アイテムに対する**DocumentId**プロパティが変更されたためにです。めったにメールボックスを移動するは、ID の一覧の検索を作成した後、コンテンツ検索の新規作成 (または既存のコンテンツの検索の検索結果を更新する) 必要があり、エクスポート、検索結果またはレポートに使用できる更新済みの CSV ファイルを生成します 新しい ID] ボックスの一覧の検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="5721f-p117">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items. That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved. In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span> 
