---
title: 機密情報の種類の検索基準：
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できる状態で、80の機密情報の種類が含まれています。 このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。
ms.openlocfilehash: dc2958af5b64f9e9318faab5d55ed340404f1857
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077553"
---
# <a name="what-the-sensitive-information-types-look-for"></a>機密情報の種類の検索基準

Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できるさまざまな機密情報の種類が含まれています。 このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。 機密情報の種類はパターンで定義され、正規表現または関数で識別できます。 機密情報の種類はさらに、キーワードやチェックサムなどの確証的な証拠を使用して識別することもできます。 信頼レベルと近接も、評価プロセスで使用されます。
  
## <a name="aba-routing-number"></a>ABA ルーティング番号

### <a name="format"></a>Format

書式設定ありまたは書式設定なしの 9 桁の数字

### <a name="pattern"></a>パターン

さ
- 0、1、2、3、6、7、または 8 で始まる 4 桁の数字
- ハイフン 1 つ 
- 4 桁の数字
- ハイフン 1 つ 
- 1 桁の数字

書式なし: 0、1、2、3、6、7、または8で始まる9桁の連続した数字 

### <a name="checksum"></a>チェックサム

いいえ

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
- aba #
- aba routing #
- aba routing number
- aba
- abarouting#
- aba number
- abaroutingnumber
- american bank association routing #
- american bank association routing number
- americanbankassociationrouting#
- americanbankassociationroutingnumber
- bank routing number
- bankrouting#
- bankroutingnumber
- routing transit number
- RTN 
   
## <a name="argentina-national-identity-dni-number"></a>アルゼンチンの国民識別 (DNI) 番号

### <a name="format"></a>Format

ピリオドで区切られた 8 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字:
- 2 桁の数字
- ピリオド 1 つ 
- 3 桁の数字 
- ピリオド 1 つ 
- 3 桁の数字 

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_argentina_national_id は、このパターンに一致するコンテンツを検出します。
- Keyword_argentina_national_id からのキーワードが見つかりました。

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
- 識別国の Id カード 
- DNI 
- 個人の NIC National レジストリ 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Dad の識別子 
- Identificación 
   
## <a name="australia-bank-account-number"></a>オーストラリアの銀行口座番号

### <a name="format"></a>Format

銀行支店識別コード (BSB) を含むまたは含まない 6 ～ 10 桁の数字

### <a name="pattern"></a>パターン

口座番号は 6 ～ 10 桁の数字。
オーストラリアの銀行の州支店番号:
- 3 桁の数字 
- ハイフン 
- 3 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

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
- correspondent bank
- base currency
- usa account
- holder address
- bank address
- information account
- fund transfers
- bank charges
- bank details
- banking information
- full names
- iaea

   
## <a name="australia-drivers-license-number"></a>オーストラリアの運転免許証番号

### <a name="format"></a>Format

9 桁の文字と数字

### <a name="pattern"></a>パターン

9 つの文字と数字: 

- 2 つの数字または文字 (大文字小文字を区別しない) 
- 2 桁の数字 
- 5 つの数字または文字 (大文字小文字を区別しない)

OR

- 1 ～ 2 桁の省略可能な文字 (大文字小文字の区別なし)  
- 4 ～ 9 桁の数字

OR

- 9 桁の数字または文字 (大文字小文字の区別なし)

### <a name="checksum"></a>チェックサム

いいえ

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
- australian automobile association
- international driving permit
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Licence
- Driver Licences
- DriversLic
- その他のライセンス
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver' Lic
- Driver' Lics
- Driver' ライセンス
- Driver'Licences
- Driver' Lic
- Driver' Lics
- Driver' Licence
- Driver' Licences
- Driver' Slic
- Driver' Slics
- ドライバ ' スライスの持続性
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences#
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- DriversLic #
- DriversLics #
- のデモライセンス #
- DriversLicences#
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver' Lic #
- Driver' Lics #
- Driver' ライセンス #
- Driver'Licences#
- Driver' Lic#
- Driver' Lics#
- Driver' Licence#
- Driver' Licences#
- Driver' Slic #
- Driver' Slics #
- ドライバ ' スライスの持続性 #
- Driver'sLicences#
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences# 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- 製品の使用許諾
- このライセンス
- Drivers License
- Drivers Licenses
- Driver' ライセンス
- Driver' ライセンス
- Driver' License
- Driver' Licenses
- ドライバのライセンス
- ドライバのライセンス
- Driver's License
- Driver's Licenses
- DriverLicense #
- DriverLicenses #
- Driver License#
- Driver Licenses#
- 製品のライセンス #
- (C#) ライセンス #
- Drivers License#
- Drivers Licenses#
- Driver' License #
- Driver' Licenses #
- Driver' License#
- Driver' Licenses#
- Driverのライセンス番号
- ドライバのライセンス #
- Driver's License#
- Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>オーストラリアの医療口座番号

### <a name="format"></a>Format

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
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- medicare

   
## <a name="australia-passport-number"></a>オーストラリアのパスポート番号

### <a name="format"></a>Format

1 桁の文字の後に 7 桁の数字

### <a name="pattern"></a>パターン

1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。
- Keyword_passport または Keyword_australia_passport_number からのキーワードが見つかりました。

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
- Passport No
- Passport #
- サインアウト
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °

#### <a name="keywordaustraliapassportnumber"></a>Keyword_australia_passport_number

- サインアウト
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- visa
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>オーストラリアの納税者番号

### <a name="format"></a>Format

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
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number

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

## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB 認証キー

### <a name="format"></a>Format

文字列 "DocumentDb" の後に、次のパターンで概説されている文字と文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "DocumentDb"
- 3-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ
- より大きい記号 (>)、等号 (=)、二重引用符 (")、またはアポストロフィ (')
- 86の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ
- 2つの等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 CEP_Regex_AzureDocumentDBAuthKey は、このパターンに一致するコンテンツを検出します。
- 正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。

```
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。

- 拠点
- fabrikam
- ノース
- サンド
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->ネット

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS データベースの接続文字列と Azure SQL 接続文字列

### <a name="format"></a>Format

文字列 "Server"、"server"、または "data source" の後に、次のパターンで概説されている文字と文字列を指定します (文字列 "cloudapp" を含む)。<!--no-hyperlink-->com または "cloudapp azure。<!--no-hyperlink-->net "または" database "です。<!--no-hyperlink-->net "、および" Password "または" pwd "という文字列を指定します。

### <a name="pattern"></a>パターン

- 文字列 "Server"、"server"、または "data source"
- 0-2 空白文字
- 等号 (=)
- 0-2 空白文字
- 1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ
- 文字列 "cloudapp。<!--no-hyperlink-->com "," cloudapp。<!--no-hyperlink-->net "、または" database "です。<!--no-hyperlink-->ネット
- 1-300 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ
- 文字列 "Password"、"password"、または "pwd"
- 0-2 空白文字
- 等号 (=)
- 0-2 空白文字
- セミコロンではない1つ以上の文字 (;)、引用符 (")、またはアポストロフィ (')
- セミコロン (;)、引用符 (")、またはアポストロフィ (')

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 CEP_Regex_AzureConnectionString は、このパターンに一致するコンテンツを検出します。
- 正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。

```
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。

- 拠点
- fabrikam
- ノース
- サンド
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->ネット

## <a name="azure-iot-connection-string"></a>Azure IoT 接続文字列

### <a name="format"></a>Format

文字列 "HostName" の後に、次のパターンで概説されている文字と文字列 ("azure デバイス" を含む)。<!--no-hyperlink-->net "および" SharedAccessKey "。

### <a name="pattern"></a>パターン

- 文字列 "HostName"
- 0-2 空白文字
- 等号 (=)
- 0-2 空白文字
- 1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ
- 文字列 "azure デバイス。<!--no-hyperlink-->ネット
- 1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ
- 文字列 "SharedAccessKey"
- 0-2 空白文字
- 等号 (=)
- 0-2 空白文字
- 43の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ
- 等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 CEP_Regex_AzureIoTConnectionString は、このパターンに一致するコンテンツを検出します。
- 正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。

```
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。

- 拠点
- fabrikam
- ノース
- サンド
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->ネット

## <a name="azure-publish-setting-password"></a>Azure 発行設定パスワード

### <a name="format"></a>Format

文字列 "userpwd =" に続けて英数字の文字列を指定します。

### <a name="pattern"></a>パターン

- 文字列 "userpwd ="
- 60小文字または数字の任意の組み合わせ
- 二重引用符 (")

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 CEP_Regex_AzurePublishSettingPasswords は、このパターンに一致するコンテンツを検出します。
- 正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。


```
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。

- 拠点
- fabrikam
- ノース
- サンド
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->ネット

## <a name="azure-redis-cache-connection-string"></a>Azure Redis Cache 接続文字列

### <a name="format"></a>Format

文字列 "redis...<!--no-hyperlink-->net "の後に、次のパターンで概説されている文字と文字列を指定します。文字列" password "または" pwd "が含まれます。

### <a name="pattern"></a>パターン

- 文字列 "redis...<!--no-hyperlink-->ネット
- 1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ
- 文字列 "password" または "pwd"
- 0-2 空白文字
- 等号 (=)
- 0-2 空白文字
- 43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))
- 等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 CEP_Regex_AzureRedisCacheConnectionString は、このパターンに一致するコンテンツを検出します。
- 正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。

```
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。

- 拠点
- fabrikam
- ノース
- サンド
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->ネット

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>Format

文字列 "sig" の後に、次のパターンで概説されている文字と文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "sig"
- 0-2 空白文字
- 等号 (=)
- 0-2 空白文字
- 43-53 文字のうち、下位または大文字の文字、数字、またはパーセント記号 (%) の任意の組み合わせ。
- 文字列 "% 3d"
- 小文字または大文字、数字、パーセント記号 (%) 以外の文字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 CEP_Regex_AzureSAS は、このパターンに一致するコンテンツを検出します。

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure Service Bus の接続文字列

### <a name="format"></a>Format

文字列 "EndPoint" の後に、次のパターンで概説されている文字と文字列が続きます。<!--no-hyperlink-->net "および" Shared' キー "。

### <a name="pattern"></a>パターン

- 文字列 "EndPoint"
- 0-2 空白文字
- 等号 (=)
- 0-2 空白文字
- 1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ
- 文字列 "windows.<!--no-hyperlink-->ネット
- 1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ
- 文字列 "SharedAccessKey"
- 0-2 空白文字
- 等号 (=)
- 0-2 空白文字
- 43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))
- 等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 CEP_Regex_AzureServiceBusConnectionString は、このパターンに一致するコンテンツを検出します。
- 正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。

```
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。

- 拠点
- fabrikam
- ノース
- サンド
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->ネット

## <a name="azure-storage-account-key"></a>Azure ストレージアカウントキー

### <a name="format"></a>Format

文字列 "DefaultEndpointsProtocol" の後に、文字列 "AccountKey" を含む、次のパターンで概説されている文字および文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "DefaultEndpointsProtocol"
- 0-2 空白文字
- 等号 (=)
- 0-2 空白文字
- 1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ
- 文字列 "AccountKey"
- 0-2 空白文字
- 等号 (=)
- 0-2 空白文字
- 86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))
- 2つの等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 CEP_Regex_AzureStorageAccountKey は、このパターンに一致するコンテンツを検出します。
- 正規表現 CEP_AzureEmulatorStorageAccountFilter は、このパターンに一致するコンテンツを検出し**ません**。
- 正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。

```
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cepazureemulatorstorageaccountfilter"></a>CEP_AzureEmulatorStorageAccountFilter

(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。

- 拠点
- fabrikam
- ノース
- サンド
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->ネット

## <a name="azure-storage-account-key-generic"></a>Azure ストレージアカウントキー (汎用)

### <a name="format"></a>Format

86の下または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせで、下のパターンで説明されている文字が前または後にある。

### <a name="pattern"></a>パターン

- 0-1 より大きい記号 (>)、アポストロフィ (')、等号 (=)、二重引用符 (")、または番号記号 (#) を指定します。
- 86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))
- 2つの等号 (=)


### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 CEP_Regex_AzureStorageAccountKeyGeneric は、このパターンに一致するコンテンツを検出します。

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a>ベルギーの国民番号

### <a name="format"></a>Format

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
- 関数 Func_belgium_national_number は、このパターンに一致するコンテンツを検索します。
- Keyword_belgium_national_number からのキーワードが見つかりました。
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

- ID
- レジスタ
- Fim 
- ID 
- 「識別子」
- Registratie nummer 
- Identificatie nummer 
- 識別子
- Registratie
- 識別子 
- Carte d’identité 
- numéro d'immatriculation
- numéro d'identification
- 識別子 
- inscription 
- Identifikation
- Identifizierung
- Identifikationsnummer
- Personalausweis
- Registrierung
- Registrationsnummer

   
## <a name="brazil-cpf-number"></a>ブラジルの CPF 番号

### <a name="format"></a>Format

書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字

### <a name="pattern"></a>パターン

さ
- 3 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ハイフン 1 つ  
- チェック ディジットとして機能する 2 桁の数字

なし
- 11 桁の数字 (最後の 2 桁はチェック ディジット)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。
- Keyword_brazil_cpf からのキーワードが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。
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
- Fim
- レジスタ
- 増大
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 
   
## <a name="brazil-legal-entity-number-cnpj"></a>Brazil Legal Entity Number (CNPJ)

### <a name="format"></a>Format

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
- 関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。
- Keyword_brazil_cnpj からのキーワードが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。
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
- サイト 
   
## <a name="brazil-national-id-card-rg"></a>	ブラジルの国民識別カード (RG)

### <a name="format"></a>Format

Registro Geral (古い形式): 9 桁の数字

Registro de 識別子 Dade (RIC) (新しい形式):11 桁の数字

### <a name="pattern"></a>パターン

Registro Geral (従来の形式):
- 2 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ハイフン 1 つ  
- チェック ディジットとして機能する 1 桁の数字

Registro de 識別子 Dade (RIC) (新しい形式):
- 10 桁の数字 
- ハイフン 1 つ  
- チェック ディジットとして機能する 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。
- Keyword_brazil_rg からのキーワードが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。
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

Cédula de 識別子 dade id カード national id número de rregistro registro de I識別子 Dade registro geral このキーワードは大文字と小文字を区別します) RIC (このキーワードは大文字と小文字を区別します) 
   
## <a name="canada-bank-account-number"></a>カナダの銀行口座番号

### <a name="format"></a>Format

7 桁または 12 桁の数字

### <a name="pattern"></a>パターン

カナダの銀行口座番号は 7 桁または 12 桁の数字です。

カナダの銀行口座転送番号は次のとおりです。
- 5 桁の数字 
- ハイフン 
- 3桁の数字または
- 1 桁のゼロ (0)  
- 8 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

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
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit
   
## <a name="canada-drivers-license-number"></a>カナダの運転免許証番号

### <a name="format"></a>Format

州によって異なります

### <a name="pattern"></a>パターン

アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン

### <a name="checksum"></a>チェックサム

いいえ

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
- 州名 (Alberta など)

#### <a name="keywordcanadadriverslicense"></a>Keyword_canada_drivers_license

- DL
- DL
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- DriversLic
- DriversLics
- その他のライセンス
- DriversLicences
- 製品の使用許諾
- このライセンス
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver' Lic
- Driver' Lics
- Driver' ライセンス
- Driver' ライセンス
- Driver' ライセンス
- Driver'Licences
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver' Licence
- Driver' Licences
- Driver' Slic
- Driver' Slics
- ドライバのライセンス
- ドライバのライセンス
- ドライバ ' スライスの持続性
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- Driver's Licence
- Driver's Licences
- Permis de Conduire
- id
- ids
- idcard number
- idcard numbers
- idcard #
- idcard #s
- idcard card
- idcard cards
- idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- fim 
- DL
- DL 
- CDL 
- CDLS # 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences# 
- Driver Lic#
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- Driver License# 
- Driver Licences# 
- DriversLic # 
- DriversLics # 
- 製品のライセンス # 
- (C#) ライセンス # 
- のデモライセンス # 
- DriversLicences# 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Drivers Licence# 
- Drivers Licences# 
- Driver' Lic # 
- Driver' Lics # 
- Driver' License # 
- Driver' Licenses # 
- Driver' ライセンス # 
- Driver'Licences# 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver' Licence# 
- Driver' Licences# 
- Driver' Slic # 
- Driver' Slics # 
- Driverのライセンス番号 
- ドライバのライセンス # 
- ドライバ ' スライスの持続性 # 
- Driver'sLicences# 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- Driver's Licence# 
- Driver's Licences# 
- Permis de Conduire# 
- rid 
- rid 
- idcard card# 
- idcard cards# 
- idcard # 
- identification card# 
- identification cards# 
- fim 
   
## <a name="canada-health-service-number"></a>カナダの健康保険番号

### <a name="format"></a>Format

10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

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
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- psychiatrist
- workers compensation
- 身体
      
## <a name="canada-passport-number"></a>カナダのパスポート番号

### <a name="format"></a>Format

2 桁の大文字の後に 6 桁の数字

### <a name="pattern"></a>パターン

2 桁の大文字の後に 6 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。
- Keyword_canada_passport_number または Keyword_passport からのキーワードが見つかりました。

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
- canadian passport
- passport application
- passport photos
- certified translator
- canadian citizens
- processing times
- renewal application

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- サインアウト
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °
   
## <a name="canada-personal-health-identification-number-phin"></a>カナダの個人保健識別番号 (PHIN)

### <a name="format"></a>Format

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_canada_phin は、このパターンに一致するコンテンツを検出します。
Keyword_canada_phin または Keyword_canada_provinces から、少なくとも2つのキーワードが見つかります。

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
- health information act
- income tax information
- manitoba health
- health registration
- prescription purchases
- benefit eligibility
- personal health
- power of attorney
- registration number
- personal health number
- practitioner referral
- wellness professional
- patient referral
- health and wellness

#### <a name="keywordcanadaprovinces"></a>Keyword_canada_provinces

- Nunavut
- 州
- Northwest Territories
- オンタリオ州
- British Columbia
- 州
- Saskatchewan
- マニトバ州
- 州
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- カナダ
   
## <a name="canada-social-insurance-number"></a>カナダの社会保険番号

### <a name="format"></a>Format

9 桁の数字と省略可能なハイフンまたはスペース

### <a name="pattern"></a>パターン

さ
- 3 桁の数字 
- ハイフンまたはスペース 
- 3 桁の数字 
- ハイフンまたはスペース 
- 3 桁の数字

書式なし: 9 桁の数字

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
- 大罪 
- ssn 
- ssn 
- social security 
- numero d'assurance social 
- national identification number 
- national id 
- sin 
- soc ins 
- social ins 

#### <a name="keywordsincollaborative"></a>Keyword_sin_collaborative

- driver's license 
- drivers license 
- driver's licence 
- drivers licence 
- DOB 
- 誕生日 
- Birthday 
- Date of Birth 
   
## <a name="chile-identity-card-number"></a>	チリの身分証明書番号

### <a name="format"></a>Format

7-8 桁の数字と区切り文字のチェックディジットまたは文字

### <a name="pattern"></a>パターン

7 ～ 8 桁の数字と区切り文字:
- 1 ～ 2 桁の数字  
- ピリオド 1 つ  
- 3 桁の数字 
- ピリオド 1 つ  
- 3 桁の数字 
- ハイフン 1 つ  
- チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別なし)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。
- Keyword_chile_id_card からのキーワードが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。
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
- Fim 
- Rol Único Nacional 
- 実行 
- Rol Único Tributario 
- 類型 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- Identificación 
   
## <a name="china-resident-identity-card-prc-number"></a>	中国の居民身分証明書 (PRC) 番号

### <a name="format"></a>Format

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
- 関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。
- Keyword_china_resident_id からのキーワードが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。
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

### <a name="format"></a>Format

書式設定または書式設定ができない16桁の数字 (dddddddddddddddd)。 Luhn テストに合格する必要があります。

### <a name="pattern"></a>パターン

世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。

### <a name="checksum"></a>チェックサム

あり (Luhn のチェックサム)

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_credit_card がパターンに一致するコンテンツを検出した。
- 次のいずれかの条件に該当する:
    - Keyword_cc_verification のキーワードを検出した。
    - Keyword_cc_name からのキーワードが見つかりました。
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
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
- cod. seguranca cod。 segurança
- cód. seguranca
- cód segurança
- cod seguranca cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablん f
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
- valor は
- vencimento
- Venc 

#### <a name="keywordccname"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- Visa
- mastercard
- master card
- mc 
- mastercards
- master cards
- diner's Club
- diners club
- din/クラブ
- discover card
- discovercard
- discover cards
- JCB
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- ]
- cc #:
- expiration date
- exp date
- expiry date
- date d’expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- カード番号
- カード番号
- card numbers
- creditcard
- credit cards
- creditcards
- ccn
- card holder
- 所有者
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
- enroute
- en route
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
- kartennr 
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
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
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- 違います。 de tarjeta
- no de tarjeta
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
- número do cartão
- numero do cartão 
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- n ° do cartão
- no do cartão
- no do cartao
- 違います。 do cartão
- 違います。 do cartao 
   
## <a name="croatia-identity-card-number"></a>クロアチアの身分証明書番号

### <a name="format"></a>Format

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_croatia_id_card は、このパターンに一致するコンテンツを検索します。
- Keyword_croatia_id_card からのキーワードが見つかりました。

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

   
## <a name="croatia-personal-identification-oib-number"></a>	Croatia Personal Identification (OIB) Number

### <a name="format"></a>Format

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字:
- 10 桁の数字 
- 最終桁は、国際的なデータ交換のためのチェックディジットです。 HR は11桁の数字の前に追加されます。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。
- Keyword_croatia_oib_number からのキーワードが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。
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

   
## <a name="czech-personal-identity-number"></a>チェコの個人 Id 番号

### <a name="format"></a>Format

省略可能なスラッシュ (古い形式) を含む9桁の数字 (省略可能)。スラッシュ (新しい形式)

### <a name="pattern"></a>パターン

9桁の数字 (古い形式):
- 9 桁の数字

OR

- 生年月日を表す6桁の数字
- スラッシュ 1 つ 
- 3 桁の数字

10桁の数字 (新しい形式):
- 10 桁の数字

OR

- 生年月日を表す6桁の数字
- スラッシュ 1 つ  
- 4桁の数字 (最後の桁はチェックディジット)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは 85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_czech_id_card は、このパターンに一致するコンテンツを検出します。
Keyword_czech_id_card からのキーワードが見つかりました。
チェックサムが渡される。

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

- チェコの個人 id 番号
- Rodnéčíslo
   
## <a name="denmark-personal-identification-number"></a>	Denmark Personal Identification Number

### <a name="format"></a>Format

ハイフンを 1 つ含む 10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字:
- DDMMYY の形式の生年月日を表す 6 桁の数字  
- ハイフン 1 つ  
- 4 桁の数字 (最後の桁はチェック ディジット)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_denmark_id は、このパターンに一致するコンテンツを検出します。
Keyword_denmark_id からのキーワードが見つかりました。
チェックサムが渡される。

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

### <a name="format"></a>Format

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

### <a name="format"></a>Format

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

- account number 
- card number 
- card no. 
- security number 
- ] 

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
- # # の連絡先 
- bank card 
- bankkaart 
- card holder 
- card holders 
- card num 
- card number 
- card numbers 
- card type 
- cardano numerico 
- 所有者 
- cardholders 
- カード番号 
- カード番号 
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
- lekaart の方法 
- lekaar10 の場合 
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
- din/クラブ 
- 開示 
- discover card 
- discover cards 
- discovercard 
- discovercards 
- débito automático
- edc 
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
- kartennr 
- kartennummer 
- kreditkarte 
- kreditkarten-nummer 
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
- no de tarjeta 
- no do cartao 
- no do cartão 
- 違います。 de tarjeta 
- 違います。 do cartao 
- 違います。 do cartão 
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
- nº do cartão 
- n ° do cartão 
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
- 単独 
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
- v-支払い 
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
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
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
- 違います。 dell'edizione 
- 違います。 di sicurezza 
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

- ablん f 
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
- nntp 
- 無効 
- 期限 
- 期限 
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
- valor は 
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- vto 
- válido hasta 
   
## <a name="eu-drivers-license-number"></a>EU 運転免許証番号

詳細については、「 [EU ドライバーのライセンス番号の機密情報の種類](eu-driver-s-license-number.md)」を参照してください。
  
## <a name="eu-national-identification-number"></a>EU 国家識別番号

詳細については、「 [EU 国立 Id 番号の機密情報の種類](eu-national-identification-number.md)」を参照してください。
  
## <a name="eu-passport-number"></a>EU パスポート番号

詳細については、「 [EU パスポート番号の機密情報の種類](eu-passport-number.md)」を参照してください。
  
## <a name="eu-social-security-number-or-equivalent-id"></a>EU 社会保障番号または同等の ID

詳細については、「 [EU 社会保障番号または同等の ID の機密情報の種類](eu-social-security-number-or-equivalent-id.md)」を参照してください。
  
## <a name="eu-tax-identification-number"></a>EU 税務識別番号

詳細については、「 [EU 税務識別番号の機密情報の種類](eu-tax-identification-number.md)」を参照してください。
  
## <a name="finland-national-id"></a>フィンランドの国民 ID

### <a name="format"></a>Format

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
- Sosiaaliturvatunnus
- SOTU Henkilötunnus HETU
- Personbeteckning
- Personnummer
   
## <a name="finland-passport-number"></a>フィンランドのパスポート番号

次の9つの文字と数字のパターンの組み合わせを書式設定します。9桁の文字 (大文字小文字を区別しない)、7桁のチェックサムを定義しません。 DLP ポリシーは 75% で、この種類の機密情報がある場合に、300文字の近接性: 正規表現 Regex_finland_passport_number は、このパターンに一致するコンテンツを検出します。
Keyword_finland_passport_number からのキーワードが見つかりました。
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity>
キーワード Keyword_finland_passport_number Passport Passi
   
## <a name="france-drivers-license-number"></a>フランスの運転免許証番号

### <a name="format"></a>Format

12 桁の数字

### <a name="pattern"></a>パターン

フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

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
- driving license
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers

## <a name="france-national-id-card-cni"></a>フランスの国民識別カード (CNI)

### <a name="format"></a>Format

12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

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

### <a name="format"></a>Format

9 桁の数字と文字

### <a name="pattern"></a>パターン

9 つの数字と文字:
- 2 桁の数字 
- 2 つの文字 (大文字小文字を区別しない) 
- 5 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

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
- Passport No
- Passport #
- サインアウト
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee"></a>フランスの社会保障番号 (INSEE)

### <a name="format"></a>Format

15 桁の数字

### <a name="pattern"></a>パターン

次のいずれかのパターンに一致する:
- 13桁の数字の後にスペースを続け、2桁の数字<br/>
または
- 15 桁の連続する数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。
- Keyword_fr_insee のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。
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
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- 違います。 d'identité
- numero d'identite
- no d'identite
- 違います。 d'identite
- social security number
- social security code
- social insurance number
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le code de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- code sécu 
   
## <a name="german-drivers-license-number"></a>ドイツの運転免許証番号

### <a name="format"></a>Format

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
- Futex
- Futex の Ehのリリース
- Führerscheinnummer
- Fuhrerscheinnummer
- Fuehrerscheinnummer
- Führerschein- 
- Futex (中) 
- Futex の Ehのリリース 
- FührerscheinnummerNr
- Futex がある Hていません Einnumnr
- Futex の Ehの再リリース/Einnumnr
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
- Futex がある Hていません Einnumnr 
- Futex の Ehの再リリース/Einnumnr 
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
- DL
- Driv Lic 
- Driv Licen 
- Driv License
- Driv Licenses 
- Driv Licence 
- Driv Licences 
- Driv Lic 
- Driver Licen 
- Driver License 
- Driver Licenses 
- Driver Licence 
- Driver Licences 
- Drivers Lic 
- Drivers Licen 
- Drivers License 
- Drivers Licenses 
- Drivers Licence 
- Drivers Licences 
- Driver's Lic 
- Driver's Licen 
- Driver's License 
- Driver's Licenses 
- Driver's Licence 
- Driver's Licences 
- Driving Lic 
- Driving Licen 
- Driving License 
- Driving Licenses 
- Driving Licence 
- Driving Licences

#### <a name="keywordgermandriverslicensecollaborative"></a>Keyword_german_drivers_license_collaborative

- Nr-Führerschein 
- Nr-Futex 
- "Nr" という Futex 
- Führerschein 
- (Futex なし) 
- その他の Ehの場合 
- N-Führerschein 
- N の Futex 
- N 桁の Ehた ehのリリース
- Nr-Führerschein 
- Nr-Futex 
- "Nr" という Futex 
- Führerschein 
- (Futex なし) 
- その他の Ehの場合 
- N-Führerschein 
- N の Futex 
- N 桁の Ehた ehのリリース 

#### <a name="keywordgermandriverslicense"></a>Keyword_german_drivers_license

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
   
## <a name="german-passport-number"></a>ドイツのパスポート番号

### <a name="format"></a>Format

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
- reisepasse
- reisepassnummer
- サインアウト
- passport

#### <a name="keywordgermanpassportcollaborative"></a>Keyword_german_passport_collaborative

- ge気流 tsdatum
- ausstellungsdatum
- ausstellungsort

#### <a name="keywordgermanpassportnumber"></a>Keyword_german_passport_number

Reisepass Nr-Reisepass

#### <a name="keywordgermanpassport1"></a>Keyword_german_passport1

Reisepass-Nr

#### <a name="keywordgermanpassport2"></a>Keyword_german_passport2

bnationalit
   
## <a name="germany-identity-card-number"></a>ドイツの身分証明書番号

### <a name="format"></a>Format

2010年11月1日以降: 9 桁の文字と数字

1987年4月1日から2010年10月31日まで:10 桁

### <a name="pattern"></a>パターン

2010 年 11 月 1 日以降:
- 1 桁の文字 (大文字小文字の区別なし)  
- 8 桁の数字

1987年4月1日から2010年10月31日まで。
- 10 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_germany_id_card は、このパターンに一致するコンテンツを検出します。
- Keyword_germany_id_card からのキーワードが見つかりました。

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
- Fim
- Personalausweis
- Identifizierungsnummer
- Ausweis
- Identifikation
   
## <a name="greece-national-id-card"></a>ギリシャの国民識別カード

### <a name="format"></a>Format

7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ

### <a name="pattern"></a>パターン

7 桁の文字と数字 (従来の形式):
- 1 桁の文字 (ギリシャ語のアルファベット文字)  
- ハイフン 1 つ  
- 6 桁の数字

8 桁の文字と数字 (現在の形式):
- ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字  
- ハイフン 1 つ  
- 6 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_greece_id_card は、このパターンに一致するコンテンツを検出します。
- Keyword_greece_id_card からのキーワードが見つかりました。

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

### <a name="format"></a>Format

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
- 関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。
- Keyword_hong_kong_id_card からのキーワードが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。
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
- id card
- Identity card
- hk の id カード
- 香港特別行政 id
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

### <a name="format"></a>Format

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
- 正規表現 Regex_india_permanent_account_number は、このパターンに一致するコンテンツを検出します。
- Keyword_india_permanent_account_number からのキーワードが見つかりました。
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
- ペン 
   
## <a name="india-unique-identification-aadhaar-number"></a>インドの固有識別 (Aadhaar) 番号

### <a name="format"></a>Format

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

DLP ポリシーは 85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。
Keyword_india_aadhar からのキーワードが見つかりました。
チェックサムが渡される。
DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。
チェックサムが渡される。
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity>

### <a name="keywords"></a>キーワード
   
#### <a name="keywordindiaaadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>インドネシアの身分証明書 (KTP) 番号

### <a name="format"></a>Format

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

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_indonesia_id_card は、このパターンに一致するコンテンツを検出します。
- Keyword_indonesia_id_card からのキーワードが見つかりました。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_indonesia_id_card は、このパターンに一致するコンテンツを検出します。

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

### <a name="format"></a>Format

国コード (2 文字)、チェックディジット (2 桁)、および番号を bban 最大30文字)

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。

- 2文字の国コード
- 2つのチェックディジット (オプションのスペースが続く) 
- 1-7 4 つの文字または数字のグループ (スペースで区切ることができます)
- 1 ～ 3 個の文字または数字

各国の形式は少し異なります。 IBAN 機密情報の種類には、次の60国が含まれています。

ad、ae、al、at、az、ba、be、bg、bh、ch、cr、cy、cz、de、dk、do、ee、es、fi、fo、fr、gb、ge、hu、gl、gr、hr、、ie、il、、it、kw、kz、lb、li、lt、lu、lv、mc、md、me、mk、mr、mt、mu、nl、no、pl、pt、ro、rs、sa、se、si、sk、sm、tn、tr、vg

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

### <a name="format"></a>Format

#### <a name="ipv4"></a>IPv4
書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン

#### <a name="ipv6"></a>IPv6
 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン

### <a name="pattern"></a>パターン

### <a name="checksum"></a>チェックサム

いいえ

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
- IP-כתובת ה 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Diseases の国際分類 (ICD-10-CM)

### <a name="format"></a>Format

Dictionary

### <a name="pattern"></a>パターン

キーワード

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- Dictionary_icd_10_cm からのキーワードが見つかりました。

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

キーワード

Dictionary_icd_10_cm キーワードディクショナリの用語。 [Diseases、10リビジョン、臨床修正 (icd-10-cm) の国際分類](https://go.microsoft.com/fwlink/?linkid=852604)に基づいています。 この型は、保険コードではなく、用語に対してのみ表示されます。

   
## <a name="international-classification-of-diseases-icd-9-cm"></a>Diseases の国際分類 (ICD-9-CM)

### <a name="format"></a>Format

Dictionary

### <a name="pattern"></a>パターン

キーワード

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- Dictionary_icd_9_cm からのキーワードが見つかりました。

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

Dictionary_icd_9_cm キーワードディクショナリの用語。 [Diseases、9リビジョン、臨床修正 (icd-9-cm) の国際分類](https://go.microsoft.com/fwlink/?linkid=852605)に基づいています。 この型は、保険コードではなく、用語に対してのみ表示されます。
   
## <a name="ireland-personal-public-service-pps-number"></a>アイルランドの個人公共サービス (PPS) 番号

### <a name="format"></a>Format

古い形式 (2012 年12月31日まで):
- 7 桁の数字の後に 1 ～ 2 桁の文字  

新しい形式 (1 Jan 2013 以降):
- 7 桁の数字の後に 2 桁の文字

### <a name="pattern"></a>パターン

古い形式 (2012 年12月31日まで):
- 7 桁の数字  
- 1 ～ 2 桁の文字 (大文字小文字の区別なし)  

新しい形式 (1 Jan 2013 以降):
- 7 桁の数字  
- チェック ディジットとして機能する 1 桁のアルファベット文字 (大文字小文字の区別なし)  
- 文字「A」または「H」 (大文字小文字の区別なし)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。
- 次のいずれかの条件に該当する:
    - Keyword_ireland_pps からのキーワードが見つかりました。
    - 関数 Func_eu_date が適切な日付形式の日付を検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。
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
- PPS 
- PPSN 
- Public Services Card 
- Uimhir Phearsanta Seirbhíse Poiblí 
- Uimh. PSP 
- PSP 
   
## <a name="israel-bank-account-number"></a>イスラエルの銀行口座番号

### <a name="format"></a>Format

13 桁の数字

### <a name="pattern"></a>パターン

さ
- 2 桁の数字 
- ダッシュ 
- 3 桁の数字 
- ダッシュ 
- 8 桁の数字

なし
- 	13 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

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

### <a name="format"></a>Format

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

### <a name="format"></a>Format

10 桁の文字と数字の組み合わせ

### <a name="pattern"></a>パターン

- 10 個の文字と数字の組み合わせ:
- 1 文字 (大文字小文字を区別しない) 
- 文字 "A" または "V" (大文字小文字を区別しない) 
- 7 つの文字 (大文字小文字を区別しない)、数字、またはアンダースコア文字 
- 1 文字 (大文字小文字を区別しない)

### <a name="checksum"></a>チェックサム

いいえ

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

### <a name="format"></a>Format

7 桁または 8 桁の数字

### <a name="pattern"></a>パターン

銀行口座番号:
- 7 桁または 8 桁の数字
- 銀行口座支店コード:
- 4 桁の数字 
- スペースまたはダッシュ (省略可能) 
- 3 桁の数字

チェックサム

いいえ

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
- Savings Account 
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
- #アカウントの確認、勘定番号の確認 
- #勘定の確認 
- 勘定番号の確認 
- 口座番号の確認 
- 銀行口座番号 
- 銀行口座 
- 銀行口座＃ 
- 銀行の勘定番号 
- 銀行のacct＃ 
- 銀行の勘定いいえ 
- 銀行口座番号
- 普通預金口座番号 
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

### <a name="format"></a>Format

12 桁の数字

### <a name="pattern"></a>パターン

12 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

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

- dl 
- DL 
- dl 
- DL 
- driver license 
- driver licenses 
- drivers license 
- driver's license 
- drivers licenses 
- driver's licenses 
- driving licence 
- そして 
- そして 
- lics # 
- state id 
- state identification 
- state identification number 
- 低所得国＃ 
- 免許証 
- 状態ID
- 状態の識別 
- 状態の識別番号 
- 運転免許 
- 運転免許証 
- 運転免許証番号 
   
## <a name="japan-passport-number"></a>日本のパスポート番号

### <a name="format"></a>Format

2 桁の文字の後に 7 桁の数字

### <a name="pattern"></a>パターン

2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

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

### <a name="format"></a>Format

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

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

### <a name="format"></a>Format

7～ 12 桁の数字

### <a name="pattern"></a>パターン

7 ～ 12 桁の数字:
- 4 桁の数字 
- ハイフン (省略可能) 
- 6桁の数字または
- 7 ～ 12 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

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

## <a name="japanese-residence-card-number"></a>日本の居住カード番号

### <a name="format"></a>Format

12桁の文字と数字

### <a name="pattern"></a>パターン

12桁の文字と数字:
- 2 桁の文字 (大文字小文字の区別なし) 
- 8 桁の数字 
- 2 桁の文字 (大文字小文字の区別なし) 

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_jp_residence_card_number は、このパターンに一致するコンテンツを検出します。
- Keyword_jp_residence_card_number からのキーワードが見つかりました。

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

- 居住カード番号
- 住居カードなし
- 住居カード #
- 在留カード番号
   
## <a name="malaysia-id-card-number"></a>マレーシアの ID カード番号

### <a name="format"></a>Format

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

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_malaysia_id_card_number は、このパターンに一致するコンテンツを検出します。
- Keyword_malaysia_id_card_number からのキーワードが見つかりました。

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

- デジタルアプリケーションカード
- i/c
- i/c いいえ
- ic
- ic no
- id card
- 識別カード
- Identity card
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad の genalan マレーシア
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- マレーシアの id カード
- マレーシアの id カード
- nric
- 個人識別カード
   
## <a name="netherlands-citizens-service-bsn-number"></a>オランダの市民サービス (BSN) 番号

### <a name="format"></a>Format

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
- 関数 Func_netherlands_bsn は、このパターンに一致するコンテンツを検索します。
- Keyword_netherlands_bsn からのキーワードが見つかりました。
- 関数 Func_eu_date2 は、日付を正しい日付形式で検索します。
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

### <a name="format"></a>Format

3 桁の文字、スペース 1 つ (省略可能)、4 桁の数字

### <a name="pattern"></a>パターン

3文字 (大文字小文字を区別しない) スペース (省略可能)、4桁の数字

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
- New Zealand 
- 正常性 
- 処理 
   
## <a name="norway-identification-number"></a>ノルウェーの識別番号

### <a name="format"></a>Format

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
- 関数 Func_norway_id_number は、このパターンに一致するコンテンツを検索します。
- Keyword_norway_id_number からのキーワードが見つかりました。
- チェックサムが渡される。
- DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_norway_id_numbe は、このパターンに一致するコンテンツを検索します。
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
- Fim
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-id-number"></a>フィリピンの汎用多目的 ID 番号

### <a name="format"></a>Format

ハイフンで区切られた 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:
- 4 桁の数字 
- ハイフン 1 つ  
- 7 桁の数字  
- ハイフン 1 つ  
- 1 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_philippines_unified_id は、このパターンに一致するコンテンツを検出します。
- Keyword_philippines_id からのキーワードが見つかりました。

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

### <a name="format"></a>Format

3 桁の文字と 6 桁の数字

### <a name="pattern"></a>パターン

3 桁の文字 (大文字小文字の区別なし) の後に 6 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_polish_national_id は、このパターンに一致するコンテンツを検出します。
Keyword_polish_national_id_passport_number のキーワードを検出した。
チェックサムが渡される。

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
- 特定 dowodu osobistego
- Nazwa i 特定 dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. hp-ux.

   
## <a name="poland-national-id-pesel"></a>ポーランドの国民 ID (PESEL)

### <a name="format"></a>Format

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

### <a name="format"></a>Format

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

- 特定の引数
- Nr. 大き Zportu
- があります

   
## <a name="portugal-citizen-card-number"></a>ポルトガルの市民カード番号

### <a name="format"></a>Format

8 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_portugal_citizen_card は、このパターンに一致するコンテンツを検出します。
- Keyword_portugal_citizen_card からのキーワードが見つかりました。

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

### <a name="format"></a>Format

10 桁の数字

### <a name="pattern"></a>パターン

10 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

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

### <a name="format"></a>Format

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
- 正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検出します。
- Keyword_singapore_nric からのキーワードが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検出します。
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

### <a name="format"></a>Format

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
- 関数 Func_south_africa_identification_number は、このパターンに一致するコンテンツを検索します。
- Keyword_south_africa_identification_number からのキーワードが見つかりました。
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
- Fim 
   
## <a name="south-korea-resident-registration-number"></a>韓国の住民登録番号

### <a name="format"></a>Format

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
- 関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。
- Keyword_south_korea_resident_number からのキーワードが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。
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

### <a name="format"></a>Format

11 ～ 12 桁の数字

### <a name="pattern"></a>パターン

11-12 桁の数字:
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

## <a name="sql-server-connection-string"></a>SQL Server の接続文字列

### <a name="format"></a>Format

文字列 "User Id"、"User ID"、"uid"、または "UserId" の後に、次のパターンで概説されている文字と文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "User Id"、"User ID"、"uid"、または "UserId"
- 1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ
- 文字列 "Password" または "pwd" ("pwd" の前に小文字が含まれていません)
- 等号 (=)
- ドル記号 ($)、パーセント記号 (%)、不等号 (>)、記号 (@)、二重引用符 (")、セミコロン (;)、左中かっこ ([)、左大かっこ ({) のいずれでもない文字
- セミコロンではない7-128 文字の任意の組み合わせ (;)、スラッシュ (/)、または引用符 (")
- セミコロン (;)または二重引用符 (")

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 CEP_Regex_SQLServerConnectionString は、このパターンに一致するコンテンツを検出します。
- CEP_GlobalFilter からのキーワードが見つかり**ません**。
- 正規表現 CEP_PasswordPlaceHolder は、このパターンに一致するコンテンツを検出し**ません**。
- 正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。

```
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cepglobalfilter"></a>CEP_GlobalFilter

- パスワードの一部
- パスワード
- secretPassword
- 示す

#### <a name="ceppasswordplaceholder"></a>CEP_PasswordPlaceHolder

(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。

- Password または pwd の後に、0-2 スペース、等号 (=)、0-2 スペース、アスタリスク (*)、または--
- Password または pwd の後に、次のように入力します。
    - 等号 (=)
    - 小なり記号 (<)
    - 1-200 文字の大文字と小文字、数字、アスタリスク (*)、ハイフン (-)、下線 (_)、または空白文字の任意の組み合わせ。
    - より大きい記号 (>)

#### <a name="cepcommonexamplekeywords"></a>CEP_CommonExampleKeywords

(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。

- 拠点
- fabrikam
- ノース
- サンド
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->ネット

## <a name="sweden-national-id"></a>スウェーデンの国民 ID

### <a name="format"></a>Format

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

いいえ
   
## <a name="sweden-passport-number"></a>スウェーデンのパスポート番号

### <a name="format"></a>Format

8 桁の数字

### <a name="pattern"></a>パターン

8 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

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
- Passport No 
- Passport # 
- サインアウト 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport# 
- PasseportNon 
- Passeportn ° 
   
## <a name="swift-code"></a>SWIFT コード

### <a name="format"></a>Format

4 桁の文字の後に 5 ～ 31 桁の文字または数字

### <a name="pattern"></a>パターン

4 文字の後に 5 ～ 31 個の文字または数字:
- 4 文字の銀行コード (大文字小文字を区別しない) 
- 省略可能なスペース 
- 4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN)) 
- 省略可能なスペース 
- 1 ～ 3 個の文字または数字 (BBAN の残りの部分)

### <a name="checksum"></a>チェックサム

いいえ

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
- 実現\# 
- swiftcode 
- swiftnumber 
- swiftroutingnumber 
- swift code 
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

### <a name="format"></a>Format

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
   
## <a name="taiwan-passport-number"></a>	台湾のパスポート番号

### <a name="format"></a>Format

- バイオメトリックパスポート番号: 9 桁の数字
- バイオメトリクスでないパスポート番号: 9 桁の数字

### <a name="pattern"></a>パターン
バイオメトリックパスポート番号:
- 数字「3」  
- 8 桁の数字

バイオメトリクスではないパスポート番号:
- 9 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_taiwan_passport は、このパターンに一致するコンテンツを検出します。
- Keyword_taiwan_passport からのキーワードが見つかりました。

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
- Passport number 
- Passport no 
- Passport Num 
- Passport # 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>台湾の在留証明書 (ARC/TARC) 番号

### <a name="format"></a>Format

10 桁の文字と数字

### <a name="pattern"></a>パターン

10 桁の文字と数字:
- 2 桁の文字 (大文字小文字の区別なし)  
- 8 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_taiwan_resident_certificate は、このパターンに一致するコンテンツを検出します。
- Keyword_taiwan_resident_certificate からのキーワードが見つかりました。

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
- Resident Cert 
- Resident Cert. 
- Identification card 
- Alien Resident Certificate 
- 円弧 
- Taiwan Area Resident Certificate 
- TARC 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>タイ語の母集団識別コード

### <a name="format"></a>Format

13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:
- 最初の桁が0または9ではない 
- 12 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。
- Keyword_Thai_Citizen_Id からのキーワードが見つかりました。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。

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
  
## <a name="turkish-national-identification-number"></a>トルコの国の識別番号

### <a name="format"></a>Format

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。
- Keyword_Turkish_National_Id からのキーワードが見つかりました。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。

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

- TC Kimlik No
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>英国の運転免許証番号

### <a name="format"></a>Format

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

### <a name="format"></a>Format

2 桁の文字の後に 1 ～ 4 桁の数字

### <a name="pattern"></a>パターン

2 桁の文字 (大文字小文字の区別なし) の後に 1 ～ 4 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

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

### <a name="format"></a>Format

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
- D. 
- Date of Birth 
- Birth Date 
   
## <a name="uk-national-insurance-number-nino"></a>英国の国民保険番号 (NINO)

### <a name="format"></a>Format

スペースまたはダッシュで区切られた7文字または9文字

### <a name="pattern"></a>パターン

次の2つのパターンを使用できます。

- 2文字 (有効な NINOs このプレフィックスには特定の文字のみを使用します。このパターンは、大文字小文字を区別しません)。
- 6 桁の数字
- 「A」、「B」、「C」、または「d」 (プレフィックスと同様に、サフィックスには特定の文字のみ指定できます。大文字と小文字は区別されません)

OR

- 2文字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- ' A '、' B '、' C '、または ' d ' のどちらか

### <a name="checksum"></a>チェックサム

いいえ

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
- 金 
- social security number 
- insurance application 
- medical application 
- social insurance 
- medical attention 
- social security 
- great britain 
- 金    
   
## <a name="us--uk-passport-number"></a>米国/英国のパスポート番号

### <a name="format"></a>Format

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

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
- Passport No 
- Passport # 
- サインアウト 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport# 
- PasseportNon 
- Passeportn ° 
   
## <a name="us-bank-account-number"></a>米国の銀行口座番号

### <a name="format"></a>Format

8 ～ 17 桁の数字

### <a name="pattern"></a>パターン

8 ～ 17 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_usa_bank_account_number は、このパターンに一致するコンテンツを検出します。
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

### <a name="format"></a>Format

州に応じて異なる

### <a name="pattern"></a>パターン

州に応じて異なる - ニューヨークの場合:
- Ddd ddd ddd のような形式の9桁の数字は一致します。
- Ddddddddd のように9桁の数字は一致しません。

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_[state_name]_drivers_license_name のキーワードを検出した。
- Keyword_us_drivers_license からのキーワードが見つかりました。

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
- DL 
- CDL 
- CDLS 
- ID 
- Rid 
- DL 
- DL 
- CDL 
- CDLS # 
- RID
- Rid 
- ID number 
- ID numbers 
- そして 
- そして 

#### <a name="keywordusdriverslicense"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- Driver Lic 
- Driver Lics 
- Driver License 
- Driver Licenses 
- DriversLic 
- DriversLics 
- 製品の使用許諾 
- このライセンス 
- Drivers Lic 
- Drivers Lics 
- Drivers License 
- Drivers Licenses 
- Driver' Lic 
- Driver' Lics 
- Driver' ライセンス 
- Driver' ライセンス 
- Driver' Lic 
- Driver' Lics 
- Driver' License 
- Driver' Licenses
- Driver' Slic 
- Driver' Slics 
- ドライバのライセンス 
- ドライバのライセンス 
- Driver's Lic 
- Driver's Lics 
- Driver's License 
- Driver's Licenses 
- identification number 
- identification numbers 
- identification # 
- id card 
- id cards 
- identification card 
- identification cards 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- Driver Lic# 
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- DriversLic # 
- DriversLics # 
- 製品のライセンス # 
- (C#) ライセンス # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Driver' Lic # 
- Driver' Lics # 
- Driver' License # 
- Driver' Licenses # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver' Slic # 
- Driver' Slics # 
- Driverのライセンス番号 
- ドライバのライセンス # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- id card# 
- id cards# 
- identification card# 
- identification cards# 


#### <a name="keywordstatenamedriverslicensename"></a>Keyword_[state_name]_drivers_license_name

- 州の略号 (たとえば、"NY") 
- 州の名前 (たとえば、"New York")    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a>米国の個人納税者識別番号 (ITIN)

### <a name="format"></a>Format

「9」で始まる 9 桁の数字、4 桁目は「7」または「8」、スペースまたはスラッシュによる書式設定は省略可能

### <a name="pattern"></a>パターン

さ
- 数字「9」 
- 2 桁の数字 
- スペースまたはダッシュ 
- 「7」または「8」 
- 1 桁の数字 
- スペースまたはダッシュ 
- 4 桁の数字

なし
- 数字「9」 
- 2 桁の数字 
- 「7」または「8」 
- 5 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

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

- 納税 
- tax id 
- tax identification 
- itin 
- ssn 
- は 
- social security 
- tax payer 
- itins 
- taxid 
- individual taxpayer 

#### <a name="keyworditincollaborative"></a>Keyword_itin_collaborative

- ライセンス 
- DL 
- DOB 
- 誕生日 
- Birthday 
- Date of Birth 
   
## <a name="us-social-security-number-ssn"></a>米国の社会保障番号 (SSN)

### <a name="format"></a>Format

書式設定ありまたは書式設定なしの 9 桁の数字

> [!NOTE]
> 2011より前に発行された場合、SSN の書式には、特定の範囲内にある特定の範囲内にある必要があり、チェックサムがないという厳密な形式があります。

### <a name="pattern"></a>パターン

次の4つの異なるパターンで SSNs を検索する4つの関数があります。
- Func_ssn は、2011 年以前の厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。
- Func_unformatted_ssn は、2011 年以前の厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。
- Func_randomized_formatted_ssn は、2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。
- Func_randomized_unformatted_ssn は、2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。

### <a name="checksum"></a>チェックサム

いいえ


### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_ssn がパターンに一致するコンテンツを検出した。
- Keyword_ssn のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_unformatted_ssn は、このパターンに一致するコンテンツを検索します。
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
- SSN 
- SSN 
- 秒 
- SSID 
   

