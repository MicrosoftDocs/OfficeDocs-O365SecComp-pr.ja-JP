---
title: Office 365 の高度な電子情報開示の分析オプションを設定する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 'Office 365 の Advanced eDiscovery で分析プロセスのオプションを設定する手順を確認します。これには、ほぼ重複、電子メールのスレッド、テーマなどが含まれます。  '
ms.openlocfilehash: 4689638f5cebe2ef17fcea5a13ff06edc29e5930
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260899"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="36e0c-103">Office 365 の高度な電子情報開示の分析オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="36e0c-103">Set Analyze options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="36e0c-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="36e0c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="36e0c-106">Advanced eDiscovery で、analyze を実行する前に analyze オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="36e0c-107">分析オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="36e0c-107">Set Analyze options</span></span>

<span data-ttu-id="36e0c-108">\> [ **Analyze \>の準備**]**セットアップ**を開きます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="36e0c-109">次のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-109">The following window is displayed.</span></span>
  
![[分析設定] のオプション](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="36e0c-111">**ほぼ重複した電子メールスレッド**分析を実行する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="36e0c-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="36e0c-112">既定では選択されています。</span><span class="sxs-lookup"><span data-stu-id="36e0c-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="36e0c-113">**ドキュメントの類似性**[重複した場合のしきい値」の値を入力するか、既定値の 65% をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="36e0c-114">**テーマ**すべてのファイルを処理して、テーマを割り当てるには、このボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="36e0c-114">**Themes**Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="36e0c-115">既定では、このチェックボックスはオフになっています。</span><span class="sxs-lookup"><span data-stu-id="36e0c-115">By default, this check box is not selected.</span></span> <span data-ttu-id="36e0c-116">テーマ処理を実行する場合は、次のオプションを入力します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="36e0c-117">**テーマの最大数**作成するテーマの数の値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-117">**Max number of themes**Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="36e0c-118">既定値は 200 です。</span><span class="sxs-lookup"><span data-stu-id="36e0c-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="36e0c-119">テーマの数を増やすと、パフォーマンスに影響が及び、一般化するテーマの能力が向上します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="36e0c-120">テーマの数が多いほど、より詳細なものになります。</span><span class="sxs-lookup"><span data-stu-id="36e0c-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="36e0c-121">たとえば、50テーマのセットに "バスケットボール、Spurs、Clippers、Lakers" などのテーマが含まれているとします。300テーマには、"Spurs"、"Clippers"、"Lakers" の各テーマが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="36e0c-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="36e0c-122">テーマ "バスケットボール" を認識していない場合に、ECA でこの機能を使用すると、"バスケットボール" というテーマが役に立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="36e0c-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="36e0c-123">しかし、処理に含まれているテーマの数が多すぎると、"バスケットボール" という単語は表示されず、Spurs と Clippers が、起動時に表示されて、ヘアサイトで使用されるアイテムではなく、確認が適切なバスケットボールテーマであることがわかりません。</span><span class="sxs-lookup"><span data-stu-id="36e0c-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="36e0c-124">**推奨**されるテーマテーマの単語を提案して、テーマの処理を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="36e0c-125">高度な電子情報開示では、推奨される単語に焦点を絞り、"テーマの最大数" の設定に基づいて1つ以上の関連するテーマの作成を試みます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="36e0c-126">たとえば、提案された単語が "computer" で、"2" が "テーマの最大数" として指定されている場合、上級電子情報開示では、"computer" という単語に関連する2つのテーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="36e0c-127">この2つのテーマは、「コンピューターソフトウェア」と「コンピュータハードウェア」などです。</span><span class="sxs-lookup"><span data-stu-id="36e0c-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![提示されたテーマの追加](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="36e0c-129">提案されたテーマを表示、追加、または編集するには、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36e0c-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="36e0c-130">[推奨された**テーマ**] パネル\*\*\*\* ![で、[](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)追加] アイコンアイコンをクリックしてテーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-130">In the **Suggested themes** panel, click the **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="36e0c-131">[**推奨テーマの追加**] パネルで、単語をコンマで区切って追加します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="36e0c-132">[**テーマの数**] で、詳細電子情報開示によって生成されるテーマの数を決定する値を選択します (既定では1テーマ)。</span><span class="sxs-lookup"><span data-stu-id="36e0c-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="36e0c-133">[**保存**] をクリックし、ダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="36e0c-134">テーマの合計数には、提案されたテーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="36e0c-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="36e0c-135">推奨されるテーマの合計は、テーマ合計を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="36e0c-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="36e0c-136">テーマの総数に対して多数の推奨テーマがある場合は、ほとんどのテーマが提案されたテーマに特化されるので、いくつかの "" 斬新 "テーマのみがシステムによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="36e0c-137">**モード**ドロップダウンリストから [**テーマ**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="36e0c-138">**モデルの作成と適用**: モデルによって、ファイルのセグメントからテーマを計算し、それらの間でファイルを配布します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="36e0c-139">**Create model**: ファイルのセグメントからテーマモデルを計算します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="36e0c-140">ファイルを分割する処理は、別の時点で個別に実行されます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="36e0c-141">[**モデルの適用**]: このオプションは、モデルが以前に作成され、まだ適用されていない場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="36e0c-142">これにより、テーマに基づいてファイルが分割されます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="36e0c-143">また、[[無視] テキストを設定](set-ignore-text-in-advanced-ediscovery.md)し、[分析のために[詳細設定を分析](set-analyze-advanced-settings-in-advanced-ediscovery.md)] を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="36e0c-144">これらのオプションを設定した後、[ **Analyze** ] をクリックして実行します。</span><span class="sxs-lookup"><span data-stu-id="36e0c-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="36e0c-145">[分析結果の表示](view-analyze-results-in-advanced-ediscovery.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="36e0c-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="36e0c-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="36e0c-146">See also</span></span>

[<span data-ttu-id="36e0c-147">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="36e0c-147">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="36e0c-148">ドキュメントの類似点について</span><span class="sxs-lookup"><span data-stu-id="36e0c-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="36e0c-149">無視するテキストを設定する</span><span class="sxs-lookup"><span data-stu-id="36e0c-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="36e0c-150">分析設定の拡張設定</span><span class="sxs-lookup"><span data-stu-id="36e0c-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="36e0c-151">分析結果の表示</span><span class="sxs-lookup"><span data-stu-id="36e0c-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

