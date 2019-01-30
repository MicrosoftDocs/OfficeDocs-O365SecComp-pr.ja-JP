---
title: 検索クエリの作成
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
ms.openlocfilehash: 119cdd9d932b6c1be847c406988efa80b8534795
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608034"
---
# <a name="building-search-queries"></a><span data-ttu-id="d0df6-102">検索クエリの作成</span><span class="sxs-lookup"><span data-stu-id="d0df6-102">Building search queries</span></span>
<span data-ttu-id="d0df6-103">クエリを構築するには、検索するのに項目を定義するのには、さまざまなキーワードや条件を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0df6-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="d0df6-104">キーワード検索</span><span class="sxs-lookup"><span data-stu-id="d0df6-104">Keyword searches</span></span>
<span data-ttu-id="d0df6-p101">[**キーワード**] ボックスに検索クエリを入力します。キーワード、プロパティは次のように送信し、日付、またはファイル名などのドキュメント プロパティ、またはドキュメントが最後に変更された日付を受信したメッセージを指定できます。**AND**、**または**、**ない**、および**NEAR**などのブール演算子を使用するより複雑なクエリを使用することができます。などの機密情報 (社会保障番号) のドキュメント、または外部で共有されているドキュメントの検索で検索することもできます。場合は、[キーワード] ボックスを空白のままにすると、指定されたコンテンツの場所にあるすべてのコンテンツが検索結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0df6-p101">Type a search query in **Keywords** box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="d0df6-p102">または、それぞれの行のキーワード**キーワードの一覧を表示**] チェック ボックスと種類を選択できます。これを行う場合、論理演算子 ( **c:s**) に作成される検索クエリで**OR**演算子の機能に似ていますが、それぞれの行のキーワードが接続されています。</span><span class="sxs-lookup"><span data-stu-id="d0df6-p102">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="d0df6-p103">キーワードの一覧を使用する理由各キーワードに一致する数の項目を表示する統計情報を取得できます。どのキーワードは、(と最も少ない) 効果をすばやく識別できます。(かっこで囲まれている) のキーワード句は、行にも使用できます。検索の統計情報の詳細については、[検索の統計情報](search-statistics.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0df6-p103">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="d0df6-117">条件</span><span class="sxs-lookup"><span data-stu-id="d0df6-117">Conditions</span></span>    
<span data-ttu-id="d0df6-p104">検索を絞り込むより洗練された結果セットを返す検索条件を追加できます。各条件が作成され、検索を開始するときに実行する検索クエリに句を追加します。条件は、 **AND**演算子の機能に次のような論理演算子 (**c:c**) によって (、[キーワード] ボックスで指定) のキーワード クエリを論理的な接続します。キーワード クエリと結果に含まれる 1 つまたは複数の条件の両方を満たすために項目があることを意味します。これは、結果を絞り込む条件がどのように役立つか。一覧と、検索クエリで使用できる条件の説明、[キーワード クエリとコンテンツの検索の検索条件](../keyword-queries-and-search-conditions.md#search-conditions)で「検索条件」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0df6-p104">You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


