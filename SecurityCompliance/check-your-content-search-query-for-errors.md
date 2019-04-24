---
title: コンテンツ検索クエリでエラーを確認する
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
description: 検索を実行する前に、サポートされていない文字や小文字のブール演算子などのエラーと入力ミスについては、キーワードクエリのコンテンツ検索を確認してください。 エラーが見つかった場合は、変更されたクエリを提案します。
ms.openlocfilehash: 00612116f345e2a01471d5c83df77f4bc8db9ce5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243666"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="0703e-104">コンテンツ検索クエリでエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="0703e-104">Check your Content Search query for errors</span></span>

<span data-ttu-id="0703e-105">コンテンツ検索を作成または編集するときに、サポートされていない文字および大文字にならないブール演算子については、Office 365 でクエリをチェックできます。</span><span class="sxs-lookup"><span data-stu-id="0703e-105">When you create or edit a Content Search, you can have Office 365 check your query for unsupported characters and Boolean operators that might not be capitalized.</span></span> <span data-ttu-id="0703e-106">どう。</span><span class="sxs-lookup"><span data-stu-id="0703e-106">How?</span></span> <span data-ttu-id="0703e-107">コンテンツ検索の [クエリ] ページで、[**クエリのスペルチェック] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="0703e-107">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![[クエリのスペルチェックを行う] をクリックして、サポートされていない文字の検索クエリを確認します。](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="0703e-109">確認するサポートされていない文字の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0703e-109">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="0703e-110">サポートされていない文字は多くの場合、非表示になっているため、通常は検索エラーが発生するか、予期しない結果を返します</span><span class="sxs-lookup"><span data-stu-id="0703e-110">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="0703e-111">**スマートクォーテーションマーク**-スマート一重引用符と二重引用符 (波引用符とも呼ばれます) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0703e-111">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="0703e-112">検索クエリでは、ストレート引用符のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0703e-112">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="0703e-113">**印刷できない文字と制御**文字。印刷できない文字と制御文字は、英数字などの文字を記述したものではありません。</span><span class="sxs-lookup"><span data-stu-id="0703e-113">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as a alpha-numeric character.</span></span> <span data-ttu-id="0703e-114">印刷不可能な文字と制御文字には、テキストを書式設定する文字や個別のテキスト行などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0703e-114">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="0703e-115">左から右の**マークと右から左のマーク**-これらは、左から右の言語 (英語やスペイン語など) と右から左の言語 (アラビア語やヘブライ語など) のテキストの方向を示すために使用される制御文字です。</span><span class="sxs-lookup"><span data-stu-id="0703e-115">**Left-to-right and right-to-left marks** - These are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="0703e-116">**小文字のブール演算子**- **AND**、 **OR**、 **NOT**などのブール演算子を検索クエリで使用する場合は、大文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0703e-116">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="0703e-117">クエリで誤字をチェックしている場合、クエリ構文は、小文字の演算子が使用されているにもかかわらずブール演算子が使用されていることを示すことがよくあります。たとえば、 `(WordA or WordB) and (WordC or WordD)`のようになります。</span><span class="sxs-lookup"><span data-stu-id="0703e-117">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="0703e-118">クエリにサポートされていない文字が含まれている場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="0703e-118">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="0703e-119">サポートされていない文字がクエリに含まれていると、サポートされていない文字が見つかったことを示す警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0703e-119">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters that were found and a suggests an alternative.</span></span> <span data-ttu-id="0703e-120">その後、元のクエリを保持するか、変更された提案されたクエリに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0703e-120">Then you then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="0703e-121">前のスクリーンショットの検索クエリに対して [クエリのスペル**チェック**] をクリックした後に表示される警告メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0703e-121">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="0703e-122">元のクエリには、スマート引用符と小文字のブール演算子が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0703e-122">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![クエリに対して推奨されるリビジョンの警告メッセージが表示されます。](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="0703e-124">検索クエリでサポートされていない文字を防ぐ方法</span><span class="sxs-lookup"><span data-stu-id="0703e-124">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="0703e-125">サポートされていない文字は、通常、他のアプリケーション (microsoft Word や microsoft Excel など) からクエリの一部をコピーし、それをコンテンツ検索のクエリページの [キーワード] ボックスにコピーするときに、クエリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="0703e-125">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and copy them to the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="0703e-126">サポートされていない文字を使用しないようにする最善の方法は、キーワード ボックスにクエリを入力することです。</span><span class="sxs-lookup"><span data-stu-id="0703e-126">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="0703e-127">また、Word や Excel からクエリをコピーして、メモ帳などのテキスト エディターでファイルに貼り付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="0703e-127">Alternatively, you can copy a query from Word or Excel and then paste it to file in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="0703e-128">そのテキスト ファイルを保存し、 **[エンコード]** ドロップダウン リストで **[ANSI]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0703e-128">Then save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="0703e-129">これにより、すべての書式設定とサポートされない文字が削除されます。</span><span class="sxs-lookup"><span data-stu-id="0703e-129">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="0703e-130">その後、テキスト ファイルからクエリをコピーして、キーワード クエリ ボックスに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0703e-130">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
