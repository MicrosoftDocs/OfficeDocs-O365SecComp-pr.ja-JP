---
title: EU 税 Id 番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 税 Id 番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
ms.openlocfilehash: 5192496b393d15fd6d063e09c9bfe1cb3dd7e2dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532123"
---
# <a name="eu-tax-identification-number"></a>EU 税 Id 番号

このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 税 Id 番号 (TIN) 機密情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
  
## <a name="austria"></a>オーストリア

### <a name="format"></a>形式

任意指定のハイフンとスラッシュの 9 つの数字
  
### <a name="pattern"></a>パターン

任意指定のハイフンとスラッシュで 9 つの数字。
  
-  2 桁の数字 
    
- ハイフン (省略可能)
    
- 3 桁の数字
    
- スラッシュ (省略可能)
    
- 4 桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_austria_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_austria_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_austria_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsaustriaeutaxfilenumber"></a>Keywords_austria_eu_tax_file_number

税番号
  
番号
  
税務登録番号
  
tax id

  
st.nr。
  
steuernummer
  
## <a name="belgium"></a>ベルギー

### <a name="format"></a>形式

スペースや区切り記号なし 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
- 2 桁の数字
    
- 「0」または「1」
    
- 1 桁の数字
    
- 「0」または「1」または「2」または「3」 
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_belgium_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_belgium_eu_tax_file_number`があります。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsbelgiumeutaxfilenumber"></a>Keywords_belgium_eu_tax_file_number

税番号
  
国内の登録番号
  
税務登録番号
  
tax id

  
%n
  
%n #
  
numéro de registre の国
  
numéro d'identification fiscale
  
## <a name="bulgaria"></a>ブルガリア

### <a name="format"></a>形式

スペースや区切り記号なしの 10 桁
  
### <a name="pattern"></a>パターン

10 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_bulgaria_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_bulgaria_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_bulgaria_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsbulgariaeutaxfilenumber"></a>Keywords_bulgaria_eu_tax_file_number

bucn
  
統一された民事上の数
  
bucn #
  
uniformcivilnumber #
  
民事 id の統一
  
民事なしの統一されました。
  
egn
  
ブルガリア語の統一された民事数
  
uniformcivilno #
  
egn #
  
УНИФОРМ ГРАЖДАНСКИ НОМЕР
  
Униформ id
  
Униформ граждански id
  
УНИФОРМ ГРАЖДАНСКИ НЕ
  
## <a name="croatia"></a>クロアチア

### <a name="format"></a>形式

スペースや区切り文字なしで 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
- ランダムに選択した 10 個の数字
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_croatia_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_croatia_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_croatia_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordscroatiaeutaxfilenumber"></a>Keywords_croatia_eu_tax_file_number

税番号
  
税
  
tax id

  
oid
  
oid 番号
  
porezni broj
  
## <a name="cyprus"></a>キプロス

### <a name="format"></a>形式

8 桁と指定されたパターンの 1 つの文字
  
### <a name="pattern"></a>パターン

8 桁の数字および文字を 1 つ。
  
-  「0」 
    
- 7 桁の数字 
    
- 1 つの文字 (文字列)
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_cyprus_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_cyprus_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_cyprus_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordscypruseutaxfilenumber"></a>Keywords_cyprus_eu_tax_file_number

税番号
  
税
  
tax id

  
税の識別コード
  
tic
  
tic #
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ
  
ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="czech-republic"></a>チェコ共和国

### <a name="format"></a>形式

オプションの円記号と 9 桁または 10 桁の数字
  
### <a name="pattern"></a>パターン

9 桁または 10 桁の数字、省略可能な backslashl で:
  
- 6 桁の数字 
    
- バック スラッシュ (省略可能)
    
- 3 つまたは 4 つの数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_czech_republic_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_czech_republic_eu_tax_file_number`があります。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsczechrepubliceutaxfilenumber"></a>Keywords_czech_republic_eu_tax_file_number

税番号
  
税
  
tax id

  
個人番号
  
daňové číslo
  
osobní číslo
  
## <a name="denmark"></a>デンマーク

### <a name="format"></a>形式

10 桁の数字、ハイフンを含む
  
### <a name="pattern"></a>パターン

10 個の数字が、hyphenl が含まれています。
  
-  6 桁の数字が日付の生年月日に対応します。 
    
- ハイフン 1 つ 
    
- 生年月日の 4 桁の年に最初の桁が対応するシーケンス番号に対応する 4 桁の数字と最後の桁は、個人の性別を (男性と女性の場合でも、奇数ページ) に対応します。
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_denmark_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_denmark_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_denmark_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsdenmarkeutaxfilenumber"></a>Keywords_denmark_eu_tax_file_number

税番号
  
税
  
tax id

  
cpr の数
  
cpr #
  
skat nummer
  
skat id
  
## <a name="estonia"></a>エストニア

### <a name="format"></a>形式

スペースや区切り文字なしで 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
-  性別および誕生日、奇数個 (オス) を示し、ことを示します (メス) を次のように、偶数の世紀に対応する 1 つの数字: 1, 2; 19 世紀の最後の3、4 の 20 世紀の年です。5、6、21 世紀の 
    
- 生年月日 (YYMMDD) に対応する 6 桁の数字
    
- シリアル番号が同じ日に生まれた人を分離することに対応する 3 桁の数字
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_estonia_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_estonia_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_estonia_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsestoniaeutaxfilenumber"></a>Keywords_estonia_eu_tax_file_number

税番号
  
税
  
tax id

  
個人コード
  
maksunumber
  
maksu id
  
isikukood
  
## <a name="finland"></a>フィンランド

### <a name="format"></a>形式

数字、11 文字の組み合わせは、次の文字、およびプラス記号とマイナス記号
  
### <a name="pattern"></a>パターン

数字、11 文字の組み合わせは、次の文字、およびプラス記号とマイナス記号。
  
- 6 桁の数字
    
- 次のいずれか: プラス記号、マイナス記号またはプラス記号の意味、文字"A"(大文字小文字を区別) 1800-1899 の間に生まれたマイナスの署名との間に生まれた意味 1900-1999 年、および"2000 の誕生は A"し、
    
- 3 桁の数字
    
- 1 つの文字または 1 つの数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_finland_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_finland_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_finland_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsfinlandeutaxfilenumber"></a>Keywords_finland_eu_tax_file_number

identification number

  
パーソナル id
  
id 番号
  
フィンランドの国民 id 番号
  
personalidnumber #
  
国際識別番号
  
id 番号
  
国民 id なし。
  
国民 id 番号
  
id なし
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
identiteetti して
  
suomen kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
kansallinen tunnus して
  
## <a name="france"></a>フランス

### <a name="format"></a>形式

個人やエンティティの 9 桁の 13 桁の数字
  
### <a name="pattern"></a>パターン

個人の 13 桁の数字。
  
- 1 桁の 0、1、2、または 3 にする必要があります。
    
- 12 桁の数字
    
エンティティの 9 桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_france_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_france_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_france_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsfranceeutaxfilenumber"></a>Keywords_france_eu_tax_file_number

税 id 番号
  
税番号
  
tax id

  
numéro d'identification fiscale
  
## <a name="germany"></a>ドイツ

### <a name="format"></a>形式

スペースや区切り記号なし 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字。
  
-  10 桁の数字 
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_germany_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_germany_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_germany_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsgermanyeutaxfilenumber"></a>Keywords_germany_eu_tax_file_number

税番号
  
なしの税です。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税 id 番号
  
税 id が不要です。
  
steuernummer
  
steuer id
  
steueridentifikationsnummer
  
## <a name="greece"></a>ギリシャ

### <a name="format"></a>形式

スペースや区切り記号なしの 9 桁
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_greece_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_greece_eu_tax_file_number`があります。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsgreeceeutaxfilenumber"></a>Keywords_greece_eu_tax_file_number

afm
  
tin

  
税 id のないです。
  
税 id のないです。
  
税 id 番号
  
税登録番号
  
レジストリを税不要です。
  
afm #
  
tin #
  
taxidno #
  
taxregistryno #
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
aφμ
  
aφμ αριθμός
  
ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。
  
ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="hungary"></a>ハンガリー

### <a name="format"></a>形式

スペースや区切り文字で 10 桁の数字
  
### <a name="pattern"></a>パターン

10 桁の数字。
  
-  1 桁の数字「8」をする必要があります。 
    
- 日付間の日数に対応する 5 桁の数字 01/01/1867 および個人の生まれた日
    
- 同じ日に生まれた個人を区別するために偶然に生成された番号に対応する 3 桁の数字
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_hungary_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordshungaryeutaxfilenumber"></a>Keywords_hungary_eu_tax_file_number

ハンガリー語の税 id 番号
  
ハンガリー語の tin
  
税 id 番号
  
vat 番号
  
税務当局がありません。
  
税 id 税 id の番号
  
taxidnumber #
  
tin #
  
hungatiantin #
  
税の識別をしません。
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Ireland

### <a name="format"></a>形式

スペースや区切り記号のない文字の後に 7 桁の数字
  
### <a name="pattern"></a>パターン

文字の後に 7 桁の数字:
  
-  7 桁の数字  
    
- 1 つの文字 (文字列)
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_ireland_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_ireland_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_ireland_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsirelandeutaxfilenumber"></a>Keywords_ireland_eu_tax_file_number

公共サービスなし
  
個人の公的サービスなし
  
pps なし
  
個人サービスなし
  
pps のサービスなし
  
ppsno #
  
アイルランド pps なし
  
publicserviceno #
  
個人の公的サービスの数
  
uimhir phearsanta seirbhíse poiblí
  
pps uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>イタリア

### <a name="format"></a>形式

16 文字と数字で指定されたパターン
  
### <a name="pattern"></a>パターン

16 の文字と数字の場合。
  
-  ファミリ名の最初の 3 つの子音に対応する 3 つの文字 
    
- 第 1、3 番目および 4 番目に対応する 3 文字名の子音
    
- 2 桁の桁の誕生年の最後に対応しています。
    
- 生年月日の月に対応する 1 つの数字、文字は、アルファベット順で使用されますが、た E、H、L、M、P、t、R には、使用 (つまり、1 月 A で、10 月 R)
    
- 男女を区別するために女性の誕生日の日に 40 を追加する位置の生年月日の月の日付に対応する 2 つの数字
    
- 個人の生まれた場所の自治体に特定の市外局番に対応する 4 桁の数字、国全体のコードを使用して外部の国
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_italy_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_italy_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_italy_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsitalyeutaxfilenumber"></a>Keywords_italy_eu_tax_file_number

税番号
  
なしの税です。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
会計年度コード
  
codice fiscale
  
## <a name="latvia"></a>ラトビア

### <a name="format"></a>形式

スペースや区切り文字なしで 11 桁の数字
  
### <a name="pattern"></a>パターン

指定したパターンに 11 桁の数字
  
-  生年月日の日付に対応する 6 桁の数字 
    
- 生年月日が「0」は、19 世紀に対応して、20 世紀年を「1」に対応して、"2"は、21 世紀の世紀に対応する 1 つの数字
    
- 4 桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_latvia_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_latvia_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_latvia_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordslatviaeutaxfilenumber"></a>Keywords_latvia_eu_tax_file_number

税番号
  
なしの税です。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税 id 番号
  
税 id が不要です。
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>リトアニア

### <a name="format"></a>形式

スペースや区切り文字なし 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_lithuania_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_lithuania_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_lithuania_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordslithuaniaeutaxfilenumber"></a>Keywords_lithuania_eu_tax_file_number

税番号
  
なしの税です。
  
税なしで
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税 id 番号
  
税 id が不要です。
  
mokesčių id
  
mokesčių numeris
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>ルクセンブルグ

### <a name="format"></a>形式

スペースや区切り記号で 13 桁の数字
  
### <a name="pattern"></a>パターン

13 桁の数字:
  
-  11 桁の数字 
    
- 2 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_luxemburg_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_luxemburg_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_luxemburg_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsluxemburgeutaxfilenumber"></a>Keywords_luxemburg_eu_tax_file_number

税番号
  
なしの税です。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税 id 番号
  
税 id が不要です。
  
steuernummer
  
steuer id
  
steueridentifikationsnummer
  
## <a name="malta"></a>マルタ

### <a name="format"></a>形式

マルタ籍の人々 の: 7 桁と指定されたパターンの 1 つの文字
  
マルタ語のない外国人向けのも、マルタ語のエンティティ: 9 桁の数字
  
### <a name="pattern"></a>パターン

マルタ籍の人々: 7 桁の数字および文字を 1 つ
  
-  7 桁の数字  
    
- 1 つの文字 (文字列)
    
マルタ語のない外国人向けのも、マルタ語のエンティティ: 9 桁の数字
  
-  9 桁の数字 
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_malta_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_malta_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_malta_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsmaltaeutaxfilenumber"></a>Keywords_malta_eu_tax_file_number

税番号
  
なしの税です。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税 id 番号
  
税 id が不要です。
  
numru tat-taxxa
  
id tat-taxxa
  
numru どっち ' identifikazzjoni tat-taxxa
  
## <a name="netherlands"></a>オランダ

### <a name="format"></a>形式

スペースや区切り文字なしの 9 つの数字
  
### <a name="pattern"></a>パターン

9 桁の数字 
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_netherlands_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_netherlands_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_netherlands_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsnetherlandseutaxfilenumber"></a>Keywords_netherlands_eu_tax_file_number

オランダ税 id 番号
  
オランダの税 id
  
オランダの税 id 番号
  
オランダの税 id
  
税 id 番号
  
オランダの納税者番号
  
オランダ語の税 id 番号
  
tax id

  
税 id 番号
  
税番号
  
税なしで
  
税番号
  
tin

  
tin #
  
オランダ tin
  
オランダの tin
  
nederlands belasting identificatienummer
  
identificatienummer van belasting
  
identificatienummer belasting
  
nederlands belasting identificatie
  
nederlands belasting id nummer
  
nederlands belastingnummer
  
ところで nummer
  
nederlandse belasting identificatie
  
## <a name="poland"></a>ポーランド

### <a name="format"></a>形式

スペースや区切り文字なしで 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_poland_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_poland_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_poland_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordspolandeutaxfilenumber"></a>Keywords_poland_eu_tax_file_number

税番号
  
なしの税です。
  
taxno #
  
taxnumber #
  
taxnumber
  
nip
  
nip #
  
tax id

  
税 id 番号
  
nip id
  
nip id 番号
  
税 id 番号
  
税 id が不要です。
  
vat 番号
  
いいえを vat です。
  
vatno #
  
vat id
  
vat id 番号
  
数値 identyfikacji podatkowej
  
polski の数値 identyfikacji podatkowej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>ポルトガル

### <a name="format"></a>形式

スペースや区切り文字なしで 9 桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_portugal_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_portugal_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_portugal_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsportugaleutaxfilenumber"></a>Keywords_portugal_eu_tax_file_number

税番号
  
なしの税です。
  
taxno #
  
taxnumber #
  
taxnumber
  
%n
  
%n #
  
会計して
  
número de identificação の会計
  
## <a name="romania"></a>ルーマニア

### <a name="format"></a>形式

スペースや区切り記号で 13 桁の数字
  
### <a name="pattern"></a>パターン

13 桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_romania_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_romania_eu_tax_file_number`があります。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsromaniaeutaxfilenumber"></a>Keywords_romania_eu_tax_file_number

tax id

  
税 id 番号
  
ファイルのない税します。
  


tax file number
  
税なし
  
税番号
  
taxid #
  
taxno #
  
id ul taxei
  
numărul デ identificare fiscală
  
## <a name="slovakia"></a>スロバキア

### <a name="format"></a>形式

スペースや区切り文字で 10 桁の数字
  
### <a name="pattern"></a>パターン

10 桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_slovakia_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_slovakia_eu_tax_file_number`があります。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsslovakiaeutaxfilenumber"></a>Keywords_slovakia_eu_tax_file_number

tax id

  
税 id 番号
  
ティン id
  
ティンなし
  
スロバキア語ティン id
  
tin

  
ファイルのない税します。
  


tax file number
  
税なし
  
税番号
  
taxid #
  
taxno #
  
daňové identifikačné číslo
  
daňové číslo
  
daňové číslo súboru
  
## <a name="slovenia"></a>スロベニア

### <a name="format"></a>形式

スペースや区切り文字なしで 8 つの数字
  
### <a name="pattern"></a>パターン

8 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovenia_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_slovenia_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovenia_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordssloveniaeutaxfilenumber"></a>Keywords_slovenia_eu_tax_file_number

tax id

  
税 id 番号
  
ティン id
  
ティンなし
  
スロベニア語ティン id
  
tin

  
ファイルのない税します。
  


tax file number
  
税なし
  
税番号
  
taxid #
  
taxno #
  
identifikacijska številka davka
  
davčna številka
  
Številka davčne datoteke
  
## <a name="spain"></a>スペイン

### <a name="format"></a>形式

7 または 8 桁の数字と 1 つまたは 2 つの文字を指定したパターンに
  
### <a name="pattern"></a>パターン

スペイン国内の Id カードを使用して自然なスペイン語の担当者:
  
-  8 桁の数字 
    
- 大文字を 1 つ (大文字小文字を区別) 
    
非居住のスペイン スペイン国内の身分証明書なし
  
- 大文字"L"(大文字小文字を区別) を 1 つ
    
- 7 桁の数字 
    
- 大文字を 1 つ (大文字小文字を区別) 
    
14 年にスペイン国内の Id カードの有効期間] の下のスペインを常駐。
  
- 1 つの大文字文字"K"(大文字小文字を区別)
    
-  7 桁の数字  
    
- 大文字を 1 つ (大文字小文字を区別)
    
他民族の識別番号を使って他の民族
  
- 大文字文字"X"、"Y"、または"Z"(大文字小文字を区別) では 
    
- 7 桁の数字 
    
- 大文字を 1 つ (大文字小文字を区別) 
    
他民族の Id 番号のない他
  
- 大文字を 1 つは"M"(大文字小文字を区別) 
    
- 7 桁の数字 
    
- 大文字を 1 つ (大文字小文字を区別) 
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_spain_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_spain_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_spain_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsspaineutaxfilenumber"></a>Keywords_spain_eu_tax_file_number

tax id

  
税 id 番号
  
cif id
  
cif なし
  
スペイン語の cif id
  
cif
  
ファイルのない税します。
  
スペイン語の cif 番号
  


tax file number
  
スペイン語の cif なし
  
税なし
  
税番号
  
taxid #
  
taxno #
  
cifid #
  
spanishcifid #
  
spanishcifno #
  
número デ contribuyente
  
número de impuesto corporativo
  
número de identificación の会計
  
cif número
  
cifnúmero #
  
## <a name="sweden"></a>スウェーデン

### <a name="format"></a>形式

10 桁の数字と記号で指定されたパターン
  
### <a name="pattern"></a>パターン

10 桁の数字および記号。
  
-  生年月日 (YYMMDD) に対応する 6 桁の数字 
    
- プラス記号、マイナス記号、または円記号)
    
- Id を構成する 3 桁の数字番号の一意の場所。 
    
  - 1990 年以前に発行された番号の 7 番目と 8 番目の数字は生年月日や foreign-born の人の市区郡を識別します。
    
  - 数字の 9 番目の位置では、男性または女性の場合も、どちらが奇数で性別を示します
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_sweden_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_sweden_eu_tax_file_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_sweden_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsswedeneutaxfilenumber"></a>Keywords_sweden_eu_tax_file_number

tax id

  
税 id のないです。
  
税 id 番号
  
tax identification

  
税識別番号
  
なしの税です。
  
税番号
  
taxid #
  
税ファイル
  
ファイルのない税です。
  
個人の id 番号
  
skatt id nummer
  
skatt identifikation
  
personnummer
  
## <a name="uk"></a>英国

### <a name="format"></a>形式

スペースや区切り記号のない 10 桁の一意な納税者 (UTR) を参照します。
  
国民保険番号 (NINO): 詳細についてを参照してください「英国国民保険番号 (NINO)」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。
  
### <a name="pattern"></a>パターン

10 桁の一意な納税者 (UTR) を参照します。
  
国民保険番号 (NINO): 詳細についてを参照してください「英国国民保険番号 (NINO)」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_uk_eu_tax_file_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_uk_eu_tax_file_number`があります。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsukeutaxfilenumber"></a>Keywords_uk_eu_tax_file_number

tax id

  
税 id のないです。
  
税 id 番号
  
tax identification

  
税識別番号
  
なしの税です。
  
税番号
  
taxid #
  
税ファイル
  
ファイルのない税です。
  
## <a name="see-also"></a>関連項目

[機密情報の種類の検索基準:](what-the-sensitive-information-types-look-for.md)

