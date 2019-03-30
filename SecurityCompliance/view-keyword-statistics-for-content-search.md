---
title: コンテンツ検索結果のキーワード統計の表示
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: 検索統計機能を使用して、Security & コンプライアンスセンターでの複数のコンテンツ検索の統計の表示と比較を行います。 検索クエリを作成または編集するときにキーワードリストを構成して、各キーワードまたはキーワードフレーズに一致するアイテムの数を示す拡張統計を取得することもできます。
ms.openlocfilehash: 5e4cca18f6a50f2647265f02dab7ab3f20f513fc
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001130"
---
# <a name="view-keyword-statistics-for-content-search-results"></a><span data-ttu-id="7d407-104">コンテンツ検索結果のキーワード統計の表示</span><span class="sxs-lookup"><span data-stu-id="7d407-104">View keyword statistics for Content Search results</span></span>

<span data-ttu-id="7d407-p102">コンテンツ検索を作成して実行した後は、予想される検索結果の統計情報を表示できます。これには、検索結果の概要 (詳細ウィンドウに表示される予想検索結果のサマリーと同様)、アイテムが検索クエリと一致したコンテンツの場所の数などのクエリ統計情報、最も多くのアイテムが一致したコンテンツの場所の名前が含まれます。1 つまたは複数のコンテンツ検索に対して統計情報を表示できます。これにより、複数の検索の結果を簡単に比較して、検索クエリの有効性を判断できます。</span><span class="sxs-lookup"><span data-stu-id="7d407-p102">After you create and run a Content Search, you can view statistics about the estimated search results. This includes a summary of the search results (similar to the summary of the estimated search results displayed in the details pane), the query statistics such as the number of content locations with items that match the search query, and the name of content locations that have the most matching items. You can display statistics for one or more content searches. This lets you to quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span>
  
<span data-ttu-id="7d407-p103">さらに、検索クエリ内の各キーワードに対する統計情報を返すように、新規および既存の検索を構成することができます。これにより、クエリ内の各キーワードの結果の数をすばやく比較したり、複数の検索のキーワード統計を比較したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d407-p103">Additionally, you can configure new and existing searches to return statistics for each keyword in a search query. This lets you compare the number of results for each keyword in a query and to compare the keyword statistics from multiple searches.</span></span>
  
<span data-ttu-id="7d407-p104">また、検索の統計情報とキーワードの統計情報を CSV ファイルにダウンロードできます。これにより、Excel のフィルター機能や並べ替え機能を使用して結果を比較し、検索結果のレポートを準備できます。</span><span class="sxs-lookup"><span data-stu-id="7d407-p104">You can also download the search statistics and keyword statistics to a CSV file. This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-content-searches"></a><span data-ttu-id="7d407-113">コンテンツ検索の統計情報を取得する</span><span class="sxs-lookup"><span data-stu-id="7d407-113">Get statistics for Content Searches</span></span>

<span data-ttu-id="7d407-114">コンテンツ検索の統計情報を表示するには:</span><span class="sxs-lookup"><span data-stu-id="7d407-114">To display statistics for Content Searches:</span></span>
  
1. <span data-ttu-id="7d407-115">セキュリティ & コンプライアンスセンターで、[**検索** \> **コンテンツの検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7d407-115">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>
    
2. <span data-ttu-id="7d407-116">検索の一覧で、検索を 1 つ以上選択して、**[検索の統計]** ![統計の検索ボタン](media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d407-116">In the list of searches, select one or more searches, and then click **Search statistics**![Search Statistics button](media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png).</span></span>
    
    ![複数の検索を選択してから [検索の統計] をクリックする](media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. <span data-ttu-id="7d407-118">**[検索の統計]** ページで、次のリンクのいずれかをクリックして、選択した検索の統計情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="7d407-118">On the **Search statistics** page, click one of the following links to display statistics about the selected searches.</span></span> 
    
    <span data-ttu-id="7d407-119">**概要**</span><span class="sxs-lookup"><span data-stu-id="7d407-119">**Summary**</span></span>
    
    <span data-ttu-id="7d407-p105">このページには、**[コンテンツ検索]** ページの詳細ウィンドウに表示されるものと似た統計情報が表示されます。選択したすべての検索の統計情報が表示されます。このページから選択した検索を再実行し、統計情報を更新できることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="7d407-p105">This page displays statistics similar to the ones displayed in the details pane on the **Content search** page. Statistics for all selected searches are displayed. Note that you can also re-run the selected searches from this page to update the statistics.</span></span> 
    
    ![選択した検索の統計情報のサマリー](media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    <span data-ttu-id="7d407-p106">a. コンテンツ検索の名前。前に説明したように、複数の検索の統計情報を表示して比較できます。</span><span class="sxs-lookup"><span data-stu-id="7d407-p106">a.  The name of the Content Search. As previously stated, you can display and compare statistics for multiple searches.</span></span>
    
    <span data-ttu-id="7d407-p107">b. 検索されたコンテンツの場所の種類。各行には、指定した検索に関するメールボックス、サイト、パブリック フォルダーの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d407-p107">b. The type of content location that was searched. Each row displays statistics for mailboxes, sites, and public folders from the specified search.</span></span>
    
    <span data-ttu-id="7d407-p108">c. 検索クエリに一致したアイテムが含まれるコンテンツの場所の数。メールボックスの場合、この統計情報には、検索クエリに一致するアイテムが含まれるアーカイブ メールボックスの数も含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d407-p108">c. The number of content locations containing items that match the search query. For mailboxes, this statistic also includes the number of archive mailboxes that contain items that match the search query.</span></span>
    
    <span data-ttu-id="7d407-p109">d. 指定したすべてのコンテンツの場所で、検索クエリと一致するアイテムの合計数。アイテムの種類の例には、メール メッセージ、予定表アイテム、ドキュメントなどが含まれます。アイテムに検索対象のキーワードの複数のインスタンスが含まれている場合は、アイテムの合計数を 1 度カウントするのみです。たとえば、「stock」または「fraud」という単語を検索しており、さらに「stock」という単語の 3 つのインスタンスがメール メッセージに含まれている場合は、**[アイテム]** 列を 1 回カウントするのみです。</span><span class="sxs-lookup"><span data-stu-id="7d407-p109">d. The total number of items of all specified content locations that match the search query. Examples of item types include email messages, calendar items, and documents. If an item contains multiple instances of a keyword that is being searched for, it's only counted once in the total number of items. For example, if you're searching for words "stock" or "fraud" and an email message contains three instances of the word "stock", it's only counted once in the **Items** column.</span></span> 
    
    <span data-ttu-id="7d407-p110">e. 指定したコンテンツの場所で見つかった、検索クエリに一致するすべてのアイテムの合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="7d407-p110">e. The total size of all items that were found in the specified content location that match the search query.</span></span> 
    
    <span data-ttu-id="7d407-140">**クエリ**</span><span class="sxs-lookup"><span data-stu-id="7d407-140">**Queries**</span></span>
    
    <span data-ttu-id="7d407-141">このページには、検索クエリに関する統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d407-141">This page displays statistics about the search query.</span></span>
    
    ![選択した検索の検索クエリ統計情報](media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    <span data-ttu-id="7d407-p111">a. その行のクエリ統計情報に対するコンテンツ検索の名前。</span><span class="sxs-lookup"><span data-stu-id="7d407-p111">a. The name of the Content Search that the row contains query statistics for.</span></span>
    
    <span data-ttu-id="7d407-p112">b. クエリ統計情報の対象となるコンテンツの場所の種類。</span><span class="sxs-lookup"><span data-stu-id="7d407-p112">b. The type of content location that the query statistics are applicable to.</span></span>
    
    <span data-ttu-id="7d407-p113">c. この列には、統計情報が該当する検索クエリの部分が示されます。**[プライマリ]** は、検索クエリ全体を示します。検索クエリを作成または編集するときにキーワード リストを使用した場合は、クエリの各コンポーネントの統計情報がこの表に含まれます。詳細については、この記事の「[コンテンツ検索のキーワード統計情報を取得する](#get-keyword-statistics-for-content-searches)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d407-p113">c. This column indicates which part of the search query the statistics are applicable to. **Primary** indicates the entire search query. If you use a keyword list when you create or edit a search query, statistics for each component of the query are included in this table. See the [Get keyword statistics for Content Searches](#get-keyword-statistics-for-content-searches) section in this article for more information.</span></span> 
    
    <span data-ttu-id="7d407-p114">d. この列には、コンテンツ検索ツールによって実行された実際の検索クエリが表示されます。クエリにはツールによっていくつかの追加コンポーネントが自動的に追加されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="7d407-p114">d. This column contains the actual search query that run by the Content Search tool. Note that the tool automatically adds a few additional components to the query that you create.</span></span> 

    - <span data-ttu-id="7d407-155">キーワードを指定せず、メールボックス内のすべてのコンテンツを検索すると、すべてのアイテムが返されるように、実際のキーワード クエリは `size>=0` のようになります。</span><span class="sxs-lookup"><span data-stu-id="7d407-155">When you search for all content in mailboxes (by not specifying any keywords), the actual key word query is  `size>=0` so that all items are returned.</span></span> 
    
     - <span data-ttu-id="7d407-156">SharePoint Online と OneDrive for Business サイトを検索すると、次の 2 つのコンポーネントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="7d407-156">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
          <span data-ttu-id="7d407-157">**NOT IsExternalContent:1** - オンプレミスの SharePoint 組織のコンテンツを除外します。</span><span class="sxs-lookup"><span data-stu-id="7d407-157">**NOT IsExternalContent:1** - Excludes any content from an on-premises SharePoint organization.</span></span> 
    
          <span data-ttu-id="7d407-158">**NOT IsOneNotePage:1** - すべての OneNote ファイルを除外します。これは、これらのファイルは検索クエリと一致するドキュメントと重複するためです。</span><span class="sxs-lookup"><span data-stu-id="7d407-158">**NOT IsOneNotePage:1** - Excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span> 

    
    <span data-ttu-id="7d407-p115">e. **[クエリ]** 列で示されている検索クエリと一致するアイテムを含むコンテンツの場所 ([\*\* コンテンツの場所 \*\*] 列で指定されているもの) の数。</span><span class="sxs-lookup"><span data-stu-id="7d407-p115">e. The number of the content locations (specified by the \*\* Location type \*\* column) that contain items that match the search query listed in the **Query** column.</span></span> 
    
    <span data-ttu-id="7d407-p116">f. **[クエリ]** 列で示されている検索クエリと一致する (指定されたコンテンツの場所の) アイテムの数。前に説明したように、アイテムに検索対象のキーワードの複数のインスタンスが含まれている場合、この列では 1 回だけカウントされます。</span><span class="sxs-lookup"><span data-stu-id="7d407-p116">f. The number of items (from the specified content location) that match the search query listed in the **Query** column. As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in the this column.</span></span> 
    
    <span data-ttu-id="7d407-p117">g. 指定したコンテンツの場所で見つかった、**[クエリ]** 列の検索クエリに一致するすべてのアイテムの合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="7d407-p117">g. The total size of all items that were found (in the specified content location) that match the search query in the **Query** column.</span></span> 
    
    <span data-ttu-id="7d407-166">**トップの場所**</span><span class="sxs-lookup"><span data-stu-id="7d407-166">**Top locations**</span></span>
    
    <span data-ttu-id="7d407-p118">このページには、検索された各コンテンツの場所で検索クエリに一致したアイテムの数に関する統計情報が表示されます。上位 1,000 の場所が表示されます。複数の検索の統計情報を表示する場合、各検索の上位 1,000 の場所が表示されます。検索クエリに一致する項目が含まれない場合、このページにはコンテンツの場所が含まれないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="7d407-p118">This page displays statistics about the number of items that match the search query in each content location that was searched. The top 1,000 locations are displayed. If you view statistics for multiple searches, the top 1,000 locations for each search are displayed. Note that a content location isn't included on this page if it doesn't contain any items that match the search query.</span></span>
    
    ![検索されたコンテンツの場所で見つかったアイテムの数に関する統計情報](media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    <span data-ttu-id="7d407-p119">a. コンテンツの場所の名前。</span><span class="sxs-lookup"><span data-stu-id="7d407-p119">a. The name of the content location.</span></span>
    
    <span data-ttu-id="7d407-p120">b. 場所の統計情報の対象となるコンテンツの場所の種類。</span><span class="sxs-lookup"><span data-stu-id="7d407-p120">b. The type of content location that the location statistics are applicable to.</span></span>
    
    <span data-ttu-id="7d407-p121">c. 統計情報を表示している検索ごとに列があります。この列には、各コンテンツの場所で検索クエリに一致したアイテムの数 (および合計サイズ) が表示されます。複数の検索の統計情報を表示している場合は、コンテンツの場所がその検索に含まれなかったことを示す "NA" がこの列に表示されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="7d407-p121">c. There are columns for each search that you're displaying statistics for. This column shows the number (and total size) of items that match the search query in each content location. Note that when you're displaying statistics for multiple searches, the "NA" in this column indicates that the content location wasn't included in that search.</span></span> 

## <a name="get-keyword-statistics-for-content-searches"></a><span data-ttu-id="7d407-180">コンテンツ検索のキーワード統計情報を取得する</span><span class="sxs-lookup"><span data-stu-id="7d407-180">Get keyword statistics for Content Searches</span></span>

<span data-ttu-id="7d407-p122">前に説明したように、[**クエリ**] ページには、検索クエリと、クエリに一致したアイテムの数 (およびサイズ) が表示されます。検索クエリを作成または編集するときにキーワード リストを使用した場合は、各キーワードやキーワード語句に一致するアイテムの数を表示する拡張統計を取得できます。これは、クエリの最も有効な (または最も有効でない) 部分をすばやく識別するのに役立ちます。たとえば、多数のアイテムを返すキーワードがある場合は、キーワード クエリを修正して検索結果を絞り込むことができます。コンテンツ検索を作成または編集するときに、キーワード リストを設定できます。</span><span class="sxs-lookup"><span data-stu-id="7d407-p122">As previous explained, the **Queries** page shows the search query and the number (and size) of items that match the query. If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase. This can help you quickly identify which parts of the query are the most (and least) effective. For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results. You can set up a keyword list when you create or edit a Content Search.</span></span> 


<span data-ttu-id="7d407-186">キーワード リストを作成して、コンテンツ検索のキーワード統計情報を表示するには:</span><span class="sxs-lookup"><span data-stu-id="7d407-186">To create a keyword list and view keyword statistics for a Content Search:</span></span>
  
1. <span data-ttu-id="7d407-187">セキュリティ & コンプライアンスセンターで、[**検索** \> **コンテンツの検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7d407-187">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>
    
2. <span data-ttu-id="7d407-188">コンテンツ検索の一覧で、検索をクリックし、**[編集]** ![編集アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d407-188">In the list of Content Searches, click and a search, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="7d407-189">**[クエリ]** をクリックして、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7d407-189">Click **Query** and then do the following things:</span></span> 
    
    ![[キーワード リストの表示] チェック ボックスをオンにして、各行にキーワードを入力する](media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    <span data-ttu-id="7d407-p123">a. **[キーワード リストの表示]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7d407-p123">a. Click the **Show keyword list** check box.</span></span> 
    
    <span data-ttu-id="7d407-p124">b. キーワード テーブルの行に、キーワードまたはキーワード句を入力します。たとえば、1 行目に「**予算**」と入力し、2 行目に「**セキュリティ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7d407-p124">b. Type a keyword or keyword phase in a row in the keywords table. For example, type **budget** in the first row and then type **security** in the second row.</span></span> 
    
4. <span data-ttu-id="7d407-196">検索して統計情報を取得するキーワードを追加した後、**[検索]** をクリックして修正した検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="7d407-196">After adding the keywords that you want to search and get statistics for, click **Search** to run the revised search.</span></span> 
    
5. <span data-ttu-id="7d407-p125">検索が完了したら、検索の一覧でそれを選択し、**[検索の統計]** ![[検索の統計] ボタン](media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) をクリックします。複数の検索のキーワード統計情報を表示して比較することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d407-p125">When the search is completed, select it in the list of searches, and then click **Search statistics** ![Search Statistics button](media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png). You can also display and compare keyword statistics for multiple searches.</span></span>
    
6. <span data-ttu-id="7d407-199">**[検索の統計]** ページで、**[クエリ]** をクリックして選択した検索のキーワード統計情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="7d407-199">On the **Search statistics** page, click **Query** to display the keyword statistics for the selected searches.</span></span> 
    
    ![選択した検索の各キーワードの統計情報が表示される](media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    <span data-ttu-id="7d407-201">前のスクリーンショットで示したように、各キーワードの統計情報が表示されます。次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d407-201">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span> 
    
    - <span data-ttu-id="7d407-202">検索に含まれるコンテンツの場所の各種類に対するキーワード統計。</span><span class="sxs-lookup"><span data-stu-id="7d407-202">The keyword statistics for each type of content location included in the search.</span></span>
    
    - <span data-ttu-id="7d407-203">各キーワードの実際の検索クエリ。これには、検索クエリのすべての条件が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d407-203">The actual search query for each keyword, which includes any conditions from the search query.</span></span> 
    
    - <span data-ttu-id="7d407-p126">完全な検索クエリ (**[部分]** 列には **[プライマリ]** と表示されます) および完全なクエリの統計情報。これらは **[概要]** ページに表示されるものと同じ統計情報であることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="7d407-p126">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query. Note these are the same statistics displayed on the **Summary** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="7d407-206">大規模なキーワード リストによって生じる問題を軽減するため、検索クエリのキーワード リストの行は最大 20 行に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7d407-206">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>
