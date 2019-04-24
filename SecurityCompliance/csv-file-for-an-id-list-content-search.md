---
title: Office 365 で ID リストコンテンツ検索用の CSV ファイルを準備する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: 特定の電子メールメッセージを返す ID リスト検索を作成するには、既存のコンテンツ検索から .csv ファイルまたはインデックスを作成しない .csv ファイルを使用します。 通常、ID リスト検索は、部分的にインデックスが作成されたメールボックスアイテムを返すために使用されます。
ms.openlocfilehash: fc26f8dab11f1121deb11dd93b2cd0c70a1d629c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265460"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a><span data-ttu-id="3a24f-104">Office 365 で ID リストコンテンツ検索用の CSV ファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="3a24f-104">Prepare a CSV file for an ID list Content Search in Office 365</span></span>

<span data-ttu-id="3a24f-105">Exchange id の一覧を使用して、特定のメールボックスの電子メールメッセージやその他のメールボックスアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="3a24f-105">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="3a24f-106">ID リスト検索 (正式には対象化検索と呼ばれていました) を作成するには、検索する特定のメールボックスアイテムを識別するコンマ区切り値 (CSV) ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-106">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="3a24f-107">この csv ファイルの場合は、コンテンツ検索の結果をエクスポートするとき、または既存のコンテンツ検索からコンテンツ検索レポートをエクスポートするときに含まれる、**結果の .csv**ファイルまたはインデックスのない**アイテム .csv**ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-107">For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search.</span></span> <span data-ttu-id="3a24f-108">次に、これらのファイルの1つを編集して、検索する特定のアイテムを指定し、新しい ID リスト検索を作成して、CSV ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-108">Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span> 
  
<span data-ttu-id="3a24f-109">ID リスト検索を作成するプロセスの簡単な概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-109">Here's a quick overview of the process for creating an ID list search.</span></span>
  
1. <span data-ttu-id="3a24f-110">セキュリティ & コンプライアンスセンターで、新規またはガイド付きコンテンツ検索を作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-110">Create and run a new or guided Content Search in the Security & Compliance Center.</span></span>
    
2. <span data-ttu-id="3a24f-111">コンテンツ検索の結果をエクスポートするか、コンテンツ検索レポートをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3a24f-111">Export the content search results or export the content search report.</span></span> <span data-ttu-id="3a24f-112">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a24f-112">For more information, see:</span></span>
    
    - [<span data-ttu-id="3a24f-113">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="3a24f-113">Export Content Search results</span></span>](export-search-results.md)
    
    - [<span data-ttu-id="3a24f-114">コンテンツ検索のレポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="3a24f-114">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
3. <span data-ttu-id="3a24f-115">結果の **.csv**ファイルまたはインデックスのない**アイテム**を編集し、ID リスト検索に含める特定のメールボックスアイテムを識別します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-115">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search.</span></span> <span data-ttu-id="3a24f-116">ID リスト検索用の CSV ファイルを準備する[方法](#prepare-the-csv-file-for-an-id-list-search)については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a24f-116">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span> 
    
4. <span data-ttu-id="3a24f-117">新しい ID リスト検索を作成し ([指示](#create-an-id-list-search)を参照)、準備した CSV ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-117">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="3a24f-118">作成された検索クエリは、CSV ファイルで選択されたアイテムのみを検索します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-118">The search query that's created will only search for the items selected in the CSV file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3a24f-119">ID リストの検索は、メールボックスアイテムに対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3a24f-119">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="3a24f-120">ID リスト検索で SharePoint および OneDrive のドキュメントを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a24f-120">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span> 
  
 <span data-ttu-id="3a24f-121">**ID リスト検索を作成する理由**</span><span class="sxs-lookup"><span data-stu-id="3a24f-121">**Why create an ID list search?**</span></span> <span data-ttu-id="3a24f-122">アイテムが、**結果 .csv**ファイルまたはインデックスのない**アイテム .csv**ファイルのメタデータに基づいて電子情報開示要求に応答しているかどうかを判断できない場合は、ID リスト検索を使用して、そのアイテムを検索、プレビュー、エクスポートし、調査中のケースに応答します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-122">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="3a24f-123">通常、ID リスト検索は、インデックスが設定されていないアイテムの特定のセットを検索して取得するために使用します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-123">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span> 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="3a24f-124">ID リスト検索用の CSV ファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="3a24f-124">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="3a24f-125">コンテンツ検索の検索結果またはレポートをエクスポートした後、次の手順を実行して、ID リスト検索用の CSV ファイルを準備できます。</span><span class="sxs-lookup"><span data-stu-id="3a24f-125">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="3a24f-126">この CSV ファイルは、ID リスト検索のすべてのアイテムを識別します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-126">This CSV file will identify every item in the ID list search.</span></span>
  
<span data-ttu-id="3a24f-127">SharePoint サイトと OneDrive アカウントを含む検索では、CSV ファイルを使用できることに注意してくださいが、ID 一覧検索のメールボックスアイテム*のみ*を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a24f-127">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search.</span></span> <span data-ttu-id="3a24f-128">SharePoint または OneDrive でドキュメントを選択すると、ID リストの検索を作成するときに、CSV ファイルが検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-128">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span> 
  
1. <span data-ttu-id="3a24f-129">結果の **.csv**ファイルまたは**インデックス**のない .csv ファイルを Excel で開きます。</span><span class="sxs-lookup"><span data-stu-id="3a24f-129">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span> 
    
2. <span data-ttu-id="3a24f-130">新しい列を挿入し、**選択した**名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-130">Insert a new column and name it **Selected**.</span></span> <span data-ttu-id="3a24f-131">列の挿入場所は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="3a24f-131">It doesn't matter where you insert the column.</span></span> <span data-ttu-id="3a24f-132">便宜上、最初の列の左側に挿入することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a24f-132">For convenience, consider inserting it to the left of the first column.</span></span>
    
3. <span data-ttu-id="3a24f-133">[**選択**した列] で、検索するアイテムに対応するセルに **「Yes** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-133">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="3a24f-134">検索するすべてのアイテムについて、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-134">Repeat this step for every item that you want to search for.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3a24f-135">Excel で CSV ファイルを開くと、**ドキュメント ID**列のデータ形式が**General**に変更されます。</span><span class="sxs-lookup"><span data-stu-id="3a24f-135">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**.</span></span> <span data-ttu-id="3a24f-136">この結果、アイテムのドキュメント ID が指数表記で表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a24f-136">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="3a24f-137">たとえば、"481037338205" のドキュメント id が "4.81037 e + 11" と表示されている場合は、次の手順を実行してドキュメント id \*\*\*\* 列のデータ形式を**Number**に変更し、ドキュメント id の正しい形式を復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a24f-137">For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="3a24f-138">この操作を行わない場合、CSV ファイルを使用する ID リスト検索は失敗します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-138">If you don't do this, the ID list search that uses the CSV file will fail.</span></span> 
  
4. <span data-ttu-id="3a24f-139">**ドキュメント ID**列全体を右クリックして、[**セルの書式設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-139">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>
    
5. <span data-ttu-id="3a24f-140">[**カテゴリ**] ボックスで、[**数値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a24f-140">In the **Category** box, click **Number**.</span></span>
    
6. <span data-ttu-id="3a24f-141">小数点以下の桁数を**0**に変更し、[ **OK** ] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-141">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="3a24f-142">[ドキュメント ID] 列の値が数値に変更されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3a24f-142">Notice that the values in the Document ID column are changed to numbers.</span></span> 
    
    <span data-ttu-id="3a24f-143">次に、ID リストコンテンツ検索用に送信できる CSV ファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-143">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>
    
    ![対象コンテンツ検索用の CSV ファイルの例](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. <span data-ttu-id="3a24f-145">CSV ファイルを保存するか、[名前を付け**て保存**するファイルを別のファイル名で保存します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-145">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="3a24f-146">どちらの場合も、必ず CSV 形式でファイルを保存してください。</span><span class="sxs-lookup"><span data-stu-id="3a24f-146">In both cases, be sure to save the file with the CSV format.</span></span> 
  
## <a name="create-an-id-list-search"></a><span data-ttu-id="3a24f-147">ID リスト検索を作成する</span><span class="sxs-lookup"><span data-stu-id="3a24f-147">Create an ID list search</span></span>

<span data-ttu-id="3a24f-148">次の手順では、新しい ID リストコンテンツ検索を作成し、前の手順で準備した CSV ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-148">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3a24f-149">コンテンツ検索から結果またはレポートをエクスポートした後は、ID リスト検索を2日以内に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a24f-149">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search.</span></span> <span data-ttu-id="3a24f-150">2日以上前にエクスポートした検索結果またはレポートの場合は、検索結果またはレポートを再エクスポートして、更新された CSV ファイルを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a24f-150">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="3a24f-151">その後、更新された CSV ファイルのいずれかを準備し、それを使用して ID リスト検索を作成できます。</span><span class="sxs-lookup"><span data-stu-id="3a24f-151">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span> 
  
1. <span data-ttu-id="3a24f-152">セキュリティ & コンプライアンスセンターで、[**検索** \> **コンテンツの検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-152">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>
    
2. <span data-ttu-id="3a24f-153">[**検索**] ページで、[追加] アイコン![](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) [**新しい検索**] の横にある矢印をクリックし、[ **ID リストで検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a24f-153">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>
    
    ![[新しい検索] ドロップダウンリストから [ID リストで検索] をクリックします。](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. <span data-ttu-id="3a24f-155">[ **ID リストによる検索**] ポップアップで、検索に名前を指定 (オプションで説明します) し、[**参照**] をクリックして、前の手順で準備した CSV ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-155">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span> 
    
    <span data-ttu-id="3a24f-156">Office 365 は、CSV ファイルの検証を試みます。</span><span class="sxs-lookup"><span data-stu-id="3a24f-156">Office 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="3a24f-157">検証が失敗した場合は、検証エラーのトラブルシューティングに役立つ可能性があるエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a24f-157">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="3a24f-158">CSV ファイルは、ID 一覧検索を作成するために、正常に検証される必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a24f-158">The CSV file has to be successfully validated to create an ID list search.</span></span>
    
4. <span data-ttu-id="3a24f-159">CSV ファイルが正常に検証されたら、[**検索**] をクリックして ID リスト検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-159">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span> 
    
    <span data-ttu-id="3a24f-160">ここでは、推定検索結果の例と、ID リスト検索用に生成されたクエリを示します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-160">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>
    
    ![詳細ウィンドウで対象コンテンツ検索の検索クエリを実行する](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    <span data-ttu-id="3a24f-162">ID 検索の統計に表示される推定アイテム数は、CSV ファイルで選択したアイテムの数と一致する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3a24f-162">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>
    
5. <span data-ttu-id="3a24f-163">ID リスト検索によって返されるアイテムをプレビューまたはエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3a24f-163">Preview or export the items returned by the ID list search.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3a24f-164">ID リスト検索を作成した後にメールボックスを移動しても、検索のクエリでは指定されたアイテムは返されません。</span><span class="sxs-lookup"><span data-stu-id="3a24f-164">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="3a24f-165">メールボックスの移動時に、メールボックスアイテムの**DocumentId**プロパティが変更されるためです。</span><span class="sxs-lookup"><span data-stu-id="3a24f-165">That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved.</span></span> <span data-ttu-id="3a24f-166">ID リスト検索を作成した後にメールボックスを移動した場合、まれに、新しいコンテンツ検索を作成する (または既存のコンテンツ検索の検索結果を更新する) 必要があります。その後、検索結果またはレポートをエクスポートして、更新された CSV ファイルを生成することができます。 新しい ID リスト検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="3a24f-166">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span> 
