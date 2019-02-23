---
title: Office 365 Advanced eDiscovery の分析の [テキストを無視] オプションを設定する
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
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 'Office 365 の Advanced eDiscovery で Analyze および Process モジュールを使用するときに、特定のテキストを無視するルールを定義する方法について説明します。  '
ms.openlocfilehash: 3a4c1d17a9a56d3018509a8dcfd6b49abb951676
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214247"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="b4fe4-103">Office 365 Advanced eDiscovery の分析の [テキストを無視] オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="b4fe4-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="b4fe4-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b4fe4-p102">[テキストを無視] 機能は、次の高度な電子情報開示モジュールのすべてまたはいずれかに適用できます: Analyze (重複、電子メールスレッド、テーマ) および関連性。無視されたテキストは、関連性に表示されているファイルには表示されず、解析/計算では無視されたテキストが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-p102">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance. Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="b4fe4-p103">既に実行しているモジュールに対して、[テキストを無視] 機能が以前に定義されていた場合は、[無視] テキスト設定が変更されないようになります。ただし、関連性モジュールの [テキストを無視] 機能は、いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-p103">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified. However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="b4fe4-110">テキストフィルターの適用方法</span><span class="sxs-lookup"><span data-stu-id="b4fe4-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="b4fe4-p104">複数の Ignore テキストフィルターは、入力された順序で適用されます。適用される順序を変更するには、それらを削除して、必要な順序で再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-p104">Multiple Ignore Text filters are applied in the order that they were entered. To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="b4fe4-113">たとえば、テキストコンテンツが "DAVE BOB ALICE CAROL イブ" の場合、次に示すのは、無視するテキストエントリと結果の例です。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="b4fe4-114">**テキストの入力を無視する**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="b4fe4-115">**結果**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-115">**Results**</span></span> <br/> |
|<span data-ttu-id="b4fe4-116">"ALICE"、"BOB CAROL"</span><span class="sxs-lookup"><span data-stu-id="b4fe4-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="b4fe4-117">"DAVE イブ"</span><span class="sxs-lookup"><span data-stu-id="b4fe4-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="b4fe4-118">"ALICE"、"BOB ALICE CAROL"</span><span class="sxs-lookup"><span data-stu-id="b4fe4-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="b4fe4-119">"DAVE BOB CAROL イブ"</span><span class="sxs-lookup"><span data-stu-id="b4fe4-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="b4fe4-120">最初の無視テキストが適用された後に、文字列が見つからないため、2番目の無視テキストエントリは実装されません。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="b4fe4-121">無視するテキストを定義するときに正規表現を使用する</span><span class="sxs-lookup"><span data-stu-id="b4fe4-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="b4fe4-p105">無視テキストを定義するときは、正規表現がサポートされています。正規表現の構文と使用法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-p105">Regular expressions are supported for use when defining Ignore Text. The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="b4fe4-124">行頭から行末までテキストを削除 (無視) するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="b4fe4-125">ここで、"Begin" は行でこの文字列を最初に出現した位置です。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="b4fe4-126">たとえば、次のようなテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="b4fe4-127">**"これは最初の文と最初の行です。**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="b4fe4-128">**これは2番目の文と2行目です。**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="b4fe4-129">正規表現の最初 (.\*)$ は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="b4fe4-130">**"これは**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-130">**"This is**</span></span>
    
    <span data-ttu-id="b4fe4-131">**これは2番目の文と2行目です。**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="b4fe4-132">電子メールスレッドの最後に自動的に挿入される免責事項と法的なステートメントを削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="b4fe4-133">"Begin" と "end" は、折り返したテキストの段落の先頭と末尾にある一意の文字列です。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="b4fe4-134">たとえば、次の正規表現は、電子メールスレッドの Begin および End 文字列間の免責事項および法的なステートメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="b4fe4-135">**このメッセージには機密情報が含まれています (. |\s)\*確認が必要な場合は、ハードコピーバージョンを要求してください。**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="b4fe4-136">免責事項 (特殊文字を含む) を削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="b4fe4-137">たとえば、次のようなテキストが含まれているとします (この免責事項は x で表されています)。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="b4fe4-138">**/\*\ このメッセージには機密情報が含まれています。xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="b4fe4-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxxx**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="b4fe4-140">\**xxxx xxxx 確認が必要な場合は、ハードコピーバージョンを要求してください。/\*\**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="b4fe4-141">上記の免責事項を削除する正規表現は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="b4fe4-142">**\/\\*\\このメッセージには機密\.情報が含まれています (. |\s)\*確認が必要な場合は、ハードコピーバージョン\.を要求してください。\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="b4fe4-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="b4fe4-143">正規表現ルール:</span><span class="sxs-lookup"><span data-stu-id="b4fe4-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="b4fe4-144">アルファベットの一部ではない文字 (スペースを除く)、"_"、および "-" は "" の前にする\"必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="b4fe4-145">通常の eexpression フィールドの長さに制限はありません。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="b4fe4-146">正規表現の説明と詳細な構文については、「[正規表現言語-クイックリファレンス](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="b4fe4-147">無視するテキストルールを定義する</span><span class="sxs-lookup"><span data-stu-id="b4fe4-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="b4fe4-148">[ \*\* \>分析分析\>オプションの管理**] タブの [**無視するテキスト**] セクションで**+\*\* 、アイコンをクリックしてルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="b4fe4-149">[**無視するテキストを追加**] ダイアログの [**名前**] フィールドに、ignore テキストルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![無視されたテキストの追加](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="b4fe4-p106">**テキスト**ボックスに、無視するテキストを入力します。text フィールドに使用できる文字数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-p106">In the **Text** box, type the text to be ignored. The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b4fe4-153">上記のウィンドウに表示されているように、[**電球**] をクリックすると、Ignore テキストルールの一般的な構文のガイドラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="b4fe4-154">必要に応じて、[**大文字小文字を区別**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="b4fe4-155">[**適用先**] ボックスの一覧で、定義を適用するアドバンスド電子情報開示モジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="b4fe4-p107">サンプルテキストに対してテストを実行する場合は、**入力**テキストボックスに「sample text」と入力し、[**テスト**] をクリックします。結果が [**出力**] テキストボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-p107">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**. The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="b4fe4-p108">[ **OK]** をクリックして、Ignore テキストルールを保存します。定義済みの Ignore テキストルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4fe4-p108">Click **OK** to save the Ignore Text rule. The defined Ignore Text rule is displayed.</span></span> 
    
    ![無視されたテキスト名を設定する](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="b4fe4-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4fe4-161">See also</span></span>

[<span data-ttu-id="b4fe4-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b4fe4-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b4fe4-163">ドキュメントの類似点について</span><span class="sxs-lookup"><span data-stu-id="b4fe4-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b4fe4-164">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="b4fe4-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
<span data-ttu-id="b4fe4-165">[[詳細設定の分析] の設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="b4fe4-165">[Setting Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span></span>
  
[<span data-ttu-id="b4fe4-166">分析結果の表示</span><span class="sxs-lookup"><span data-stu-id="b4fe4-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

