---
title: EU 社会保障番号または同等の ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号または同等の ID の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: c0c808eafa52209c79f3b4e8a2113f587fd8a771
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410802"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>EU 社会保障番号または同等の ID

このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号 (SSN) または同等の ID 機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
  
## <a name="austria"></a>オーストリア

### <a name="format"></a>Format

指定した形式の10桁の数字
  
### <a name="pattern"></a>パターン

10 桁の数字:
  
-  シリアル番号に対応する3桁の数字 
    
- 1つのチェックディジット
    
- 誕生日に対応する6桁の数字 (ddmmyy)
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_austria_eu_ssn_or_equivalent`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsaustriaeussnorequivalent"></a>Keywords_austria_eu_ssn_or_equivalent

ソーシャルセキュリティなし
  
social security number
  
social security code
  
保険番号
  
オーストリア ssn
  
ssn
  
ssn
  
保険コード
  
保険コード #
  
"社会 securityno"
  
sozialversicherungsnummer
  
soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>ベルギー

### <a name="format"></a>Format

11桁の数字 (スペースまたは区切り文字なし)
  
### <a name="pattern"></a>パターン

11 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_belgium_eu_ssn_or_equivalent`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsbelgiumeussnorequivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

ベルギーの国番号
  
国番号
  
social security number
  
nationalnumber #
  
ssn
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
個人 id 番号
  
personalidnumber #
  
numéro national
  
numéro de sécurité
  
numéro d'assuré
  
identifiant national
  
identifiantnational #
  
numéronational #
  
## <a name="croatia"></a>クロアチア

### <a name="format"></a>Format

スペースと区切り文字を含まない11桁の数字
  
### <a name="pattern"></a>パターン

 11 桁の数字: 
  
-  10桁の数字 
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_croatia_eu_ssn_or_equivalent`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordscroatiaeussnorequivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

個人識別番号
  
マスター市民番号
  
national identification number
  
social security number
  
nationalnumber #
  
ssn
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
個人 id 番号
  
personalidnumber #
  
oib
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>チェコ共和国

### <a name="format"></a>Format

指定したパターンの10桁の数字と円記号
  
### <a name="pattern"></a>パターン

10桁の数字と円記号:
  
- 誕生日に対応する6桁の数字 (yymmdd という): 
    
- 円記号
    
- 同じ日付で個人の出生を区切るシリアル番号に対応する3桁の数字
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_czech_republic_eu_ssn_or_equivalent`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsczechrepubliceussnorequivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

出生地番号
  
national identification number
  
個人識別番号
  
social security number
  
nationalnumber #
  
ssn
  
ssn
  
国番号
  
個人 id 番号
  
personalidnumber #
  
rč
  
rodnéčíslo
  
rodne cislo
  
## <a name="denmark"></a>デンマーク

### <a name="format"></a>Format

指定したパターンの10桁の数字とハイフン
  
### <a name="pattern"></a>パターン

10桁の数字とハイフン:
  
- 誕生日に対応する6桁の数字 (ddmmyy) 
    
- ハイフン 1 つ 
    
- シーケンス番号に対応する4桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_denmark_eu_ssn_or_equivalent`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsdenmarkeussnorequivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

個人識別番号
  
national identification number
  
social security number
  
nationalnumber #
  
ssn
  
ssn
  
国番号
  
個人 id 番号
  
personalidnumber #
  
cpr-nummer
  
personnummer
  
## <a name="finland"></a>フィンランド

### <a name="format"></a>Format

指定した書式の11文字の組み合わせ
  
### <a name="pattern"></a>パターン

指定した形式の11文字の組み合わせ。
  
-  6 桁の数字 
    
- 次のいずれかのインスタンス。
    
  - プラス記号
    
  - マイナス記号
    
  - 文字 "A" (大文字と小文字を区別しない)
    
- 3 桁の数字
    
- 1文字または1桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_finland_eu_ssn_or_equivalent`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsfinlandeussnorequivalent"></a>Keywords_finland_eu_ssn_or_equivalent

identification number
  
個人 id
  
id 番号
  
フィンランドの国民 id 番号
  
personalidnumber #
  
national identification number
  
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
  
hetu
  
## <a name="france"></a>フランス

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの社会保障番号 (insee)」セクションを参照してください。
  
## <a name="germany"></a>ドイツ

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツの id カード番号」セクションを参照してください。
  
## <a name="greece"></a>ギリシャ

詳細については、「ギリシャの国民 ID カード」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。
  
## <a name="hungary"></a>ハンガリー

### <a name="format"></a>Format

スペースと区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_hungary_eu_ssn_or_equivalent`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordshungaryeussnorequivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

ハンガリーのソーシャルセキュリティ番号
  
social security number
  
指定した仮のセキュリティ番号
  
hssn #
  
"対話型"
  
hssn
  
taj
  
taj #
  
ssn
  
ssn
  
ソーシャルセキュリティなし
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
magyar áfa szám
  
## <a name="portugal"></a>ポルトガル

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポルトガル市民カード番号」セクションを参照してください。
  
## <a name="spain"></a>スペイン

詳細については、「スペインの社会保障番号 (SSN)」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。
  
## <a name="sweden"></a>スウェーデン

### <a name="format"></a>Format

12桁の数字 (スペースと区切り記号なし)
  
### <a name="pattern"></a>パターン

12 桁の数字:
  
-  誕生日に対応する8桁の数字 (YYYYMMDD) 
    
- 次の場合、シリアル番号に対応する3桁の数字です。 
    
  - シリアル番号の最後の桁は、男性の場合は奇数、女性の場合は偶数の数字を指定します。
    
  - 1990までの間、シリアル番号 corresponded は、番号のベアラーが生まれたか (1947 以前に作成された場合)、特別なコード (通常は7番目の数字) を使用して、税務レコードに従って、そのユーザーが生活していた市区郡に割り当てられています。immigrants 
    
- 1つのチェックディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
- from `Keywords_sweden_eu_ssn_or_equivalent`キーワードが見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。 
    
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

### <a name="keywords"></a>キーワード

#### <a name="keywordsswedeneussnorequivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

個人 id 番号
  
identification number
  
個人 id 番号
  
id 番号
  
識別番号
  
個人識別番号
  
personnummer id
  
personligt id-nummer
  
unikt id-nummer
  
personnummer
  
identifikationsnumret
  
personnummer #
  
identifikationsnumret #
  
## <a name="see-also"></a>関連項目

[機密情報の種類の検索基準:](what-the-sensitive-information-types-look-for.md)

