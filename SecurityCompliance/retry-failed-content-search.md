---
title: コンテンツ検索を再試行してコンテンツの場所のエラーを解決する
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: コンテンツの場所にエラーがあるコンテンツ検索を解決するには、[再試行] ボタンを使用します。
ms.openlocfilehash: 91c656a05111391ad93e03946cf367133f2c25a2
ms.sourcegitcommit: ff1d18aaddde2048f1cf88338c916295cf8c354e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2019
ms.locfileid: "34748570"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="f90bd-103">コンテンツ検索を再試行してコンテンツの場所のエラーを解決する</span><span class="sxs-lookup"><span data-stu-id="f90bd-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="f90bd-104">セキュリティ/コンプライアンスセンターでコンテンツ検索を使用して多数のメールボックスを検索すると、次のような検索エラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f90bd-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the following:</span></span>

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="f90bd-105">これらのエラー (エラーコード CS001-002、CS003-002、CS008-009、CS012-002、および CS0XX-0XX の他のエラー) は、コンテンツ検索で特定のコンテンツの場所を検索できなかったことを示しています。この例では、2つのメールボックスが検索されませんでした。</span><span class="sxs-lookup"><span data-stu-id="f90bd-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="f90bd-106">これらのエラーは、コンテンツ検索の [状態の詳細] ポップアップページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f90bd-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="f90bd-107">コンテンツの場所にエラーが発生する原因</span><span class="sxs-lookup"><span data-stu-id="f90bd-107">Cause of content location errors</span></span>

<span data-ttu-id="f90bd-108">多数のメールボックスを検索する場合、検索は Microsoft データセンター内の数千人のサーバーに分散されます。</span><span class="sxs-lookup"><span data-stu-id="f90bd-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="f90bd-109">いつでも、特定のサーバーが再起動状態になったり、冗長コピーにフェールオーバーするプロセスであったりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f90bd-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="f90bd-110">どちらの場合も、データを取得するためのコンテンツ検索要求がタイムアウトになります。</span><span class="sxs-lookup"><span data-stu-id="f90bd-110">In either of these cases, the Content Search's request to retrieve data will timeout.</span></span> <span data-ttu-id="f90bd-111">前の例では、失敗したメールボックスのエラーは、検索がタイムアウトした結果です。</span><span class="sxs-lookup"><span data-stu-id="f90bd-111">In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="f90bd-112">コンテンツの場所のエラーを解決する</span><span class="sxs-lookup"><span data-stu-id="f90bd-112">Resolving content location errors</span></span>

<span data-ttu-id="f90bd-113">検索を再起動すると、複数のサーバーで同様のエラーが発生することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="f90bd-113">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="f90bd-114">検索を再起動する代わりに、検索結果ページの上部に表示される [**再試行**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f90bd-114">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![[再試行] ボタンをクリックしてコンテンツの場所のエラーを解決する](media/retrycontentsearch3.png)

<span data-ttu-id="f90bd-116">これにより、失敗したメールボックスに対してのみ検索を再試行します。</span><span class="sxs-lookup"><span data-stu-id="f90bd-116">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="f90bd-117">検索を再試行すると、正常に返されたその他の結果は保持されます。</span><span class="sxs-lookup"><span data-stu-id="f90bd-117">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="f90bd-118">コンテンツの場所エラーを回避するためのヒント</span><span class="sxs-lookup"><span data-stu-id="f90bd-118">Tips to avoid content location errors</span></span>

<span data-ttu-id="f90bd-119">ここでは、コンテンツの場所に関するエラーの原因と、多数のメールボックスを検索するときに回避するためのヒントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f90bd-119">Here are some addition causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="f90bd-120">検索されているメールボックスが、ユーザーのアクティビティのためにビジー状態である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f90bd-120">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="f90bd-121">この場合、検索サービスでは、メールボックスが使用できなくなるように調整されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f90bd-121">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="f90bd-122">この問題を回避するには、勤務時間外に検索を実行するようにします。</span><span class="sxs-lookup"><span data-stu-id="f90bd-122">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="f90bd-123">検索クエリがメールボックスから大量のコンテンツを取得している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f90bd-123">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="f90bd-124">可能であれば、キーワード、日付の範囲、および検索条件を使用して、検索範囲を絞るようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f90bd-124">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="f90bd-125">キーワード[リスト](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)を使用して検索クエリを作成するときに、キーワードやキーワード語句が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f90bd-125">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches).</span></span> <span data-ttu-id="f90bd-126">キーワードリストを使用する検索クエリを実行すると、基本的には、統計が生成されるように、キーワードリストの各行に対して個別に検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="f90bd-126">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="f90bd-127">検索クエリでキーワードリストを使用している場合は、キーワードリストの行数を最小にするか、数字のキーワードを小さなリストに分割して、各キーワードリストに対して異なる検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="f90bd-127">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f90bd-128">大規模なキーワード リストによって生じる問題を軽減するため、検索クエリのキーワード リストの行は最大 20 行に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f90bd-128">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="f90bd-129">同じメールボックスで同時に実行されている検索が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f90bd-129">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="f90bd-130">可能であれば、1つのメールボックスで一度に1つずつ検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="f90bd-130">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="f90bd-131">単一の検索で大量のメールボックスを検索しています。</span><span class="sxs-lookup"><span data-stu-id="f90bd-131">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="f90bd-132">非常に多くのメールボックスを検索すると、コンテンツの場所エラーが発生する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="f90bd-132">The probability of content location errors increases when searching a very large number of mailboxes.</span></span> <span data-ttu-id="f90bd-133">可能であれば、各検索で組織内のメールボックスのサブセットが含まれるように、複数の検索を実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="f90bd-133">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="f90bd-134">メールボックスで必要なメンテナンスが実行されている。</span><span class="sxs-lookup"><span data-stu-id="f90bd-134">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="f90bd-135">この原因はほとんどありませんが、コンテンツの場所エラーを受け取ってからしばらく待ってから、検索を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="f90bd-135">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
