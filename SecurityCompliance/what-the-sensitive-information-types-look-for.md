---
title: 機密情報の種類の検索基準：
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;準拠のセンターには、DLP ポリシーを使用する準備ができている 80 の機密性の高い情報の種類が含まれています。このトピックでは、機密性の高い情報の種類のすべてを一覧表示しを示しています DLP ポリシーそれぞれの種類を検出したとき。
ms.openlocfilehash: 4b083f80e02c80053b63ee897b2515a4505c16d9
ms.sourcegitcommit: 8c5a88433cff23c59b436260808cf3d91b06fdef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2018
ms.locfileid: "27194738"
---
# <a name="what-the-sensitive-information-types-look-for"></a>機密情報の種類の検索基準

Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;コンプライアンス センターには、DLP ポリシーに使用する準備ができている多くの機密性の高い情報の種類が含まれています。このトピックでは、機密性の高い情報の種類のすべてを一覧表示しを示しています DLP ポリシーそれぞれの種類を検出したとき。機密性の高い情報の種類は、正規表現、または関数を識別可能なパターンによって定義されます。さらに、機密性の高い情報の種類を識別するキーワードやチェックサムなどの corroborative の証拠を使用できます。信頼レベルと近接は、評価プロセスで使用されます。
  
## <a name="aba-routing-number"></a>ABA ルーティング番号

### <a name="format"></a>形式

書式設定ありまたは書式設定なしの 9 桁の数字

### <a name="pattern"></a>パターン

書式設定されている場合:
- 0、1、2、3、6、7、または 8 で始まる 4 桁の数字
- ハイフン
- 4 桁の数字
- ハイフン
- 1 桁の数字

以降では 0、1、2、3、6、7、8 または 9 連続した数字をフォーマットします。 

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_aba_routing がパターンに一致するコンテンツを検出した。
- Keyword_ABA_Routing のキーワードを検出した。

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>キーワード

#### <a name="keywordabarouting"></a>Keyword_ABA_Routing

- aba
- 
aba #
- 
aba routing #
- aba ルーティング番号
- 
aba#
- 
abarouting#
- 
aba number
- 
abaroutingnumber
- 
american bank association routing #
- 
american bank association routing number
- 
americanbankassociationrouting#
- 
americanbankassociationroutingnumber
- 
bank routing number
- 
bankrouting#
- 
bankroutingnumber
- 
routing transit number
- 
RTN
 
   
## <a name="argentina-national-identity-dni-number"></a>アルゼンチンの国民識別 (DNI) 番号

### <a name="format"></a>形式

ピリオドで区切られた 8 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字:
- 2 桁の数字
- ピリオド 1 つ 
- 3 桁の数字
- ピリオド 1 つ 
- 3 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_argentina_national_id がパターンに一致するコンテンツを検出した。
- Keyword_argentina_national_id のキーワードを検出した。

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordargentinanationalid"></a>Keyword_argentina_national_id

- Argentina National Identity number
 
- ID 
- 国家身分証明書の識別 
- DNI
 
- 担当者の NIC の国別レジストリ 
- Documento Nacional de Identidad
 
- Registro Nacional de las Personas
 
- Identidad
 
- Identificación
 
   
## <a name="australia-bank-account-number"></a>オーストラリアの銀行口座番号

### <a name="format"></a>形式

銀行支店識別コード (BSB) を含むまたは含まない 6 ～ 10 桁の数字

### <a name="pattern"></a>パターン

勘定番号は、6-10 桁の数字です。オーストラリアの銀行の状態の枝番号。
- 3 桁の数字 
- ハイフン 1 つ  
- 3 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_australia_bank_account_number のキーワードを検出した。
- 正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_australia_bank_account_number のキーワードを検出した。

```
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordaustraliabankaccountnumber"></a>Keyword_australia_bank_account_number

- swift bank code
- 
correspondent bank
- 
base currency
- 
usa account
- 
holder address
- 
bank address
- 
information account
- 
fund transfers
- 
bank charges
- 
bank details
- 
banking information
- 
full names
- 

iaea

   
## <a name="australia-drivers-license-number"></a>オーストラリアの運転免許証番号

### <a name="format"></a>形式

9 桁の文字と数字

### <a name="pattern"></a>パターン

9 つの文字と数字: 

- 2 つの数字または文字 (大文字小文字を区別しない) 
- 2 桁の数字 
- 5 つの数字または文字 (大文字小文字を区別しない)

または

- 1 ～ 2 桁の省略可能な文字 (大文字小文字の区別なし)  
- 4 ～ 9 桁の数字

または

- 9 桁の数字または文字 (大文字小文字の区別なし)

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_australia_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_australia_drivers_license_number のキーワードを検出した。
- Keyword_australia_drivers_license_number_exclusions のキーワードを検出しなかった。

```
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordaustraliadriverslicensenumber"></a>Keyword_australia_drivers_license_number

- international driving permits
- 
australian automobile association
- 
international driving permit
- DriverLicence
- DriverLicences
- ドライバー Lic
- Driver Licence

- Driver Licences

- DriversLic
- DriversLicence
- DriversLicences
- ドライバー Lic
- ドライバー Lics
- ドライバー ライセンス
- ドライバー ライセンス
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- ドライバー ' Lic
- ドライバー ' Lics
- ドライバー ' ライセンス
- ドライバー ' ライセンス
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- ドライバーの Lic
- ドライバーの Lics
- Driver's Licence

- Driver's Licences

- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic#
- 
Driver Lics#

- ドライバーのライセンス数
- ドライバーのライセンス数
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- ドライバー Lic #
- ドライバー Lics #
- ドライバーのライセンス数
- ドライバーのライセンス数
- Driver'Lic#

- Driver'Lics#

- Driver'Licence#

- Driver'Licences#

- Driver' Lic#

- Driver' Lics#

- ドライバー ' ライセンス数
- ドライバー ' ライセンス数
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic#

- Driver's Lics#

- ドライバーのライセンス数
- ドライバーのライセンス数 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- ドライバー ライセンス
- ドライバー ライセンス
- 証
- DriversLicenses
- 運転免許証番号
- ドライバー ライセンス
- Driver'License
- Driver'Licenses
- ドライバー ' ライセンス
- ドライバー ' ライセンス
- Driver'sLicense
- Driver'sLicenses
- 運転免許証
- 運転免許証
- DriverLicense #
- DriverLicenses #
- ドライバーのライセンス数
- ドライバーのライセンス数
- 証番号
- DriversLicenses #
- ドライバーのライセンス数
- ドライバーのライセンス数
- Driver'License#

- Driver'Licenses#

- Driver' License#

- Driver' Licenses#

- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#

- 

Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>オーストラリアの医療口座番号

### <a name="format"></a>形式

10 ～ 11 桁の数字

### <a name="pattern"></a>パターン

10 ～ 11 桁の数字:
- 最初の桁は 2 ～ 6 のいずれか
- 9 桁目はチェック ディジット
- 10 桁目は発行桁
- 11 桁目 (省略可能) は個人番号

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。
- Keyword_Australia_Medical_Account_Number のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordaustraliamedicalaccountnumber"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- 
medicare payments
- 
mortgage account
- 
bank payments
- 
information branch
- 
credit card loan
- 
department of human services
- ローカル サービス
- 

medicare

   
## <a name="australia-passport-number"></a>オーストラリアのパスポート番号

### <a name="format"></a>形式

1 桁の文字の後に 7 桁の数字

### <a name="pattern"></a>パターン

1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。
- Keyword_passport または Keyword_australia_passport_number からキーワードを検出するとします。

```
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>キーワード

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number
- 
Passport No
- Passport #

- Passport#

- PassportID
- Passportno

- passportnumber

- パスポート
- パスポート番号

- パスポートのNum

- 
パスポート ＃
 
- Numéro de passeport
- 
Passeport n °
- Passeport Non

- Passeport #

- Passeport#

- PasseportNon
- Passeportn °


#### <a name="keywordaustraliapassportnumber"></a>Keyword_australia_passport_number

- passport
- 
passport details
- 
immigration and citizenship
- 
commonwealth of australia
- 
department of immigration
- 
residential address
- 
department of immigration and citizenship
- visa

- 
national identity card
- パスポート番号
- 
travel document
- 

issuing authority
   
## <a name="australia-tax-file-number"></a>オーストラリアの納税者番号

### <a name="format"></a>形式

8 ～ 9 桁の数字

### <a name="pattern"></a>パターン

8 ～ 9 桁の数字。通常は次のようにスペースが含まれます。
- 3 桁の数字 
- 省略可能なスペース 
- 3 桁の数字 
- 省略可能なスペース 
- 2 ～ 3 桁の数字。最後の桁はチェック ディジット用です

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。
- Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。
- チェックサムが渡される。

```
    <!-- Australia Tax File Number -->
<Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
    
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_Australia_Tax_File_Number" />
          <Match idRef="Keyword_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordaustraliataxfilenumber"></a>Keyword_Australia_Tax_File_Number

- australian business number
- 
marginal tax rate
- 
medicare levy
- 
portfolio number
- 
service veterans
- 
withholding tax
- 
individual tax return
- 

tax file number

#### <a name="keywordnumberexclusions"></a>Keyword_number_exclusions

- 00000000
- 11111111
- 22222222
- 33333333
- 44444444
- 55555555
- 66666666
- 77777777
- 88888888
- 99999999
- 000000000
- 111111111
- 222222222
- 333333333
- 444444444
- 555555555
- 666666666
- 777777777
- 888888888
- 999999999
- 0000000000
- 1111111111
- 2222222222
- 3333333333
- 4444444444
- 5555555555
- 6666666666
- 7777777777
- 8888888888
- 9999999999
   
## <a name="belgium-national-number"></a>ベルギーの国民番号

### <a name="format"></a>形式

11 の数字と区切り文字

### <a name="pattern"></a>パターン

11 の数字と区切り文字:
- YY.MM.DD の形式の生年月日を表す 6 桁の数字と 2 つピリオド  
- ハイフン 1 つ  
- 3 桁の連番 (男性の場合は奇数、女性の場合は偶数)  
- ピリオド 1 つ  
- チェック ディジットとして機能する 2 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_belgium_national_number がパターンに一致するコンテンツを検出した。
- Keyword_belgium_national_number のキーワードを検出した。
- チェックサムが渡される。

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordbelgiumnationalnumber"></a>Keyword_belgium_national_number

- Identity
- Registration
- Identification 
- ID 
- Identiteitskaart
- Registratie nummer 
 
- Identificatie nummer
 
- Identiteit
- Registratie
- Identificatie

 
- Carte d’identité
 
- numéro d'immatriculation
- numéro d'identification
- 
identité
 
- inscription
 
- Identifikation
- Identifizierung
- Identifikationsnummer
- Personalausweis
- Registrierung
- Registrationsnummer

   
## <a name="brazil-cpf-number"></a>ブラジルの CPF 番号

### <a name="format"></a>形式

書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字

### <a name="pattern"></a>パターン

書式設定されている場合:
- 3 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ハイフン 1 つ  
- チェック ディジットとして機能する 2 桁の数字

書式設定なし:
- 11 桁の数字 (最後の 2 桁はチェック ディジット)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_cpf がパターンに一致するコンテンツを検出した。
- Keyword_brazil_cpf のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_cpf がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordbrazilcpf"></a>Keyword_brazil_cpf

- CPF
- Identification
- Registration
- Revenue
- Cadastro de Pessoas Físicas
 
- Imposto
 
- Identificação
 
- Inscrição
 
- Receita

 
   
## <a name="brazil-legal-entity-number-cnpj"></a>Brazil Legal Entity Number (CNPJ)

### <a name="format"></a>形式

登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字

### <a name="pattern"></a>パターン
14 桁の数字と区切り文字:
- 2 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 (最初の 8 桁の数字は登録番号)  
- スラッシュ 1 つ  
- 4 桁の枝番号  
- ハイフン 1 つ  
- チェック ディジットとして機能する 2 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_cnpj がパターンに一致するコンテンツを検出した。
- Keyword_brazil_cnpj のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_cnpj がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordbrazilcnpj"></a>Keyword_brazil_cnpj

- CNPJ
 
- CNPJ/MF 
- CNPJ-MF
 
- National Registry of Legal Entities
 
- Taxpayers Registry
 
- Legal entity
 
- Legal entities
 
- Registration Status
 
- Business
 
- Company
- CNPJ
 
- Cadastro Nacional da Pessoa Jurídica
 
- Cadastro Geral de Contribuintes
 
- CGC
 
- Pessoa jurídica
 
- Pessoas jurídicas
 
- Situação cadastral
 
- Inscrição
 
- Empresa
 
   
## <a name="brazil-national-id-card-rg"></a>	ブラジルの国民識別カード (RG)

### <a name="format"></a>形式

Registro Geral (古い形式): 9 桁の数字

Registro de Identidade (RIC) (新しい形式): 11 桁の数字

### <a name="pattern"></a>パターン

Registro Geral (従来の形式):
- 2 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ハイフン 1 つ  
- チェック ディジットとして機能する 1 桁の数字

Registro de Identidade (RIC) (新しい形式)。
- 10 桁の数字 
- ハイフン 1 つ  
- チェック ディジットとして機能する 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_rg がパターンに一致するコンテンツを検出した。
- Keyword_brazil_rg のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_rg がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordbrazilrg"></a>Keyword_brazil_rg

Cédula de identidade 身分証明書国民 id número de rregistro registro de Iidentidade registro geral (このキーワードでは大文字小文字を区別) RG (このキーワードでは大文字小文字を区別) RIC 
   
## <a name="canada-bank-account-number"></a>カナダの銀行口座番号

### <a name="format"></a>形式

7 桁または 12 桁の数字

### <a name="pattern"></a>パターン

カナダの銀行口座番号は 7 桁または 12 桁の数字です。

カナダの銀行口座転送番号は次のとおりです。
- 5 桁の数字 
- ハイフン 1 つ  
- 3 桁の数字または
- 1 桁のゼロ (0)  
- 8 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_canada_bank_account_number のキーワードを検出した。
- 正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_canada_bank_account_number のキーワードを検出した。

```
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordcanadabankaccountnumber"></a>Keyword_canada_bank_account_number

- canada savings bonds
- 
canada revenue agency
- 
canadian financial institution
- 
direct deposit form
- 
canadian citizen
- 
legal representative
- 
notary public
- 
commissioner for oaths
- 
child care benefit
- 
universal child care
- 
canada child tax benefit
- 
income tax benefit
- 
harmonized sales tax
- social insurance number
- 
income tax refund
- 
child tax benefit
- 
territorial payments
- 
institution number
- 
deposit request
- 
banking information
- 

direct deposit
   
## <a name="canada-drivers-license-number"></a>カナダの運転免許証番号

### <a name="format"></a>形式

州によって異なります

### <a name="pattern"></a>パターン

アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_[province_name]_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_[province_name]_drivers_license_name のキーワードを検出した。
- Keyword_canada_drivers_license のキーワードを検出した。

```
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordprovincenamedriverslicensename"></a>Keyword_[province_name]_drivers_license_name

- 州の略号、AB など
- 
州名 (Alberta など)

#### <a name="keywordcanadadriverslicense"></a>Keyword_canada_drivers_license

- DL
- DLS
- CDL
- CDL
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- ドライバー Lic
- ドライバー Lics
- ドライバー ライセンス
- ドライバー ライセンス
- Driver Licence

- Driver Licences

- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- 証
- DriversLicenses
- ドライバー Lic
- ドライバー Lics
- 運転免許証番号
- ドライバー ライセンス
- ドライバー ライセンス
- ドライバー ライセンス
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- ドライバー ' Lic
- ドライバー ' Lics
- ドライバー ' ライセンス
- ドライバー ' ライセンス
- ドライバー ' ライセンス
- ドライバー ' ライセンス
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- ドライバーの Lic
- ドライバーの Lics
- 運転免許証
- 運転免許証
- Driver's Licence

- Driver's Licences

- Permis デ Conduire
- id
- id
- 
idcard number
- 
idcard numbers
- 
idcard #
- 
idcard #s
- idcard カード
- idcard カード
- idcard
- identification number

- identification numbers

- identification #

- 
identification #s
- id カード
- id カード
- 
identification
 
- DL#
- 
DLS#
 
- CDL#
 
- CDLS#
 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences # 
- Driver Lic#
- 
Driver Lics#
 
- ドライバーのライセンス数 
- ドライバーのライセンス数 
- ドライバーのライセンス数 
- ドライバーのライセンス数 
- DriversLic # 
- DriversLics # 
- 証番号 
- DriversLicenses # 
- DriversLicence # 
- DriversLicences # 
- ドライバー Lic # 
- ドライバー Lics # 
- ドライバーのライセンス数 
- ドライバーのライセンス数 
- ドライバーのライセンス数 
- ドライバーのライセンス数 
- Driver'Lic#
 
- Driver'Lics#
 
- Driver'License#
 
- Driver'Licenses#
 
- Driver'Licence#
 
- Driver'Licences#
 
- Driver' Lic#
 
- Driver' Lics#
 
- Driver' License#
 
- Driver' Licenses#
 
- ドライバー ' ライセンス数 
- ドライバー ' ライセンス数 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver'sLicence # 
- Driver'sLicences # 
- Driver's Lic#
 
- Driver's Lics#
 
- Driver's License#
 
- Driver's Licenses#
 
- ドライバーのライセンス数 
- ドライバーのライセンス数 
- Permis de Conduire # 
- id 番号 
- id # 
- idcard card#
 
- idcard cards#
 
- idcard#
 
- identification card#
 
- identification cards#
 
- identification#
 
   
## <a name="canada-health-service-number"></a>カナダの健康保険番号

### <a name="format"></a>形式

10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_canada_health_service_number がパターンに一致するコンテンツを検出した。
- Keyword_canada_health_service_number のキーワードを検出した。

```
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordcanadahealthservicenumber"></a>Keyword_canada_health_service_number

- personal health number
- 
patient information
- 正常性サービス
- 
speciality services
- 
automobile accident
- 
patient hospital
- 
psychiatrist
- 
workers compensation
- 
disability
      
## <a name="canada-passport-number"></a>カナダのパスポート番号

### <a name="format"></a>形式

2 桁の大文字の後に 6 桁の数字

### <a name="pattern"></a>パターン

2 桁の大文字の後に 6 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。
- Keyword_canada_passport_number または Keyword_passport からキーワードを検出するとします。

``` 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordcanadapassportnumber"></a>Keyword_canada_passport_number

- canadian citizenship
- 
canadian passport
- 
passport application
- 
passport photos
- 
certified translator
- 
canadian citizens
- 
processing times
- 

renewal application

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number
- 
Passport No
- Passport #

- Passport#

- PassportID
- Passportno

- passportnumber

- パスポート
- パスポート番号

- パスポートのNum

- パスポート＃

- Numéro de passeport
- 
Passeport n °
- Passeport Non

- Passeport #

- Passeport#

- PasseportNon
- 

Passeportn °
   
## <a name="canada-personal-health-identification-number-phin"></a>カナダの個人保健識別番号 (PHIN)

### <a name="format"></a>形式

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Regex_canada_phin の正規表現パターンに一致するコンテンツを検索します。Keyword_canada_phin または Keyword_canada_provinces からの 2 つ以上のキーワードが見つかりました。

```
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordcanadaphin"></a>Keyword_canada_phin

- social insurance number
- 
health information act
- 
income tax information
- 
manitoba health
- 
health registration
- 
prescription purchases
- 
benefit eligibility
- 
personal health
- 
power of attorney
- 
registration number
- personal health number
- 
practitioner referral
- 
wellness professional
- 
patient referral
- 

health and wellness

#### <a name="keywordcanadaprovinces"></a>Keyword_canada_provinces

- Nunavut
- 
Quebec
- 
Northwest Territories
- 
Ontario
- 
British Columbia
- 
Alberta
- 
Saskatchewan
- 
Manitoba
- 
Yukon
- 
Newfoundland and Labrador
- 
New Brunswick
- 
Nova Scotia
- 
Prince Edward Island
- カナダ
   
## <a name="canada-social-insurance-number"></a>カナダの社会保険番号

### <a name="format"></a>形式

9 桁の数字と省略可能なハイフンまたはスペース

### <a name="pattern"></a>パターン

書式設定されている場合:
- 3 桁の数字 
- ハイフンまたはスペース 1 つ  
- 3 桁の数字 
- ハイフンまたはスペース 1 つ  
- 3 桁の数字

9 桁のフォーマットされていません。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。
- 以下の 2 つ以上の条件に該当する:
    - Keyword_sin のキーワードを検出した。
    - Keyword_sin_collaborative のキーワードを検出した。
    - 関数 Func_eu_date が適切な日付形式の日付を検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。
- Keyword_sin のキーワードを検出した。
- チェックサムが渡される。

```
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordsin"></a>Keyword_sin

- sin 
- social insurance
 
- numero d'assurance sociale
 
- sins
 
- ssn 
- ssn 
- 社会保障 
- numero d'assurance social
 
- 国際識別番号 
- 
national id 
- sin#
 
- soc ins
 
- social ins
 

#### <a name="keywordsincollaborative"></a>Keyword_sin_collaborative

- driver's license 
- drivers license 
- ドライバーのライセンス 
- drivers licence 
- DOB
 
- 誕生日 
- 誕生日  
- Date of Birth
 
   
## <a name="chile-identity-card-number"></a>チリの身分証明書番号

### <a name="format"></a>形式

7-8 桁の数字と区切り文字チェックの数字または文字

### <a name="pattern"></a>パターン

7 ～ 8 桁の数字と区切り文字:
- 1 ～ 2 桁の数字  
- ピリオド 1 つ  
- 3 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ダッシュ 
- チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別なし)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_chile_id_card がパターンに一致するコンテンツを検出した。
- Keyword_chile_id_card のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_chile_id_card がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordchileidcard"></a>Keyword_chile_id_card

- National Identification Number
 
- Identity card 
- ID 
- Identification 
- Rol Único Nacional
 
- 実行 
- Rol Único Tributario
 
- RUT
 
- Cédula de Identidad
 
- Número De Identificación Nacional
 
- Tarjeta de identificación
 
- Identificación
 
   
## <a name="china-resident-identity-card-prc-number"></a>	中国の居民身分証明書 (PRC) 番号

### <a name="format"></a>形式

18 桁の数字

### <a name="pattern"></a>パターン

18 桁の数字:
- 住所コードを表す 6 桁の数字  
- YYYYMMDD の形式で生年月日を表す 8 桁の数字  
- 順序コードを表す 3 桁の数字  
- チェック ディジットとして機能する 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_china_resident_id がパターンに一致するコンテンツを検出した。
- Keyword_china_resident_id のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_china_resident_id がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

### <a name="keywordchinaresidentid"></a>Keyword_china_resident_id

- Resident Identity Card
 
- PRC
 
- National Identification Card
 
- 身份证  
- 居民 身份证  
- 居民身份证
 
- 鉴定

 
- 身分證  
- 居民 身份證
- 鑑定  
   
## <a name="credit-card-number"></a>クレジット カード番号

### <a name="format"></a>形式

16 桁の数字書式を設定することができますが、または書式設定されていない (dddddddddddddddd) と、Luhn のテストに合格する必要があります。

### <a name="pattern"></a>パターン

世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。

### <a name="checksum"></a>チェックサム

あり (Luhn のチェックサム)

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_credit_card がパターンに一致するコンテンツを検出した。
- 次のいずれかの条件に該当する:
    - Keyword_cc_verification のキーワードを検出した。
    - Keyword_cc_name のキーワードを検出した。
    - 関数 Func_expiration_date が適切な日付形式の日付を検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_credit_card がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordccverification"></a>Keyword_cc_verification

- card verification
- card identification number
- cvn

- cid

- cvc2
- cvv2
- pin block

- security code

- security number

- security no

- issue number

- issue no

- cryptogramme

- numéro de sécurité

- numero de securite

- kreditkartenprüfnummer

- kreditkartenprufnummer

- prüfziffer

- prufziffer

- sicherheits Kode
- sicherheitscode

- sicherheitsnummer

- verfalldatum

- codice di verifica

- cod. sicurezza

- 代金引換払いの sicurezza
- 
n autorizzazione
- código

- codigo

- cod. seg

- 代金引換払い seg
- código de segurança

- codigo de seguranca

- codigo de segurança

- código de seguranca

- cód. segurança

- 代金引換払いです。seguranca 代金引換払いです。segurança
- cód. seguranca

- cód segurança
- 代金引換払いの代金引換払い segurança の seguranca
- cód seguranca
- número de verificação

- numero de verificacao

- ablauf

- gültig bis

- gültigkeitsdatum

- gultig bis

- gultigkeitsdatum

- scadenza

- data scad

- fecha de expiracion

- fecha de venc

- vencimiento

- válido hasta

- valido hasta

- vto

- data de expiração

- data de expiracao

- data em que expira

- validade

- valor

- vencimento

- Venc 

#### <a name="keywordccname"></a>Keyword_cc_name

- amex
- 
american express
- americanexpress

- Visa
- mastercard

- master card

- 
mc
 
- mastercards
- 
master cards
- 給仕のクラブ
- diners club

- dinersclub

- discover card

- discovercard

- discover cards

- 安全
- japanese card bureau

- carte blanche

- carteblanche

- credit card

- cc #
- cc # します。
- 
expiration date
- exp date

- 
expiry date
- 
date d’expiration
- 
date d'exp
- 
date expiration
- bank card

- 
bankcard
- card number

- card num

- cardnumber

- cardnumbers

- card numbers

- creditcard

- credit cards

- creditcards

- ccn

- card holder

- cardholder

- card holders

- cardholders

- check card

- checkcard

- check cards

- checkcards

- debit card

- debitcard

- debit cards

- debitcards

- atm card

- atmcard

- atm cards

- atmcards

- 
enroute
- 
en route
- card type

- carte bancaire

- carte de crédit

- carte de credit

- numéro de carte

- numero de carte

- nº de la carte

- nº de carte

- kreditkarte

- karte

- karteninhaber

- karteninhabers
- kreditkarteninhaber

- kreditkarteninstitut

- kreditkartentyp

- eigentümername

- 
kartennr
 
- kartennummer
- 
kreditkartennummer
- kreditkarten nummer
- carta di credito

- carta credito

- carta
- n carta
- nr. carta

- nr carta
- numero carta

- numero della carta

- numero di carta

- tarjeta credito

- tarjeta de credito

- 
tarjeta crédito
- 
tarjeta de crédito
- tarjeta de atm

- tarjeta atm

- tarjeta debito

- tarjeta de debito

- 
tarjeta débito
- 
tarjeta de débito
- nº de tarjeta

- no. de tarjeta

- なし de tarjeta
- numero de tarjeta

- número de tarjeta

- tarjeta no

- tarjetahabiente

- cartão de crédito

- cartão de credito

- cartao de crédito

- cartao de credito

- cartão de débito

- cartao de débito

- cartão de debito

- cartao de debito

- débito automático
- debito automatico

- 
número do cartão
- 
numero do cartão
 
- número do cartao
- 
numero do cartao
- número de cartão

- numero de cartão

- número de cartao

- numero de cartao

- nº は cartão
- nº do cartao

- nº. do cartão

- なしは cartão
- なしは cartao
- no. do cartão

- 
no. do cartao
 
   
## <a name="croatia-identity-card-number"></a>クロアチアの身分証明書番号

### <a name="format"></a>形式

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の連続する数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_croatia_id_card がパターンに一致するコンテンツを検出した。
- Keyword_croatia_id_card のキーワードを検出した。

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordcroatiaidcard"></a>Keyword_croatia_id_card

- Croatian identity card
- Osobna iskaznica

   
## <a name="croatia-personal-identification-oib-number"></a>クロアチアの個人識別 (OIB) 番号

### <a name="format"></a>形式

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字:
- 10 桁の数字 
- 11 桁の数字の前の国際的なデータ交換のためにチェック桁の最後の桁には、人事部の文字が追加されます。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_croatia_oib_number がパターンに一致するコンテンツを検出した。
- Keyword_croatia_oib_number のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_croatia_oib_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordcroatiaoibnumber"></a>Keyword_croatia_oib_number

- Personal Identification Number
- Osobni identifikacijski broj
 
- OIB
 

   
## <a name="czech-personal-identity-number"></a>チェコ語の個人識別番号

### <a name="format"></a>形式

オプションで 9 桁の数字はスラッシュ (古い形式) と省略可能な 10 桁の数字はスラッシュ (新しい形式)

### <a name="pattern"></a>パターン

9 桁 (古い形式)。
- 9 桁の数字

または

- 生年月日を表す 6 桁の数字
- スラッシュ 1 つ 
- 3 桁の数字

10 桁 (新しい形式)。
- 10 桁の数字

または

- 生年月日を表す 6 桁の数字
- スラッシュ 1 つ  
- 最後の桁がチェック ディジットを 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーとは、85% をこの種類の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_czech_id_card 関数は、パターンに一致するコンテンツを検索します。。Keyword_czech_id_card からキーワードを検出するとします。チェックサムが渡されます。

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a>キーワード

- チェコ語の個人識別番号
- Rodné číslo
   
## <a name="denmark-personal-identification-number"></a>デンマークの個人識別番号

### <a name="format"></a>形式

ハイフンを 1 つ含む 10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字:
- DDMMYY の形式の生年月日を表す 6 桁の数字  
- ハイフン 1 つ  
- 4 桁の数字 (最後の桁はチェック ディジット)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Regex_denmark_id の正規表現パターンに一致するコンテンツを検索します。Keyword_denmark_id からキーワードを検出するとします。チェックサムが渡されます。

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyworddenmarkid"></a>Keyword_denmark_id

- Personal Identification Number
- CPR
- Det Centrale Personregister
- Personnummer
   
## <a name="drug-enforcement-agency-dea-number"></a>麻薬取締局 (DEA) 番号

### <a name="format"></a>形式

2 桁の文字の後に 7 桁の数字

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。
- 次の文字セットのいずれか 1 つの文字 (大文字小文字を区別しない):abcdefghjklmnprstux。これは登録者コードです 
- 1 文字 (大文字小文字を区別しない)。登録者の姓の最初の文字 
- 7 桁の数字。最後の桁はチェック ディジット用です

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_dea_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

なし

   
## <a name="eu-debit-card-number"></a>欧州連合のデビット カード番号

### <a name="format"></a>形式

16 桁の数字

### <a name="pattern"></a>パターン

非常に複雑で信頼性の高いパターン

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_eu_debit_card がパターンに一致するコンテンツを検出した。
- 次の条件のうち 1 つ以上に該当する:
    - Keyword_eu_debit_card のキーワードを検出した。
    - Keyword_card_terms_dict のキーワードを検出した。
    - Keyword_card_security_terms_dict のキーワードを検出した。
    - Keyword_card_expiration_terms_dict のキーワードを検出した。
    - 関数 Func_expiration_date が適切な日付形式の日付を検出した。
- チェックサムが渡される。

```
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordeudebitcard"></a>Keyword_eu_debit_card

- アカウント番号 
- card number
 
- card no.
 
- security number
 
- cc # 

#### <a name="keywordcardtermsdict"></a>Keyword_card_terms_dict

- acct nbr
 
- acct num
 
- acct no
 
- american express
 
- americanexpress
 
- americano espresso
 
- amex 
- atm card
 
- atm cards
 
- atm kaart
 
- atmcard
 
- atmcards
 
- atmkaart
 
- atmkaarten
 
- bancontact
 
- bank card
 
- bankkaart
 
- card holder
 
- card holders
 
- card num
 
- card number
 
- card numbers
 
- card type
 
- cardano numerico
 
- cardholder
 
- cardholders
 
- cardnumber
 
- cardnumbers
 
- carta bianca
 
- carta credito
 
- carta di credito
 
- cartao de credito
 
- cartao de crédito
 
- cartao de debito
 
- cartao de débito
 
- carte bancaire
 
- carte blanche
 
- carte bleue
 
- carte de credit
 
- carte de crédit
 
- carte di credito
 
- carteblanche
 
- cartão de credito
 
- cartão de crédito
 
- cartão de debito
 
- cartão de débito
 
- cb
 
- ccn
 
- check card
 
- check cards
 
- checkcard

- checkcards
 
- chequekaart
 
- cirrus
 
- cirrus-edc-maestro
 
- controlekaart
 
- controlekaarten
 
- credit card
 
- credit cards
 
- creditcard
 
- creditcards
 
- debetkaart
 
- debetkaarten
 
- debit card
 
- debit cards
 
- debitcard
 
- debitcards
 
- debito automatico
 
- diners club
 
- dinersclub
 
- 検出 
- discover card
 
- discover cards
 
- discovercard
 
- discovercards
 
- débito automático
- 
edc
 
- eigentümername
 
- european debit card
 
- hoofdkaart
 
- hoofdkaarten
 
- in viaggio
 
- japanese card bureau
 
- japanse kaartdienst
 
- jcb
 
- kaart
 
- kaart num
 
- kaartaantal
 
- kaartaantallen
 
- kaarthouder
 
- kaarthouders
 
- karte
  
- karteninhaber
 
- karteninhabers
- 
kartennr
 
- kartennummer 
- kreditkarte
 
- kreditkarten nummer 
- kreditkarteninhaber
 
- kreditkarteninstitut
 
- kreditkartennummer
 
- kreditkartentyp
 
- maestro
 
- master card
 
- master cards
 
- mastercard
 
- mastercards 
- mc 
- mister cash
 
- n carta 
- carta 
- なし de tarjeta 
- なしは cartao 
- なしは cartão 
- no. de tarjeta
 
- no. do cartao
 
- no. do cartão
 
- nr carta 
- nr. carta
 
- numeri di scheda
 
- numero carta
 
- numero de cartao
 
- numero de carte
 
- numero de cartão
 
- numero de tarjeta

- numero della carta
 
- numero di carta
 
- numero di scheda
 
- numero do cartao
 
- numero do cartão
 
- numéro de carte
 
- nº carta
 
- nº de carte
 
- nº de la carte
 
- nº de tarjeta
 
- nº do cartao
 
- nº は cartão 
- nº. do cartão
 
- número de cartao
 
- número de cartão
 
- número de tarjeta
 
- número do cartao 
- scheda dell'assegno
 
- scheda dell'atmosfera
 
- scheda dell'atmosfera
 
- scheda della banca
 
- scheda di controllo
 
- scheda di debito
 
- scheda matrice
 
- schede dell'atmosfera
 
- schede di controllo
 
- schede di debito
 
- schede matrici
 
- scoprono la scheda
 
- scoprono le schede
 
- solo
 
- supporti di scheda
 
- supporto di scheda
 
- switch
 
- tarjeta atm
 
- tarjeta credito
 
- tarjeta de atm
 
- tarjeta de credito
 
- tarjeta de debito
 
- tarjeta debito
 
- tarjeta no

- tarjetahabiente
 
- tipo della scheda
 
- ufficio giapponese della 
- scheda
 
- v pay
 
- v 支払 
- visa
 
- visa plus
 
- visa electron
 
- visto
 
- visum
 
- vpay
   

#### <a name="keywordcardsecuritytermsdict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification 
- cardi la verifica
 
- cid
 
- 代金引換払い seg 
- 代金引換払い seguranca 
- 代金引換払い segurança 
- 代金引換払いの sicurezza 
- cod. seg
 
- cod. seguranca
 
- cod. segurança
 
- cod. sicurezza
 
- codice di sicurezza
 
- codice di verifica
 
- codigo
 
- codigo de seguranca
 
- codigo de segurança
 
- crittogramma
 
- cryptogram
 
- cryptogramme
 
- cv2 
- cvc
 
- cvc2 
- cvn
 
- cvv
 
- cvv2 
- cód seguranca 
- cód segurança 
- cód. seguranca
 
- cód. segurança
 
- código
 
- código de seguranca
 
- código de segurança
 
- de kaart controle
 
- geeft nr uit
 
- issue no
 
- issue number
 
- kaartidentificatienummer
 
- kreditkartenprufnummer
 
- kreditkartenprüfnummer
 
- kwestieaantal
 
- no. dell'edizione
 
- no. di sicurezza
 
- numero de securite
 
- numero de verificacao
 
- numero dell'edizione
 
- numero di identificazione della 
- scheda
 
- numero di sicurezza
 
- numero van veiligheid
 
- numéro de sécurité
 
- nº autorizzazione
 
- número de verificação
 
- perno il blocco
 
- pin block
 
- prufziffer
 
- prüfziffer
 
- security code
 
- security no
 
- security number
 
- sicherheits kode
 
- sicherheitscode
 
- sicherheitsnummer
 
- speldblok
 
- veiligheid nr
 
- veiligheidsaantal
 
- veiligheidscode
 
- veiligheidsnummer
 
- verfalldatum
 

#### <a name="keywordcardexpirationtermsdict"></a>Keyword_card_expiration_terms_dict

- ablauf
 
- data de expiracao
 
- data de expiração
 
- data del exp
 
- data di exp
 
- data di scadenza
 
- data em que expira
 
- data scad
 
- data scadenza
 
- date de validité
 
- datum afloop
 
- datum van exp
 
- de afloop
 
- espira
 
- espira
 
- exp date
 
- exp datum
 
- 有効期限 
- expire
 
- expires
 
- expiry
 
- fecha de expiracion
 
- fecha de venc
 
- gultig bis
 
- gultigkeitsdatum
 
- gültig bis
 
- gültigkeitsdatum
 
- la scadenza
 
- scadenza
 
- valable
 
- validade
 
- valido hasta
 
- valor
 
- venc
 
- vencimento
 
- vencimiento
 
- verloopt
 
- vervaldag
 
- vervaldatum
 
- vto
 
- válido hasta
 
   
## <a name="eu-drivers-license-number"></a>EU 運転免許証番号

詳細については、 [EU ドライバーのライセンス番号の機密性の高い情報の種類](eu-driver-s-license-number.md)を参照してください。
  
## <a name="eu-national-identification-number"></a>EU 国民 Id 番号

詳細については、 [EU 各国の識別番号の機密性の高い情報の種類](eu-national-identification-number.md)を参照してください。
  
## <a name="eu-passport-number"></a>EU パスポート番号

詳細については、 [EU のパスポート番号の機密性の高い情報の種類](eu-passport-number.md)を参照してください。
  
## <a name="eu-social-security-number-or-equivalent-id"></a>EU の社会保障番号またはそれと同等の ID

詳細については、 [EU の社会保障番号、または機密性の高い情報の種類のと同じ ID](eu-social-security-number-or-equivalent-id.md)を参照してください。
  
## <a name="eu-tax-identification-number"></a>EU 税 Id 番号

詳細については、 [EU の税 Id 番号の機密性の高い情報の種類](eu-tax-identification-number.md)を参照してください。
  
## <a name="finland-national-id"></a>フィンランドの国民 ID

### <a name="format"></a>形式

6 桁の数字、世紀を表す 1 桁の文字、3 桁の数字、1 桁のチェック ディジット

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。
- DDMMYY という形式の誕生日を示す 6 桁の数字 
- 世紀マーカー (「-」、「+」、または「a」) 
- 3 桁の個人識別番号 
- チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別あり)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_finnish_national_id がパターンに一致するコンテンツを検出した。
- Keyword_finnish_national_id のキーワードを検出した。
- チェックサムが渡される。

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

- Keyword_finnish_national_id
- 

Sosiaaliturvatunnus
- SOTU Henkilötunnus HETU
- Personbeteckning
- Personnummer
   
## <a name="finland-passport-number"></a>フィンランドのパスポート番号

9 つの文字と数字の 9 つの文字と数字の組み合わせのパターンの組み合わせを書式設定: 2 つの文字 (いない大文字小文字を区別) の 7 桁のチェックサムなしの定義 A DLP ポリシーは、75% の場合はこの種の機密情報を検出したことを確信で、300 文字の長さ: Regex_finland_passport_number の正規表現パターンに一致するコンテンツを検索します。Keyword_finland_passport_number からキーワードを検出するとします。<!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
 </Entity> Keyword_finland_passport_number Passport Passi のキーワード
   
## <a name="france-drivers-license-number"></a>フランスの運転免許証番号

### <a name="format"></a>形式

12 桁の数字

### <a name="pattern"></a>パターン

フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_french_drivers_license がパターンに一致するコンテンツを検出した。
- 次の条件のうち 1 つ以上に該当する:
- Keyword_french_drivers_license のキーワードを検出した。
- 関数 Func_eu_date が適切な日付形式の日付を検出した。

```
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordfrenchdriverslicense"></a>Keyword_french_drivers_license

- drivers licence
- drivers license
- driving licence

- ライセンスを推進
- 
permis de conduire
- 
licence number
- 
license number
- 
licence numbers
- 

license numbers

## <a name="france-national-id-card-cni"></a>フランスの国民識別カード (CNI)

### <a name="format"></a>形式

12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

なし
   
## <a name="france-passport-number"></a>フランスのパスポート番号

### <a name="format"></a>形式

9 桁の数字と文字

### <a name="pattern"></a>パターン

9 つの数字と文字:
- 2 桁の数字 
- 2 桁の文字 (大文字小文字の区別なし)  
- 5 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_fr_passport がパターンに一致するコンテンツを検出した。
- Keyword_passport のキーワードを検出した。

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number
- 
Passport No
- Passport #

- Passport#

- PassportID
- Passportno

- passportnumber

- パスポート
- パスポート番号

- パスポートのNum

- 
パスポート ＃
 
- Numéro de passeport
- 
Passeport n °
- Passeport Non

- Passeport #

- Passeport#

- PasseportNon
- 

Passeportn °

      
## <a name="france-social-security-number-insee"></a>フランスの社会保障番号 (INSEE)

### <a name="format"></a>形式

15 桁の数字

### <a name="pattern"></a>パターン

次のいずれかのパターンに一致する:
- 13 桁の数字が 2 桁の後にスペースの後に<br/>
または
- 15 桁の連続する数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。
- Func_french_insee または Func_fr_insee 関数は、パターンに一致するコンテンツを検索します。
- Keyword_fr_insee のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- Func_french_insee または Func_fr_insee 関数は、パターンに一致するコンテンツを検索します。
- Keyword_fr_insee のキーワードを検出しなかった。
- チェックサムが渡される。

```
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordfrinsee"></a>Keyword_fr_insee

- insee
- 
securité sociale
- 
securite sociale
- 
national id
- 
national identification
- 
numéro d'identité
- なし d'identité
- 
no. d'identité
- 
numero d'identite
- なし d'identite
- 
no. d'identite
- social security number

- 
social security code
- social insurance number
- 
le numéro d'identification nationale
- 
d'identité nationale
- 
numéro de sécurité sociale
- 
le code de la sécurité sociale
- 
numéro d'assurance sociale
- 
numéro de sécu
- 
code sécu
 
   
## <a name="german-drivers-license-number"></a>ドイツの運転免許証番号

### <a name="format"></a>形式

11 桁の数字と文字の組み合わせ

### <a name="pattern"></a>パターン

11 個の数字と文字 (大文字小文字を区別しない):
- 1 つの数字または文字 
- 2 桁の数字 
- 6 つの数字または文字 
- 1 桁の数字 
- 1 つの数字または文字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_german_drivers_license がパターンに一致するコンテンツを検出した。
- 次の条件のうち 1 つ以上に該当する:
    - Keyword_german_drivers_license_number のキーワードを検出した。
    - Keyword_german_drivers_license_collaborative のキーワードを検出した。
    - Keyword_german_drivers_license のキーワードを検出した。
- チェックサムが渡される。

```
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordgermandriverslicensenumber"></a>Keyword_german_drivers_license_number

- Führerschein
- 
Fuhrerschein
- Fuehrerschein
- 
Führerscheinnummer
- 
Fuhrerscheinnummer
- 
Fuehrerscheinnummer
- 
Führerschein-
 
- Fuhrerschein-
 
- Fuehrerschein-
 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein- Nr

- Fuhrerschein- Nr

- Fuehrerschein- Nr
 
- Führerschein- Klasse
 
- Fuhrerschein- Klasse
 
- Fuehrerschein- Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein- Nr
 
- Fuhrerschein- Nr
 
- Fuehrerschein- Nr
 
- Führerschein- Klasse
 
- Fuhrerschein- Klasse
 
- Fuehrerschein- Klasse 
- DL 
- DLS
- 
Driv Lic
 
- Driv Licen
 
- Driv License
- 
Driv Licenses
 
- Driv Licence
 
- Driv Licences
 
- Driv Lic
 
- Driver Licen
 
- ドライバー ライセンス 
- ドライバー ライセンス 
- Driver Licence
 
- Driver Licences
 
- ドライバー Lic 
- ドライバー Licen 
- 運転免許証番号 
- ドライバー ライセンス 
- ドライバー ライセンス 
- ドライバー ライセンス 
- ドライバーの Lic 
- Driver's Licen
 
- 運転免許証 
- 運転免許証 
- Driver's Licence
 
- Driver's Licences
 
- Driving Lic
 
- Driving Licen
 
- Driving License
 
- Driving Licenses
 
- Driving Licence

 
- Driving Licences

#### <a name="keywordgermandriverslicensecollaborative"></a>Keyword_german_drivers_license_collaborative

- 
Nr-Führerschein
 
- Nr-Fuhrerschein
 
- Nr-Fuehrerschein
 
- No-Führerschein
 
- No-Fuhrerschein
 
- No-Fuehrerschein
 
- N-Führerschein
 
- N-Fuhrerschein
 
- N-Fuehrerschein
- 
Nr-Führerschein
 
- Nr-Fuhrerschein
 
- Nr-Fuehrerschein
 
- No-Führerschein
 
- No-Fuhrerschein
 
- No-Fuehrerschein
 
- N-Führerschein
 
- N-Fuhrerschein
 
- N-Fuehrerschein 

#### <a name="keywordgermandriverslicense"></a>Keyword_german_drivers_license

- ausstellungsdatum
- 
ausstellungsort
- 
ausstellende behöde
- 
ausstellende behorde
- 

ausstellende behoerde
   
## <a name="german-passport-number"></a>ドイツのパスポート番号

### <a name="format"></a>形式

10 桁の数字または文字

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。
- 最初の文字は 1 桁の数字、またはこのセット (C、F、G、H、J、K) からの 1 文字 
- 3 桁の数字 
- 数字またはこの文字セット (C、H、J から N、P、R、T、V から Z) から 5 個 
- 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_german_passport がパターンに一致するコンテンツを検出した。
- 5 つのキーワード リストのうちいずれかのキーワードを検索した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_german_passport_data がパターンに一致するコンテンツを検出した。
- 5 つのキーワード リストのうちいずれかのキーワードを検索した。
- チェックサムが渡される。

```
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordgermanpassport"></a>Keyword_german_passport

- reisepass
- 
reisepasse
- 
reisepassnummer
- passport
- 

passports

#### <a name="keywordgermanpassportcollaborative"></a>Keyword_german_passport_collaborative

- geburtsdatum
- ausstellungsdatum
- 
ausstellungsort

#### <a name="keywordgermanpassportnumber"></a>Keyword_german_passport_number

いいえ-Reisepass-Reisepass Nr

#### <a name="keywordgermanpassport1"></a>Keyword_german_passport1

Reisepass-Nr


#### <a name="keywordgermanpassport2"></a>Keyword_german_passport2

bnationalit.t
   
## <a name="germany-identity-card-number"></a>ドイツの身分証明書番号

### <a name="format"></a>形式

1 2010 年 11 月以降: 9 つの文字と数字

31 10 月 2010: 10 桁までの 1 年 1987年 4 月から

### <a name="pattern"></a>パターン

2010 年 11 月 1 日以降:
- 1 文字 (大文字小文字を区別しない) 
- 8 桁の数字

31 2010 年 10 月までの 1 年 1987年 4 月: から
- 10 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_germany_id_card がパターンに一致するコンテンツを検出した。
- Keyword_germany_id_card のキーワードを検出した。

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordgermanyidcard"></a>Keyword_germany_id_card

- Identity Card
- ID
- Identification
- Personalausweis
- Identifizierungsnummer
- Ausweis
- Identifikation
   
## <a name="greece-national-id-card"></a>ギリシャの国民識別カード

### <a name="format"></a>形式

7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ

### <a name="pattern"></a>パターン

7 桁の文字と数字 (従来の形式):
- 1 桁の文字 (ギリシャ語のアルファベット文字)  
- ダッシュ 
- 6 桁の数字

8 桁の文字と数字 (現在の形式):
- ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字  
- ダッシュ 
- 6 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_greece_id_card がパターンに一致するコンテンツを検出した。
- Keyword_greece_id_card のキーワードを検出した。

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordgreeceidcard"></a>Keyword_greece_id_card

- Greek identity Card
- Tautotita
- Δελτίο αστυνομικής ταυτότητας
- Ταυτότητα
   
## <a name="hong-kong-identity-card-hkid-number"></a>香港の ID カード (HKID) 番号

### <a name="format"></a>形式

8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能

### <a name="pattern"></a>パターン

8 ～ 9 桁の文字の組み合わせ:
- 1 ～ 2 桁の文字 (大文字小文字の区別なし)  
- 6 桁の数字 
- チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_hong_kong_id_card がパターンに一致するコンテンツを検出した。
- Keyword_hong_kong_id_card のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_hong_kong_id_card がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordhongkongidcard"></a>Keyword_hong_kong_id_card

- 香港の id カード
- HKIDC
- id カード
- Identity card
- 香港の id カード
- 香港 id
- 香港身份證

- 香港永久性居民身份證

- 身份證

- 身份証
- 身分證 
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證

- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證

- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証
   
## <a name="india-permanent-account-number-pan"></a>インドの永久口座番号 (PAN)

### <a name="format"></a>形式

10 桁の文字または数字

### <a name="pattern"></a>パターン

10 桁の文字または数字:
- 5 桁の文字 (大文字小文字の区別なし)  
- 4 桁の数字 
- チェック ディジットとして機能する 1 桁のアルファベット文字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_india_permanent_account_number がパターンに一致するコンテンツを検出した。
- Keyword_india_permanent_account_number のキーワードを検出した。
- チェックサムが渡される。

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordindiapermanentaccountnumber"></a>Keyword_india_permanent_account_number

- Permanent Account Number
 
- PAN
 
   
## <a name="india-unique-identification-aadhaar-number"></a>インドの固有識別 (Aadhaar) 番号

### <a name="format"></a>形式

省略可能なスペースまたはハイフンを含む 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:
- 4 桁の数字 
- スペースまたはハイフン 1 つ (省略可能)  
- 4 桁の数字 
- スペースまたはハイフン 1 つ (省略可能)  
- 最後の数字はチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーとは、85% をこの種類の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_india_aadhaar 関数は、パターンに一致するコンテンツを検索します。。Keyword_india_aadhar からキーワードを検出するとします。チェックサムが渡されます。DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_india_aadhaar 関数は、パターンに一致するコンテンツを検索します。。チェックサムが渡されます。<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity>

### <a name="keywords"></a>キーワード
   
#### <a name="keywordindiaaadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>インドネシアの身分証明書 (KTP) 番号

### <a name="format"></a>形式

省略可能なピリオドを含む 16 桁の数字

### <a name="pattern"></a>パターン

16 桁の数字:
- 2 桁の行政区コード  
- ピリオド 1 つ (省略可能)  
- 2 桁の行政区または市コード  
- 2 桁の分区コード  
- ピリオド 1 つ (省略可能)  
- DDMMYY の形式の生年月日を表す 6 桁の数字  
- ピリオド 1 つ (省略可能)  
- 4 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_indonesia_id_card がパターンに一致するコンテンツを検出した。
- Keyword_indonesia_id_card のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_indonesia_id_card がパターンに一致するコンテンツを検出した。

```
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード
   
#### <a name="keywordindonesiaidcard"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk
 
- Nomor Induk Kependudukan
 
   
## <a name="international-banking-account-number-iban"></a>国際銀行口座番号 (IBAN)

### <a name="format"></a>形式

国コード (2 文字)、チェック ディジット (2 桁)、bban 番号 (最大 30 文字)

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。

- 2 文字の国コード
- 2 桁のチェック ディジット (省略可能なスペースが続く)  
- 4 個の文字または数字で構成される 1 から 7 個のグループ (スペースで区切ることができる)
- 1 ～ 3 個の文字または数字

各国の形式は多少異なります。IBAN 機密情報の型は、次の 60 か国をカバーしています。

ad、ae、al、at、az、ba、be、bg、bh、ch、cr、cy、cz、de、dk、do、ee、es、fi、fo、fr、gb、ge、gi、gl、gr、hr、hu、ie、il、is、it、kw、kz、lb、li、lt、lu、lv、mc、md、me、mk、mr、mt、mu、nl、no、pl、pt、ro、rs、sa、se、si、sk、sm、tn、tr、vg

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_iban がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

なし

   
## <a name="ip-address"></a>IP アドレス

### <a name="format"></a>形式

#### <a name="ipv4"></a>IPv4:
書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン

#### <a name="ipv6"></a>IPv6:
 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン

### <a name="pattern"></a>パターン

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。
- Keyword_ipaddress のキーワードを検出しなかった。

IPv4 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。
- Keyword_ipaddress のキーワードを検出した。

IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。
- Keyword_ipaddress のキーワードを検出しなかった。

```
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordipaddress"></a>Keyword_ipaddress

- IP (このキーワードでは大文字と小文字が区別されます)
- ip address
 
- ip addresses
- internet protocol
- 
IP-כתובת ה
 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a>病気 (ICD 10 CM) の国際的な分類

### <a name="format"></a>形式

辞書

### <a name="pattern"></a>パターン

キーワード

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- Dictionary_icd_10_cm からキーワードを検出するとします。

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

キーワード

Dictionary_icd_10_cm キーワード辞書からすべての用語をに基づいて[病気の分類を国際、10 分のリビジョン、臨床変更 (ICD 10 CM)](https://go.microsoft.com/fwlink/?linkid=852604)。このタイプは、用語、保険のコードではないのだけを検索します。

   
## <a name="international-classification-of-diseases-icd-9-cm"></a>病気 (ICD 9 CM) の国際的な分類

### <a name="format"></a>形式

辞書

### <a name="pattern"></a>パターン

キーワード

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- Dictionary_icd_9_cm からキーワードを検出するとします。

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

Dictionary_icd_9_cm キーワード辞書からすべての用語をに基づいて[病気の分類を国際、9 番目のリビジョン、臨床変更 (ICD 9 CM)](https://go.microsoft.com/fwlink/?linkid=852605)。このタイプは、用語、保険のコードではないのだけを検索します。
   
## <a name="ireland-personal-public-service-pps-number"></a>アイルランドの個人公共サービス (PPS) 番号

### <a name="format"></a>形式

(2012 年 5 年 12 月 31日) までの古い形式:
- 7 桁の数字の後に 1 ～ 2 桁の文字  

新しい形式 (1 年 2013年 1 月と後)。
- 7 桁の数字の後に 2 桁の文字

### <a name="pattern"></a>パターン

(2012 年 5 年 12 月 31日) までの古い形式:
- 7 桁の数字  
- 1 ～ 2 桁の文字 (大文字小文字の区別なし)  

新しい形式 (1 年 2013年 1 月と後)。
- 7 桁の数字  
- チェック ディジットとして機能する 1 桁のアルファベット文字 (大文字小文字の区別なし)  
- 文字「A」または「H」 (大文字小文字の区別なし)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_ireland_pps がパターンに一致するコンテンツを検出した。
- 次のいずれかの条件に該当する:
    - Keyword_ireland_pps のキーワードを検出した。
    - 関数 Func_eu_date が適切な日付形式の日付を検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_ireland_pps がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordirelandpps"></a>Keyword_ireland_pps

- Personal Public Service Number 
 
- PPS Number
 
- PPS Num
 
- PPS No.
 
- PPS #
 
- PPS # 
- PPSN
 
- Public Services Card
 
- Uimhir Phearsanta Seirbhíse Poiblí
 
- Uimh.PSP
 
- PSP
 
   
## <a name="israel-bank-account-number"></a>イスラエルの銀行口座番号

### <a name="format"></a>形式

13 桁の数字

### <a name="pattern"></a>パターン

書式設定されている場合:
- 2 桁の数字 
- ダッシュ 
- 3 桁の数字 
- ダッシュ 
- 8 桁の数字

書式設定されていない場合:
- 	13 桁の連続する数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_israel_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_israel_bank_account_number のキーワードを検出した。

```
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordisraelbankaccountnumber"></a>Keyword_israel_bank_account_number

- Bank Account Number
 
- Bank Account
 
- Account Number
 
- מספר חשבון בנק
 
   
## <a name="israel-national-id"></a>イスラエルの国民 ID

### <a name="format"></a>形式

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の連続する数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_israeli_national_id_number がパターンに一致するコンテンツを検出した。
- Keyword_Israel_National_ID のキーワードを検出した。
- チェックサムが渡される。

```
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordisraelnationalid"></a>Keyword_Israel_National_ID

- מספר זהות
 
- National ID Number
   
## <a name="italy-drivers-license-number"></a>イタリアの運転免許証番号

### <a name="format"></a>形式

10 桁の文字と数字の組み合わせ

### <a name="pattern"></a>パターン

- 10 個の文字と数字の組み合わせ:
- 1 文字 (大文字小文字を区別しない) 
- 文字 "A" または "V" (大文字小文字を区別しない) 
- 7 つの文字 (大文字小文字を区別しない)、数字、またはアンダースコア文字 
- 1 文字 (大文字小文字を区別しない)

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_italy_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_italy_drivers_license_number のキーワードを検出した。

```
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyworditalydriverslicensenumber"></a>Keyword_italy_drivers_license_number

- numero di patente di guida
 
- patente di guida
 
   
## <a name="japan-bank-account-number"></a>日本の銀行口座番号

### <a name="format"></a>形式

7 桁または 8 桁の数字

### <a name="pattern"></a>パターン

銀行口座番号:
- 7 桁または 8 桁の数字
- 銀行口座支店コード:
- 4 桁の数字 
- スペースまたはダッシュ (省略可能) 
- 3 桁の数字

チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。
- Keyword_jp_bank_account のキーワードを検出した。
- 次のいずれかの条件に該当する:
- 関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。
- Keyword_jp_bank_branch_code のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。
- Keyword_jp_bank_account のキーワードを検出した。

```
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordjpbankaccount"></a>Keyword_jp_bank_account

- Checking Account Number
 
- Checking Account
 
- Checking Account #
 
- Checking Acct Number
 
- Checking Acct #
 
- Checking Acct No.
 
- Checking Account No.
 
- Bank Account Number
 
- Bank Account
 
- Bank Account #
 
- Bank Acct Number
 
- Bank Acct #
 
- Bank Acct No.
 
- Bank Account No.
 
- Savings Account Number
 
- 預金/貯蓄口座 
- Savings Account #
 
- Savings Acct Number
 
- Savings Acct #
 
- Savings Acct No.
 
- Savings Account No.
 
- Debit Account Number
 
- Debit Account
 
- Debit Account #
 
- Debit Acct Number
 
- Debit Acct #
 
- Debit Acct No.
 
- Debit Account No.
 
- 口座番号を当座預金口座の確認
 
- ＃アカウントの確認、勘定番号の確認
 
- ＃勘定の確認
 
- 勘定番号の確認
 
- 口座番号の確認
 
- 銀行口座番号 
- 銀行口座 
- 銀行口座＃
 
- 銀行の勘定番号
 
- 銀行のacct＃
 
- 銀行の勘定いいえ
 
- 銀行口座番号
- 
普通預金口座番号
 
- 預金口座
 
- 貯蓄口座＃
 
- 貯蓄勘定の数
 
- 貯蓄勘定＃
 
- 貯蓄勘定番号
 
- 普通預金口座番号
 
- 引き落とし口座番号
 
- 口座番号 
- 口座番号＃
 
- デビットのacct番号
 
- デビット勘定＃
 
- デビットACCTの番号
 
- デビット口座番号
 

#### <a name="keywordjpbankbranchcode"></a>Keyword_jp_bank_branch_code

Otemachi

## <a name="japan-drivers-license-number"></a>日本の運転免許証番号

### <a name="format"></a>形式

12 桁の数字

### <a name="pattern"></a>パターン

12 桁の連続する数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_jp_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_jp_drivers_license_number のキーワードを検出した。

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordjpdriverslicensenumber"></a>Keyword_jp_drivers_license_number

- dl# 
- DL # 
- dls# 
- DL # 
- driver license 
- driver licenses 
- drivers license 
- driver's license 
- drivers licenses 
- driver's licenses 
- driving licence
 
- lic# 
- LIC # 
- lics# 
- 状態 id 
- state identification
 
- state identification number
 
- 低所得国＃
 
- 免許証 
- 状態ID
- 
状態の識別
 
- 状態の識別番号
 
- 運転免許 
- 運転免許証 
- 運転免許証番号 
   
## <a name="japan-passport-number"></a>日本のパスポート番号

### <a name="format"></a>形式

2 桁の文字の後に 7 桁の数字

### <a name="pattern"></a>パターン

2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_jp_passport がパターンに一致するコンテンツを検出した。
- Keyword_jp_passport のキーワードを検出した。

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordjppassport"></a>Keyword_jp_passport

- パスポート
 
- パスポート番号
 
- パスポートのNum
 
- パスポート＃
 
   
## <a name="japan-resident-registration-number"></a>日本の住民登録番号

### <a name="format"></a>形式

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の連続する数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_jp_resident_registration_number がパターンに一致するコンテンツを検出した。
- Keyword_jp_resident_registration_number のキーワードを検出した。

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordjpresidentregistrationnumber"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Resident Register Number
 
- Residents Basic Registry Number
 
- Resident Registration No.
 
- Resident Register No.
 
- Residents Basic Registry No.
 
- Basic Resident Register No.
 
- 住民登録番号、登録番号をレジデント
 
- 住民基本登録番号、登録番号
 
- 住民基本レジストリ番号を常駐
 
- 登録番号を常駐住民基本台帳登録番号
 

   
## <a name="japan-social-insurance-number-sin"></a>日本の社会保険番号 (SIN)

### <a name="format"></a>形式

7～ 12 桁の数字

### <a name="pattern"></a>パターン

7 ～ 12 桁の数字:
- 4 桁の数字 
- ハイフン (省略可能) 
- 6 桁または
- 7 ～ 12 桁の連続する数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_jp_sin がパターンに一致するコンテンツを検出した。
- Keyword_jp_sin のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_jp_sin_pre_1997 がパターンに一致するコンテンツを検出した。
- Keyword_jp_sin のキーワードを検出した。

```
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordjpsin"></a>Keyword_jp_sin

- Social Insurance No.
 
- Social Insurance Num
 
- Social Insurance Number
 
- 社会保険のテンキー
 
- 社会保険番号
 

## <a name="japanese-residence-card-number"></a>居住地の日本語のカード番号

### <a name="format"></a>形式

12 の文字と数字

### <a name="pattern"></a>パターン

12 の文字と数字の場合。
- 2 桁の文字 (大文字小文字の区別なし) 
- 8 桁の数字 
- 2 桁の文字 (大文字小文字の区別なし) 

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- Regex_jp_residence_card_number の正規表現パターンに一致するコンテンツを検索します。
- Keyword_jp_residence_card_number からキーワードを検出するとします。

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordjpresidencecardnumber"></a>Keyword_jp_residence_card_number

- 居住カードの数
- 住居なしをカードします。
- 居住地のカード番号
- 在留カード番号
   
## <a name="malaysia-id-card-number"></a>マレーシアの ID カード番号

### <a name="format"></a>形式

省略可能なハイフンを含む 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:
- YYMMDD の形式の生年月日を表す 6 桁の数字  
- ハイフン 1 つ (省略可能)  
- 出生地コードを表す 2 桁の文字  
- ハイフン 1 つ (省略可能)  
- 3 桁のランダムな数字  
- 1 桁の性別コード

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_malaysia_id_card_number がパターンに一致するコンテンツを検出した。
- Keyword_malaysia_id_card_number のキーワードを検出した。

```
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード
   
#### <a name="keywordmalaysiaidcardnumber"></a>Keyword_malaysia_id_card_number

- アプリケーションのデジタル カード
- i/c
- i/c なし
- ic
- ic なし
- id カード
- id カード
- Identity card
- k と p
- k と p なし
- kad akuan diri
- kad aplikasi のデジタル
- kad pengenalan マレーシア
- kp
- kp なし
- mykad
- mykas
- mykid
- mypr
- mytentera
- マレーシアの id カード
- マレーシアの id カード
- nric
- 個人の id カード
   
## <a name="netherlands-citizens-service-bsn-number"></a>オランダの市民サービス (BSN) 番号

### <a name="format"></a>形式

省略可能なハイフンを含む 8 ～ 9 桁の数字

### <a name="pattern"></a>パターン

8 ～ 9 桁の数字:
- 3 桁の数字 
- スペース 1 つ (省略可能)  
- 3 桁の数字 
- スペース 1 つ (省略可能)  
- 2 ～ 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_netherlands_bsn がパターンに一致するコンテンツを検出した。
- Keyword_netherlands_bsn のキーワードを検出した。
- 関数 Func_eu_date2 が適切な日付形式の日付を検出した。
- チェックサムが渡される。

```
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordnetherlandsbsn"></a>Keyword_netherlands_bsn

- Citizen service number
 
- BSN

 
- Burgerservicenummer
 
- Sofinummer
 
- Persoonsgebonden nummer
 
- Persoonsnummer
    

   
## <a name="new-zealand-ministry-of-health-number"></a>ニュージーランドの保健省番号

### <a name="format"></a>形式

3 桁の文字、スペース 1 つ (省略可能)、4 桁の数字

### <a name="pattern"></a>パターン

3 つの文字を (大文字小文字を区別)、スペース (省略可能) 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。
- Keyword_nz_terms のキーワードを検出した。
- チェックサムが渡される。

```
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

キーワード

Keyword_nz_terms

- NHI
 
- ニュージーランド 
- 正常性 
- treatment
 
   
## <a name="norway-identification-number"></a>ノルウェーの識別番号

### <a name="format"></a>形式

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字:
- DDMMYY の形式の生年月日を表す 6 桁の数字  
- 3 桁の個人番号  
- 2 桁のチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_norway_id_number がパターンに一致するコンテンツを検出した。
- Keyword_norway_id_number のキーワードを検出した。
- チェックサムが渡される。
- DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_norway_id_numbe がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordnorwayidnumber"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- Identification
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-id-number"></a>フィリピンの汎用多目的 ID 番号

### <a name="format"></a>形式

ハイフンで区切られた 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:
- 4 桁の数字 
- ハイフン 1 つ  
- 7 桁の数字  
- ハイフン 1 つ  
- 1 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_philippines_unified_id がパターンに一致するコンテンツを検出した。
- Keyword_philippines_id のキーワードを検出した。

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード
   
#### <a name="keywordphilippinesid"></a>Keyword_philippines_id

- Unified Multi-Purpose ID
 
- UMID
 
- Identity Card 
- Pinag-isang Multi-Layunin ID
   
## <a name="poland-identity-card"></a>ポーランドの ID カード

### <a name="format"></a>形式

3 桁の文字と 6 桁の数字

### <a name="pattern"></a>パターン

3 桁の文字 (大文字小文字の区別なし) の後に 6 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_polish_national_id 関数は、パターンに一致するコンテンツを検索します。。Keyword_polish_national_id_passport_number からキーワードを検出するとします。チェックサムが渡されます。

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordpolishnationalidpassportnumber"></a>Keyword_polish_national_id_passport_number

- Dowód osobisty
- 数値 dowodu osobistego
- Nazwa 私の数値 dowodu osobistego
- Nazwa に nr dowodu osobistego
- Nazwa i nr dowodu tożsamości

- Dowód Tożsamości

- dow. os.


   
## <a name="poland-national-id-pesel"></a>ポーランドの国民 ID (PESEL)

### <a name="format"></a>形式

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の連続する数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。
- Keyword_pesel_identification_number のキーワードを検出した。
- チェックサムが渡される。

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordpeselidentificationnumber"></a>Keyword_pesel_identification_number

- Nr PESEL
- PESEL   

   
## <a name="poland-passport"></a>ポーランドのパスポート

### <a name="format"></a>形式

2 桁の文字と 7 桁の数字

### <a name="pattern"></a>パターン

2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_polish_passport_number がパターンに一致するコンテンツを検出した。
- Keyword_polish_national_id_passport_number のキーワードを検出した。
- チェックサムが渡される。

```
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordpolishnationalidpassportnumber"></a>Keyword_polish_national_id_passport_number

- 数値 paszportu
- Paszportu nr。
- Paszport

   
## <a name="portugal-citizen-card-number"></a>ポルトガルの市民カード番号

### <a name="format"></a>形式

8 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_portugal_citizen_card がパターンに一致するコンテンツを検出した。
- Keyword_portugal_citizen_card のキーワードを検出した。

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordportugalcitizencard"></a>Keyword_portugal_citizen_card

- Citizen Card
- National ID Card
- CC
- Cartão de Cidadão
- Bilhete de Identidade
   
## <a name="saudi-arabia-national-id"></a>サウジアラビアの国民 ID

### <a name="format"></a>形式

10 桁の数字

### <a name="pattern"></a>パターン

10 桁の連続する数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_saudi_arabia_national_id がパターンに一致するコンテンツを検出した。
- Keyword_saudi_arabia_national_id のキーワードを検出した。

```
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordsaudiarabianationalid"></a>Keyword_saudi_arabia_national_id

- Identification Card
 
- I card number
 
- ID number
 
- الوطنية الهوية بطاقة رقم
 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>シンガポールの国民登録 ID カード (NRIC) 番号

### <a name="format"></a>形式

9 桁の文字と数字

### <a name="pattern"></a>パターン

- 9 桁の文字と数字:
- 文字「F」、「G」、「S」、または「T」 (大文字小文字の区別なし)  
- 7 桁の数字  
- 1 桁のアルファベットのチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_singapore_nric がパターンに一致するコンテンツを検出した。
- Keyword_singapore_nric のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_singapore_nric がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード
   
#### <a name="keywordsingaporenric"></a>Keyword_singapore_nric

- National Registration Identity Card
 
- Identity Card Number
 
- NRIC
 
- IC
 
- Foreign Identification Number
 
- FIN
 
- 身份证  
- 身份證
 
   
## <a name="south-africa-identification-number"></a>南アフリカの識別番号

### <a name="format"></a>形式

省略可能なスペースを含む 13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:
- YYMMDD の形式の生年月日を表す 6 桁の数字  
- 4 桁の数字 
- 1 桁の市民標識  
- 数字「8」または「9」  
- チェックサム ディジットとして機能する 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_south_africa_identification_number がパターンに一致するコンテンツを検出した。
- Keyword_south_africa_identification_number のキーワードを検出した。
- チェックサムが渡される。

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード
   
#### <a name="keywordsouthafricaidentificationnumber"></a>Keyword_south_africa_identification_number

- Identity card
- ID
- Identification 
   
## <a name="south-korea-resident-registration-number"></a>韓国の住民登録番号

### <a name="format"></a>形式

ハイフンを 1 つ含む 13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:
- YYMMDD の形式の生年月日を表す 6 桁の数字  
- ハイフン 1 つ  
- 世紀と性別によって決まる 1 桁の数字  
- 4 桁の出生地域コード  
- 先頭の番号が同一である人々を区別するための 1 桁の数字  
- 1 桁のチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_south_korea_resident_number がパターンに一致するコンテンツを検出した。
- Keyword_south_korea_resident_number のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_south_korea_resident_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード
   
#### <a name="keywordsouthkorearesidentnumber"></a>Keyword_south_korea_resident_number

- National ID card
 
- Citizen's Registration Number
 
- Jumin deungnok beonho
 
- RRN
 
- 주민등록번호
   
## <a name="spain-social-security-number-ssn"></a>スペインの社会保障番号 (SSN)

### <a name="format"></a>形式

11 ～ 12 桁の数字

### <a name="pattern"></a>パターン

11-12 桁の数字。
- 2 桁の数字 
- スラッシュ (省略可能) 
- 7 ～ 8 桁の数字 
- スラッシュ (省略可能) 
- 2 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

なし
   
## <a name="sweden-national-id"></a>スウェーデンの国民 ID

### <a name="format"></a>形式

10 桁または 12 桁の数字とオプションの区切り記号 1 つ

### <a name="pattern"></a>パターン

10 桁または 12 桁の数字と省略可能な区切り記号:
- 2 ～ 4 桁の数字 (省略可能) 
- YYMMDD という日付形式の 6 桁の数字 
- 区切り文字「-」または「+」(省略可能)、および
- 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_swedish_national_identifier がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

なし
   
## <a name="sweden-passport-number"></a>スウェーデンのパスポート番号

### <a name="format"></a>形式

8 桁の数字

### <a name="pattern"></a>パターン

8 桁の連続する数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_sweden_passport_number がパターンに一致するコンテンツを検出した。
- 次のいずれかの条件に該当する:
    - Keyword_passport のキーワードを検出した。
    - Keyword_sweden_passport のキーワードを検出した。

```
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード
   
#### <a name="keywordswedenpassport"></a>Keyword_sweden_passport

- visa requirements
 
- Alien Registration Card
 
- Schengen visas
 
- Schengen visa
 
- Visa Processing
 
- Visa Type
 
- Single Entry
 
- Multiple Entry
 
- G3 Processing Fees

 

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number 
- 
Passport No 
- Passport #
 
- Passport#
 
- PassportID 
- Passportno
 
- passportnumber
 
- パスポート 
- パスポート番号
 
- パスポートのNum
 
- パスポート＃
 
- Numéro de passeport 
- 
Passeport n ° 
- Passeport Non
 
- Passeport #
 
- Passeport#
 
- PasseportNon 
- Passeportn °
 
   
## <a name="swift-code"></a>SWIFT コード

### <a name="format"></a>形式

4 桁の文字の後に 5 ～ 31 桁の文字または数字

### <a name="pattern"></a>パターン

4 文字の後に 5 ～ 31 個の文字または数字:
- 4 文字の銀行コード (大文字小文字を区別しない) 
- 省略可能なスペース 
- 4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN)) 
- 省略可能なスペース 
- 1 ～ 3 個の文字または数字 (BBAN の残りの部分)

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_swift がパターンに一致するコンテンツを検出した。
- Keyword_swift のキーワードを検出した。

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード
   
#### <a name="keywordswift"></a>Keyword_swift

- international organization for standardization 9362
 
- iso 9362
 
- iso9362 
- swift\# 
- swiftcode
 
- swiftnumber
 
- swiftroutingnumber
 
- swift コード 
- swift number #
 
- swift routing number
 
- bic number
 
- bic code
 
- bic\# 
- bic\# 
- bank identifier code
 
- 標準化9362 
- 迅速＃
 
- SWIFTコード
 
- SWIFT番号
 
- 迅速なルーティング番号
 
- BIC番号
 
- BICコード
 
- 銀行識別コードのための国際組織
 
- Organisation internationale de normalisation 9362
 
- rapide\# 
- code SWIFT
 
- le numéro de swift
 
- swift numéro d'acheminement
 
- le numéro BIC
 
- \#BIC 
- code identificateur de banque
 
   
## <a name="taiwan-national-id"></a>台湾の国民 ID

### <a name="format"></a>形式

1 桁の文字 (アルファベット) の後に 9 桁の数字

### <a name="pattern"></a>パターン

1 文字 の後に 9 桁の数字:
- 1 文字 (英語、大文字小文字を区別しません) 
- 数字の「1」または「2」 
- 8 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。
- Keyword_taiwanese_national_id のキーワードを検出した。
- チェックサムが渡される。

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordtaiwanesenationalid"></a>Keyword_taiwanese_national_id

- 身份證字號
 
- 身份證
 
- 身份證號碼
 
- 身份證號
 
- 身分證字號
 
- 身分證  
- 身分證號碼
 
- 身份證號
 
- 身分證統一編號
 
- 國民身分證統一編號
 
- 簽名
 
- 蓋章
 
- 簽名或蓋章

 
- 簽章   
   
## <a name="taiwan-passport-number"></a>台湾のパスポート番号

### <a name="format"></a>形式

- 生体認証パスポート番号: 9 桁の数字
- 非生体認証パスポート番号: 9 桁の数字

### <a name="pattern"></a>パターン
生体認証パスポートの番号:
- 数字「3」  
- 8 桁の数字

非生体認証パスポートの番号:
- 9 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_taiwan_passport がパターンに一致するコンテンツを検出した。
- Keyword_taiwan_passport のキーワードを検出した。

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordtaiwanpassport"></a>Keyword_taiwan_passport

- ROC passport number
 
- パスポート番号 
- パスポートなし 
- Passport Num
 
- Passport #
 
- 护照
 
- 中華民國護照
 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>台湾の在留証明書 (ARC/TARC) 番号

### <a name="format"></a>形式

10 桁の文字と数字

### <a name="pattern"></a>パターン

10 桁の文字と数字:
- 2 桁の文字 (大文字小文字の区別なし)  
- 8 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_taiwan_resident_certificate がパターンに一致するコンテンツを検出した。
- Keyword_taiwan_resident_certificate のキーワードを検出した。

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordtaiwanresidentcertificate"></a>Keyword_taiwan_resident_certificate

- Resident Certificate
 
- 常駐の証明書 
- Resident Cert.
 
- Id カード 
- Alien Resident Certificate
 
- ARC
 
- Taiwan Area Resident Certificate
 
- TARC
 
- 居留證
 
- 外僑居留證
 
- 台灣地區居留證
 

## <a name="thai-population-identification-code"></a>タイの人口の識別コード

### <a name="format"></a>形式

13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:
- 最初の桁は 0 または 9 ではありません。 
- 12 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_Thai_Citizen_Id では、パターンに一致するコンテンツを検索します。
- Keyword_Thai_Citizen_Id からキーワードを検出するとします。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_Thai_Citizen_Id では、パターンに一致するコンテンツを検索します。

```
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordthaicitizenid"></a>Keyword_Thai_Citizen_Id

- ID Number
- 識別番号
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>トルコ語の国際識別番号

### <a name="format"></a>形式

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_Turkish_National_Id では、パターンに一致するコンテンツを検索します。
- Keyword_Turkish_National_Id からキーワードを検出するとします。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_Turkish_National_Id では、パターンに一致するコンテンツを検索します。

```
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordturkishnationalid"></a>Keyword_Turkish_National_Id

- TC Kimlik なし
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık なし

## <a name="uk-drivers-license-number"></a>英国の運転免許証番号

### <a name="format"></a>形式

指定の形式で組み合わせた 18 桁の文字と数字

### <a name="pattern"></a>パターン

18 個の文字と数字:
- 5 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり) 
- 1 桁の数字 
- 誕生日を示す DDMMY という日付形式の 5 桁の数字 
- 2 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり) 
- 5 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_uk_drivers_license がパターンに一致するコンテンツを検出した。
- Keyword_uk_drivers_license のキーワードを検出した。
- チェックサムが渡される。

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordukdriverslicense"></a>Keyword_uk_drivers_license

- DVLA
 
- light vans
 
- quadbikes
 
- motor cars
 
- 125cc 
- sidecar
 
- tricycles
 
- motorcycles
 
- photocard licence
 
- learner drivers
 
- licence holder
 
- licence holders
 
- driving licences
 
- driving licence
 
- dual control car
 
   
## <a name="uk-electoral-roll-number"></a>英国の選挙登録番号

### <a name="format"></a>形式

2 桁の文字の後に 1 ～ 4 桁の数字

### <a name="pattern"></a>パターン

2 桁の文字 (大文字小文字の区別なし) の後に 1 ～ 4 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_uk_electoral がパターンに一致するコンテンツを検出した。
- Keyword_uk_electoral のキーワードを検出した。

```
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordukelectoral"></a>Keyword_uk_electoral

- council nomination
 
- nomination form
 
- electoral register

 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>英国の国民健康保険番号

### <a name="format"></a>形式

スペースで区切られた 10 ～ 17 桁の数字

### <a name="pattern"></a>パターン

10 ～ 17 桁の数字:
- 3 桁または 10 桁の数字 
- スペース 
- 3 桁の数字 
- スペース 
- 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_uk_nhs_number がパターンに一致するコンテンツを検出した。
- 次のいずれかの条件に該当する:
    - Keyword_uk_nhs_number のキーワードを検出した。
    - Keyword_uk_nhs_number1 のキーワードを検出した。
    - Keyword_uk_nhs_number_dob のキーワードを検出した。
- チェックサムが渡される。

```
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード
   
#### <a name="keyworduknhsnumber"></a>Keyword_uk_nhs_number

- national health service
 
- nhs
 
- health services authority

 
- health authority

#### <a name="keyworduknhsnumber1"></a>Keyword_uk_nhs_number1

- patient id
 
- patient identification
 
- patient no

 
- patient number

#### <a name="keyworduknhsnumberdob"></a>Keyword_uk_nhs_number_dob

- GP 
- DOB
 
- D.O.B 
- Date of Birth
 
- Birth Date
 
   
## <a name="uk-national-insurance-number-nino"></a>英国の国民保険番号 (NINO)

### <a name="format"></a>形式

7 文字またはスペースまたはハイフンで区切られた 9 の文字

### <a name="pattern"></a>パターン

2 つの可能なパターン:

- 2 つの文字 (有効な NINOs では、特定の文字のみを使用して、このプレフィックスは、このパターンを検証します大文字と小文字を区別しない)。
- 6 桁の数字
- どちらか '、' 'B'、'C'、または必要がある ' (などの接頭辞、のみ特定の文字が許可、サフィックスのない大文字小文字を区別)

または

- 2 つの文字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- どちらか '、'、'B'、'C'、または必要がある '

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_uk_nino がパターンに一致するコンテンツを検出した。
- Keyword_uk_nino のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_uk_nino がパターンに一致するコンテンツを検出した。
- Keyword_uk_nino のキーワードを検出しなかった。

```
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyworduknino"></a>Keyword_uk_nino

- national insurance number
 
- national insurance contributions
 
- protection act
 
- insurance
 
- social security number
 
- insurance application
 
- medical application
 
- social insurance
 
- medical attention
 
- 社会保障 
- great britain
 
- insurance
    
   
## <a name="us--uk-passport-number"></a>米国/英国のパスポート番号

### <a name="format"></a>形式

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の連続する数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。
- Keyword_passport のキーワードを検出した。

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number 
- 
Passport No 
- Passport #
 
- Passport#
 
- PassportID 
- Passportno
 
- passportnumber
 
- パスポート 
- パスポート番号
 
- パスポートのNum
 
- パスポート＃
 
- Numéro de passeport 
- 
Passeport n ° 
- Passeport Non
 
- Passeport #
 
- Passeport#
 
- PasseportNon 
- Passeportn °
 
   
## <a name="us-bank-account-number"></a>米国の銀行口座番号

### <a name="format"></a>形式

8 ～ 17 桁の数字

### <a name="pattern"></a>パターン

8 ～ 17 桁の連続する数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_usa_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_usa_Bank_Account のキーワードを検出した。

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordusabankaccount"></a>Keyword_usa_Bank_Account

- Checking Account Number
 
- Checking Account
 
- Checking Account #
 
- Checking Acct Number
 
- Checking Acct #
 
- Checking Acct No.
 
- Checking Account No.
 
- Bank Account Number
 
- Bank Account #
 
- Bank Acct Number
 
- Bank Acct #
 
- Bank Acct No.
 
- Bank Account No.
 
- Savings Account Number
 
- Savings Account.
 
- Savings Account #
 
- Savings Acct Number
 
- Savings Acct #
 
- Savings Acct No.
 
- Savings Account No.
 
- Debit Account Number
 
- Debit Account
 
- Debit Account #
 
- Debit Acct Number
 
- Debit Acct #
 
- Debit Acct No.
 
- Debit Account No.
 
   
## <a name="us-drivers-license-number"></a>米国の運転免許証番号

### <a name="format"></a>形式

州に応じて異なる

### <a name="pattern"></a>パターン

州に応じて異なる - ニューヨークの場合:
- ddd ddd ddd のような形式の 9 桁の数字がマッチします。
- ddddddddd のような 9 桁の数字はマッチしません。

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_[state_name]_drivers_license_name のキーワードを検出した。
- Keyword_us_drivers_license のキーワードを検出しました。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_[state_name]_drivers_license_name のキーワードを検出した。
- Keyword_us_drivers_license_abbreviations のキーワードを検出した。
- Keyword_us_drivers_license のキーワードを検出しなかった。

```
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordusdriverslicenseabbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL 
- DLS 
- CDL 
- CDL 
- ID 
- Id 
- DL# 
- 
DLS#
 
- CDL#
 
- CDLS#
 
- ID#
- 
IDs#
 
- ID number
 
- ID numbers
 
- LIC 
- LIC#
 

#### <a name="keywordusdriverslicense"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- ドライバー Lic 
- ドライバー Lics 
- ドライバー ライセンス 
- ドライバー ライセンス 
- DriversLic 
- DriversLics 
- 証 
- DriversLicenses 
- ドライバー Lic 
- ドライバー Lics 
- 運転免許証番号 
- ドライバー ライセンス 
- Driver'Lic 
- Driver'Lics 
- Driver'License 
- Driver'Licenses 
- ドライバー ' Lic 
- ドライバー ' Lics 
- ドライバー ' ライセンス 
- ドライバー ' ライセンス
- Driver'sLic 
- Driver'sLics 
- Driver'sLicense 
- Driver'sLicenses 
- ドライバーの Lic 
- ドライバーの Lics 
- 運転免許証 
- 運転免許証 
- identification number
 
- identification numbers
 
- identification #
 
- id カード 
- id カード 
- id カード 
- id カード 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- Driver Lic# 
- 
Driver Lics#
 
- ドライバーのライセンス数 
- ドライバーのライセンス数 
- DriversLic # 
- DriversLics # 
- 証番号 
- DriversLicenses # 
- ドライバー Lic # 
- ドライバー Lics # 
- ドライバーのライセンス数 
- ドライバーのライセンス数 
- Driver'Lic#
 
- Driver'Lics#
 
- Driver'License#
 
- Driver'Licenses#
 
- Driver' Lic#
 
- Driver' Lics#
 
- Driver' License#
 
- Driver' Licenses#
 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver's Lic#
 
- Driver's Lics#
 
- Driver's License#
 
- Driver's Licenses#
 
- id のカード番号 
- id cards#
 
- identification card#
 
- identification cards#
 


#### <a name="keywordstatenamedriverslicensename"></a>Keyword_[state_name]_drivers_license_name

- 州の略号 (たとえば、"NY")
 
- 州の名前 (たとえば、"New York")
    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a>米国の個人納税者識別番号 (ITIN)

### <a name="format"></a>形式

「9」で始まる 9 桁の数字、4 桁目は「7」または「8」、スペースまたはスラッシュによる書式設定は省略可能

### <a name="pattern"></a>パターン

書式設定されている場合:
- 数字「9」 
- 2 桁の数字 
- スペースまたはダッシュ 
- 「7」または「8」 
- 1 桁の数字 
- スペースまたはダッシュ 
- 4 桁の数字

書式設定されていない場合:
- 数字「9」 
- 2 桁の数字 
- 「7」または「8」 
- 5 桁の数字

### <a name="checksum"></a>チェックサム

なし

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。
- 次の条件のうち 1 つ以上に該当する:
    - Keyword_itin のキーワードを検出した。
    - 関数 Func_us_address が適切な形式の住所を検出した。
    - 関数 Func_us_date が適切な日付形式の日付を検出した。
    - Keyword_itin_collaborative のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。
- 次の条件のうち 1 つ以上に該当する:
    - Keyword_itin_collaborative のキーワードを検出した。
    - 関数 Func_us_address が適切な形式の住所を検出した。
    - 関数 Func_us_date が適切な日付形式の日付を検出した。

```
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyworditin"></a>Keyword_itin

- taxpayer
 
- tax id
 
- tax identification
 
- itin
 
- ssn 
- tin
 
- 社会保障 
- tax payer
 
- itins
 
- taxid

 
- individual taxpayer
 

#### <a name="keyworditincollaborative"></a>Keyword_itin_collaborative

- License 
- DL 
- DOB
 
- 誕生日 
- 誕生日  
- Date of Birth
 
   
## <a name="us-social-security-number-ssn"></a>米国の社会保障番号 (SSN)

### <a name="format"></a>形式

書式設定ありまたは書式設定なしの 9 桁の数字

> [!NOTE]
> 2011 年の中旬より前に発行されている場合、SSN には厳密な書式があり、数値の特定の部分が一定の範囲内に入っていなければ有効になりません。

### <a name="pattern"></a>パターン

4 つの異なるパターンで SSN を検索する 4 つの関数を次に示します。
- Func_ssn は 2011 年以前の、厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。
- Func_unformatted_ssn は 2011 年以前の、厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。
- Func_randomized_formatted_ssn は 2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。
- Func_randomized_unformatted_ssn は 2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。

### <a name="checksum"></a>チェックサム

なし


### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_ssn がパターンに一致するコンテンツを検出した。
- Keyword_ssn のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出した。
- Keyword_ssn のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。
- Keyword_ssn のキーワードを検出した。
- 関数 Func_ssn がパターンに一致するコンテンツを検出しなかった。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に 55% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_randomized_unformatted_ssn がパターンに一致するコンテンツを検出した。
- Keyword_ssn のキーワードを検出した。
- 関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出しなかった。

```
<!-- U.S. Social Security Number (SSN) -->
    <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywordssn"></a>Keyword_ssn

- Social Security
 
- Social Security#
 
- Soc Sec
 
- SSN 
- SSNS
 
- SSN#
 
- SS#
 
- SSID
 
   

