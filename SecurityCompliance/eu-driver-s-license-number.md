---
title: EU 運転免許証番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 運転免許証番号機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
ms.openlocfilehash: 065684249f9766d567c63e6b8170d36f56692e45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532112"
---
# <a name="eu-drivers-license-number"></a>EU 運転免許証番号

このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 運転免許証番号機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
  
## <a name="austria"></a>オーストリア

### <a name="format"></a>形式

8 桁の空白と区切り記号なし
  
### <a name="pattern"></a>パターン

8 桁の数字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_austria_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_austria_eu_driver's_license_number`があります。 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>Keywords

| |
|**Keywords_austria_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> ドライバーのライセンス  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/>  ライセンス番号を推進  <br/> dlno #  <br/> fuhrerschein  <br/> fuhrerschein republik osterreich  <br/> |
   
## <a name="belgium"></a>ベルギー

### <a name="format"></a>形式

スペースや区切り記号なしの 10 桁
  
### <a name="pattern"></a>パターン

10 桁の数字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_belgium_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_belgium_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Keywords

| |
|**Keywords__belgium_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> dlno #  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> führerschein nr  <br/> fuehrerschein Nr  <br/> fuehrerschein nr  <br/> |
   
## <a name="bulgaria"></a>ブルガリア

### <a name="format"></a>形式

スペースや区切り記号なしの 9 桁
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_bulgaria_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_bulgaria_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>Keywords

| |
|**Keywords_bulgaria_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> ЗА УПРАВЛЕНИЕ НА МПС の СВИДЕТЕЛСТВО  <br/> СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО  <br/> СУМПС  <br/> ШОФЬОРСКА КНИЖКА  <br/> |
   
## <a name="croatia"></a>クロアチア

### <a name="format"></a>形式

8 桁の空白と区切り記号なし
  
### <a name="pattern"></a>パターン

8 桁の数字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_croatia_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_croatia_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Keywords

| |
|**Keywords_croatia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> vozačka dozvola  <br/> |
   
## <a name="cyprus"></a>キプロス

### <a name="format"></a>形式

スペースや区切り記号のない 12 桁の数字
  
### <a name="pattern"></a>パターン

12 桁の数字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_cyprus_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_cyprus_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_cyprus_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ  <br/> |
   
## <a name="czech-republic"></a>チェコ共和国

### <a name="format"></a>形式

6 桁の後に 2 つの文字
  
### <a name="pattern"></a>パターン

8 つの文字と数字の場合。
  
- 2 つの文字 (文字列)
    
- スペース 1 つ (省略可能) 
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_czech_republic_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_czech_republic_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Keywords

| |
|**Keywords_czech_republic_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> Řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>デンマーク

### <a name="format"></a>形式

8 桁の空白と区切り記号なし
  
### <a name="pattern"></a>パターン

8 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_denmark_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_denmark_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Keywords

| |
|**Keywords_denmark_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> kørekort  <br/> kørekortnummer  <br/> |
   
## <a name="estonia"></a>エストニア

### <a name="format"></a>形式

6 桁の後に 2 つの文字
  
### <a name="pattern"></a>パターン

2 つの文字と 6 桁の数字。
  
-  文字"ET"(いない大文字小文字を区別) 
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_estonia_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_estonia_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_estonia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ライセンス番号を推進  <br/> dlno #  <br/> 
permis de conduire  <br/> |
   
## <a name="finland"></a>フィンランド

### <a name="format"></a>形式

ハイフンを 1 つ含む 10 桁の数字
  
### <a name="pattern"></a>パターン

ハイフンが含まれている 10 桁の数字。
  
-  6 桁の数字 
    
- ハイフン
    
-  4 桁の数字 
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_finland_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_finland_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_finland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> ajokortti  <br/> |
   
## <a name="france"></a>フランス

詳細についてを参照してください「フランスのドライバーのライセンス番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>ドイツ

詳細についてを参照してください「ドイツ語の運転免許証番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>ギリシャ

### <a name="format"></a>形式

スペースや区切り記号なしの 9 桁
  
### <a name="pattern"></a>パターン

 9 桁の数字 
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_greece_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_greece_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_greece_eu_driver's_license_number**|
|:-----|
|dlL の場合  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> ΔΕΙΑ ΟΔΉΓΗΣΗΣ  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>ハンガリー

### <a name="format"></a>形式

6 桁の後に 2 つの文字
  
### <a name="pattern"></a>パターン

2 つの文字と 6 桁の数字。
  
-  2 つの文字 (文字列) 
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_hungary_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_hungary_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_hungary_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>Ireland

### <a name="format"></a>形式

4 文字の後に 6 桁の数字
  
### <a name="pattern"></a>パターン

6 桁および 4 つの文字。
  
- 6 桁の数字
    
- 4 つの文字 (文字列)
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_ireland_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_ireland_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_ireland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>イタリア

詳細についてを参照してください「イタリア ドライバー ライセンスの数」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="latvia"></a>ラトビア

### <a name="format"></a>形式

6 桁の後に次の 3 つの文字
  
### <a name="pattern"></a>パターン

3 文字と 6 桁の数字。
  
-  3 つの文字 (文字列) 
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_latvia_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_latvia_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_latvia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>リトアニア

### <a name="format"></a>形式

8 桁の空白と区切り記号なし
  
### <a name="pattern"></a>パターン

 8 桁の数字 
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_lithuania_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_lithuania_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_lithuania_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> vairuotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>ルクセンブルグ

### <a name="format"></a>形式

スペースや区切り文字なしの 6 桁
  
### <a name="pattern"></a>パターン

 6 桁の数字 
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_luxemburg_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_luxemburg_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_luxemburg_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> fahrerlaubnis  <br/> |
   
## <a name="malta"></a>マルタ

### <a name="format"></a>形式

2 つの文字と指定したパターンには 6 桁の組み合わせ
  
### <a name="pattern"></a>パターン

2 つの文字と 6 桁の数字の組み合わせです。
  
- 2 つの文字 (数字または文字、大文字小文字を区別しない)
    
- スペース 1 つ (省略可能) 
    
- 3 桁の数字
    
- スペース 1 つ (省略可能) 
    
- 3 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_malta_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_malta_eu_driver's_license_number`があります。 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_malta_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> liċenzja タス-sewqan  <br/> |
   
## <a name="netherlands"></a>オランダ

### <a name="format"></a>形式

スペースや区切り記号なしの 10 桁
  
### <a name="pattern"></a>パターン

10 桁の数字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_netherlands_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_netherlands_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_netherlands_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> 
permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>ポーランド

### <a name="format"></a>形式

2 つのスラッシュが含まれている 14 桁の数字
  
### <a name="pattern"></a>パターン

14 桁の数字と 2 つのスラッシュ。
  
-  5 桁の数字 
    
- スラッシュ 1 つ 
    
- 2 桁の数字
    
- スラッシュ 1 つ 
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_poland_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_poland_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_poland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> prawo jazdy  <br/> |
   
## <a name="portugal"></a>ポルトガル

### <a name="format"></a>形式

2 つの文字が指定されたパターンで 7 つの数字が続く
  
### <a name="pattern"></a>パターン

2 つの文字が特殊文字を含む 7 つの数字が続きます。
  
-  2 つの文字 (文字列) 
    
- ハイフン 1 つ 
    
- 6 桁の数字
    
- スペース
    
- 1 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_portugal_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_portugal_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_portugal_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> carteira de motorista  <br/> |
   
## <a name="romania"></a>ルーマニア

### <a name="format"></a>形式

8 桁の数字の後に 1 つの文字
  
### <a name="pattern"></a>パターン

8 桁の数字の後に 1 つの文字。
  
-  1 つの文字列の文字または数字 
    
- 8 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_romania_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_romania_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_romania_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> permis デ conducere  <br/> |
   
## <a name="slovakia"></a>スロバキア

### <a name="format"></a>形式

7 桁の後に 1 つの文字
  
### <a name="pattern"></a>パターン

7 桁の後に 1 つの文字
  
- 1 つの文字列の文字または数字
    
-  7 桁の数字 
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_slovakia_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_slovakia_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_slovakia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>スロベニア

### <a name="format"></a>形式

スペースや区切り記号なしの 9 桁
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_slovenia_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_slovenia_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_slovenia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>スペイン

### <a name="format"></a>形式

8 桁の後に 1 つの文字
  
### <a name="pattern"></a>パターン

8 の数字が 1 つの文字が続きます。
  
-  8 桁の数字 
    
- 1 つの数字または文字 (文字列)
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_spain_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_spain_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_spain_eu_driver's_license_number**|
|:-----|
|dlno #  <br/> dl#  <br/> lic のドライバーです。  <br/> ドライバー ライセンス  <br/> driver license  <br/> drivers licence  <br/> drivers license  <br/> ドライバーのライセンス  <br/> driver's license  <br/> driving licence
  <br/> ライセンスを推進  <br/> ドライバーのライセンスの数  <br/> ドライバーのライセンスの数  <br/> ドライバーのライセンス数  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> 運転免許証番号  <br/> 駆動のライセンス数  <br/> ライセンス番号を推進  <br/> 許可を推進  <br/> 駆動の許可番号  <br/> permiso de conducción  <br/> permiso conducción  <br/> número licencia conducir  <br/> número de carnet de の conducir  <br/> número carnet conducir  <br/> licencia conducir  <br/> número de permiso de の conducir  <br/> número de permiso conducir  <br/> número permiso conducir  <br/> permiso conducir  <br/> licencia de manejo  <br/> el carnet de conducir  <br/> carnet conducir  <br/> |
   
## <a name="sweden"></a>スウェーデン

### <a name="format"></a>形式

10 桁の数字、ハイフンを含む
  
### <a name="pattern"></a>パターン

10 個の数字がハイフンが含まれています。
  
-  6 桁の数字 
    
- ハイフン
    
- 4 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_sweden_eu_driver's_license_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_sweden_eu_driver's_license_number`があります。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_sweden_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> ドライバーのライセンスの数  <br/> ドライバー ライセンス  <br/> lic のドライバーです。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンスの数  <br/> ライセンス番号を推進  <br/> dlno #  <br/> körkort  <br/> |
   
## <a name="uk"></a>英国

詳細についてを参照してください「英国のドライバーのライセンスの数」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="see-also"></a>関連項目

[機密情報の種類の検索基準:](what-the-sensitive-information-types-look-for.md)

