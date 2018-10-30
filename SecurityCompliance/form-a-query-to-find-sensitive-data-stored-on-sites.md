---
title: サイトに保存された機密データを検索するクエリの形成
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3019fbc5-7f15-4972-8d0e-dc182dc7f836
description: SharePoint Online のデータ損失防止 (DLP) と、テナント内の機密データを含むドキュメントを検出できます。ドキュメントを検出した後には、データを保護するドキュメントの所有者に使用できます。このトピックでは、機密性の高いデータを検索するクエリを作成できます。
ms.openlocfilehash: c30cb2e4b93e1a7db90f3e3f922f406285c6f692
ms.sourcegitcommit: 81e06e09bf5ca8e3f51b164d6251b1c35b3285cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2018
ms.locfileid: "25829188"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>サイトに保存された機密データを検索するクエリの形成

ユーザーは多くの場合、クレジット_カード番号、社会保障番号などの機密性の高いデータを格納または個人、サイト、および時間の経過と共にこの公開データ消失の重大なリスクを組織します。サイト上のドキュメント-ビジネス サイトの OneDrive を含む、情報へのアクセス権を持つべきではない、組織外のユーザーと共有する可能性があります。SharePoint Online のデータ損失防止 (DLP) と、テナント内の機密データを含むドキュメントを検出できます。ドキュメントを検出した後には、データを保護するドキュメントの所有者に使用できます。このトピックでは、機密性の高いデータを検索するクエリを作成できます。
  
> [!NOTE]
> 、電子的証拠開示や電子的証拠開示、DLP は、 [SharePoint のオンライン計画 2](https://go.microsoft.com/fwlink/?LinkId=510080)を必要とする高度な機能です。 
  
## <a name="forming-a-basic-dlp-query"></a>基本的な DLP クエリの形成

DLP の基本的なクエリを構成する 3 つの部分がある: SensitiveType、範囲、および信頼の範囲をカウントします。次の図に示すように**SensitiveType:"\<型\>"** は必須では両方と**|\<範囲をカウントする\>** と**|\<信頼度の範囲\>** は省略可能。 
  
![必須とオプションに分割されるクエリの例](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>機密情報の種類: 必須

では、各パーツとは何ですか。通常、SharePoint の DLP のクエリのプロパティを使用して先頭`SensitiveType:"`と情報の種類から[機密性の高い情報の種類の在庫](https://go.microsoft.com/fwlink/?LinkID=509999)、名、最後に、 `"`。組織用に作成した[カスタムの機密性の高い情報の種類](create-a-custom-sensitive-information-type.md)の名前を使用することもできます。たとえば、クレジット カード番号を含む文書を探すことです。このような場合に、次の形式を使用すると: `SensitiveType:"Credit Card Number"`。数の指定範囲または精度の範囲が含まれていない、ために、クエリは、クレジット カード番号が検出されたすべてのドキュメントを返します。これは、最も単純なクエリを実行することができますが、ほとんどの結果を返します。スペル チェックとの重要な文字の間隔が重要なことに留意してください。 
  
### <a name="ranges---optional"></a>範囲: 省略可能

では、すぐに調査して、範囲は次のように範囲は、両方の次の 2 つのパーツ。SharePoint の DLP のクエリで基本的な範囲は、2 つのピリオドで区切られた 2 つの数値を次のような: `[number]..[number]`。たとえば場合、`10..20`は、使用すると、その範囲は 10 ~ 20 の数字をキャプチャ。多くの別の範囲の組み合わせがあるし、は、このトピックで扱ういくつか。 
  
クエリの数の範囲を追加しましょう。ドキュメントはクエリ結果に含まれている前に必要な重要な情報の出現回数を定義するのには、数の範囲を使用できます。たとえば、5 つのクレジット カード番号が含まれるドキュメントだけを返すようにクエリを実行する場合に、これを使用: `SensitiveType:"Credit Card Number|5"`。数の範囲は、リスクの高度となるドキュメントを識別するにも役立ちます。組織は、可能性があります例えば、5 つ以上のクレジット カード番号を使用してドキュメント、リスクの高い。この条件を自動調整するドキュメントを検索するには、このクエリを使用します: `SensitiveType:"Credit Card Number|5.."`。または、うちの 5 つのドキュメントを検索するか、このクエリを使用して、以下のクレジット_カード番号: `SensitiveType:"Credit Card Number|..5"`。 
  
#### <a name="confidence-range"></a>信頼範囲

最後に、信頼度の範囲は、検出された機密性の高い型が実際に一致する信頼のレベルです。信頼度の範囲の値は、範囲をカウントする同様に動作します。数の範囲を指定せず、クエリを形成できます。など、クレジット カード番号の任意の数のドキュメントを検索する-間の信頼の範囲は、85% 以上、このクエリを使用する: `SensitiveType:"Credit Card Number|*|85.."`。 
  
> [!IMPORTANT]
> アスタリスク ( `*`) は、任意の値のしくみのことを意味するワイルドカード文字です。ワイルドカード文字を使用することができます ( `*`) か、数の範囲内または信頼度の範囲内ではなく、機密性の高い型です。 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>電子情報開示センターで使用できるその他のクエリ プロパティと検索演算子

SharePoint の DLP では、プロパティ、することができますが特定の期間内にスキャンされたファイルを検索する LastSensitiveContentScan も紹介します。クエリの例については、`LastSensitiveContentScan`プロパティでは、次のセクションで[複雑なクエリの例](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries)を参照してください。 
  
DLP 固有のプロパティをクエリを作成するだけでなく、標準的な SharePoint の電子的証拠開示検索のプロパティを次のように使用することができます`Author`または`FileExtension`。複雑なクエリを作成するのに演算子を使用することができます。、使用できるプロパティと演算子の一覧は、[検索のプロパティを使用して、電子的証拠開示の演算子](https://go.microsoft.com/fwlink/?LinkId=510093)のブログの記事を参照してください。 
  
## <a name="examples-of-complex-queries"></a>例

次の例では、正確にどのような探しているを検索するのにようにクエリを調整する方法を説明するために機密性の高い別の型、プロパティ、および演算子を使用します。
  
|**クエリ**|**説明**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |名前が奇妙に思われるが長い、その機密性の高いタイプの正しい名前であるためです。[機密性の高い情報の種類の在庫](https://go.microsoft.com/fwlink/?LinkID=509999)からの正確な名前を使用することを確認してください。組織用に作成した[カスタムの機密性の高い情報の種類](create-a-custom-sensitive-information-type.md)の名前を使用することもできます。<br/> |
| ' SensitiveType:「クレジット カード番号|1..4294967295|1..100"' <br/> |機密性の高い型「クレジット カード番号」に 1 つ以上と一致するドキュメントが返されますそれぞれの範囲の値は、それぞれの最小値と最大値です。このクエリを記述する簡単な方法は、`SensitiveType:"Credit Card Number"`が、そのメリットはどこですか?<br/> |
| ' SensitiveType:「クレジット カード番号| 5..25"と LastSensitiveContentScan:"8/11/2018..8/13/2018"' <br/> |2018 年 8 月 13日を通じて、2018 年 8 月 11日からスキャンされた 5-25 クレジット カード番号を持つドキュメントを返します。  <br/> |
| ' SensitiveType:「クレジット カード番号| 5..25"と LastSensitiveContentScan:"8/11/2018..8/13/2018"FileExtension:XLSX ではない ' <br/> |2018 年 8 月 13日を通じて、2018 年 8 月 11日からスキャンされた 5-25 クレジット カード番号を持つドキュメントを返します。拡張子が XLSX ファイルは、クエリ結果に含まれません。 `FileExtension`は、クエリに含めることができる多くのプロパティの 1 つです。詳細については、[検索のプロパティを使用して、電子的証拠開示の演算子](https://go.microsoft.com/fwlink/?LinkId=510093)を参照してください。<br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |クレジット カード番号または社会保障番号が含まれているドキュメントを返します。  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>例

等しいすべてのクエリが作成されます。次の表は、SharePoint の DLP で動作しないクエリの例し、理由を説明します。
  
|**サポートされていないクエリ**|**Reason**|
|:-----|:-----|
| ' SensitiveType:「クレジット カード番号|.."` <br/> |少なくとも 1 つの値を追加する必要があります。  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule"では、機密性の高いタイプの有効な名前はありません。[機密性の高い情報の種類の在庫](https://go.microsoft.com/fwlink/?LinkID=509999)の名前だけでは、DLP のクエリで動作します。<br/> |
| ' SensitiveType:「クレジット カード番号|0"' <br/> |0 は、最小値または最大値の範囲内のいずれかとして正しくありません。  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |見えにくい場合がありますが、「クレジット」と無効なクエリは、「カード」と間の余分な空白文字があります。[機密性の高い情報の種類の在庫](https://go.microsoft.com/fwlink/?LinkID=509999)からの機密の正確な型名を使用します。<br/> |
| ' SensitiveType:「クレジット カード番号|1.。 3"' <br/> |2 期部分は、スペースで区切る必要はありません。  <br/> |
| ' SensitiveType:「クレジット カード番号| |1.|80.."' <br/> |多くのパイプ区切り記号 (|).以下この形式の代わりに: ' SensitiveType:「クレジット カード番号|1.|80.."' <br/> |
| ' SensitiveType:「クレジット カード番号|1.|80..101"' <br/> |信頼度の値は、パーセンテージを表す、ため 100 を超えることはできません。代わりに、1 から 100 までの数を選択します。  <br/> |
   
## <a name="for-more-information"></a>詳細情報

[機密情報の種類の検索基準](what-the-sensitive-information-types-look-for.md)
  
[Office 365 のセキュリティ コンテンツの検索を実行する&amp;コンプライアンス センター](run-a-content-search-in-the-security-and-compliance-center.md)
  
[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
  

