---
title: EU 国民 Id 番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 国の識別番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
ms.openlocfilehash: 29d2126b937ff46039284a74eb2a84f2ebbacb41
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532090"
---
# <a name="eu-national-identification-number"></a>EU 国民 Id 番号

このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 国の識別番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
  
## <a name="austria"></a>オーストリア

### <a name="format"></a>形式

文字、数字、特殊文字の 24 文字の組み合わせ
  
### <a name="pattern"></a>パターン

24 文字。
  
-  22 の文字列の文字、数字、円記号 ()、スラッシュ、またはプラス記号 
    
- (いない大文字小文字を区別) の 2 つの文字、数字、円記号 ()、スラッシュのプラス記号または等号
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_austria_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_austria_eu_national_id_card`があります。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsaustriaeunationalidcard"></a>Keywords_austria_eu_national_id_card

オーストリアの id 番号
  
国内の id 番号
  
id 番号
  

national id
  
personalausweis republik österreich
  
## <a name="belgium"></a>ベルギー

詳細についてを参照してください「ベルギーの国番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="bulgaria"></a>ブルガリア

### <a name="format"></a>形式

スペースや区切り記号なしの 10 桁
  
### <a name="pattern"></a>パターン

スペースや区切り記号なしの 10 桁
  
-  生年月日 (YYMMDD) に対応する 6 桁の数字 
    
- 誕生の順序に対応する 2 つの数字
    
- 性別に対応する 1 つの数字: 男性と女性の場合、奇数桁の偶数
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_bulgaria_national_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_bulgaria_national_number`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_bulgaria_national_number`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsbulgarianationalnumber"></a>Keywords_bulgaria_national_number

egn
  
egn #
  
ブルガリアの国番号
  
国番号
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
個人の id 番号
  
personalidnumber #
  
ЕДИНЕН ГРАЖДАНСКИ НОМЕР
  
edinen grazhdanski nomer
  
ЕГН
  
ЕГН #
  
## <a name="croatia"></a>クロアチア

詳細についてを参照してください「クロアチア Id 番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="cyprus"></a>キプロス

### <a name="format"></a>形式

スペースや区切り記号なしの 10 桁
  
### <a name="pattern"></a>パターン

 10 桁の数字 
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_cyprus_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_cyprus_eu_national_id_card`があります。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordscypruseunationalidcard"></a>Keywords_cyprus_eu_national_id_card

id のカード番号
  
国際識別番号
  
個人の id 番号
  
身分証明書番号
  
ΤΑΥΤΟΤΗΤΑΣ
  
## <a name="czech-republic"></a>チェコ共和国

詳細についてを参照してください「チェコ国内の Id 番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="denmark"></a>デンマーク

詳細についてを参照してください「千葉県個人識別番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="estonia"></a>エストニア

### <a name="format"></a>形式

スペースや区切り記号なし 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
- 性別と生年月日の世紀に対応する 1 つの数字 (奇数番号 (オス)、偶数 (メス); 1-2: 19 世紀; 3-4: 20 世紀; 5-6: 21 世紀)
    
- 生年月日 (YYMMDD) に対応する 6 桁の数字
    
- シリアル番号が同じ日に生まれた人を分離することに対応する 3 桁の数字
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_estonia_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_estonia_eu_national_id_card`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_estonia_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsestoniaeunationalidcard"></a>Keywords_estonia_eu_national_id_card

個人識別コード
  
個人識別番号
  
国際識別番号
  
国番号
  
個人の id 番号
  
personalidnumber #
  
ik
  
isikukood
  
id kaart
  
## <a name="finland"></a>フィンランド

詳細についてを参照してください「フィンランドの国民 ID」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="france"></a>フランス

詳細についてを参照してください「フランス国内の ID カードいます (CNI)」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>ドイツ

詳細についてを参照してください"ドイツの Id カードの番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>ギリシャ

詳細についてを参照してください「ギリシャ国内の ID カード」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="hungary"></a>ハンガリー

### <a name="format"></a>形式

11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
-  (1 男性 2 女性、その他の番号が 1900 年より前に生まれた市民や二重市民権を持つ市民も) 性別に対応する 1 つの数字 
    
- 生年月日 (YYMMDD) に対応する 6 桁の数字
    
- シリアル番号に対応する 3 桁の数字
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_hungary_eu_national_id_card`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordshungaryeunationalidcard"></a>Keywords_hungary_eu_national_id_card

個人識別番号
  
identification number

  
個人の id 番号
  
személyazonosító igazolvány
  
## <a name="ireland"></a>Ireland

### <a name="format"></a>形式

文字、数字、および指定したパターンにスペースの 9 文字の組み合わせ
  
### <a name="pattern"></a>パターン

文字、数字、および指定したパターンにスペースの 9 文字の組み合わせ
  
現在までの 01 年 2013年 1 月。
  
-  7 桁の数字  
    
- 1 つのチェック ディジット
    
- 1 つのスペースや大文字の"W"(大文字と小文字を区別)
    
前の 01 年 2013年 1 月:
  
-  7 桁の数字  
    
- 1 つのチェック ディジット
    
- 1 つのスペースや大文字の文字 (大文字小文字を区別)
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数は、パターンに一致するコンテンツを検索します。
    
- キーワードを検出するとします。
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsirelandeunationalidcard"></a>Keywords_ireland_eu_national_id_card

個人の公的サービスの数
  
pps なし
  
収益と社会保険番号
  
rsi なし
  
個人識別番号
  
identification number

  
個人の id 番号
  
uimhir phearsanta seirbhíse poiblí
  
uimh。psp
  
## <a name="italy"></a>イタリア

### <a name="format"></a>形式

文字と数字で指定されたパターンの 16 文字の組み合わせ
  
### <a name="pattern"></a>パターン

文字と数字の 16 文字の組み合わせです。
  
- ファミリ名の最初の 3 つの子音に対応する 3 つの文字
    
- 第 1、3 番目および 4 番目に対応する 3 文字名の子音
    
- 2 桁の桁の誕生年の最後に対応しています。
    
- 生年月日の月の文字に対応する 1 つの文字、文字は、アルファベット順で使用されますが、た E、H、L、M、P、t、R には、使用 (つまり、1 月 A で、10 月 R)
    
- 生年月日の月の日付に対応する 2 つの数字、性別を区別するために 40、女性の誕生日の日に追加
    
- 個人の生まれた場所の自治体に固有の領域のコードに対応する 4 桁の数字 (外国の国全体のコードが使用されます)
    
- 1 桁のパリティ
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_italy_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_italy_eu_national_id_card`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_italy_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsitalyeunationalidcard"></a>Keywords_italy_eu_national_id_card

個人コード
  
個人コード番号
  
個人証明書の番号
  
会計年度コード
  
personalcodeno #
  
個人の id 番号
  
個人の id コード
  
codice personale
  
certificato personale
  
して personale
  
id personale
  
codice id personale
  
codice fiscale
  
## <a name="italy"></a>イタリア

### <a name="format"></a>形式

11 桁の数字とハイフンで指定された形式
  
### <a name="pattern"></a>パターン

11 桁の数字とハイフン。
  
-  6 桁の数字が日付の生年月日に対応します。 
    
- ハイフン 1 つ 
    
- 1 桁の数字 (0: 19 世紀の 20 世紀の年の「1」と 21 世紀の"2") の生年月日の 4 桁年に対応します。
    
- 4 桁の数字をランダムに生成されます。
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_latvia_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_latvia_eu_national_id_card`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_latvia_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordslatviaeunationalidcard"></a>Keywords_latvia_eu_national_id_card

個人コード
  
個人コード番号
  
個人証明書の番号
  
personalcodeno #
  
個人の id 番号
  
個人の id コード
  
ペルソナ kods
  
## <a name="lithuania"></a>リトアニア

### <a name="format"></a>形式

スペースや区切り記号なし 11 桁の数字
  
### <a name="pattern"></a>パターン

スペースや区切り記号のない 11 桁の数字。
  
- 人の性別と生年月日の世紀に対応する 1 つの数字
    
-  生年月日 (YYMMDD) に対応する 6 桁の数字 
    
- 生年月日の日付のシリアル番号に対応する 3 桁の数字
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_lithuania_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_lithuania_eu_national_id_card`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_lithuania_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordslithuaniaeunationalidcard"></a>Keywords_lithuania_eu_national_id_card

個人の数値コード
  
一意な識別番号
  
市民サービス番号
  
一意の id 番号
  
uniqueidentityno #
  
個人コードです。
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo kodas
  
asmens kodas。
  
## <a name="luxemburg"></a>ルクセンブルグ

### <a name="format"></a>形式

スペースや区切り記号なし 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字
  
- 人の性別と生年月日の世紀に対応する 1 つの数字
    
-  生年月日 (YYMMDD) に対応する 6 桁の数字 
    
- 生年月日の日付のシリアル番号に対応する 3 桁の数字
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_luxemburg_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_luxemburg_eu_national_id_card`があります。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsluxemburgeunationalidcard"></a>Keywords_luxemburg_eu_national_id_card

パーソナル id
  
個人の id 番号
  
personalidno #
  
一意の id 番号
  
personalidnumber #
  
キーの一意の id
  
個人の id コード
  
uniqueidkey #
  
個々 のコード
  
個々 の id
  
- nummer eindeutige id
  
eindeutige id
  
id personnelle
  
numéro d'identification スタッフ
  
idpersonnelle #
  
persönliche identifikationsnummer
  
eindeutigeid #
  
## <a name="malta"></a>マルタ

### <a name="format"></a>形式

1 つの文字の後に 7 桁の数字
  
### <a name="pattern"></a>パターン

7 つの数字が 1 つの文字の後に。
  
-  7 桁の数字  
    
- 大文字を 1 つ (大文字小文字を区別)
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_malta_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_malta_eu_national_id_card`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_malta_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsmaltaeunationalidcard"></a>Keywords_malta_eu_national_id_card

個人の数値コード
  
一意な識別番号
  
市民サービス番号
  
一意の id 番号
  
uniqueidentityno #
  
kodiċi numerali personali
  
numru どっち ' identifikazzjoni uniku
  
numru tas servizz taċ-ċittadin
  
numru どっち ' identità uniku
  
## <a name="netherlands"></a>オランダ

### <a name="format"></a>形式

スペースや区切り文字なしの 9 つの数字
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_netherlands_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードを検出するとします。
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_netherlands_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsnetherlandseunationalidcard"></a>Keywords_netherlands_eu_national_id_card

個人の数値コード
  
一意な識別番号
  
市民サービス番号
  
一意の id 番号
  
uniqueidentityno #
  
bsn
  
bsn #
  
persoonlijke numerieke コード
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>ポーランド

詳細についてを参照してください「ポーランド国 ID (PESEL)」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="portugal"></a>ポルトガル

詳細についてを参照してください「ポルトガルの市民のカード番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="romania"></a>ルーマニア

### <a name="format"></a>形式

スペースや区切り記号のない 13 桁の数字
  
### <a name="pattern"></a>パターン

13 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_romania_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_romania_eu_national_id_card`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_romania_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsromaniaeunationalidcard"></a>Keywords_romania_eu_national_id_card

個人の数値コード
  
一意な識別番号
  
cnp
  
cnp #
  
固定
  
暗証番号 (pin) #
  
保険番号
  
insurancenumber #
  
一意の id 番号
  
uniqueidentityno #
  
代金引換払いの個人の数値
  
代金引換払いの個人 identificare
  
代金引換払い unic identificare
  
număr 個人 unic
  
număr identitate
  
個人の număr identificare
  
număridentitate #
  
codnumericpersonal #
  
numărpersonalunic #
  
## <a name="slovakia"></a>スロバキア

### <a name="format"></a>形式

1 つのバック スラッシュが含まれている 10 桁の数字
  
### <a name="pattern"></a>パターン

10 個の数字が 1 つのバック スラッシュが含まれています。
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovakia_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_slovakia_eu_national_id_card`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovakia_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsslovakiaeunationalidcard"></a>Keywords_slovakia_eu_national_id_card

生年月日数
  
国際識別番号
  
個人識別番号
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
国番号
  
個人の id 番号
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>スロベニア

### <a name="format"></a>形式

スペースや区切り文字のない 13 桁の数字
  
### <a name="pattern"></a>パターン

指定したパターンで 13 桁の数字:
  
-  「LLL」が生まれた年の 3 桁の数字で対応最後に生年月日 (DDMMLLL) に対応する 7 桁の数字 
    
- 生年月日の区分に対応する 2 つの数字
    
- (000-499 男性の場合) と女性の場合に、500-999 は、同じ日に生まれた人の性別とシリアル番号の組み合わせに対応する 3 桁の数字
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovenia_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_slovenia_eu_national_id_card`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_slovenia_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordssloveniaeunationalidcard"></a>Keywords_slovenia_eu_national_id_card

個人の数値コード
  
一意な識別番号
  
一意の登録番号
  
一意の id 番号
  
uniqueidentityno #
  
一意のマスターの市民数
  
edinstvena identifikacijska številka
  
uniqueidentityno #
  
edinstvena številka glavnega državljana
  
emšo
  
## <a name="spain"></a>スペイン

### <a name="format"></a>形式

1 つの文字の後に 7 桁の数字
  
### <a name="pattern"></a>パターン

1 つの文字の後に 7 桁の数字
  
- 7 桁の数字 
    
- 1 つの数字または文字 (文字列)
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_spain_eu_national_id_card`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_spain_eu_national_id_card"`があります。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsspaineunationalidcard"></a>Keywords_spain_eu_national_id_card

dni
  
国際識別番号
  
国内の id 番号
  
保険番号
  
個人識別番号
  
国家のアイデンティティ
  
個人識別情報なし
  
一意の id 番号
  
nationalidno #
  
uniqueid #
  
dni #
  
nationalid #
  
nie #
  
nie
  
nienúmero #
  
nie número
  
documento nacional de identidad
  
identidad único
  
número nacional identidad
  
dni número
  
dninúmero #
  
identidadúnico #
  
## <a name="sweden"></a>スウェーデン

詳細についてを参照してください「スウェーデン国民 ID」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="see-also"></a>関連項目

[機密情報の種類の検索基準:](what-the-sensitive-information-types-look-for.md)

