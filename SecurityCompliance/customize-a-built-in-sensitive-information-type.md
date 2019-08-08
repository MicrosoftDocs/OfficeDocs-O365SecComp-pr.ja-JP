---
title: 組み込みの機密情報の種類をカスタマイズする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: コンテンツから機密情報を探すときには、ルールと呼ばれるものの中にその情報を記述する必要があります。データ損失防止 (DLP) には、すぐに利用できる最も一般的な機密情報の種類を表すルールが含まれています。これらのルールを使用するには、それらをポリシーの中に組み込む必要があります。これらの組み込みのルールを組織の特定のニーズに合わせて調整する必要がある場合は、カスタムの機密情報の種類を作成することができます。このトピックでは、クレジット カード情報である可能性のある情報をより幅広い範囲で検出できるように、既存のルール コレクションが入っている XML ファイルをカスタマイズする方法について説明します。
ms.openlocfilehash: 2944202bf0f44c1a46834dce580abaf4f04aa40b
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230731"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="6d195-107">組み込みの機密情報の種類をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="6d195-107">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="6d195-p102">コンテンツから機密情報を探すときには、*ルール*と呼ばれるものの中にその情報を記述する必要があります。データ損失防止 (DLP) には、すぐに利用できる最も一般的な機密情報の種類を表すルールが含まれています。これらのルールを使用するには、それらをポリシーの中に組み込む必要があります。これらの組み込みのルールを組織の特定のニーズに合わせて調整する必要がある場合は、カスタムの機密情報の種類を作成することができます。このトピックでは、クレジット カード情報である可能性のある情報をより幅広い範囲で検出できるように、既存のルール コレクションが入っている XML ファイルをカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d195-p102">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  . Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away. To use these rules, you have to include them in a policy. You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type. This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="6d195-p103">この例は、これ以外の組み込みの機密情報の種類に適用することもできます。機密情報の既定の種類と XML 定義のリストについては、「[機密情報の種類の検索基準](what-the-sensitive-information-types-look-for.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d195-p103">You can take this example and apply it to other built-in sensitive information types. For a list of default sensitive information types and XML definitions, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="6d195-115">現在のルールの XML ファイルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="6d195-115">Export the XML file of the current rules</span></span>

<span data-ttu-id="6d195-116">XML をエクスポートするには、[リモート PowerShell を介してセキュリティ/コンプライアンス センターに接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d195-116">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="6d195-p104">PowerShell で次のように入力すると、組織のルールが画面上に表示されます。まだ独自のルールを作成していない場合は、"Microsoft Rule Package" というラベルの付いた既定の組み込みルールだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d195-p104">In the PowerShell, type the following to display your organization's rules on screen. If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>
    
     `Get-DlpSensitiveInformationTypeRulePackage`
    
2. <span data-ttu-id="6d195-p105">組織のルールを変数に格納するため、次のように入力します。変数に情報を格納すると、後ほどリモート PowerShell コマンドで使用するフォーマットの中で簡単に利用できます。</span><span class="sxs-lookup"><span data-stu-id="6d195-p105">Store your organization's rules in a in a variable by typing the following. Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>
    
     `$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage`
    
3. <span data-ttu-id="6d195-p106">そのデータをすべて含む書式設定した XML ファイルを作成するために、次のように入力します (`Set-content` は、ファイルに XML を書き込むコマンドレットの一部です。)</span><span class="sxs-lookup"><span data-stu-id="6d195-p106">Make a formatted XML file with all that data by typing the following. ( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 
    
     `Set-Content -path "C:\custompath\exportedRules.xml" -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection`
    
    > [!IMPORTANT]
    > <span data-ttu-id="6d195-p107">ルール パックが実際に格納されている場所を指定してください。`C:\custompath\` はプレースホルダーです。</span><span class="sxs-lookup"><span data-stu-id="6d195-p107">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="6d195-125">変更する必要のあるルールを XML の中から見つける</span><span class="sxs-lookup"><span data-stu-id="6d195-125">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="6d195-p108">上記のコマンドレットによって、既定のルールを含む*ルール コレクション* 全体がエクスポートされます。この中から、修正しようとしているクレジット カード番号のルールを探す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d195-p108">The cmdlets above exported the entire  *rule collection*  , which includes the default rules we provide. Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="6d195-128">前のセクションでエクスポートした XML ファイルをテキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="6d195-128">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="6d195-p109">下へスクロールして `<Rules>` タグに移動します。ここが、DLP ルールを含むセクションの先頭です。(この XML ファイルにはルール コレクション全体の情報が含まれているため、ルールの部分を表示するには、先頭にある他の情報をスキップする必要があります。)</span><span class="sxs-lookup"><span data-stu-id="6d195-p109">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules. (Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.)</span></span> 
    
3. <span data-ttu-id="6d195-p110">クレジット カード番号のルール定義を見つけるため、*Func_credit_card* を探します。XML ではルール名にスペースを含めることができないため、スペースは通常、アンダースコアで置き換えられます。また、ルール名が省略形になることもあります。たとえば、米国の社会保障番号 (Social Security number) のルールは、"SSN" という省略形になります。クレジット カード番号のルールの XML は、次のコード サンプルのようなものです。</span><span class="sxs-lookup"><span data-stu-id="6d195-p110">Look for  *Func_credit_card*  to find the Credit Card Number rule definition. (In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated. An example of this is the U.S. Social Security number rule, which is abbreviated "SSN." The Credit Card Number rule XML should look like the following code sample.</span></span> 
    
  ```
  <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
         patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
         <IdMatch idRef="Func_credit_card" />
          <Any minMatches="1">
            <Match idRef="Keyword_cc_verification" />
            <Match idRef="Keyword_cc_name" />
            <Match idRef="Func_expiration_date" />
          </Any>
        </Pattern>
      </Entity>
  ```

<span data-ttu-id="6d195-p111">XML 内でクレジット カード番号のルール定義が見つかったら、ニーズに合わせてルールの XML をカスタマイズします。(XML 定義の詳細については、このトピックの最後にある「[用語集](#term-glossary)」を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="6d195-p111">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs. (For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.)</span></span> 
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="6d195-137">XML を変更し、新しい機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="6d195-137">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="6d195-p112">既定のルールは直接変更できないため、最初に、新しい機密情報の種類を作成する必要があります。カスタムの機密情報の種類では、さまざまなことができます。その概要については、「[セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。この例では、シンプルにするため、クレジット カード番号ルールの補強証拠を削除し、キーワードを追加するだけにします。</span><span class="sxs-lookup"><span data-stu-id="6d195-p112">First, you need to create a new sensitive information type because you can't directly modify the default rules. You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="6d195-p113">すべての XML ルール定義は、次のような一般的なテンプレートに基づいて作成されます。テンプレート内でクレジット カード番号定義 XML をコピーしてから貼り付け、いくつかの値を変更する必要があります (次の例の ".. ." プレースホルダーに注意してください)。続いて、変更された XML をポリシーで使用できる新しいルールとしてアップロードします。</span><span class="sxs-lookup"><span data-stu-id="6d195-p113">All XML rule definitions are built on the following general template. You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ". . ." placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
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
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

<span data-ttu-id="6d195-p114">ここまでで、次の例のような XML ができあがります。ルール パッケージとルールは独自の GUID によって識別されるため、2 つの一意な GUID を生成する必要があります。1 つはルール パッケージのため、もう 1 つはクレジット カード番号ルールの GUID を置き換えるために使用します。(次のコード例のエンティティ ID に指定されている GUID は、組み込みルール定義の GUID であるため、新しい GUID で置き換える必要があります。)GUID を生成するにはいくつかの方法がありますが、PowerShell で「 **[guid]::NewGuid()** 」と入力すれば容易に生成できます。</span><span class="sxs-lookup"><span data-stu-id="6d195-p114">Now, you have something that looks similar to the following XML. Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule. (The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.) There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
```
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="6d195-149">機密情報の種類から補強証拠の要件を削除する</span><span class="sxs-lookup"><span data-stu-id="6d195-149">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="6d195-p115">ここまでで、セキュリティ/コンプライアンス センターにアップロードできる新しい機密情報の種類を作成できました。次の手順は、ルールをもう少し具体的にすることです。チェックサムの条件を満たす 16 桁の番号だけを検索し、追加の (補強) 証拠 (たとえば、キーワード) を必要としないように、ルールを変更します。これを行うには、XML のうち補強証拠を探している部分を削除する必要があります。クレジット カード番号の近くには特定のキーワードや有効期限があるのが普通なので、誤検知を減らすために補強証拠が非常に役立ちます。その証拠を削除する場合は、クレジット カード番号を見つけた場合の `confidenceLevel` を低い値に調整する必要があります (この例では 85)。</span><span class="sxs-lookup"><span data-stu-id="6d195-p115">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific. Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence (for example keywords). To do this, you need to remove the part of the XML that looks for corroborative evidence. Corroborative evidence is very helpful in reducing false positives because usually there are certain keywords or an expiration date near the credit card number. If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>
  
```
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="6d195-155">組織に固有のキーワードを探す</span><span class="sxs-lookup"><span data-stu-id="6d195-155">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="6d195-p116">補強証拠が必要であるものの、異なるキーワードまたは追加のキーワードを指定し、その証拠を探す場所を変更する必要がある場合について考えてみましょう。16 桁の番号の前後から補強証拠を探す範囲を拡大または縮小するため、`patternsProximity` を調整することができます。独自のキーワードを追加するには、キーワード リストを定義し、それをルールの中で参照する必要があります。次の XML では、キーワードとして "company card" と "Contoso card" を追加し、これらの語句がクレジット カード番号の前後 150 文字以内に含まれるメッセージをクレジット カード番号として識別します。</span><span class="sxs-lookup"><span data-stu-id="6d195-p116">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence. You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number. To add your own keywords, you need to define a keyword list and reference it within your rule. The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span> 
  
```
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a><span data-ttu-id="6d195-160">ルールをアップロードする</span><span class="sxs-lookup"><span data-stu-id="6d195-160">Upload your rule</span></span>

<span data-ttu-id="6d195-161">ルールをアップロードするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d195-161">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="6d195-p117">ルールを Unicode エンコードの .xml ファイルとして保存します。これとは違うエンコードでファイルを保存すると、ルールが機能しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6d195-p117">Save it as an .xml file with Unicode encoding. This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. [<span data-ttu-id="6d195-164">リモート PowerShell を介してセキュリティ/コンプライアンス センターに接続する</span><span class="sxs-lookup"><span data-stu-id="6d195-164">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. <span data-ttu-id="6d195-165">PowerShell で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6d195-165">In the PowerShell, type the following.</span></span>
    
     <span data-ttu-id="6d195-166">`New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)`</span><span class="sxs-lookup"><span data-stu-id="6d195-166">`New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)`.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6d195-p118">ルール パックが実際に格納されている場所を指定してください。`C:\custompath\` はプレースホルダーです。</span><span class="sxs-lookup"><span data-stu-id="6d195-p118">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="6d195-169">確認のために「Y」と入力し、**ENTER** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6d195-169">To confirm, type Y, and then press **Enter**.</span></span>
    
5. <span data-ttu-id="6d195-170">新しいルールがアップロードされたことを確認するため、`Get-DlpSensitiveInformationType` と入力します。新しいルールの名前が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="6d195-170">Verify that your new rule was uploaded by typing  `Get-DlpSensitiveInformationType`, which now displays the name of your rule.</span></span>
    
<span data-ttu-id="6d195-p119">機密情報の検出に新しいルールを使用するようにするには、ルールを DLP ポリシーに追加する必要があります。ルールをポリシーに追加する方法については、「[テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d195-p119">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy. To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="6d195-173">用語集</span><span class="sxs-lookup"><span data-stu-id="6d195-173">Term glossary</span></span>

<span data-ttu-id="6d195-174">このトピックの手順に登場した用語の定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d195-174">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="6d195-175">**用語**</span><span class="sxs-lookup"><span data-stu-id="6d195-175">**Term**</span></span>|<span data-ttu-id="6d195-176">**定義**</span><span class="sxs-lookup"><span data-stu-id="6d195-176">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6d195-177">エンティティ</span><span class="sxs-lookup"><span data-stu-id="6d195-177">Entity</span></span>|<span data-ttu-id="6d195-p120">エンティティとは、機密情報の種類 (たとえば、クレジット カード番号) のことです。各エンティティには、その ID として一意の GUID があります。GUID をコピーして XML 内で検索すると、XML ルール定義と XML ルールをローカライズしたすべての翻訳版が見つかります。また、翻訳版の GUID を検索して定義を見つけ、その GUID を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="6d195-p120">Entities are what we call sensitive information types, such as credit card numbers. Each entity has a unique GUID as its ID. If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule. You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="6d195-182">= (式) フィールドで使用できる関数</span><span class="sxs-lookup"><span data-stu-id="6d195-182">Functions</span></span>|<span data-ttu-id="6d195-p121">XML ファイルが参照する `Func_credit_card` は、コンパイル済みコードでは関数です。関数は、複雑な正規表現を実行し、チェックサムが組み込みルールと一致することを確認するために使用されます。これはコード内で実行されるため、一部の変数は XML ファイルに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="6d195-p121">The XML file references  `Func_credit_card`, which is a function in compiled code. Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="6d195-185">IdMatch</span><span class="sxs-lookup"><span data-stu-id="6d195-185">IdMatch</span></span>|<span data-ttu-id="6d195-186">一致が照合されるパターンの ID です (たとえば、クレジット カード番号)。</span><span class="sxs-lookup"><span data-stu-id="6d195-186">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="6d195-187">キーワード リスト</span><span class="sxs-lookup"><span data-stu-id="6d195-187">Keyword lists</span></span>|<span data-ttu-id="6d195-p122">XML ファイルでは、`keyword_cc_verification` および `keyword_cc_name` も参照します。これらは、エンティティの前後 `patternsProximity` 文字以内から一致を探すキーワードのリストです。現在のところ、これらは XML 内に表示されません。</span><span class="sxs-lookup"><span data-stu-id="6d195-p122">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity. These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="6d195-190">パターン</span><span class="sxs-lookup"><span data-stu-id="6d195-190">Pattern</span></span>|<span data-ttu-id="6d195-p123">パターンは、一致を検索する機密情報の種類の内容を示すリストです。これには、キーワード、正規表現、および内部関数 (チェックサムの検査などのタスクを実行する) が含まれます。機密情報の種類には、固有の信頼レベルを持つ複数のパターンを指定することができます。これは、補強証拠が見つかる場合に高い信頼レベルを返し、補強証拠が少ししか、あるいはまったく見つからない場合に低い信頼レベルを返す、という機密情報の種類を作成する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6d195-p123">The pattern contains the list of what the sensitive type is looking for. This includes keywords, regexes, and internal functions (that perform tasks like verifying checksums). Sensitive information types can have multiple patterns with unique confidences. This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="6d195-195">パターンの confidenceLevel</span><span class="sxs-lookup"><span data-stu-id="6d195-195">Pattern confidenceLevel</span></span>|<span data-ttu-id="6d195-p124">DLP エンジンが一致を検索した内容の信頼性のレベルです。信頼性のレベルは、パターンの要件が満たされた場合のパターンへの一致に関連付けられます。これは、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を使用するときに考慮する必要のある信頼性の尺度です。</span><span class="sxs-lookup"><span data-stu-id="6d195-p124">This is the level of confidence that the DLP engine found a match. This level of confidence is associated with a match for the pattern if the pattern's requirements are met. This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="6d195-199">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="6d195-199">patternsProximity</span></span>|<span data-ttu-id="6d195-200">クレジット カード番号パターンらしき情報が見つかった場合、`patternsProximity` はその番号からどの程度近接した範囲内で補強証拠の探索を行うかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d195-200">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="6d195-201">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="6d195-201">recommendedConfidence</span></span>|<span data-ttu-id="6d195-p125">このルールに対して推奨される信頼レベルです。推奨される信頼性は、エンティティとアフィニティに適用されます。エンティティの場合、この数値がパターンの `confidenceLevel` に対して評価されることはありません。この数値は、必要な場合に信頼レベルを選択するために役立つ提案にすぎません。アフィニティの場合、メール フロー ルール アクションが呼び出されるためには、パターンの `confidenceLevel` が `recommendedConfidence` の数値を上回っている必要があります。`recommendedConfidence` は、アクションを起動するメール フロー ルールで使用される既定の信頼レベルです。必要であれば、この代わりにパターンの信頼レベルに基づいてメール フロー ルールを起動するように手動で変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="6d195-p125">This is the confidence level we recommend for this rule. The recommended confidence applies to entities and affinities. For entities, this number is never evaluated against the  `confidenceLevel` for the pattern. It's merely a suggestion to help you choose a confidence level if you want to apply one. For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked. The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action. If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|
   
## <a name="for-more-information"></a><span data-ttu-id="6d195-209">関連情報</span><span class="sxs-lookup"><span data-stu-id="6d195-209">For more information</span></span>

- [<span data-ttu-id="6d195-210">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="6d195-210">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="6d195-211">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="6d195-211">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    
- [<span data-ttu-id="6d195-212">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="6d195-212">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    

