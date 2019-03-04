---
title: Office 365 セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 82c382a5-b6db-44fd-995d-b333b3c7fc30
description: Office 365 セキュリティ/コンプライアンス センターの　DLP について、カスタムの機密情報の種類を作成してインポートする方法について説明します。
ms.openlocfilehash: b6289b962211bbe1764e2b6e3b4f08900cb6abd8
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341518"
---
# <a name="create-a-custom-sensitive-information-type-in-office-365-security--compliance-center-powershell"></a>Office 365 セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する

Office 365 のデータ損失防止 (DLP) には、DLP ポリシーですぐに使用できる組み込みの[機密情報の種類](what-the-sensitive-information-types-look-for.md)が多数含まれています。これらの組み込みの種類は、クレジット カード番号、銀行口座番号、パスポート番号などの特定と保護に役立ちます。 
  
ただし、組織に固有の形式を使用する従業員 ID など、さまざまな種類の機密情報を特定して保護する必要がある場合は、カスタムの機密情報の種類を作成することができます。機密情報の種類は、_ルール パッケージ_と呼ばれる XML ファイルで定義されます。
  
このトピックでは、独自のカスタムの機密情報の種類を定義した XML ファイルを作成する方法を示します。正規表現の作成方法を理解している必要があります。たとえば、このトピックでは、従業員 ID を特定するカスタムの機密情報の種類を作成します。この XML 例を基に、独自の XML ファイルを作成できます。
  
整形式の XML ファイルを作成したら、Office 365 の PowerShell を使用して Office 365 にアップロードできます。これで DLP ポリシーでカスタムの機密情報の種類を使用する準備ができたので、意図したとおりに機密情報が検出されることをテストします。

> [!NOTE]
> より単純なカスタムの機密情報の種類をセキュリティ/コンプライアンス センターの UI で作成することもできます。詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。

## <a name="important-disclaimer"></a>重要な免責事項

お客様の環境やコンテンツ マッチの要件はさまざまに異なるため、Microsoft サポートは、カスタム分類や正規表現 (別名: RegEx) パターンを定義するなど、カスタムのコンテンツ マッチング定義を提供することの支援は行えません。カスタムのコンテンツ マッチングの開発、テスト、デバッグについては、Office 365 のお客様は、内部の IT リソースを利用するか、Microsoft コンサルティング サービス (MCS) などの外部のコンサルティング リソースを利用する必要があります。サポート エンジニアは、機能の制限付きサポートを提供することはできますが、カスタムのコンテンツ マッチング開発がお客様の要件や義務を満たすことの保証はできません。提供できるサポートの種類の例として、テスト目的の正規表現パターンのサンプルが挙げられます。また、サポートは、特定の単一コンテンツにおいて期待通りに動作していない既存の RegEx パターンのトラブルシューティングを支援できます。

 テキストを処理するために使用されている Boost.RegEx (以前の RegEx++) エンジンの詳細については、「[Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)」を参照してください。
    
## <a name="sample-xml-of-a-rule-package"></a>ルール パッケージのサンプル XML

このトピックで作成するルール パッケージのサンプル XML を示します。要素と属性については、以降のセクションで説明します。
  
```
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
    <Version build="0" major="1" minor="0" revision="0"/>
    <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
    <Details defaultLangCode="en-us">
        <LocalizedDetails langcode="en-us">
            <PublisherName>Contoso</PublisherName>
            <Name>Employee ID Custom Rule Pack</Name>
            <Description>
            This rule package contains the custom Employee ID entity.
            </Description>
        </LocalizedDetails>
    </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
    <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="70">
        <Pattern confidenceLevel="60">
            <IdMatch idRef="Regex_employee_id"/>
        </Pattern>
        <Pattern confidenceLevel="70">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
        </Pattern>
        <Pattern confidenceLevel="80">
            <IdMatch idRef="Regex_employee_id"/>
            <Match idRef="Func_us_date"/>
            <Any minMatches="1">
                <Match idRef="Keyword_badge" minCount="2"/>
                <Match idRef="Keyword_employee"/>
            </Any>
            <Any minMatches="0" maxMatches="0">
                <Match idRef="Keyword_false_positives_local"/>
                <Match idRef="Keyword_false_positives_intl"/>
            </Any>
        </Pattern>
    </Entity>
    <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
    <Keyword id="Keyword_employee">
        <Group matchStyle="word">
            <Term>Identification</Term>
            <Term>Contoso Employee</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_badge">
        <Group matchStyle="string">
            <Term>card</Term>
            <Term>badge</Term>
            <Term caseSensitive="true">ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_local">
        <Group matchStyle="word">
            <Term>credit card</Term>
            <Term>national ID</Term>
        </Group>
    </Keyword>
    <Keyword id="Keyword_false_positives_intl">
        <Group matchStyle="word">
            <Term>identity card</Term>
            <Term>national ID</Term>
            <Term>EU debit card</Term>
        </Group>
    </Keyword>
    <LocalizedStrings>
        <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
            <Name default="true" langcode="en-us">Employee ID</Name>
            <Description default="true" langcode="en-us">
            A custom classification for detecting Employee IDs.
            </Description>
            <Name default="true" langcode="de-de">Name for German locale</Name>
            <Description default="true" langcode="de-de">
            Description for German locale.
            </Description>
        </Resource>
    </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a>主な要件 [Rule、Entity、Pattern 要素]

作業を開始する前に、ルールの XML スキーマの基本構造と、その構造を使用してカスタムの機密情報の種類を定義し、適切なコンテンツを特定できるようにする方法を理解しておくことをお勧めします。
  
1 つのルールによって 1 つまたは複数のエンティティ (機密情報の種類) が定義され、各エンティティによって 1 つまたは複数のパターンが定義されています。パターンとは、メールやドキュメントなどのコンテンツを評価するときに DLP が検索する内容です。
  
(用語に関する注意: DLP ポリシーを使い慣れている方は、複数の条件とアクションから構成される 1 つまたは複数のルールが 1 つのポリシーに含まれていることをご存知でしょう。しかしながら、このトピックでは、XML マークアップが、エンティティ (機密情報の種類とも呼びます) を定義するパターンとして、ルールを使用しています。そのため、このトピックに出てくる "ルール" は、条件やアクションではなく、エンティティまたは機密情報の種類と考えてください)。
  
### <a name="simplest-scenario-entity-with-one-pattern"></a>最もシンプルなシナリオ: パターンが 1 つのエンティティ

ここでは、最もシンプルなシナリオについて説明します。この例では、組織の従業員 ID を含むコンテンツを特定する DLP ポリシーが必要です。ID の書式は 9 桁の数値です。この場合のパターンは、9 桁の数値を識別するルールに含まれる正規表現を示します。9 桁の数値を含むすべてのコンテンツはこのパターンを満たします。
  
![パターンが 1 つのエンティティの図](media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
このパターンはシンプルですが、従業員 ID ではない可能性がある 9 桁の数値を含むコンテンツと一致するため、誤検知が多数特定される可能性があります。
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a>より一般的なシナリオ: パターンが複数あるエンティティ

この理由から、複数のパターンを使用してエンティティを定義し、エンティティ (9 桁の数値など) だけでなく、それらのパターンで補強証拠 (キーワードや日付など) を特定する方が一般的です。
  
たとえば、従業員 ID を含むコンテンツを特定する可能性を高めるために、9 桁の数値に加え、雇用日も特定する別のパターンを定義することができます。雇用日とキーワード ("従業員 ID" など) の両方を特定する別のパターンを定義することもできます。
  
![パターンが複数あるエンティティの図](media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
この構造の重要な側面について一部を説明します。
  
- より多くの証拠が必要なパターンの方が信頼度が高くなります。この機密情報の種類を後で DLP ポリシーにおいて使用する場合、より信頼度の高い一致に対してのみ制限の多いアクション (コンテンツのブロックなど) を使用し、信頼度の低い一致には制限の少ないアクション (通知の送信など) を使用できるので便利です。
    
- サポートされる IdMatch 要素と Match 要素は、Pattern ではなく Rule 要素の子である正規表現とキーワードを参照します。これらのサポートされる要素は、Pattern から参照されますが、Rule に含まれています。つまり、サポートされる要素の 1 つの定義 (正規表現やキーワード一覧など) は、複数のエンティティとパターンで参照できます。
    
## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a>特定する必要があるエンティティ [Entity 要素、id 属性]

エンティティは、明確に定義されたパターンを持つ、クレジットカード番号などの機密情報の種類です。各エンティティは、ID として一意の GUID を持っています。
  
### <a name="name-the-entity-and-generate-its-guid"></a>エンティティに名前を付けて GUID を生成する

Rules および Entity 要素を追加します。次に、カスタムのエンティティ名 (この例では Employee ID) を含むコメントを追加します。後で、ローカライズされた文字列セクションにこのエンティティ名を追加します。この名前は、DLP ポリシーを作成するときに UI に表示されます。
  
次に、エンティティの GUID を生成します。GUID を生成するにはいくつかの方法がありますが、PowerShell で [guid]::NewGuid() と入力することで簡単に生成できます。このエンティティ GUID も、ローカライズされた文字列セクションに後で追加します。
  
![Rules および Entity 要素を示す XML マークアップ](media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a>マッチングするパターン [Pattern 要素、IdMatch 要素、Regex 要素]

パターンには、機密情報の種類が検索している内容の一覧が含まれています。この一覧には、正規表現、キーワード、組み込み関数 (正規表現を実行して日付や住所を検索するなどのタスクを実行する関数) を含めることができます。機密情報の種類には、固有の信頼度を持つ複数のパターンが含まれます。
  
以下のすべてのパターンで共通している点は、すべてが同じ正規表現を参照していることです。この正規表現では、空白 (\s) … (\s) で囲まれた 9 桁の数値 (\d{9}) を検索しています。この正規表現は IdMatch 要素から参照されます。また、この正規表現は従業員 ID エンティティを検索するすべてのパターンに共通する要件です。IdMatch は、パターンがマッチングしようとしている識別子 (従業員 ID、クレジット カード番号、社会保障番号など) です。1 つの Pattern 要素には、1 つの IdMatch 要素のみがあります。
  
![単一の Regex 要素を参照する複数の Pattern 要素を示す XML マークアップ](media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
パターンを満たす場合は、数と信頼度が返され、DLP ポリシーの条件に使用できます。機密情報の種類を検出する条件を DLP ポリシーに追加する場合、次のように数と信頼度を編集できます。信頼度 (一致精度とも呼ばれます) については、このトピックで後述します。
  
![インスタンス数と一致精度オプション](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
正規表現を作成するときは、潜在的な問題があることに注意してください。たとえば、特定されるコンテンツ数が多すぎる正規表現を作成し、アップロードすると、パフォーマンスに影響する可能性があります。このような潜在的な問題の詳細については、後述の「[注意する必要がある潜在的な検証の問題](#potential-validation-issues-to-be-aware-of)」を参照してください。
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a>追加の証拠が必要な場合 [Match 要素、minCount 属性]

パターンでは、IdMatch だけでなく、Match 要素を使用して、キーワード、正規表現、日付、住所など、追加の補強証拠を必須にすることができます。
  
1 つのパターンには複数の Match 要素を含めることができます。Pattern 要素に直接含めるか、Any 要素を使用して組み合わせることができます。複数の Match 要素の場合は、暗黙的な AND 演算子で結合されます。パターンが一致するには、すべての Match 要素を満たす必要があります。Any 要素を使用して、AND 演算子または OR 演算子を導入することもできます (詳細については後述します)。
  
省略可能な minCount 属性を使用して、各 Match 要素で検出する必要のある一致のインスタンス数を指定できます。たとえば、キーワード一覧の少なくとも 2 つのキーワードが検出された場合にのみ、パターンを満たすものと指定することができます。
  
![minOccurs 属性を持つ Match 要素を示す XML マークアップ](media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a>キーワード [Keyword 要素、Group 要素、Term 要素、matchStyle 属性、caseSensitive 属性]

従業員 ID などの機密情報を特定するときに、多くの場合、補強証拠としてキーワードが必要になります。たとえば、9 桁の数値と一致するだけでなく、"カード"、"バッジ"、"ID" などの単語を検索することがあります。このような場合に Keyword 要素を使用します。Keyword 要素には id 属性があり、複数のパターンまたはエンティティの複数の Match 要素から参照できます。
  
キーワードは、Group 要素の Term 要素の一覧として含まれます。Group 要素には、2 つの有効値を持つ matchStyle 属性があります。
  
- **matchStyle="word"** word の一致は、空白または他の区切り文字で囲まれた複数の単語全体を特定します。複数の単語の一部に一致させる場合、またはアジア言語の単語と一致させる場合を除き、常に word を使用することをお勧めします。 
    
- **matchStyle="string"** string の一致は、囲んでいる文字にかかわらず、文字列を特定します。たとえば、"id" は "bid" と "idea" と一致します。アジア言語と一致させる必要がある場合、またはキーワードが他の文字列の一部に含まれる可能性がある場合にのみ、string を使用してください。 
    
最後に、Term 要素の caseSensitive 属性を使用して、大文字と小文字を含め、コンテンツがキーワードと完全に一致する必要があることを指定できます。
  
![キーワードを参照する Match 要素を示す XML マークアップ](media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a>正規表現 [Regex 要素]

この例の従業員 ID エンティティは、既に IdMatch 要素を使用して、空白で囲まれた 9 桁の数値というパターンの正規表現を参照しています。さらに、パターンに Match 要素を使用して追加の Regex 要素を参照し、米国の郵便番号の書式である 5 桁または 9 桁の数値など、補強証拠を特定することができます。
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a>日付や住所などのその他のパターン [組み込み関数]

DLP には、組み込みの機密情報の種類だけでなく、米国の日付、EU の日付、有効期限の日付、または米国の住所など、補強証拠を特定できる組み込み関数も含まれています。DLP は独自のカスタム関数のアップロードをサポートしていませんが、カスタムの機密情報の種類を作成した場合は、エンティティから組み込み関数を参照できます。
  
たとえば、従業員 ID バッジには雇用日が記載されているので、このカスタム エンティティで組み込み関数 `Func_us_date` を使用して、米国で一般的に使用されている形式の日付を特定できます。 
  
詳細は、「[DLP 関数で探索する内容](what-the-dlp-functions-look-for.md)」を参照してください。
  
![組み込み関数を参照する Match 要素を示す XML マークアップ](media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a>証拠のさまざまな組み合わせ [Any 要素、minMatches 属性、maxMatches 属性]

Pattern 要素内のすべての IdMatch 要素と Match 要素は暗黙的な AND 演算子で結合されます。パターンを満たすには、すべての一致を満たしている必要があります。ただし、Any 要素を使用して複数の Match 要素をグループ化することで、より柔軟なマッチング ロジックを作成できます。たとえば、Any 要素を使用して、子 Match 要素のすべて一致、一致なし、完全サブセットの一致を表すことができます。
  
Any 要素には省略可能な minMatches 属性と maxMatches 属性があります。これらの属性を使用して、パターンが一致する前に満たす必要がある子 Match 要素数を定義できます。これらの属性では、一致が検出された証拠のインスタンス数ではなく、満たす必要がある Match 要素数を定義する点に注意してください。特定の一致について最小のインスタンス数を定義するには (たとえば、一覧の 2 つのキーワードなど)、Match 要素に minCount 属性を使用します (上記を参照してください)。
  
### <a name="match-at-least-one-child-match-element"></a>少なくとも 1 つの子 Match 要素に一致する

最小数の Match 要素のみを満たすことを必須にするには、minMatches 属性を使用できます。実質的に、これらの Match 要素は暗黙的な OR 演算子で結合されています。この Any 要素は、米国形式の日付またはいずれかのリストのキーワードが見つかった場合に満たされます。
  
![minMatches 属性を持つ Any 要素を示す XML マークアップ](media/385db1b1-571b-4a05-81b3-db28f5099c17.png)
  
### <a name="match-an-exact-subset-of-any-children-match-elements"></a>任意の子 Match 要素の完全サブセットと一致する

特定の数の Match 要素を満たすことを必須にするには、minMatches と maxMatches を同じ値に設定できます。この Any 要素は、完全に一致する日付またはキーワードが見つかった場合にのみ満たされます。また、パターンはマッチングされません。
  
![minMatches および maxMatches 属性を持つ Any 要素を示す XML マークアップ](media/97b10002-7781-42e8-ac5a-20ad8c5a887e.png)
  
### <a name="match-none-of-children-match-elements"></a>子 Match 要素のいずれとも一致しない

パターンを満たすための特定の証拠がないことを必須にするには、minMatches と maxMatches の両方を 0 に設定できます。この方法は、誤検知を示す可能性が高いキーワード一覧やその他の証拠がある場合に便利です。
  
たとえば、従業員 ID エンティティは "ID カード" を指している可能性があるため、キーワード "カード" を探しているとします。ただし、カードという単語が "クレジット カード" という語句内にのみ出現する場合、このコンテンツの "カード" が "ID カード" を示す可能性はあまりありません。そのため、パターンを満たす単語から除外する単語の一覧にキーワードとして "クレジット カード" を追加できます。
  
![0 の maxMatches 属性値を示す XML マークアップ](media/f81d44e5-3db8-48a8-8919-f483a386afdf.png)
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a>エンティティと他の証拠との近接度 [patternsProximity 属性]

機密情報の種類で従業員 ID を表すパターンを検索していて、そのパターンの一部として、"ID" などのキーワードのような補強証拠も検索する場合があります。この証拠が互いに近くにあるほど、パターンが実際の従業員 ID になる可能性が高くなります。パターン内の他の証拠とエンティティの近接度を判断するには、Entity 要素の必須の patternsProximity 属性を使用します。
  
![patternsProximity 属性を示す XML マークアップ](media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
エンティティ内の各パターンに対し、そのパターンに対して指定されたすべての他の一致について、patternsProximity 属性値で IdMatch の場所からの距離 (Unicode 文字) を定義します。近接ウィンドウは、IdMatch の場所によってアンカーされ、IdMatch の左側と右側にウィンドウが展開されます。
  
![近接ウィンドウの図](media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
以下の例は、従業員 ID のカスタム エンティティの IdMatch 要素で、キーワードまたは日付の少なくとも 1 つの補完的な一致を必要とするパターン マッチングに対して、近接ウィンドウがどのように影響するかを示しています。ID2 と ID3 の場合、近接ウィンドウ内に補強証拠がまったくないか、部分的にしかないため、ID1 のみが一致します。
  
![補強証拠と近接ウィンドウの図](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
メールの場合、メッセージ本文と各添付ファイルは、別のアイテムとして扱われる点に注意してください。つまり、近接ウィンドウは、これらの各アイテムの終端を超えて延長されないということです。各アイテム (添付ファイルまたは本文) に、idMatch と補強証拠の両方が存在している必要があります。
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a>パターンごとの適切な信頼度 [confidenceLevel 属性、recommendedConfidence 属性]

パターンに必要な証拠が多くなるほど、パターンが一致したときに実際のエンティティ (従業員 ID など) が特定される信頼度が高くなります。たとえば、9 桁の ID 番号、雇用日、近接度の高いキーワードが必要なパターンの場合、9 桁の ID 番号のみが必要なパターンよりも信頼度が高くなります。
  
Pattern 要素には必須の confidenceLevel 属性があります。confidenceLevel の値 (1 から 100 の整数) は、エンティティに含まれる各パターンの一意の ID と考えることができます。エンティティのパターンには、異なる信頼度を割り当てる必要があります。この整数を細かく指定することにあまり大きな意味はありません。社内のコンプライアンス チームにとって意味のある数値を選択してください。カスタムの機密情報の種類をアップロードし、DLP ポリシーを作成したら、作成するルールの条件でその信頼度を参照できます。
  
![confidenceLevel 属性にさまざまな値を持つ Pattern 要素を示す XML マークアップ](media/301e0ba1-2deb-4add-977b-f6e9e18fba8b.png)
  
エンティティには各 Pattern の confidenceLevel に加え、recommendedConfidence 属性があります。推奨される信頼度の属性は、ルールの既定の信頼度と考えることができます。DLP ポリシーにルールを作成するときに、使用するルールの信頼度を指定しない場合、そのエンティティの推奨される信頼度に基づいてルールのマッチングが行われます。
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-security-amp-compliance-center-localizedstrings-element"></a>セキュリティ/コンプライアンス センターの UI で他の言語をサポートする場合 [LocalizedStrings 要素]

コンプライアンス チームが Office 365 セキュリティ/コンプライアンス センターを使用して異なるロケールと異なる言語で DLP ポリシーを作成する場合、カスタムの機密情報の種類の名前と説明について、ローカライズされたバージョンを提供することができます。コンプライアンス チームがサポートしている言語で Office 365 を使用すると、ローカライズされた名前が UI に表示されます。
  
![インスタンス数と一致精度オプション](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
Rules 要素には、LocalizedStrings 要素を含める必要があります。LocalizedStrings 要素には、カスタム エンティティの GUID を参照する Resource 要素が含まれています。また、各 Resource 要素には、1 つまたは複数の Name 要素と Description 要素が含まれており、それぞれが langcode 属性を使用して特定の言語のローカライズされた文字列を提供します。
  
![LocalizedStrings 要素の内容を示す XML マークアップ](media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
ローカライズされた文字列は、カスタムの機密情報の種類がセキュリティ/コンプライアンス センターの UI でどのように表示されるかを指定するためにのみ使用できることに注意してください。ローカライズされた文字列を使用して、キーワード リストまたは正規表現の異なるローカライズ バージョンを提供することはできません。
  
## <a name="other-rule-package-markup-rulepack-guid"></a>その他のルール パッケージ マークアップ [RulePack GUID]

最後に、各 RulePackage の先頭には、入力する必要のある一般的な情報が含まれています。次のマークアップをテンプレートとして使用し、「. . .」プレースホルダーを自分の情報に置き換えることができます。
  
最も重要な点は、RulePack の GUID を生成する必要があることです。これまでにエンティティの GUID を生成しましたが、これは RulePack の 2 つ目の GUID です。GUID を生成するにはいくつかの方法がありますが、PowerShell では [guid]::NewGuid() と入力することで簡単に行うことができます。
  
Version 要素も重要です。ルール パッケージを初めてアップロードすると、Office 365 はバージョン番号を記録します。後でルール パッケージを更新して新しいバージョンをアップロードする場合は、バージョン番号を必ず更新してください。更新しないと、Office 365 で新しいルール パッケージが展開されません。
  
```
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    . . .
 </Rules>
</RulePackage>

```

完了すると、RulePack 要素は次のようになります。
  
![RulePack 要素を示す XML マークアップ](media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)
  
## <a name="changes-for-exchange-online"></a>Exchange Online の変更

以前は、DLP 用にカスタムの機密情報の種類をインポートするために Exchange Online PowerShell を使用することがありました。現在は、カスタムの機密情報の種類を Exchange 管理センターとセキュリティ/コンプライアンス センターの両方で使用できるようになりました。この改善の一環で、カスタムの機密情報の種類をインポートする場合、セキュリティ/コンプライアンス センター PowerShell の使用が必須になりました。Exchange PowerShell からはインポートできません。カスタムの機密情報の種類は以前と同様に使用できますが、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を変更した場合、Exchange 管理センターに表示されるまでに最大 1 時間かかる場合があります。
  
セキュリティ/コンプライアンス センターでは、`DlpSensitiveInformationTypeRulePackage` コマンドレットを使用してルール パッケージをアップロードします。これまでは、Exchange 管理センターで `ClassificationRuleCollection` コマンドレットを使用していました。 
  
## <a name="upload-your-rule-package"></a>ルール パッケージをアップロードする

ルール パッケージをアップロードするには、次の手順を実行します。
  
1. ルールを Unicode エンコードで .xml ファイルとして保存します。
    
2. [Office 365 セキュリティ/コンプライアンス センター PowerShell への接続](http://go.microsoft.com/fwlink/p/?LinkID=799771)
    
3. 次の構文を使用してください。

    ```
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte)
    ```

    この例では、MyNewRulePack.xml という名前の Unicode XML ファイルを C:\My Documents からアップロードします。

    ```
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte)
    ```

    構文とパラメーターの詳細情報については、[New-dlpsensitiveinformationtyperulepackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpsensitiveinformationtyperulepackage) をご覧ください。

5. 新しい機密情報の種類が正常に作成されたことを確認するには、次に示す手順のいずれかを実行します。

  - 次のコマンドを実行して、新しいルール パッケージが一覧表示されていることを確認します。

    ```
    Get-DlpSensitiveInformationTypeRulePackage
    ``` 

  - 次のコマンドを実行して、機密情報の種類が一覧表示されていることを確認します。

    ```
    Get-DlpSensitiveInformationType
    ``` 

    カスタムの機密情報の種類の場合、Publisher プロパティ値を Microsoft Corporation 以外に設定します。

  - \<Name\> を機密情報タイプの名前値 (たとえば、従業員 ID) に置き換えて、次のコマンドを実行します。

    ```
    Get-DlpSensitiveInformationType -Identity "<Name>"
    ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a>注意する必要がある潜在的な検証の問題

ルール パッケージの XML ファイルをアップロードすると、システムで XML が検証され、既知の不適切なパターンや明らかなパフォーマンスの問題が確認されます。検証で確認される既知の正規表現に関する問題について一部を紹介します。
  
- 先頭または末尾に縦棒 "|" を指定することはできません。これは、空の一致とみなされるため、あらゆるものと一致します。
    
    たとえば、"|a" や "b|" では検証に合格しません。
    
- 先頭または末尾に ".{0,m}" パターンを指定することはできません。これは機能的な目的がなく、単にパフォーマンスが低下します。
    
    たとえば、".{0,50}ASDF" や "ASDF.{0,50}" では検証に合格しません。
    
- ".{0,m}" や ".{1,m}" をグループに含めることはできません。また、".\*" や ".+" をグループに含めることはできません。
    
    たとえば、"(.{0,50000})" では検証に合格しません。
    
- "{0,m}" または "{1,m}" リピーターを含む文字はグループ内に含めることができません。
    
    たとえば、"(a\*)" では検証に合格しません。
    
- 先頭または末尾に ".{1,m}" を指定することはできません。代わりに、"." のみを使用してください。
    
    たとえば、".{1,m}asdf" では検証に合格しません。代わりに、".asdf" のみを使用してください。
    
- グループに無制限のリピーター (「\*」や「+」など) を含めることはできません。
    
    たとえば、"(xx)\*" や "(xx)+" では検証に合格しません。
    
パフォーマンスに影響する可能性のある問題がカスタムの機密情報の種類に含まれている場合は、アップロードされず、次のいずれかのエラー メッセージが表示されることがあります。
  
- **予想よりも多くのコンテンツに一致する汎用的な限定詞 (‘+’、‘\*’ など)**
    
- **ルックアラウンド アサーション**
    
- **複雑なグループ化と汎用的な限定詞の併用**
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a>コンテンツを再クロールして機密情報を特定する

DLP は、検索クローラーを使用して、サイト コンテンツ内の機密情報を特定し、分類しています。SharePoint Online サイトと OneDrive for Business サイトのコンテンツが更新されると、自動的に再クロールされます。ただし、既存のすべてのコンテンツで新しいカスタムの機密情報の種類を特定するには、そのコンテンツを再クロールする必要があります。
  
Office 365 でテナント全体の再クロールを手動で要求することはできませんが、サイト コレクション、リスト、またはライブラリに対して再クロールすることはできます。詳細については、「[サイト、ライブラリ、またはリストのクロールとインデックス再作成を手動で要求する](https://support.office.com/article/9afa977d-39de-4321-b4ca-8c7c7e6d264e)」を参照してください。
  
## <a name="remove-a-custom-sensitive-information-type"></a>カスタムの機密情報の種類を削除する

**注**: カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。

セキュリティ/コンプライアンス センターの PowerShell では、カスタムの機密情報の種類を削除する 2 つの方法があります。

- **個々のカスタムの機密情報の種類を削除する**: 「[カスタムの機密情報の種類を変更する](#modify-a-custom-sensitive-information-type)」に記載されている方法を使用します。カスタムの機密情報の種類を含むカスタム ルール パッケージをエクスポートし、XML ファイルから機密情報の種類を削除して、更新された XML ファイルを既存のカスタム ルール パッケージにインポートします。

- **カスタム ルール パッケージとそれに含まれるすべてのカスタムの機密情報の種類を削除する**: この方法は、このセクションに記載されています。

1. [Office 365 セキュリティ/コンプライアンス センター PowerShell への接続](http://go.microsoft.com/fwlink/p/?LinkID=799771)

2. カスタム ルール パッケージを削除するには、次の構文を使用します。

    ```
    Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
    ```

    Name 値 (任意の言語) または `RulePack id` (GUID) 値を使用して、ルール パッケージを識別します。

    この例では、"Employee ID Custom Rule Pack" (従業員 ID カスタム ルール パック) という名前のルール パッケージを削除します。

    ```
       Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
    ```

    構文とパラメーターの詳細情報については、[Remove-dlpsensitiveinformationtyperulepackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/remove-dlpsensitiveinformationtyperulepackage) をご覧ください。

3. カスタムの機密情報の種類が正常に削除されたことを確認するには、次に示す手順のいずれかを実行します。

  - 次のコマンドを実行して、ルール パッケージが一覧表示されなくなったことを確認します。

    ```
    Get-DlpSensitiveInformationTypeRulePackage
    ``` 

  - 次のコマンドを実行し、削除されたルール パッケージで機密情報の種類が一覧表示されなくなったことを確認します。

    ```
    Get-DlpSensitiveInformationType
    ``` 

    カスタムの機密情報の種類の場合、Publisher プロパティ値を Microsoft Corporation 以外に設定します。

  - \<Name\> を機密情報タイプの名前値 (たとえば、従業員 ID) に置き換えて、次のコマンドを実行し、機密情報の種類が一覧表示されなくなったことを確認します。

    ```
    Get-DlpSensitiveInformationType -Identity "<Name>"
    ```

## <a name="modify-a-custom-sensitive-information-type"></a>カスタムの機密情報の種類を変更する

セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を変更するには、次のようにする必要があります。

1. カスタムの機密情報の種類が含まれている既存のルール パッケージを XML ファイル (または、ある場合は既存の XML ファイル) にエクスポートします。 

2. エクスポートした XML ファイルで、カスタムの機密情報の種類を変更します。

3. 更新した XML ファイルを既存のルール パッケージにインポートします。

セキュリティ/コンプライアンス センターの PowerShell に接続するには、「[Office 365 セキュリティ/コンプライアンス センター PowerShell への接続](http://go.microsoft.com/fwlink/p/?LinkID=799771)」を参照してください。

#### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>手順 1: 既存のルール パッケージを XML ファイルにエクスポートします

**注**: XML ファイルのコピーがある場合 (たとえば、先ほど作成してインポートした場合)、次の手順に進んで、XML ファイルを変更することができます。

1. カスタム ルール パッケージの名前を知らない場合、次のコマンドを実行して確認します。

    ```
    Get-DlpSensitiveInformationTypeRulePackage
    ```

    **注**: 組み込みの機密情報の種類が含まれる組み込みのルール パッケージは、Microsoft Rule Package と呼ばれます。セキュリティ/コンプライアンス センターの UI で作成したカスタムの機密情報の種類が含まれるルール パッケージは Microsoft.SCCManaged.CustomRulePack と呼ばれます。

2. カスタム ルール パッケージを変数に格納するには、次の構文を使用します。

    ```
    $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
    ```

   たとえば、ルール パッケージの名前が "Employee ID Custom Rule Pack" (従業員 ID カスタム ルール パック) の場合、次のコマンドを実行します。

    ```
    $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
    ```

3. カスタム ルール パッケージを XML ファイルにエクスポートするには、次の構文を使用します。

    ```
    Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
    ```

    この例では、ルール パッケージを C:\My Documents フォルダーの ExportedRulePackage.xml という名前のファイルにエクスポートします。

    ```
    Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
    ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>手順 2: エクスポートした XML ファイルでカスタムの機密情報の種類を変更します

XML ファイル内の機密情報の種類、およびファイル内の他の要素については、このトピックで前述されています。

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>手順 3: 更新した XML ファイルを既存のルール パッケージにインポートします

更新した XML ファイルを既存のルール パッケージにインポートするには、次の構文を使用します。

```
Set-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity" -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte)
```

Name 値または `RulePack id` (GUID) 値を使用して、ルール パッケージを識別します。

この例では、MyUpdatedRulePack.xml という名前の更新した Unicode XML ファイルを、C:\My Documents から "Employee ID Custom Rule Pack" (従業員 ID カスタム ルール パック) という名前の既存のルール パッケージにアップロードします。

```
Set-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack" -FileData (Get-Content -Path "C:\My Documents\MyUpdatedRulePack.xml" -Encoding Byte)
```

構文とパラメーターの詳細情報については、[Set-DlpSensitiveInformationTypeRulePackage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpsensitiveinformationtyperulepackage) をご覧ください。

## <a name="reference-rule-package-xml-schema-definition"></a>リファレンス: ルール パッケージ XML スキーマの定義

このマークアップをコピーし、XSD ファイルとして保存して、ルール パッケージの XML ファイルの検証に使用できます。
  
```
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="http://schemas.microsoft.com/office/2011/mce"
           targetNamespace="http://schemas.microsoft.com/office/2011/mce" 
           xmlns:xs="http://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>        
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>

```

## <a name="more-information"></a>詳細情報

- [データ損失防止ポリシーの概要](data-loss-prevention-policies.md)
    
- [機密情報の種類で検索される情報](what-the-sensitive-information-types-look-for.md)
    
- [DLP 関数で探索する内容](what-the-dlp-functions-look-for.md)
    

