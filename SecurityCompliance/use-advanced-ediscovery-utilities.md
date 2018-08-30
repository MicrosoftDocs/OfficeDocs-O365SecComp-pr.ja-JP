---
title: Office 365 Advanced eDiscovery のユーティリティを使用する
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Office 365 の高度な電子的証拠開示、サポート ・ リクエストのログを含むユーティリティについて説明、データをオフに、エラーを処理する、関連性、および透過性の分析を変更します。  '
ms.openlocfilehash: a68c98dd353971fcaa13fdc6b8e12bcf00c2faf0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531632"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="d7c34-103">Office 365 Advanced eDiscovery のユーティリティを使用する</span><span class="sxs-lookup"><span data-stu-id="d7c34-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="d7c34-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d7c34-106">表示と高度な電子的証拠開示に利用可能なユーティリティは、コンテキスト、ユーザーの役割によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d7c34-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="d7c34-107">ケース ログ</span><span class="sxs-lookup"><span data-stu-id="d7c34-107">Case log</span></span>

<span data-ttu-id="d7c34-p102">ケースのログは、管理、トラブルシューティング、およびエラーや警告に対処するために使用できるアプリケーションの処理の活動の詳細な一覧を提供します。ログの生成しホストまたはサーバーにローカルに保存または電子メール アドレスに直接送信できます。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p102">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings. The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="d7c34-p103">ログ ファイルは、クライアントのコンピューターにもダウンロードできます。クライアントのダウンロード オプションを有効または構成やユーザーの役割に応じて無効になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p103">The log file can also be downloaded to the client's computer. The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="d7c34-112">メニュー ・ バーで、[ **Cogwheel** ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7c34-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="d7c34-113">**の設定とユーティリティ\>ユーティリティ**] タブで、**ケース ログ\>セットアップ**。</span><span class="sxs-lookup"><span data-stu-id="d7c34-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="d7c34-114">次のように**ログ レベル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="d7c34-p104">**標準**: 基本的なログ データが含まれています。このオプションは、通常を監視する必要は、それ以外の場合に推奨されていない限り、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p104">**Standard**: Includes the basic log data. This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="d7c34-117">**最小限**: 非常に大きい場合は、使用され、最新のデータのみを返します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="d7c34-p105">**ケースの実行ログ**をクリックします。ログが生成され、パスが表示されます。[状態] 作業ウィンドウは、現在および過去のタスクのタスクの進捗状況の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p105">Click **Run Case log**. The log is generated and path is displayed. The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="d7c34-121">データを消去</span><span class="sxs-lookup"><span data-stu-id="d7c34-121">Clear data</span></span>

<span data-ttu-id="d7c34-p106">削除または大文字のデータを再初期化する必要がある場合は、データベース ・ インスタンスを初期化してください。データを消去ユーティリティは、サポート案件のデータベース、テキスト ファイル、ケース フォルダー、および蓄積された結果から指定したすべてのエントリを削除します。機能は、管理者によってのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p106">If it is necessary to delete or reinitialize case data, the database instance must be initialized. The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results. The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d7c34-p107">この操作は取り消すことはできません、関連性のタグを付けると、エキスパートによる分析のすべてがクリアします。必要に応じて、データのバックアップを保存します。細心の注意とは、このオプションを使用します。タグとランク付けのファイルを削除すると関連性の結果に影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p107">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert. Save a backup of data, if necessary. Use this option with extreme care. Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="d7c34-129">メニュー ・ バーで、[ **Cogwheel** ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7c34-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="d7c34-130">**の設定とユーティリティ\>ユーティリティ**] タブで、**データをオフに\>セットアップ**。</span><span class="sxs-lookup"><span data-stu-id="d7c34-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="d7c34-131">情報を初期化するためのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="d7c34-p108">**関連性**: 関連性、荷重の定義など、ロードするファイルの関連付けで行ったすべての作業を削除します。すべてのサンプルを削除してタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p108">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads. It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="d7c34-134">**重複の近くと電子メールのスレッド**: 重複の近くのすべての分析情報を削除し、電子メールのスレッドです。</span><span class="sxs-lookup"><span data-stu-id="d7c34-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="d7c34-135">**テーマ**: テーマに関連するデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="d7c34-136">**履歴のエクスポート**: エクスポートのバッチの履歴情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="d7c34-p109">**データを消去**] をクリックします。大文字のデータが消去されます。現在および過去のタスクのタスクの進捗状況の情報は、**タスクの進捗状況**ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p109">Click **Clear data**. The case data is cleared. The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="d7c34-140">関連性の高さを変更します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-140">Modify Relevance</span></span>

<span data-ttu-id="d7c34-141">このセクションでは、スキップしたり、関連性のサンプルを元に戻す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="d7c34-142">メニュー ・ バーで、[ **Cogwheel** ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7c34-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="d7c34-143">**の設定とユーティリティ\>ユーティリティ**] タブで、**変更の妥当性**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="d7c34-144">オプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="d7c34-p110">**現在のユーザーの現在のサンプルのスキップ**: これはタグを**スキップ**] としてユーティリティを実行するユーザーのオープン ケースのサンプル内のすべてのタグ付けされていないファイルです。**スキップ**としてタグ付けされたファイルに関連性の処理は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p110">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility. Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="d7c34-p111">**スキップ ・ サンプルの現在の開いているすべてのサンプル**: これはタグを**スキップ**] として開いているすべてのサンプルのすべてのタグ付けされていないファイルのすべてのユーザーです。ユーザーは、サンプルのタグ付けされている場合、このオプションは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p111">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users. This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="d7c34-p112">**最後のサンプルを元に戻す**: 最後には、関連性の高いトレーニング サンプルはロールバックされます、「再計算」プロセスの前後にあるかどうかに関係なくが完了しました。キャッチアップ サンプルのロールバックは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p112">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process. Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="d7c34-151">実行する**実行**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7c34-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="d7c34-152">透明度の分析</span><span class="sxs-lookup"><span data-stu-id="d7c34-152">Transparency analysis</span></span>

<span data-ttu-id="d7c34-p113">透明度分析ユーティリティは、ファイルとその割り当てられた関連性スコアの詳細を表示を使用できます。正当性チェックとして、または高度な電子的証拠開示によって割り当てられているとの関連性と比較して、人間のレビューアーによって定義されているファイルとの関連性を比較するレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p113">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score. The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="d7c34-p114">関連性のスコアだけでなく高度な電子的証拠開示が計算し、キーワードのコンテキストを検討しているキーワードの重みが割り当てられます。ファイルで同じ単語には、コンテキスト、および場所によって、別の重量を割り当てることができます。各キーワードは、黄色から濃いオレンジ色に至るまで、灰色の網掛けをさまざまな色の輝度の増加のスケールを使用してマークされています。色の設定は、視覚的に示すために使用単語の相対的な関連性スコアに正または負の影響を与えた。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p114">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context. The same word in a file can be assigned different weights, depending on context and location. Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray. Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="d7c34-159">複数の問題のシナリオで、各問題の透明度の分析レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="d7c34-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="d7c34-160">メニュー ・ バーで、[ **Cogwheel** ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7c34-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="d7c34-161">**の設定やユーティリティ\>ユーティリティ**] タブで、**の透過性の分析\>セットアップ**。</span><span class="sxs-lookup"><span data-stu-id="d7c34-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="d7c34-162">* * ファイル ID * * を処理するファイルのファイル ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-162">In ** File ID **, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="d7c34-163">**懸案事項**の一覧に関連する問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="d7c34-p115">**透明度の分析**] をクリックします。完了すると、ファイルの透明度の分析レポートが表示になり、マークされたキーワードの色が全体の関連性のスコアに関連する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-p115">Click **Transparency analysis**. Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d7c34-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7c34-166">See also</span></span>

[<span data-ttu-id="d7c34-167">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d7c34-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d7c34-168">ケースとテナントの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="d7c34-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

