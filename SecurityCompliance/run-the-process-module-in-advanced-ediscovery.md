---
title: Office 365 Advanced eDiscovery でプロセス モジュールを実行する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: '電子的証拠開示の Office 365 の詳細な分析のための Office 365 のデータ、大文字のファイルの準備に関するガイドラインについて説明します。  '
ms.openlocfilehash: 52b1dce9fb778c6628d90c39135f0c93f08134d7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532700"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="ed54f-103">Office 365 Advanced eDiscovery でプロセス モジュールを実行する</span><span class="sxs-lookup"><span data-stu-id="ed54f-103">Run the Process module in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="ed54f-104">ケース ・ ファイルは、**準備**時に、高度な電子的証拠開示に読み込まれる\>**プロセス**。</span><span class="sxs-lookup"><span data-stu-id="ed54f-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ed54f-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="ed54f-107">ガイドライン: 高度な電子的証拠開示のデータを準備します。</span><span class="sxs-lookup"><span data-stu-id="ed54f-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="ed54f-108">**品質**: 大文字のファイルの作成をサポート案件に関連するを明確に識別します。</span><span class="sxs-lookup"><span data-stu-id="ed54f-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="ed54f-109">**荷重**: 高度な電子的証拠開示にアクセス可能な場所にファイルをロードします。</span><span class="sxs-lookup"><span data-stu-id="ed54f-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="ed54f-p102">**ファイル ID**: 高度な電子的証拠開示での一意なファイル識別子。高度な電子的証拠開示が ID を自動的に生成する場合はファイルの識別子はインポートされませんでしたが、プロセスの後続の読み込みでの ID にマップしてプロセスの最初の読み込みで高度な電子的証拠開示はパスではなくファイルの新しいエントリを追加する) よりも、別のパスをマップします。ID は、エクスポート プロセスで参照として使用できます。ID の値を「-1」とはなりません。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p102">**File ID**: A unique file identifier in Advanced eDiscovery. If no file identifier is imported, Advanced eDiscovery automatically generates the ID. If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry). The ID can be used as a reference in the Export process. The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="ed54f-p103">**MD5**: (2 つのファイルは考慮されません完全に重複しない限り、同一の MD5) のファイルを区別するためにこの署名を使用します。既定では、高度な電子的証拠開示は、ファイルの MD5 を計算します。読み込まれているファイルのテキスト ファイルでは、ときに、ロードし、高度な電子的証拠開示での計算ではなく元の MD5 値をマップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p103">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5). By default, Advanced eDiscovery calculates the MD5 of files. When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="ed54f-118">**ファイルの種類と名前**を表示します。</span><span class="sxs-lookup"><span data-stu-id="ed54f-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="ed54f-p104">高度な電子的証拠開示はさまざまな形式のファイルを処理し、次のように、標準的な形式に読み込まれているネイティブのファイルを抽出\*。TXT、HTML、または。Xml テキスト ファイルの処理では、ネイティブのファイルよりも高速です。抽出されたテキスト ファイルは、大文字のフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p104">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML. Processing of text files is faster than native files. Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="ed54f-p105">システム ファイルまたはグラフィック イメージなどの抽出できないファイルは読み込まれません。これらのファイルは、処理を遅らせることができます。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p105">Do not load files that cannot be extracted, such as system files or graphic images. These files may delay processing.</span></span>
    
  - <span data-ttu-id="ed54f-124">ファイル名の名前は非常にパスが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed54f-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="ed54f-125">**ファイルのパス**: 高度な電子的証拠開示は、400 文字までのパスの長さを持つファイルを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="ed54f-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="ed54f-p106">**テキストの抽出**: 通常のテキストだけでなく、ネイティブのファイルからテキストを抽出する場合は、次も抽出: 非表示のテキスト (Excel および .doc) は、非表示の列 (Excel)、変更履歴の記録 (.doc)、発表者のノート (.ppt ファイル) が埋め込まれているオブジェクト (たとえば、Excel のオブジェクトが、.ppt)。これらは、テキスト エディターで表示できます。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p106">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt). These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="ed54f-p107">**テキストを無視する**: プロセスを実行した後、分析する前に、このオプションの機能が定義されています。無視の使用ファイルの解析のパフォーマンスが低下する可能性がありますので、注意してテキストを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p107">**Ignore Text**: This optional feature is defined after Process is run and before Analyze. Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="ed54f-130">**多言語テキスト**: 高度な電子的証拠開示が現在のタグ、保管担当者、および問題の多言語の名前を処理します。</span><span class="sxs-lookup"><span data-stu-id="ed54f-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="ed54f-p108">**メタデータ**: 保管担当者、日付の範囲、ファイル サイズ、ファイルの種類など、将来の参照用のケースのデータベースに保存し、対象とするメタデータがないか確認します。ファイルは、インベントリを再実行するか、オーバーヘッドの再処理を追加することがなく既に読み込まれた後、メタデータを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p108">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject. Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="ed54f-p109">ファイルは、パスを使用してロードされた当初場合、は、後でメタデータをインポートするときのパス] 列をマップします。Id ファイルを参照して、別のパスをマップします。これは、ファイルのパスを変更するときに便利なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p109">If the files were originally loaded by path, map the path column when later importing metadata. It is possible to refer to the file by ID and to map a different path. This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="ed54f-p110">ファイルは、ファイル ID でロードされた当初場合、は、メタデータを読み込むときに ID 列をマップします。(ID) ではなくパス、ファイルを参照すると、別の ID を再ロードするファイル高度な電子的証拠開示ではなく、メタデータの読み込み中の既存のファイルのファイルのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p110">If the files were originally loaded by File ID, map the ID column when loading metadata. Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID. Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="ed54f-139">**ファミリ**: せず、親 (家族のヘッド) ファミリをロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ed54f-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="ed54f-p111">**ファイル サイズ**: 高度な電子的証拠開示に読み込まれたファイルのサイズに制限はありません。分析 (分析、関連性など) は、制限は、抽出したテキストの 5,242,880 文字です。サイズの大きいファイルは無視されます (などの関連性、ファイル関連のトレーニング プロセスに参加していないとバッチの計算の後、関連性スコアは表示されません)。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p111">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery. For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text. Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="ed54f-p112">**ファイル数量**: 1 つのケースで処理できるファイルの数の推奨制限はありません。パフォーマンスは、システムのリソースに依存します。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p112">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case. Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="ed54f-145">ファイルのフィルタ リング</span><span class="sxs-lookup"><span data-stu-id="ed54f-145">Filtering files</span></span>

<span data-ttu-id="ed54f-p113">ユーザー定義のラベルは、プロセス、またはその他のタスクから除外するファイルのセットを関連付けることができます。各プロセスのセッションでは、バッチ ID に関連付けられています。バッチ ID は、関連性のエキスパートに表示されているは、これを行うユーティリティを使用して、検索、現在のバッチのフィルターを追加して、ユーザー定義のラベルを持つすべての適切なファイルへのタグ付けをします。</span><span class="sxs-lookup"><span data-stu-id="ed54f-p113">A user-defined label can be associated with a set of files to exclude them from Process or other tasks. Each Process session is associated with a batch ID. Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ed54f-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed54f-149">See also</span></span>

[<span data-ttu-id="ed54f-150">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ed54f-150">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ed54f-151">プロセス モジュールを実行して、データの読み込み</span><span class="sxs-lookup"><span data-stu-id="ed54f-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ed54f-152">プロセス モジュールの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="ed54f-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

