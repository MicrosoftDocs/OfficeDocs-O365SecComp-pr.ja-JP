---
title: Office 365 Advanced eDiscovery で簡易分析を使用する
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: 電子的証拠開示の Office 365 の詳細設定の高速分析モードを実行する方法を学習します。
ms.openlocfilehash: a71e6775b1116e805e455815dca53a727d887809
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532013"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="5c058-103">Office 365 Advanced eDiscovery で簡易分析を使用する</span><span class="sxs-lookup"><span data-stu-id="5c058-103">Use Express Analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="5c058-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="5c058-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="5c058-106">**分析を高速**を使用するケースを迅速に分析し、結果をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5c058-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="5c058-p102">重複の近くを計算し、電子メールのスレッドとテーマを計算するのには、高速分析を使用できます。[高速分析のための高度な設定](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)のテーマ、ドキュメントの類似性、およびエクスポート ファイルの特定のパラメーターを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5c058-p102">You can use express analysis to calculate near-duplicates and email threads and calculate themes. You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="5c058-109">高速分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="5c058-109">Run Express analysis</span></span>

1. <span data-ttu-id="5c058-110">**高速分析**(1)] タブを有効にするためのコンテナーを選択して、* * 分析を高速 * * (2) と **[詳細設定**] ボタン。</span><span class="sxs-lookup"><span data-stu-id="5c058-110">In the **Express analysis** (1) tab, select a container to enable the ** Express analysis ** (2), and **Advanced settings** buttons.</span></span> 
    
    ![高速分析のページのスクリーン ショット](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="5c058-112">[**分析のパラメーター**。</span><span class="sxs-lookup"><span data-stu-id="5c058-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="5c058-p103">解析を実行する場合は、**重複の近くを計算し電子メールのスレッド**を確認します。既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="5c058-p103">Check **Calculate near-duplicates and email threads** if you want to run the analysis. It is selected by default.</span></span> 
    
  - <span data-ttu-id="5c058-p104">すべてのファイルを処理し、それらにテーマを割り当てるには、**テーマの計算**を確認してください。既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="5c058-p104">Check **Calculate Themes** to process all files and assign themes to them. It is selected by default.</span></span> 
    
3. <span data-ttu-id="5c058-117">[**エクスポート先**。</span><span class="sxs-lookup"><span data-stu-id="5c058-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="5c058-118">ローカル コンピューターにダウンロードするのには**ローカル マシンにダウンロード**を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5c058-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="5c058-119">**Azure blob のユーザー定義のエクスポート]** をオンにした場合、コンテナーの URL と SAS のトークンも指定できます。</span><span class="sxs-lookup"><span data-stu-id="5c058-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5c058-p105">エクスポート パッケージが格納されているユーザーは Azure blob を定義、データは高度な電子的証拠開示によって管理されなくなります。Azure blob が管理します。つまり場合は、大文字と小文字を削除すると、書き出されたファイルもに残ります Azure blob です。</span><span class="sxs-lookup"><span data-stu-id="5c058-p105">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery. it is managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="5c058-123">**将来のエクスポート ・ セッションのトークンを SAS の保存**: チェックすると、SAS のトークンが将来使用するための高度な電子的証拠開示の内部データベースに暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="5c058-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c058-p106">現在 SAS のトークンは、1 か月後に有効期限が切れます。最後のセッションを取り消す必要が複数の月の後にダウンロードしようとする場合は、もう一度エクスポートし、します。</span><span class="sxs-lookup"><span data-stu-id="5c058-p106">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="5c058-126">既定の高速分析を開始するには、**分析を高速**での設定を選択し、[**タスクの状態**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c058-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="5c058-127">[**タスクの状態**] ページは、高速の実行に関する詳細を表示する**プロセス**、**分析**および**エクスポート**のタブを展開できます。</span><span class="sxs-lookup"><span data-stu-id="5c058-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![スクリーン ショットの高度な電子的証拠開示高速分析タスクの状態] ページ](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="5c058-129">**分析の概要を高速**実行に関する詳細な情報を一覧表示するページを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c058-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="5c058-p107">**分析の概要**ページの下部に分析ファイルの tp をローカル コンピューターにダウンロードする**ダウンロードの最後のセッション**をクリックします。電子的証拠開示のエクスポート ツールをダウンロードし、電子的証拠開示のエクスポート ・ ツールにキーのエクスポートをペーストする必要が最初にします。</span><span class="sxs-lookup"><span data-stu-id="5c058-p107">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer. You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="5c058-132">高速分析の詳細設定</span><span class="sxs-lookup"><span data-stu-id="5c058-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="5c058-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="5c058-133"></span></span>

<span data-ttu-id="5c058-134">**詳細設定**を既定の高速分析パラメーターを変更するのにはオプションで設定できます。</span><span class="sxs-lookup"><span data-stu-id="5c058-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="5c058-135">[ **Analyze** ] セクション。</span><span class="sxs-lookup"><span data-stu-id="5c058-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="5c058-136">**ほぼ重複と電子メールのスレッド**、**文書の類似性**の値を入力または 65% の既定値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="5c058-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="5c058-p108">**テーマの最大数**を入力するか、作成するテーマの数の値を選択します。デフォルトは 200 です。</span><span class="sxs-lookup"><span data-stu-id="5c058-p108">In the **Max number of themes** enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5c058-p109">テーマの数を増やすことを一般化するテーマの機能と同様に、パフォーマンスに影響します。テーマの回数が多いほどより詳細なこれらは。一連の 50 のテーマは、「バスケット ボール、スパー、はさみ、Lakers」などのテーマを含める場合など、300 のテーマは、別のテーマを含めることがあります:「を受け、」、「はさみ」、"Lakers"です。テーマを認識していない「バスケット ボール」する必要があるし、ECA のこの機能を使用すると、テーマを表示する「バスケット ボール」も有効です。ですが、「バスケット ボール」という単語を読み取ることはありませんし、わからないことがあることを確認して、適切なバスケット ボールのテーマは、2 人とはさみではなく上に移動する項目が起動し、髪の毛のために使用する処理に多くのテーマがある場合。</span><span class="sxs-lookup"><span data-stu-id="5c058-p109">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="5c058-p110">**候補テーマ**テーマ テーマの処理を制御する候補を表示する**変更**を選択します。高度な電子的証拠開示はこれらの単語の候補に集中し、1 つまたは複数と関連するテーマを「最大のテーマの数」設定基づくを作成しようとしていますいます。</span><span class="sxs-lookup"><span data-stu-id="5c058-p110">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="5c058-p111">などの修正候補の単語は、「コンピューター」、「最大の数のテーマ」として「2」を指定した場合は、高度な電子的証拠開示は、word の [コンピューター] に関連する 2 つのテーマを生成しようとします。2 つのテーマがありますコンピューター ソフトウェア」と「ハードウェア」、などです。</span><span class="sxs-lookup"><span data-stu-id="5c058-p111">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![提示されたテーマの追加](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="5c058-149">**モード**」ドロップ ダウン リストからは、**テーマ**のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c058-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="5c058-150">**を作成するモデルを適用し、**: ファイルのセグメントからのモデルでのテーマを計算し、それらの間でファイルを配布します。</span><span class="sxs-lookup"><span data-stu-id="5c058-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="5c058-p112">**モデルの作成**: ファイルのセグメントからのテーマのモデルを計算します。ファイルに分割することの適用処理は、後で個別に実行されます。</span><span class="sxs-lookup"><span data-stu-id="5c058-p112">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="5c058-p113">**適用モデル**: モデルが以前に作成し、適用されていないかどうかにのみ、このオプションが表示されます。これは、テーマに基づいてファイルで除算します。</span><span class="sxs-lookup"><span data-stu-id="5c058-p113">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="5c058-155">[**エクスポート**] セクションでします。</span><span class="sxs-lookup"><span data-stu-id="5c058-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="5c058-156">で**バッチのエクスポートを選択**します。</span><span class="sxs-lookup"><span data-stu-id="5c058-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="5c058-157">**バッチのエクスポート**] ボックスの一覧で、バッチの名前を選択またはエクスポート バッチ 01、(既定のバッチ) に結果をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5c058-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="5c058-p114">既存のケースに追加した新しいファイルの結果をエクスポートするには、現在のバッチを続行します。バッチ内のセッションを作成、同じバッチ番号を選択および**作成するセッションのエクスポート**] をクリックするには、前のバッチでは、増分方式で同じパラメーターをエクスポートするのにはこのオプションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5c058-p114">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="5c058-p115">新しいバッチにエクスポートする場合の [**追加**] をクリックします![のアイコンを追加](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)および**バッチ名**に新しい名前を入力 (または既定値をそのまま使用) と**バッチの説明**で説明します。**[Ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c058-p115">To export to a new batch, click **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
  - <span data-ttu-id="5c058-162">バッチの名前または説明を編集するには、**バッチのエクスポート**の名前を選択して、[**編集**] をクリックして![[編集] アイコン](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)、し、フィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="5c058-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c058-p116">エクスポート バッチのセッションを実行すると、それらを削除することはできません。さらに、最初のセッションが実行されるにはいくつかのパラメーターのみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="5c058-p116">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="5c058-165">重複データのエクスポートのバッチを作成するには、**重複データのエクスポートのバッチ**を選択します![重複データのエクスポートのバッチ アイコンを作成する](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)パネルの名前と重複するバッチの説明を入力するとします。</span><span class="sxs-lookup"><span data-stu-id="5c058-165">To create a duplicate export batch, choose **Duplicate export batch**![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="5c058-166">[**削除**] に、エクスポートのバッチを削除するには、![バッチ エクスポート アイコンを削除](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。</span><span class="sxs-lookup"><span data-stu-id="5c058-166">To delete an export batch, choose **Delete**![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="5c058-167">バッチの履歴を表示するには、**バッチの履歴**を選択して![の履歴の表示アイコン](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="5c058-167">To view the history of a batch, choose **Batch history**![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="5c058-p117">定義する p [ **opulation:** 、エクスポートのバッチの設定を微調整する場合は、**関連性の高いカットオフ スコアの上のファイルのみを含める**と**絞り込みのエクスポートのバッチ**を選択します。**カットオフ スコアの妥当性上のファイルのみを含む**を選択した場合は、**問題**が有効であり、ファイルの関連性スコアが選択されている問題に対するカットオフ スコアより高い場合は、ファイルがエクスポートします。除外される場合を除き、ファイルがエクスポートされます、'**確認のため**のフィルターです。**エクスポートのバッチを絞り込み**を選択した場合、**重複除外**と**の確認] でフィルター フィールド**ラジオ ボタンが有効にします。選択した場合 **、重複除外**、し、重複したファイルがするフィルターを定義したポリシーに従って: [レベル (既定値) の場合: 全体の場合は、重複するファイルのすべてのセットから 1 つを除くすべてのファイルは除外に対してされます。管理者レベル: 同じ書の重複したファイルのすべてのセットから 1 つを除くすべてのファイルは除外に対してされます。すべての重複するファイルのレコードは、エクスポート出力で使用できます。**'レビュー' のフィルター**フィールドを選択した場合は、 **'レビュー' の**フィールドの設定を入力するのには、**メタデータの変更**を選択します。パッケージ コンテンツのソース ファイルを含めることを**含む入力ファイル**を選択します。エクスポート処理を高速化するには、このオプションをオフにすることができます。ネイティブのファイルがどのような場合にエクスポートされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5c058-p117">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch. If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported. The file will be exported unless it's excluded by the ' **For review** filter. If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled. If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped. A record of all duplicate files is available in export output. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files**to include source files in the package content. You can clear this option to speed up the export process. Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="5c058-179">**を定義するメタデータ**、下には、**テンプレートをエクスポート**します (セッション) ごとに次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="5c058-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="5c058-p118">**標準**: 基本的な項目のデータ、メタデータ、およびプロパティのセットです。インポート データが高度な電子的証拠開示で既に処理されて、ファイルが既に含まれているシステムにアップロードされているデータをエクスポートするときは、このオプションを使用します。既定では、列が作成され、入力のテンプレートをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5c058-p118">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="5c058-p119">**すべて**: すべてのデータ処理を行うと分析との関連性のスコアを含む標準のメタデータの完全なセットです。このテンプレートは、高度な電子的証拠開示の処理を実行すると、最初に、外部システムにアップロードするファイル データに必要です。</span><span class="sxs-lookup"><span data-stu-id="5c058-p119">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="5c058-185">**問題**:**すべての懸案事項**を選択または作成した特定の問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c058-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="5c058-186">**[Ok]**、[詳細設定を保存するのには**既定値に戻す**を既定値を使用するか、詳細設定の設定をキャンセルするのには**キャンセル**を選択してください。</span><span class="sxs-lookup"><span data-stu-id="5c058-186">Choose **OK**to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5c058-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c058-187">See also</span></span>
<span data-ttu-id="5c058-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="5c058-188"></span></span>

[<span data-ttu-id="5c058-189">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5c058-189">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)

