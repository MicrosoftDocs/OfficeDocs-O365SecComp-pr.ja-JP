---
title: レビューセット内のデータを照会する
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
ms.openlocfilehash: 395cc01238f4dbc91de5dd652e10121f5e0cc926
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527216"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="f970f-102">レビューセット内のデータを照会する</span><span class="sxs-lookup"><span data-stu-id="f970f-102">Query the data in a review set</span></span>

<span data-ttu-id="f970f-103">ほとんどの場合、レビューセットにあるものを深く掘り下げて、レビューのために整理して、より効率的にレビューできるようにするのが便利です。</span><span class="sxs-lookup"><span data-stu-id="f970f-103">In most cases, it will be useful to be able to dig deeper into what is there in a review set and organize them to review more efficiently.</span></span> <span data-ttu-id="f970f-104">校閲セット内のクエリを使用すると、一度に定義された条件を満たすドキュメントのサブセットに集中することができます。</span><span class="sxs-lookup"><span data-stu-id="f970f-104">Queries within a review set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-review-set"></a><span data-ttu-id="f970f-105">レビューセット内でのクエリの作成と実行</span><span class="sxs-lookup"><span data-stu-id="f970f-105">Creating and running a query within a review set</span></span>

<span data-ttu-id="f970f-106">レビューセット内でクエリを作成して実行するには、レビューセットの [新しいクエリ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f970f-106">In order to create and run a query within your review set, click on "New Query" in your review set.</span></span> <span data-ttu-id="f970f-107">クエリの名前を指定して条件を定義したら、[保存] をクリックしてクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="f970f-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="f970f-108">以前に保存したクエリを実行するには、保存されているクエリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f970f-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="f970f-109">検索可能なメタデータの一覧については、「[ドキュメントメタデータ」フィールド](document-metadata-fields.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f970f-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="f970f-110">クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="f970f-110">Building your query</span></span>

<span data-ttu-id="f970f-111">キーワード条件カードでは、条件カードとクエリ言語の組み合わせを使用してクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f970f-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="f970f-112">条件カードをブロックとしてグループ化して、より複雑なクエリを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f970f-112">You can group condition cards together as a block to craft a more complex query.</span></span>

### <a name="condition-card"></a><span data-ttu-id="f970f-113">条件カード</span><span class="sxs-lookup"><span data-stu-id="f970f-113">Condition card</span></span>

<span data-ttu-id="f970f-114">レビューセット内のすべての検索可能なフィールドには、クエリの作成に使用できる対応する条件カードがあります。</span><span class="sxs-lookup"><span data-stu-id="f970f-114">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="f970f-115">複数の種類の条件カードがあります。</span><span class="sxs-lookup"><span data-stu-id="f970f-115">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="f970f-116">Freetext: freetext 条件カードは、subject などのテキストフィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f970f-116">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="f970f-117">複数の検索用語をコンマで区切ってリストすることができます。</span><span class="sxs-lookup"><span data-stu-id="f970f-117">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="f970f-118">日付: 日付の条件カードは、最終変更日などの日付フィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f970f-118">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="f970f-119">検索オプション: 検索オプション条件カードは、レビューセットの特定のフィールドに使用可能な値の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="f970f-119">Search options: search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="f970f-120">これは、[送信者] などのフィールドに対して使用されます。これは、レビューセットに指定できる値が限定されている場合です。</span><span class="sxs-lookup"><span data-stu-id="f970f-120">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>
- <span data-ttu-id="f970f-121">キーワード: キーワード条件カードは、用語を検索したり、で KQL に似たクエリ言語を使用したりするために使用できる、freetext 条件カードの特定のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f970f-121">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="f970f-122">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f970f-122">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="f970f-123">クエリ言語</span><span class="sxs-lookup"><span data-stu-id="f970f-123">Query language</span></span>

<span data-ttu-id="f970f-124">条件カードに加えて、キーワードカードで KQL のようなクエリ言語を使用してクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f970f-124">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="f970f-125">クエリ言語は、AND、OR、NOT、NEAR (n) などの標準の KQL 構文をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f970f-125">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="f970f-126">また、1文字のワイルドカード (?) と複数文字のワイルドカード (\*) もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f970f-126">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>

## <a name="filter"></a><span data-ttu-id="f970f-127">フィルター</span><span class="sxs-lookup"><span data-stu-id="f970f-127">Filter</span></span>

<span data-ttu-id="f970f-128">保存できるクエリに加えて、フィルターを使用して、クエリ結果に対して、その場で追加の条件を重ねて表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f970f-128">In addition to queries that you can save, you can overlay additional conditions on the fly to your query results using filters.</span></span> <span data-ttu-id="f970f-129">フィルターは、いくつかの重要な方法でクエリとは異なります。</span><span class="sxs-lookup"><span data-stu-id="f970f-129">Filters differ from queries in a few significant ways:</span></span>
- <span data-ttu-id="f970f-130">フィルターは一時的なもの (つまり、異なるセッションでは保持されない) ですが、クエリはレビューセットに保存されます。</span><span class="sxs-lookup"><span data-stu-id="f970f-130">Filters are transient (i.e. they do not persist over different sessions), whereas queries are saved to the review set.</span></span>
- <span data-ttu-id="f970f-131">フィルターは常に付加的です。フィルターは、その時点で有効になっているクエリの上に適用されますが、クエリを適用すると、有効になっているクエリに置き換わります。</span><span class="sxs-lookup"><span data-stu-id="f970f-131">Filters are always additive; filters will apply on top of the query you have in effect at the moment, whereas applying a query will replace the query in effect.</span></span>