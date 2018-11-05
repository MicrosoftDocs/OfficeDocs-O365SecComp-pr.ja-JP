---
title: カスタムの機密情報の種類を作成する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Office 365 セキュリティ/コンプライアンス センターのグラフィカル ユーザー インターフェイスで DLP のカスタム機密情報の種類を作成、変更、削除、およびテストする方法について説明します。
ms.openlocfilehash: cd7041ee9c20038fb7cb0c337f31d7cef7f7192d
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857295"
---
# <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="1f081-103">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="1f081-103">Create a custom sensitive information type</span></span>

<span data-ttu-id="1f081-p101">Office 365 のデータ損失防止 (DLP) には、[機密情報の種類](what-the-sensitive-information-types-look-for.md)が多数含まれており、DLP ポリシーで使用するための準備が整っています。これらの組み込みの種類は、クレジット カード番号、銀行口座番号、パスポート番号などの特定と保護に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1f081-p101">Data loss prevention (DLP) in Office 365 includes many [sensitive information types](what-the-sensitive-information-types-look-for.md) that are ready for you to use in your DLP policies. These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span></span> 

<span data-ttu-id="1f081-106">ただし、組織に固有の形式を使用する従業員 ID やプロジェクト番号など、さまざまな種類の機密情報を特定して保護する必要がある場合は、カスタムの機密情報の種類を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1f081-106">But if you need to identify and protect a different type of sensitive information - for example, an employee ID that uses a format specific to your organization - you can create a custom sensitive information type. A sensitive information type is defined in an XML file called a rule package.</span></span>

<span data-ttu-id="1f081-107">カスタムの機密情報の種類の基本的な部分は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f081-107">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="1f081-108">**プライマリ パターン**: 従業員 ID 番号、プロジェクト番号など。これは通常、正規表現 (RegEx) によって識別されますが、キーワード リストにもできます。</span><span class="sxs-lookup"><span data-stu-id="1f081-108">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="1f081-p102">**追加の証拠**: 9 桁の従業員 ID 番号を探していると仮定します。9 桁の数字がすべて従業員 ID 番号ではないので、「従業員」、「社員証」、「ID」などのキーワードや追加の正規表現を基にして、別のテキスト パターンを検索できます。この補強証拠 (_補強_または_裏付け_証拠とも呼ばれる) は、コンテンツに含まれる 9 桁の数字が実際に従業員 ID 番号である可能性を高めます。</span><span class="sxs-lookup"><span data-stu-id="1f081-p102">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="1f081-p103">**文字の近接**: プライマリ パターンと補強証拠が互いに近いほど、検出されたコンテンツが探しているものになる可能性が高くなります。次の図に示すように、プライマリ パターンと補強証拠との文字の距離 (_近接ウィンドウ_とも呼ばれる) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f081-p103">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![補強証拠と近接ウィンドウの図](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="1f081-p104">**信頼レベル**: 持っている補強証拠が多ければ多いほど、探している機密情報と一致する可能性が高くなります。より多くの証拠を使用して検出された一致には、より高いレベルの信頼を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1f081-p104">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="1f081-p105">パターンを満たす場合は、数と信頼度が返され、DLP ポリシーの条件に使用できます。機密情報の種類を検出する条件を DLP ポリシーに追加する場合、次の図に示すように、数と信頼度を編集できます。</span><span class="sxs-lookup"><span data-stu-id="1f081-p105">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policy. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown here. Confidence level (also called match accuracy) is explained later in this topic.</span></span>

    ![インスタンス数と一致精度オプション](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

<span data-ttu-id="1f081-120">次のオプションを使用して、Office 365 セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f081-120">To create custom sensitive information types in the Office 365 Security & Compliance Center, you have the following options:</span></span>

- <span data-ttu-id="1f081-p106">**UI を使用**: この方法は簡単で高速ですが、PowerShell よりも構成オプションが少なくなります。このトピックの残りの部分では、これらの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f081-p106">**Use the UI**: This method is easier and faster, but you have less configuration options than PowerShell. The rest of this topic describes these procedures.</span></span>

- <span data-ttu-id="1f081-p107">**PowerShell を使用**: この方法では、まず機密情報の種類を 1 つ以上含む XML ファイル (_ルール パッケージ_と呼ばれる) を作成し、次に、PowerShell を使用してルール パッケージをインポートします (ルール パッケージのインポートは、ルール パッケージの作成と比べて簡単です)。この方法は UI より格段複雑ですが、より多くの構成オプションを使用できます。手順については、「[Office 365 セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f081-p107">**Use PowerShell**: This method requires that you first create an XML file (called a _rule package_) that contains one or more sensitive information types, and then you use PowerShell to import the rule package (importing the rule package is trivial compared to creating the rule package. This method is much more complex than the UI, but you have more configuration options. For instructions, see [Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

<span data-ttu-id="1f081-126">次の表で主な違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1f081-126">The differences are described in the following list:</span></span>

|<span data-ttu-id="1f081-127">UI でのカスタムの機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="1f081-127">Custom sensitive information types in the UI</span></span>|<span data-ttu-id="1f081-128">PowerShell でのカスタムの機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="1f081-128">Custom sensitive information types in PowerShell</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f081-129">名前と説明は 1 つの言語</span><span class="sxs-lookup"><span data-stu-id="1f081-129">Name and Description are in one language</span></span>|<span data-ttu-id="1f081-130">名前と説明は複数の言語をサポート</span><span class="sxs-lookup"><span data-stu-id="1f081-130">Supports multiple languages for Name and Description</span></span>|
|<span data-ttu-id="1f081-131">1 つのパターン (プライマリ パターン) をサポート。</span><span class="sxs-lookup"><span data-stu-id="1f081-131">Supports one pattern (the primary pattern).</span></span>|<span data-ttu-id="1f081-132">プライマリ パターンの他に複数のパターンをサポート。</span><span class="sxs-lookup"><span data-stu-id="1f081-132">Supports multiple patterns in addition to the primary pattern.</span></span>|
|<span data-ttu-id="1f081-133">補強証拠は次のものにできます。</span><span class="sxs-lookup"><span data-stu-id="1f081-133">Supporting evidence can be:</span></span> <br/><span data-ttu-id="1f081-134">• 正規表現</span><span class="sxs-lookup"><span data-stu-id="1f081-134">• Regular expressions</span></span> <br/><span data-ttu-id="1f081-135">• キーワード</span><span class="sxs-lookup"><span data-stu-id="1f081-135">• Keywords</span></span> <br/><span data-ttu-id="1f081-136">• キーワード辞書</span><span class="sxs-lookup"><span data-stu-id="1f081-136">• Keyword dictionaries</span></span>|<span data-ttu-id="1f081-137">補強証拠は次のものにできます。</span><span class="sxs-lookup"><span data-stu-id="1f081-137">Supporting evidence can be:</span></span> <br/><span data-ttu-id="1f081-138">• 正規表現</span><span class="sxs-lookup"><span data-stu-id="1f081-138">• Regular expressions</span></span> <br/><span data-ttu-id="1f081-139">• キーワード</span><span class="sxs-lookup"><span data-stu-id="1f081-139">• Keywords</span></span> <br/><span data-ttu-id="1f081-140">• キーワード辞書</span><span class="sxs-lookup"><span data-stu-id="1f081-140">• Keyword dictionaries</span></span> <br/><span data-ttu-id="1f081-141">• [組み込み DLP 関数](what-the-dlp-functions-look-for.md)</span><span class="sxs-lookup"><span data-stu-id="1f081-141">• [Built-in DLP functions](what-the-dlp-functions-look-for.md)</span></span>|
|<span data-ttu-id="1f081-142">機密情報の種類に対して信頼レベルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1f081-142">Confidence level is configurable for the sensitive information type.</span></span>|<span data-ttu-id="1f081-143">機密情報の種類と、その中の個々のパターンに対して、信頼レベルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1f081-143">Confidence level is configurable for the sensitive information type and each individual pattern within.</span></span>|
|<span data-ttu-id="1f081-144">パターンの一致には、プライマリ パターンとすべて補強証拠 (暗黙の AND 演算子を使用) の検出が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f081-144">Pattern match requires the detection of the primary pattern and all supporting evidence (the implicit AND operator is used).</span></span>|<span data-ttu-id="1f081-145">パターンの一致には、プライマリ パターンと構成可能な補強証拠の量 (暗黙の AND および OR 演算子が使用可能) の検出が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f081-145">Pattern match requires the detection of the primary pattern and a configurable amount of supporting evidence (implicit AND and OR operators can be used).</span></span>|

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1f081-146">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="1f081-146">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1f081-147">セキュリティ/コンプライアンス センターを開くには、「[Office 365 のセキュリティ センターとコンプライアンス センターに移動する](go-to-the-securitycompliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f081-147">To open the Security & Compliance Center, see [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span>

- <span data-ttu-id="1f081-p108">カスタムの機密情報の種類では、正規表現 (RegEx) に精通している必要があります。テキストの処理に使用される .NET RegEx エンジンの詳細については、「[.NET 正規表現](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f081-p108">Custom sensitive information types require familiarity with regular expressions (RegEx). For additional information on the .NET RegEx engine that's used for processing the text, see [.NET Regular Expressions](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions).</span></span>

  <span data-ttu-id="1f081-p109">Microsoft カスタマー サービス & サポートは、カスタムのコンテンツ一致定義 (カスタムの分類や正規表現パターンの作成) の提供を支援できません。サポート エンジニアは、機能の制限付きサポート (たとえば、テスト目的でサンプルの正規表現パターンを提供したり、期待どおりにトリガーされない既存の正規表現パターンのトラブルシューティングを支援するなど) は提供できますが、カスタムのコンテンツ一致の開発がユーザーの要件を満たしたり、義務を果たすことを確約できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1f081-p109">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="1f081-152">テキストの処理に使用される .NET RegEx エンジンの詳細については、「[.NET の正規表現](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f081-152">For additional information on the .NET regex engine that's used for processing the text, see the documentaiton on [Regular Expressions in .NET](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions).</span></span>

- <span data-ttu-id="1f081-p110">DLP は検索クローラーを使用して、SharePoint Online サイトと OneDrive for Business サイトの機密情報を識別および分類します。既存のコンテンツで新しいカスタムの機密情報の種類を特定するには、コンテンツを再クロールする必要があります。コンテンツはスケジュールに基づいて再クロールされますが、サイト コレクション、リスト、またはライブラリのコンテンツは手動で再クロールできます。詳細については、「[サイト、ライブラリ、またはリストのクロールとインデックス再作成を手動で要求する](https://docs.microsoft.com/sharepoint/crawl-site-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f081-p110">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites. To identify your new custom sensitive information type in existing content, the content must be recrawled. Content is recrawled based on a schedule, but you can manually recrawl content for a site collection, list, or library. For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="1f081-157">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="1f081-157">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="1f081-158">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f081-158">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="1f081-159">各設定については説明するまでもありませんが、ウィザードの関連ページには説明が記載されています。</span><span class="sxs-lookup"><span data-stu-id="1f081-159">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="1f081-160">**[名前]**</span><span class="sxs-lookup"><span data-stu-id="1f081-160">**Name**</span></span>

- <span data-ttu-id="1f081-161">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="1f081-161">**Description**</span></span>

- <span data-ttu-id="1f081-162">**[近接性]**</span><span class="sxs-lookup"><span data-stu-id="1f081-162">**Proximity**</span></span>

- <span data-ttu-id="1f081-163">**[信頼度]**</span><span class="sxs-lookup"><span data-stu-id="1f081-163">**Confidence level**</span></span>

- <span data-ttu-id="1f081-164">**[プライマリ パターン要素]** (キーワード、正規表現、またはディクショナリ)</span><span class="sxs-lookup"><span data-stu-id="1f081-164">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="1f081-165">オプションの **[補強パターン要素]** (キーワード、正規表現、またはディクショナリ) および対応する **[最小コスト]** 値。</span><span class="sxs-lookup"><span data-stu-id="1f081-165">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="1f081-p111">この例のシナリオ: キーワードの「従業員」、「ID」および「社員証」と共に、コンテンツに含まれる 9 桁の従業員番号を検出するために、カスタムの機密情報の種類が必要になりました。このカスタムの機密情報の種類を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f081-p111">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="1f081-168">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f081-168">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

2. <span data-ttu-id="1f081-169">**[名前と説明の選択]** ページが開いたら、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f081-169">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="1f081-170">**[名前]**: 従業員 ID。</span><span class="sxs-lookup"><span data-stu-id="1f081-170">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="1f081-171">**[説明]**: 9 桁の Contoso 従業員 ID 番号を検出します。</span><span class="sxs-lookup"><span data-stu-id="1f081-171">**Description** Detect nine-digit Contoso employee ID numbers.</span></span>

  <span data-ttu-id="1f081-172">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f081-172">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="1f081-173">**[一致の要件]** ページが開いたら、**[要素の追加]** をクリックして、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1f081-173">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

  - <span data-ttu-id="1f081-174">**次を含むコンテンツを検出する**:</span><span class="sxs-lookup"><span data-stu-id="1f081-174">**Detect content containing**:</span></span>
 
    <span data-ttu-id="1f081-p112">a. **[これらのいずれか]** をクリックして、**[正規表現]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f081-p112">a. Click **Any of these** and select **Regular expression**.</span></span>

    <span data-ttu-id="1f081-p113">b. 正規表現ボックスに、`(\s)(\d{9})(\s)` (空白文字で囲まれた 9 桁の数字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f081-p113">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space)</span></span>
  
  - <span data-ttu-id="1f081-179">**[補強要素]**: **[補強要素の追加]** をクリックして、**[このキーワード リストを含める]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f081-179">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

  - <span data-ttu-id="1f081-180">**[このキーワード リストを含める]** 領域が表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1f081-180">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

    - <span data-ttu-id="1f081-181">**[キーワード リスト]**: 次の値を入力します: 従業員、ID、社員証。</span><span class="sxs-lookup"><span data-stu-id="1f081-181">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

    - <span data-ttu-id="1f081-182">**[最低数]**: 既定値 1 のままにします。</span><span class="sxs-lookup"><span data-stu-id="1f081-182">**Minimum count**: Leave the default value 1.</span></span>

  - <span data-ttu-id="1f081-183">既定の **[信頼度]** 値 60 のままにします。</span><span class="sxs-lookup"><span data-stu-id="1f081-183">Leave the default **Confidence level** value 60.</span></span> 

  - <span data-ttu-id="1f081-184">既定の **[文字の近接]** 値 300 のままにします。</span><span class="sxs-lookup"><span data-stu-id="1f081-184">Leave the default **Character proximity** value 300.</span></span>

  <span data-ttu-id="1f081-185">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f081-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="1f081-186">**[確認と最終処理]** ページが開いたら、設定を確認して **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f081-186">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

5. <span data-ttu-id="1f081-p114">次のページでは、新しいカスタムの機密情報の種類をテストするように促されます。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。テストしない場合は、**[キャンセル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f081-p114">The next page encourages you to test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). Otherwise, click **Cancel**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1f081-190">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="1f081-190">How do you know this worked?</span></span>

<span data-ttu-id="1f081-191">新しい機密情報の種類が正常に作成されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f081-191">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="1f081-192">**[分類]** \> **[機密情報の種類]** に移動して、新しいカスタムの機密情報の種類が一覧に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f081-192">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="1f081-p115">新しいカスタムの機密情報の種類をテストします。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f081-p115">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="1f081-195">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を変更する</span><span class="sxs-lookup"><span data-stu-id="1f081-195">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="1f081-p116">**注**: カスタムの機密情報の種類のみを変更できます。組み込みの機密情報の種類は変更できません。ただし、PowerShell を使用して組み込みの機密情報の種類をエクスポートし、エクスポートしたものをカスタムの機密情報の種類としてインポートすることができます。詳細については、「[組み込みの機密情報の種類をカスタマイズする](customize-a-built-in-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f081-p116">**Note**: You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

<span data-ttu-id="1f081-199">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、変更するカスタムの機密情報の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f081-199">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select the custom sensitive information type that you want to modify.</span></span>

<span data-ttu-id="1f081-p117">ここでは、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成したときと同じオプションを選択できます。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する](#create-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f081-p117">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1f081-202">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="1f081-202">How do you know this worked?</span></span>

<span data-ttu-id="1f081-203">機密情報の種類が正常に変更されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f081-203">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="1f081-204">**[分類]** \> **[機密情報の種類]** に移動して、変更したカスタムの機密情報の種類のプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f081-204">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span>

  - <span data-ttu-id="1f081-p118">変更したカスタムの機密情報の種類をテストします。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f081-p118">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="1f081-207">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を削除する</span><span class="sxs-lookup"><span data-stu-id="1f081-207">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="1f081-208">**注**:</span><span class="sxs-lookup"><span data-stu-id="1f081-208">**Notes**:</span></span>

- <span data-ttu-id="1f081-209">カスタムの機密情報の種類のみを削除できます。組み込みの機密情報の種類は削除できません。</span><span class="sxs-lookup"><span data-stu-id="1f081-209">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="1f081-210">カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1f081-210">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="1f081-211">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、削除するカスタムの機密情報の種類を 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="1f081-211">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="1f081-212">ポップアップが開いたら、**[削除]** (複数選択した場合は **[機密情報の種類の削除]**) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f081-212">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

3. <span data-ttu-id="1f081-213">警告メッセージが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f081-213">In the warning that appears, click **yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1f081-214">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="1f081-214">How do you know this worked?</span></span>

<span data-ttu-id="1f081-215">カスタムの機密情報の種類が正常に削除されたことを確認するには、**[分類]** \> **[機密情報の種類]** に移動して、そのカスタムの機密情報の種類が一覧に表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f081-215">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>


## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="1f081-216">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする</span><span class="sxs-lookup"><span data-stu-id="1f081-216">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="1f081-217">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1f081-217">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="1f081-p119">テストするカスタムの機密情報の種類を 1 つ以上選択します。ポップアップが開いたら、**[種類のテスト]** (複数選択した場合は **[機密情報の種類のテスト]**) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f081-p119">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

3. <span data-ttu-id="1f081-220">ページが開いたら、ファイルをドラッグ アンド ドロップするか、**[参照]** をクリックしてからファイルを選択することで、テストするドキュメントをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="1f081-220">On the page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

4. <span data-ttu-id="1f081-221">**[テスト]** ボタンをクリックして、ファイル内のパターン マッチについてドキュメントをテストします。</span><span class="sxs-lookup"><span data-stu-id="1f081-221">Click the **Test** button to test the document for pattern matches in the file.</span></span>
