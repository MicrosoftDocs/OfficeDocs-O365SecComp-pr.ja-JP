---
title: コンテンツ検索のクエリでエラーを確認する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: エラーや入力ミス、サポートされていない文字などのコンテンツの検索、キーワード クエリを確認し、小文字のブール演算子は、検索を実行する前にします。、エラーが見つかった場合、修正済みのクエリをお勧めします。
ms.openlocfilehash: 0d2119ceef4ce3777d3967a56357551e235e426c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532139"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="2cc05-104">コンテンツ検索のクエリでエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="2cc05-104">Check your Content Search query for errors</span></span>

<span data-ttu-id="2cc05-p102">作成または、コンテンツの検索を編集するときは、Office 365 のサポートされていない文字および資本化されない可能性があります、ブール演算子のクエリを確認することができます。どう。だけで、クエリのページでコンテンツの検索**クエリの入力ミスをチェック**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cc05-p102">When you create or edit a Content Search, you can have Office 365 check your query for unsupported characters and Boolean operators that might not be capitalized. How? Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![[クエリの入力ミスをチェックする] をクリックしてサポートされていない文字の検索クエリを確認するには](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="2cc05-p103">ここではサポートされていない文字をチェックしているのリストです。サポートされていない文字が表示されていない多くの場合と、通常検索エラーが発生または予期しない結果を返します。</span><span class="sxs-lookup"><span data-stu-id="2cc05-p103">Here's a list of the unsupported characters that we check for. Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="2cc05-p104">**スマート引用符**を単一引用符と二重引用符 ("活字タイプの引用符"とも呼ばれます) はサポートされていません。検索クエリでは、直線の引用符のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2cc05-p104">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported. Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="2cc05-p105">**以外の文字や制御文字**の印字不能および制御文字ものではない記述の記号、英数字の文字などです。印字の例として、制御文字がテキストの別の行またはテキストの書式を設定する文字を含みます。</span><span class="sxs-lookup"><span data-stu-id="2cc05-p105">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as a alpha-numeric character. Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="2cc05-115">**左から右と右から左のマーク**のこれらは、コントロール文字が左から右の言語 (英語、スペイン語など) と右から左の言語 (アラビア語やヘブライ語) のテキストの方向を示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="2cc05-115">**Left-to-right and right-to-left marks** - These are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="2cc05-p106">**小文字のブール演算子**をブール演算子など**と**、**または**、**ない**、検索クエリを使用する場合、必ず大文字です。クエリの構文が表示されます多くの場合、クエリの入力ミスをチェックすると小文字の演算子を使用する可能性があります; 場合でも、ブール演算子を使用しています。たとえば、 `(WordA or WordB) and (WordC or WordD)`。</span><span class="sxs-lookup"><span data-stu-id="2cc05-p106">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase. When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="2cc05-118">クエリには、サポートされていない文字が含まれてとすると、どうなりますか。</span><span class="sxs-lookup"><span data-stu-id="2cc05-118">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="2cc05-p107">クエリでサポートされていない文字が見つかった場合、警告メッセージが表示されます検出された文字がサポートされていないことを示すと、別の方法をお勧めします。なら、オプションの元のクエリを保持するか、提示された修正済みのクエリで置き換えます。ここでは、前のスクリーン ショットでは、検索クエリの**クエリの入力ミスをチェックする**をクリックした後に表示される警告メッセージの例です。元のクエリには、スマート クオートと小文字のブール演算子が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2cc05-p107">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters that were found and a suggests an alternative. Then you then have the option keep the original query or replace it with the suggested revised query. Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot. Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![クエリの提示されたリビジョンと警告メッセージが表示されます。](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="2cc05-124">検索クエリでサポートされていない文字を防止する方法</span><span class="sxs-lookup"><span data-stu-id="2cc05-124">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="2cc05-p108">サポートされていない文字は、他のアプリケーション (Word または Excel) からクエリまたはクエリの部分をコピーして、[クエリ] ページで、コンテンツの検索のキーワード] ボックスにコピーするときに通常、クエリに追加されます。サポートされていない文字を防止する最善の方法は、クエリ、[キーワード] ボックスに入力するだけです。代わりに、Word または Excel からクエリをコピーして、メモ帳などのテキスト エディターでファイルに貼り付けます。テキスト ファイルを保存し、[**エンコード**] ドロップダウン リストで、 **ANSI**を選択します。書式設定と、サポートされていない文字を削除します。できますをコピーし、キーワード クエリ] ボックスにテキスト ファイルからのクエリを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2cc05-p108">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and copy them to the keyword box on the query page of a Content Search. The best way to prevent unsupported characters is to just type the query in the keyword box. Alternatively, you can copy a query from Word or Excel and then paste it to file in a plain text editor, such as Microsoft Notepad. Then save the text file and select **ANSI** in the **Encoding** drop-down list. This will remove any formatting and unsupported characters. Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
