---
title: ワーキング セット内のドキュメントを表示する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 155d5663ff54e48bee0c0561e58319b5f213c016
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30306516"
---
# <a name="view-documents-in-a-working-set"></a><span data-ttu-id="21226-102">ワーキング セット内のドキュメントを表示する</span><span class="sxs-lookup"><span data-stu-id="21226-102">View documents in a working set</span></span>

<span data-ttu-id="21226-p101">Advanced eDiscovery (プレビュー) では、複数の閲覧者がそれぞれ異なる目的でコンテンツを表示します。作業セット内の任意の文書をクリックすると、さまざまなビューアーを使用できます。現在提供されているビューアーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="21226-p101">Advanced eDiscovery (Preview) displays content via several viewers each with different purposes. The various viewers can be used by clicking on any document within a working set. The viewers currently provided are:</span></span>

- <span data-ttu-id="21226-106">ファイルのメタデータ  
</span><span class="sxs-lookup"><span data-stu-id="21226-106">File metadata</span></span>
- <span data-ttu-id="21226-107">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="21226-107">Native view</span></span>
- <span data-ttu-id="21226-108">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="21226-108">Text view</span></span>
- <span data-ttu-id="21226-109">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="21226-109">Annotate view</span></span>
- <span data-ttu-id="21226-110">変換されたビュー</span><span class="sxs-lookup"><span data-stu-id="21226-110">Converted view</span></span>

## <a name="file-metadata"></a><span data-ttu-id="21226-111">ファイルのメタデータ  
</span><span class="sxs-lookup"><span data-stu-id="21226-111">File metadata</span></span>

<span data-ttu-id="21226-p102">このパネルは、ドキュメントに関連付けられているさまざまなメタデータを表示するために、オン/オフを切り替えることができます。検索結果グリッドをカスタマイズして特定のメタデータを表示することはできますが、データを確認する間、水平方向にスクロールするのが困難な場合があります。[ファイルメタデータ] パネルを使用すると、ユーザーはビューアー内のビューを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="21226-p102">This panel can be toggled on/off to display various metadata associated with the document. Although the search results grid can be customized to display specific metadata, there are instances where scrolling horizontally can be difficult while reviewing data. The File metadata panel allows a user to toggle on a view within the viewer.</span></span>

![<span data-ttu-id="21226-115">ファイルのメタデータパネル</span><span class="sxs-lookup"><span data-stu-id="21226-115">File metadata panel</span></span>
](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="21226-116">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="21226-116">Native view</span></span>

<span data-ttu-id="21226-p103">ネイティブビューアーは、ドキュメントの最も豊富なビューを表示します。数百のファイルの種類をサポートしており、できる限りの、ネイティブの環境を表示することを目的としています。たとえば、Microsoft office ファイルの場合、viewer は office Online を利用して、ドキュメントコメント、Excel の数式、非表示の行/列、PowerPoint メモなどのコンテンツを表示します。Office Online 閲覧者の詳細については、 \[「必要な情報」リンクを参照してください。\]</span><span class="sxs-lookup"><span data-stu-id="21226-p103">The Native viewer displays the richest view of a document. It supports hundreds of file types and is meant to display the truest to native experience possible. For Microsoft Office files, for example, the viewer leverages Office Online in order to display content such as document comments, Excel formulas, hidden rows/columns, PowerPoint notes, etc. For more information regarding the Office Online viewers, visit here \[need link\]</span></span>

![<span data-ttu-id="21226-120">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="21226-120">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="21226-121">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="21226-121">Text view</span></span>

<span data-ttu-id="21226-p104">テキストビューアーは、ファイルの抽出されたテキストのビューを提供します。埋め込まれた画像と書式設定は無視されますが、ユーザーがすぐにコンテンツを理解しようとしている場合は、非常にパフォーマンスの高い表示になります。テキストビューには、その他の機能もあります。</span><span class="sxs-lookup"><span data-stu-id="21226-p104">The Text viewer provides a view of the extracted text of a file. It ignores any embedded images and formatting but will be a very performant view if a user is trying to understand the content quickly. Text view also includes other features:</span></span>

  - <span data-ttu-id="21226-125">行カウンターを使用すると、文書の特定の部分を簡単に参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="21226-125">Line counter makes it easier to reference specific portions of a document</span></span>

  - <span data-ttu-id="21226-126">ドキュメント内の用語およびスクロールバーの強調表示を示す検索語句の強調表示</span><span class="sxs-lookup"><span data-stu-id="21226-126">Search hit highlighting that will highlight terms within the document as well as the scrollbar</span></span>

  - <span data-ttu-id="21226-127">Diff ビューは、重複するドキュメントを表示するときにテキストの違いを強調表示する比較ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="21226-127">Diff view provides a comparison view that highlights textual differences when viewing Near Duplicate documents</span></span>

![<span data-ttu-id="21226-128">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="21226-128">Text view</span></span>
](../media/Reviewimage4.png)

![<span data-ttu-id="21226-129">相違ビュー</span><span class="sxs-lookup"><span data-stu-id="21226-129">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="21226-130">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="21226-130">Annotate view</span></span>

<span data-ttu-id="21226-131">[注釈] ビューには、ユーザーがドキュメントにマークアップを適用できるようにする機能があります。次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="21226-131">The Annotate view provides features that allow users to apply markup on a document including:</span></span>

  - <span data-ttu-id="21226-132">エリア redactions –機密コンテンツを非表示にするために、ユーザーはドキュメント上にボックスを描画できます。</span><span class="sxs-lookup"><span data-stu-id="21226-132">Area redactions – users can draw a box on the document in order to hide sensitive content</span></span>

  - <span data-ttu-id="21226-133">鉛筆-ユーザーはドキュメントの一部を自由に描画して、ドキュメントの特定の部分に注意することができます。</span><span class="sxs-lookup"><span data-stu-id="21226-133">Pencil – users can free-hand draw on a document in order to bring attention to certain portions of a document</span></span>

  - <span data-ttu-id="21226-134">コメントの選択-ユーザーはドキュメントでコメントを選択して削除することができます。</span><span class="sxs-lookup"><span data-stu-id="21226-134">Select annotations - users can select annotations on a document in order to delete</span></span>

  - <span data-ttu-id="21226-135">コメントの透明度の切り替え-コメントの背後にあるコンテンツを表示するために、コメントを半透明にします。</span><span class="sxs-lookup"><span data-stu-id="21226-135">Toggle annotation transparency – makes annotations semi-transparent in order to view the content behind the annotation</span></span>

  - <span data-ttu-id="21226-136">前のページ-前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="21226-136">Previous page – navigates to previous page</span></span>

  - <span data-ttu-id="21226-137">次のページ-次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="21226-137">Next page – navigates to the next page</span></span>

  - <span data-ttu-id="21226-138">ページに移動-ユーザーは特定のページ番号を入力して移動することができます。</span><span class="sxs-lookup"><span data-stu-id="21226-138">Go to page – user can enter a specific page number to navigate to</span></span>

  - <span data-ttu-id="21226-139">zoom –注釈ビューのズームレベルを設定する</span><span class="sxs-lookup"><span data-stu-id="21226-139">Zoom – set zoom level for annotate view</span></span>

  - <span data-ttu-id="21226-140">回転-ユーザーは右回りでドキュメントを回転できます。</span><span class="sxs-lookup"><span data-stu-id="21226-140">Rotate – user can rotate document clockwise</span></span>

  - <span data-ttu-id="21226-141">検索-ユーザーはドキュメント内で検索し、ドキュメント内のさまざまなヒットに移動できます。</span><span class="sxs-lookup"><span data-stu-id="21226-141">Search – user can search within a document and navigate to the various hits within the document</span></span>
    
    ![<span data-ttu-id="21226-142">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="21226-142">Annotate view</span></span>
    ](../media/Reviewimage1.png)