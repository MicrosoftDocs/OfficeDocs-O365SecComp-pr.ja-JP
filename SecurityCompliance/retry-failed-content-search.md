---
title: コンテンツの場所のエラーを解決するのにはコンテンツの検索を再試行してください。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: コンテンツの場所のエラーのあるコンテンツの検索を解決するためには、[再試行] ボタンを使用します。
ms.openlocfilehash: 0fdc11593fec42e1f9f9b76fbbb408d9c16fd183
ms.sourcegitcommit: d5f841744b716fcf368c670009b61441f5a5eed2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2018
ms.locfileid: "27210192"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="9f3e6-103">コンテンツの場所のエラーを解決するのにはコンテンツの検索を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="9f3e6-104">非常に多数の (たとえば、100,000 のメールボックスまたは 1 つのコンテンツ検索では、複数の検索など) のメールボックスを検索するのには Office 365 のセキュリティとコンプライアンス ・ センター内のコンテンツの検索を使用する場合、次のような検索エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-104">When you use Content Search in the Office 365 Security & Compliance Center to search a very large number of mailboxes (for example, searching 100,000 mailboxes or more in a single Content Search), you may get search errors that are similar to the following:</span></span>

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="9f3e6-p101">特定コンテンツの場所を検索するコンテンツの検索が失敗したことを示すこれらのエラー (CS008 009 と CS012 002 のエラー コード)この例では、2 つのメールボックスが検索されませんでした。コンテンツの検索のステータス詳細ポップアップ ページでは、これらのエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-p101">These errors (with error codes of CS008-009 and CS012-002) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched. These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="9f3e6-107">コンテンツの場所のエラーの原因</span><span class="sxs-lookup"><span data-stu-id="9f3e6-107">Cause of content location errors</span></span>

<span data-ttu-id="9f3e6-p102">多数のメールボックスを検索する場合は、検索が何千もの Microsoft のデータ センター内のサーバーに分散されます。どの時点においても 1 つの再起動状態または冗長なコピーへのフェイル オーバー中に特定のサーバー可能性があります。データを取得するためのコンテンツの検索の要求では、これらのケースのいずれか、タイムアウトになります。前の例では、失敗したメールボックスのエラーは検索のタイムアウトの結果でした。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-p102">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter. At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies. In either of these cases, the Content Search's request to retrieve data will timeout. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="9f3e6-112">コンテンツの場所のエラーの解決</span><span class="sxs-lookup"><span data-stu-id="9f3e6-112">Resolving content location errors</span></span>

<span data-ttu-id="9f3e6-p103">検索を再起動することがよくありますエラーが発生のような別のサーバーにします。検索を再起動するには、代わりに、検索結果ページの上部に表示される [**再試行**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-p103">Restarting the search will often result in similar errors on different servers. Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![コンテンツの場所のエラーを解決するのには [再試行] ボタンをクリックします。](media/retrycontentsearch3.png)

<span data-ttu-id="9f3e6-p104">失敗したメールボックスに対してのみ、検索を再試行して、これが発生します。検索を再試行すると正常に返されたその他の結果は保持されます。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-p104">This will result in the retrying the search only for the mailboxes that failed. When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="9f3e6-118">コンテンツの場所のエラーを回避するためのヒント</span><span class="sxs-lookup"><span data-stu-id="9f3e6-118">Tips to avoid content location errors</span></span>

<span data-ttu-id="9f3e6-119">多数のメールボックスを検索するときに、それらを回避するためには、追加コンテンツの場所のエラーの原因の一部といくつかのヒントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-119">Here are some addition causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="9f3e6-p105">検索対象のメールボックスは、ユーザー操作のためビジー状態である可能性があります。この例では、検索サービスでは、自身のメールボックスが使用できなくなることを防ぐためスロットル可能性があります。これを回避するには、業務時間外に検索を実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-p105">The mailbox being searched might be busy due to user activity. In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable. To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="9f3e6-p106">メールボックスからは、検索クエリをコンテンツが多すぎて取得する可能性があります。可能な場合は、キーワード、日付の範囲、および検索条件を使用して、検索範囲を絞り込むためにしてみてください。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-p106">The search query might be retrieving too much content from the mailbox. If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="9f3e6-p107">多すぎるキーワードまたはキーフレーズ[キーワード リスト](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)を使用して検索クエリを作成するとします。キーワード リストを使用する検索クエリを実行するとサービス本質的に実行行ごとに別の検索キーワードの一覧で統計情報を生成できるようにします。検索クエリで、[キーワード] ボックスの一覧を使用する場合、[キーワード] ボックスの一覧で行の数を最小限に抑えるより小さいリストに番号のキーワードを分割、各キーワードの一覧の別の検索を作成</span><span class="sxs-lookup"><span data-stu-id="9f3e6-p107">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated. If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9f3e6-128">大規模なキーワード リストに起因する問題を低減する手助けとする場合のキーワードの一覧での検索クエリの 20 行の最大数に制限されます。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-128">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="9f3e6-p108">多くの検索を同時に同じメールボックスで実行されます。可能であれば、1 つの任意のメールボックスに一度に 1 つの検索を実行する実行してください。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-p108">Too many searches are being performed on the same mailbox at the same time. If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="9f3e6-p109">1 つの検索に多数のメールボックスを検索しています。コンテンツの場所のエラーの確率は、非常に多数のメールボックスを検索するときに増加します。可能であれば、各検索には、組織内のメールボックスのサブセットが含まれていますので、複数の検索を実行する実行してください。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-p109">Searching too many mailboxes in a single search. The probability of content location errors increases when searching a very large number of mailboxes. If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="9f3e6-p110">メールボックスに必要なメンテナンスを実行しています。この原因が頻繁に発生する可能性があります、ただしは、コンテンツの場所のエラーを受け取った後、少し待ってから、検索を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="9f3e6-p110">Required maintenance is being performed on the mailbox. Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
