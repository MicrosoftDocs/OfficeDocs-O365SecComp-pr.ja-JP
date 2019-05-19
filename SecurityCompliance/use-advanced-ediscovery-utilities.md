---
title: Office 365 の高度な電子情報開示ユーティリティを使用する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Office 365 の高度な電子情報開示のユーティリティ (ケースログ、クリアデータ、プロセスエラー、関連性の変更、透過性の分析など) について説明します。  '
ms.openlocfilehash: df769ddddd37284da50bc715444f2bf928307706
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157959"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="7fb2a-103">Office 365 の高度な電子情報開示ユーティリティを使用する</span><span class="sxs-lookup"><span data-stu-id="7fb2a-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="7fb2a-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="7fb2a-106">アドバンスト eDiscovery で表示および使用できるユーティリティは、コンテキストおよびユーザーの役割によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="7fb2a-107">ケースログ</span><span class="sxs-lookup"><span data-stu-id="7fb2a-107">Case log</span></span>

<span data-ttu-id="7fb2a-108">ケースログには、アプリケーション処理アクティビティの詳細な一覧が用意されています。これは、追跡、トラブルシューティング、およびエラーと警告への対処に使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="7fb2a-109">ログは、ホストまたはサーバー上でローカルに生成して保存することも、電子メールアドレスに直接送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="7fb2a-110">ログファイルは、クライアントのコンピューターにダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="7fb2a-111">[クライアントダウンロード] オプションは、構成とユーザーの役割に従って有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="7fb2a-112">メニューバーで、[ **Cogwheel** ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="7fb2a-113">[**設定およびユーティリティ\>ユーティリティ**] タブで、[**ケース\>ログのセットアップ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="7fb2a-114">**ログレベル**を次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="7fb2a-115">**標準**: 基本的なログデータを含みます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="7fb2a-116">通常、このオプションは監視に必要なもので、特に推奨されていない限り、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="7fb2a-117">**最小**: 非常に大きなケースで使用され、最新のデータのみを返します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="7fb2a-118">[**ケースログの実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-118">Click **Run Case log**.</span></span> <span data-ttu-id="7fb2a-119">ログが生成され、パスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="7fb2a-120">現在のタスクと最後のタスクの進捗状況の情報が [タスクの状態] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="7fb2a-121">データをクリアする</span><span class="sxs-lookup"><span data-stu-id="7fb2a-121">Clear data</span></span>

<span data-ttu-id="7fb2a-122">ケースデータを削除または再初期化する必要がある場合は、データベースインスタンスを初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="7fb2a-123">データのクリアユーティリティは、ケースデータベース、テキストファイル、ケースフォルダー、および蓄積された結果から、指定されたすべてのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="7fb2a-124">この関数は、管理者のみが実行できます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7fb2a-125">この操作は元に戻すことができず、エキスパートによって実行されるすべての関連性のタグ付けと分析がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="7fb2a-126">必要に応じて、データのバックアップを保存します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="7fb2a-127">このオプションは細心の注意を払って使用してください。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-127">Use this option with extreme care.</span></span> <span data-ttu-id="7fb2a-128">タグ付けされたファイルを削除すると、関連性の結果に影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="7fb2a-129">メニューバーで、[ **Cogwheel** ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="7fb2a-130">[**設定およびユーティリティ\>ユーティリティ**] タブで、[**データ\>セットアップのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="7fb2a-131">初期化する情報のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="7fb2a-132">**関連性**: 関連して実行されたすべての作業を削除します。ロードの定義、および読み込みに対するファイルの関連付けを含みます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="7fb2a-133">すべてのサンプルとタグ付けが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="7fb2a-134">**ほぼ重複した電子メールスレッド**: ほぼ重複した電子メールスレッドのすべての分析情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="7fb2a-135">**Themes**: テーマに関連するデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="7fb2a-136">**履歴のエクスポート**: エクスポートバッチの履歴情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="7fb2a-137">[**データのクリア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-137">Click **Clear data**.</span></span> <span data-ttu-id="7fb2a-138">ケースデータはクリアされます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-138">The case data is cleared.</span></span> <span data-ttu-id="7fb2a-139">現在のタスクと最後のタスクの進捗状況の情報が [**タスクの状態**] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="7fb2a-140">関連性の変更</span><span class="sxs-lookup"><span data-stu-id="7fb2a-140">Modify Relevance</span></span>

<span data-ttu-id="7fb2a-141">このセクションでは、関連性サンプルをスキップまたはロールバックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="7fb2a-142">メニューバーで、[ **Cogwheel** ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="7fb2a-143">[**設定およびユーティリティ\>ユーティリティ**] タブで、[**関連性の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="7fb2a-144">次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="7fb2a-145">[現在**のサンプルをスキップする]-現在のユーザーの**場合: このタグは、ユーティリティを実行しているユーザーのオープンケースサンプルに含まれるタグなしファイルすべてを**skip**としてタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="7fb2a-146">**スキップ**としてタグ付けされたファイルでは、関連性処理は実行されません。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="7fb2a-147">**現在のサンプル**をすべてスキップします。すべてのユーザーについて開いているすべてのサンプルにタグ付けされたすべてのタグのないファイルを**skip**としてタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="7fb2a-148">ユーザーが現在、サンプルにタグ付けしている場合、このオプションは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="7fb2a-149">**最後のサンプルをロールバック**する: 最後に完了した関連性トレーニングサンプルは、「計算」プロセスの前後であるかどうかに関係なく、ロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="7fb2a-150">キャッチアップサンプルのロールバックは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="7fb2a-151">[ \*\*\*\* 実行] をクリックして実行します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="7fb2a-152">透過性の分析</span><span class="sxs-lookup"><span data-stu-id="7fb2a-152">Transparency analysis</span></span>

<span data-ttu-id="7fb2a-153">透過性分析ユーティリティを使用すると、ファイルとそれに割り当てられている関連性スコアを詳細に表示できます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="7fb2a-154">このレポートは、上級電子情報開示によって割り当てられた関連性と比較して、正当性チェックとして、または人間の校閲者によって定義されたファイルの関連性を比較するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="7fb2a-155">関連性スコアに加えて、Advanced eDiscovery はキーワードコンテキストを考慮するキーワードの重みを計算して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="7fb2a-156">ファイル内の同じ単語には、コンテキストと場所に応じて異なるウエイトを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="7fb2a-157">各キーワードには、色の強度を黄色から濃いオレンジ、さまざまな階調のグレーにそれぞれ使用してマークされています。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="7fb2a-158">色のコーディングを使用して、関連性スコアに対する単語の相対正または負の貢献度を視覚的に示すことができます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="7fb2a-159">複数の問題があるケースシナリオでは、各問題について透過的な分析レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="7fb2a-160">メニューバーで、[ **Cogwheel** ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="7fb2a-161">[**設定およびユーティリティ\>ユーティリティ**] タブで、[**透過\>分析の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="7fb2a-162">\* \* ファイル ID \* \* で、処理するファイルのファイル ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="7fb2a-163">[**問題**] リストで、関連する問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="7fb2a-164">[**透過分析**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="7fb2a-165">完了すると、ファイルの透過性分析レポートが表示されます。これは、マークされたキーワードの色が全体的な関連性スコアとどのように関連しているかを示しています。</span><span class="sxs-lookup"><span data-stu-id="7fb2a-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7fb2a-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fb2a-166">See also</span></span>

[<span data-ttu-id="7fb2a-167">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7fb2a-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7fb2a-168">ケースとテナントの設定の定義</span><span class="sxs-lookup"><span data-stu-id="7fb2a-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

