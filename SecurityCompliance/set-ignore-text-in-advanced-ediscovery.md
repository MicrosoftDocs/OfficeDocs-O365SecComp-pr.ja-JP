---
title: Office 365 で分析の [テキストを無視] オプションを設定する Advanced eDiscovery
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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260829"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="9ac38-103">Office 365 で分析の [テキストを無視] オプションを設定する Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9ac38-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="9ac38-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="9ac38-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="9ac38-106">[テキストを無視] 機能は、次の高度な電子情報開示モジュールのすべてまたはいずれかに適用できます: Analyze (重複、電子メールスレッド、テーマ) および関連性。</span><span class="sxs-lookup"><span data-stu-id="9ac38-106">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance.</span></span> <span data-ttu-id="9ac38-107">無視されたテキストは、関連性に表示されているファイルには表示されず、解析/計算では無視されたテキストが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="9ac38-107">Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="9ac38-108">既に実行しているモジュールに対して、[テキストを無視] 機能が以前に定義されていた場合は、[無視] テキスト設定が変更されないようになります。</span><span class="sxs-lookup"><span data-stu-id="9ac38-108">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified.</span></span> <span data-ttu-id="9ac38-109">ただし、関連性モジュールの [テキストを無視] 機能は、いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="9ac38-109">However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="9ac38-110">テキストフィルターの適用方法</span><span class="sxs-lookup"><span data-stu-id="9ac38-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="9ac38-111">複数の Ignore テキストフィルターは、入力された順序で適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ac38-111">Multiple Ignore Text filters are applied in the order that they were entered.</span></span> <span data-ttu-id="9ac38-112">適用される順序を変更するには、それらを削除して、必要な順序で再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac38-112">To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="9ac38-113">たとえば、テキストコンテンツが "DAVE BOB ALICE CAROL イブ" の場合、次に示すのは、無視するテキストエントリと結果の例です。</span><span class="sxs-lookup"><span data-stu-id="9ac38-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9ac38-114">**テキストの入力を無視する**</span><span class="sxs-lookup"><span data-stu-id="9ac38-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="9ac38-115">**結果**</span><span class="sxs-lookup"><span data-stu-id="9ac38-115">**Results**</span></span> <br/> |
|<span data-ttu-id="9ac38-116">"ALICE"、"BOB CAROL"</span><span class="sxs-lookup"><span data-stu-id="9ac38-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="9ac38-117">"DAVE イブ"</span><span class="sxs-lookup"><span data-stu-id="9ac38-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="9ac38-118">"ALICE"、"BOB ALICE CAROL"</span><span class="sxs-lookup"><span data-stu-id="9ac38-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="9ac38-119">"DAVE BOB CAROL イブ"</span><span class="sxs-lookup"><span data-stu-id="9ac38-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="9ac38-120">最初の無視テキストが適用された後に、文字列が見つからないため、2番目の無視テキストエントリは実装されません。</span><span class="sxs-lookup"><span data-stu-id="9ac38-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="9ac38-121">無視するテキストを定義するときに正規表現を使用する</span><span class="sxs-lookup"><span data-stu-id="9ac38-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="9ac38-122">無視テキストを定義するときは、正規表現がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9ac38-122">Regular expressions are supported for use when defining Ignore Text.</span></span> <span data-ttu-id="9ac38-123">正規表現の構文と使用法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9ac38-123">The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="9ac38-124">行頭から行末までテキストを削除 (無視) するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9ac38-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="9ac38-125">ここで、"Begin" は行でこの文字列を最初に出現した位置です。</span><span class="sxs-lookup"><span data-stu-id="9ac38-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="9ac38-126">たとえば、次のようなテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="9ac38-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="9ac38-127">**"これは最初の文と最初の行です。**</span><span class="sxs-lookup"><span data-stu-id="9ac38-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="9ac38-128">**これは2番目の文と2行目です。**</span><span class="sxs-lookup"><span data-stu-id="9ac38-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="9ac38-129">正規表現の最初 (.\*)$ は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9ac38-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="9ac38-130">**"これは**</span><span class="sxs-lookup"><span data-stu-id="9ac38-130">**"This is**</span></span>
    
    <span data-ttu-id="9ac38-131">**これは2番目の文と2行目です。**</span><span class="sxs-lookup"><span data-stu-id="9ac38-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="9ac38-132">電子メールスレッドの最後に自動的に挿入される免責事項と法的なステートメントを削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9ac38-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="9ac38-133">"Begin" と "end" は、折り返したテキストの段落の先頭と末尾にある一意の文字列です。</span><span class="sxs-lookup"><span data-stu-id="9ac38-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="9ac38-134">たとえば、次の正規表現は、電子メールスレッドの Begin および End 文字列間の免責事項および法的なステートメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="9ac38-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="9ac38-135">**このメッセージには機密情報が含まれています (. |\s)\*確認が必要な場合は、ハードコピーバージョンを要求してください。**</span><span class="sxs-lookup"><span data-stu-id="9ac38-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="9ac38-136">免責事項 (特殊文字を含む) を削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9ac38-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="9ac38-137">たとえば、次のようなテキストが含まれているとします (この免責事項は x で表されています)。</span><span class="sxs-lookup"><span data-stu-id="9ac38-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="9ac38-138">**/\*\ このメッセージには機密情報が含まれています。xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="9ac38-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="9ac38-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxxx**</span><span class="sxs-lookup"><span data-stu-id="9ac38-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="9ac38-140">\**xxxx xxxx 確認が必要な場合は、ハードコピーバージョンを要求してください。/\*\**</span><span class="sxs-lookup"><span data-stu-id="9ac38-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="9ac38-141">上記の免責事項を削除する正規表現は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9ac38-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="9ac38-142">**\/\\*\\このメッセージには機密\.情報が含まれています (. |\s)\*確認が必要な場合は、ハードコピーバージョン\.を要求してください。\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="9ac38-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="9ac38-143">正規表現ルール:</span><span class="sxs-lookup"><span data-stu-id="9ac38-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="9ac38-144">アルファベットの一部ではない文字 (スペースを除く)、"_"、および "-" は "" の前にする\"必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac38-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="9ac38-145">通常の eexpression フィールドの長さに制限はありません。</span><span class="sxs-lookup"><span data-stu-id="9ac38-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="9ac38-146">正規表現の説明と詳細な構文については、「[正規表現言語-クイックリファレンス](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ac38-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="9ac38-147">無視するテキストルールを定義する</span><span class="sxs-lookup"><span data-stu-id="9ac38-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="9ac38-148">[ \*\* \>分析分析\>オプションの管理**] タブの [**無視するテキスト**] セクションで**+\*\* 、アイコンをクリックしてルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="9ac38-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="9ac38-149">[**無視するテキストを追加**] ダイアログの [**名前**] フィールドに、ignore テキストルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ac38-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![無視されたテキストの追加](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="9ac38-151">**テキスト**ボックスに、無視するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="9ac38-151">In the **Text** box, type the text to be ignored.</span></span> <span data-ttu-id="9ac38-152">text フィールドに使用できる文字数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="9ac38-152">The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="9ac38-153">上記のウィンドウに表示されているように、[**電球**] をクリックすると、Ignore テキストルールの一般的な構文のガイドラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ac38-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="9ac38-154">必要に応じて、[**大文字小文字を区別**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9ac38-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="9ac38-155">[**適用先**] ボックスの一覧で、定義を適用するアドバンスド電子情報開示モジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ac38-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="9ac38-156">サンプルテキストに対してテストを実行する場合は、**入力**テキストボックスに「sample text」と入力し、[**テスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ac38-156">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**.</span></span> <span data-ttu-id="9ac38-157">結果が [**出力**] テキストボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ac38-157">The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="9ac38-158">[ **OK]** をクリックして、Ignore テキストルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="9ac38-158">Click **OK** to save the Ignore Text rule.</span></span> <span data-ttu-id="9ac38-159">定義済みの Ignore テキストルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ac38-159">The defined Ignore Text rule is displayed.</span></span> 
    
    ![無視されたテキスト名を設定する](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="9ac38-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ac38-161">See also</span></span>

[<span data-ttu-id="9ac38-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9ac38-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="9ac38-163">ドキュメントの類似点について</span><span class="sxs-lookup"><span data-stu-id="9ac38-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="9ac38-164">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="9ac38-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
<span data-ttu-id="9ac38-165">[[詳細設定の分析] の設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="9ac38-165">[Setting Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span></span>
  
[<span data-ttu-id="9ac38-166">分析結果の表示</span><span class="sxs-lookup"><span data-stu-id="9ac38-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

