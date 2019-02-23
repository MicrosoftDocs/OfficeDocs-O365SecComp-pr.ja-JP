---
title: EU 税務識別番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: f851cce4be70fd41c24a7876d97c452f0a738eda
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213827"
---
# <a name="eu-tax-identification-number"></a>EU 税務識別番号

このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号 (TIN) 機密情報の種類を検出したときにどのように検索されるかを示します。この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
  
## <a name="austria"></a>オーストリア

### <a name="format"></a>形式

任意指定のハイフンとスラッシュ (/) を含む9桁の数字
  
### <a name="pattern"></a>パターン

任意指定のハイフンとスラッシュ (/) を含む9桁の数字:
  
-  2 桁の数字 
    
- ハイフン (省略可能)
    
- 3 桁の数字
    
- スラッシュ (省略可能)
    
- 4 桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_austria_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsaustriaeutaxfilenumber"></a>Keywords_austria_eu_tax_file_number

課税番号
  
件数
  
税務登録番号
  
tax id

  
st.nr。
  
steuernummer
  
## <a name="belgium"></a>ベルギー

### <a name="format"></a>形式

スペースと区切り文字を含まない11桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
- 2 桁の数字
    
- "0" または "1"
    
- 1 桁の数字
    
- "0" または "1" または "2" または "3" 
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>Definition

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_belgium_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_belgium_eu_tax_file_number`キーワードが見つかりました。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordsbelgiumeutaxfilenumber"></a>Keywords_belgium_eu_tax_file_number

課税番号
  
国内登録番号
  
税務登録番号
  
tax id

  
\n\n
  
\n\n
  
numéro de registre national
  
numéro d'identification fiscale
  
## <a name="bulgaria"></a>ブルガリア

### <a name="format"></a>形式

スペースと区切り文字を含まない10桁の数字
  
### <a name="pattern"></a>パターン

10 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_bulgaria_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsbulgariaeutaxfilenumber"></a>Keywords_bulgaria_eu_tax_file_number

bucn
  
一律の民事番号
  
bucn #
  
uniformcivilnumber #
  
uniform 民事 id
  
uniform 民事 no
  
「//入力 n」
  
ブルガリアの一様な民事訴訟番号
  
uniformcivilno #
  
"/入力 id"
  
униформгражданскиномер
  
униформ id
  
униформграждански id
  
униформгражданскине
  
## <a name="croatia"></a>クロアチア

### <a name="format"></a>形式

スペースまたは区切り文字を含まない11桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
- ランダムに選択された10桁の数字
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_croatia_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordscroatiaeutaxfilenumber"></a>Keywords_croatia_eu_tax_file_number

課税番号
  
申告
  
tax id

  
ドーナツ
  
ドーナツ
  
porezni broj
  
## <a name="cyprus"></a>キプロス

### <a name="format"></a>形式

指定したパターンの8桁の数字と1文字
  
### <a name="pattern"></a>パターン

8桁の数字と1つの文字:
  
-  "0" 
    
- 7 桁の数字 
    
- 1文字 (大文字小文字を区別しない)
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_cyprus_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordscypruseutaxfilenumber"></a>Keywords_cyprus_eu_tax_file_number

課税番号
  
申告
  
tax id

  
税 id コード
  
認め
  
認め
  
αριθμόςφορολογικούμητρώου
  
φορολογικήταυτότητα
  
κωδικόςφορολογικούμητρώου
  
## <a name="czech-republic"></a>チェコ共和国

### <a name="format"></a>形式

9桁または10桁の数字 (省略可能な円記号付き)
  
### <a name="pattern"></a>パターン

9桁または10桁の数字で、省略可能な backslashl を指定します。
  
- 6 桁の数字 
    
- 円記号 (省略可能)
    
- 3桁または4桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>Definition

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_czech_republic_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_czech_republic_eu_tax_file_number`キーワードが見つかりました。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordsczechrepubliceutaxfilenumber"></a>Keywords_czech_republic_eu_tax_file_number

課税番号
  
申告
  
tax id

  
個人番号
  
daňovéčíslo
  
osobníčíslo
  
## <a name="denmark"></a>デンマーク

### <a name="format"></a>形式

10桁の数字 (ハイフンを含む)
  
### <a name="pattern"></a>パターン

hyphenl を含む10桁の数字:
  
-  誕生日に対応する6桁の数字 (ddmmyy) 
    
- ハイフン 1 つ 
    
- 1桁目が誕生日の世紀に対応し、最後の桁は個人の性別に対応する4桁の数字 (男性の場合は奇数、女性の場合もあります)。
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_denmark_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsdenmarkeutaxfilenumber"></a>Keywords_denmark_eu_tax_file_number

課税番号
  
申告
  
tax id

  
cpr 番号
  
cpr
  
nummer の sk
  
id の sk
  
## <a name="estonia"></a>エストニア

### <a name="format"></a>形式

スペースまたは区切り文字を含まない11桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
-  性別と世紀に対応する1桁の数字。奇数は男性を表し、偶数の場合は1、2は19世紀に対しては女性を示します。20世紀に3、4世紀。21世紀の場合は5、6。 
    
- 誕生日に対応する6桁の数字 (yymmdd という)
    
- 同じ日付に出生地を分けるシリアル番号に対応する3桁の数字
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_estonia_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsestoniaeutaxfilenumber"></a>Keywords_estonia_eu_tax_file_number

課税番号
  
申告
  
tax id

  
個人コード
  
maksunumber
  
maksu id
  
isikukood
  
## <a name="finland"></a>フィンランド

### <a name="format"></a>形式

数字、文字、プラス記号とマイナス記号の11文字の組み合わせ
  
### <a name="pattern"></a>パターン

数字、文字、プラス記号とマイナス記号の11文字の組み合わせ。
  
- 6 桁の数字
    
- プラス記号、マイナス記号、または文字 "a" (大文字小文字を区別しない) の1つ。プラス記号を1800-1899 の間に置きます。マイナス記号は、1900-1999 の間に出生することを意味します。
    
- 3 桁の数字
    
- 1つの文字または1つの番号
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_finland_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsfinlandeutaxfilenumber"></a>Keywords_finland_eu_tax_file_number

identification number

  
個人 id
  
id 番号
  
フィンランドの国民 id 番号
  
personalidnumber #
  
国別の識別番号
  
id 番号
  
国民 id 番号
  
国民 id 番号
  
id 番号
  
tun/st列挙 o
  
henkilötunnus
  
yksilöllinen henkilökohtainen tun/st列挙 o
  
ainutlaatuinen henkilökohtainen tunnus
  
識別子 teetti numero
  
suomen kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tun/st列挙 o
  
tunnusnumero
  
kansallinen tunnus numero
  
## <a name="france"></a>フランス

### <a name="format"></a>形式

各ユーザーの13桁の数字、およびエンティティの9桁の数字
  
### <a name="pattern"></a>パターン

個人の場合は13桁。
  
- 0、1、2、または3である1桁の数字
    
- 12 桁の数字
    
エンティティの9桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_france_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsfranceeutaxfilenumber"></a>Keywords_france_eu_tax_file_number

税識別番号
  
課税番号
  
tax id

  
numéro d'identification fiscale
  
## <a name="germany"></a>ドイツ

### <a name="format"></a>形式

スペースと区切り文字を含まない11桁の数字
  
### <a name="pattern"></a>パターン

11桁の数字:
  
-  10桁の数字 
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_germany_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsgermanyeutaxfilenumber"></a>Keywords_germany_eu_tax_file_number

課税番号
  
課税番号
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税識別番号
  
税 id 番号
  
steuernummer
  
steuer id
  
steueridentifikationsnummer
  
## <a name="greece"></a>ギリシャ

### <a name="format"></a>形式

スペースと区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>Definition

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_greece_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_greece_eu_tax_file_number`キーワードが見つかりました。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordsgreeceeutaxfilenumber"></a>Keywords_greece_eu_tax_file_number

afm
  
tin

  
納税者番号
  
納税者番号
  
税識別番号
  
納税者番号
  
納税レジストリ番号
  
afm
  
は
  
taxidno #
  
taxregistryno #
  
αριθμόςφορολογικούμητρώου
  
aφμ
  
aφμαριθμός
  
φορολογικούμητρώουνο。
  
τοναριθμόφορολογικούμητρώου
  
## <a name="hungary"></a>ハンガリー

### <a name="format"></a>形式

スペースまたは区切り文字を含まない10桁の数字
  
### <a name="pattern"></a>パターン

10桁の数字:
  
-  "8" である1桁の数字 
    
- 日付01/01/1867 と個人の誕生日との間の日数に対応する5桁の数字
    
- 同じ日に生まれた個人を区別する機会によって生成された番号に対応する3桁の数字
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_hungary_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordshungaryeutaxfilenumber"></a>Keywords_hungary_eu_tax_file_number

ハンガリーの税識別番号
  
ハンガリー tin
  
納税者番号
  
vat 番号
  
税務当局番号
  
課税 id 番号
  
taxidnumber #
  
は
  
hungatiantin #
  
税 id 番号
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Ireland

### <a name="format"></a>形式

7桁の数字の後にスペースまたは区切り文字を含まない文字
  
### <a name="pattern"></a>パターン

7桁の数字の後に、文字を続けます。
  
-  7 桁の数字  
    
- 1文字 (大文字小文字を区別しない)
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_ireland_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsirelandeutaxfilenumber"></a>Keywords_ireland_eu_tax_file_number

パブリックサービスいいえ
  
個人用パブリックサービスいいえ
  
pps no
  
個人サービスいいえ
  
pps サービスいいえ
  
ppsno #
  
アイルランド語 (pps)
  
publicserviceno #
  
個人用パブリックサービス番号
  
uimhir phearsanta seirbhíse poiblí
  
pps uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>イタリア

### <a name="format"></a>形式

指定したパターンの16桁の文字と数字
  
### <a name="pattern"></a>パターン

16桁の文字と数字:
  
-  ファミリ名の最初の3つの子音に対応する3つの文字 
    
- 最初の名前の最初、3番目、および4番目の子音に対応する3つの文字
    
- 誕生年の最後の桁に対応する2桁の数字
    
- 誕生日に対応する1桁の数字。文字はアルファベット順に使用されますが、a から E、H、L、M、P、R から T までの文字が使用されます (つまり、1月は a と10月は r)。
    
- 誕生日に対応する2桁の数字。40が男性と区別するために女性の誕生日に追加されます。
    
- 個人が生まれた municipality に固有のエリアコードに対応する4桁の数字。国全体のコードが外国の国に使用されます。
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_italy_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsitalyeutaxfilenumber"></a>Keywords_italy_eu_tax_file_number

課税番号
  
課税番号
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
会計コード
  
codice fiscale
  
## <a name="latvia"></a>ラトビア

### <a name="format"></a>形式

スペースまたは区切り文字を含まない11桁の数字
  
### <a name="pattern"></a>パターン

指定したパターンの11桁の数字
  
-  誕生日に対応する6桁の数字 (ddmmyy) 
    
- "0" が19世紀に対応する1桁の数字、"1" は20世紀に、"2" は21世紀に対応します。
    
- 4 桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_latvia_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordslatviaeutaxfilenumber"></a>Keywords_latvia_eu_tax_file_number

課税番号
  
課税番号
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税識別番号
  
税 id 番号
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>リトアニア

### <a name="format"></a>形式

11桁の数字 (スペースまたは区切り文字なし)
  
### <a name="pattern"></a>パターン

11 桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_lithuania_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordslithuaniaeutaxfilenumber"></a>Keywords_lithuania_eu_tax_file_number

課税番号
  
課税番号
  
課税 no. #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税識別番号
  
税 id 番号
  
mokesčių id
  
mokesčių numeris
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>ルクセンブルク

### <a name="format"></a>形式

13桁の数字、スペースまたは区切り記号なし
  
### <a name="pattern"></a>パターン

13 桁の数字:
  
-  11 桁の数字 
    
- 2 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_luxemburg_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsluxemburgeutaxfilenumber"></a>Keywords_luxemburg_eu_tax_file_number

課税番号
  
課税番号
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税識別番号
  
税 id 番号
  
steuernummer
  
steuer id
  
steueridentifikationsnummer
  
## <a name="malta"></a>マルタ

### <a name="format"></a>形式

マルタ nationals の場合: 7 桁の数字と、指定したパターンの1文字
  
非マルタ nationals およびマルタエンティティ: 9 桁の数字
  
### <a name="pattern"></a>パターン

マルタ nationals: 7 桁と1文字
  
-  7 桁の数字  
    
- 1文字 (大文字小文字を区別しない)
    
非マルタ nationals およびマルタエンティティ: 9 桁の数字
  
-  9 桁の数字 
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>Definition

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_malta_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsmaltaeutaxfilenumber"></a>Keywords_malta_eu_tax_file_number

課税番号
  
課税番号
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税識別番号
  
税 id 番号
  
numru tat-taxxa
  
id tat-taxxa
  
numru ta ' identifikazzjoni tat-taxxa
  
## <a name="netherlands"></a>オランダ

### <a name="format"></a>形式

スペースまたは区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字 
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_netherlands_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsnetherlandseutaxfilenumber"></a>Keywords_netherlands_eu_tax_file_number

オランダの税識別番号
  
オランダの税 id
  
netherland の税識別番号
  
netherland の税 id
  
税識別番号
  
オランダの納税者番号
  
オランダの税識別番号
  
tax id

  
税 id 番号
  
課税番号
  
課税 no. #
  
申告
  
tin

  
は
  
オランダ tin
  
netherland の tin
  
nederlands belasting identificatienummer
  
identificatienummer van belasting
  
identificatienummer belasting
  
nederlands belasting 識別子
  
nederlands belasting id nummer
  
nederlands belastingnummer
  
btw nummer
  
nederlandse belasting 識別子
  
## <a name="poland"></a>ポーランド

### <a name="format"></a>形式

スペースまたは区切り文字を含まない11桁の数字
  
### <a name="pattern"></a>パターン

11桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_poland_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordspolandeutaxfilenumber"></a>Keywords_poland_eu_tax_file_number

課税番号
  
課税番号
  
taxno #
  
taxnumber #
  
taxnumber
  
nip
  
nip #
  
tax id

  
税 id 番号
  
nip id
  
nip id #
  
税識別番号
  
税 id 番号
  
vat 番号
  
vat 番号
  
vatno #
  
vat id
  
vat id #
  
特定 identyfikacji podat・ wewej
  
polski 特定 identyfikacji podat・ wej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>ポルトガル

### <a name="format"></a>形式

スペースまたは区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_portugal_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsportugaleutaxfilenumber"></a>Keywords_portugal_eu_tax_file_number

課税番号
  
課税番号
  
taxno #
  
taxnumber #
  
taxnumber
  
\n\n
  
\n\n
  
numero 会計
  
número de identificação 会計
  
## <a name="romania"></a>ルーマニア

### <a name="format"></a>形式

13桁の数字、スペースまたは区切り記号なし
  
### <a name="pattern"></a>パターン

13 桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>Definition

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_romania_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_romania_eu_tax_file_number`キーワードが見つかりました。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordsromaniaeutaxfilenumber"></a>Keywords_romania_eu_tax_file_number

tax id

  
納税者番号
  
税ファイル番号
  


tax file number
  
課税番号
  
課税番号
  
taxid #
  
taxno #
  
id-ul taxei
  
numărul de 識別子は fiscală
  
## <a name="slovakia"></a>スロバキア

### <a name="format"></a>形式

スペースまたは区切り文字を含まない10桁の数字
  
### <a name="pattern"></a>パターン

10 桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>Definition

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_slovakia_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_slovakia_eu_tax_file_number`キーワードが見つかりました。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordsslovakiaeutaxfilenumber"></a>Keywords_slovakia_eu_tax_file_number

tax id

  
納税者番号
  
tin id
  
tin no
  
スロバキア tin id
  
tin

  
税ファイル番号
  


tax file number
  
課税番号
  
課税番号
  
taxid #
  
taxno #
  
daňové identifikačnéčíslo
  
daňovéčíslo
  
daňovéčíslo súboru
  
## <a name="slovenia"></a>スロベニア

### <a name="format"></a>形式

スペースまたは区切り文字を含まない8桁の数字
  
### <a name="pattern"></a>パターン

8 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_slovenia_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordssloveniaeutaxfilenumber"></a>Keywords_slovenia_eu_tax_file_number

tax id

  
納税者番号
  
tin id
  
tin no
  
スロベニア tin id
  
tin

  
税ファイル番号
  


tax file number
  
課税番号
  
課税番号
  
taxid #
  
taxno #
  
identifikacijska številka davka
  
davčna številka
  
številka davčne datoteke
  
## <a name="spain"></a>スペイン

### <a name="format"></a>形式

7桁または8桁の数字と、指定したパターンの1文字または2文字
  
### <a name="pattern"></a>パターン

スペインの国民 id カードを持つスペインの自然の人物:
  
-  8 桁の数字 
    
- 1つの大文字 (大文字と小文字を区別) 
    
スペインの国民 id カードを持たない非常駐 Spaniards
  
- 1つの大文字の "L" (大文字と小文字を区別する)
    
- 7 桁の数字 
    
- 1つの大文字 (大文字と小文字を区別) 
    
Spaniards は、次のようにします。
  
- 1つの大文字の "K" (大文字と小文字を区別)
    
-  7 桁の数字  
    
- 1つの大文字 (大文字と小文字を区別)
    
Foreigner の id 番号を持つ Foreigners
  
- "X"、"Y"、または "Z" (大文字と小文字を区別) の1つの大文字 
    
- 7 桁の数字 
    
- 1つの大文字 (大文字と小文字を区別) 
    
Foreigner の識別番号のない Foreigners
  
- 1つの大文字の "M" (大文字と小文字を区別する) 
    
- 7 桁の数字 
    
- 1つの大文字 (大文字と小文字を区別) 
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_spain_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsspaineutaxfilenumber"></a>Keywords_spain_eu_tax_file_number

tax id

  
納税者番号
  
cif id
  
cif 番号
  
スペインの cif id
  
cif
  
税ファイル番号
  
スペインの cif 番号
  


tax file number
  
スペインの cif 番号
  
課税番号
  
課税番号
  
taxid #
  
taxno #
  
cifid #
  
spanishcifid #
  
spanishcifno #
  
número de contribuyente
  
número de impuesto corporativo
  
número de identificación 会計
  
cif número
  
cifnúmero #
  
## <a name="sweden"></a>スウェーデン

### <a name="format"></a>形式

指定したパターンの10桁の数字と記号
  
### <a name="pattern"></a>パターン

10桁の数字と記号:
  
-  誕生日に対応する6桁の数字 (yymmdd という) 
    
- プラス記号、マイナス記号、または円記号
    
- 識別番号を一意にするための3桁の数字: 
    
  - 1990より前に発行された番号については、7桁目と8桁目の数字は、誕生日または外国出身の人物を識別します。
    
  - 9桁の数字は、男性に対して、または女性に対して、性別を示します。
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_sweden_eu_tax_file_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsswedeneutaxfilenumber"></a>Keywords_sweden_eu_tax_file_number

tax id

  
納税者番号
  
納税者番号
  
tax identification

  
税 id #
  
課税番号
  
申告
  
taxid #
  
税ファイル
  
税ファイル番号
  
個人 id 番号
  
skatt id の nummer
  
skatt identifikation
  
personnummer
  
## <a name="uk"></a>英国

### <a name="format"></a>形式

Unique 納税リファレンス (utr): スペースと区切り文字を含まない10桁の数字
  
国家保険番号 (NINO): 詳細については、「[機密情報の種類がどのようなものか](what-the-sensitive-information-types-look-for.md)」の「英国国立保険番号 (NINO)」セクションを参照してください。
  
### <a name="pattern"></a>パターン

Unique 納税リファレンス (utr):10 桁の数字
  
国家保険番号 (NINO): 詳細については、「[機密情報の種類がどのようなものか](what-the-sensitive-information-types-look-for.md)」の「英国国立保険番号 (NINO)」セクションを参照してください。
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_uk_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_uk_eu_tax_file_number`キーワードが見つかりました。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordsukeutaxfilenumber"></a>Keywords_uk_eu_tax_file_number

tax id

  
納税者番号
  
納税者番号
  
tax identification

  
税 id #
  
課税番号
  
申告
  
taxid #
  
税ファイル
  
税ファイル番号
  
## <a name="see-also"></a>関連項目

[機密情報の種類の検索基準:](what-the-sensitive-information-types-look-for.md)

