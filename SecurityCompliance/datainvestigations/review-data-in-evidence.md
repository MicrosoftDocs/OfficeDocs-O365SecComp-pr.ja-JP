---
title: 証拠でデータを確認する
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
ms.openlocfilehash: 279d2117a69e889f9e605e0ab211c03c5842a59d
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030300"
---
# <a name="review-data-in-evidence"></a><span data-ttu-id="3096f-102">証拠でデータを確認する</span><span class="sxs-lookup"><span data-stu-id="3096f-102">Review data in evidence</span></span>

<span data-ttu-id="3096f-103">**証拠**は収集した検索結果のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="3096f-103">**Evidence** is a snapshot of search results that you collected.</span></span> <span data-ttu-id="3096f-104">検索結果を証拠に追加すると、ファイル、メタデータ、およびテキストを抽出するプロセスがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="3096f-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text.</span></span> <span data-ttu-id="3096f-105">その後、システムはすべてのデータの新しいインデックスを作成し、**証拠**に追加します。</span><span class="sxs-lookup"><span data-stu-id="3096f-105">Then, the system builds a new index of all the data and adds to **Evidence**.</span></span> 

<span data-ttu-id="3096f-106">時間に依存しないインシデントについては、これを使用すると、検疫された環境で再作成された証拠を調査しながら、元の場所にあるデータを削除することによって、環境をすばやく含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3096f-106">For any time-sensitive incidents, this allows you to quickly contain the environment by deleting data at original locations while investigating re-created evidence in a quarantined environment.</span></span> <span data-ttu-id="3096f-107">エビデンスが収集されると、個々のドキュメントをネイティブ形式、テキスト形式、またはほぼネイティブ形式で確認できます。</span><span class="sxs-lookup"><span data-stu-id="3096f-107">Once evidence is collected, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="3096f-108">さらに、クエリを実行して、時間範囲、ファイルの種類、データ所有者、その他のさまざまな条件カードによってデータを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3096f-108">Additionally, you can run queries to narrow the data by time range, file types, data owners, and many other condition cards.</span></span> <span data-ttu-id="3096f-109">作成者/送信者/受信者条件カードを使用すると、スピルに関係しているユーザーと、外部共有があるかどうかをすばやく調べることができます。</span><span class="sxs-lookup"><span data-stu-id="3096f-109">Using Author/Sender/Recipient condition cards, you can quickly examine who are involved in the spill and if there have been any external shares.</span></span> <span data-ttu-id="3096f-110">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3096f-110">For more information, see:</span></span>

  - [<span data-ttu-id="3096f-111">証拠でデータを照会する</span><span class="sxs-lookup"><span data-stu-id="3096f-111">Query the data in evidence</span></span>](evidence-query.md)

<span data-ttu-id="3096f-112">ドキュメントをグループ化して、レビューのための詳細を取得するには、[**証明の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3096f-112">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="3096f-113">[**分析**] タイルで、[**分析**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3096f-113">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="3096f-114">これにより、重複データ検出、電子メールスレッド、テーマ分析などの高度な分析が実行されます。</span><span class="sxs-lookup"><span data-stu-id="3096f-114">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="3096f-115">その後、データの一般的なテーマを表示することができます。また、電子メールのスレッド別にドキュメントを整理したり、正確な複製やほぼ重複を調べて、調査を容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3096f-115">Afterwards, you can see the general themes of the data and also organize documents by email threads, exact duplicates and near duplicates to facilitate your investigation.</span></span> <span data-ttu-id="3096f-116">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3096f-116">For more information, see:</span></span>

  - [<span data-ttu-id="3096f-117">分析を実行してより早く調査する</span><span class="sxs-lookup"><span data-stu-id="3096f-117">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)

## <a name="view-documents-in-evidence"></a><span data-ttu-id="3096f-118">証拠でドキュメントを表示する</span><span class="sxs-lookup"><span data-stu-id="3096f-118">View documents in evidence</span></span>

<span data-ttu-id="3096f-119">データ調査 (プレビュー) は、複数のビューアーを使用して、それぞれ異なる目的でコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="3096f-119">Data investigation (Preview) displays content via several viewers each with different purposes.</span></span> <span data-ttu-id="3096f-120">さまざまなビューアーは、**証拠**の任意のドキュメントをクリックして使用できます。</span><span class="sxs-lookup"><span data-stu-id="3096f-120">The various viewers can be used by clicking on any document in **Evidence**.</span></span> <span data-ttu-id="3096f-121">現在提供されているビューアーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3096f-121">The viewers currently provided are:</span></span>

- <span data-ttu-id="3096f-122">ファイルのメタデータ</span><span class="sxs-lookup"><span data-stu-id="3096f-122">File metadata</span></span>
- <span data-ttu-id="3096f-123">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="3096f-123">Native view</span></span>
- <span data-ttu-id="3096f-124">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="3096f-124">Text view</span></span>
- <span data-ttu-id="3096f-125">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="3096f-125">Annotate view</span></span>
- <span data-ttu-id="3096f-126">変換されたビュー</span><span class="sxs-lookup"><span data-stu-id="3096f-126">Converted view</span></span>

## <a name="file-metadata"></a><span data-ttu-id="3096f-127">ファイルのメタデータ</span><span class="sxs-lookup"><span data-stu-id="3096f-127">File metadata</span></span>

<span data-ttu-id="3096f-128">このパネルは、ドキュメントに関連付けられているさまざまなメタデータを表示するために、オン/オフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="3096f-128">This panel can be toggled on/off to display various metadata associated with the document.</span></span> <span data-ttu-id="3096f-129">検索結果グリッドをカスタマイズして特定のメタデータを表示することはできますが、データを確認する間、水平方向にスクロールするのが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3096f-129">Although the search results grid can be customized to display specific metadata, there are instances where scrolling horizontally can be difficult while reviewing data.</span></span> <span data-ttu-id="3096f-130">[ファイルメタデータ] パネルを使用すると、ユーザーはビューアー内のビューを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="3096f-130">The File metadata panel allows a user to toggle on a view within the viewer.</span></span>

![<span data-ttu-id="3096f-131">ファイルのメタデータパネル</span><span class="sxs-lookup"><span data-stu-id="3096f-131">File metadata panel</span></span>
](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="3096f-132">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="3096f-132">Native view</span></span>

<span data-ttu-id="3096f-133">ネイティブビューアーは、ドキュメントの最も豊富なビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="3096f-133">The Native viewer displays the richest view of a document.</span></span> <span data-ttu-id="3096f-134">数百のファイルの種類をサポートしており、できる限りの、ネイティブの環境を表示することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="3096f-134">It supports hundreds of file types and is meant to display the truest to native experience possible.</span></span> <span data-ttu-id="3096f-135">たとえば、Microsoft office ファイルの場合、viewer は office Online を利用して、ドキュメントコメント、Excel の数式、非表示の行/列、PowerPoint メモなどのコンテンツを表示します。Office Online 閲覧者の詳細については、 \[「必要な情報」リンクを参照してください。\]</span><span class="sxs-lookup"><span data-stu-id="3096f-135">For Microsoft Office files, for example, the viewer leverages Office Online in order to display content such as document comments, Excel formulas, hidden rows/columns, PowerPoint notes, etc. For more information regarding the Office Online viewers, visit here \[need link\]</span></span>

![<span data-ttu-id="3096f-136">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="3096f-136">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="3096f-137">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="3096f-137">Text view</span></span>

<span data-ttu-id="3096f-138">テキストビューアーは、ファイルの抽出されたテキストのビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="3096f-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="3096f-139">埋め込まれた画像と書式設定は無視されますが、ユーザーがすぐにコンテンツを理解しようとしている場合は、非常にパフォーマンスの高い表示になります。</span><span class="sxs-lookup"><span data-stu-id="3096f-139">It ignores any embedded images and formatting but will be a very performant view if a user is trying to understand the content quickly.</span></span> <span data-ttu-id="3096f-140">テキストビューには、その他の機能もあります。</span><span class="sxs-lookup"><span data-stu-id="3096f-140">Text view also includes other features:</span></span>

  - <span data-ttu-id="3096f-141">行カウンターを使用すると、文書の特定の部分を簡単に参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3096f-141">Line counter makes it easier to reference specific portions of a document</span></span>

  - <span data-ttu-id="3096f-142">ドキュメント内の用語およびスクロールバーの強調表示を示す検索語句の強調表示</span><span class="sxs-lookup"><span data-stu-id="3096f-142">Search hit highlighting that will highlight terms within the document as well as the scrollbar</span></span>

  - <span data-ttu-id="3096f-143">Diff ビューは、重複するドキュメントを表示するときにテキストの違いを強調表示する比較ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="3096f-143">Diff view provides a comparison view that highlights textual differences when viewing Near Duplicate documents</span></span>

![<span data-ttu-id="3096f-144">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="3096f-144">Text view</span></span>
](../media/Reviewimage4.png)

![<span data-ttu-id="3096f-145">相違ビュー</span><span class="sxs-lookup"><span data-stu-id="3096f-145">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="3096f-146">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="3096f-146">Annotate view</span></span>

<span data-ttu-id="3096f-147">[注釈] ビューには、調査時にドキュメントにマークアップを適用するための次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="3096f-147">The Annotate view provides features that allow users to apply markup on a document during investigation including:</span></span>

  - <span data-ttu-id="3096f-148">エリア redactions –機密コンテンツを非表示にするために、ユーザーはドキュメント上にボックスを描画できます。</span><span class="sxs-lookup"><span data-stu-id="3096f-148">Area redactions – users can draw a box on the document in order to hide sensitive content</span></span>

  - <span data-ttu-id="3096f-149">鉛筆-ユーザーはドキュメントの一部を自由に描画して、ドキュメントの特定の部分に注意することができます。</span><span class="sxs-lookup"><span data-stu-id="3096f-149">Pencil – users can free-hand draw on a document in order to bring attention to certain portions of a document</span></span>

  - <span data-ttu-id="3096f-150">コメントの選択-ユーザーはドキュメントでコメントを選択して削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3096f-150">Select annotations - users can select annotations on a document in order to delete</span></span>

  - <span data-ttu-id="3096f-151">コメントの透明度の切り替え-コメントの背後にあるコンテンツを表示するために、コメントを半透明にします。</span><span class="sxs-lookup"><span data-stu-id="3096f-151">Toggle annotation transparency – makes annotations semi-transparent in order to view the content behind the annotation</span></span>

  - <span data-ttu-id="3096f-152">前のページ-前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3096f-152">Previous page – navigates to previous page</span></span>

  - <span data-ttu-id="3096f-153">次のページ-次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3096f-153">Next page – navigates to the next page</span></span>

  - <span data-ttu-id="3096f-154">ページに移動-ユーザーは特定のページ番号を入力して移動することができます。</span><span class="sxs-lookup"><span data-stu-id="3096f-154">Go to page – user can enter a specific page number to navigate to</span></span>

  - <span data-ttu-id="3096f-155">zoom –注釈ビューのズームレベルを設定する</span><span class="sxs-lookup"><span data-stu-id="3096f-155">Zoom – set zoom level for annotate view</span></span>

  - <span data-ttu-id="3096f-156">回転-ユーザーは右回りでドキュメントを回転できます。</span><span class="sxs-lookup"><span data-stu-id="3096f-156">Rotate – user can rotate document clockwise</span></span>

  - <span data-ttu-id="3096f-157">検索-ユーザーはドキュメント内で検索し、ドキュメント内のさまざまなヒットに移動できます。</span><span class="sxs-lookup"><span data-stu-id="3096f-157">Search – user can search within a document and navigate to the various hits within the document</span></span>
    
    ![<span data-ttu-id="3096f-158">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="3096f-158">Annotate view</span></span>
    ](../media/Reviewimage1.png)

<span data-ttu-id="3096f-159">これらの注釈は、証拠として収集されるデータ上にあり、ライブシステムの元の場所ではありません。</span><span class="sxs-lookup"><span data-stu-id="3096f-159">Note that these annotations are on data collected as evidence, not at its original location in live system.</span></span> 

## <a name="more-information"></a><span data-ttu-id="3096f-160">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3096f-160">More information</span></span>

<span data-ttu-id="3096f-161">次の表は、データ調査 (プレビュー) における証拠の制限を示しています。</span><span class="sxs-lookup"><span data-stu-id="3096f-161">The following table lists the limits for evidence in Data Investigations (Preview).</span></span>  <span data-ttu-id="3096f-162">1つのファイルの最大数を超えるアイテムは、処理エラーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="3096f-162">Any items that exceed the single file maximums will show up as processing errors.</span></span>
    
  |<span data-ttu-id="3096f-163">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="3096f-163">**Description of limit**</span></span>|<span data-ttu-id="3096f-164">**制限**</span><span class="sxs-lookup"><span data-stu-id="3096f-164">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="3096f-165">証拠コレクションの最大数</span><span class="sxs-lookup"><span data-stu-id="3096f-165">Maximum number of evidence collections</span></span>  <br/> |<span data-ttu-id="3096f-166">50</span><span class="sxs-lookup"><span data-stu-id="3096f-166">50</span></span>  <br/> |
  |<span data-ttu-id="3096f-167">ケースに取り込まれたできるドキュメントの合計数 (調査中のすべての証拠コレクションに対して)</span><span class="sxs-lookup"><span data-stu-id="3096f-167">Total number of documents that can be ingested into a case (for all evidence collections in the investigation)</span></span>  <br/> |<span data-ttu-id="3096f-168">100 万</span><span class="sxs-lookup"><span data-stu-id="3096f-168">1 million</span></span>  <br/> |
  |<span data-ttu-id="3096f-169">ロードあたりの合計ファイルサイズ</span><span class="sxs-lookup"><span data-stu-id="3096f-169">Total file size per load</span></span>  <br/> |<span data-ttu-id="3096f-170">100 GB</span><span class="sxs-lookup"><span data-stu-id="3096f-170">100 GB</span></span>  <br/> |
  |<span data-ttu-id="3096f-171">単一ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="3096f-171">Maximum size of single file</span></span>   <br/> |<span data-ttu-id="3096f-172">100 MB</span><span class="sxs-lookup"><span data-stu-id="3096f-172">100 MB</span></span>  <br/> |
  |<span data-ttu-id="3096f-173">1つのファイルから抽出される最大文字数</span><span class="sxs-lookup"><span data-stu-id="3096f-173">Maximum number of characters extracted from a single file</span></span>  <br/> |<span data-ttu-id="3096f-174">1000 万</span><span class="sxs-lookup"><span data-stu-id="3096f-174">10 million</span></span>  <br/> |
  |<span data-ttu-id="3096f-175">文書内の埋め込みアイテムの深さ</span><span class="sxs-lookup"><span data-stu-id="3096f-175">Depth of embedded items in a document</span></span>  <br/> |<span data-ttu-id="3096f-176">まで</span><span class="sxs-lookup"><span data-stu-id="3096f-176">25</span></span>  <br/> |
  