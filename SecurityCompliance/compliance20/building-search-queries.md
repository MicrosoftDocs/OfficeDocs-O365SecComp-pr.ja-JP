---
title: 検索クエリのビルド
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e62d486b102fa035ae21b379d30bb0657b82acc9
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296220"
---
# <a name="build-search-queries"></a><span data-ttu-id="99053-102">検索クエリのビルド</span><span class="sxs-lookup"><span data-stu-id="99053-102">Build search queries</span></span>

<span data-ttu-id="99053-103">クエリを作成するときには、さまざまなキーワードと条件を使用して、検索するアイテムを定義できます。</span><span class="sxs-lookup"><span data-stu-id="99053-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="99053-104">キーワード検索</span><span class="sxs-lookup"><span data-stu-id="99053-104">Keyword searches</span></span>

<span data-ttu-id="99053-p101">[**キーワード**] ボックスに検索クエリを入力します。キーワード、メッセージプロパティ (送信日時や受信日時など)、またはファイル名、ドキュメントが最後に変更された日付などのドキュメントプロパティを指定できます。**and**、 **OR**、 **NOT**、 **NEAR**などのブール演算子を使用するより複雑なクエリを使用することができます。また、ドキュメント内の機密情報 (社会保障番号など) を検索したり、外部で共有されているドキュメントを検索したりすることもできます。[キーワード] ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが検索結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="99053-p101">Type a search query in **Keywords** box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="99053-p102">または、[**キーワードリストを表示**する] チェックボックスをオンにして、各行にキーワードを入力することもできます。このようにすると、各行のキーワードは、作成された検索クエリの**or**演算子の機能に似た論理演算子 ( **c:s**) によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="99053-p102">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="99053-p103">キーワードリストを使用する理由各キーワードに一致するアイテムの数を示す統計情報を取得することができます。これにより、どのキーワードが最もよく (かつ最も少ない) 有効であるかをすばやく識別することができます。また、行内のキーワード句 (かっこで囲む) を使用することもできます。検索統計の詳細については、「[検索統計](search-statistics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99053-p103">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="99053-117">条件</span><span class="sxs-lookup"><span data-stu-id="99053-117">Conditions</span></span>
    
<span data-ttu-id="99053-p104">検索条件を追加して、検索を絞り込んだり、より洗練された結果セットを返すことができます。各条件は、検索を開始するときに作成され、実行される句を検索クエリに追加します。条件は、論理演算子 (**c:c**) によって論理的に (キーワードボックスで指定された) キーワードクエリに関連付けられています。これは、 **and 演算子と**機能が似ています。つまり、アイテムは、キーワードクエリと、結果に含まれる1つ以上の条件を満たす必要があることを意味します。このようにすると、条件によって結果を絞り込むことができます。検索クエリで使用できる条件の一覧と説明については、「[コンテンツ検索のキーワードクエリと検索条件](../keyword-queries-and-search-conditions.md#search-conditions)」の「検索条件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99053-p104">You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


