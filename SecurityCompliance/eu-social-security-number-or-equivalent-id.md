---
title: EU の社会保障番号またはそれと同等の ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: このトピックでは、どのようなデータ損失防止 (DLP) ポリシーを検索、機密性の高い情報の種類として [EU の社会保障番号または同等の ID を検出したときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
ms.openlocfilehash: 6f1027dcfb648ed937b8180d74d4bc6348dab650
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532030"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>EU の社会保障番号またはそれと同等の ID

このトピックでは、どのようなデータ損失防止 (DLP) ポリシーを検索、機密性の高い情報の種類として [EU の社会保障番号 (SSN) または同等の ID を検出したときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
  
## <a name="austria"></a>オーストリア

### <a name="format"></a>形式

指定した形式で 10 桁の数字
  
### <a name="pattern"></a>パターン

10 桁の数字:
  
-  シリアル番号に対応する 3 桁の数字 
    
- 1 つのチェック ディジット
    
- 6 桁の数字が日付の生年月日に対応します。
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_austria_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_austria_eu_ssn_or_equivalent`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_austria_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsaustriaeussnorequivalent"></a>Keywords_austria_eu_ssn_or_equivalent

社会保険なし
  
social security number

  

social security code
  
保険番号
  
オーストリア ssn
  
ssn #
  
ssn
  
保険コード
  
保険コード番号
  
socialsecurityno #
  
sozialversicherungsnummer
  
soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>ベルギー

### <a name="format"></a>形式

スペースや区切り文字なし 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_belgium_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_belgium_eu_ssn_or_equivalent`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_belgium_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsbelgiumeussnorequivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

ベルギーの国番号
  
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
  
numéro 国立
  
numéro de sécurité

  
numéro d'assuré
  
国内 identifiant
  
identifiantnational #
  
numéronational #
  
## <a name="croatia"></a>クロアチア

### <a name="format"></a>形式

スペースや区切り記号なし 11 桁の数字
  
### <a name="pattern"></a>パターン

 11 桁の数字: 
  
-  10 桁の数字 
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_croatia_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_croatia_eu_ssn_or_equivalent`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_croatia_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordscroatiaeussnorequivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

個人識別番号
  
マスターの市民数
  
国際識別番号
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
個人の id 番号
  
personalidnumber #
  
oib
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>チェコ共和国

### <a name="format"></a>形式

10 桁と指定したパターン内のバック スラッシュ
  
### <a name="pattern"></a>パターン

10 桁の数字と、円記号 ()。
  
- 生年月日 (YYMMDD) に対応する 6 つの数字。 
    
- 円記号
    
- 同じ日に生まれた人を分離するためのシリアル番号に対応する 3 桁の数字
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_czech_republic_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_czech_republic_eu_ssn_or_equivalent`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_czech_republic_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsczechrepubliceussnorequivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

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
  
## <a name="denmark"></a>デンマーク

### <a name="format"></a>形式

10 桁の数字とハイフンで指定されたパターン
  
### <a name="pattern"></a>パターン

10 桁の数字とハイフン。
  
- 6 桁の数字が日付の生年月日に対応します。 
    
- ハイフン 1 つ 
    
- シーケンス番号に対応する 4 桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_denmark_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_denmark_eu_ssn_or_equivalent`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_denmark_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsdenmarkeussnorequivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

個人識別番号
  
国際識別番号
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
国番号
  
個人の id 番号
  
personalidnumber #
  
cpr nummer
  
personnummer
  
## <a name="finland"></a>フィンランド

### <a name="format"></a>形式

指定した形式で、11 文字の組み合わせ
  
### <a name="pattern"></a>パターン

指定した形式での 11 文字の組み合わせ。
  
-  6 桁の数字 
    
- 次のいずれかのインスタンスを 1 つ。
    
  - プラス記号
    
  - マイナス記号
    
  - 文字"A"(いない大文字小文字を区別)
    
- 3 桁の数字
    
- 1 つの文字または 1 桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_finland_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_finland_eu_ssn_or_equivalent`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_finland_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsfinlandeussnorequivalent"></a>Keywords_finland_eu_ssn_or_equivalent

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
  
hetu
  
## <a name="france"></a>フランス

詳細についてを参照してください「フランスの社会保障番号 (INSEE)」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>ドイツ

詳細についてを参照してください"ドイツの Id カードの番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>ギリシャ

詳細についてを参照してください「ギリシャ国内の ID カード」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="hungary"></a>ハンガリー

### <a name="format"></a>形式

スペースや区切り記号なしの 9 桁
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_hungary_eu_ssn_or_equivalent`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordshungaryeussnorequivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

ハンガリー語の社会保障番号
  
social security number

  
socialsecuritynumber #
  
hssn #
  
socialsecuritynno
  
hssn
  
taj
  
taj #
  
ssn
  
ssn #
  
社会保険なし
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
magyar áfa szám
  
## <a name="portugal"></a>ポルトガル

詳細についてを参照してください「ポルトガルの市民のカード番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="spain"></a>スペイン

詳細についてを参照してください「スペインの社会保障番号 (SSN)」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="sweden"></a>スウェーデン

### <a name="format"></a>形式

スペースや区切り記号のない 12 桁の数字
  
### <a name="pattern"></a>パターン

12 桁の数字:
  
-  8 桁の日付 (YYYYMMDD) の生年月日に対応します。 
    
- シリアル番号に対応する 3 つの桁位置。 
    
  - シリアル番号の最後の数字は、男性の数が奇数と偶数の女性の場合の割り当てによって性別を示します
    
  - 1990 年までのシリアル番号の割り当てに当てはめて考える郡番号のベアラーが誕生した (1947年の前に生まれた) 場合や、本人が生活、税の記録による 1947 年 1 月 1日、上の特別なコード (通常 7 桁の数字としての 9) のimmigrants 
    
- 1 つのチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_sweden_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_sweden_eu_ssn_or_equivalent`があります。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_sweden_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsswedeneussnorequivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

個人の id 番号
  
identification number

  
パーソナル id なし
  
識別情報なし
  
識別なし
  
個人識別なし
  
personnummer id
  
- nummer personligt id
  
- nummer unikt id
  
personnummer
  
identifikationsnumret
  
personnummer #
  
identifikationsnumret #
  
## <a name="see-also"></a>関連項目

[機密情報の種類の検索基準:](what-the-sensitive-information-types-look-for.md)

