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
description: Microsoft 365 でデータ調査を使用しているときにデータを検索するときに、検索範囲を絞るには、キーワードと条件を使用します。
ms.openlocfilehash: 913306ff488d9cf2ba715c26eaa49f6f8e1473aa
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "36649942"
---
# <a name="build-search-queries"></a><span data-ttu-id="fa2f4-103">検索クエリのビルド</span><span class="sxs-lookup"><span data-stu-id="fa2f4-103">Build search queries</span></span>

<span data-ttu-id="fa2f4-104">検索クエリを作成するときには、キーワードを使用して特定のコンテンツと条件を検索し、検索の範囲を絞り込んで、調査に最も関連のあるアイテムを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-104">When building search queries, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your investigation.</span></span>

![キーワードと条件を使用して検索結果を絞り込む](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="fa2f4-106">キーワード検索</span><span class="sxs-lookup"><span data-stu-id="fa2f4-106">Keyword searches</span></span>

<span data-ttu-id="fa2f4-107">検索クエリの [**キーワード**] ボックスにキーワードクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="fa2f4-108">キーワード、電子メールメッセージのプロパティ (送信日時や受信日時など)、またはドキュメントプロパティ (ファイル名、ドキュメントが最後に変更された日付など) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-108">You can specify keywords, email message properties, (such as sent and received dates), or document properties (such as file names or the date that a document was last changed).</span></span> <span data-ttu-id="fa2f4-109">**And**、 **OR**、 **NOT**、 **NEAR**などのブール演算子を使用するより複雑なクエリを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="fa2f4-110">SharePoint および OneDrive (電子メールメッセージではない) のドキュメントで機密情報 (社会保障番号など) を検索したり、外部で共有されているドキュメントを検索したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="fa2f4-111">[**キーワード**] ボックスを空白のままにすると、指定されたコンテンツの場所にあるすべてのコンテンツが検索結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-111">If you leave the **Keywords** box empty, all content located in the specified content locations is included in the search results.</span></span>
    
<span data-ttu-id="fa2f4-112">または、[**キーワードリストを表示**する] チェックボックスをオンにして、各行にキーワードまたはキーワードフレーズを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-112">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="fa2f4-113">このようにすると、各行のキーワードが論理演算子 ( *c:s*として表されます) によって接続されます。これは、作成された検索クエリの**or**演算子の機能と類似しています。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-113">If you do this, the keywords in each row are connected by a logical operator (represented as *c:s*) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="fa2f4-114">つまり、任意の行にキーワードが含まれているアイテムは検索結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-114">This means that items that contain any keyword in any row are included in the search results.</span></span>

![キーワードリストを使用して、クエリ内の各キーワードの統計情報を取得する](../media/KeywordListSearch.png)

<span data-ttu-id="fa2f4-116">キーワードリストを使用する理由</span><span class="sxs-lookup"><span data-stu-id="fa2f4-116">Why use the keyword list?</span></span> <span data-ttu-id="fa2f4-117">キーワードリストの各キーワードに一致するアイテムの数を示す統計情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="fa2f4-118">これは、最も頻繁に使用される (および最も少ない) キーワードをすばやく識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="fa2f4-119">キーワードリストの行にキーワードフレーズ (かっこで囲む) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="fa2f4-120">検索統計の詳細については、「[検索統計](search-statistics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fa2f4-121">大きなキーワードリストによって発生する問題を減らすために、キーワード一覧では最大20行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="fa2f4-122">条件</span><span class="sxs-lookup"><span data-stu-id="fa2f4-122">Conditions</span></span>
    
<span data-ttu-id="fa2f4-123">検索条件を追加して検索の範囲を絞り込んだり、より洗練された結果セットを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="fa2f4-124">各条件は、検索を開始するときに作成され、実行される句を検索クエリに追加します。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="fa2f4-125">条件は論理演算子 (キーワード box で指定されています) によって論理的に接続されています ( *c:c*として表されます)。 **and 演算子と**機能が似ています。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-125">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (which is represented as *c:c*) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="fa2f4-126">つまり、アイテムは、キーワードクエリと、検索結果に含まれる1つまたは複数の条件を満たす必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-126">That means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="fa2f4-127">このように条件は、結果を絞り込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="fa2f4-128">検索クエリで使用できる条件の一覧と説明については、「[キーワードクエリと検索条件](../keyword-queries-and-search-conditions.md#search-conditions)」の「検索条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-128">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>
