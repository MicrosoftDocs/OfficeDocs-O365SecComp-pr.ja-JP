---
title: 検索クエリのビルド
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
ms.openlocfilehash: a33ecb6e1a2549b6bdc3bde9897b8a75e742b482
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151929"
---
# <a name="build-search-queries"></a><span data-ttu-id="5a6a1-102">検索クエリのビルド</span><span class="sxs-lookup"><span data-stu-id="5a6a1-102">Build search queries</span></span>

<span data-ttu-id="5a6a1-103">クエリを作成するときには、さまざまなキーワードと条件を使用して、検索するアイテムを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="5a6a1-104">キーワード検索</span><span class="sxs-lookup"><span data-stu-id="5a6a1-104">Keyword searches</span></span>

<span data-ttu-id="5a6a1-105">[**キーワード**] ボックスに検索クエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-105">Type a search query in **Keywords** box.</span></span> <span data-ttu-id="5a6a1-106">キーワード、メッセージ プロパティ (送信日付や受信日付など)、ドキュメント プロパティ (ファイル名や、ドキュメントの最終変更日など) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-106">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="5a6a1-107">**And**、 **OR**、 **NOT**、 **NEAR**などのブール演算子を使用するより複雑なクエリを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-107">You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="5a6a1-108">また、ドキュメント内の機密情報 (社会保障番号など) を検索したり、外部で共有されているドキュメントを検索したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-108">You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="5a6a1-109">[キーワード] ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが検索結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-109">If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="5a6a1-p102">または、**[キーワード リストの表示]** チェックボックスをオンにして、各行にキーワードを入力することもできます。このようにすると、各行のキーワードは、作成された検索クエリの **OR** 演算子の機能に似た論理演算子 (**c:s**) によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-p102">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="5a6a1-112">キーワードリストを使用する理由</span><span class="sxs-lookup"><span data-stu-id="5a6a1-112">Why use the keyword list?</span></span> <span data-ttu-id="5a6a1-113">各キーワードに一致するアイテムの数を示す統計情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-113">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="5a6a1-114">これにより、どのキーワードが最もよく (かつ最も少ない) 有効であるかをすばやく識別することができます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-114">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="5a6a1-115">また、行内のキーワード句 (かっこで囲む) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-115">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="5a6a1-116">検索統計の詳細については、「[検索統計](search-statistics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-116">For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="5a6a1-117">条件</span><span class="sxs-lookup"><span data-stu-id="5a6a1-117">Conditions</span></span>
    
<span data-ttu-id="5a6a1-118">検索条件を追加して、検索を絞り込んだり、より洗練された結果セットを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-118">You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="5a6a1-119">各条件は、検索を開始するときに作成され、実行される句を検索クエリに追加します。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-119">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="5a6a1-120">条件は、論理演算子 (**c:c**) によって論理的に (キーワードボックスで指定された) キーワードクエリに関連付けられています。これは、 **and 演算子と**機能が似ています。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-120">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="5a6a1-121">つまり、アイテムは、キーワードクエリと、結果に含まれる1つ以上の条件を満たす必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-121">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="5a6a1-122">このように条件は、結果を絞り込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-122">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="5a6a1-123">検索クエリで使用できる条件の一覧と説明については、「[コンテンツ検索のキーワードクエリと検索条件](../keyword-queries-and-search-conditions.md#search-conditions)」の「検索条件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a6a1-123">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


