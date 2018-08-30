---
title: Office 365 Advanced eDiscovery で分析オプションを設定する
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: '分析プロセスでは、Office 365 の高度な電子的証拠開示、重複の近くに、電子メールのスレッド、テーマなどのオプションを設定する手順を確認します。  '
ms.openlocfilehash: a0ebbadb180321a3094cb1056ed8e0e6500ee66a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532140"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="8cec0-103">Office 365 Advanced eDiscovery で分析オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="8cec0-103">Set Analyze options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="8cec0-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="8cec0-106">[詳細設定] は、電子的証拠開示は、Analyze を実行する前に、分析のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="8cec0-107">分析オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-107">Set Analyze options</span></span>

<span data-ttu-id="8cec0-p102">オープン**準備\>分析** \> **セットアップ**します。次のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p102">Open **Prepare \> Analyze** \> **Setup**. The following window is displayed.</span></span>
  
![[分析設定] のオプション](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="8cec0-p103">**重複の近くと電子メールのスレッド**解析を実行する場合は、このチェック ボックスをオンにします。既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p103">**Near-duplicates and email threads** Check this box if you want to run the analysis. It is selected by default.</span></span> 
  
 <span data-ttu-id="8cec0-113">**ドキュメントの類似性**Near 重複のしきい値の値を入力するか、65% の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-113">**Document similarity**Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="8cec0-p104">**テーマ**すべてのファイルを処理し、それらにテーマを割り当てるには、このボックスをチェックします。既定では、このチェック ボックスはオフです。テーマの処理を実行する場合は、次のオプションを入力します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p104">**Themes**Check this box to process all files and assign themes to them. By default, this check box is not selected. Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="8cec0-p105">**テーマの最大数**入力するか、作成するテーマの数の値を選択します。デフォルトは 200 です。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p105">**Max number of themes**Enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8cec0-p106">テーマの数を増やすことを一般化するテーマの機能と同様に、パフォーマンスに影響します。テーマの回数が多いほどより詳細なこれらは。一連の 50 のテーマは、「バスケット ボール、スパー、はさみ、Lakers」などのテーマを含める場合など、300 のテーマは、別のテーマを含めることがあります:「を受け、」、「はさみ」、"Lakers"です。テーマを認識していない「バスケット ボール」する必要があるし、ECA のこの機能を使用すると、テーマを表示する「バスケット ボール」も有効です。ですが、「バスケット ボール」という単語を読み取ることはありませんし、わからないことがあることを確認して、適切なバスケット ボールのテーマは、2 人とはさみではなく上に移動する項目が起動し、髪の毛のために使用する処理に多くのテーマがある場合。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p106">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="8cec0-p107">**候補のテーマ**テーマの処理を制御するためのテーマの単語を提案することができます。高度な電子的証拠開示はこれらの単語の候補に集中し、1 つまたは複数と関連するテーマを「最大のテーマの数」設定基づくを作成しようとしていますいます。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p107">**Suggested themes**You can suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="8cec0-p108">などの修正候補の単語は、「コンピューター」、「最大の数のテーマ」として「2」を指定した場合は、高度な電子的証拠開示は、word の [コンピューター] に関連する 2 つのテーマを生成しようとします。2 つのテーマがありますコンピューター ソフトウェア」と「ハードウェア」、などです。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p108">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![提示されたテーマの追加](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="8cec0-129">表示、追加、または提案されたテーマの編集をするには、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cec0-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="8cec0-p109">**候補テーマ**パネルで、[**追加**] をクリックします![のアイコンを追加](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)テーマを追加するアイコン。**提示されたテーマの追加**パネルで、カンマで区切って、単語を追加します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p109">In the **Suggested themes** panel, click the **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme. In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="8cec0-132">**テーマの数**] (既定では 1 テーマ) これらの単語を生成しようとして、高度な電子的証拠開示のテーマ数を決定する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="8cec0-133">[**保存**] をクリックして、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8cec0-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8cec0-p110">テーマの合計数には、テーマ提示にはが含まれています。合計の提案されたテーマは、全体のテーマを超えることはできません。合計のテーマを基準にして多くの提案されたテーマがある場合は、テーマのほとんどは専用にするテーマを提案するためには、のみいくつかの「小説」テーマ名は、システムにより検出されます。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p110">The total number of themes includes Suggested Themes. The total Suggested Themes cannot exceed the total themes. If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="8cec0-137">**モード**」ドロップ ダウン リストからは、**テーマ**のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="8cec0-138">**を作成するモデルを適用し、**: ファイルのセグメントからのモデルでのテーマを計算し、それらの間でファイルを配布します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="8cec0-p111">**モデルの作成**: ファイルのセグメントからのテーマのモデルを計算します。ファイルに分割することの適用処理は、後で個別に実行されます。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p111">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="8cec0-p112">**適用モデル**: モデルが以前に作成し、適用されていないかどうかにのみ、このオプションが表示されます。これは、テーマに基づいてファイルで除算します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p112">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="8cec0-143">ことも[設定は無視して](set-ignore-text-in-advanced-ediscovery.md)、[分析の詳細設定を設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)の分析。</span><span class="sxs-lookup"><span data-stu-id="8cec0-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="8cec0-p113">これらのオプションを設定すると、 **Analyze**を実行するをクリックします。[ビューの分析の結果](view-analyze-results-in-advanced-ediscovery.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cec0-p113">After you've set these options, click **Analyze** to run. [View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8cec0-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cec0-146">See also</span></span>

[<span data-ttu-id="8cec0-147">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8cec0-147">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8cec0-148">ドキュメントの類似性を理解します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8cec0-149">無視するテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="8cec0-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8cec0-150">分析設定の拡張設定</span><span class="sxs-lookup"><span data-stu-id="8cec0-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8cec0-151">分析結果の表示</span><span class="sxs-lookup"><span data-stu-id="8cec0-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

