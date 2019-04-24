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
description: 高度な電子情報開示では、検索とタグ付けモジュールを使用して、ケースでドキュメントを検索、プレビュー、および整理することができます。 現時点では、このモジュールはベータ版です。
ms.openlocfilehash: 58913a01f30b4169470592f5fc271e3ce785ac5d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261372"
---
# <a name="search-and-tagging"></a><span data-ttu-id="5fe96-104">検索とタグ付け</span><span class="sxs-lookup"><span data-stu-id="5fe96-104">Search and Tagging</span></span>

<span data-ttu-id="5fe96-105">高度な電子情報開示では、検索とタグ付けモジュールを使用して、ケースでドキュメントを検索、プレビュー、および整理することができます。</span><span class="sxs-lookup"><span data-stu-id="5fe96-105">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case.</span></span> <span data-ttu-id="5fe96-106">現時点では、このモジュールはベータ版です。</span><span class="sxs-lookup"><span data-stu-id="5fe96-106">Currently, this module is in beta.</span></span> <span data-ttu-id="5fe96-107">検索とタグ付けの概要については、「 [Advanced eDiscovery ビデオでデータを管理](https://www.youtube.com/watch?v=VaPYL3DHP6I)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fe96-107">For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="5fe96-p103">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="5fe96-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="5fe96-110">ケースでドキュメントを検索する</span><span class="sxs-lookup"><span data-stu-id="5fe96-110">Search the documents in your case</span></span>

<span data-ttu-id="5fe96-111">高度な電子情報開示ケースでドキュメントを処理した後 (必要に応じて Analyze または関連性モジュールを実行すると)、検索とタグ付けを使用してドキュメントを検索し、大文字と小文字を区別したタグ (ラベルとも呼ばれます) を適用することで、それらを整理することができます。</span><span class="sxs-lookup"><span data-stu-id="5fe96-111">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels).</span></span> <span data-ttu-id="5fe96-112">検索クエリは、指定された条件カードを使用するか、またはキーワードの条件カードで kql のようなクエリ言語を使用して定義できます。</span><span class="sxs-lookup"><span data-stu-id="5fe96-112">You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card.</span></span> <span data-ttu-id="5fe96-113">and、OR、NOT、NEAR (n) などの一般的な kql 構文がサポートされています。また、末尾の複数文字ワイルドカード (\*) もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5fe96-113">Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="5fe96-114">次の表に、kql キーワードクエリを使用して検索できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="5fe96-114">The following table lists the properties that you can search for using a KQL keyword query.</span></span> <span data-ttu-id="5fe96-115">または、高度な電子情報開示検索ツールで条件カードを使用して、検索クエリに条件 (選択したプロパティの場合) を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="5fe96-115">Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="5fe96-116">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="5fe96-116">**Property**</span></span>|<span data-ttu-id="5fe96-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="5fe96-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5fe96-118">**caselabel**</span><span class="sxs-lookup"><span data-stu-id="5fe96-118">**caselabel**</span></span> <br/> | <span data-ttu-id="5fe96-119">文書にタグ付けするときに作成/適用されるタグの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5fe96-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="5fe96-120">**保管担当者**</span><span class="sxs-lookup"><span data-stu-id="5fe96-120">**custodian**</span></span> <br/> | <span data-ttu-id="5fe96-121">ドキュメントに関連付けられている保管担当者。制限の対象となります。</span><span class="sxs-lookup"><span data-stu-id="5fe96-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="5fe96-122">**date**</span><span class="sxs-lookup"><span data-stu-id="5fe96-122">**date**</span></span> <br/> | <span data-ttu-id="5fe96-123">電子メールの送信日。サイトドキュメントの変更された日付。</span><span class="sxs-lookup"><span data-stu-id="5fe96-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="5fe96-124">**fileid**</span><span class="sxs-lookup"><span data-stu-id="5fe96-124">**fileid**</span></span> <br/> | <span data-ttu-id="5fe96-125">ケース内のファイル ID。</span><span class="sxs-lookup"><span data-stu-id="5fe96-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="5fe96-126">**filetype**</span><span class="sxs-lookup"><span data-stu-id="5fe96-126">**filetype**</span></span> <br/> | <span data-ttu-id="5fe96-127">ネイティブファイル拡張子。</span><span class="sxs-lookup"><span data-stu-id="5fe96-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="5fe96-128">**fileclass**</span><span class="sxs-lookup"><span data-stu-id="5fe96-128">**fileclass**</span></span> <br/> | <span data-ttu-id="5fe96-129">電子メール、ドキュメント、または添付ファイル。</span><span class="sxs-lookup"><span data-stu-id="5fe96-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="5fe96-130">**senderauthor**</span><span class="sxs-lookup"><span data-stu-id="5fe96-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="5fe96-131">電子メールの送信者。サイトドキュメントの作成者。</span><span class="sxs-lookup"><span data-stu-id="5fe96-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="5fe96-132">**size**</span><span class="sxs-lookup"><span data-stu-id="5fe96-132">**size**</span></span> <br/> | <span data-ttu-id="5fe96-133">ファイルのサイズ (KB 単位)。</span><span class="sxs-lookup"><span data-stu-id="5fe96-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="5fe96-134">**subjecttitle**</span><span class="sxs-lookup"><span data-stu-id="5fe96-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="5fe96-135">電子メールの件名。サイトドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="5fe96-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="5fe96-136">**bcc**</span><span class="sxs-lookup"><span data-stu-id="5fe96-136">**bcc**</span></span> <br/> | <span data-ttu-id="5fe96-137">電子メールの Bcc フィールド。</span><span class="sxs-lookup"><span data-stu-id="5fe96-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="5fe96-138">**cc**</span><span class="sxs-lookup"><span data-stu-id="5fe96-138">**cc**</span></span> <br/> | <span data-ttu-id="5fe96-139">電子メールの Cc フィールド。</span><span class="sxs-lookup"><span data-stu-id="5fe96-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="5fe96-140">**participants**</span><span class="sxs-lookup"><span data-stu-id="5fe96-140">**participants**</span></span> <br/> | <span data-ttu-id="5fe96-141">電子メールスレッド内のすべての参加者の電子メールアドレス (存在しないリンクを含む)。</span><span class="sxs-lookup"><span data-stu-id="5fe96-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="5fe96-142">**received**</span><span class="sxs-lookup"><span data-stu-id="5fe96-142">**received**</span></span> <br/> | <span data-ttu-id="5fe96-143">電子メールが受信された日付。</span><span class="sxs-lookup"><span data-stu-id="5fe96-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="5fe96-144">**recipients**</span><span class="sxs-lookup"><span data-stu-id="5fe96-144">**recipients**</span></span> <br/> | <span data-ttu-id="5fe96-145">[宛先]、[Cc]、または [Bcc] フィールドに含まれている電子メールの受信者。</span><span class="sxs-lookup"><span data-stu-id="5fe96-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="5fe96-146">**sender**</span><span class="sxs-lookup"><span data-stu-id="5fe96-146">**sender**</span></span> <br/> | <span data-ttu-id="5fe96-147">電子メールの送信者。</span><span class="sxs-lookup"><span data-stu-id="5fe96-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="5fe96-148">**lastmodifieddate**</span><span class="sxs-lookup"><span data-stu-id="5fe96-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="5fe96-149">サイトドキュメントの最終更新日。</span><span class="sxs-lookup"><span data-stu-id="5fe96-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="5fe96-150">**sent**</span><span class="sxs-lookup"><span data-stu-id="5fe96-150">**sent**</span></span> <br/> | <span data-ttu-id="5fe96-151">電子メールの送信日。</span><span class="sxs-lookup"><span data-stu-id="5fe96-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="5fe96-152">**to**</span><span class="sxs-lookup"><span data-stu-id="5fe96-152">**to**</span></span> <br/> | <span data-ttu-id="5fe96-153">電子メールの宛先フィールドに記載されている受信者。</span><span class="sxs-lookup"><span data-stu-id="5fe96-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="5fe96-154">**判別**</span><span class="sxs-lookup"><span data-stu-id="5fe96-154">**author**</span></span> <br/> | <span data-ttu-id="5fe96-155">サイトドキュメントの作成者。</span><span class="sxs-lookup"><span data-stu-id="5fe96-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="5fe96-156">**title**</span><span class="sxs-lookup"><span data-stu-id="5fe96-156">**title**</span></span> <br/> | <span data-ttu-id="5fe96-157">サイトドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="5fe96-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="5fe96-158">**dominanttheme**\*</span><span class="sxs-lookup"><span data-stu-id="5fe96-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="5fe96-159">アイテムの主要なテーマ。</span><span class="sxs-lookup"><span data-stu-id="5fe96-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="5fe96-160">**テーマ一覧**\*</span><span class="sxs-lookup"><span data-stu-id="5fe96-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="5fe96-161">アイテムに関連付けられているテーマ。</span><span class="sxs-lookup"><span data-stu-id="5fe96-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="5fe96-162">**readpercentile_ [# enum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="5fe96-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="5fe96-163">アイテムの閲覧の百分位。 [設定] で定義されている問題を示します。</span><span class="sxs-lookup"><span data-stu-id="5fe96-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="5fe96-164">**relevancescore_ [# enum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="5fe96-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="5fe96-165">アイテムの関連性スコア。 [/設定] で定義されている問題について。</span><span class="sxs-lookup"><span data-stu-id="5fe96-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="5fe96-166">**relevancetag_ [tagname]**\*\*</span><span class="sxs-lookup"><span data-stu-id="5fe96-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="5fe96-167">関連性に対して手動でタグ付けされたアイテムの場合は、[tagname] で定義されているタグ。</span><span class="sxs-lookup"><span data-stu-id="5fe96-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="5fe96-168">\*Themes モジュールが実行されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5fe96-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="5fe96-169">\*\*関連性モジュールが実行されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5fe96-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="5fe96-170">または、高度な電子情報開示検索ツールの条件カードを使用して、検索クエリに条件 (選択したプロパティの場合) を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="5fe96-170">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span> <span data-ttu-id="5fe96-171">次のスクリーンショットは、クエリに追加できる条件を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fe96-171">The following screenshot shows the conditions that can be added to a query.</span></span> <span data-ttu-id="5fe96-172">[**グループ]** 列は、プロパティが電子メール、サイトドキュメント、またはその両方に適用されるかどうかを示します (*共通*の値で示されます)。</span><span class="sxs-lookup"><span data-stu-id="5fe96-172">The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*).</span></span> <span data-ttu-id="5fe96-173">この列は、関連性モジュールを実行した後に使用できる検索可能なプロパティも識別します。</span><span class="sxs-lookup"><span data-stu-id="5fe96-173">This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![高度な電子情報開示検索ツールの検索条件](media/AeDSearchConditions.png)

<span data-ttu-id="5fe96-175">検索可能なプロパティの詳細については、「[キーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fe96-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5fe96-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fe96-176">See also</span></span>

[<span data-ttu-id="5fe96-177">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5fe96-177">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="5fe96-178">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="5fe96-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5fe96-179">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="5fe96-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5fe96-180">タグ付けと関連性トレーニング</span><span class="sxs-lookup"><span data-stu-id="5fe96-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5fe96-181">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="5fe96-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5fe96-182">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="5fe96-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5fe96-183">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="5fe96-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

