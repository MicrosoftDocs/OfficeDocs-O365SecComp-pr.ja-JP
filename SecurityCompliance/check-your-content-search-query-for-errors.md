---
title: コンテンツ検索のクエリでエラーを確認する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: 検索を実行する前に、サポートされていない文字や小文字のブール演算子などのエラーと入力ミスについては、キーワードクエリのコンテンツ検索を確認してください。エラーが見つかった場合は、変更されたクエリを提案します。
ms.openlocfilehash: 00612116f345e2a01471d5c83df77f4bc8db9ce5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215937"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="b0a45-104">コンテンツ検索のクエリでエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="b0a45-104">Check your Content Search query for errors</span></span>

<span data-ttu-id="b0a45-p102">コンテンツ検索を作成または編集するときに、サポートされていない文字および大文字にならないブール演算子については、Office 365 でクエリをチェックできます。どう。コンテンツ検索の [クエリ] ページで、[**クエリのスペルチェック] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="b0a45-p102">When you create or edit a Content Search, you can have Office 365 check your query for unsupported characters and Boolean operators that might not be capitalized. How? Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![[クエリのスペルチェックを行う] をクリックして、サポートされていない文字の検索クエリを確認します。](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="b0a45-p103">確認するサポートされていない文字の一覧を次に示します。サポートされていない文字は多くの場合、非表示になっているため、通常は検索エラーが発生するか、予期しない結果を返します</span><span class="sxs-lookup"><span data-stu-id="b0a45-p103">Here's a list of the unsupported characters that we check for. Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="b0a45-p104">**スマートクォーテーションマーク**-スマート一重引用符と二重引用符 (波引用符とも呼ばれます) はサポートされていません。検索クエリでは、直線の引用符のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0a45-p104">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported. Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="b0a45-p105">**印刷できない文字と制御**文字。印刷できない文字と制御文字は、英数字などの文字を記述したものではありません。印刷できない文字と制御文字の例としては、テキストの書式設定またはテキスト行の区切り文字があります。</span><span class="sxs-lookup"><span data-stu-id="b0a45-p105">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as a alpha-numeric character. Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="b0a45-115">左から右の**マークと右から左のマーク**-これらは、左から右の言語 (英語やスペイン語など) と右から左の言語 (アラビア語やヘブライ語など) のテキストの方向を示すために使用される制御文字です。</span><span class="sxs-lookup"><span data-stu-id="b0a45-115">**Left-to-right and right-to-left marks** - These are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="b0a45-p106">**小文字のブール演算子**- **AND**、 **OR**、 **NOT**などのブール演算子を検索クエリで使用する場合は、大文字である必要があります。クエリで誤字をチェックしている場合、クエリ構文は、小文字の演算子が使用されているにもかかわらずブール演算子が使用されていることを示すことがよくあります。たとえば、 `(WordA or WordB) and (WordC or WordD)`のようになります。</span><span class="sxs-lookup"><span data-stu-id="b0a45-p106">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase. When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="b0a45-118">クエリにサポートされていない文字が含まれている場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="b0a45-118">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="b0a45-p107">サポートされていない文字がクエリに含まれていると、サポートされていない文字が見つかったことを示す警告メッセージが表示されます。その後、元のクエリを保持するか、変更された提案されたクエリに置き換えます。前のスクリーンショットの検索クエリに対して [クエリのスペル**チェック**] をクリックした後に表示される警告メッセージの例を次に示します。元のクエリには、スマート引用符と小文字のブール演算子が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b0a45-p107">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters that were found and a suggests an alternative. Then you then have the option keep the original query or replace it with the suggested revised query. Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot. Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![クエリに対して推奨されるリビジョンの警告メッセージが表示されます。](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="b0a45-124">検索クエリでサポートされていない文字を防ぐ方法</span><span class="sxs-lookup"><span data-stu-id="b0a45-124">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="b0a45-p108">サポートされていない文字は、通常、他のアプリケーション (microsoft Word や microsoft Excel など) からクエリの一部をコピーし、それをコンテンツ検索のクエリページの [キーワード] ボックスにコピーするときに、クエリに追加されます。サポートされていない文字を回避する最善の方法は、[キーワード] ボックスにクエリを入力することです。または、word または Excel からクエリをコピーして、Microsoft メモ帳などのテキストエディターでファイルに貼り付けることができます。テキストファイルを保存して、[**エンコード**] ドロップダウンリストで [ **ANSI** ] を選択します。書式設定とサポートされていない文字を削除します。その後、テキストファイルから [キーワードクエリ] ボックスにクエリをコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b0a45-p108">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and copy them to the keyword box on the query page of a Content Search. The best way to prevent unsupported characters is to just type the query in the keyword box. Alternatively, you can copy a query from Word or Excel and then paste it to file in a plain text editor, such as Microsoft Notepad. Then save the text file and select **ANSI** in the **Encoding** drop-down list. This will remove any formatting and unsupported characters. Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
