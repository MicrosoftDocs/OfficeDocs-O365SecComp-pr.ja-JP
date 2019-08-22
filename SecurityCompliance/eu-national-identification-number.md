---
title: EU 国家識別番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 国内の識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: cbcacb3f85877f5a84238468fb52d612d90f5f0b
ms.sourcegitcommit: 3f3f3ecb28ef65d023f3573f9a4e09a0586d8f53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36490774"
---
# <a name="eu-national-identification-number"></a>EU 国家識別番号

このトピックでは、データ損失防止 (DLP) ポリシーが EU 国内の識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
  
## <a name="austria"></a>オーストリア

### <a name="format"></a>Format

24文字の文字、数字、特殊文字の組み合わせ
  
### <a name="pattern"></a>パターン

24文字:
  
-  22文字 (大文字小文字を区別しない)、数字、円記号、スラッシュ、またはプラス記号 
    
- 2つの文字 (大文字小文字を区別しない)、数字、バックスラッシュ、スラッシュ、プラス記号、または等号
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_austria_eu_national_id_card`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_austria_eu_national_id_card`キーワードが見つかりました。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

オーストリアの id 番号
  
国内の id 番号
  
id 番号
  
national id
  
personalausweis republik österreich
  
## <a name="belgium"></a>ベルギー

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ベルギー国立番号」セクションを参照してください。
  
## <a name="bulgaria"></a>ブルガリア

### <a name="format"></a>Format

スペースと区切り文字を含まない10桁の数字
  
### <a name="pattern"></a>パターン

スペースと区切り文字を含まない10桁の数字
  
-  誕生日に対応する6桁の数字 (YYMMDD という) 
    
- 誕生日の順序に対応する2桁の数字
    
- 性別に対応する1桁の数字: 男性の偶数桁で、女性に奇数の数字
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_bulgaria_national_number`は、パターンに一致するコンテンツを検索します。 
    
- From `Keywords_bulgaria_national_number`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_bulgaria_national_number`は、パターンに一致するコンテンツを検索します。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_bulgaria_national_number"></a>Keywords_bulgaria_national_number

「//入力 n」
  
「//入力 n」#
  
ブルガリアの国番号
  
国番号
  
social security number
  
nationalnumber#
  
ssn#
  
ssn
  
nationalnumber
  
bnn#
  
bnn
  
個人 id 番号
  
personalidnumber#
  
единен граждански номер
  
edinen grazhdanski nomer
  
егн
  
егн#
  
## <a name="croatia"></a>クロアチア

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「クロアチアの id 番号」セクションを参照してください。
  
## <a name="cyprus"></a>キプロス

### <a name="format"></a>Format

スペースと区切り文字を含まない10桁の数字
  
### <a name="pattern"></a>パターン

 10桁の数字 
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_cyprus_eu_national_id_card`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_cyprus_eu_national_id_card`キーワードが見つかりました。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

id カード番号
  
national identification number
  
個人 id 番号
  
id カード番号
  
ταυτοτητασ
  
## <a name="czech-republic"></a>チェコ共和国

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「チェコ国立 id 番号」セクションを参照してください。
  
## <a name="denmark"></a>デンマーク

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「デンマークの個人識別番号」セクションを参照してください。
  
## <a name="estonia"></a>エストニア

### <a name="format"></a>Format

スペースと区切り文字を含まない11桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
- 性別と世紀に対応する1桁の数字 (奇数個の男性、偶数の女性、1-2:19 世紀、3-4:20 世紀、5-6:21 世紀)
    
- 誕生日に対応する6桁の数字 (YYMMDD という)
    
- 同じ日付に出生地を分けるシリアル番号に対応する3桁の数字
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_estonia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
- From `Keywords_estonia_eu_national_id_card`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_estonia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

個人識別コード
  
個人識別番号
  
national identification number
  
国番号
  
個人 id 番号
  
personalidnumber#
  
ik
  
isikukood
  
id-kaart
  
## <a name="finland"></a>フィンランド

詳細については、「フィンランド国立 ID」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。
  
## <a name="france"></a>フランス

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランス国立 ID カード (CNI)」セクションを参照してください。
  
## <a name="germany"></a>ドイツ

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツの Id カード番号」セクションを参照してください。
  
## <a name="greece"></a>ギリシャ

詳細については、「ギリシャの国民 ID カード」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。
  
## <a name="hungary"></a>ハンガリー

### <a name="format"></a>Format

11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
-  性別に対応する1桁の数字 (1-オス、2-女性、その他の数字は1900または市民が二重市民権を持つ市民の場合もあります) 
    
- 誕生日に対応する6桁の数字 (YYMMDD という)
    
- シリアル番号に対応する3桁の数字
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
- From `Keywords_hungary_eu_national_id_card`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

個人識別番号
  
identification number
  
個人 id 番号
  
személyazonosító igazolvány
  
## <a name="ireland"></a>アイルランド

### <a name="format"></a>Format

指定したパターンの文字、数字、スペースの9文字の組み合わせ
  
### <a name="pattern"></a>パターン

指定したパターンの文字、数字、スペースの9文字の組み合わせ
  
01年 1 2013 月から今すぐに。
  
-  7 桁の数字  
    
- 1つのチェックディジット
    
- 1つのスペースまたは大文字の "W" (大文字小文字を区別)
    
01年1月2013前:
  
-  7 桁の数字  
    
- 1つのチェックディジット
    
- 1つのスペースまたは大文字 (大文字と小文字を区別)
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数は、パターンに一致するコンテンツを検索します。
    
- From キーワードが見つかりました。
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数は、パターンに一致するコンテンツを検索します。
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

個人用パブリックサービス番号
  
pps no
  
収益および社会保険番号
  
rsi no
  
個人識別番号
  
identification number
  
個人 id 番号
  
uimhir phearsanta seirbhíse poiblí
  
uimh. psp
  
## <a name="italy"></a>イタリア

### <a name="format"></a>Format

指定したパターンの文字と数字の16文字の組み合わせ
  
### <a name="pattern"></a>パターン

文字と数字の16文字の組み合わせ。
  
- ファミリ名の最初の3つの子音に対応する3つの文字
    
- 最初の名前の最初、3番目、および4番目の子音に対応する3つの文字
    
- 誕生年の最後の桁に対応する2桁の数字
    
- 誕生日の文字に対応する1つの文字-文字はアルファベット順に使用されますが、A から E、H、L、M、P、R から T までの文字が使用されます (つまり、1月は A と10月は R)。
    
- Genders を区別するために、誕生日に対応する2桁の数字は、女性の誕生日に40が追加されます。
    
- 個人が生まれた municipality に固有のエリアコードに対応する4桁の数字 (国全体のコードは外国で使用されます)
    
- 1つのパリティ付き数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_italy_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
- From `Keywords_italy_eu_national_id_card`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_italy_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

個人コード
  
個人コード番号
  
個人証明書番号
  
会計コード
  
personalcodeno#
  
個人 id 番号
  
個人 id コード
  
codice 個人 ale
  
numero certificato 個人 ale
  
numero 個人 ale
  
numero id 個人 ale
  
codice id 個人 ale
  
codice fiscale
  
## <a name="latvia"></a>ラトビア

### <a name="format"></a>Format

11桁の数字と、指定された形式のハイフン
  
### <a name="pattern"></a>パターン

11桁の数字とハイフン:
  
-  誕生日に対応する6桁の数字 (DDMMYY) 
    
- ハイフン 1 つ 
    
- 誕生日の世紀に対応する1桁の数字 (「0」、20世紀の場合は「1」、21世紀の場合は「2」)
    
- ランダムに生成される4桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_latvia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
- From `Keywords_latvia_eu_national_id_card`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_latvia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

個人コード
  
個人コード番号
  
個人証明書番号
  
personalcodeno#
  
個人 id 番号
  
個人 id コード
  
ペルソナ kods
  
## <a name="lithuania"></a>リトアニア

### <a name="format"></a>Format

スペースと区切り文字を含まない11桁の数字
  
### <a name="pattern"></a>パターン

スペースと区切り文字を含まない11桁の数字:
  
- ユーザーの性別および誕生世紀に対応する1桁の数字
    
-  誕生日に対応する6桁の数字 (YYMMDD という) 
    
- 誕生日のシリアル番号に対応する3桁の数字
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_lithuania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
- From `Keywords_lithuania_eu_national_id_card`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_lithuania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

個人の数値コード
  
一意の識別番号
  
市民サービス番号
  
一意の id 番号
  
uniqueidentityno#
  
個人コード
  
asmeninis skaitmeninis das
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo のための das
  
asmens のためのものです。
  
## <a name="luxemburg"></a>ルクセンブルク

### <a name="format"></a>Format

スペースと区切り文字を含まない11桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字
  
- ユーザーの性別および誕生世紀に対応する1桁の数字
    
-  誕生日に対応する6桁の数字 (YYMMDD という) 
    
- 誕生日のシリアル番号に対応する3桁の数字
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_luxemburg_eu_national_id_card`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_luxemburg_eu_national_id_card`キーワードが見つかりました。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

個人 id
  
個人 id 番号
  
パーソナル id no#
  
一意の id 番号
  
personalidnumber#
  
一意の id キー
  
個人 id コード
  
uniqueidkey#
  
個別のコード
  
個別の id
  
eindeutige id-nummer
  
eindeutige id
  
id personnelle
  
numéro d'identification 職員
  
idpersonnelle#
  
persönliche identifikationsnummer
  
eindeutigeid#
  
## <a name="malta"></a>マルタ

### <a name="format"></a>Format

7桁の数字の後に1文字
  
### <a name="pattern"></a>パターン

7桁の数字の後に1文字。
  
-  7 桁の数字  
    
- 1つの大文字 (大文字と小文字を区別)
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_malta_eu_national_id_card`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_malta_eu_national_id_card`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_malta_eu_national_id_card`は、パターンに一致するコンテンツを検出します。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

個人の数値コード
  
一意の識別番号
  
市民サービス番号
  
一意の id 番号
  
uniqueidentityno#
  
kodiċi numerali パーソナル i
  
numru ta ' identifikazzjoni uniku
  
numru tas-servizz taċ-ċittadin
  
numru ta ' 識別子 tuniku
  
## <a name="netherlands"></a>オランダ

### <a name="format"></a>Format

スペースまたは区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_netherlands_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
- From キーワードが見つかりました。
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_netherlands_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

個人の数値コード
  
一意の識別番号
  
市民サービス番号
  
一意の id 番号
  
uniqueidentityno#
  
bsn
  
bsn#
  
persoonlijke numerieke コード
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>ポーランド

詳細については、「[機密情報の種類](what-the-sensitive-information-types-look-for.md)について」の「ポーランド国立 ID (pesel)」セクションを参照してください。
  
## <a name="portugal"></a>ポルトガル

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポルトガル市民カード番号」セクションを参照してください。
  
## <a name="romania"></a>ルーマニア

### <a name="format"></a>Format

13桁の数字 (スペースと区切り文字なし)
  
### <a name="pattern"></a>パターン

13 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_romania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
- From `Keywords_romania_eu_national_id_card`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_romania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

個人の数値コード
  
一意の識別番号
  
cnp
  
cnp#
  
pin
  
pin#
  
保険番号
  
insurancenumber#
  
一意の id 番号
  
uniqueidentityno#
  
cod 数値個人
  
cod 識別子 (個人)
  
cod の識別子は
  
număr 個人用非 ic
  
număr 識別子縦
  
număr 識別子の個人情報
  
număridentitate#
  
codnumericpersonal#
  
numărpersonalunic#
  
## <a name="slovakia"></a>スロバキア

### <a name="format"></a>Format

1つの円記号を含む10桁の数字
  
### <a name="pattern"></a>パターン

1つの円記号を含む10桁の数字:
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovakia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
- From `Keywords_slovakia_eu_national_id_card`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovakia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

出生地番号
  
national identification number
  
個人識別番号
  
social security number
  
nationalnumber#
  
ssn#
  
ssn
  
国番号
  
個人 id 番号
  
personalidnumber#
  
rč
  
rodnéčíslo
  
rodne cislo
  
## <a name="slovenia"></a>スロベニア

### <a name="format"></a>Format

13桁の数字、スペースまたは区切り記号なし
  
### <a name="pattern"></a>パターン

指定したパターンの13桁の数字:
  
-  誕生日 (DDMMLLL) に対応する7桁の数字で、"LLL" は誕生年の最後の3桁に対応します。 
    
- 誕生日の範囲に対応する2桁の数字
    
- 同じ日に生まれた人物の性別とシリアル番号の組み合わせに対応する3つの数字 (女性の場合は男性と500-999 は 000-499)
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovenia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
- From `Keywords_slovenia_eu_national_id_card`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovenia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

個人の数値コード
  
一意の識別番号
  
一意の登録番号
  
一意の id 番号
  
uniqueidentityno#
  
一意のマスター市民番号
  
edinstベンダー a identifikacijska številka
  
uniqueidentityno#
  
edinstベンダー a številka glavnega državljana
  
emšo
  
## <a name="spain"></a>スペイン

### <a name="format"></a>Format

7桁の数字の後に1文字
  
### <a name="pattern"></a>パターン

7桁の数字の後に1文字
  
- 7 桁の数字 
    
- 1桁の数字または文字 (大文字小文字を区別しない)
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_spain_eu_national_id_card`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_spain_eu_national_id_card"`キーワードが見つかりました。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

dni
  
national identification number
  
国内の id 番号
  
保険番号
  
個人識別番号
  
国民 id
  
個人 id いいえ
  
一意の id 番号
  
nationalidno#
  
見つから#
  
dni#
  
nationalid#
  
nie#
  
nie
  
nienúmero#
  
nie número
  
documento nacional de 識別子 dad
  
dad único の識別子
  
número nacional 識別子 dad
  
dni número
  
dninúmero#
  
identidadúnico#
  
## <a name="sweden"></a>スウェーデン

詳細については、「スウェーデン国立 ID」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。
  
## <a name="see-also"></a>関連項目

[機密情報の種類の検索基準:](what-the-sensitive-information-types-look-for.md)

