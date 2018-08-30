---
title: 検索とタグ付け
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 高度な電子的証拠開示、検索し、名札管理モジュールを使用すると、検索、プレビュー、および、ケース内のドキュメントを整理できます。現時点では、このモジュールは、ベータ版です。
ms.openlocfilehash: fde887e496e9a40aa88d841053a0c66e48f04200
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532229"
---
# <a name="search-and-tagging"></a><span data-ttu-id="1d113-104">検索とタグ付け</span><span class="sxs-lookup"><span data-stu-id="1d113-104">Search and Tagging</span></span>

<span data-ttu-id="1d113-p102">高度な電子的証拠開示、検索し、名札管理モジュールを使用すると、検索、プレビュー、および、ケース内のドキュメントを整理できます。現時点では、このモジュールは、ベータ版です。</span><span class="sxs-lookup"><span data-stu-id="1d113-p102">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta.</span></span>

> [!NOTE]
> <span data-ttu-id="1d113-p103">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="1d113-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="1d113-109">場合、ドキュメントを検索します。</span><span class="sxs-lookup"><span data-stu-id="1d113-109">Search the documents in your case</span></span>

<span data-ttu-id="1d113-p104">高度な電子的証拠開示のドキュメントを処理すると、分析モジュール、または関連性の高いモジュールを必要に応じて実行する、検索を使用することができ、名札ケース内のドキュメントを検索し、それらを整理する場合に固有のタグを使用しています。指定された条件のカードを使用するクエリを定義したり、カードの条件を [キーワード] KQL のようなクエリ言語を使用してできます。AND、OR、NOT などの一般的な KQL 構文はサポートされていると同様に後続複数文字のワイルドカード (\*)、NEAR(n) とします。クエリ言語のプロパティ名では、これらのプロパティがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1d113-p104">Once you have processed documents in Advanced eDiscovery and optionally run the Analyze module or the Relevance module, you can use Search and Tagging to search through the documents in the case and organize them using case-specific tags. You can define your queries using the provided condition cards, or through a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*). These properties are supported in the query language property name:</span></span>

- <span data-ttu-id="1d113-114">caselabel: このサポート案件の検索し、名札の作成と適用される同じタグ</span><span class="sxs-lookup"><span data-stu-id="1d113-114">caselabel: tags created/applied in Search and Tagging for this case</span></span> 
- <span data-ttu-id="1d113-115">通告: 制限の場合は、割り当てられている通告</span><span class="sxs-lookup"><span data-stu-id="1d113-115">custodians: custodians assigned in the case - subject to limitations</span></span>
- <span data-ttu-id="1d113-116">日付: 送信メールの日付、ドキュメントの日付を変更します。</span><span class="sxs-lookup"><span data-stu-id="1d113-116">date: sent date for email, modified date for documents</span></span>
- <span data-ttu-id="1d113-117">ファイル id: ファイル ID の大文字と小文字の</span><span class="sxs-lookup"><span data-stu-id="1d113-117">fileid: file ID within the case</span></span>
- <span data-ttu-id="1d113-118">ファイルの種類: ネイティブのファイルの拡張子</span><span class="sxs-lookup"><span data-stu-id="1d113-118">filetype: native file extension</span></span>
- <span data-ttu-id="1d113-119">fileclass: 電子メール、ドキュメント、または添付ファイル</span><span class="sxs-lookup"><span data-stu-id="1d113-119">fileclass: email, document, or attachment</span></span>
- <span data-ttu-id="1d113-120">senderauthor: 送信者の e メール、ドキュメントの作成者</span><span class="sxs-lookup"><span data-stu-id="1d113-120">senderauthor: sender for emails, author for documents</span></span>
- <span data-ttu-id="1d113-121">サイズ: KB のファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="1d113-121">size: size of the file in KB</span></span>
- <span data-ttu-id="1d113-122">subjecttitle: 電子メールの場合、ドキュメントのタイトルは件名</span><span class="sxs-lookup"><span data-stu-id="1d113-122">subjecttitle: subject for emails, title for documents</span></span>
- <span data-ttu-id="1d113-123">Bcc</span><span class="sxs-lookup"><span data-stu-id="1d113-123">bcc</span></span>
- <span data-ttu-id="1d113-124">Cc</span><span class="sxs-lookup"><span data-stu-id="1d113-124">cc</span></span>
- <span data-ttu-id="1d113-125">参加者: 無効なリンクを含む、電子メール スレッドのすべての参加者のアドレスを電子メールで送信</span><span class="sxs-lookup"><span data-stu-id="1d113-125">participants: Email addresses of all participants in an email thread, including for missing links</span></span>
- <span data-ttu-id="1d113-126">受信: 受信日</span><span class="sxs-lookup"><span data-stu-id="1d113-126">received: received date</span></span>
- <span data-ttu-id="1d113-127">宛先: 受信者の名前またはアドレス (宛先、cc、bcc) の電子メールを送信</span><span class="sxs-lookup"><span data-stu-id="1d113-127">recipients: email recipient names or addresses (to, cc, bcc)</span></span>
- <span data-ttu-id="1d113-128">送信者</span><span class="sxs-lookup"><span data-stu-id="1d113-128">sender</span></span>
- <span data-ttu-id="1d113-129">lastmodifieddate: ドキュメントの日付が最終更新日</span><span class="sxs-lookup"><span data-stu-id="1d113-129">lastmodifieddate: last modified date of a document</span></span>
- <span data-ttu-id="1d113-130">送信: 送信メールの日付</span><span class="sxs-lookup"><span data-stu-id="1d113-130">sent: sent date of an email</span></span>
- <span data-ttu-id="1d113-131">から</span><span class="sxs-lookup"><span data-stu-id="1d113-131">to</span></span>
- <span data-ttu-id="1d113-132">作成者: 電子メールの作成者</span><span class="sxs-lookup"><span data-stu-id="1d113-132">author: author of an email</span></span>
- <span data-ttu-id="1d113-133">タイトル: ドキュメントのタイトル</span><span class="sxs-lookup"><span data-stu-id="1d113-133">title: title of a document</span></span>
- <span data-ttu-id="1d113-134">dominanttheme: 項目の優先度の高いテーマ\*</span><span class="sxs-lookup"><span data-stu-id="1d113-134">dominanttheme: dominant theme of an item\*</span></span>
- <span data-ttu-id="1d113-135">themeslist: 項目に関連付けられているテーマ\*</span><span class="sxs-lookup"><span data-stu-id="1d113-135">themeslist: themes that are associated with an item\*</span></span>
- <span data-ttu-id="1d113-136">readpercentile_ [issuenum]: 読み取りの問題 [issuenum] の項目には、百分位数\*\*</span><span class="sxs-lookup"><span data-stu-id="1d113-136">readpercentile_[issuenum]: read percentile of an item for issue [issuenum]\*\*</span></span>
- <span data-ttu-id="1d113-137">relevancescore_ [issuenum]: 問題 [issuenum] の項目の関連性スコア\*\*</span><span class="sxs-lookup"><span data-stu-id="1d113-137">relevancescore_[issuenum]: relevance score of an item for issue [issuenum]\*\*</span></span>
- <span data-ttu-id="1d113-138">relevancetag_ [issuenum]: [issuenum] には、そのタグの関連性の項目を手動でタグしてかどうか\*\*</span><span class="sxs-lookup"><span data-stu-id="1d113-138">relevancetag_[issuenum]: if an item has been manually tagged for relevance, its tag for [issuenum]\*\*</span></span>

<span data-ttu-id="1d113-139">\*テーマ モジュールが実行された場合にのみ使用可能な\*\*関連性の高いモジュールが実行された場合にのみ使用可能</span><span class="sxs-lookup"><span data-stu-id="1d113-139">\* Only available if the Themes module has been run \*\* Only available if the Relevance module has been run</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1d113-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d113-140">See also</span></span>

[<span data-ttu-id="1d113-141">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1d113-141">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="1d113-142">関連性の評価を理解します。</span><span class="sxs-lookup"><span data-stu-id="1d113-142">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1d113-143">タグ付けおよび評価</span><span class="sxs-lookup"><span data-stu-id="1d113-143">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1d113-144">タグ付けと関連性の高いトレーニング</span><span class="sxs-lookup"><span data-stu-id="1d113-144">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1d113-145">追跡の関連性の分析</span><span class="sxs-lookup"><span data-stu-id="1d113-145">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1d113-146">結果に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="1d113-146">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1d113-147">テストの関連性の分析</span><span class="sxs-lookup"><span data-stu-id="1d113-147">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

