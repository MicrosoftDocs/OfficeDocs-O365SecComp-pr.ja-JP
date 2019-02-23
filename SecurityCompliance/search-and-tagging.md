---
title: 検索とタグ付け
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 高度な電子情報開示では、検索とタグ付けモジュールを使用して、ケースでドキュメントを検索、プレビュー、および整理することができます。現時点では、このモジュールはベータ版です。
ms.openlocfilehash: 58913a01f30b4169470592f5fc271e3ce785ac5d
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222966"
---
# <a name="search-and-tagging"></a><span data-ttu-id="3effe-104">検索とタグ付け</span><span class="sxs-lookup"><span data-stu-id="3effe-104">Search and Tagging</span></span>

<span data-ttu-id="3effe-p102">高度な電子情報開示では、検索とタグ付けモジュールを使用して、ケースでドキュメントを検索、プレビュー、および整理することができます。現時点では、このモジュールはベータ版です。検索とタグ付けの概要については、「 [Advanced eDiscovery ビデオでデータを管理](https://www.youtube.com/watch?v=VaPYL3DHP6I)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3effe-p102">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta. For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="3effe-p103">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="3effe-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="3effe-110">ケースでドキュメントを検索する</span><span class="sxs-lookup"><span data-stu-id="3effe-110">Search the documents in your case</span></span>

<span data-ttu-id="3effe-p104">高度な電子情報開示ケースでドキュメントを処理した後 (必要に応じて Analyze または関連性モジュールを実行すると)、検索とタグ付けを使用してドキュメントを検索し、大文字と小文字を区別したタグ (ラベルとも呼ばれます) を適用することで、それらを整理することができます。検索クエリは、指定された条件カードを使用するか、またはキーワードの条件カードで kql のようなクエリ言語を使用して定義できます。and、OR、NOT、NEAR (n) などの一般的な kql 構文がサポートされています。また、末尾の複数文字ワイルドカード (\*) もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3effe-p104">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels). You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="3effe-p105">次の表に、kql キーワードクエリを使用して検索できるプロパティを示します。または、高度な電子情報開示検索ツールで条件カードを使用して、検索クエリに条件 (選択したプロパティの場合) を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="3effe-p105">The following table lists the properties that you can search for using a KQL keyword query. Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="3effe-116">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="3effe-116">**Property**</span></span>|<span data-ttu-id="3effe-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="3effe-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3effe-118">**caselabel**</span><span class="sxs-lookup"><span data-stu-id="3effe-118">**caselabel**</span></span> <br/> | <span data-ttu-id="3effe-119">文書にタグ付けするときに作成/適用されるタグの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3effe-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="3effe-120">**保管担当者**</span><span class="sxs-lookup"><span data-stu-id="3effe-120">**custodian**</span></span> <br/> | <span data-ttu-id="3effe-121">ドキュメントに関連付けられている保管担当者。制限の対象となります。</span><span class="sxs-lookup"><span data-stu-id="3effe-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="3effe-122">**状態**</span><span class="sxs-lookup"><span data-stu-id="3effe-122">**date**</span></span> <br/> | <span data-ttu-id="3effe-123">電子メールの送信日。サイトドキュメントの変更された日付。</span><span class="sxs-lookup"><span data-stu-id="3effe-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="3effe-124">**fileid**</span><span class="sxs-lookup"><span data-stu-id="3effe-124">**fileid**</span></span> <br/> | <span data-ttu-id="3effe-125">ケース内のファイル ID。</span><span class="sxs-lookup"><span data-stu-id="3effe-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="3effe-126">**filetype**</span><span class="sxs-lookup"><span data-stu-id="3effe-126">**filetype**</span></span> <br/> | <span data-ttu-id="3effe-127">ネイティブファイル拡張子。</span><span class="sxs-lookup"><span data-stu-id="3effe-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="3effe-128">**fileclass**</span><span class="sxs-lookup"><span data-stu-id="3effe-128">**fileclass**</span></span> <br/> | <span data-ttu-id="3effe-129">電子メール、ドキュメント、または添付ファイル。</span><span class="sxs-lookup"><span data-stu-id="3effe-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="3effe-130">**senderauthor**</span><span class="sxs-lookup"><span data-stu-id="3effe-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="3effe-131">電子メールの送信者。サイトドキュメントの作成者。</span><span class="sxs-lookup"><span data-stu-id="3effe-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="3effe-132">**サイズ**</span><span class="sxs-lookup"><span data-stu-id="3effe-132">**size**</span></span> <br/> | <span data-ttu-id="3effe-133">ファイルのサイズ (KB 単位)。</span><span class="sxs-lookup"><span data-stu-id="3effe-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="3effe-134">**subjecttitle**</span><span class="sxs-lookup"><span data-stu-id="3effe-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="3effe-135">電子メールの件名。サイトドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="3effe-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="3effe-136">**Bcc**</span><span class="sxs-lookup"><span data-stu-id="3effe-136">**bcc**</span></span> <br/> | <span data-ttu-id="3effe-137">電子メールの Bcc フィールド。</span><span class="sxs-lookup"><span data-stu-id="3effe-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="3effe-138">**Cc**</span><span class="sxs-lookup"><span data-stu-id="3effe-138">**cc**</span></span> <br/> | <span data-ttu-id="3effe-139">電子メールの Cc フィールド。</span><span class="sxs-lookup"><span data-stu-id="3effe-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="3effe-140">**全員**</span><span class="sxs-lookup"><span data-stu-id="3effe-140">**participants**</span></span> <br/> | <span data-ttu-id="3effe-141">電子メールスレッド内のすべての参加者の電子メールアドレス (存在しないリンクを含む)。</span><span class="sxs-lookup"><span data-stu-id="3effe-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="3effe-142">**時**</span><span class="sxs-lookup"><span data-stu-id="3effe-142">**received**</span></span> <br/> | <span data-ttu-id="3effe-143">電子メールが受信された日付。</span><span class="sxs-lookup"><span data-stu-id="3effe-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="3effe-144">**全員**</span><span class="sxs-lookup"><span data-stu-id="3effe-144">**recipients**</span></span> <br/> | <span data-ttu-id="3effe-145">[宛先]、[Cc]、または [Bcc] フィールドに含まれている電子メールの受信者。</span><span class="sxs-lookup"><span data-stu-id="3effe-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="3effe-146">**送信者**</span><span class="sxs-lookup"><span data-stu-id="3effe-146">**sender**</span></span> <br/> | <span data-ttu-id="3effe-147">電子メールの送信者。</span><span class="sxs-lookup"><span data-stu-id="3effe-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="3effe-148">**lastmodifieddate**</span><span class="sxs-lookup"><span data-stu-id="3effe-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="3effe-149">サイトドキュメントの最終更新日。</span><span class="sxs-lookup"><span data-stu-id="3effe-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="3effe-150">**送信**</span><span class="sxs-lookup"><span data-stu-id="3effe-150">**sent**</span></span> <br/> | <span data-ttu-id="3effe-151">電子メールの送信日。</span><span class="sxs-lookup"><span data-stu-id="3effe-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="3effe-152">**宛先**</span><span class="sxs-lookup"><span data-stu-id="3effe-152">**to**</span></span> <br/> | <span data-ttu-id="3effe-153">電子メールの宛先フィールドに記載されている受信者。</span><span class="sxs-lookup"><span data-stu-id="3effe-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="3effe-154">**判別**</span><span class="sxs-lookup"><span data-stu-id="3effe-154">**author**</span></span> <br/> | <span data-ttu-id="3effe-155">サイトドキュメントの作成者。</span><span class="sxs-lookup"><span data-stu-id="3effe-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="3effe-156">**title**</span><span class="sxs-lookup"><span data-stu-id="3effe-156">**title**</span></span> <br/> | <span data-ttu-id="3effe-157">サイトドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="3effe-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="3effe-158">**dominanttheme**\*</span><span class="sxs-lookup"><span data-stu-id="3effe-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="3effe-159">アイテムの主要なテーマ。</span><span class="sxs-lookup"><span data-stu-id="3effe-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="3effe-160">**テーマ一覧**\*</span><span class="sxs-lookup"><span data-stu-id="3effe-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="3effe-161">アイテムに関連付けられているテーマ。</span><span class="sxs-lookup"><span data-stu-id="3effe-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="3effe-162">**readpercentile_ [# enum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="3effe-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="3effe-163">アイテムの閲覧の百分位。 [設定] で定義されている問題を示します。</span><span class="sxs-lookup"><span data-stu-id="3effe-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="3effe-164">**relevancescore_ [# enum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="3effe-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="3effe-165">アイテムの関連性スコア。 [/設定] で定義されている問題について。</span><span class="sxs-lookup"><span data-stu-id="3effe-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="3effe-166">**relevancetag_ [tagname]**\*\*</span><span class="sxs-lookup"><span data-stu-id="3effe-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="3effe-167">関連性に対して手動でタグ付けされたアイテムの場合は、[tagname] で定義されているタグ。</span><span class="sxs-lookup"><span data-stu-id="3effe-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="3effe-168">\*Themes モジュールが実行されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3effe-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="3effe-169">\*\*関連性モジュールが実行されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3effe-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="3effe-p106">または、高度な電子情報開示検索ツールの条件カードを使用して、検索クエリに条件 (選択したプロパティの場合) を追加することもできます。次のスクリーンショットは、クエリに追加できる条件を示しています。[**グループ]** 列は、プロパティが電子メール、サイトドキュメント、またはその両方に適用されるかどうかを示します (*共通*の値で示されます)。この列は、関連性モジュールを実行した後に使用できる検索可能なプロパティも識別します。</span><span class="sxs-lookup"><span data-stu-id="3effe-p106">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query. The following screenshot shows the conditions that can be added to a query. The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*). This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![高度な電子情報開示検索ツールの検索条件](media/AeDSearchConditions.png)

<span data-ttu-id="3effe-175">検索可能なプロパティの詳細については、「[キーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3effe-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3effe-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="3effe-176">See also</span></span>

[<span data-ttu-id="3effe-177">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3effe-177">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="3effe-178">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="3effe-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3effe-179">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="3effe-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3effe-180">タグ付けと関連性トレーニング</span><span class="sxs-lookup"><span data-stu-id="3effe-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3effe-181">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="3effe-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3effe-182">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="3effe-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3effe-183">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="3effe-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

