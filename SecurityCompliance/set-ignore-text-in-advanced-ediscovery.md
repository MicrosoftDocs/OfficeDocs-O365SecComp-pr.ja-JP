---
title: Office 365 Advanced eDiscovery の分析の [テキストを無視] オプションを設定する
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
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: '電子的証拠開示の Office 365 の詳細に分析し、プロセスのモジュールを使用する場合は、特定のテキストを無視するようにルールを定義する方法について説明します。  '
ms.openlocfilehash: eb7e7052979087b7dba98aac3b0c9ab75ec0d02a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532192"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="f8bd5-103">Office 365 Advanced eDiscovery の分析の [テキストを無視] オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="f8bd5-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="f8bd5-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f8bd5-p102">テキストを無視する機能は、次の高度な電子的証拠開示のモジュールのいずれかまたはすべてに適用できます: (近くの重複、電子メールのスレッド、テーマ) の分析と関連します。無視されたテキストは、関連性の高さで表示されているファイルには表示されませんし、分析と計算が無視される文字列を破棄します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-p102">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance. Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="f8bd5-p103">テキストを無視する機能が既に実行されたモジュールで定義されて、テキストを無視する設定今すぐ変更から保護されます。ただし、関連性の高いモジュールのテキストを無視する機能はいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-p103">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified. However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="f8bd5-110">無視するテキスト フィルターを適用する方法</span><span class="sxs-lookup"><span data-stu-id="f8bd5-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="f8bd5-p104">複数のテキストを無視するフィルターは、入力した順序で適用されます。適用される順序を変更するのにはそれらを削除し、目的の順序で再入力します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-p104">Multiple Ignore Text filters are applied in the order that they were entered. To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="f8bd5-113">例では、テキスト コンテンツの場合:「知らせ、CAROL BOB ALICE が DAVE 場合」は次のエントリのテキストを無視して、結果のサンプル。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="f8bd5-114">**テキスト エントリを無視します。**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="f8bd5-115">**結果**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-115">**Results**</span></span> <br/> |
|<span data-ttu-id="f8bd5-116">"ALICE"、"プライベートな BOB 佐賀明美</span><span class="sxs-lookup"><span data-stu-id="f8bd5-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="f8bd5-117">「デイブ知らせ」</span><span class="sxs-lookup"><span data-stu-id="f8bd5-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="f8bd5-118">"ALICE"、"ALICE が BOB CAROL」</span><span class="sxs-lookup"><span data-stu-id="f8bd5-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="f8bd5-119">「デイブ BOB CAROL の知らせ」</span><span class="sxs-lookup"><span data-stu-id="f8bd5-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="f8bd5-120">文字列が見つからなかったので、次のような無視の最初のテキストが適用された後、2 番目のテキストを無視するエントリが実装されていません。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="f8bd5-121">無視するテキストを定義するときに正規表現を使用</span><span class="sxs-lookup"><span data-stu-id="f8bd5-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="f8bd5-p105">無視するテキストを定義するとき使用する正規表現をサポートします。次に、正規表現の構文と使用方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-p105">Regular expressions are supported for use when defining Ignore Text. The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="f8bd5-124">削除する (無視)、行の終わりまでの開始からのテキスト。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="f8bd5-125">"Begin"が行では、この文字列の最初の出現します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="f8bd5-126">たとえば、次のテキスト。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="f8bd5-127">**"これは、最初の文と最初の行**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="f8bd5-128">**これは、2 番目の文と 2 行目"**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="f8bd5-129">正規表現 first(.\*)$ になります。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="f8bd5-130">**"これは、します。**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-130">**"This is**</span></span>
    
    <span data-ttu-id="f8bd5-131">**これは、2 番目の文と 2 行目"**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="f8bd5-132">免責事項と電子メール スレッドの終了時に自動的に挿入される法律上のステートメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="f8bd5-133">場所「開始」および"End"は、先頭と文字列の折り返しが設定された段落の末尾に一意の文字列です。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="f8bd5-134">たとえば、免責事項および法的ステートメント電子メール スレッドの開始と終了の文字列の間に存在していた次の正規表現が削除されます。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="f8bd5-135">**このメッセージには、機密情報が含まれています (. |\s)\*の確認が必要な場合は、ハード ・ コピーのバージョンを要求してください**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="f8bd5-136">(特殊文字を含む) についての免責事項を削除するには。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="f8bd5-137">たとえば、(x では、ここに表される免責事項) を次のテキスト。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="f8bd5-138">**/\*\ このメッセージには、機密情報が含まれています。xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="f8bd5-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="f8bd5-140">\**xxxx xxxx の検証が必要な場合は、ハード ・ コピーのバージョンを要求してください。/\*\**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="f8bd5-141">上記の免責条項を削除するのには正規表現は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="f8bd5-142">**\/\\*\\このメッセージには、機密情報が含まれています\.(. |\s)\*の確認が必要な場合は、ハード ・ コピーのバージョンを要求してください\.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="f8bd5-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="f8bd5-143">正規表現の規則:</span><span class="sxs-lookup"><span data-stu-id="f8bd5-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="f8bd5-144">アルファベットの文字を「_」以外の部分ではない任意の文字と"-"の前に"\"。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="f8bd5-145">正規の eExpression フィールドは、無制限の長さにできます。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="f8bd5-146">説明と正規表現の構文の詳細についてを参照してください:[正規表現言語 - クイック リファレンス](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="f8bd5-147">テキストを無視するルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="f8bd5-148">**管理\>分析\>オプションの分析****テキストを無視する**] セクションで、タブをクリックして、**+** の規則を追加するにはアイコンです。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="f8bd5-149">**無視するテキストを追加**] ダイアログ ボックスで **「名前**」フィールドにテキストを無視するルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![無視されたテキストの追加](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="f8bd5-p106">**テキスト**ボックスで、無視するテキストを入力します。テキスト フィールドでは、無制限の数の文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-p106">In the **Text** box, type the text to be ignored. The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="f8bd5-153">上のウィンドウのように、一般的な構文にガイドラインを無視するテキストを表示するのには、**電球**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="f8bd5-154">必要な場合は、**大文字小文字を区別**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="f8bd5-155">**適用先**] ボックスの一覧で、定義を適用するための高度な電子的証拠開示のモジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="f8bd5-p107">サンプル テキストに対して実行するテストを実行する場合に、**入力**テキスト ボックスにサンプル テキストを入力および**テスト**] をクリックします。結果は、**出力**テキスト ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-p107">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**. The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="f8bd5-p108">テキストを無視するルールを保存するのには **[ok]** をクリックします。定義済みのテキストを無視するルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-p108">Click **OK** to save the Ignore Text rule. The defined Ignore Text rule is displayed.</span></span> 
    
    ![無視されたテキスト名を設定する](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="f8bd5-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8bd5-161">See also</span></span>

[<span data-ttu-id="f8bd5-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f8bd5-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f8bd5-163">ドキュメントの類似性を理解します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f8bd5-164">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="f8bd5-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f8bd5-165">分析の設定の詳細設定</span><span class="sxs-lookup"><span data-stu-id="f8bd5-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f8bd5-166">分析結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="f8bd5-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

