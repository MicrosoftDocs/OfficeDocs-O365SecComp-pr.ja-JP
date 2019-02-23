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
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>サイトに保存された機密データを検索するクエリの形成

ユーザーは、多くの場合、クレジットカード番号、社会保障番号、個人などの機密データをサイトに保存し、時間の経過とともに、組織がデータ損失のリスクを負うことがあります。サイト (OneDrive for business サイトを含む) に保存されているドキュメントは、その情報へのアクセスを必要としない組織外のユーザーと共有できます。SharePoint Online でデータ損失防止 (DLP) を使用すると、テナント全体の機密データを含むドキュメントを検出できます。ドキュメントの検出後、ドキュメント所有者と協力してデータを保護することができます。このトピックは、機密データを検索するクエリを作成するのに役立ちます。
  
> [!NOTE]
> 電子情報開示、電子情報開示、DLP は、 [SharePoint Online プラン 2](https://go.microsoft.com/fwlink/?LinkId=510080)を必要とするプレミアム機能です。 
  
## <a name="forming-a-basic-dlp-query"></a>基本的な DLP クエリの形成

基本的な DLP クエリを構成する3つのパーツがあります。 SensitiveType、count の範囲、信頼の範囲です。次の図に示されているように、 **SensitiveType:\<"type\>"** は必須であり、カウントの**|\<\>範囲**と**|\<信頼範囲\> **の両方が省略可能です。 
  
![必須とオプションに分割されるクエリの例](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>機密情報の種類: 必須

では、各部分は何でしょうか。SharePoint DLP クエリは通常、[機密情報の種類のインベントリ](https://go.microsoft.com/fwlink/?LinkID=509999)から、プロパティ`"` `SensitiveType:"`と情報の種類の名前を開始し、に終了します。組織に対して作成した[カスタムの機密情報の種類](create-a-custom-sensitive-information-type.md)の名前を使用することもできます。たとえば、クレジットカード番号が含まれているドキュメントを探している場合があります。このようなインスタンスでは、次の形式`SensitiveType:"Credit Card Number"`を使用します。カウント範囲または信頼範囲が含まれていないため、クエリはクレジットカード番号が検出されたすべてのドキュメントを返します。これは、実行できる最も簡単なクエリで、最も多くの結果が返されます。機密型のスペルと間隔は重要であることに注意してください。 
  
### <a name="ranges---optional"></a>範囲: 省略可能

次の2つの部分はどちらも範囲が指定されているので、どのように表示されるかをすばやく確認できます。SharePoint DLP クエリでは、基本的な範囲は2つの数値で区切られ、次`[number]..[number]`のようになります。たとえば、が使用`10..20`されている場合、その範囲は 10 ~ 20 の数値をキャプチャします。さまざまな範囲の組み合わせがありますが、このトピックではいくつかの内容について説明します。 
  
クエリにカウント範囲を追加してみましょう。count の範囲を使用すると、クエリ結果に含める前に、ドキュメントに含める必要がある機密情報の出現回数を定義できます。たとえば、クエリで、5つのクレジットカード番号が含まれるドキュメントのみを返す場合は、次の`SensitiveType:"Credit Card Number|5"`ように使用します。また、カウントの範囲は、高い程度のリスクを持つドキュメントを特定するのに役立ちます。たとえば、組織では、5つ以上のクレジットカード番号を持つドキュメントに高いリスクがあると考えている場合があります。この条件を調整するドキュメントを検索するには、次`SensitiveType:"Credit Card Number|5.."`のクエリを使用します。または、次のクエリを使用して、5つ以下のクレジットカード番号`SensitiveType:"Credit Card Number|..5"`を持つドキュメントを検索できます。 
  
#### <a name="confidence-range"></a>信頼範囲

最後に、信頼範囲とは、検出された機密情報の種類が実際に一致するという信頼度のレベルです。信頼範囲の値は、カウント範囲と同様に動作します。カウント範囲を含めずにクエリを作成できます。たとえば、信頼範囲が 85% 以上である限り、任意の数のクレジットカード番号を含むドキュメントを検索するには、次`SensitiveType:"Credit Card Number|*|85.."`のクエリを使用します。 
  
> [!IMPORTANT]
> アスタリスク ( `*`) はワイルドカード文字で、任意の値を意味します。ワイルドカード文字 ( `*`) は、count の範囲または信頼範囲に指定できますが、機密型では使用できません。 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>電子情報開示センターで使用できるその他のクエリ プロパティと検索演算子

SharePoint の DLP には、LastSensitiveContentScan プロパティも導入されており、特定の期間内にスキャンされたファイルを検索するのに役立ちます。`LastSensitiveContentScan`プロパティを使用したクエリの例については、次のセクションの[複雑なクエリの例](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries)を参照してください。 
  
クエリを作成するのに`Author`は、DLP 固有のプロパティだけでなく、または`FileExtension`のような標準の SharePoint eDiscovery 検索プロパティも使用できます。演算子を使用して複雑なクエリを作成できます。使用可能なプロパティと演算子の一覧については、「[電子情報開示のブログ投稿で検索プロパティと演算子を使用する](https://go.microsoft.com/fwlink/?LinkId=510093)」を参照してください。 
  
## <a name="examples-of-complex-queries"></a>例

次の例では、さまざまな機密情報の種類、プロパティ、および演算子を使用して、クエリを絞り込み、目的の情報を正確に検索する方法を示します。
  
|**クエリ**|**説明**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |この名前は長いため、奇妙に見えるかもしれませんが、その機密の種類の正しい名前です。[機密情報の種類のインベントリ](https://go.microsoft.com/fwlink/?LinkID=509999)から正確な名前を使用していることを確認してください。組織に対して作成した[カスタムの機密情報の種類](create-a-custom-sensitive-information-type.md)の名前を使用することもできます。<br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |これにより、機密の種類 "クレジットカード番号" に少なくとも1つ一致するドキュメントが返されます。各範囲の値は、それぞれの最小値と最大値になります。このクエリはより簡単に記述する`SensitiveType:"Credit Card Number"`ことができますが、おもしろいのはどこにありますか。<br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |これにより、2018年8月11日から2018にスキャンされた5-25 クレジットカード番号を持つドキュメントが返されます。  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |これにより、2018年8月11日から2018にスキャンされた5-25 クレジットカード番号を持つドキュメントが返されます。.xlsx 拡張子を持つファイルは、クエリの結果に含まれていません。 `FileExtension`は、クエリに含めることができる、多くのプロパティの1つです。詳細については、「[電子情報開示で検索プロパティと演算子を使用する](https://go.microsoft.com/fwlink/?LinkId=510093)」を参照してください。<br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |クレジット カード番号または社会保障番号が含まれているドキュメントを返します。  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>例

すべてのクエリが同じように作成されるわけではありません。次の表では、SharePoint の DLP で動作しないクエリの例を示し、その理由を説明します。
  
|**サポートされていないクエリ**|**Reason**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |少なくとも 1 つの値を追加する必要があります。  <br/> |
| `SensitiveType:"NotARule"` <br/> |"notarule" は、有効な機密型名ではありません。DLP クエリでは、[機密情報の種類が一覧](https://go.microsoft.com/fwlink/?LinkID=509999)に含まれる名前のみが機能します。<br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |0は、範囲内の最小値または最大値のいずれかとしては有効ではありません。  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |"クレジット" と "カード" の間に空白のスペースがあると、クエリが無効になる可能性があります。[機密情報の種類のインベントリ](https://go.microsoft.com/fwlink/?LinkID=509999)から、厳密に機密性の高い種類名を使用します。<br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |2つのピリオドの部分は、スペースで区切る必要があります。  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |パイプの区切り文字が多すぎます (|).代わりに、次の形式に従います。`SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |信頼度の値はパーセンテージを表しているため、100を超えることはできません。代わりに 1 ~ 100 の数値を選択します。  <br/> |
   
## <a name="for-more-information"></a>詳細情報

[機密情報の種類の検索基準](what-the-sensitive-information-types-look-for.md)
  
[Office 365 セキュリティ&amp;コンプライアンスセンターでコンテンツ検索を実行する](run-a-content-search-in-the-security-and-compliance-center.md)
  
[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
  

