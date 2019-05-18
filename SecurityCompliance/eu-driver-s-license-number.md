---
title: EU 運転免許証番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152979"
---
# <a name="eu-drivers-license-number"></a>EU 運転免許証番号

このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
  
## <a name="austria"></a>オーストリア

### <a name="format"></a>Format

スペースと区切り文字を含まない8桁の数字
  
### <a name="pattern"></a>パターン

8 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_austria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_austria_eu_driver's_license_number`キーワードが見つかりました。 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>キーワード

| |
|**Keywords_austria_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/>  運転免許証番号  <br/> dlno #  <br/> futex  <br/> futex (futex) republik osterreich  <br/> |
   
## <a name="belgium"></a>ベルギー

### <a name="format"></a>Format

スペースと区切り文字を含まない10桁の数字
  
### <a name="pattern"></a>パターン

10 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_belgium_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_belgium_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>キーワード

| |
|**Keywords__belgium_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> dlno #  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> führerschein-nr  <br/> futex の eh/Nr  <br/> futex の eh/nr  <br/> |
   
## <a name="bulgaria"></a>ブルガリア

### <a name="format"></a>Format

スペースと区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_bulgaria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_bulgaria_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>キーワード

| |
|**Keywords_bulgaria_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> свидетелство за управление на мпс  <br/> свидетелство за управление на моторно превозно средство  <br/> сумпс  <br/> шофьорска книжка  <br/> |
   
## <a name="croatia"></a>クロアチア

### <a name="format"></a>Format

スペースと区切り文字を含まない8桁の数字
  
### <a name="pattern"></a>パターン

8 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_croatia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_croatia_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>キーワード

| |
|**Keywords_croatia_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> vozačka dozvola  <br/> |
   
## <a name="cyprus"></a>キプロス

### <a name="format"></a>Format

12桁の数字 (スペースと区切り記号なし)
  
### <a name="pattern"></a>パターン

12 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_cyprus_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_cyprus_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_cyprus_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> άδεια οδήγησης  <br/> |
   
## <a name="czech-republic"></a>チェコ共和国

### <a name="format"></a>Format

2つの文字の後に6桁の数字
  
### <a name="pattern"></a>パターン

8つの文字と数字:
  
- 2桁の文字 (大文字小文字を区別しない)
    
- スペース 1 つ (省略可能) 
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_czech_republic_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_czech_republic_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>キーワード

| |
|**Keywords_czech_republic_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>デンマーク

### <a name="format"></a>Format

スペースと区切り文字を含まない8桁の数字
  
### <a name="pattern"></a>パターン

8 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_denmark_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_denmark_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>キーワード

| |
|**Keywords_denmark_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> kørekort  <br/> kørekortnummer  <br/> |
   
## <a name="estonia"></a>エストニア

### <a name="format"></a>Format

2つの文字の後に6桁の数字
  
### <a name="pattern"></a>パターン

2つの文字と6桁の数字:
  
-  文字 "ET" (大文字と小文字を区別しない) 
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_estonia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_estonia_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_estonia_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> 運転免許証番号  <br/> dlno #  <br/> permis de conduire  <br/> |
   
## <a name="finland"></a>フィンランド

### <a name="format"></a>Format

ハイフンを 1 つ含む 10 桁の数字
  
### <a name="pattern"></a>パターン

ハイフンを含む10桁の数字:
  
-  6 桁の数字 
    
- ハイフン 1 つ
    
-  4 桁の数字 
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_finland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_finland_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_finland_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> ajokortti  <br/> |
   
## <a name="france"></a>フランス

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの運転免許証番号」セクションを参照してください。
  
## <a name="germany"></a>ドイツ

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」に記載されている「ドイツの運転免許証番号」セクションを参照してください。
  
## <a name="greece"></a>ギリシャ

### <a name="format"></a>Format

スペースと区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

 9 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_greece_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_greece_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_greece_eu_driver's_license_number**|
|:-----|
|ライブラリ  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> δεια οδήγησης  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>ハンガリー

### <a name="format"></a>Format

2つの文字の後に6桁の数字
  
### <a name="pattern"></a>パターン

2つの文字と6桁の数字:
  
-  2桁の文字 (大文字小文字を区別しない) 
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_hungary_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_hungary_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_hungary_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>アイルランド

### <a name="format"></a>Format

6桁の数字の後に4文字
  
### <a name="pattern"></a>パターン

6桁の数字と4文字:
  
- 6 桁の数字
    
- 4桁の文字 (大文字小文字を区別しない)
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_ireland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_ireland_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_ireland_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>イタリア

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「イタリアの運転免許証番号」セクションを参照してください。
  
## <a name="latvia"></a>ラトビア

### <a name="format"></a>Format

3つの文字の後に6桁の数字
  
### <a name="pattern"></a>パターン

3つの文字と6桁の数字:
  
-  3桁の文字 (大文字小文字を区別しない) 
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_latvia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_latvia_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_latvia_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>リトアニア

### <a name="format"></a>Format

スペースと区切り文字を含まない8桁の数字
  
### <a name="pattern"></a>パターン

 8 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_lithuania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_lithuania_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_lithuania_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> vエア uotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>ルクセンブルク

### <a name="format"></a>Format

スペースと区切り文字を含まない6桁の数字
  
### <a name="pattern"></a>パターン

 6 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_luxemburg_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_luxemburg_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_luxemburg_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> fahて fabnis  <br/> |
   
## <a name="malta"></a>マルタ

### <a name="format"></a>Format

指定したパターンの2つの文字と6桁の数字の組み合わせ
  
### <a name="pattern"></a>パターン

2つの文字と6桁の数字の組み合わせ:
  
- 2つの文字 (大文字小文字を区別しない数字または文字)
    
- スペース 1 つ (省略可能) 
    
- 3 桁の数字
    
- スペース 1 つ (省略可能) 
    
- 3 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_malta_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_malta_eu_driver's_license_number`キーワードが見つかりました。 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_malta_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> liċenzja tas-sewqan  <br/> |
   
## <a name="netherlands"></a>オランダ

### <a name="format"></a>Format

スペースと区切り文字を含まない10桁の数字
  
### <a name="pattern"></a>パターン

10 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_netherlands_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_netherlands_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_netherlands_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>ポーランド

### <a name="format"></a>Format

2つのスラッシュを含む14桁の数字
  
### <a name="pattern"></a>パターン

14桁の数字と2つのスラッシュ:
  
-  5 桁の数字 
    
- スラッシュ 1 つ 
    
- 2 桁の数字
    
- スラッシュ 1 つ 
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_poland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_poland_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_poland_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> prawo jazdy  <br/> |
   
## <a name="portugal"></a>ポルトガル

### <a name="format"></a>Format

指定したパターンの2文字の後に7桁の数字
  
### <a name="pattern"></a>パターン

2つの文字の後に特殊文字を含む7個の数字。
  
-  2桁の文字 (大文字小文字を区別しない) 
    
- ハイフン 1 つ 
    
- 6 桁の数字
    
- スペース
    
- 1 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_portugal_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_portugal_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_portugal_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> carteira de motorista  <br/> |
   
## <a name="romania"></a>ルーマニア

### <a name="format"></a>Format

1文字の後に8桁の数字
  
### <a name="pattern"></a>パターン

1文字の後に8桁の数字。
  
-  1文字 (大文字小文字を区別しない) または数字 
    
- 8 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_romania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_romania_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_romania_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> permis de conducere  <br/> |
   
## <a name="slovakia"></a>スロバキア

### <a name="format"></a>Format

1文字の後に7桁の数字
  
### <a name="pattern"></a>パターン

1文字の後に7桁の数字
  
- 1文字 (大文字小文字を区別しない) または数字
    
-  7 桁の数字 
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_slovakia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_slovakia_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_slovakia_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>スロベニア

### <a name="format"></a>Format

スペースと区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_slovenia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_slovenia_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_slovenia_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>スペイン

### <a name="format"></a>Format

8桁の数字の後に1つの文字
  
### <a name="pattern"></a>パターン

8桁の数字の後に1文字。
  
-  8 桁の数字 
    
- 1桁の数字または文字 (大文字小文字を区別しない)
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 関数`Func_spain_eu_driver's_license_number`は、パターンに一致するコンテンツを検索します。 
    
- From `Keywords_spain_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_spain_eu_driver's_license_number**|
|:-----|
|dlno #  <br/> dl  <br/> ドライバー lic  <br/> ドライバーのライセンス  <br/> driver license  <br/> drivers licence  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> driving licence  <br/> driving license  <br/> ドライバーライセンス番号  <br/> 運転免許証番号  <br/> ドライバーライセンス番号  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> ライセンス番号の運転  <br/> 運転免許証番号  <br/> 許可の推進  <br/> 許可番号の運転  <br/> permiso de conducción  <br/> permiso conducción  <br/> número/encia conducir  <br/> número デカーネット de conducir  <br/> número carnet conducir  <br/> /暗号化 ia conducir  <br/> número de permiso de conducir  <br/> número de permiso conducir  <br/> número permiso conducir  <br/> permiso conducir  <br/> -encia de manejo  <br/> el carnet de conducir  <br/> carnet conducir  <br/> |
   
## <a name="sweden"></a>スウェーデン

### <a name="format"></a>Format

10桁の数字 (ハイフンを含む)
  
### <a name="pattern"></a>パターン

ハイフンを含む10桁の数字:
  
-  6 桁の数字 
    
- ハイフン 1 つ
    
- 4 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_sweden_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。 
    
- From `Keywords_sweden_eu_driver's_license_number`キーワードが見つかりました。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_sweden_eu_driver's_license_number**|
|:-----|
|dl  <br/> driver license  <br/> 運転免許証番号  <br/> ドライバーのライセンス  <br/> ドライバー lic  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 運転免許証番号  <br/> ドライバーのライセンス番号  <br/> 運転免許証番号  <br/> dlno #  <br/> körkort  <br/> |
   
## <a name="uk"></a>佐賀

詳細については、「英国 [[機密情報の種類](what-the-sensitive-information-types-look-for.md)] に表示される運転免許証番号。
  
## <a name="see-also"></a>関連項目

[機密情報の種類の検索基準:](what-the-sensitive-information-types-look-for.md)

