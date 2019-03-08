---
title: ワーキング セットからドキュメントをエクスポートする
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
ms.openlocfilehash: 815b92b13ed09d8aec64f5207f1c82d910e2dce0
ms.sourcegitcommit: 9f38ba72eba0b656e507860ca228726e4199f7ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30475707"
---
# <a name="export-documents-from-a-working-set"></a><span data-ttu-id="cd6ee-102">ワーキング セットからドキュメントをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="cd6ee-102">Export documents from a working set</span></span>

<span data-ttu-id="cd6ee-103">作業セットからのコンテンツのエクスポートは、次の3つの方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-103">Exporting content from a working set can be accomplished via 3 different methods:</span></span>

## <a name="download"></a><span data-ttu-id="cd6ee-104">ダウンロード</span><span class="sxs-lookup"><span data-stu-id="cd6ee-104">Download</span></span>

<span data-ttu-id="cd6ee-105">ダウンロードは、ネイティブ形式で作業セットからコンテンツをダウンロードする簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-105">Download offers a simple way to download content from a working set in Native format.</span></span> <span data-ttu-id="cd6ee-106">ブラウザーのデータ転送機能を利用して、ダウンロードが完了するとブラウザーのプロンプトが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-106">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="cd6ee-107">このメソッドを使用してダウンロードしたファイルは、コンテナーファイルに圧縮され、アイテムレベルのファイルになります。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-107">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="cd6ee-108">これは、添付ファイルを選択すると、添付ファイルが含まれている電子メールを自動的に受信することを意味します。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-108">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="cd6ee-109">同様に、word 文書に埋め込まれた excel スプレッドシートを選択すると、excel スプレッドシートが埋め込まれた word 文書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-109">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="cd6ee-110">ダウンロードされたアイテムは、ファイルプロパティとして表示できる最終変更日を保持します。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-110">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="cd6ee-111">作業セットからコンテンツをダウンロードするには、まずダウンロードするファイルを選択し、[操作] メニューの [ダウンロード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-111">To download content from a working set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![コンピューターの説明のスクリーンショットが自動的に生成される](../media/eDiscoDownload.png)

## <a name="export"></a><span data-ttu-id="cd6ee-113">エクスポート</span><span class="sxs-lookup"><span data-stu-id="cd6ee-113">Export</span></span>

<span data-ttu-id="cd6ee-114">[エクスポートすると、ユーザーはダウンロードパッケージに含まれるコンテンツをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-114">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="cd6ee-115">構成ページには、次の設定が用意されています。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-115">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="cd6ee-116">メタデータファイル</span><span class="sxs-lookup"><span data-stu-id="cd6ee-116">Metadata file</span></span>

> <span data-ttu-id="cd6ee-117">これは、エクスポートしたファイルに関連付けられているメタデータを含む "load file" と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-117">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="cd6ee-118">メタデータファイルで使用可能なフィールドの一覧につい\[て\]は、「link」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-118">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="cd6ee-119">このファイルは、通常、下位の<sup></sup>サードパーティ製のツールによって取り込まれたすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-119">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="cd6ee-120">タグデータ</span><span class="sxs-lookup"><span data-stu-id="cd6ee-120">Tag data</span></span>

> <span data-ttu-id="cd6ee-121">このコンテンツは、メタデータファイルのフィールドとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-121">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="cd6ee-122">これには、作業セットに適用されるすべてのタグ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-122">It contains all of the tag information applied in working sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="cd6ee-123">テキスト ファイル</span><span class="sxs-lookup"><span data-stu-id="cd6ee-123">Text files</span></span>

> <span data-ttu-id="cd6ee-124">作業セットからエクスポートされたファイルごとに、テキストファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-124">Text files can be generated for each file exported from a working set.</span></span> <span data-ttu-id="cd6ee-125">多くの場合、これらのファイルは、取り込むデータの一部として<sup></sup>サービスパートナーによって、ダウンストリームで3人のサードパーティ製ツールに必要になります。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-125">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="cd6ee-126">がファイル</span><span class="sxs-lookup"><span data-stu-id="cd6ee-126">Redacted files</span></span>

> <span data-ttu-id="cd6ee-127">レビュー中にが pdf が生成された場合、これらのファイルはエクスポート中に利用できます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-127">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="cd6ee-128">ユーザーは、ネイティブファイルのみをエクスポートするか、または redactions を持つ natives を pdf で焼き付けられるものに置き換えるかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-128">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="cd6ee-129">エクスポート場所</span><span class="sxs-lookup"><span data-stu-id="cd6ee-129">Export Location</span></span>

> <span data-ttu-id="cd6ee-130">エクスポートされたコンテンツは、Microsoft が提供する Azure blob またはお客様の blob のいずれかに配信されます。詳細については、export で提供されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-130">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

## <a name="export-structure"></a><span data-ttu-id="cd6ee-131">エクスポート構造</span><span class="sxs-lookup"><span data-stu-id="cd6ee-131">Export Structure</span></span>

<span data-ttu-id="cd6ee-132">コンテンツが作業セットからエクスポートされると、コンテンツは次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-132">When content is exported from a working set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="cd6ee-133">ルートフォルダー–ダウンロード ID</span><span class="sxs-lookup"><span data-stu-id="cd6ee-133">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="cd6ee-134">load\_\_ファイル .csv = メタデータファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="cd6ee-134">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="cd6ee-135">summary.txt = エクスポート統計情報を含む要約ファイル</span><span class="sxs-lookup"><span data-stu-id="cd6ee-135">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="cd6ee-136">入力\_ファイルまた\_はネイティブファイル = すべてのネイティブファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-136">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="cd6ee-137">エラー\_ファイル = エクスポートに含まれているエラーファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-137">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="cd6ee-138">extractionerror –親ファイルから正しく抽出されなかったファイルの利用可能なメタデータを含む csv。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-138">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="cd6ee-139">processingerror-処理エラーがあるコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-139">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="cd6ee-140">このコンテンツはアイテムレベルを意味する。添付ファイルに処理エラーが発生した場合、添付ファイルを含む電子メールはこのフォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-140">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="cd6ee-141">抽出\_さ\_れたテキストファイル = 処理時に生成されたすべての抽出済みテキストファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-141">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>

## <a name="working-set"></a><span data-ttu-id="cd6ee-142">ワーキング セット</span><span class="sxs-lookup"><span data-stu-id="cd6ee-142">Working Set</span></span>

<span data-ttu-id="cd6ee-143">コンテンツを別の作業セットに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cd6ee-143">Content can be added to another working set.</span></span>