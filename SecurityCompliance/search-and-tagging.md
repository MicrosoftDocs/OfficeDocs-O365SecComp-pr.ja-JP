---
title: 検索とタグ付け
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 高度な電子的証拠開示、検索し、名札管理モジュールを使用すると、検索、プレビュー、および、ケース内のドキュメントを整理できます。現時点では、このモジュールは、ベータ版です。
ms.openlocfilehash: 013e559ca55e9a877dfb2f8747c4696f81e1e095
ms.sourcegitcommit: 25f1028643d8a20d17306e8b09cafea46eaf7a58
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2019
ms.locfileid: "29666147"
---
# <a name="search-and-tagging"></a><span data-ttu-id="c4dec-104">検索とタグ付け</span><span class="sxs-lookup"><span data-stu-id="c4dec-104">Search and Tagging</span></span>

<span data-ttu-id="c4dec-p102">高度な電子的証拠開示、検索し、名札管理モジュールを使用すると、検索、プレビュー、および、ケース内のドキュメントを整理できます。現時点では、このモジュールは、ベータ版です。検索とタグ付けの簡単なデモでは、[高度な電子的証拠開示を使用してデータの管理](https://www.youtube.com/watch?v=VaPYL3DHP6I)のビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4dec-p102">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta. For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="c4dec-p103">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="c4dec-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="c4dec-110">場合、ドキュメントを検索します。</span><span class="sxs-lookup"><span data-stu-id="c4dec-110">Search the documents in your case</span></span>

<span data-ttu-id="c4dec-p104">した後、高度な電子的証拠開示のケース内のドキュメントの処理 (分析や関連性のモジュールを必要に応じて実行)、ドキュメントを検索し、(ラベルとも呼ばれます) に固有の大文字と小文字のタグを適用することによって整理を検索し、名札を使用できます。指定された条件のカードを使用して検索クエリを定義したり、キーワードで KQL のようなクエリ言語を使用して、カードの条件します。AND、OR、NOT などの一般的な KQL 構文はサポートされていると同様に後続複数文字のワイルドカード (\*)、NEAR(n) とします。</span><span class="sxs-lookup"><span data-stu-id="c4dec-p104">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels). You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="c4dec-p105">KQL キーワード クエリを使用するために検索可能なプロパティを次の表に一覧します。代わりに、検索クエリ (選択したプロパティ) の条件を追加するのには、高度な電子的証拠開示検索ツールでの条件のカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4dec-p105">The following table lists the properties that you can search for using a KQL keyword query. Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="c4dec-116">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="c4dec-116">**Property**</span></span>|<span data-ttu-id="c4dec-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="c4dec-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c4dec-118">**caselabel**</span><span class="sxs-lookup"><span data-stu-id="c4dec-118">**caselabel**</span></span> <br/> | <span data-ttu-id="c4dec-119">文書をタグ付けするときに作成/適用するタグの名前。</span><span class="sxs-lookup"><span data-stu-id="c4dec-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="c4dec-120">**保管担当者**</span><span class="sxs-lookup"><span data-stu-id="c4dec-120">**custodian**</span></span> <br/> | <span data-ttu-id="c4dec-121">ドキュメントに関連付けられている保管担当者制限にさらされます。</span><span class="sxs-lookup"><span data-stu-id="c4dec-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="c4dec-122">**日付**</span><span class="sxs-lookup"><span data-stu-id="c4dec-122">**date**</span></span> <br/> | <span data-ttu-id="c4dec-123">送信日時のメールです。サイトのドキュメントの変更された日付です。</span><span class="sxs-lookup"><span data-stu-id="c4dec-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="c4dec-124">**ファイル id**</span><span class="sxs-lookup"><span data-stu-id="c4dec-124">**fileid**</span></span> <br/> | <span data-ttu-id="c4dec-125">ケース内のファイル ID です。</span><span class="sxs-lookup"><span data-stu-id="c4dec-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="c4dec-126">**ファイルの種類**</span><span class="sxs-lookup"><span data-stu-id="c4dec-126">**filetype**</span></span> <br/> | <span data-ttu-id="c4dec-127">ネイティブ ファイルの拡張子。</span><span class="sxs-lookup"><span data-stu-id="c4dec-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="c4dec-128">**fileclass**</span><span class="sxs-lookup"><span data-stu-id="c4dec-128">**fileclass**</span></span> <br/> | <span data-ttu-id="c4dec-129">電子メール、ドキュメント、または添付ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c4dec-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="c4dec-130">**senderauthor**</span><span class="sxs-lookup"><span data-stu-id="c4dec-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="c4dec-131">送信者の電子メールです。サイトのドキュメントの作成者です。</span><span class="sxs-lookup"><span data-stu-id="c4dec-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="c4dec-132">**サイズ**</span><span class="sxs-lookup"><span data-stu-id="c4dec-132">**size**</span></span> <br/> | <span data-ttu-id="c4dec-133">KB のファイルのサイズ。</span><span class="sxs-lookup"><span data-stu-id="c4dec-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="c4dec-134">**subjecttitle**</span><span class="sxs-lookup"><span data-stu-id="c4dec-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="c4dec-135">電子メールの件名サイトのドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="c4dec-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="c4dec-136">**Bcc**</span><span class="sxs-lookup"><span data-stu-id="c4dec-136">**bcc**</span></span> <br/> | <span data-ttu-id="c4dec-137">電子メールの Bcc フィールドです。</span><span class="sxs-lookup"><span data-stu-id="c4dec-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="c4dec-138">**Cc**</span><span class="sxs-lookup"><span data-stu-id="c4dec-138">**cc**</span></span> <br/> | <span data-ttu-id="c4dec-139">電子メールの Cc フィールドです。</span><span class="sxs-lookup"><span data-stu-id="c4dec-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="c4dec-140">**参加者**</span><span class="sxs-lookup"><span data-stu-id="c4dec-140">**participants**</span></span> <br/> | <span data-ttu-id="c4dec-141">無効なリンクを含む、電子メール スレッドのすべての参加者の電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="c4dec-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="c4dec-142">**受信しました**</span><span class="sxs-lookup"><span data-stu-id="c4dec-142">**received**</span></span> <br/> | <span data-ttu-id="c4dec-143">電子メールが受信された日付。</span><span class="sxs-lookup"><span data-stu-id="c4dec-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="c4dec-144">**受信者**</span><span class="sxs-lookup"><span data-stu-id="c4dec-144">**recipients**</span></span> <br/> | <span data-ttu-id="c4dec-145">宛先、Cc、または Bcc のフィールドには、電子メールの受信者が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4dec-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="c4dec-146">**送信者**</span><span class="sxs-lookup"><span data-stu-id="c4dec-146">**sender**</span></span> <br/> | <span data-ttu-id="c4dec-147">電子メールの送信者です。</span><span class="sxs-lookup"><span data-stu-id="c4dec-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="c4dec-148">**lastmodifieddate**</span><span class="sxs-lookup"><span data-stu-id="c4dec-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="c4dec-149">最終では、サイトのドキュメントの日付を変更します。</span><span class="sxs-lookup"><span data-stu-id="c4dec-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="c4dec-150">**送信**</span><span class="sxs-lookup"><span data-stu-id="c4dec-150">**sent**</span></span> <br/> | <span data-ttu-id="c4dec-151">電子メールの送信日。</span><span class="sxs-lookup"><span data-stu-id="c4dec-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="c4dec-152">**宛先**</span><span class="sxs-lookup"><span data-stu-id="c4dec-152">**to**</span></span> <br/> | <span data-ttu-id="c4dec-153">受信する電子メールの [宛先] フィールドに記載されています。</span><span class="sxs-lookup"><span data-stu-id="c4dec-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="c4dec-154">**作成者**</span><span class="sxs-lookup"><span data-stu-id="c4dec-154">**author**</span></span> <br/> | <span data-ttu-id="c4dec-155">サイトのドキュメントの作成者です。</span><span class="sxs-lookup"><span data-stu-id="c4dec-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="c4dec-156">**title**</span><span class="sxs-lookup"><span data-stu-id="c4dec-156">**title**</span></span> <br/> | <span data-ttu-id="c4dec-157">サイトのドキュメントのタイトルです。</span><span class="sxs-lookup"><span data-stu-id="c4dec-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="c4dec-158">**dominanttheme**\*</span><span class="sxs-lookup"><span data-stu-id="c4dec-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="c4dec-159">アイテムの優先度の高いテーマです。</span><span class="sxs-lookup"><span data-stu-id="c4dec-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="c4dec-160">**themeslist**\*</span><span class="sxs-lookup"><span data-stu-id="c4dec-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="c4dec-161">アイテムに関連付けられているテーマです。</span><span class="sxs-lookup"><span data-stu-id="c4dec-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="c4dec-162">**readpercentile_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="c4dec-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="c4dec-163">[Issuenum] で定義されている現象で、アイテムの読み取りの百分位です。</span><span class="sxs-lookup"><span data-stu-id="c4dec-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="c4dec-164">**relevancescore_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="c4dec-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="c4dec-165">[Issuenum] で定義されている現象で、アイテムの関連性スコアです。</span><span class="sxs-lookup"><span data-stu-id="c4dec-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="c4dec-166">**relevancetag_ [tagname]**\*\*</span><span class="sxs-lookup"><span data-stu-id="c4dec-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="c4dec-167">項目がある場合手動でタグが付けられて、[タグ名] で定義されているタグの関連性について。</span><span class="sxs-lookup"><span data-stu-id="c4dec-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="c4dec-168">\*テーマ モジュールが実行された場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4dec-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="c4dec-169">\*\*関連モジュールが実行された場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4dec-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="c4dec-p106">代わりに、検索クエリ (選択したプロパティ) の条件を追加するのには、高度な電子的証拠開示検索ツールの条件のカードを使用できます。次のスクリーン ショットは、クエリに追加できる条件を示しています。**[グループ**] 列では、電子メール、サイトのドキュメント、または両方 (*共通*の値で示されます) にプロパティが適用されるかどうかを示します。この列は、関連性の高いモジュールを実行した後に表示される検索可能なプロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="c4dec-p106">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query. The following screenshot shows the conditions that can be added to a query. The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*). This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![高度な電子的証拠開示検索ツールで検索条件](media/AeDSearchConditions.png)

<span data-ttu-id="c4dec-175">検索可能なプロパティの詳細については、[キーワード クエリと検索条件](keyword-queries-and-search-conditions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4dec-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4dec-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4dec-176">See also</span></span>

[<span data-ttu-id="c4dec-177">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c4dec-177">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c4dec-178">関連性の評価を理解します。</span><span class="sxs-lookup"><span data-stu-id="c4dec-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c4dec-179">タグ付けおよび評価</span><span class="sxs-lookup"><span data-stu-id="c4dec-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c4dec-180">タグ付けと関連性の高いトレーニング</span><span class="sxs-lookup"><span data-stu-id="c4dec-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c4dec-181">追跡の関連性の分析</span><span class="sxs-lookup"><span data-stu-id="c4dec-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c4dec-182">結果に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="c4dec-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c4dec-183">テストの関連性の分析</span><span class="sxs-lookup"><span data-stu-id="c4dec-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

