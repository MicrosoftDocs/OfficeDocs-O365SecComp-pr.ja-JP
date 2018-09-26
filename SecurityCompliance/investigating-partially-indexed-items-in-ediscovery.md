---
title: Office 365 の電子情報開示で部分的にインデックスが作成されたアイテムを調査する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 一部の項目をインデックス (インデックス付けされない呼び出しの項目も) は、Exchange メールボックスのアイテムと SharePoint のドキュメントと OneDrive のサイトが何らかの理由がコンテンツの検索用にインデックス完全にいなかったのです。この記事で項目が検索用インデックスを作成することはできず、部分的にインデックス付きの項目として返される理由を説明、部分的にインデックス付きのアイテムの検索エラーを識別して PowerShell スクリプトを使用して、部分的にインデックス付きの電子メールを組織のリスクを判断するのにはアイテムです。
ms.openlocfilehash: 98f794e80ea8a6016887ff139bc5b546c438f093
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038080"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a><span data-ttu-id="29da3-104">Office 365 の電子情報開示で部分的にインデックスが作成されたアイテムを調査する</span><span class="sxs-lookup"><span data-stu-id="29da3-104">Investigating partially indexed items in Office 365 eDiscovery</span></span>

<span data-ttu-id="29da3-p102">Office 365 のセキュリティを実行するコンテンツの検索&amp;コンプライアンス センターが検索を実行すると、予定の検索結果に部分的にインデックス付きのアイテムが自動的に含まれます。部分的にインデックス付きのアイテムは、Exchange メールボックスのアイテムを何らかの理由により検索用インデックスが作成されなかった完全にビジネス サイトの SharePoint と OneDrive のドキュメントです。[電子メール メッセージのインデックス作成の制限](limits-for-content-search.md#indexinglimits)内に収まっているために、ほとんどの電子メール メッセージおよびサイトのドキュメントが正常にインデックスします。ただし、いくつかの項目は、これらのインデックスの制限を超える可能性がありますが部分的にインデックスを作成します。アイテムの検索用インデックスを作成できない理由とは、コンテンツの検索を実行すると、部分的にインデックス付きの項目として返されます、その他の理由を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="29da3-p102">A Content Search that you run from the Office 365 Security &amp; Compliance Center automatically includes partially indexed items in the estimated search results when you run a search. Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search. Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexinglimits). However, some items may exceed these indexing limits, and will be partially indexed. Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="29da3-110">電子メール メッセージがある添付ファイルの種類のファイルのインデックスを作成することはできません。ほとんどの場合、ファイルの種類は[認識されない、またはインデックス作成でサポートされていません](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="29da3-110">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="29da3-111">イメージ ファイルの有効なハンドラーがない場合、添付ファイルがある電子メール メッセージこれは、部分的にインデックス付きの電子メール アイテムの最も一般的な原因</span><span class="sxs-lookup"><span data-stu-id="29da3-111">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="29da3-112">電子メール メッセージに添付ファイルが多すぎます</span><span class="sxs-lookup"><span data-stu-id="29da3-112">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="29da3-113">電子メール メッセージの添付ファイルが大きすぎます</span><span class="sxs-lookup"><span data-stu-id="29da3-113">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="29da3-114">インデックス作成のためにファイルの種類がサポートされていますが、特定のファイルのインデックス作成エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29da3-114">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="29da3-p103">さまざまですが、部分的にインデックスが設定されたサイズでボリュームと内容の 12% 未満でコンテンツの 1% 未満の場合がある Office 365 の組織のほとんどのお客様です。ボリュームとサイズの違いの理由は、サイズの大きいファイルの完全にインデックスを作成できないコンテンツが含まれている可能性が高くです。</span><span class="sxs-lookup"><span data-stu-id="29da3-p103">Although it varies, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed. The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="29da3-117">部分的にインデックス付きのアイテム数は、検索、なぜ変更しますか。</span><span class="sxs-lookup"><span data-stu-id="29da3-117">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="29da3-p104">Office 365 のセキュリティ コンテンツの検索を実行した後&amp;コンプライアンス センターの合計数、検索された場所に部分的にインデックス付きの項目のサイズは、「検索結果統計の詳細な統計情報に表示される検索します。検索の統計情報の*項目のインデックスを持たない*呼ばれますを注意してください。検索結果に返される部分的にインデックス付きのアイテムの数に影響を与えることがいくつかを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="29da3-p104">After you run a Content Search in the Office 365 Security &amp; Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search. Note these are called  *unindexed items*  in the search statistics. Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="29da3-p105">アイテムのインデックスは部分的に、検索クエリに一致する場合、カウント (とサイズ) の検索結果の項目と部分的にインデックス付きの項目に含まれます。ただし、同じ検索結果がエクスポートされると、アイテムが検索結果のセットにのみ付属それが部分的にインデックス付きの項目として含まれていません。</span><span class="sxs-lookup"><span data-stu-id="29da3-p105">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items. However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="29da3-p106">(キーワード クエリでそれを含む) や条件を使用して検索クエリの日付範囲を指定すると、日付の範囲に一致しない一部のインデックス付きの項目が部分的にインデックス付きの項目の数に含まれていません。部分的にインデックス付きの項目の数には、日付の範囲内に含まれる部分的にインデックス付きのアイテムのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="29da3-p106">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items. Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="29da3-p107">**注:** 部分的にインデックス付きのアイテムを SharePoint に配置し、OneDrive のサイト*は*検索の詳細な統計情報に表示されている部分的にインデックス付きの項目の見積もりに含まれています。ただし、コンテンツの検索結果をエクスポートする場合は、部分的にインデックス付きのアイテムをエクスポートできます。たとえば、のみを検索する場合のサイト コンテンツの検索、推定数に部分的にインデックス付きの項目は 0 にします。</span><span class="sxs-lookup"><span data-stu-id="29da3-p107">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search. However, partially indexed items can be exported when you export the results of a Content Search. For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="29da3-128">組織内で部分的にインデックス付きの項目の比率を計算します。</span><span class="sxs-lookup"><span data-stu-id="29da3-128">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="29da3-p108">(クエリを使用して空白のキーワード) 部分的にインデックス付きの項目の組織のリスクを理解するため、すべてのメールボックス内のすべてのコンテンツを検索を実行できます。56,208 (4,830 MB) がある、次の例で完全なアイテム、470 (316 MB) のインデックスを作成インデックス項目の一部です。</span><span class="sxs-lookup"><span data-stu-id="29da3-p108">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query). In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![部分的にインデックス作成済みアイテムの検索の統計情報の表示の例](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="29da3-132">次の計算を使用して部分的にインデックス付きの項目のパーセンテージを指定できます。</span><span class="sxs-lookup"><span data-stu-id="29da3-132">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="29da3-133">**組織内で部分的にインデックス付きの項目の比率を計算します。**</span><span class="sxs-lookup"><span data-stu-id="29da3-133">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="29da3-134">前の例では、検索結果を使用しています。 すべてのメールボックス アイテムの 84% が部分的にインデックス付けします。</span><span class="sxs-lookup"><span data-stu-id="29da3-134">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="29da3-135">**組織内で部分的にインデックス付きのアイテムのサイズの割合を計算します。**</span><span class="sxs-lookup"><span data-stu-id="29da3-135">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="29da3-p109">前の例では、メールボックスのアイテムの合計サイズの 6.54%、部分的にインデックス付きのアイテムです。述べたように、ほとんどの Office 365 組織を部分的にインデックスが設定されたサイズでボリュームと内容の 12% より小さく、コンテンツの 1% 未満の場合があるお客様。</span><span class="sxs-lookup"><span data-stu-id="29da3-p109">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items. As previously stated, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="29da3-138">インデックス作成済みアイテムを部分的に使用</span><span class="sxs-lookup"><span data-stu-id="29da3-138">Working with partially indexed items</span></span>

<span data-ttu-id="29da3-p110">場合は部分的に関連情報が含まれているは、[コンテンツの検索レポートをエクスポート](export-a-content-search-report.md)することができますを検証するために項目を確認する必要があるとき部分的にインデックス付きの項目に関する情報を格納します。コンテンツの検索レポートをエクスポートする場合は、部分的にインデックス付きのアイテムを含む、エクスポート オプションのいずれかを選択してください。</span><span class="sxs-lookup"><span data-stu-id="29da3-p110">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items. When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![部分的にインデックス付きのアイテムをエクスポートするのには、2 番目または 3 番目のオプションを選択します。](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="29da3-p111">コンテンツの検索結果、またはこれらのオプションのいずれかを使用してコンテンツの検索、レポートをエクスポートする場合、エクスポートには、インデックス Items.csv をという名前のレポートが含まれています。このレポートには、ResultsLog.csv ファイルと同じ情報のほとんどが含まれています。ただし、インデックス付けされない Items.csv ファイルも含まれる部分的にインデックス付きのアイテムに関連する 2 つのフィールド:**エラー タグ**および**プロパティのエラー**です。これらのフィールドには、部分的にインデックス付きの各項目のインデックス作成のエラーに関する情報が含まれています。これら 2 つのフィールドに情報を使用すると、特定のインデックス作成のエラーの調査に影響を与えるかどうかを判断することができます。場合は、対象となるコンテンツの検索を実行して取得して調査に関連するかを決定することを確認することができますように、特定の電子メール メッセージ、および SharePoint または OneDrive のドキュメントをエクスポートできます。手順については、 [Office 365 のコンテンツ検索の対象となる CSV ファイルの準備](csv-file-for-an-id-list-content-search.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29da3-p111">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv. This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**. These fields contain information about the indexing error for each partially indexed item. Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation. If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation. For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="29da3-p112">**注:** インデックス付けされない Items.csv ファイルには、**エラーの種類**と、**エラー メッセージ**という名前のフィールドも含まれています。これらは、あまり詳細な情報が、**タグのエラー**および**エラーのプロパティ**のフィールドに情報を次のような情報が含まれている従来のフィールドです。従来のこれらのフィールドは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="29da3-p112">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**. These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information. You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="29da3-151">部分的にインデックス付きのアイテムに関連するエラー</span><span class="sxs-lookup"><span data-stu-id="29da3-151">Errors related to partially indexed items</span></span>

<span data-ttu-id="29da3-p113">エラー タグは、2 つの情報、エラー、およびファイルの種類で構成されています。: このエラーとファイルの種類の組み合わせで、</span><span class="sxs-lookup"><span data-stu-id="29da3-p113">Error tags are made up of two pieces of information, the error and the file type. For example, in this error/filetype pair:</span></span>

```
 parseroutputsize_xls
```

   
 <span data-ttu-id="29da3-p114">`parseroutputsize`エラーと`xls`は、エラーが発生したファイルのファイルの種類。されたファイルの種類が認識されなかったか、ファイルの種類の場合は適用されません、エラー値が表示されます`noformat`ファイルの種類の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="29da3-p114">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on. In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="29da3-156">エラーとエラーの原因の説明のインデックスの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="29da3-156">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="29da3-157">**エラー タグ**</span><span class="sxs-lookup"><span data-stu-id="29da3-157">**Error tag**</span></span>|<span data-ttu-id="29da3-158">**説明**</span><span class="sxs-lookup"><span data-stu-id="29da3-158">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="29da3-159">電子メール メッセージ、添付ファイルが多すぎる、これらの添付ファイルの一部が処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="29da3-159">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="29da3-p115">コンテンツの取得元とドキュメントのパーサーでは、添付ファイルの他の添付ファイルの入れ子のレベルが多すぎるが見つかりました。これらの添付ファイルの一部は処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="29da3-p115">The content retriever and document parser found too many levels of attachments nested inside other attachments. Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="29da3-162">添付ファイルは、RM で保護されたためにデコードできませんでした。</span><span class="sxs-lookup"><span data-stu-id="29da3-162">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="29da3-163">電子メール メッセージの添付ファイルが大きすぎて、処理することができませんでした。</span><span class="sxs-lookup"><span data-stu-id="29da3-163">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="29da3-p116">インデックス処理された電子メール メッセージを作成する場合、インデックス付け可能なプロパティの 1 つが大きすぎます、切り捨てられました。切り捨てられたプロパティは、エラー プロパティ フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="29da3-p116">When writing the processed email message to the index, one of the indexable properties was too large and was truncated. The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="29da3-p117">電子メール メッセージには、有効な Unicode として処理することができませんでしたのテキストが含まれています。このアイテムのインデックス作成になりません。</span><span class="sxs-lookup"><span data-stu-id="29da3-p117">An email message contained text that couldn't be processed as valid Unicode. Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="29da3-168">添付ファイルまたは電子メール メッセージの内容が暗号化され、Office 365 は、コンテンツをデコードできませんでした。</span><span class="sxs-lookup"><span data-stu-id="29da3-168">The content of attachment or email message is encrypted, and Office 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="29da3-p118">解析中に不明なエラーが発生しました。通常、この結果から、ソフトウェアのバグ、またはサービスがクラッシュします。</span><span class="sxs-lookup"><span data-stu-id="29da3-p118">An unknown error occurred during parsing. This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="29da3-171">を処理するパーサーの添付ファイルが大きすぎます、その添付ファイルの解析は見られませんでしたが終了しませんでした。</span><span class="sxs-lookup"><span data-stu-id="29da3-171">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="29da3-p119">添付ファイルは、形式が正しくないし、パーサーによって処理されることができませんでした。互換性のないソフトウェアは、またはを装って何かを要求した以外のウイルスによって作成されたファイルは古いファイルからこの結果が書式設定します。</span><span class="sxs-lookup"><span data-stu-id="29da3-p119">An attachment was malformed and couldn't be handled by the parser. This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="29da3-174">添付ファイルの解析からの出力が大きすぎて、トランケートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29da3-174">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="29da3-175">添付ファイルには、Office 365 を検出できませんでした。 ファイルの種類が必要があります。</span><span class="sxs-lookup"><span data-stu-id="29da3-175">An attachment had a file type that Office 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="29da3-176">添付ファイルには、Office 365could の検出がサポートされていないファイルの種類を解析するファイルの種類が必要があります。</span><span class="sxs-lookup"><span data-stu-id="29da3-176">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="29da3-p120">電子メールのプロパティの値を Exchange ストアが取得するには大きすぎると、メッセージを処理できませんでした。これは通常のみ発生、電子メール メッセージの本文のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="29da3-p120">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed. This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="29da3-179">コンテンツの取得元は、RM で保護されたメッセージをデコードできませんでした。</span><span class="sxs-lookup"><span data-stu-id="29da3-179">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="29da3-p121">インデックス作成時にドキュメントに多くの語句が確認されました。、上限に達すると、プロパティの処理が停止しているし、プロパティが切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="29da3-p121">Too many words were identified in the document during indexing. Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="29da3-p122">エラー フィールドは、フィールドの影響を受けるエラー タグ] フィールドに表示されている処理エラーについて説明します。プロパティを次のように検索する場合は`subject`または`participants`、エラー メッセージの本文ではありません、検索の結果に影響を与えます。これは、さらに調査する必要があります正確に部分的にインデックス付けされた項目を決定する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="29da3-p122">Error fields describe which fields are affected by the processing error listed in the Error Tags field. If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search. This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="29da3-185">PowerShell スクリプトを使用して部分的にインデックス付きの電子メール アイテムの組織のリスクを決定するには</span><span class="sxs-lookup"><span data-stu-id="29da3-185">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="29da3-p123">次の手順を表示するすべての Exchange メールボックス内のすべてのアイテムを検索 (数とサイズで)、組織の部分的にインデックス付きの電子メール アイテムの比率に関するレポートが生成され、アイテムの数を表示する PowerShell スクリプトを実行する方法 (およびファイルの種類) の各インデックスに発生するエラーです。前のセクションでエラー タグの説明を使用すると、インデックス作成のエラーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="29da3-p123">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs. Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="29da3-188">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `PartiallyIndexedItems.ps1`。</span><span class="sxs-lookup"><span data-stu-id="29da3-188">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

```
  write-host "**************************************************"
  write-host "     Office 365 Security &amp; Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```
   
2. <span data-ttu-id="29da3-189">[Office 365 のセキュリティへの接続&amp;コンプライアンス センター PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。</span><span class="sxs-lookup"><span data-stu-id="29da3-189">[Connect to Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="29da3-190">セキュリティで&amp;コンプライアンス センター、手順 1 のスクリプトの保存先フォルダーに移動して、スクリプトを実行し、例えば：</span><span class="sxs-lookup"><span data-stu-id="29da3-190">In Security &amp; Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
<span data-ttu-id="29da3-191">例/fo オプション、スクリプトによって返される出力します。</span><span class="sxs-lookup"><span data-stu-id="29da3-191">Here's an example fo the output returned by the script.</span></span>
  
![部分的にインデックス付きの電子メール アイテムの組織のリスクに関するレポートを生成するスクリプトからの出力の例](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="29da3-193">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="29da3-193">Note the following:</span></span>
  
1. <span data-ttu-id="29da3-194">総数と、電子メール アイテムのサイズと、組織の (数とサイズで)、部分的にインデックス付きの電子メール アイテムの比率</span><span class="sxs-lookup"><span data-stu-id="29da3-194">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="29da3-195">リストのエラー タグと対応するファイルの種類のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29da3-195">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="29da3-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="29da3-196">See also</span></span>

[<span data-ttu-id="29da3-197">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="29da3-197">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
