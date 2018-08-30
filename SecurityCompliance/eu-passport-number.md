---
title: EU パスポート番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: このトピックでは、データ損失防止 (DLP) ポリシーがどの EU パスポート番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
ms.openlocfilehash: 71acc39b885c057e1771ec13b2f3c25017ac1bb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532233"
---
# <a name="eu-passport-number"></a>EU パスポート番号

このトピックでは、データ損失防止 (DLP) ポリシーがどの EU パスポート番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
  
## <a name="austria"></a>オーストリア

### <a name="format"></a>形式

省略可能なスペースと 7 桁の後に 1 つの文字
  
### <a name="pattern"></a>パターン

1 つの文字、7 桁の数字、およびスペースを 1 つの組み合わせです。
  
- 1 文字 (大文字小文字を区別しない)
    
- 1 つのスペース (省略可能)
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_austria_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_austria_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_austria_eu_passport_number**|
|:-----|
|パスポート番号  <br/> オーストリアのパスポート番号  <br/> パスポートなし  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>ベルギー

### <a name="format"></a>形式

スペースや区切り文字なしで 6 桁の数字の後に 2 つの文字
  
### <a name="pattern"></a>パターン

2 文字 6 桁の後に、
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_belgium_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_belgium_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_belgium_eu_passport_number**|
|:-----|
|パスポート番号  <br/> ベルギーのパスポート番号  <br/> パスポートなし  <br/> paspoort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>ブルガリア

### <a name="format"></a>形式

スペースや区切り記号なしの 9 桁
  
### <a name="pattern"></a>パターン

 9 桁の数字 
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_bulgaria_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_bulgaria_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_bulgaria_eu_passport_number**|
|:-----|
|パスポート番号  <br/> ブルガリア語パスポート番号  <br/> パスポートなし  <br/> НОМЕР НА ПАСПОРТА  <br/> |
   
## <a name="croatia"></a>クロアチア

### <a name="format"></a>形式

スペースや区切り記号なしの 9 桁
  
### <a name="pattern"></a>パターン

 9 桁の数字 
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_croatia_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_croatia_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_croatia_eu_passport_number**|
|:-----|
|パスポート番号  <br/> クロアチア パスポート番号  <br/> パスポートなし  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>キプロス

### <a name="format"></a>形式

スペースや区切り文字なしで 6-8 桁の数字の後に 1 つの文字
  
### <a name="pattern"></a>パターン

6 ~ 8 桁の数字の後に 1 つの文字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_cyprus_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_cyprus_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_cyprus_eu_passport_number**|
|:-----|
|パスポート番号  <br/> キプロス パスポート番号  <br/> パスポートなし  <br/> ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ  <br/> |
   
## <a name="czech-republic"></a>チェコ共和国

### <a name="format"></a>形式

8 桁のスペースや区切り文字なし
  
### <a name="pattern"></a>パターン

8 桁のスペースや区切り文字なし
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_czech_republic_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_czech_republic_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_czech_republic_eu_passport_number**|
|:-----|
|パスポート番号  <br/> チェコ語パスポート番号  <br/> パスポートなし  <br/> cestovní pas  <br/> pas  <br/> |
   
## <a name="denmark"></a>デンマーク

### <a name="format"></a>形式

スペースや区切り記号なしの 9 桁
  
### <a name="pattern"></a>パターン

 9 桁の数字 
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_denmark_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_denmark_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_denmark_eu_passport_number**|
|:-----|
|パスポート番号  <br/> デンマークのパスポート番号  <br/> パスポートなし  <br/> pas  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>エストニア

### <a name="format"></a>形式

スペースや区切り文字なしで 7 桁の数字の後に 1 つの文字
  
### <a name="pattern"></a>パターン

7 桁の後に 1 つの文字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_estonia_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_estonia_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_estonia_eu_passport_number**|
|:-----|
|パスポート番号  <br/> エストニア語パスポート番号  <br/> パスポートなし  <br/> eesti kodaniku パス  <br/> |
   
## <a name="finland"></a>フィンランド

詳細についてを参照してください「フィンランドのパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="france"></a>フランス

詳細についてを参照してください「東京都パスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>ドイツ

詳細についてを参照してください「ドイツのパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>ギリシャ

### <a name="format"></a>形式

スペースや区切り文字なしで 7 桁の数字の後に 2 つの文字
  
### <a name="pattern"></a>パターン

2 桁の文字の後に 7 桁の数字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_greece_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_greece_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_greece_eu_passport_number**|
|:-----|
|パスポート番号  <br/> ギリシャ語のパスポート番号  <br/> パスポートなし  <br/> ΔΙΑΒΑΤΗΡΙΟ  <br/> |
   
## <a name="hungary"></a>ハンガリー

### <a name="format"></a>形式

スペースや区切り文字なしで 6 または 7 桁の数字の後に 2 つの文字
  
### <a name="pattern"></a>パターン

6 または 7 桁の数字の後に 2 つの文字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_hungary_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_hungary_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_hungary_eu_passport_number**|
|:-----|
|パスポート番号  <br/> ハンガリーのパスポート番号  <br/> パスポートなし  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>Ireland

### <a name="format"></a>形式

2 つの文字または数字の後にスペースや区切り文字なしで 7 桁の数字
  
### <a name="pattern"></a>パターン

2 つの文字または数字が 7 桁の後に。
  
- 2 つの数字または文字 (大文字小文字を区別しない)
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_ireland_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_ireland_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_ireland_eu_passport_number**|
|:-----|
|パスポート番号  <br/> アイルランドのパスポート番号  <br/> パスポートなし  <br/> pas  <br/> passport  <br/> passeport  <br/> passeport して  <br/> |
   
## <a name="italy"></a>イタリア

### <a name="format"></a>形式

2 つの文字または数字の後にスペースや区切り文字なしで 7 桁の数字
  
### <a name="pattern"></a>パターン

2 つの文字または数字が 7 桁の後に。
  
- 2 つの数字または文字 (大文字小文字を区別しない)
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_italy_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_italy_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_italy_eu_passport_number**|
|:-----|
|イタリアのパスポート番号  <br/> repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> パスポート番号  <br/> italiana passaporto して  <br/> passaporto して  <br/> numéro passeport italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>ラトビア

### <a name="format"></a>形式

2 つの文字または数字の後にスペースや区切り文字なしで 7 桁の数字
  
### <a name="pattern"></a>パターン

2 つの文字または数字が 7 桁の後に。
  
- 2 つの数字または文字 (大文字小文字を区別しない)
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_latvia_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_latvia_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_latvia_eu_passport_number**|
|:-----|
|パスポート番号  <br/> ラトビア語パスポート番号  <br/> パスポートなし  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>リトアニア

### <a name="format"></a>形式

8 つのスペースや区切り記号付きの文字または数字
  
### <a name="pattern"></a>パターン

8 つの数字または文字 (いない大文字小文字を区別)
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_lithuania_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_lithuania_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_lithuania_eu_passport_number**|
|:-----|
|パスポート番号  <br/> lithunian パスポート番号  <br/> パスポートなし  <br/> paso numeris  <br/> |
   
## <a name="luxemburg"></a>ルクセンブルグ

### <a name="format"></a>形式

8 つのスペースや区切り記号付きの文字または数字
  
### <a name="pattern"></a>パターン

8 つの数字または文字 (いない大文字小文字を区別)
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_nation_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_nation_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_nation_eu_passport_number**|
|:-----|
|パスポート番号  <br/> ラトビア語パスポート番号  <br/> パスポートなし  <br/> passnummer  <br/> |
   
## <a name="malta"></a>マルタ

### <a name="format"></a>形式

スペースや区切り文字なしの 7 桁
  
### <a name="pattern"></a>パターン

 7 桁の数字 
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_malta_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_malta_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_malta_eu_passport_number**|
|:-----|
|パスポート番号  <br/> マルタ語パスポート番号  <br/> パスポートなし  <br/> numru tal ・ passaport  <br/> |
   
## <a name="netherlands"></a>オランダ

### <a name="format"></a>形式

9 つの文字またはスペースや区切り文字と数字
  
### <a name="pattern"></a>パターン

9 つの文字または数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_netherlands_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_netherlands_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_netherlands_eu_passport_number**|
|:-----|
|オランダのパスポート番号  <br/> パスポート番号  <br/> オランダのパスポート番号  <br/> nederlanden paspoort nummer  <br/> paspoort  <br/> nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>ポーランド

詳細についてを参照してください「ポーランド パスポート番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="portugal"></a>ポルトガル

### <a name="format"></a>形式

スペースや区切り文字なしで 6 桁の数字の後に 1 つの文字
  
### <a name="pattern"></a>パターン

6 桁の後に 1 つの文字。
  
- 1 文字 (大文字小文字を区別しない)
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_portugal_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_portugal_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_portugal_eu_passport_number**|
|:-----|
|パスポート番号  <br/> ポルトガル語パスポート番号  <br/> パスポートなし  <br/> número は passaporte  <br/> |
   
## <a name="romania"></a>ルーマニア

### <a name="format"></a>形式

スペースや区切り記号なしの 8 または 9 の数字
  
### <a name="pattern"></a>パターン

8 または 9 桁の数字
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_romania_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_romania_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_romania_eu_passport_number**|
|:-----|
|パスポート番号  <br/> ルーマニアのパスポート番号  <br/> パスポートなし  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>スロバキア

### <a name="format"></a>形式

1 つの数字または文字の後にスペースや区切り文字なしで 7 桁の数字
  
### <a name="pattern"></a>パターン

1 つの桁または 7 桁の後に文字 (いない大文字小文字を区別)
  
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_slovakia_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_slovakia_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_slovakia_eu_passport_number**|
|:-----|
|パスポート番号  <br/> スロバキア語パスポート番号  <br/> パスポートなし  <br/> Číslo pasu  <br/> |
   
## <a name="slovenia"></a>スロベニア

### <a name="format"></a>形式

スペースや区切り文字なしで 7 桁の数字の後に 2 つの文字
  
### <a name="pattern"></a>パターン

7 桁の後に 2 つの文字。
  
- 文字"P"
    
- 大文字を 1 つ
    
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_slovenia_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_slovenia_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_slovenia_eu_passport_number**|
|:-----|
|パスポート番号  <br/> スロベニア語パスポート番号  <br/> パスポートなし  <br/> Številka potnega リスト  <br/> |
   
## <a name="spain"></a>スペイン

### <a name="format"></a>形式

文字とスペースや区切り記号と数字の 8 または 9 文字組み合わせ
  
### <a name="pattern"></a>パターン

文字と数字の 8 または 9 文字の組み合わせです。
  
-  2 つの数字または文字 
    
- 1 つの数字または文字 (省略可能)
    
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現`Regex_spain_eu_passport_number`パターンに一致するコンテンツを検索します。 
    
- キーワードの`Keywords_spain_eu_passport_number`があります。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

| |
|**Keywords_spain_eu_passport_number**|
|:-----|
|passport  <br/> スペインのパスポート  <br/> パスポート帳  <br/> パスポート番号  <br/> パスポートなし  <br/> libreta pasaporte  <br/> número pasaporte  <br/> españa pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>スウェーデン

詳細についてを参照してください「スウェーデンのパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="uk"></a>英国

詳細についてを参照してください「米国/英国のパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。
  
## <a name="see-also"></a>関連項目

[機密情報の種類の検索基準:](what-the-sensitive-information-types-look-for.md)

