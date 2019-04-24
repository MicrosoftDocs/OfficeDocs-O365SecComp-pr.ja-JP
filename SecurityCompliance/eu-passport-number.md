---
title: EU パスポート番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 3ab92e87607f41cffa8c15f1179a4eef5369cb29
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256825"
---
# <a name="eu-passport-number"></a>EU パスポート番号

このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
  
## <a name="austria"></a>オーストリア

### <a name="format"></a>Format

1文字の後にオプションのスペースと7桁の数字
  
### <a name="pattern"></a>パターン

1つの文字、7桁の数字、および1つのスペースの組み合わせ。
  
- 1 文字 (大文字小文字を区別しない)
    
- スペース1つ (オプション)
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_austria_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_austria_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_austria_eu_passport_number**|
|:-----|
|passport number  <br/> オーストリアのパスポート番号  <br/> passport いいえ  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>ベルギー

### <a name="format"></a>Format

2つの文字の後に6桁の数字 (スペースまたは区切り記号を付けない)
  
### <a name="pattern"></a>パターン

2つの文字の後に6桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_belgium_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_belgium_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_belgium_eu_passport_number**|
|:-----|
|passport number  <br/> ベルギーのパスポート番号  <br/> passport いいえ  <br/> 大き poort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>ブルガリア

### <a name="format"></a>Format

スペースと区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

 9 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_bulgaria_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_bulgaria_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_bulgaria_eu_passport_number**|
|:-----|
|passport number  <br/> ブルガリアのパスポート番号  <br/> passport いいえ  <br/> номернапаспорта  <br/> |
   
## <a name="croatia"></a>クロアチア

### <a name="format"></a>Format

スペースと区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

 9 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_croatia_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_croatia_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_croatia_eu_passport_number**|
|:-----|
|passport number  <br/> クロアチア語のパスポート番号  <br/> passport いいえ  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>キプロス

### <a name="format"></a>Format

1文字の後に、スペースまたは区切り記号を含まない6-8 桁の数字
  
### <a name="pattern"></a>パターン

1文字の後に6桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_cyprus_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_cyprus_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_cyprus_eu_passport_number**|
|:-----|
|passport number  <br/> キプロスパスポート番号  <br/> passport いいえ  <br/> αριθμόδιαβατηρίου  <br/> |
   
## <a name="czech-republic"></a>チェコ共和国

### <a name="format"></a>Format

スペースまたは区切り文字を含まない8桁の数字
  
### <a name="pattern"></a>パターン

スペースまたは区切り文字を含まない8桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_czech_republic_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_czech_republic_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_czech_republic_eu_passport_number**|
|:-----|
|passport number  <br/> チェコのパスポート番号  <br/> passport いいえ  <br/> cestovní pas  <br/> pas  <br/> |
   
## <a name="denmark"></a>デンマーク

### <a name="format"></a>Format

スペースと区切り文字を含まない9桁の数字
  
### <a name="pattern"></a>パターン

 9 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_denmark_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_denmark_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_denmark_eu_passport_number**|
|:-----|
|passport number  <br/> デンマークのパスポート番号  <br/> passport いいえ  <br/> pas  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>エストニア

### <a name="format"></a>Format

1文字の後に7桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

1文字の後に7桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_estonia_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_estonia_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_estonia_eu_passport_number**|
|:-----|
|passport number  <br/> エストニア語のパスポート番号  <br/> passport いいえ  <br/> eesti kodaniku pass  <br/> |
   
## <a name="finland"></a>フィンランド

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フィンランドのパスポート番号」セクションを参照してください。
  
## <a name="france"></a>フランス

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスのパスポート番号」セクションを参照してください。
  
## <a name="germany"></a>ドイツ

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツのパスポート番号」セクションを参照してください。
  
## <a name="greece"></a>ギリシャ

### <a name="format"></a>Format

2つの文字の後に、スペースや区切り文字を含まない7桁の数字
  
### <a name="pattern"></a>パターン

2 桁の文字の後に 7 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_greece_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_greece_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_greece_eu_passport_number**|
|:-----|
|passport number  <br/> ギリシャのパスポート番号  <br/> passport いいえ  <br/> διαβατηριο  <br/> |
   
## <a name="hungary"></a>ハンガリー

### <a name="format"></a>Format

2つの文字の後に、スペースや区切り文字を含まない6桁または7桁の数字
  
### <a name="pattern"></a>パターン

2つの文字の後に6桁または7桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_hungary_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_hungary_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_hungary_eu_passport_number**|
|:-----|
|passport number  <br/> ハンガリーのパスポート番号  <br/> passport いいえ  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>アイルランド

### <a name="format"></a>Format

2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字
  
### <a name="pattern"></a>パターン

2つの文字または数字の後に7桁の数字が続きます。
  
- 2 つの数字または文字 (大文字小文字を区別しない)
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_ireland_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_ireland_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_ireland_eu_passport_number**|
|:-----|
|passport number  <br/> アイルランドのパスポート番号  <br/> passport いいえ  <br/> pas  <br/> サインアウト  <br/> passeport  <br/> passeport numero  <br/> |
   
## <a name="italy"></a>イタリア

### <a name="format"></a>Format

2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字
  
### <a name="pattern"></a>パターン

2つの文字または数字の後に7桁の数字が続きます。
  
- 2 つの数字または文字 (大文字小文字を区別しない)
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_italy_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_italy_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_italy_eu_passport_number**|
|:-----|
|イタリアのパスポート番号  <br/> repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> passport number  <br/> italiana passaporto numero  <br/> passaporto numero  <br/> numéro passeport italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>ラトビア

### <a name="format"></a>Format

2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字
  
### <a name="pattern"></a>パターン

2つの文字または数字の後に7桁の数字が続きます。
  
- 2 つの数字または文字 (大文字小文字を区別しない)
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_latvia_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_latvia_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_latvia_eu_passport_number**|
|:-----|
|passport number  <br/> ラトビアのパスポート番号  <br/> passport いいえ  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>リトアニア

### <a name="format"></a>Format

8桁の数字または文字、スペースまたは区切り記号なし
  
### <a name="pattern"></a>パターン

8桁の数字または文字 (大文字小文字を区別しない)
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_lithuania_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_lithuania_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_lithuania_eu_passport_number**|
|:-----|
|passport number  <br/> lithunian パスポート番号  <br/> passport いいえ  <br/> 大き o numeris  <br/> |
   
## <a name="luxemburg"></a>ルクセンブルク

### <a name="format"></a>Format

8桁の数字または文字、スペースまたは区切り記号なし
  
### <a name="pattern"></a>パターン

8桁の数字または文字 (大文字小文字を区別しない)
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_nation_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_nation_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_nation_eu_passport_number**|
|:-----|
|passport number  <br/> ラトビアのパスポート番号  <br/> passport いいえ  <br/> passnummer  <br/> |
   
## <a name="malta"></a>マルタ

### <a name="format"></a>Format

スペースまたは区切り文字を含まない7桁の数字
  
### <a name="pattern"></a>パターン

 7 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_malta_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_malta_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_malta_eu_passport_number**|
|:-----|
|passport number  <br/> マルタのパスポート番号  <br/> passport いいえ  <br/> numru tal-passaport  <br/> |
   
## <a name="netherlands"></a>オランダ

### <a name="format"></a>Format

9文字または数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

9桁の文字または数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_netherlands_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_netherlands_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_netherlands_eu_passport_number**|
|:-----|
|オランダのパスポート番号  <br/> passport number  <br/> オランダのパスポート番号  <br/> nederlanden の nummer  <br/> 大き poort  <br/> nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>ポーランド

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポーランドのパスポート番号」セクションを参照してください。
  
## <a name="portugal"></a>ポルトガル

### <a name="format"></a>Format

1文字の後に6桁の数字 (スペースまたは区切り記号を付けない)
  
### <a name="pattern"></a>パターン

1文字の後に6桁の数字:
  
- 1 文字 (大文字小文字を区別しない)
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_portugal_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_portugal_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_portugal_eu_passport_number**|
|:-----|
|passport number  <br/> ポルトガルのパスポート番号  <br/> passport いいえ  <br/> número do passaporte  <br/> |
   
## <a name="romania"></a>ルーマニア

### <a name="format"></a>Format

スペースと区切り文字を除いた8桁または9桁の数字
  
### <a name="pattern"></a>パターン

8桁または9桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_romania_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_romania_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_romania_eu_passport_number**|
|:-----|
|passport number  <br/> ルーマニアのパスポート番号  <br/> passport いいえ  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>スロバキア

### <a name="format"></a>Format

1つの数字または文字の後に7桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

1桁の数字または文字 (大文字小文字を区別しない) の後に7桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_slovakia_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_slovakia_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_slovakia_eu_passport_number**|
|:-----|
|passport number  <br/> スロバキアのパスポート番号  <br/> passport いいえ  <br/> číslo/  <br/> |
   
## <a name="slovenia"></a>スロベニア

### <a name="format"></a>Format

2つの文字の後に、スペースや区切り文字を含まない7桁の数字
  
### <a name="pattern"></a>パターン

2つの文字の後に7桁の数字:
  
- 文字 "P"
    
- 1文字の大文字
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_slovenia_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_slovenia_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_slovenia_eu_passport_number**|
|:-----|
|passport number  <br/> スロベニアのパスポート番号  <br/> passport いいえ  <br/> številka potnega lista  <br/> |
   
## <a name="spain"></a>スペイン

### <a name="format"></a>Format

スペースまたは区切り記号を含まない、文字と数字の8文字または9文字の組み合わせ
  
### <a name="pattern"></a>パターン

文字と数字の8文字または9文字の組み合わせ。
  
-  2桁の数字または文字 
    
- 1桁の数字または文字 (省略可能)
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_spain_eu_passport_number`は、パターンに一致するコンテンツを検出します。 
    
- from `Keywords_spain_eu_passport_number`キーワードが見つかりました。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

| |
|**Keywords_spain_eu_passport_number**|
|:-----|
|サインアウト  <br/> スペインのパスポート  <br/> パスポートブック  <br/> passport number  <br/> passport いいえ  <br/> libreta pasaporte  <br/> número pasaporte  <br/> españ a pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>スウェーデン

詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「スウェーデンのパスポート番号」セクションを参照してください。
  
## <a name="uk"></a>佐賀

詳細については、「米国/英国」を参照してください。 [機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、パスポート番号
  
## <a name="see-also"></a>関連項目

[機密情報の種類の検索基準:](what-the-sensitive-information-types-look-for.md)

