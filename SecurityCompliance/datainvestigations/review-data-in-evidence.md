---
title: エビデンスのデータを確認する
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
ms.openlocfilehash: e84f05fa1a7356952b62f2f4adc3b7d0f1ddc94e
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258045"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="642db-102">エビデンスのデータを確認する</span><span class="sxs-lookup"><span data-stu-id="642db-102">Review the data in evidence</span></span>

<span data-ttu-id="642db-103">データ調査での証拠セット内のデータは、収集して証拠セットに追加した検索結果のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="642db-103">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="642db-104">検索結果を証拠に追加すると、検索によって返されたアイテムからファイル、メタデータ、およびテキストを抽出するプロセスがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="642db-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="642db-105">その後、データ調査 (プレビュー) ツールは、すべてのデータの新しいインデックスを (*高度なインデックス*と呼ばれるプロセスによって) 作成し、[**証拠**] タブの証拠セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="642db-105">Then the Data Investigations (Preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="642db-106">時間に依存する調査では、元のデータソースにある実際のこぼれたデータや悪意のあるデータを削除することによって、その環境を迅速に格納し、再作成された証拠を a に調査できるようにすることができます。検疫された環境。この場合、証拠セットにコピーされるデータです。</span><span class="sxs-lookup"><span data-stu-id="642db-106">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="642db-107">証拠を収集して証拠セットに追加すると、個々のドキュメントのネイティブ形式、テキスト形式、またはほぼネイティブな形式で、ドキュメントに注釈を付けて表示することができます。</span><span class="sxs-lookup"><span data-stu-id="642db-107">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="642db-108">さらに、クエリを実行して、時間の範囲、ファイルの種類、データ所有者、その他の多くのプロパティおよび検索条件によってデータセットを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="642db-108">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="642db-109">たとえば、作成者、送信者、または受信者の条件を使用することにより、インシデントに関係する人と、組織のデータが外部ユーザーと共有されているかどうかをすばやく識別できます。</span><span class="sxs-lookup"><span data-stu-id="642db-109">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="642db-110">証拠セット内のデータの検索の詳細については、「[証拠でデータを照会](evidence-query.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="642db-110">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="642db-111">ドキュメントをグループ化し、レビューのための詳細を取得するには、[**証拠**] タブで証拠セットを選択し、[**証拠の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="642db-111">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="642db-112">[**分析**] タイルで、[**セット全体の分析を再構築**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="642db-112">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="642db-113">これにより、重複データ検出、電子メールスレッド、テーマ分析などの高度な分析が実行されます。</span><span class="sxs-lookup"><span data-stu-id="642db-113">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="642db-114">その後、データの一般的なテーマを表示することができます。また、電子メールのスレッド、ほぼ重複、正確な複製によってドキュメントを整理して、調査に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="642db-114">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="642db-115">詳細については、「[分析を実行してより早く調査する」を](run-analytics-to-investigate-faster.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="642db-115">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="642db-116">証拠でドキュメントを表示する</span><span class="sxs-lookup"><span data-stu-id="642db-116">View documents in evidence</span></span>

<span data-ttu-id="642db-117">データ調査 (プレビュー) を使用すると、さまざまなビューアーでコンテンツを表示し、各ビューアーにそれぞれ異なる目的を持たせることができます。</span><span class="sxs-lookup"><span data-stu-id="642db-117">Data Investigations (Preview) allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="642db-118">これらのビューアーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="642db-118">These viewers are:</span></span>

- <span data-ttu-id="642db-119">ファイルのメタデータ</span><span class="sxs-lookup"><span data-stu-id="642db-119">File metadata</span></span>
- <span data-ttu-id="642db-120">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="642db-120">Native view</span></span>
- <span data-ttu-id="642db-121">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="642db-121">Text view</span></span>
- <span data-ttu-id="642db-122">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="642db-122">Annotate view</span></span>

<span data-ttu-id="642db-123">これらのビューアーにアクセスするには、証拠セット内のドキュメントを選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="642db-123">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="642db-124">ファイルのメタデータ</span><span class="sxs-lookup"><span data-stu-id="642db-124">File metadata</span></span>

<span data-ttu-id="642db-125">このビューには、選択したドキュメントに関連付けられているさまざまなメタデータプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="642db-125">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="642db-126">[**ファイルメタデータ**] をクリックすると、このビューのオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="642db-126">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="642db-127">ドキュメントをレビューするときは、ファイルメタデータを表示できますが、異なるビューアー間で変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="642db-127">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="642db-128">ドキュメントのファイルメタデータの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="642db-128">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="642db-129">メタデータフィールドの詳細については、「[データ調査のドキュメントメタデータフィールド (プレビュー)](document-metadata-fields.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="642db-129">For more information about the metadata fields, see [Document metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span></span>

![ファイルのメタデータパネル](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="642db-131">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="642db-131">Native view</span></span>

<span data-ttu-id="642db-132">ネイティブビューアーは、ドキュメントをネイティブ形式で最も正確に表示します。</span><span class="sxs-lookup"><span data-stu-id="642db-132">The Native viewer displays the most accurate view of a document in it's native format.</span></span> <span data-ttu-id="642db-133">ネイティブビューは、数百種類のファイルタイプでサポートされており、ドキュメントを表示することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="642db-133">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="642db-134">Microsoft office ファイルの場合、ネイティブビューアーは office Online を使用します。</span><span class="sxs-lookup"><span data-stu-id="642db-134">For Microsoft Office files, the Native viewer uses Office Online.</span></span> <span data-ttu-id="642db-135">これにより、さまざまな Office ドキュメント、数式、Excel の非表示の行/列、PowerPoint のメモビューなどのコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="642db-135">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="642db-136">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="642db-136">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="642db-137">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="642db-137">Text view</span></span>

<span data-ttu-id="642db-138">テキストビューアーは、ファイルの抽出されたテキストのビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="642db-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="642db-139">埋め込まれた画像と書式設定は無視されますが、ドキュメント内のコンテンツをすばやく確認して理解しようとする場合は、このビューが非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="642db-139">It ignores any embedded images and formatting, but this view is very useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="642db-140">テキストビューには、次の機能も含まれます。</span><span class="sxs-lookup"><span data-stu-id="642db-140">Text view also includes these features:</span></span>

  - <span data-ttu-id="642db-141">行カウンターを使用すると、ドキュメントの特定の部分を簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="642db-141">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="642db-142">ドキュメント内およびスクロールバー上の用語を強調表示する検索語句の強調表示</span><span class="sxs-lookup"><span data-stu-id="642db-142">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="642db-143">差分表示では、 **Near [重複**] パネルを使用してドキュメントを表示するときのテキストの相違点を強調表示する比較ビューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="642db-143">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="642db-144">**テキストとスクロールバーでの行カウンターと検索検索の強調表示の例**</span><span class="sxs-lookup"><span data-stu-id="642db-144">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="642db-145">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="642db-145">Text view</span></span>
](../media/Reviewimage4.png)

<span data-ttu-id="642db-146">**相違ビューの例**</span><span class="sxs-lookup"><span data-stu-id="642db-146">**Example of the diff view**</span></span>

![<span data-ttu-id="642db-147">相違ビュー</span><span class="sxs-lookup"><span data-stu-id="642db-147">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="642db-148">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="642db-148">Annotate view</span></span>

<span data-ttu-id="642db-149">[注釈] ビューには、レビュープロセス中にドキュメントにマークアップを適用できるようにする機能が用意されています。これには、次のツールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="642db-149">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="642db-150">**エリア redactions** –機密コンテンツを非表示にするドキュメント上に不透明なボックスを描くことができます。</span><span class="sxs-lookup"><span data-stu-id="642db-150">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="642db-151">**鉛筆**: ドキュメントを自由に描画して、コンテンツの特定の部分に注意することができます。</span><span class="sxs-lookup"><span data-stu-id="642db-151">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="642db-152">**[注釈の選択]** -ドキュメント内のコメントを選択して削除できます。</span><span class="sxs-lookup"><span data-stu-id="642db-152">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="642db-153">[**注釈の透過性を切り替える**] –注釈の透明度を切り替えることができます。これにより、コメントの背後にあるコンテンツを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="642db-153">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent)so you can view the content behind the annotation.</span></span> <span data-ttu-id="642db-154">これには、鉛筆の注釈と redactions の透明度の切り替えが含まれます。</span><span class="sxs-lookup"><span data-stu-id="642db-154">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="642db-155">注釈ビューには、次のナビゲーション機能もあります。</span><span class="sxs-lookup"><span data-stu-id="642db-155">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="642db-156">[**前のページ**]、[次の**ページ**]、および **[ページ移動**] コントロールを使用して、複数ページのドキュメントに使用します。</span><span class="sxs-lookup"><span data-stu-id="642db-156">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="642db-157">**Zoom** -注釈ビューでドキュメントのサイズを拡大または縮小します。</span><span class="sxs-lookup"><span data-stu-id="642db-157">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="642db-158">**回転**: ドキュメントを時計回りに回転します。</span><span class="sxs-lookup"><span data-stu-id="642db-158">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="642db-159">**検索**–ドキュメント内のキーワードを検索し、前と次のコントロールを使用して、ドキュメント内のヒット (強調表示されている) を表示します。</span><span class="sxs-lookup"><span data-stu-id="642db-159">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="642db-160">**注釈の表示の例**</span><span class="sxs-lookup"><span data-stu-id="642db-160">**Example of Annotate view**</span></span>

![ビューに注釈を付ける](../media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="642db-162">注釈は、証拠セットに追加されたドキュメントのコピーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="642db-162">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="642db-163">live サービスの元のドキュメントには、注釈は付けません。</span><span class="sxs-lookup"><span data-stu-id="642db-163">The original documents in the live service aren't annotated.</span></span>
