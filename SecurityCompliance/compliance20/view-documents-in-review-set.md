---
title: レビュー セット内のドキュメントを表示する
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: ''
ms.openlocfilehash: d1a51e2496bd57d83e1baf78d82611c406a10e26
ms.sourcegitcommit: 6bb40cf53374eaaae8da0a469f0248b1163184a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2019
ms.locfileid: "34767368"
---
# <a name="view-documents-in-a-review-set"></a><span data-ttu-id="14849-102">レビュー セット内のドキュメントを表示する</span><span class="sxs-lookup"><span data-stu-id="14849-102">View documents in a review set</span></span>

<span data-ttu-id="14849-103">上級電子情報開示では、それぞれ異なる目的を持つ複数の閲覧者を使用してコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="14849-103">Advanced eDiscovery displays content via several viewers each with different purposes.</span></span> <span data-ttu-id="14849-104">校閲セット内の任意の文書をクリックすると、さまざまなビューアーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="14849-104">The various viewers can be used by clicking on any document within a review set.</span></span> <span data-ttu-id="14849-105">現在提供されているビューアーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="14849-105">The viewers currently provided are:</span></span>

- <span data-ttu-id="14849-106">ファイルのメタデータ</span><span class="sxs-lookup"><span data-stu-id="14849-106">File metadata</span></span>
- <span data-ttu-id="14849-107">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="14849-107">Native view</span></span>
- <span data-ttu-id="14849-108">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="14849-108">Text view</span></span>
- <span data-ttu-id="14849-109">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="14849-109">Annotate view</span></span>
- <span data-ttu-id="14849-110">変換されたビュー</span><span class="sxs-lookup"><span data-stu-id="14849-110">Converted view</span></span>

## <a name="file-metadata"></a><span data-ttu-id="14849-111">ファイルのメタデータ</span><span class="sxs-lookup"><span data-stu-id="14849-111">File metadata</span></span>

<span data-ttu-id="14849-112">このパネルは、ドキュメントに関連付けられているさまざまなメタデータを表示するために、オン/オフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="14849-112">This panel can be toggled on/off to display various metadata associated with the document.</span></span> <span data-ttu-id="14849-113">検索結果グリッドをカスタマイズして特定のメタデータを表示することはできますが、データを確認する間、水平方向にスクロールするのが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="14849-113">Although the search results grid can be customized to display specific metadata, there are instances where scrolling horizontally can be difficult while reviewing data.</span></span> <span data-ttu-id="14849-114">[ファイルメタデータ] パネルを使用すると、ユーザーはビューアー内のビューを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="14849-114">The File metadata panel allows a user to toggle on a view within the viewer.</span></span>

![<span data-ttu-id="14849-115">ファイルのメタデータパネル</span><span class="sxs-lookup"><span data-stu-id="14849-115">File metadata panel</span></span>
](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="14849-116">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="14849-116">Native view</span></span>

<span data-ttu-id="14849-117">ネイティブビューアーは、ドキュメントの最も豊富なビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="14849-117">The Native viewer displays the richest view of a document.</span></span> <span data-ttu-id="14849-118">数百のファイルの種類をサポートしており、できる限りの、ネイティブの環境を表示することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="14849-118">It supports hundreds of file types and is meant to display the truest to native experience possible.</span></span> <span data-ttu-id="14849-119">Microsoft Office ファイルの場合、viewer は Office アプリの web 版を使用して、ドキュメントコメント、Excel の数式、非表示の行/列、PowerPoint メモなどのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="14849-119">For Microsoft Office files, the viewer uses the web version of Office apps to display content such as document comments, Excel formulas, hidden rows/columns, and PowerPoint notes.</span></span>

![<span data-ttu-id="14849-120">ネイティブビュー</span><span class="sxs-lookup"><span data-stu-id="14849-120">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="14849-121">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="14849-121">Text view</span></span>

<span data-ttu-id="14849-122">テキストビューアーは、ファイルの抽出されたテキストのビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="14849-122">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="14849-123">埋め込まれた画像と書式設定は無視されますが、コンテンツをすばやく理解しようとする場合は、非常に効果的です。</span><span class="sxs-lookup"><span data-stu-id="14849-123">It ignores any embedded images and formatting but is very effective if you are trying to understand the content quickly.</span></span> <span data-ttu-id="14849-124">テキストビューには、次の機能も含まれます。</span><span class="sxs-lookup"><span data-stu-id="14849-124">Text view also includes these features:</span></span>

  - <span data-ttu-id="14849-125">行カウンターを使用すると、文書の特定の部分を簡単に参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="14849-125">Line counter makes it easier to reference specific portions of a document</span></span>

  - <span data-ttu-id="14849-126">ドキュメント内の用語およびスクロールバーの強調表示を示す検索語句の強調表示</span><span class="sxs-lookup"><span data-stu-id="14849-126">Search hit highlighting that will highlight terms within the document as well as the scrollbar</span></span>

  - <span data-ttu-id="14849-127">Diff ビューは、重複するドキュメントを表示するときにテキストの違いを強調表示する比較ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="14849-127">Diff view provides a comparison view that highlights textual differences when viewing Near Duplicate documents</span></span>

![<span data-ttu-id="14849-128">テキストビュー</span><span class="sxs-lookup"><span data-stu-id="14849-128">Text view</span></span>
](../media/Reviewimage4.png)

![<span data-ttu-id="14849-129">相違ビュー</span><span class="sxs-lookup"><span data-stu-id="14849-129">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="14849-130">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="14849-130">Annotate view</span></span>

<span data-ttu-id="14849-131">[注釈] ビューには、ユーザーがドキュメントにマークアップを適用できるようにする機能があります。次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="14849-131">The Annotate view provides features that allow users to apply markup on a document including:</span></span>

  - <span data-ttu-id="14849-132">エリア redactions –機密コンテンツを非表示にするために、ユーザーはドキュメント上にボックスを描画できます。</span><span class="sxs-lookup"><span data-stu-id="14849-132">Area redactions – users can draw a box on the document in order to hide sensitive content</span></span>

  - <span data-ttu-id="14849-133">鉛筆-ユーザーはドキュメントの一部を自由に描画して、ドキュメントの特定の部分に注意することができます。</span><span class="sxs-lookup"><span data-stu-id="14849-133">Pencil – users can free-hand draw on a document in order to bring attention to certain portions of a document</span></span>

  - <span data-ttu-id="14849-134">コメントの選択-ユーザーはドキュメントでコメントを選択して削除することができます。</span><span class="sxs-lookup"><span data-stu-id="14849-134">Select annotations - users can select annotations on a document in order to delete</span></span>

  - <span data-ttu-id="14849-135">コメントの透明度の切り替え-コメントの背後にあるコンテンツを表示するために、コメントを半透明にします。</span><span class="sxs-lookup"><span data-stu-id="14849-135">Toggle annotation transparency – makes annotations semi-transparent in order to view the content behind the annotation</span></span>

  - <span data-ttu-id="14849-136">前のページ-前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="14849-136">Previous page – navigates to previous page</span></span>

  - <span data-ttu-id="14849-137">次のページ-次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="14849-137">Next page – navigates to the next page</span></span>

  - <span data-ttu-id="14849-138">ページに移動-ユーザーは特定のページ番号を入力して移動することができます。</span><span class="sxs-lookup"><span data-stu-id="14849-138">Go to page – user can enter a specific page number to navigate to</span></span>

  - <span data-ttu-id="14849-139">Zoom –注釈ビューのズームレベルを設定する</span><span class="sxs-lookup"><span data-stu-id="14849-139">Zoom – set zoom level for annotate view</span></span>

  - <span data-ttu-id="14849-140">回転-ユーザーは右回りでドキュメントを回転できます。</span><span class="sxs-lookup"><span data-stu-id="14849-140">Rotate – user can rotate document clockwise</span></span>

  - <span data-ttu-id="14849-141">検索-ユーザーはドキュメント内で検索し、ドキュメント内のさまざまなヒットに移動できます。</span><span class="sxs-lookup"><span data-stu-id="14849-141">Search – user can search within a document and navigate to the various hits within the document</span></span>
    
    ![<span data-ttu-id="14849-142">ビューに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="14849-142">Annotate view</span></span>
    ](../media/Reviewimage1.png)