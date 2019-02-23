---
title: サイトに保存された機密データを検索するクエリの形成
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3019fbc5-7f15-4972-8d0e-dc182dc7f836
description: SharePoint Online でデータ損失防止 (DLP) を使用すると、テナント全体の機密データを含むドキュメントを検出できます。ドキュメントの検出後、ドキュメント所有者と協力してデータを保護することができます。このトピックは、機密データを検索するクエリを作成するのに役立ちます。
ms.openlocfilehash: 3dc1081d4627f1a26c50eed84f733c31a3f6c194
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217237"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a><span data-ttu-id="8e5dd-105">サイトに保存された機密データを検索するクエリの形成</span><span class="sxs-lookup"><span data-stu-id="8e5dd-105">Form a query to find sensitive data stored on sites</span></span>

<span data-ttu-id="8e5dd-p102">ユーザーは、多くの場合、クレジットカード番号、社会保障番号、個人などの機密データをサイトに保存し、時間の経過とともに、組織がデータ損失のリスクを負うことがあります。サイト (OneDrive for business サイトを含む) に保存されているドキュメントは、その情報へのアクセスを必要としない組織外のユーザーと共有できます。SharePoint Online でデータ損失防止 (DLP) を使用すると、テナント全体の機密データを含むドキュメントを検出できます。ドキュメントの検出後、ドキュメント所有者と協力してデータを保護することができます。このトピックは、機密データを検索するクエリを作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p102">Users often store sensitive data, such as credit card numbers, social security numbers, or personal, on their sites, and over time this can expose an organization to significant risk of data loss. Documents stored on sites—including OneDrive for Business sites—could be shared with people outside the organization who shouldn't have access to the information. With data loss prevention (DLP) in SharePoint Online, you can discover documents that contain sensitive data throughout your tenant. After discovering the documents, you can work with the document owners to protect the data. This topic can help you form a query to search for sensitive data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e5dd-111">電子情報開示、電子情報開示、DLP は、 [SharePoint Online プラン 2](https://go.microsoft.com/fwlink/?LinkId=510080)を必要とするプレミアム機能です。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-111">Electronic discovery, or eDiscovery, and DLP are premium features that require [SharePoint Online Plan 2](https://go.microsoft.com/fwlink/?LinkId=510080).</span></span> 
  
## <a name="forming-a-basic-dlp-query"></a><span data-ttu-id="8e5dd-112">基本的な DLP クエリの形成</span><span class="sxs-lookup"><span data-stu-id="8e5dd-112">Forming a basic DLP query</span></span>

<span data-ttu-id="8e5dd-p103">基本的な DLP クエリを構成する3つのパーツがあります。 SensitiveType、count の範囲、信頼の範囲です。次の図に示されているように、 **SensitiveType:\<"type\>"** は必須であり、カウントの**|\<\>範囲**と\*\*|\<信頼範囲\> \*\*の両方が省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p103">There are three parts that make up a basic DLP query: SensitiveType, count range, and confidence range. As illustrated in the following graphic, **SensitiveType:"\<type\>"** is required, and both**|\<count range\>** and**|\<confidence range\>** are optional.</span></span> 
  
![必須とオプションに分割されるクエリの例](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a><span data-ttu-id="8e5dd-116">機密情報の種類: 必須</span><span class="sxs-lookup"><span data-stu-id="8e5dd-116">Sensitive type - required</span></span>

<span data-ttu-id="8e5dd-p104">では、各部分は何でしょうか。SharePoint DLP クエリは通常、[機密情報の種類のインベントリ](https://go.microsoft.com/fwlink/?LinkID=509999)から、プロパティ`"` `SensitiveType:"`と情報の種類の名前を開始し、に終了します。組織に対して作成した[カスタムの機密情報の種類](create-a-custom-sensitive-information-type.md)の名前を使用することもできます。たとえば、クレジットカード番号が含まれているドキュメントを探している場合があります。このようなインスタンスでは、次の形式`SensitiveType:"Credit Card Number"`を使用します。カウント範囲または信頼範囲が含まれていないため、クエリはクレジットカード番号が検出されたすべてのドキュメントを返します。これは、実行できる最も簡単なクエリで、最も多くの結果が返されます。機密型のスペルと間隔は重要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p104">So what is each part? SharePoint DLP queries typically begin with the property  `SensitiveType:"` and an information type name from the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999), and end with a  `"`. You can also use the name of a [custom sensitive information type](create-a-custom-sensitive-information-type.md) that you created for your organization. For example, you might be looking for documents that contain credit card numbers. In such an instance, you'd use the following format:  `SensitiveType:"Credit Card Number"`. Because you didn't include count range or confidence range, the query returns every document in which a credit card number is detected. This is the simplest query that you can run, and it returns the most results. Keep in mind that the spelling and spacing of the sensitive type matters.</span></span> 
  
### <a name="ranges---optional"></a><span data-ttu-id="8e5dd-125">範囲: 省略可能</span><span class="sxs-lookup"><span data-stu-id="8e5dd-125">Ranges - optional</span></span>

<span data-ttu-id="8e5dd-p105">次の2つの部分はどちらも範囲が指定されているので、どのように表示されるかをすばやく確認できます。SharePoint DLP クエリでは、基本的な範囲は2つの数値で区切られ、次`[number]..[number]`のようになります。たとえば、が使用`10..20`されている場合、その範囲は 10 ~ 20 の数値をキャプチャします。さまざまな範囲の組み合わせがありますが、このトピックではいくつかの内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p105">Both of the next two parts are ranges, so let's quickly examine what a range looks like. In SharePoint DLP queries, a basic range is represented by two numbers separated by two periods, which looks like this:  `[number]..[number]`. For instance, if  `10..20` is used, that range would capture numbers from 10 through 20. There are many different range combinations and several are covered in this topic.</span></span> 
  
<span data-ttu-id="8e5dd-p106">クエリにカウント範囲を追加してみましょう。count の範囲を使用すると、クエリ結果に含める前に、ドキュメントに含める必要がある機密情報の出現回数を定義できます。たとえば、クエリで、5つのクレジットカード番号が含まれるドキュメントのみを返す場合は、次の`SensitiveType:"Credit Card Number|5"`ように使用します。また、カウントの範囲は、高い程度のリスクを持つドキュメントを特定するのに役立ちます。たとえば、組織では、5つ以上のクレジットカード番号を持つドキュメントに高いリスクがあると考えている場合があります。この条件を調整するドキュメントを検索するには、次`SensitiveType:"Credit Card Number|5.."`のクエリを使用します。または、次のクエリを使用して、5つ以下のクレジットカード番号`SensitiveType:"Credit Card Number|..5"`を持つドキュメントを検索できます。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p106">Let's add a count range to the query. You can use count range to define the number of occurrences of sensitive information a document needs to contain before it's included in the query results. For example, if you want your query to return only documents that contain exactly five credit card numbers, use this:  `SensitiveType:"Credit Card Number|5"`. Count range can also help you identify documents that pose high degrees of risk. For example, your organization might consider documents with five or more credit card numbers a high risk. To find documents fitting this criterion, you would use this query:  `SensitiveType:"Credit Card Number|5.."`. Alternatively, you can find documents with five or fewer credit card numbers by using this query:  `SensitiveType:"Credit Card Number|..5"`.</span></span> 
  
#### <a name="confidence-range"></a><span data-ttu-id="8e5dd-137">信頼範囲</span><span class="sxs-lookup"><span data-stu-id="8e5dd-137">Confidence range</span></span>

<span data-ttu-id="8e5dd-p107">最後に、信頼範囲とは、検出された機密情報の種類が実際に一致するという信頼度のレベルです。信頼範囲の値は、カウント範囲と同様に動作します。カウント範囲を含めずにクエリを作成できます。たとえば、信頼範囲が 85% 以上である限り、任意の数のクレジットカード番号を含むドキュメントを検索するには、次`SensitiveType:"Credit Card Number|*|85.."`のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p107">Finally, confidence range is the level of confidence that the detected sensitive type is actually a match. The values for confidence range work similarly to count range. You can form a query without including a count range. For example, to search for documents with any number of credit card numbers—as long as the confidence range is 85 percent or higher—you would use this query:  `SensitiveType:"Credit Card Number|*|85.."`.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8e5dd-p108">アスタリスク ( `*`) はワイルドカード文字で、任意の値を意味します。ワイルドカード文字 ( `*`) は、count の範囲または信頼範囲に指定できますが、機密型では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p108">The asterisk ( `*`) is a wildcard character that means any value works. You can use the wildcard character ( `*`) either in the count range or in the confidence range, but not in a sensitive type.</span></span> 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a><span data-ttu-id="8e5dd-144">電子情報開示センターで使用できるその他のクエリ プロパティと検索演算子</span><span class="sxs-lookup"><span data-stu-id="8e5dd-144">Additional query properties and search operators available in the eDiscovery Center</span></span>

<span data-ttu-id="8e5dd-p109">SharePoint の DLP には、LastSensitiveContentScan プロパティも導入されており、特定の期間内にスキャンされたファイルを検索するのに役立ちます。`LastSensitiveContentScan`プロパティを使用したクエリの例については、次のセクションの[複雑なクエリの例](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p109">DLP in SharePoint also introduces the LastSensitiveContentScan property, which can help you search for files scanned within a specific timeframe. For query examples with the  `LastSensitiveContentScan` property, see the [Examples of complex queries](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries) in the next section.</span></span> 
  
<span data-ttu-id="8e5dd-p110">クエリを作成するのに`Author`は、DLP 固有のプロパティだけでなく、または`FileExtension`のような標準の SharePoint eDiscovery 検索プロパティも使用できます。演算子を使用して複雑なクエリを作成できます。使用可能なプロパティと演算子の一覧については、「[電子情報開示のブログ投稿で検索プロパティと演算子を使用する](https://go.microsoft.com/fwlink/?LinkId=510093)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p110">You can use not only DLP-specific properties to create a query, but also standard SharePoint eDiscovery search properties such as  `Author` or  `FileExtension`. You can use operators to build complex queries. For the list of available properties and operators, see the [Using Search Properties and Operators with eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093) blog post.</span></span> 
  
## <a name="examples-of-complex-queries"></a><span data-ttu-id="8e5dd-150">例</span><span class="sxs-lookup"><span data-stu-id="8e5dd-150">Examples of complex queries</span></span>

<span data-ttu-id="8e5dd-151">次の例では、さまざまな機密情報の種類、プロパティ、および演算子を使用して、クエリを絞り込み、目的の情報を正確に検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-151">The following examples use different sensitive types, properties, and operators to illustrate how you can refine your queries to find exactly what you're looking for.</span></span>
  
|<span data-ttu-id="8e5dd-152">**クエリ**</span><span class="sxs-lookup"><span data-stu-id="8e5dd-152">**Query**</span></span>|<span data-ttu-id="8e5dd-153">**説明**</span><span class="sxs-lookup"><span data-stu-id="8e5dd-153">**Explanation**</span></span>|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |<span data-ttu-id="8e5dd-p111">この名前は長いため、奇妙に見えるかもしれませんが、その機密の種類の正しい名前です。[機密情報の種類のインベントリ](https://go.microsoft.com/fwlink/?LinkID=509999)から正確な名前を使用していることを確認してください。組織に対して作成した[カスタムの機密情報の種類](create-a-custom-sensitive-information-type.md)の名前を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p111">The name might seem strange because it's so long, but it's the correct name for that sensitive type. Make sure to use exact names from the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999). You can also use the name of a [custom sensitive information type](create-a-custom-sensitive-information-type.md) that you created for your organization.  </span></span><br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |<span data-ttu-id="8e5dd-p112">これにより、機密の種類 "クレジットカード番号" に少なくとも1つ一致するドキュメントが返されます。各範囲の値は、それぞれの最小値と最大値になります。このクエリはより簡単に記述する`SensitiveType:"Credit Card Number"`ことができますが、おもしろいのはどこにありますか。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p112">This returns documents with at least one match to the sensitive type "Credit Card Number." The values for each range are the respective minimum and maximum values. A simpler way to write this query is  `SensitiveType:"Credit Card Number"`, but where's the fun in that?  </span></span><br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |<span data-ttu-id="8e5dd-160">これにより、2018年8月11日から2018にスキャンされた5-25 クレジットカード番号を持つドキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-160">This returns documents with 5-25 credit card numbers that were scanned from August 11, 2018 through August 13, 2018.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |<span data-ttu-id="8e5dd-p113">これにより、2018年8月11日から2018にスキャンされた5-25 クレジットカード番号を持つドキュメントが返されます。.xlsx 拡張子を持つファイルは、クエリの結果に含まれていません。 `FileExtension`は、クエリに含めることができる、多くのプロパティの1つです。詳細については、「[電子情報開示で検索プロパティと演算子を使用する](https://go.microsoft.com/fwlink/?LinkId=510093)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p113">This returns documents with 5-25 credit card numbers that were scanned from August 11, 2018 through August 13, 2018. Files with an XLSX extension aren't included in the query results.  `FileExtension` is one of many properties that you can include in a query. For more information, see [Using Search Properties and Operators with eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093).  </span></span><br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |<span data-ttu-id="8e5dd-165">クレジット カード番号または社会保障番号が含まれているドキュメントを返します。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-165">This returns documents that contain either a credit card number or a social security number.</span></span>  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a><span data-ttu-id="8e5dd-166">例</span><span class="sxs-lookup"><span data-stu-id="8e5dd-166">Examples of queries to avoid</span></span>

<span data-ttu-id="8e5dd-p114">すべてのクエリが同じように作成されるわけではありません。次の表では、SharePoint の DLP で動作しないクエリの例を示し、その理由を説明します。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p114">Not all queries are created equal. The following table gives examples of queries that don't work with DLP in SharePoint and describes why.</span></span>
  
|<span data-ttu-id="8e5dd-169">**サポートされていないクエリ**</span><span class="sxs-lookup"><span data-stu-id="8e5dd-169">**Unsupported query**</span></span>|<span data-ttu-id="8e5dd-170">**Reason**</span><span class="sxs-lookup"><span data-stu-id="8e5dd-170">**Reason**</span></span>|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |<span data-ttu-id="8e5dd-171">少なくとも 1 つの値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-171">You must add at least one number.</span></span>  <br/> |
| `SensitiveType:"NotARule"` <br/> |<span data-ttu-id="8e5dd-p115">"notarule" は、有効な機密型名ではありません。DLP クエリでは、[機密情報の種類が一覧](https://go.microsoft.com/fwlink/?LinkID=509999)に含まれる名前のみが機能します。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p115">"NotARule" isn't a valid sensitive type name. Only names in the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999) work in DLP queries.  </span></span><br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |<span data-ttu-id="8e5dd-174">0は、範囲内の最小値または最大値のいずれかとしては有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-174">Zero isn't valid as either the minimum value or the maximum value in a range.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |<span data-ttu-id="8e5dd-p116">"クレジット" と "カード" の間に空白のスペースがあると、クエリが無効になる可能性があります。[機密情報の種類のインベントリ](https://go.microsoft.com/fwlink/?LinkID=509999)から、厳密に機密性の高い種類名を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p116">It's might be difficult to see, but there's extra white space between "Credit" and "Card" that makes the query invalid. Use exact sensitive type names from the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999).  </span></span><br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |<span data-ttu-id="8e5dd-177">2つのピリオドの部分は、スペースで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-177">The two-period portion shouldn't be separated by a space.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |<span data-ttu-id="8e5dd-178">パイプの区切り文字が多すぎます (</span><span class="sxs-lookup"><span data-stu-id="8e5dd-178">There are too many pipe delimiters (</span></span>|<span data-ttu-id="8e5dd-p117">).代わりに、次の形式に従います。`SensitiveType: "Credit Card Number|1..|80.."`</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p117">). Follow this format instead: `SensitiveType: "Credit Card Number|1..|80.."`</span></span> <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |<span data-ttu-id="8e5dd-p118">信頼度の値はパーセンテージを表しているため、100を超えることはできません。代わりに 1 ~ 100 の数値を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e5dd-p118">Because confidence values represent a percentage, they can't exceed 100. Choose a number from 1 through 100 instead.</span></span>  <br/> |
   
## <a name="for-more-information"></a><span data-ttu-id="8e5dd-183">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8e5dd-183">For more information</span></span>

[<span data-ttu-id="8e5dd-184">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="8e5dd-184">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
  
[<span data-ttu-id="8e5dd-185">Office 365 セキュリティ&amp;コンプライアンスセンターでコンテンツ検索を実行する</span><span class="sxs-lookup"><span data-stu-id="8e5dd-185">Run a Content Search in the Office 365 Security &amp; Compliance Center</span></span>](run-a-content-search-in-the-security-and-compliance-center.md)
  
[<span data-ttu-id="8e5dd-186">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="8e5dd-186">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
  

