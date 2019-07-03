---
title: セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: セキュリティ/コンプライアンス センターのグラフィカル ユーザー インターフェイスで DLP のカスタム機密情報の種類を作成、変更、削除、およびテストする方法について説明します。
ms.openlocfilehash: 55e54bf8b49ec21bb5ed4f161efc4e5924ee52fb
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077743"
---
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="8a1ba-103">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8a1ba-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

## <a name="summary"></a><span data-ttu-id="8a1ba-104">概要</span><span class="sxs-lookup"><span data-stu-id="8a1ba-104">Summary</span></span>

<span data-ttu-id="8a1ba-105">セキュリティ/コンプライアンス センターで[カスタムの機密情報の種類](custom-sensitive-info-types.md)を作成するために、この記事をお読みください(「[https://protection.office.com](https://protection.office.com)」)。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-105">Read this article to create a [custom sensitive information type](custom-sensitive-info-types.md) in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="8a1ba-106">この方法を使用して作成されるカスタムの機密情報の種類は、`Microsoft.SCCManaged.CustomRulePack`という名前のルール パッケージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-106">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="8a1ba-107">PowerShell および Exact Data Match の機能を使用して、カスタムの機密情報の種類を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-107">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="8a1ba-108">これらの方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-108">To learn more about those methods, see:</span></span>
- <span data-ttu-id="8a1ba-109">[セキュリティ/コンプライアンス センター PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="8a1ba-109">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>
- [<span data-ttu-id="8a1ba-110">Exact Data Match (EMD) を使用して、DPL 向けのカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8a1ba-110">Create a custom sensitive information type with Exact Data Match (Preview)</span></span>](create-custom-sensitive-info-type-edm.md)

## <a name="before-you-begin"></a><span data-ttu-id="8a1ba-111">開始する前に</span><span class="sxs-lookup"><span data-stu-id="8a1ba-111">Before you begin</span></span>

- <span data-ttu-id="8a1ba-112">組織には、データ損失防止 (DLP) を含む Office 365 Enterprise などのサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-112">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="8a1ba-113">[メッセージング ポリシーとコンプライアンス サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-113">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="8a1ba-p104">カスタムの機密情報の種類では、正規表現 (RegEx) に精通している必要があります。テキストの処理に使用される Boost.RegEx (旧称 RegEx++) エンジンの詳細については、「[Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p104">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="8a1ba-p105">Microsoft カスタマー サービス & サポートは、カスタムのコンテンツ一致定義 (カスタムの分類や正規表現パターンの作成) の提供を支援できません。サポート エンジニアは、機能の制限付きサポート (たとえば、テスト目的でサンプルの正規表現パターンを提供したり、期待どおりにトリガーされない既存の正規表現パターンのトラブルシューティングを支援するなど) は提供できますが、カスタムのコンテンツ一致の開発がユーザーの要件を満たしたり、義務を果たすことを確約できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p105">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="8a1ba-p106">DLP は検索クローラーを使用して、SharePoint Online サイトと OneDrive for Business サイトの機密情報を識別および分類します。既存のコンテンツで新しいカスタムの機密情報の種類を特定するには、コンテンツを再クロールする必要があります。コンテンツはスケジュールに基づいて再クロールされますが、サイト コレクション、リスト、またはライブラリのコンテンツは手動で再クロールできます。詳細については、「[サイト、ライブラリ、またはリストのクロールとインデックス再作成を手動で要求する](https://docs.microsoft.com/sharepoint/crawl-site-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p106">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites. To identify your new custom sensitive information type in existing content, the content must be recrawled. Content is recrawled based on a schedule, but you can manually recrawl content for a site collection, list, or library. For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="8a1ba-122">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8a1ba-122">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="8a1ba-123">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-123">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="8a1ba-124">各設定については説明するまでもありませんが、ウィザードの関連ページには説明が記載されています。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-124">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="8a1ba-125">**[名前]**</span><span class="sxs-lookup"><span data-stu-id="8a1ba-125">**Name**</span></span>

- <span data-ttu-id="8a1ba-126">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="8a1ba-126">**Description**</span></span>

- <span data-ttu-id="8a1ba-127">**[近接性]**</span><span class="sxs-lookup"><span data-stu-id="8a1ba-127">**Proximity**</span></span>

- <span data-ttu-id="8a1ba-128">**[信頼度]**</span><span class="sxs-lookup"><span data-stu-id="8a1ba-128">**Confidence level**</span></span>

- <span data-ttu-id="8a1ba-129">**[プライマリ パターン要素]** (キーワード、正規表現、またはディクショナリ)</span><span class="sxs-lookup"><span data-stu-id="8a1ba-129">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="8a1ba-130">オプションの **[補強パターン要素]** (キーワード、正規表現、またはディクショナリ) および対応する **[最小コスト]** 値。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-130">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="8a1ba-p107">この例のシナリオ: キーワードの「従業員」、「ID」および「社員証」と共に、コンテンツに含まれる 9 桁の従業員番号を検出するために、カスタムの機密情報の種類が必要になりました。このカスタムの機密情報の種類を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p107">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="8a1ba-133">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-133">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![機密情報の種類と [作成] ボタンの場所](media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="8a1ba-135">**[名前と説明の選択]** ページが開いたら、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-135">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="8a1ba-136">**[名前]**: 従業員 ID。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-136">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="8a1ba-137">**[説明]**: 9 桁の Contoso 従業員 ID 番号を検出します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-137">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![名前と説明のページ](media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="8a1ba-139">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-139">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="8a1ba-140">**[一致の要件]** ページが開いたら、**[要素の追加]** をクリックして、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-140">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="8a1ba-141">**次を含むコンテンツを検出する**:</span><span class="sxs-lookup"><span data-stu-id="8a1ba-141">**Detect content containing**:</span></span>
 
      <span data-ttu-id="8a1ba-p108">a. **[これらのいずれか]** をクリックして、**[正規表現]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p108">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="8a1ba-p109">b. 正規表現ボックスに、`(\s)(\d{9})(\s)` (空白文字で囲まれた 9 桁の数字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p109">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="8a1ba-146">**[補強要素]**: **[補強要素の追加]** をクリックして、**[このキーワード リストを含める]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-146">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="8a1ba-147">**[このキーワード リストを含める]** 領域が表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-147">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="8a1ba-148">**[キーワード リスト]**: 次の値を入力します: 従業員、ID、社員証。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-148">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="8a1ba-149">**[最低数]**: 既定値 1 のままにします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-149">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="8a1ba-150">既定の **[信頼度]** 値 60 のままにします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-150">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="8a1ba-151">既定の **[文字の近接]** 値 300 のままにします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-151">Leave the default **Character proximity** value 300.</span></span>

    ![[一致の要件] ページ](media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="8a1ba-153">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8a1ba-154">**[確認と最終処理]** ページが開いたら、設定を確認して **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-154">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![[確認と最終処理] ページ](media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="8a1ba-p110">次のページでは、[**はい**] をクリックして新しいカスタムの機密情報の種類をテストするように促されます。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。ルールのテストを後で行うには、[**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p110">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![推奨をテストするページ](media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8a1ba-160">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="8a1ba-160">How do you know this worked?</span></span>

<span data-ttu-id="8a1ba-161">新しい機密情報の種類が正常に作成されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-161">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="8a1ba-162">**[分類]** \> **[機密情報の種類]** に移動して、新しいカスタムの機密情報の種類が一覧に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-162">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="8a1ba-p111">新しいカスタムの機密情報の種類をテストします。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p111">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="8a1ba-165">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を変更する</span><span class="sxs-lookup"><span data-stu-id="8a1ba-165">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="8a1ba-166">**注**:</span><span class="sxs-lookup"><span data-stu-id="8a1ba-166">**Notes**:</span></span>

- <span data-ttu-id="8a1ba-p112">カスタムの機密情報の種類のみを変更できます。組み込みの機密情報の種類は変更できません。ただし、PowerShell を使用して組み込みの機密情報の種類をエクスポートし、エクスポートしたものをカスタムの機密情報の種類としてインポートすることができます。詳細については、「[組み込みの機密情報の種類をカスタマイズする](customize-a-built-in-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p112">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="8a1ba-p113">変更できるのは、UI で作成したカスタムの機密情報の種類のみです。カスタムの機密情報の種類のルール パッケージをインポートするのに [PowerShell プロシージャ](create-a-custom-sensitive-information-type-in-scc-powershell.md)を使用した場合、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p113">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="8a1ba-172">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、変更するカスタムの機密情報の種類を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-172">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![機密情報の種類と [編集] ボタンの場所](media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="8a1ba-p114">ここでは、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成したときと同じオプションを選択できます。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する](#create-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p114">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8a1ba-176">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="8a1ba-176">How do you know this worked?</span></span>

<span data-ttu-id="8a1ba-177">機密情報の種類が正常に変更されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-177">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="8a1ba-178">**[分類]** \> **[機密情報の種類]** に移動して、変更したカスタムの機密情報の種類のプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-178">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="8a1ba-p115">変更したカスタムの機密情報の種類をテストします。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p115">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="8a1ba-181">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を削除する</span><span class="sxs-lookup"><span data-stu-id="8a1ba-181">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="8a1ba-182">**注**:</span><span class="sxs-lookup"><span data-stu-id="8a1ba-182">**Notes**:</span></span>

- <span data-ttu-id="8a1ba-183">カスタムの機密情報の種類のみを削除できます。組み込みの機密情報の種類は削除できません。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-183">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="8a1ba-184">カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-184">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="8a1ba-185">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、削除するカスタムの機密情報の種類を 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-185">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="8a1ba-186">ポップアップが開いたら、**[削除]** (複数選択した場合は **[機密情報の種類の削除]**) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-186">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![機密情報の種類と [削除] ボタンの場所](media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="8a1ba-188">警告メッセージが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-188">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8a1ba-189">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="8a1ba-189">How do you know this worked?</span></span>

<span data-ttu-id="8a1ba-190">カスタムの機密情報の種類が正常に削除されたことを確認するには、**[分類]** \> **[機密情報の種類]** に移動して、そのカスタムの機密情報の種類が一覧に表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-190">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="8a1ba-191">セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする</span><span class="sxs-lookup"><span data-stu-id="8a1ba-191">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="8a1ba-192">セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-192">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="8a1ba-p116">テストするカスタムの機密情報の種類を 1 つ以上選択します。ポップアップが開いたら、**[種類のテスト]** (複数選択した場合は **[機密情報の種類のテスト]**) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-p116">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![機密情報の種類と [種類のテスト] ボタンの場所](media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="8a1ba-196">[**テストの対象ファイルのアップロード**] ページが開いたら、ファイルをドラッグ アンド ドロップするか、または [**参照**] をクリックしてファイルを選択し、テストの対象ドキュメントをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-196">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![[テストの対象ファイルのアップロード] ページ](media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="8a1ba-198">**[テスト]** ボタンをクリックして、ファイル内のパターン マッチについてドキュメントをテストします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-198">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="8a1ba-199">[**照合結果**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a1ba-199">On the **Match results** page, click **Finish**.</span></span>

    ![照合結果](media/scc-cust-sens-info-type-test-results.png)