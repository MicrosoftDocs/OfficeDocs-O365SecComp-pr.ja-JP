---
title: 検索の統計情報
ms.author: markjjo
author: esclee
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
ms.openlocfilehash: c5b7caff3550d42d84408d6b4e966655b8341123
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608044"
---
# <a name="search-statistics"></a><span data-ttu-id="f8b77-102">検索の統計情報</span><span class="sxs-lookup"><span data-stu-id="f8b77-102">Search statistics</span></span>
<span data-ttu-id="f8b77-p101">検索結果を検証する方法の 1 つは、期待どおりにそれらを配置することを確認するのには、結果の周りの統計を参照するのには。検索が完了すると、高度な統計情報の検索の詳細のフライアウトのとおりです。</span><span class="sxs-lookup"><span data-stu-id="f8b77-p101">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations. When a search completes, high-level statistics are shown on the search details flyout:</span></span>
- <span data-ttu-id="f8b77-105">番号と検索で取得したアイテムのボリューム</span><span class="sxs-lookup"><span data-stu-id="f8b77-105">Number and volume of items retrieved by the search</span></span>
- <span data-ttu-id="f8b77-106">番号とボリュームの部分的にインデックスとインデックス検索の場所で見つかった項目</span><span class="sxs-lookup"><span data-stu-id="f8b77-106">Number and volume of partially indexed/unindexed items that were found in the search locations</span></span>
- <span data-ttu-id="f8b77-p102">メールボックス数と場所を検索します。詳細な統計情報を表示するために検索の詳細のフライアウトから [統計] でをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8b77-p102">Number of mailboxes and locations searched. In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary"></a><span data-ttu-id="f8b77-109">概要</span><span class="sxs-lookup"><span data-stu-id="f8b77-109">Summary</span></span>
<span data-ttu-id="f8b77-p103">サマリー ビューでは、(Exchange など) の場所の種類ごとに分類された検索結果を表示できます。各場所の種類には次の内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f8b77-p103">In Summary view, you can see the search results broken down by location type (e.g. Exchange). For each location type, you can see:</span></span>
- <span data-ttu-id="f8b77-112">検索条件に一致したアイテムがあった場所の数</span><span class="sxs-lookup"><span data-stu-id="f8b77-112">Number of locations that had items that matched the search conditions</span></span>
- <span data-ttu-id="f8b77-113">検索条件に一致したこれらの場所からのアイテムの数</span><span class="sxs-lookup"><span data-stu-id="f8b77-113">Number of items from these locations that matched the search conditions</span></span>
- <span data-ttu-id="f8b77-114">検索条件に一致した項目の総ボリュームです。</span><span class="sxs-lookup"><span data-stu-id="f8b77-114">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations"></a><span data-ttu-id="f8b77-115">上の場所</span><span class="sxs-lookup"><span data-stu-id="f8b77-115">Top locations</span></span>
<span data-ttu-id="f8b77-p104">上の場所のビューでは、個々 の場所に一致するものでは、最も参照してください。それぞれの場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8b77-p104">In Top locations view, you see the individual locations with the most matches. For each location, you will see:</span></span>
- <span data-ttu-id="f8b77-118">場所の名前 (例: SharePoint の URL)</span><span class="sxs-lookup"><span data-stu-id="f8b77-118">Location name (e.g. SharePoint URL)</span></span>
- <span data-ttu-id="f8b77-119">場所の種類</span><span class="sxs-lookup"><span data-stu-id="f8b77-119">Location type</span></span>
- <span data-ttu-id="f8b77-120">検索条件に一致した項目の数</span><span class="sxs-lookup"><span data-stu-id="f8b77-120">Number of items that matched the search conditions</span></span>
- <span data-ttu-id="f8b77-121">検索条件に一致した項目の総ボリュームです。</span><span class="sxs-lookup"><span data-stu-id="f8b77-121">Total volume of items that matched the search conditions.</span></span>

## <a name="queries"></a><span data-ttu-id="f8b77-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="f8b77-122">Queries</span></span>
<span data-ttu-id="f8b77-p105">クエリ (c:s) のキーワードまたはキーワードの行を使用した場合、場所の種類ごとにクエリのビューでクエリの詳細を参照してくださいことができます。各場所の種類に対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8b77-p105">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type. For each location type, you will see:</span></span>
- <span data-ttu-id="f8b77-p106">パーツ: 単語「プライマリ」または「キーワード」する必要がこの列です。「プライマリ」は、行は、クエリ全体の統計情報を、"キーワード"は、クエリ コンポーネントのいずれか一方。</span><span class="sxs-lookup"><span data-stu-id="f8b77-p106">Part: this column will either have the word "Primary" or "Keyword". "Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>
- <span data-ttu-id="f8b77-p107">クエリ: クエリの実際のコンポーネント行を指します。部品が「プライマリ」の場合、クエリ全体になります部品が「キーワード」の場合、クエリ コンポーネントを次いずれかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8b77-p107">Query: the actual query component the row refers to. If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  - <span data-ttu-id="f8b77-129">(任意のキーワードを指定しない)、contentin のすべてのメールボックスを検索すると、実際のクエリは、(サイズ _gt = 0) のすべてのアイテムが返されるように</span><span class="sxs-lookup"><span data-stu-id="f8b77-129">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  - <span data-ttu-id="f8b77-130">ビジネス サイトの SharePoint Online と OneDrive を検索すると、次の 2 つのコンポーネントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="f8b77-130">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    - <span data-ttu-id="f8b77-131">-IsExternalContent:1 ではありませんが、設置型の SharePoint の組織からのコンテンツを除外します。</span><span class="sxs-lookup"><span data-stu-id="f8b77-131">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    - <span data-ttu-id="f8b77-132">IsOneNotePage ではありません: 1 - は、これらが検索クエリに一致するすべてのドキュメントの重複になるために OneNote のすべてのファイルを除外します。</span><span class="sxs-lookup"><span data-stu-id="f8b77-132">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>
- <span data-ttu-id="f8b77-133">検索条件に一致したアイテムがあった場所の数</span><span class="sxs-lookup"><span data-stu-id="f8b77-133">Number of locations that had items that matched the search conditions</span></span>
- <span data-ttu-id="f8b77-134">検索条件に一致したこれらの場所からのアイテムの数</span><span class="sxs-lookup"><span data-stu-id="f8b77-134">Number of items from these locations that matched the search conditions</span></span>
- <span data-ttu-id="f8b77-135">検索条件に一致した項目の総ボリュームです。</span><span class="sxs-lookup"><span data-stu-id="f8b77-135">Total volumne of items that matched the search conditions.</span></span>

## <a name="refiners"></a><span data-ttu-id="f8b77-136">絞り込み条件</span><span class="sxs-lookup"><span data-stu-id="f8b77-136">Refiners</span></span>
<span data-ttu-id="f8b77-p108">Exchange メールボックスの絞り込み条件ビューでは、ItemClass、送信者、および受信者がその他の内訳です。場所と絞り込み条件、値ごとには、ドキュメントの数は、検索で返されたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f8b77-p108">For Exchange mailboxes, Refiners view gives you additional breakdowns by ItemClass, Sender, and Recipient. For each location and refiner value, you can see how many documents were returned in the search.</span></span>