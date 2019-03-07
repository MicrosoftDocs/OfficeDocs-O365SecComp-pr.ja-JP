---
title: ワーキング セット内のデータのクエリ
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
ms.openlocfilehash: 2523072181307cce510f0f318834329b2c70b376
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454989"
---
# <a name="query-the-data-in-a-working-set"></a><span data-ttu-id="ce823-102">ワーキング セット内のデータのクエリ</span><span class="sxs-lookup"><span data-stu-id="ce823-102">Query the data in a working set</span></span>

<span data-ttu-id="ce823-103">ほとんどの場合、作業セットに含まれるものをより深く掘り下げて、より効率的にレビューできるように整理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ce823-103">In most cases, it will be useful to be able to dig deeper into what is there in a working set and organize them to review more efficiently.</span></span> <span data-ttu-id="ce823-104">作業セット内のクエリを使用すると、一度に定義された条件を満たすドキュメントのサブセットに集中することができます。</span><span class="sxs-lookup"><span data-stu-id="ce823-104">Queries within a working set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-working-set"></a><span data-ttu-id="ce823-105">作業セット内でのクエリの作成と実行</span><span class="sxs-lookup"><span data-stu-id="ce823-105">Creating and running a query within a working set</span></span>

<span data-ttu-id="ce823-106">作業セット内でクエリを作成して実行するには、ワーキングセット内の [新しいクエリ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce823-106">In order to create and run a query within your working set, click on "New Query" in your working set.</span></span> <span data-ttu-id="ce823-107">クエリの名前を指定して条件を定義したら、[保存] をクリックしてクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce823-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="ce823-108">以前に保存したクエリを実行するには、保存されているクエリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce823-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="ce823-109">検索可能なメタデータの一覧については、「[ドキュメントメタデータ」フィールド](document-metadata-fields.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce823-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="ce823-110">クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="ce823-110">Building your query</span></span>

<span data-ttu-id="ce823-111">キーワード条件カードでは、条件カードとクエリ言語の組み合わせを使用してクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce823-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span>

### <a name="condition-card"></a><span data-ttu-id="ce823-112">条件カード</span><span class="sxs-lookup"><span data-stu-id="ce823-112">Condition card</span></span>

<span data-ttu-id="ce823-113">作業セット内のすべての検索可能なフィールドには、クエリの作成に使用できる対応する条件カードがあります。</span><span class="sxs-lookup"><span data-stu-id="ce823-113">Every searchable field in a working set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="ce823-114">複数の種類の条件カードがあります。</span><span class="sxs-lookup"><span data-stu-id="ce823-114">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="ce823-115">freetext: freetext 条件カードは、subject などのテキストフィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce823-115">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="ce823-116">複数の検索用語をコンマで区切ってリストすることができます。</span><span class="sxs-lookup"><span data-stu-id="ce823-116">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="ce823-117">日付: 日付の条件カードは、最終変更日などの日付フィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce823-117">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="ce823-118">検索オプション: 検索オプション条件カードは、作業セットの特定のフィールドに使用可能な値の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="ce823-118">Search options: search options condition card will provide a list of possible values for the particular field in your working set.</span></span> <span data-ttu-id="ce823-119">これは、送信者などのフィールドに使用されます。これは、ワーキングセットに指定できる値が限定されている場合です。</span><span class="sxs-lookup"><span data-stu-id="ce823-119">This is used for fields such as sender, where there is a finite number of possible values in your working set.</span></span>
- <span data-ttu-id="ce823-120">キーワード: キーワード条件カードは、用語を検索したり、で kql に似たクエリ言語を使用したりするために使用できる、freetext 条件カードの特定のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="ce823-120">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="ce823-121">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce823-121">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="ce823-122">クエリ言語</span><span class="sxs-lookup"><span data-stu-id="ce823-122">Query language</span></span>

<span data-ttu-id="ce823-123">条件カードに加えて、キーワードカードで kql のようなクエリ言語を使用してクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce823-123">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="ce823-124">クエリ言語は、and、OR、NOT、NEAR (n) などの標準の kql 構文をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ce823-124">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="ce823-125">また、1文字のワイルドカード (?) と複数文字のワイルドカード (\*) もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ce823-125">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>